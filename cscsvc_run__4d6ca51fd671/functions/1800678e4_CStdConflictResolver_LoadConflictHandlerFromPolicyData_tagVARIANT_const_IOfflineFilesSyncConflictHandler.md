# CStdConflictResolver::_LoadConflictHandlerFromPolicyData(tagVARIANT const &,IOfflineFilesSyncConflictHandler * *)

- ea: `0x1800678e4`
- end: `0x180067a10`
- name: `?_LoadConflictHandlerFromPolicyData@CStdConflictResolver@@AEAAJAEBUtagVARIANT@@PEAPEAUIOfflineFilesSyncConflictHandler@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CStdConflictResolver *__hidden this, VARIANTARG *pvarSrc, struct IOfflineFilesSyncConflictHandler **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068e90`

## callees

- `0x180039610`
- `0x1800667b4`
- `0x1800678e4`
- `0x180068898`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180067922`
- `OLEAUT32!__imp_VariantInit` at `0x180067922`
- `OLEAUT32!__imp_VariantClear` at `0x1800679ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800679ec`
- `OLEAUT32!__imp_VariantChangeType` at `0x180067938`
- `OLEAUT32!__imp_VariantChangeType` at `0x180067938`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800679ab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800679ab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180067970`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180067970`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067990`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800679cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067990`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800679cd`

## pseudocode

```c
__int64 __fastcall CStdConflictResolver::_LoadConflictHandlerFromPolicyData(
        CStdConflictResolver *this,
        VARIANTARG *pvarSrc,
        struct IOfflineFilesSyncConflictHandler **a3)
{
  HRESULT ConflictHandlerCache; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-18h] BYREF

  *a3 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  ConflictHandlerCache = VariantChangeType(&pvarg, pvarSrc, 0, 8u);
  if ( ConflictHandlerCache >= 0 )
  {
    ConflictHandlerCache = CStdConflictResolver::_QueryConflictHandlerCache(this, pvarg.bstrVal, a3);
    if ( ConflictHandlerCache < 0 )
    {
      pclsid = 0;
      if ( CLSIDFromString(pvarg.bstrVal, &pclsid) >= 0 )
      {
        ConflictHandlerCache = CoCreateInstance(&pclsid, 0, 4u, &IID_IOfflineFilesSyncConflictHandler, (LPVOID *)a3);
        if ( ConflictHandlerCache >= 0 )
          goto LABEL_8;
      }
      pclsid = 0;
      ConflictHandlerCache = CLSIDFromProgID(pvarg.bstrVal, &pclsid);
      if ( ConflictHandlerCache >= 0 )
        ConflictHandlerCache = CoCreateInstance(&pclsid, 0, 4u, &IID_IOfflineFilesSyncConflictHandler, (LPVOID *)a3);
      if ( ConflictHandlerCache >= 0 )
LABEL_8:
        CStdConflictResolver::_CacheConflictHandler(this, pvarg.bstrVal, *a3);
    }
  }
  VariantClear(&pvarg);
  return (unsigned int)ConflictHandlerCache;
}

```

## disassembly

