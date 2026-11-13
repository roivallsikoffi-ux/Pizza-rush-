// Remplace les pubs simulées par AdMob quand le jeu tourne dans l'app Android.
(function () {
  const C = window.Capacitor;
  if (!C || !C.isNativePlatform || !C.isNativePlatform()) return;
  const AdMob = C.Plugins && C.Plugins.AdMob;
  if (!AdMob) return;
  const TESTING = true;
  const REWARDED_ID = 'ca-app-pub-5763188155984547/4012727071';
  const INTERSTITIAL_ID = 'ca-app-pub-5763188155984547/1985329533';
  AdMob.initialize({}).catch(console.error);

  MONETIZATION.showRewardedAd = async function (onDone) {
    try {
      await AdMob.prepareRewardVideoAd({ adId: REWARDED_ID, isTesting: TESTING });
      await AdMob.showRewardVideoAd();
      onDone();
    } catch (e) { console.error(e); }
  };
  MONETIZATION.showInterstitial = async function () {
    try {
      await AdMob.prepareInterstitial({ adId: INTERSTITIAL_ID, isTesting: TESTING });
      await AdMob.showInterstitial();
    } catch (e) { console.error(e); }
  };
  MONETIZATION.purchase = function () { alert('Achat bientôt disponible.'); };
})();
