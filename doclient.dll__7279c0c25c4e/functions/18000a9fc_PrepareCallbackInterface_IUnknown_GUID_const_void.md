# PrepareCallbackInterface(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a9fc`
- end: `0x18000abe7`
- name: `?PrepareCallbackInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `491`
- prototype: `__int64 __fastcall(IUnknown *pProxy, const struct _GUID *, IUnknown **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b738`
- `0x18000bd54`
- `0x18000f2b4`
- `0x18000f3fc`

## callees

- `0x18000933c`
- `0x18000a9fc`
- `0x18000cea4`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000aa94`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ab00`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ab83`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ab9e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000aa94`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ab00`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ab83`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000ab9e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000aa28`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000aa28`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000aa6e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000ab3d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000aa6e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000ab3d`

## string_xrefs

- `0x18000abd4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18000aa82`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000aace`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000ab51`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrepareCallbackInterface(IUnknown *pProxy, const struct _GUID *a2, IUnknown **a3)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // ebx
  IUnknown *v12; // rcx
  const char *v13; // r9
  HRESULT v14; // eax
  IUnknown *v15; // rcx
  IUnknown *v16; // rax
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-58h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-58h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-58h]
  IUnknown *pProxya; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a3 = 0;
  v6 = CoImpersonateClient();
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1262,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v6,
      dwAuthnLevel);
  v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
      (const char *)(unsigned int)v7,
      dwAuthnLevela);
    CoRevertToSelf();
    return v8;
  }
  try
  {
    pProxya = 0;
    v10 = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
            pProxy,
            a2,
            &pProxya);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)v10,
        dwAuthnLevela);
      v12 = pProxya;
      if ( pProxya )
      {
        pProxya = 0;
        ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
      }