```asm
0x1800678e4  mov     [rsp-18h+arg_18], rbx
0x1800678e9  push    rbp
0x1800678ea  push    rsi
0x1800678eb  push    rdi
0x1800678ec  mov     rbp, rsp
0x1800678ef  sub     rsp, 60h
0x1800678f3  mov     rax, cs:__security_cookie
0x1800678fa  xor     rax, rsp
0x1800678fd  mov     [rbp+var_8], rax
0x180067901  mov     rsi, rcx
0x180067904  mov     qword ptr [r8], 0
0x18006790b  xorps   xmm0, xmm0
0x18006790e  lea     rcx, [rbp+pvarg]; pvarg
0x180067912  xor     eax, eax
0x180067914  mov     rdi, r8
0x180067917  movups  xmmword ptr [rbp+pvarg], xmm0
0x18006791b  mov     qword ptr [rbp+pvarg+10h], rax
0x18006791f  mov     rbx, rdx
0x180067922  call    cs:__imp_VariantInit
0x180067928  mov     r9d, 8; vt
0x18006792e  lea     rcx, [rbp+pvarg]; pvargDest
0x180067932  xor     r8d, r8d; wFlags
0x180067935  mov     rdx, rbx; pvarSrc
0x180067938  call    cs:__imp_VariantChangeType
0x18006793e  mov     ebx, eax
0x180067940  test    eax, eax
0x180067942  js      loc_1800679E8
0x180067948  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x18006794c  mov     r8, rdi; struct IOfflineFilesSyncConflictHandler **
0x18006794f  mov     rcx, rsi; this
0x180067952  call    ?_QueryConflictHandlerCache@CStdConflictResolver@@AEAAJPEBGPEAPEAUIOfflineFilesSyncConflictHandler@@@Z; CStdConflictResolver::_QueryConflictHandlerCache(ushort const *,IOfflineFilesSyncConflictHandler * *)
0x180067957  mov     ebx, eax
0x180067959  test    eax, eax
0x18006795b  jns     loc_1800679E8
0x180067961  mov     rcx, qword ptr [rbp+pvarg+8]; lpsz
0x180067965  lea     rdx, [rbp+pclsid]; pclsid
0x180067969  xorps   xmm0, xmm0
0x18006796c  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180067970  call    cs:__imp_CLSIDFromString
0x180067976  test    eax, eax
0x180067978  js      short loc_18006799C
0x18006797a  xor     edx, edx; pUnkOuter
0x18006797c  mov     [rsp+60h+ppv], rdi; ppv
0x180067981  lea     r9, IID_IOfflineFilesSyncConflictHandler; riid
0x180067988  lea     rcx, [rbp+pclsid]; rclsid
0x18006798c  lea     r8d, [rdx+4]; dwClsContext
0x180067990  call    cs:__imp_CoCreateInstance
0x180067996  mov     ebx, eax
0x180067998  test    eax, eax
0x18006799a  jns     short loc_1800679D9
0x18006799c  mov     rcx, qword ptr [rbp+pvarg+8]; lpszProgID
0x1800679a0  lea     rdx, [rbp+pclsid]; lpclsid
0x1800679a4  xorps   xmm0, xmm0
0x1800679a7  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800679ab  call    cs:__imp_CLSIDFromProgID
0x1800679b1  mov     ebx, eax
0x1800679b3  test    eax, eax
0x1800679b5  js      short loc_1800679D5
0x1800679b7  xor     edx, edx; pUnkOuter
0x1800679b9  mov     [rsp+60h+ppv], rdi; ppv
0x1800679be  lea     r9, IID_IOfflineFilesSyncConflictHandler; riid
0x1800679c5  lea     rcx, [rbp+pclsid]; rclsid
0x1800679c9  lea     r8d, [rdx+4]; dwClsContext
0x1800679cd  call    cs:__imp_CoCreateInstance
0x1800679d3  mov     ebx, eax
0x1800679d5  test    ebx, ebx
0x1800679d7  js      short loc_1800679E8
0x1800679d9  mov     r8, [rdi]; struct IOfflineFilesSyncConflictHandler *
0x1800679dc  mov     rcx, rsi; this
0x1800679df  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x1800679e3  call    ?_CacheConflictHandler@CStdConflictResolver@@AEAAJPEBGPEAUIOfflineFilesSyncConflictHandler@@@Z; CStdConflictResolver::_CacheConflictHandler(ushort const *,IOfflineFilesSyncConflictHandler *)
0x1800679e8  lea     rcx, [rbp+pvarg]; pvarg
0x1800679ec  call    cs:__imp_VariantClear
0x1800679f2  mov     eax, ebx
0x1800679f4  mov     rcx, [rbp+var_8]
0x1800679f8  xor     rcx, rsp; StackCookie
0x1800679fb  call    __security_check_cookie
0x180067a00  mov     rbx, [rsp+60h+arg_18]
0x180067a08  add     rsp, 60h
0x180067a0c  pop     rdi
0x180067a0d  pop     rsi
0x180067a0e  pop     rbp
0x180067a0f  retn
```
