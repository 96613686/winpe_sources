# Windows::Internal::WiFiCloudStore::TriggerTask(ushort const *)

- ea: `0x180099c64`
- end: `0x180099f8c`
- name: `?TriggerTask@WiFiCloudStore@Internal@Windows@@YAJPEBG@Z`
- size: `808`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801290e4`

## callees

- `0x180015608`
- `0x18005ebf8`
- `0x18009753c`
- `0x180099c64`
- `0x180099f94`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180099cab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180099cab`
- `OLEAUT32!__imp_SysAllocString` at `0x180099d83`
- `OLEAUT32!__imp_SysAllocString` at `0x180099e12`
- `OLEAUT32!__imp_SysAllocString` at `0x180099ea7`
- `OLEAUT32!__imp_SysAllocString` at `0x180099d83`
- `OLEAUT32!__imp_SysAllocString` at `0x180099e12`
- `OLEAUT32!__imp_SysAllocString` at `0x180099ea7`
- `OLEAUT32!__imp_VariantInit` at `0x180099cd6`
- `OLEAUT32!__imp_VariantInit` at `0x180099cd6`
- `OLEAUT32!__imp_VariantClear` at `0x180099f58`
- `OLEAUT32!__imp_VariantClear` at `0x180099f58`

## string_xrefs

- `0x180099cc0`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099d6b`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099d9e`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099dfa`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099e2d`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099e89`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099ebf`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180099f0f`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::WiFiCloudStore::TriggerTask(OLECHAR *psz, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // eax
  __int64 v5; // rdx
  BSTR v6; // rbx
  const char *v7; // r9
  LPVOID v8; // rsi
  __int64 (__fastcall *v9)(LPVOID, BSTR, __int64 *); // rdi
  int v10; // eax
  __int64 v11; // rdx
  BSTR v12; // rbx
  const char *v13; // r9
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, BSTR, __int64 *); // rdi
  int v16; // eax
  const char *v17; // r9
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  const char *v22; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-D8h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-C8h] BYREF
  BSTR v26; // [rsp+48h] [rbp-B0h] BYREF
  BSTR v27[2]; // [rsp+50h] [rbp-A8h] BYREF
  VARIANTARG v28; // [rsp+60h] [rbp-98h] BYREF
  VARIANTARG v29; // [rsp+80h] [rbp-78h] BYREF
  VARIANTARG v30; // [rsp+A0h] [rbp-58h] BYREF
  VARIANTARG v31; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  LPVOID v33; // [rsp+108h] [rbp+10h] BYREF
  __int64 v34; // [rsp+110h] [rbp+18h] BYREF
  __int64 v35; // [rsp+118h] [rbp+20h] BYREF

  v33 = 0;
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v33, a2);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v33);
  try
  {
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v3,
        ppv);
    VariantInit(&pvarg);
    v29 = pvarg;
    v30 = pvarg;
    v31 = pvarg;
    v28 = pvarg;
    v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v33 + 80LL))(
           v33,
           &v28,
           &v31,
           &v30);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v4,
        (int)&v29);
    v6 = SysAllocString(L"\\Microsoft\\Windows\\WlanSvc");
    v27[0] = v6;
    if ( !v6 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        v7);
    v35 = 0;
    v8 = v33;
    v9 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v33 + 56LL);
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v35, v5);
    v10 = v9(v8, v6, &v35);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v10,
        (int)&v29);
    v12 = SysAllocString(L"CDSSync");
    v26 = v12;
    if ( !v12 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        v13);
    v34 = 0;
    v14 = v35;
    v15 = *(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v35 + 104LL);
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v34, v11);
    v16 = v15(v14, v12, &v34);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v16,
        (int)&v29);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( !pvarg.llVal )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        v17);
    v28 = pvarg;
    v18 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v34 + 96LL))(v34, &v28, 0);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v18,
        (int)&v29);
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v34, v19);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v35, v20);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v27);
    VariantClear(&pvarg);
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v33, v21);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v33) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x48,
                     (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                     v22);
    return (unsigned int)v33;
  }
  return result;
}

```

## disassembly

