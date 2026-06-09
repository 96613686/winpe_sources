# CTabWindow::LCIEWinProc(HWND__ *,uint,unsigned __int64,__int64,ulong,_IsoMessage *,_IsoComponent *,ulong,bool *)

- ea: `0x180031fb0`
- end: `0x180032f88`
- name: `?LCIEWinProc@CTabWindow@@IEAA_JPEAUHWND__@@I_K_JKPEAU_IsoMessage@@PEAU_IsoComponent@@KPEA_N@Z`
- size: `4056`
- prototype: `__int64 __usercall@<rax>(CTabWindow *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, unsigned int, unsigned int, struct _IsoMessage *, struct _IsoComponent *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `80`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180058df0`

## callees

- `0x18000b9e0`
- `0x18000c5c0`
- `0x18002acc0`
- `0x180031fb0`
- `0x180033280`
- `0x180034518`
- `0x18005794c`
- `0x1800904a8`
- `0x180093ec0`
- `0x1800b8f46`
- `0x1801ba544`
- `0x1801bd0b8`
- `0x1801bd118`
- `0x1801bd178`
- `0x1801de6c8`
- `0x1801ef2bc`
- `0x18022c61c`
- `0x18022d9fc`
- `0x18022dbfc`
- `0x18022e668`
- `0x180244c94`
- `0x18024ffc0`
- `0x180252d2c`
- `0x180253cd4`
- `0x180255f58`
- `0x180258da8`
- `0x18025a630`
- `0x18025a690`
- `0x18025a6f0`
- `0x18025a750`
- `0x18025b3a0`
- `0x18025b8fc`
- `0x18025bf48`
- `0x18025c508`
- `0x18025c6ec`
- `0x18025c8d4`
- `0x18025cb64`
- `0x18025d2e0`
- `0x18025d4b8`
- `0x18025d568`
- `0x18025d5cc`
- `0x18025d614`
- `0x18025d6e4`
- `0x18025d760`
- `0x18025d7f4`
- `0x18025d888`
- `0x18025d91c`
- `0x18025d998`
- `0x18025da30`
- `0x18025da8c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180032c12`
- `KERNEL32!LeaveCriticalSection` at `0x180032c12`
- `KERNEL32!EnterCriticalSection` at `0x180032bac`
- `KERNEL32!EnterCriticalSection` at `0x180032bac`
- `USER32!KillTimer` at `0x180032c7b`
- `USER32!KillTimer` at `0x180032ca0`
- `USER32!KillTimer` at `0x180032c7b`
- `USER32!KillTimer` at `0x180032ca0`
- `USER32!PostMessageW` at `0x1800322e9`
- `USER32!PostMessageW` at `0x1800322e9`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180032bc7`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180032bc7`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180032299`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180032299`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18003228f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18003228f`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003274b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032790`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800327c6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032807`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003282a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003284d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032870`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800328bc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800328f3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032916`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032939`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032958`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003297b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003299e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800329bd`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800329dc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800329fb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032a1e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032a76`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032aae`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032acd`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032ae8`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b05`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b22`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b41`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b5e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b7b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032c3d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003274b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032790`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800327c6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032807`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003282a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003284d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032870`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800328bc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800328f3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032916`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032939`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032958`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003297b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003299e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800329bd`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800329dc`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800329fb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032a1e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032a76`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032aae`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032acd`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032ae8`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b05`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b22`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b41`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b5e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032b7b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180032c3d`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x180032062`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x180032062`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180031fd5`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180031fd5`

## pseudocode

```c

```
