# CCscWmiSingletonEnum<COfflineFilesMachineConfiguration>::Initialize(IWbemServices *,IWbemContext *)

- ea: `0x180025248`
- end: `0x18002531a`
- name: `?Initialize@?$CCscWmiSingletonEnum@VCOfflineFilesMachineConfiguration@@@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023b18`

## callees

- `0x180016df8`
- `0x180025248`
- `0x180027200`
- `0x180027264`

## string_xrefs

- `0x1800252c9`: `Win32_OfflineFilesMachineConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCscWmiSingletonEnum<COfflineFilesMachineConfiguration>::Initialize(
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
  v19 = L"Win32_OfflineFilesMachineConfiguration";
  _InterlockedIncrement(&g_cUstRefDll);
  v9 = &COfflineFilesMachineConfiguration::`vftable'{for `UstCommon::CRefCounted'};
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
0x180025248  push    rbp
0x18002524a  push    rbx
0x18002524b  push    rsi
0x18002524c  push    rdi
0x18002524d  mov     rbp, rsp
0x180025250  sub     rsp, 78h
0x180025254  mov     rbx, r8
0x180025257  mov     rsi, rdx
0x18002525a  mov     rdi, rcx
0x18002525d  add     rcx, 10h; struct IUnknown **
0x180025261  cmp     [rcx], rdx
0x180025264  jz      short loc_18002526B
0x180025266  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002526b  lea     rcx, [rdi+18h]; struct IUnknown **
0x18002526f  cmp     [rcx], rbx
0x180025272  jz      short loc_18002527C
0x180025274  mov     rdx, rbx; struct IUnknown *
0x180025277  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002527c  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x180025283  mov     [rbp+var_58], rax
0x180025287  xor     ecx, ecx
0x180025289  mov     [rbp+var_50], ecx
0x18002528c  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180025293  mov     [rbp+var_48], rax
0x180025297  mov     [rbp+var_40], ecx
0x18002529a  mov     [rbp+var_38], rcx
0x18002529e  mov     [rbp+var_30], ecx
0x1800252a1  mov     [rbp+var_28], rcx
0x1800252a5  mov     [rbp+var_20], ecx
0x1800252a8  mov     [rbp+var_18], rcx
0x1800252ac  mov     [rbp+var_2C], 10h
0x1800252b3  lea     rax, ??_7CWmiObject@UstCommon@@6BCRefCounted@1@@; const UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'}
0x1800252ba  mov     [rbp+var_58], rax
0x1800252be  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x1800252c5  mov     [rbp+var_48], rax
0x1800252c9  lea     rax, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x1800252d0  mov     [rbp+var_10], rax
0x1800252d4  lock inc cs:?g_cUstRefDll@@3JA; long g_cUstRefDll
0x1800252db  lea     rax, ??_7COfflineFilesMachineConfiguration@@6BCRefCounted@UstCommon@@@; const COfflineFilesMachineConfiguration::`vftable'{for `UstCommon::CRefCounted'}
0x1800252e2  mov     [rbp+var_58], rax
0x1800252e6  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x1800252ed  mov     [rbp+var_48], rax
0x1800252f1  lea     r9, [rdi+20h]; struct IWbemClassObject **
0x1800252f5  mov     r8, rbx; struct IWbemContext *
0x1800252f8  mov     rdx, rsi; struct IWbemServices *
0x1800252fb  lea     rcx, [rbp+var_58]; this
0x1800252ff  call    ?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x180025304  mov     ebx, eax
0x180025306  lea     rcx, [rbp+var_58]; this
0x18002530a  call    ??1CWmiObject@UstCommon@@UEAA@XZ; UstCommon::CWmiObject::~CWmiObject(void)
0x18002530f  mov     eax, ebx
0x180025311  add     rsp, 78h
0x180025315  pop     rdi
0x180025316  pop     rsi
0x180025317  pop     rbx
0x180025318  pop     rbp
0x180025319  retn
```
