# _GetKeyCertificate(unsigned __int64,_CERT_CONTEXT const * *)

- ea: `0x180008ca4`
- end: `0x180008d52`
- name: `?_GetKeyCertificate@@YAK_KPEAPEBU_CERT_CONTEXT@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001970`

## callees

- `0x180003750`
- `0x1800048d0`
- `0x180008ca4`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180008d14`
- `CRYPT32!CertCreateCertificateContext` at `0x180008d14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d22`

## string_xrefs

- `0x180008d28`: `ERROR: CertCreateCertificateContext. Return=%d\n`

## pseudocode

```c
__int64 __fastcall _GetKeyCertificate(NCRYPT_HANDLE a1, const struct _CERT_CONTEXT **a2)
{
  unsigned int NCryptBlobProperty; // eax
  __int64 LastError; // rbx
  const struct _CERT_CONTEXT *CertificateContext; // rax
  DWORD cbCertEncoded; // [rsp+48h] [rbp+10h] BYREF
  BYTE *pbCertEncoded; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  pbCertEncoded = 0;
  cbCertEncoded = 0;
  NCryptBlobProperty = _GetNCryptBlobProperty(a1, L"SmartCardKeyCertificate", &cbCertEncoded, &pbCertEncoded, 0);
  LODWORD(LastError) = NCryptBlobProperty;
  if ( NCryptBlobProperty )
  {
    ekTraceFmt(0x7D312C2u, 1, "ERROR: _GetNCryptBlobProperty(CERT). Hr=%x\n", NCryptBlobProperty);
  }
  else
  {
    CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
    *a2 = CertificateContext;
    if ( CertificateContext )
    {
      LODWORD(LastError) = 0;
    }
    else
    {
      LastError = GetLastError();
      ekTraceFmt(0x7E012C2u, 1, "ERROR: CertCreateCertificateContext. Return=%d\n", LastError);
    }
  }
  LocalFree(pbCertEncoded);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008ca4  mov     rax, rsp
0x180008ca7  mov     [rax+8], rbx
0x180008cab  push    rdi
0x180008cac  sub     rsp, 30h
0x180008cb0  mov     rdi, rdx
0x180008cb3  mov     qword ptr [rdx], 0
0x180008cba  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180008cc1  mov     qword ptr [rax+18h], 0
0x180008cc9  lea     r9, [rax+18h]; unsigned __int8 **
0x180008ccd  mov     dword ptr [rax+10h], 0
0x180008cd4  lea     r8, [rax+10h]; unsigned int *
0x180008cd8  mov     dword ptr [rax-18h], 0
0x180008cdf  call    ?_GetNCryptBlobProperty@@YAJ_KPEBGPEAKPEAPEAEK@Z; _GetNCryptBlobProperty(unsigned __int64,ushort const *,ulong *,uchar * *,ulong)
0x180008ce4  mov     ebx, eax
0x180008ce6  test    eax, eax
0x180008ce8  jz      short loc_180008D05
0x180008cea  lea     r8, aErrorGetncrypt_0; "ERROR: _GetNCryptBlobProperty(CERT). Hr"...
0x180008cf1  mov     ecx, 7D312C2h; unsigned int
0x180008cf6  mov     edx, 1; unsigned int
0x180008cfb  mov     r9d, eax
0x180008cfe  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180008d03  jmp     short loc_180008D3A
0x180008d05  mov     r8d, [rsp+38h+cbCertEncoded]; cbCertEncoded
0x180008d0a  mov     ecx, 10001h; dwCertEncodingType
0x180008d0f  mov     rdx, [rsp+38h+pbCertEncoded]; pbCertEncoded
0x180008d14  call    cs:__imp_CertCreateCertificateContext
0x180008d1a  mov     [rdi], rax
0x180008d1d  test    rax, rax
0x180008d20  jnz     short loc_180008D38
0x180008d22  call    cs:__imp_GetLastError
0x180008d28  lea     r8, aErrorCertcreat; "ERROR: CertCreateCertificateContext. Re"...
0x180008d2f  mov     ecx, 7E012C2h
0x180008d34  mov     ebx, eax
0x180008d36  jmp     short loc_180008CF6
0x180008d38  xor     ebx, ebx
0x180008d3a  mov     rcx, [rsp+38h+pbCertEncoded]; hMem
0x180008d3f  call    cs:__imp_LocalFree
0x180008d45  mov     eax, ebx
0x180008d47  mov     rbx, [rsp+38h+arg_0]
0x180008d4c  add     rsp, 30h
0x180008d50  pop     rdi
0x180008d51  retn
```