```asm
0x180099c64  mov     rax, rsp
0x180099c67  mov     [rax+8], rbx
0x180099c6b  push    rsi
0x180099c6c  push    rdi
0x180099c6d  push    r14
0x180099c6f  sub     rsp, 0E0h
0x180099c76  mov     r14, rcx
0x180099c79  mov     qword ptr [rax+10h], 0
0x180099c81  lea     rcx, [rax+10h]
0x180099c85  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180099c8a  lea     rax, [rsp+0F8h+arg_8]
0x180099c92  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x180099c97  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180099c9e  xor     edx, edx; pUnkOuter
0x180099ca0  lea     r8d, [rdx+1]; dwClsContext
0x180099ca4  lea     rcx, CLSID_TaskScheduler; rclsid
0x180099cab  call    cs:__imp_CoCreateInstance
0x180099cb1  mov     rcx, [rsp+0F8h]; this
0x180099cb9  test    eax, eax
0x180099cbb  jns     short loc_180099CD1
0x180099cbd  mov     r9d, eax; char *
0x180099cc0  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099cc7  mov     edx, 30h ; '0'; void *
0x180099ccc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099cd1  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180099cd6  call    cs:__imp_VariantInit
0x180099cdc  nop
0x180099cdd  mov     rcx, [rsp+0F8h+arg_8]
0x180099ce5  movups  xmm1, xmmword ptr [rsp+0F8h+pvarg]
0x180099cea  movaps  xmmword ptr [rsp+0F8h+var_78], xmm1
0x180099cf2  movsd   xmm0, qword ptr [rsp+0F8h+pvarg+10h]
0x180099cf8  movsd   [rsp+0F8h+var_68], xmm0
0x180099d01  movaps  [rsp+0F8h+var_58], xmm1
0x180099d09  movsd   [rsp+0F8h+var_48], xmm0
0x180099d12  movaps  [rsp+0F8h+var_38], xmm1
0x180099d1a  movsd   [rsp+0F8h+var_28], xmm0
0x180099d23  movaps  [rsp+0F8h+var_98], xmm1
0x180099d28  movsd   [rsp+0F8h+var_88], xmm0
0x180099d2e  mov     rax, [rcx]
0x180099d31  lea     rdx, [rsp+0F8h+var_78]
0x180099d39  mov     qword ptr [rsp+0F8h+ppv], rdx; int
0x180099d3e  lea     r9, [rsp+0F8h+var_58]
0x180099d46  lea     r8, [rsp+0F8h+var_38]
0x180099d4e  lea     rdx, [rsp+0F8h+var_98]
0x180099d53  mov     rax, [rax+50h]
0x180099d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d5c  mov     rcx, [rsp+0F8h]; this
0x180099d64  test    eax, eax
0x180099d66  jns     short loc_180099D7C
0x180099d68  mov     r9d, eax; char *
0x180099d6b  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099d72  mov     edx, 33h ; '3'; void *
0x180099d77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099d7c  lea     rcx, psz; "\\Microsoft\\Windows\\WlanSvc"
0x180099d83  call    cs:__imp_SysAllocString
0x180099d89  mov     rbx, rax
0x180099d8c  mov     [rsp+0F8h+var_A8], rax
0x180099d91  mov     rcx, [rsp+0F8h]; this
0x180099d99  test    rax, rax
0x180099d9c  jnz     short loc_180099DAD
0x180099d9e  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099da5  lea     edx, [rax+36h]; void *
0x180099da8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180099dad  mov     [rsp+0F8h+arg_18], 0
0x180099db9  mov     rsi, [rsp+0F8h+arg_8]
0x180099dc1  mov     rax, [rsi]
0x180099dc4  mov     rdi, [rax+38h]
0x180099dc8  lea     rcx, [rsp+0F8h+arg_18]
0x180099dd0  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180099dd5  lea     r8, [rsp+0F8h+arg_18]
0x180099ddd  mov     rdx, rbx
0x180099de0  mov     rcx, rsi
0x180099de3  mov     rax, rdi
0x180099de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099deb  mov     rcx, [rsp+0F8h]; this
0x180099df3  test    eax, eax
0x180099df5  jns     short loc_180099E0B
0x180099df7  mov     r9d, eax; char *
0x180099dfa  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099e01  mov     edx, 39h ; '9'; void *
0x180099e06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099e0b  lea     rcx, aCdssync; "CDSSync"
0x180099e12  call    cs:__imp_SysAllocString
0x180099e18  mov     rbx, rax
0x180099e1b  mov     [rsp+0F8h+var_B0], rax
0x180099e20  mov     rcx, [rsp+0F8h]; this
0x180099e28  test    rax, rax
0x180099e2b  jnz     short loc_180099E3C
0x180099e2d  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099e34  lea     edx, [rax+3Ch]; void *
0x180099e37  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180099e3c  mov     [rsp+0F8h+arg_10], 0
0x180099e48  mov     rsi, [rsp+0F8h+arg_18]
0x180099e50  mov     rax, [rsi]
0x180099e53  mov     rdi, [rax+68h]
0x180099e57  lea     rcx, [rsp+0F8h+arg_10]
0x180099e5f  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180099e64  lea     r8, [rsp+0F8h+arg_10]
0x180099e6c  mov     rdx, rbx
0x180099e6f  mov     rcx, rsi
0x180099e72  mov     rax, rdi
0x180099e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e7a  mov     rcx, [rsp+0F8h]; this
0x180099e82  test    eax, eax
0x180099e84  jns     short loc_180099E9A
0x180099e86  mov     r9d, eax; char *
0x180099e89  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099e90  mov     edx, 3Fh ; '?'; void *
0x180099e95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099e9a  mov     eax, 8
0x180099e9f  mov     word ptr [rsp+0F8h+pvarg], ax
0x180099ea4  mov     rcx, r14; psz
0x180099ea7  call    cs:__imp_SysAllocString
0x180099ead  mov     qword ptr [rsp+0F8h+pvarg+8], rax
0x180099eb2  mov     rcx, [rsp+0F8h]; this
0x180099eba  test    rax, rax
0x180099ebd  jnz     short loc_180099ECE
0x180099ebf  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099ec6  lea     edx, [rax+43h]; void *
0x180099ec9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180099ece  mov     rcx, [rsp+0F8h+arg_10]
0x180099ed6  movups  xmm0, xmmword ptr [rsp+0F8h+pvarg]
0x180099edb  movaps  [rsp+0F8h+var_98], xmm0
0x180099ee0  movsd   xmm1, qword ptr [rsp+0F8h+pvarg+10h]
0x180099ee6  movsd   [rsp+0F8h+var_88], xmm1
0x180099eec  mov     rax, [rcx]
0x180099eef  xor     r8d, r8d
0x180099ef2  lea     rdx, [rsp+0F8h+var_98]
0x180099ef7  mov     rax, [rax+60h]
0x180099efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f00  mov     rcx, [rsp+0F8h]; this
0x180099f08  test    eax, eax
0x180099f0a  jns     short loc_180099F21
0x180099f0c  mov     r9d, eax; char *
0x180099f0f  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x180099f16  mov     edx, 45h ; 'E'; void *
0x180099f1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099f21  lea     rcx, [rsp+0F8h+arg_10]
0x180099f29  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180099f2e  nop
0x180099f2f  lea     rcx, [rsp+0F8h+var_B0]
0x180099f34  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180099f39  nop
0x180099f3a  lea     rcx, [rsp+0F8h+arg_18]
0x180099f42  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180099f47  nop
0x180099f48  lea     rcx, [rsp+0F8h+var_A8]
0x180099f4d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180099f52  nop
0x180099f53  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180099f58  call    cs:__imp_VariantClear
0x180099f5e  nop
0x180099f5f  lea     rcx, [rsp+0F8h+arg_8]
0x180099f67  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180099f6c  xor     eax, eax
0x180099f6e  jmp     short loc_180099F77
0x180099f70  mov     eax, dword ptr [rsp+0F8h+arg_8]
0x180099f77  mov     rbx, [rsp+0F8h+arg_0]
0x180099f7f  add     rsp, 0E0h
0x180099f86  pop     r14
0x180099f88  pop     rdi
0x180099f89  pop     rsi
0x180099f8a  retn
```
