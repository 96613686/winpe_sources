# CCscWmiSingletonEnum<COfflineFilesUserConfiguration>::Initialize(IWbemServices *,IWbemContext *)

- ea: `0x180025320`
- end: `0x1800253f2`
- name: `?Initialize@?$CCscWmiSingletonEnum@VCOfflineFilesUserConfiguration@@@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023bac`

## callees

- `0x180016df8`
- `0x180025320`
- `0x180027200`
- `0x180027264`

## string_xrefs

- `0x1800253a1`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall CCscWmiSingletonEnum<COfflineFilesUserConfiguration>::Initialize(
        __int64 a1,
        struct IUnknown *a2,
        struct IUnknown *a3)
{
  struct IUnknown **v6; // rcx
  unsigned int WbemClassObject; // ebx
  void **v9; // [rsp+20h] [rbp-58h] BYREF
  int v10; // [rsp+28h] [rbp-50h]
  void **v11; // [rsp+30h] [rbp-48h]
  int v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+40h] [rbp-38h]
  int v14; // [rsp+48h] [rbp-30h]
  int v15; // [rsp+4Ch] [rbp-2Ch]
  __int64 v16; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-20h]
  __int64 v18; // [rsp+60h] [rbp-18h]
  const WCHAR *v19; // [rsp+68h] [rbp-10h]

  v6 = (struct IUnknown **)(a1 + 16);
  if ( *v6 != a2 )
    ATL::AtlComPtrAssign(v6, a2);
  if ( *(struct IUnknown **)(a1 + 24) != a3 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 24), a3);
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 16;
  v19 = L"Win32_OfflineFilesUserConfiguration";
  _InterlockedIncrement(&g_cUstRefDll);
  v9 = &COfflineFilesUserConfiguration::`vftable'{for `UstCommon::CRefCounted'};
  v11 = &UstCommon::CWmiLanternObject::`vftable';
  WbemClassObject = UstCommon::CWmiObject::CreateWbemClassObject(
                      (UstCommon::CWmiObject *)&v9,
                      (struct IWbemServices *)a2,
                      (struct IWbemContext *)a3,
                      (struct IWbemClassObject **)(a1 + 32));
  UstCommon::CWmiObject::~CWmiObject((UstCommon::CWmiObject *)&v9);
  return WbemClassObject;
}

```

## disassembly

```asm
0x180025320  push    rbp
0x180025322  push    rbx
0x180025323  push    rsi
0x180025324  push    rdi
0x180025325  mov     rbp, rsp
0x180025328  sub     rsp, 78h
0x18002532c  mov     rbx, r8
0x18002532f  mov     rsi, rdx
0x180025332  mov     rdi, rcx
0x180025335  add     rcx, 10h; struct IUnknown **
0x180025339  cmp     [rcx], rdx
0x18002533c  jz      short loc_180025343
0x18002533e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180025343  lea     rcx, [rdi+18h]; struct IUnknown **
0x180025347  cmp     [rcx], rbx
0x18002534a  jz      short loc_180025354
0x18002534c  mov     rdx, rbx; struct IUnknown *
0x18002534f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180025354  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x18002535b  mov     [rbp+var_58], rax
0x18002535f  xor     ecx, ecx
0x180025361  mov     [rbp+var_50], ecx
0x180025364  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x18002536b  mov     [rbp+var_48], rax
0x18002536f  mov     [rbp+var_40], ecx
0x180025372  mov     [rbp+var_38], rcx
0x180025376  mov     [rbp+var_30], ecx
0x180025379  mov     [rbp+var_28], rcx
0x18002537d  mov     [rbp+var_20], ecx
0x180025380  mov     [rbp+var_18], rcx
0x180025384  mov     [rbp+var_2C], 10h
0x18002538b  lea     rax, ??_7CWmiObject@UstCommon@@6BCRefCounted@1@@; const UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'}
0x180025392  mov     [rbp+var_58], rax
0x180025396  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x18002539d  mov     [rbp+var_48], rax
0x1800253a1  lea     rax, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x1800253a8  mov     [rbp+var_10], rax
0x1800253ac  lock inc cs:?g_cUstRefDll@@3JA; long g_cUstRefDll
0x1800253b3  lea     rax, ??_7COfflineFilesUserConfiguration@@6BCRefCounted@UstCommon@@@; const COfflineFilesUserConfiguration::`vftable'{for `UstCommon::CRefCounted'}
0x1800253ba  mov     [rbp+var_58], rax
0x1800253be  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x1800253c5  mov     [rbp+var_48], rax
0x1800253c9  lea     r9, [rdi+20h]; struct IWbemClassObject **
0x1800253cd  mov     r8, rbx; struct IWbemContext *
0x1800253d0  mov     rdx, rsi; struct IWbemServices *
0x1800253d3  lea     rcx, [rbp+var_58]; this
0x1800253d7  call    ?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x1800253dc  mov     ebx, eax
0x1800253de  lea     rcx, [rbp+var_58]; this
0x1800253e2  call    ??1CWmiObject@UstCommon@@UEAA@XZ; UstCommon::CWmiObject::~CWmiObject(void)
0x1800253e7  mov     eax, ebx
0x1800253e9  add     rsp, 78h
0x1800253ed  pop     rdi
0x1800253ee  pop     rsi
0x1800253ef  pop     rbx
0x1800253f0  pop     rbp
0x1800253f1  retn
```