LABEL_7:
      CoRevertToSelf();
      return v11;
    }
    v14 = CoSetProxyBlanket(pProxya, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    v11 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)v14,
        dwAuthnLevelb);
      v15 = pProxya;
      if ( pProxya )
      {
        pProxya = 0;
        ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
      }
      goto LABEL_7;
    }
    v16 = pProxya;
    pProxya = 0;
    *a3 = v16;
    CoRevertToSelf();
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18000a9fc  mov     [rsp+arg_18], rbx
0x18000aa01  push    rsi
0x18000aa02  push    rdi
0x18000aa03  push    r14
0x18000aa05  sub     rsp, 60h
0x18000aa09  mov     rax, cs:__security_cookie
0x18000aa10  xor     rax, rsp
0x18000aa13  mov     [rsp+78h+var_28], rax
0x18000aa18  mov     rdi, r8
0x18000aa1b  mov     r14, rdx
0x18000aa1e  mov     rsi, rcx
0x18000aa21  mov     qword ptr [r8], 0
0x18000aa28  call    cs:__imp_CoImpersonateClient
0x18000aa2e  mov     rcx, [rsp+78h]; this
0x18000aa33  test    eax, eax
0x18000aa35  js      loc_18000ABD1
0x18000aa3b  mov     [rsp+78h+var_38], 1
0x18000aa40  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18000aa48  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x18000aa51  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x18000aa59  mov     [rsp+78h+dwAuthnLevel], 0; int
0x18000aa61  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000aa65  xor     r8d, r8d; dwAuthzSvc
0x18000aa68  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000aa6b  mov     rcx, rsi; pProxy
0x18000aa6e  call    cs:__imp_CoSetProxyBlanket
0x18000aa74  mov     ebx, eax
0x18000aa76  test    eax, eax
0x18000aa78  jns     short loc_18000AAA1
0x18000aa7a  mov     rcx, [rsp+78h]; this
0x18000aa7f  mov     r9d, eax; char *
0x18000aa82  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000aa89  mov     edx, 17h; void *
0x18000aa8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa93  nop
0x18000aa94  call    cs:__imp_CoRevertToSelf
0x18000aa9a  mov     eax, ebx
0x18000aa9c  jmp     loc_18000ABB3
0x18000aaa1  mov     [rsp+78h+pProxy], 0
0x18000aaaa  mov     rax, [rsi]
0x18000aaad  lea     r8, [rsp+78h+pProxy]
0x18000aab2  mov     rdx, r14
0x18000aab5  mov     rcx, rsi
0x18000aab8  mov     rax, [rax]
0x18000aabb  call    _guard_dispatch_icall
0x18000aac0  mov     ebx, eax
0x18000aac2  test    eax, eax
0x18000aac4  jns     short loc_18000AB0D
0x18000aac6  mov     rcx, [rsp+78h]; this
0x18000aacb  mov     r9d, eax; char *
0x18000aace  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000aad5  mov     edx, 1Ch; void *
0x18000aada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aadf  nop
0x18000aae0  mov     rcx, [rsp+78h+pProxy]
0x18000aae5  test    rcx, rcx
0x18000aae8  jz      short loc_18000AB00
0x18000aaea  mov     [rsp+78h+pProxy], 0
0x18000aaf3  mov     rax, [rcx]
0x18000aaf6  mov     rax, [rax+10h]
0x18000aafa  call    _guard_dispatch_icall
0x18000aaff  nop
0x18000ab00  call    cs:__imp_CoRevertToSelf
0x18000ab06  mov     eax, ebx
0x18000ab08  jmp     loc_18000ABB3
0x18000ab0d  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18000ab15  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x18000ab1e  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x18000ab26  mov     [rsp+78h+dwAuthnLevel], 0; int
0x18000ab2e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000ab32  xor     r8d, r8d; dwAuthzSvc
0x18000ab35  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000ab38  mov     rcx, [rsp+78h+pProxy]; pProxy
0x18000ab3d  call    cs:__imp_CoSetProxyBlanket
0x18000ab43  mov     ebx, eax
0x18000ab45  test    eax, eax
0x18000ab47  jns     short loc_18000AB8D
0x18000ab49  mov     rcx, [rsp+78h]; this
0x18000ab4e  mov     r9d, eax; char *
0x18000ab51  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000ab58  mov     edx, 28h ; '('; void *
0x18000ab5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab62  nop
0x18000ab63  mov     rcx, [rsp+78h+pProxy]
0x18000ab68  test    rcx, rcx
0x18000ab6b  jz      short loc_18000AB83
0x18000ab6d  mov     [rsp+78h+pProxy], 0
0x18000ab76  mov     rax, [rcx]
0x18000ab79  mov     rax, [rax+10h]
0x18000ab7d  call    _guard_dispatch_icall
0x18000ab82  nop
0x18000ab83  call    cs:__imp_CoRevertToSelf
0x18000ab89  mov     eax, ebx
0x18000ab8b  jmp     short loc_18000ABB3
0x18000ab8d  mov     rax, [rsp+78h+pProxy]
0x18000ab92  mov     [rsp+78h+pProxy], 0
0x18000ab9b  mov     [rdi], rax
0x18000ab9e  call    cs:__imp_CoRevertToSelf
0x18000aba4  xor     eax, eax
0x18000aba6  jmp     short loc_18000ABB3
0x18000aba8  mov     eax, 8007000Eh
0x18000abad  jmp     short loc_18000ABB3
0x18000abaf  mov     eax, dword ptr [rsp+78h+pProxy]
0x18000abb3  mov     rcx, [rsp+78h+var_28]
0x18000abb8  xor     rcx, rsp; StackCookie
0x18000abbb  call    __security_check_cookie
0x18000abc0  mov     rbx, [rsp+78h+arg_18]
0x18000abc8  add     rsp, 60h
0x18000abcc  pop     r14
0x18000abce  pop     rdi
0x18000abcf  pop     rsi
0x18000abd0  retn
0x18000abd1  mov     r9d, eax; char *
0x18000abd4  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000abdb  mov     edx, 1262h; void *
0x18000abe0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
