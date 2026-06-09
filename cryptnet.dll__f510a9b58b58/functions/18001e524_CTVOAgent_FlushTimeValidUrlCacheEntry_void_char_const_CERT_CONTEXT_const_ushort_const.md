# CTVOAgent::FlushTimeValidUrlCacheEntry(void *,char const *,_CERT_CONTEXT const *,ushort const *)

- ea: `0x18001e524`
- end: `0x18001e657`
- name: `?FlushTimeValidUrlCacheEntry@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@PEBG@Z`
- size: `307`
- prototype: `__int64 __fastcall(CTVOAgent *this, struct _CERT_CONTEXT *, const char *, const struct _CERT_CONTEXT *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e1b8`
- `0x18001e410`

## callees

- `0x180007a40`
- `0x180009df0`
- `0x18000a990`
- `0x18000c470`
- `0x18000cef0`
- `0x180015e90`
- `0x18001e524`
- `0x18001ff84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e63e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e63e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e60b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e60b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e616`

## pseudocode

```c
__int64 __fastcall CTVOAgent::FlushTimeValidUrlCacheEntry(
        CTVOAgent *this,
        struct _CERT_CONTEXT *a2,
        const char *a3,
        const struct _CERT_CONTEXT *a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v5; // rbp
  unsigned int v8; // r15d
  unsigned __int16 *Request; // rdi
  unsigned __int16 *OcspCacheFileNamePrefix; // rsi
  const struct _OCSP_CERT_ID *CertId; // rax
  struct _OCSP_CERT_ID *v12; // rbx
  DWORD LastError; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14

  v5 = a5;
  v8 = 1;
  if ( !(unsigned int)IsOcspUrl(a5, a3, a2) )
  {
    if ( !a5 )
      return v8;
    LastError = 0;
    OcspCacheFileNamePrefix = 0;
    Request = 0;
    goto LABEL_14;
  }
  Request = 0;
  OcspCacheFileNamePrefix = CertificateGetOcspCacheFileNamePrefix(a2);
  CertId = OcspCreateCertId(a2, a4);
  v12 = (struct _OCSP_CERT_ID *)CertId;
  if ( CertId )
  {
    Request = OcspFormatGetRequest(a5 + 5, CertId);
    operator delete(v12);
  }
  if ( Request )
  {
    v5 = Request;
    v14 = OcspFormatPostRequest(Request);
    v15 = v14;
    if ( v14 )
    {
      LastError = 0;
      if ( !(unsigned int)SchemeDeleteUrlCacheEntry((__int64)v14, 0) && GetLastError() != 2 )
        LastError = GetLastError();
      operator delete(v15);
    }
    else
    {
      LastError = GetLastError();
    }
LABEL_14:
    if ( !(unsigned int)SchemeDeleteUrlCacheEntry((__int64)v5, OcspCacheFileNamePrefix) && GetLastError() != 2 )
      LastError = GetLastError();
    if ( Request )
      operator delete(Request);
    goto LABEL_19;
  }
  LastError = GetLastError();
LABEL_19:
  if ( OcspCacheFileNamePrefix )
    operator delete(OcspCacheFileNamePrefix);
  if ( LastError )
  {
    SetLastError(LastError);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18001e524  push    rbx
0x18001e526  push    rbp
0x18001e527  push    rsi
0x18001e528  push    rdi
0x18001e529  push    r14
0x18001e52b  push    r15
0x18001e52d  sub     rsp, 28h
0x18001e531  mov     rbp, [rsp+58h+arg_20]
0x18001e539  mov     rax, r8
0x18001e53c  mov     r8, rdx; void *
0x18001e53f  mov     rbx, rdx
0x18001e542  mov     rdx, rax; char *
0x18001e545  mov     rcx, rbp; unsigned __int16 *
0x18001e548  mov     r14, r9
0x18001e54b  mov     r15d, 1
0x18001e551  call    ?IsOcspUrl@@YAHPEBGPEBDPEAX@Z; IsOcspUrl(ushort const *,char const *,void *)
0x18001e556  test    eax, eax
0x18001e558  jz      loc_18001E5F1
0x18001e55e  mov     rcx, rbx; pCertContext
0x18001e561  xor     edi, edi
0x18001e563  call    ?CertificateGetOcspCacheFileNamePrefix@@YAPEAGPEBU_CERT_CONTEXT@@@Z; CertificateGetOcspCacheFileNamePrefix(_CERT_CONTEXT const *)
0x18001e568  mov     rdx, r14; struct _CERT_CONTEXT *
0x18001e56b  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18001e56e  mov     rsi, rax
0x18001e571  call    ?OcspCreateCertId@@YAPEAU_OCSP_CERT_ID@@PEBU_CERT_CONTEXT@@0@Z; OcspCreateCertId(_CERT_CONTEXT const *,_CERT_CONTEXT const *)
0x18001e576  mov     rbx, rax
0x18001e579  test    rax, rax
0x18001e57c  jz      short loc_18001E595
0x18001e57e  lea     rcx, [rbp+0Ah]; Src
0x18001e582  mov     rdx, rax; struct _OCSP_CERT_ID *
0x18001e585  call    ?OcspFormatGetRequest@@YAPEAGPEBGPEBU_OCSP_CERT_ID@@@Z; OcspFormatGetRequest(ushort const *,_OCSP_CERT_ID const *)
0x18001e58a  mov     rcx, rbx; hMem
0x18001e58d  mov     rdi, rax
0x18001e590  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e595  test    rdi, rdi
0x18001e598  jnz     short loc_18001E5A7
0x18001e59a  call    cs:__imp_GetLastError
0x18001e5a0  mov     ebx, eax
0x18001e5a2  jmp     loc_18001E62B
0x18001e5a7  mov     rcx, rdi; Src
0x18001e5aa  mov     rbp, rdi
0x18001e5ad  call    ?OcspFormatPostRequest@@YAPEAGPEBG@Z; OcspFormatPostRequest(ushort const *)
0x18001e5b2  mov     r14, rax
0x18001e5b5  test    rax, rax
0x18001e5b8  jnz     short loc_18001E5C4
0x18001e5ba  call    cs:__imp_GetLastError
0x18001e5c0  mov     ebx, eax
0x18001e5c2  jmp     short loc_18001E5FC
0x18001e5c4  xor     edx, edx
0x18001e5c6  mov     rcx, r14
0x18001e5c9  xor     ebx, ebx
0x18001e5cb  call    SchemeDeleteUrlCacheEntry
0x18001e5d0  test    eax, eax
0x18001e5d2  jnz     short loc_18001E5E7
0x18001e5d4  call    cs:__imp_GetLastError
0x18001e5da  cmp     eax, 2
0x18001e5dd  jz      short loc_18001E5E7
0x18001e5df  call    cs:__imp_GetLastError
0x18001e5e5  mov     ebx, eax
0x18001e5e7  mov     rcx, r14; hMem
0x18001e5ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e5ef  jmp     short loc_18001E5FC
0x18001e5f1  test    rbp, rbp
0x18001e5f4  jz      short loc_18001E647
0x18001e5f6  xor     ebx, ebx
0x18001e5f8  xor     esi, esi
0x18001e5fa  xor     edi, edi
0x18001e5fc  mov     rdx, rsi
0x18001e5ff  mov     rcx, rbp
0x18001e602  call    SchemeDeleteUrlCacheEntry
0x18001e607  test    eax, eax
0x18001e609  jnz     short loc_18001E61E
0x18001e60b  call    cs:__imp_GetLastError
0x18001e611  cmp     eax, 2
0x18001e614  jz      short loc_18001E61E
0x18001e616  call    cs:__imp_GetLastError
0x18001e61c  mov     ebx, eax
0x18001e61e  test    rdi, rdi
0x18001e621  jz      short loc_18001E62B
0x18001e623  mov     rcx, rdi; hMem
0x18001e626  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e62b  test    rsi, rsi
0x18001e62e  jz      short loc_18001E638
0x18001e630  mov     rcx, rsi; hMem
0x18001e633  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e638  test    ebx, ebx
0x18001e63a  jz      short loc_18001E647
0x18001e63c  mov     ecx, ebx; dwErrCode
0x18001e63e  call    cs:__imp_SetLastError
0x18001e644  xor     r15d, r15d
0x18001e647  mov     eax, r15d
0x18001e64a  add     rsp, 28h
0x18001e64e  pop     r15
0x18001e650  pop     r14
0x18001e652  pop     rdi
0x18001e653  pop     rsi
0x18001e654  pop     rbp
0x18001e655  pop     rbx
0x18001e656  retn
```
