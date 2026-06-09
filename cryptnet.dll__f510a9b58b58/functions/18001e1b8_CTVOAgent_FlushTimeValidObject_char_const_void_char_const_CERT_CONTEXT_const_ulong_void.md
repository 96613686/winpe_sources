# CTVOAgent::FlushTimeValidObject(char const *,void *,char const *,_CERT_CONTEXT const *,ulong,void *)

- ea: `0x18001e1b8`
- end: `0x18001e407`
- name: `?FlushTimeValidObject@CTVOAgent@@QEAAHPEBDPEAX0PEBU_CERT_CONTEXT@@K1@Z`
- size: `591`
- prototype: `__int64 __fastcall(CTVOAgent *this, const char *, CERT_CONTEXT *, char *, struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e080`
- `0x18001e120`

## callees

- `0x180005bd0`
- `0x18000a990`
- `0x18001254c`
- `0x180017b30`
- `0x180017c34`
- `0x180018ff8`
- `0x18001e1b8`
- `0x18001e410`
- `0x18001e524`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e3d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e23a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e23a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3ad`

## pseudocode

```c
__int64 __fastcall CTVOAgent::FlushTimeValidObject(
        CTVOAgent *this,
        const char *a2,
        CERT_CONTEXT *a3,
        char *a4,
        struct _CERT_CONTEXT *a5)
{
  DWORD LastError; // r14d
  struct _CERT_CONTEXT *v6; // r13
  int v9; // edi
  __int64 v10; // r12
  int v11; // r13d
  CERT_CONTEXT *v12; // r15
  int v13; // r8d
  int OriginIdentifierFromCrlIssuer; // eax
  unsigned int RevocationUrl; // eax
  char *v16; // r12
  unsigned int v18; // edi
  _QWORD *v19; // rbx
  __int64 v20; // rsi
  struct _CRYPT_URL_ARRAY **v21; // [rsp+20h] [rbp-81h]
  unsigned int v22; // [rsp+40h] [rbp-61h] BYREF
  char *v23; // [rsp+48h] [rbp-59h]
  HLOCAL hMem; // [rsp+50h] [rbp-51h] BYREF
  struct _CERT_CONTEXT *v25; // [rsp+58h] [rbp-49h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-41h]
  unsigned __int8 v27[32]; // [rsp+68h] [rbp-39h] BYREF
  unsigned __int8 v28[32]; // [rsp+88h] [rbp-19h] BYREF

  LastError = 0;
  v6 = a5;
  lpCriticalSection = g_pProcessTVOAgent;
  v23 = a4;
  v25 = a5;
  hMem = 0;
  v22 = 0;
  if ( a2 == (const char *)3 )
  {
    v9 = 1;
    v10 = 10;
    v11 = 0;
    v12 = a3;
    if ( !OcspGetOriginIdentifier(a3, v28)
      || !(unsigned int)CTVOAgent::FlushTimeValidOriginIdentifier(lpCriticalSection, a3, v23, v25, v28) )
    {
      LastError = GetLastError();
    }
    goto LABEL_11;
  }
  if ( a2 == (const char *)4 )
  {
    v10 = 6;
    v12 = a3;
LABEL_10:
    v11 = 1;
    v9 = 1;
LABEL_11:
    v13 = v11;
    v6 = v25;
    OriginIdentifierFromCrlIssuer = CrlGetOriginIdentifierFromCrlIssuer(v25, &v12->pCertInfo->Issuer, v13, v27);
    goto LABEL_12;
  }
  if ( a2 == (const char *)5 )
  {
    v12 = *(CERT_CONTEXT **)&a3->dwCertEncodingType;
    v10 = 7;
    goto LABEL_10;
  }
  v9 = 0;
  v10 = 0;
  v12 = 0;
  OriginIdentifierFromCrlIssuer = ObjectContextGetOriginIdentifier(a4, a3, a5, (unsigned int)a4, v27);
LABEL_12:
  if ( !OriginIdentifierFromCrlIssuer )
    return 0;
  if ( !(unsigned int)CTVOAgent::FlushTimeValidOriginIdentifier(lpCriticalSection, v12, v23, v6, v27) )
    LastError = GetLastError();
  if ( v9 )
  {
    RevocationUrl = CertificateGetRevocationUrl((LPCSTR)v10, a3, 0, 0, (struct _CRYPT_URL_ARRAY **)&hMem, &v22, 0);
    v16 = v23;
  }
  else
  {
    v18 = 1;
    if ( a2 != (const char *)1 )
      goto LABEL_30;
    v16 = v23;
    RevocationUrl = ObjectContextGetNextUpdateUrl(v23, a3, v6, 0, (struct _CRYPT_URL_ARRAY **)&hMem, &v22, 0);
  }
  v19 = hMem;
  v18 = RevocationUrl;
  if ( RevocationUrl != 1 )
    goto LABEL_27;
  if ( hMem )
  {
    v20 = 0;
    if ( *(_DWORD *)hMem )
    {
      do
      {
        v21 = *(struct _CRYPT_URL_ARRAY ***)(v19[1] + 8 * v20);
        if ( !CTVOAgent::FlushTimeValidUrlCacheEntry((CTVOAgent *)v21, v12, v16, v6, (const unsigned __int16 *)v21) )
          LastError = GetLastError();
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (unsigned int)v20 < *(_DWORD *)v19 );
    }
LABEL_27:
    if ( v19 )
      operator delete(v19);
    if ( v18 != 1 )
      return v18;
  }
LABEL_30:
  if ( LastError )
  {
    SetLastError(LastError);
    return 0;
  }
  return v18;
}

