# CWmiObjPath::_CreateCscMachineConfigObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)

- ea: `0x1800229ac`
- end: `0x180022a56`
- name: `?_CreateCscMachineConfigObject@CWmiObjPath@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(CWmiObjPath *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IOfflineFilesCache *, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002273c`

## callees

- `0x180027200`
- `0x180027264`

## string_xrefs

- `0x180022a06`: `Win32_OfflineFilesMachineConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWmiObjPath::_CreateCscMachineConfigObject(
        CWmiObjPath *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IOfflineFilesCache *a4,
        struct IWbemClassObject **a5)
{
  unsigned int WbemClassObject; // ebx
  void **v7; // [rsp+20h] [rbp-50h] BYREF
  int v8; // [rsp+28h] [rbp-48h]
  void **v9; // [rsp+30h] [rbp-40h]
  int v10; // [rsp+38h] [rbp-38h]
  __int64 v11; // [rsp+40h] [rbp-30h]
  int v12; // [rsp+48h] [rbp-28h]
  int v13; // [rsp+4Ch] [rbp-24h]
  __int64 v14; // [rsp+50h] [rbp-20h]
  int v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+60h] [rbp-10h]
  const WCHAR *v17; // [rsp+68h] [rbp-8h]

  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v13 = 16;
  v17 = L"Win32_OfflineFilesMachineConfiguration";
  _InterlockedIncrement(&g_cUstRefDll);
  v7 = &COfflineFilesMachineConfiguration::`vftable'{for `UstCommon::CRefCounted'};
  v9 = &UstCommon::CWmiLanternObject::`vftable';
  WbemClassObject = UstCommon::CWmiObject::CreateWbemClassObject((UstCommon::CWmiObject *)&v7, a2, a3, a5);
  UstCommon::CWmiObject::~CWmiObject((UstCommon::CWmiObject *)&v7);
  return WbemClassObject;
}

```

## disassembly

```asm
0x1800229ac  mov     [rsp-8+arg_0], rbx
0x1800229b1  push    rbp
0x1800229b2  mov     rbp, rsp
0x1800229b5  sub     rsp, 70h
0x1800229b9  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x1800229c0  mov     [rbp+var_50], rax
0x1800229c4  xor     ecx, ecx
0x1800229c6  mov     [rbp+var_48], ecx
0x1800229c9  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x1800229d0  mov     [rbp+var_40], rax
0x1800229d4  mov     [rbp+var_38], ecx
0x1800229d7  mov     [rbp+var_30], rcx
0x1800229db  mov     [rbp+var_28], ecx
0x1800229de  mov     [rbp+var_20], rcx
0x1800229e2  mov     [rbp+var_18], ecx
0x1800229e5  mov     [rbp+var_10], rcx
0x1800229e9  mov     [rbp+var_24], 10h
0x1800229f0  lea     rax, ??_7CWmiObject@UstCommon@@6BCRefCounted@1@@; const UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'}
0x1800229f7  mov     [rbp+var_50], rax
0x1800229fb  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180022a02  mov     [rbp+var_40], rax
0x180022a06  lea     rax, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x180022a0d  mov     [rbp+var_8], rax
0x180022a11  lock inc cs:?g_cUstRefDll@@3JA; long g_cUstRefDll
0x180022a18  lea     rax, ??_7COfflineFilesMachineConfiguration@@6BCRefCounted@UstCommon@@@; const COfflineFilesMachineConfiguration::`vftable'{for `UstCommon::CRefCounted'}
0x180022a1f  mov     [rbp+var_50], rax
0x180022a23  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180022a2a  mov     [rbp+var_40], rax
0x180022a2e  mov     r9, [rbp+arg_20]; struct IWbemClassObject **
0x180022a32  lea     rcx, [rbp+var_50]; this
0x180022a36  call    ?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x180022a3b  mov     ebx, eax
0x180022a3d  lea     rcx, [rbp+var_50]; this
0x180022a41  call    ??1CWmiObject@UstCommon@@UEAA@XZ; UstCommon::CWmiObject::~CWmiObject(void)
0x180022a46  mov     eax, ebx
0x180022a48  mov     rbx, [rsp+70h+arg_0]
0x180022a50  add     rsp, 70h
0x180022a54  pop     rbp
0x180022a55  retn
```
