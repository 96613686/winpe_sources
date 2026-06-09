# CWmiObjPath::_CreateCscUserConfigObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)

- ea: `0x180022a5c`
- end: `0x180022b06`
- name: `?_CreateCscUserConfigObject@CWmiObjPath@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z`
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

- `0x180022ab6`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CWmiObjPath::_CreateCscUserConfigObject(
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
  v17 = L"Win32_OfflineFilesUserConfiguration";
  _InterlockedIncrement(&g_cUstRefDll);
  v7 = &COfflineFilesUserConfiguration::`vftable'{for `UstCommon::CRefCounted'};
  v9 = &UstCommon::CWmiLanternObject::`vftable';
  WbemClassObject = UstCommon::CWmiObject::CreateWbemClassObject((UstCommon::CWmiObject *)&v7, a2, a3, a5);
  UstCommon::CWmiObject::~CWmiObject((UstCommon::CWmiObject *)&v7);
  return WbemClassObject;
}

```

## disassembly

```asm
0x180022a5c  mov     [rsp-8+arg_0], rbx
0x180022a61  push    rbp
0x180022a62  mov     rbp, rsp
0x180022a65  sub     rsp, 70h
0x180022a69  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x180022a70  mov     [rbp+var_50], rax
0x180022a74  xor     ecx, ecx
0x180022a76  mov     [rbp+var_48], ecx
0x180022a79  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180022a80  mov     [rbp+var_40], rax
0x180022a84  mov     [rbp+var_38], ecx
0x180022a87  mov     [rbp+var_30], rcx
0x180022a8b  mov     [rbp+var_28], ecx
0x180022a8e  mov     [rbp+var_20], rcx
0x180022a92  mov     [rbp+var_18], ecx
0x180022a95  mov     [rbp+var_10], rcx
0x180022a99  mov     [rbp+var_24], 10h
0x180022aa0  lea     rax, ??_7CWmiObject@UstCommon@@6BCRefCounted@1@@; const UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'}
0x180022aa7  mov     [rbp+var_50], rax
0x180022aab  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180022ab2  mov     [rbp+var_40], rax
0x180022ab6  lea     rax, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x180022abd  mov     [rbp+var_8], rax
0x180022ac1  lock inc cs:?g_cUstRefDll@@3JA; long g_cUstRefDll
0x180022ac8  lea     rax, ??_7COfflineFilesUserConfiguration@@6BCRefCounted@UstCommon@@@; const COfflineFilesUserConfiguration::`vftable'{for `UstCommon::CRefCounted'}
0x180022acf  mov     [rbp+var_50], rax
0x180022ad3  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180022ada  mov     [rbp+var_40], rax
0x180022ade  mov     r9, [rbp+arg_20]; struct IWbemClassObject **
0x180022ae2  lea     rcx, [rbp+var_50]; this
0x180022ae6  call    ?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x180022aeb  mov     ebx, eax
0x180022aed  lea     rcx, [rbp+var_50]; this
0x180022af1  call    ??1CWmiObject@UstCommon@@UEAA@XZ; UstCommon::CWmiObject::~CWmiObject(void)
0x180022af6  mov     eax, ebx
0x180022af8  mov     rbx, [rsp+70h+arg_0]
0x180022b00  add     rsp, 70h
0x180022b04  pop     rbp
0x180022b05  retn
```