```

## disassembly

```asm
0x18001e1b8  mov     [rsp-8+arg_0], rbx
0x18001e1bd  push    rbp
0x18001e1be  push    rsi
0x18001e1bf  push    rdi
0x18001e1c0  push    r12
0x18001e1c2  push    r13
0x18001e1c4  push    r14
0x18001e1c6  push    r15
0x18001e1c8  lea     rbp, [rsp-0Fh]
0x18001e1cd  sub     rsp, 0B0h
0x18001e1d4  mov     rax, cs:__security_cookie
0x18001e1db  xor     rax, rsp
0x18001e1de  mov     [rbp+3Fh+var_38], rax
0x18001e1e2  mov     rcx, cs:?g_pProcessTVOAgent@@3PEAVCTVOAgent@@EA; CTVOAgent * g_pProcessTVOAgent
0x18001e1e9  xor     r14d, r14d
0x18001e1ec  mov     r13, [rbp+3Fh+arg_20]
0x18001e1f0  mov     rax, r9
0x18001e1f3  mov     [rbp+3Fh+lpCriticalSection], rcx
0x18001e1f7  mov     rbx, r8
0x18001e1fa  mov     [rbp+3Fh+var_98], rax
0x18001e1fe  mov     rsi, rdx
0x18001e201  mov     [rbp+3Fh+var_88], r13
0x18001e205  lea     ecx, [r14+1]
0x18001e209  mov     [rbp+3Fh+hMem], 0
0x18001e211  mov     [rbp+3Fh+var_A0], 0
0x18001e218  cmp     rdx, 3
0x18001e21c  jnz     short loc_18001E268
0x18001e21e  mov     edi, ecx
0x18001e220  lea     r12d, [rdx+7]
0x18001e224  lea     rdx, [rbp+3Fh+var_58]; unsigned __int8 *
0x18001e228  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18001e22b  xor     r13d, r13d
0x18001e22e  mov     r15, rbx
0x18001e231  call    ?OcspGetOriginIdentifier@@YAHPEBU_CERT_CONTEXT@@QEAE@Z; OcspGetOriginIdentifier(_CERT_CONTEXT const *,uchar * const)
0x18001e236  test    eax, eax
0x18001e238  jnz     short loc_18001E245
0x18001e23a  call    cs:__imp_GetLastError
0x18001e240  mov     r14d, eax
0x18001e243  jmp     short loc_18001E28D
0x18001e245  mov     r9, [rbp+3Fh+var_88]; struct _CERT_CONTEXT *
0x18001e249  lea     rax, [rbp+3Fh+var_58]
0x18001e24d  mov     r8, [rbp+3Fh+var_98]; char *
0x18001e251  mov     rdx, rbx; void *
0x18001e254  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x18001e258  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 *
0x18001e25d  call    ?FlushTimeValidOriginIdentifier@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@QEAE@Z; CTVOAgent::FlushTimeValidOriginIdentifier(void *,char const *,_CERT_CONTEXT const *,uchar * const)
0x18001e262  test    eax, eax
0x18001e264  jnz     short loc_18001E28D
0x18001e266  jmp     short loc_18001E23A
0x18001e268  cmp     rsi, 4
0x18001e26c  jnz     short loc_18001E277
0x18001e26e  lea     r12d, [rsi+2]
0x18001e272  mov     r15, rbx
0x18001e275  jmp     short loc_18001E288
0x18001e277  cmp     rsi, 5
0x18001e27b  jnz     loc_18001E30F
0x18001e281  mov     r15, [r8]
0x18001e284  lea     r12d, [rsi+2]
0x18001e288  mov     r13d, ecx
0x18001e28b  mov     edi, ecx
0x18001e28d  mov     rdx, [r15+18h]
0x18001e291  lea     r9, [rbp+3Fh+var_78]; unsigned __int8 *
0x18001e295  mov     r8d, r13d; int
0x18001e298  add     rdx, 30h ; '0'; struct _CRYPTOAPI_BLOB *
0x18001e29c  mov     r13, [rbp+3Fh+var_88]
0x18001e2a0  mov     rcx, r13; struct _CERT_CONTEXT *
0x18001e2a3  call    ?CrlGetOriginIdentifierFromCrlIssuer@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@HQEAE@Z; CrlGetOriginIdentifierFromCrlIssuer(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *,int,uchar * const)
0x18001e2a8  test    eax, eax
0x18001e2aa  jz      loc_18001E333
0x18001e2b0  mov     r8, [rbp+3Fh+var_98]; char *
0x18001e2b4  lea     rax, [rbp+3Fh+var_78]
0x18001e2b8  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x18001e2bc  mov     r9, r13; struct _CERT_CONTEXT *
0x18001e2bf  mov     rdx, r15; void *
0x18001e2c2  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 *
0x18001e2c7  call    ?FlushTimeValidOriginIdentifier@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@QEAE@Z; CTVOAgent::FlushTimeValidOriginIdentifier(void *,char const *,_CERT_CONTEXT const *,uchar * const)
0x18001e2cc  test    eax, eax
0x18001e2ce  jnz     short loc_18001E2D9
0x18001e2d0  call    cs:__imp_GetLastError
0x18001e2d6  mov     r14d, eax
0x18001e2d9  test    edi, edi
0x18001e2db  jz      short loc_18001E33A
0x18001e2dd  lea     rax, [rbp+3Fh+var_A0]
0x18001e2e1  mov     [rsp+0E0h+var_B0], 0; unsigned int *
0x18001e2ea  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18001e2ef  xor     r9d, r9d; unsigned int
0x18001e2f2  lea     rax, [rbp+3Fh+hMem]
0x18001e2f6  xor     r8d, r8d; unsigned __int16 *
0x18001e2f9  mov     rdx, rbx; pCertContext
0x18001e2fc  mov     [rsp+0E0h+var_C0], rax; struct _CRYPT_URL_ARRAY **
0x18001e301  mov     rcx, r12; pszOID
0x18001e304  call    ?CertificateGetRevocationUrl@@YAHPEBDPEAXPEAGKPEAPEAU_CRYPT_URL_ARRAY@@PEAK4@Z; CertificateGetRevocationUrl(char const *,void *,ushort *,ulong,_CRYPT_URL_ARRAY * *,ulong *,ulong *)
0x18001e309  mov     r12, [rbp+3Fh+var_98]
0x18001e30d  jmp     short loc_18001E378
0x18001e30f  lea     rcx, [rbp+3Fh+var_78]
0x18001e313  xor     edi, edi
0x18001e315  mov     [rsp+0E0h+var_C0], rcx; unsigned __int8 *
0x18001e31a  xor     r12d, r12d
0x18001e31d  mov     rcx, rax; char *
0x18001e320  xor     r15d, r15d
0x18001e323  mov     r8, r13; struct _CERT_CONTEXT *
0x18001e326  mov     rdx, rbx; void *
0x18001e329  call    ?ObjectContextGetOriginIdentifier@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@KQEAE@Z; ObjectContextGetOriginIdentifier(char const *,void *,_CERT_CONTEXT const *,ulong,uchar * const)
0x18001e32e  jmp     loc_18001E2A8
0x18001e333  xor     eax, eax
0x18001e335  jmp     loc_18001E3E0
0x18001e33a  mov     edi, 1
0x18001e33f  cmp     rsi, rdi
0x18001e342  jnz     loc_18001E3CE
0x18001e348  mov     r12, [rbp+3Fh+var_98]
0x18001e34c  lea     rax, [rbp+3Fh+var_A0]
0x18001e350  mov     [rsp+0E0h+var_B0], 0; unsigned int *
0x18001e359  xor     r9d, r9d; unsigned __int16 *
0x18001e35c  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18001e361  mov     r8, r13; struct _CERT_CONTEXT *
0x18001e364  lea     rax, [rbp+3Fh+hMem]
0x18001e368  mov     rdx, rbx; void *
0x18001e36b  mov     rcx, r12; char *
0x18001e36e  mov     [rsp+0E0h+var_C0], rax; struct _CRYPT_URL_ARRAY **
0x18001e373  call    ?ObjectContextGetNextUpdateUrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@PEAGPEAPEAU_CRYPT_URL_ARRAY@@PEAK5@Z; ObjectContextGetNextUpdateUrl(char const *,void *,_CERT_CONTEXT const *,ushort *,_CRYPT_URL_ARRAY * *,ulong *,ulong *)
0x18001e378  mov     rbx, [rbp+3Fh+hMem]
0x18001e37c  mov     edi, eax
0x18001e37e  cmp     eax, 1
0x18001e381  jnz     short loc_18001E3BC
0x18001e383  test    rbx, rbx
0x18001e386  jz      short loc_18001E3CE
0x18001e388  xor     esi, esi
0x18001e38a  cmp     [rbx], esi
0x18001e38c  jbe     short loc_18001E3BC
0x18001e38e  mov     rax, [rbx+8]
0x18001e392  mov     r9, r13; struct _CERT_CONTEXT *
0x18001e395  mov     r8, r12; char *
0x18001e398  mov     rdx, r15; void *
0x18001e39b  mov     rcx, [rax+rsi*8]; this
0x18001e39f  mov     [rsp+0E0h+var_C0], rcx; unsigned __int16 *
0x18001e3a4  call    ?FlushTimeValidUrlCacheEntry@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@PEBG@Z; CTVOAgent::FlushTimeValidUrlCacheEntry(void *,char const *,_CERT_CONTEXT const *,ushort const *)
0x18001e3a9  test    eax, eax
0x18001e3ab  jnz     short loc_18001E3B6
0x18001e3ad  call    cs:__imp_GetLastError
0x18001e3b3  mov     r14d, eax
0x18001e3b6  inc     esi
0x18001e3b8  cmp     esi, [rbx]
0x18001e3ba  jb      short loc_18001E38E
0x18001e3bc  test    rbx, rbx
0x18001e3bf  jz      short loc_18001E3C9
0x18001e3c1  mov     rcx, rbx; hMem
0x18001e3c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e3c9  cmp     edi, 1
0x18001e3cc  jnz     short loc_18001E3DE
0x18001e3ce  test    r14d, r14d
0x18001e3d1  jz      short loc_18001E3DE
0x18001e3d3  mov     ecx, r14d; dwErrCode
0x18001e3d6  call    cs:__imp_SetLastError
0x18001e3dc  xor     edi, edi
0x18001e3de  mov     eax, edi
0x18001e3e0  mov     rcx, [rbp+3Fh+var_38]
0x18001e3e4  xor     rcx, rsp; StackCookie
0x18001e3e7  call    __security_check_cookie
0x18001e3ec  mov     rbx, [rsp+0E0h+arg_0]
0x18001e3f4  add     rsp, 0B0h
0x18001e3fb  pop     r15
0x18001e3fd  pop     r14
0x18001e3ff  pop     r13
0x18001e401  pop     r12
0x18001e403  pop     rdi
0x18001e404  pop     rsi
0x18001e405  pop     rbp
0x18001e406  retn
```
