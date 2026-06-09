# _GetHpkpCtls

- ea: `0x1800015a4`
- end: `0x180001702`
- name: `_GetHpkpCtls`
- size: `350`
- prototype: `void __fastcall(const CTL_CONTEXT **, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001868`

## callees

- `0x1800015a4`
- `0x180001708`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800016ec`
- `CRYPT32!CertCreateContext` at `0x18000167c`
- `CRYPT32!CertCreateContext` at `0x1800016c6`
- `CRYPT32!CertCreateContext` at `0x18000167c`
- `CRYPT32!CertCreateContext` at `0x1800016c6`
- `CRYPT32!CertFindExtension` at `0x18000169c`
- `CRYPT32!CertFindExtension` at `0x18000169c`
- `CRYPT32!CertFreeCTLContext` at `0x1800016f5`
- `CRYPT32!CertFreeCTLContext` at `0x1800016f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001630`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001604`

## string_xrefs

- `0x1800015e7`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
void __fastcall GetHpkpCtls(const CTL_CONTEXT **a1, _QWORD *a2)
{
  const CTL_CONTEXT *v4; // rbx
  const void *Context; // rdi
  LSTATUS v6; // eax
  const CTL_CONTEXT *v7; // rax
  PCERT_EXTENSION Extension; // rax
  struct _CERT_CREATE_CONTEXT_PARA pCreatePara; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  BYTE *pbEncoded; // [rsp+A0h] [rbp+40h]

  hKey = 0;
  pbEncoded = 0;
  v4 = 0;
  Context = 0;
  memset(&pCreatePara, 0, sizeof(pCreatePara));
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
         0,
         0x20119u,
         &hKey);
  if ( v6 )
  {
    SetLastError(v6);
  }
  else if ( (unsigned int)I_CertReadBINARYValueFromRegistry(hKey) )
  {
    pCreatePara.pfnFree = (PFN_CRYPT_FREE)PkiFree;
    pCreatePara.cbSize = 40;
    v7 = (const CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, pbEncoded, 0, 5u, &pCreatePara);
    v4 = v7;
    if ( v7 )
    {
      Extension = CertFindExtension("1.3.6.1.4.1.311.10.3.61", v7->pCtlInfo->cExtension, v7->pCtlInfo->rgExtension);
      if ( Extension )
      {
        Context = CertCreateContext(3u, 0x10001u, Extension->Value.pbData, Extension->Value.cbData, 5u, 0);
        if ( Context )
          goto LABEL_3;
      }
      else
      {
        SetLastError(0x8000FFFF);
      }
      CertFreeCTLContext(v4);
      v4 = 0;
    }
  }
LABEL_3:
  if ( hKey )
    RegCloseKey(hKey);
  *a1 = v4;
  *a2 = Context;
}

```

## disassembly

```asm
0x1800015a4  push    rbp
0x1800015a6  push    rbx
0x1800015a7  push    rsi
0x1800015a8  push    rdi
0x1800015a9  push    r14
0x1800015ab  mov     rbp, rsp
0x1800015ae  sub     rsp, 60h
0x1800015b2  xor     eax, eax
0x1800015b4  mov     [rbp+hKey], 0
0x1800015bc  xorps   xmm0, xmm0
0x1800015bf  mov     [rbp+var_30.pvSort], rax
0x1800015c3  lea     rax, [rbp+hKey]
0x1800015c7  mov     [rbp+pbEncoded], 0
0x1800015cf  mov     rsi, rdx
0x1800015d2  mov     [rsp+60h+phkResult], rax; phkResult
0x1800015d7  mov     r14, rcx
0x1800015da  mov     [rbp+cbEncoded], 0
0x1800015e1  mov     r9d, 20119h; samDesired
0x1800015e7  lea     rdx, SubKey; "Software\\Microsoft\\SystemCertificates"...
0x1800015ee  xor     r8d, r8d; ulOptions
0x1800015f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800015f8  xor     ebx, ebx
0x1800015fa  xor     edi, edi
0x1800015fc  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x180001600  movups  xmmword ptr [rbp+var_30.pvFree], xmm0
0x180001604  call    cs:__imp_RegOpenKeyExW
0x18000160a  test    eax, eax
0x18000160c  jnz     loc_1800016DA
0x180001612  mov     rcx, [rbp+hKey]; hKey
0x180001616  lea     r9, [rbp+cbEncoded]
0x18000161a  lea     r8, [rbp+pbEncoded]
0x18000161e  call    I_CertReadBINARYValueFromRegistry
0x180001623  test    eax, eax
0x180001625  jnz     short loc_180001647
0x180001627  mov     rcx, [rbp+hKey]; hKey
0x18000162b  test    rcx, rcx
0x18000162e  jz      short loc_180001636
0x180001630  call    cs:__imp_RegCloseKey
0x180001636  mov     [r14], rbx
0x180001639  mov     [rsi], rdi
0x18000163c  add     rsp, 60h
0x180001640  pop     r14
0x180001642  pop     rdi
0x180001643  pop     rsi
0x180001644  pop     rbx
0x180001645  pop     rbp
0x180001646  retn
0x180001647  mov     r9d, [rbp+cbEncoded]; cbEncoded
0x18000164b  lea     rax, PkiFree
0x180001652  mov     r8, [rbp+pbEncoded]; pbEncoded
0x180001656  mov     edx, 10001h; dwEncodingType
0x18000165b  mov     [rbp+var_30.pfnFree], rax
0x18000165f  mov     ecx, 3; dwContextType
0x180001664  lea     rax, [rbp+var_30]
0x180001668  mov     [rbp+var_30.cbSize], 28h ; '('
0x18000166f  mov     [rsp+60h+pCreatePara], rax; pCreatePara
0x180001674  mov     dword ptr [rsp+60h+phkResult], 5; dwFlags
0x18000167c  call    cs:__imp_CertCreateContext
0x180001682  mov     rbx, rax
0x180001685  test    rax, rax
0x180001688  jz      short loc_180001627
0x18000168a  mov     rdx, [rax+18h]
0x18000168e  lea     rcx, pszObjId; "1.3.6.1.4.1.311.10.3.61"
0x180001695  mov     r8, [rdx+78h]; rgExtensions
0x180001699  mov     edx, [rdx+70h]; cExtensions
0x18000169c  call    cs:__imp_CertFindExtension
0x1800016a2  test    rax, rax
0x1800016a5  jz      short loc_1800016E7
0x1800016a7  mov     r9d, [rax+10h]; cbEncoded
0x1800016ab  mov     edx, 10001h; dwEncodingType
0x1800016b0  mov     r8, [rax+18h]; pbEncoded
0x1800016b4  mov     ecx, 3; dwContextType
0x1800016b9  mov     [rsp+60h+pCreatePara], rdi; pCreatePara
0x1800016be  mov     dword ptr [rsp+60h+phkResult], 5; dwFlags
0x1800016c6  call    cs:__imp_CertCreateContext
0x1800016cc  mov     rdi, rax
0x1800016cf  test    rax, rax
0x1800016d2  jnz     loc_180001627
0x1800016d8  jmp     short loc_1800016F2
0x1800016da  mov     ecx, eax; dwErrCode
0x1800016dc  call    cs:__imp_SetLastError
0x1800016e2  jmp     loc_180001627
0x1800016e7  mov     ecx, 8000FFFFh; dwErrCode
0x1800016ec  call    cs:__imp_SetLastError
0x1800016f2  mov     rcx, rbx; pCtlContext
0x1800016f5  call    cs:__imp_CertFreeCTLContext
0x1800016fb  xor     ebx, ebx
0x1800016fd  jmp     loc_180001627
```
