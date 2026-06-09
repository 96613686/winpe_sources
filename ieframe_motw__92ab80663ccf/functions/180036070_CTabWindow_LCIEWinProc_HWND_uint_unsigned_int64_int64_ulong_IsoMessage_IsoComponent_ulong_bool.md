# CTabWindow::LCIEWinProc(HWND__ *,uint,unsigned __int64,__int64,ulong,_IsoMessage *,_IsoComponent *,ulong,bool *)

- ea: `0x180036070`
- end: `0x180037140`
- name: `?LCIEWinProc@CTabWindow@@IEAA_JPEAUHWND__@@I_K_JKPEAU_IsoMessage@@PEAU_IsoComponent@@KPEA_N@Z`
- size: `4304`
- prototype: `__int64 __usercall@<rax>(CTabWindow *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, unsigned int, unsigned int, struct _IsoMessage *, struct _IsoComponent *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `80`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c8f0`

## callees

- `0x180005030`
- `0x180007010`
- `0x1800096a0`
- `0x180036070`
- `0x18003746c`
- `0x1800388cc`
- `0x18005ba40`
- `0x18009759c`
- `0x18009b248`
- `0x1800bfc56`
- `0x1801d06f0`
- `0x1801d3808`
- `0x1801d3874`
- `0x1801d38e0`
- `0x1801f7564`
- `0x180208d48`
- `0x18024915c`
- `0x18024a628`
- `0x18024a830`
- `0x18024b2ac`
- `0x180262e78`
- `0x18026eeb8`
- `0x180271e2c`
- `0x180272e84`
- `0x1802752e0`
- `0x18027843c`
- `0x180279e00`
- `0x180279e6c`
- `0x180279ed8`
- `0x180279f44`
- `0x18027ac4c`
- `0x18027b1c4`
- `0x18027b858`
- `0x18027be98`
- `0x18027c098`
- `0x18027c29c`
- `0x18027c560`
- `0x18027cd5c`
- `0x18027cf40`
- `0x18027cff0`
- `0x18027d054`
- `0x18027d0a4`
- `0x18027d178`
- `0x18027d1f8`
- `0x18027d298`
- `0x18027d338`
- `0x18027d3d8`
- `0x18027d458`
- `0x18027d4fc`
- `0x18027d558`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180036dae`
- `KERNEL32!LeaveCriticalSection` at `0x180036dae`
- `KERNEL32!EnterCriticalSection` at `0x180036d3c`
- `KERNEL32!EnterCriticalSection` at `0x180036d3c`
- `USER32!KillTimer` at `0x180036e26`
- `USER32!KillTimer` at `0x180036e51`
- `USER32!KillTimer` at `0x180036e26`
- `USER32!KillTimer` at `0x180036e51`
- `USER32!PostMessageW` at `0x1800363c9`
- `USER32!PostMessageW` at `0x1800363c9`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180036d5d`
- `iertutil!__imp_DSA_GetItemPtr` at `0x180036d5d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180036373`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180036373`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180036363`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180036363`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036835`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036884`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800368c0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036907`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036930`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036959`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036982`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800369d4`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a11`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a3a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a63`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a88`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036ab1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036ada`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036aff`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036b24`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036b49`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036b72`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036bd0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c0e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c33`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c54`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c77`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c9a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036cbf`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036ce2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036d05`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036de2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036835`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036884`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800368c0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036907`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036930`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036959`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036982`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800369d4`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a11`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a3a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a63`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036a88`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036ab1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036ada`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036aff`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036b24`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036b49`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036b72`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036bd0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c0e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c33`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c54`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c77`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036c9a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036cbf`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036ce2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036d05`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180036de2`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x18003612c`
- `msIso!__imp_?IsoArtifactInstanceIntegrityLevel@@YA?AW4_IsoIntegrity@@K@Z` at `0x18003612c`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180036095`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x180036095`

## pseudocode

```c

```
