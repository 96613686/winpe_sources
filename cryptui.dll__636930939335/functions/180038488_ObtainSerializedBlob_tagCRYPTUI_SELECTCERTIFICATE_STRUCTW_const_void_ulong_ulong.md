# ObtainSerializedBlob(tagCRYPTUI_SELECTCERTIFICATE_STRUCTW const *,void * *,ulong *,ulong *)

- ea: `0x180038488`
- end: `0x1800385bc`
- name: `?ObtainSerializedBlob@@YAJPEBUtagCRYPTUI_SELECTCERTIFICATE_STRUCTW@@PEAPEAXPEAK2@Z`
- size: `308`
- prototype: `int(const struct tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *, void **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800389e0`

## callees

- `0x180038488`
- `0x1800385c4`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003855b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003855b`
- `CRYPT32!CertOpenStore` at `0x1800384c5`
- `CRYPT32!CertOpenStore` at `0x1800384c5`
- `CRYPT32!CertCloseStore` at `0x180038595`
- `CRYPT32!CertCloseStore` at `0x180038595`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003850e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003850e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180038548`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180038548`
- `CRYPT32!CertFreeCertificateContext` at `0x1800385a3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800385a3`

## pseudocode

```c
__int64 __fastcall ObtainSerializedBlob(
        const struct tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *a1,
        void **a2,
        unsigned int *a3,
        unsigned int *a4)
{
  HCERTSTORE v7; // rsi
  signed int v8; // eax
  unsigned int v9; // ebx
  const CERT_CONTEXT *v10; // rdi
  unsigned int v11; // r14d
  __int64 v12; // rbx
  unsigned int (__fastcall *v13)(const CERT_CONTEXT *, _DWORD *, _QWORD); // rax
  signed int LastError; // eax
  _DWORD v16[22]; // [rsp+30h] [rbp-58h] BYREF

  v16[0] = 0;
  v7 = CertOpenStore((LPCSTR)2, 0, 0, 0x200u, 0);
  if ( v7 )
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
LABEL_5:
    if ( (unsigned int)v12 >= *((_DWORD *)a1 + 18) )
    {
      *a4 = v11;
      v9 = SerializeStore(v7, 0x10u, a2, a3);
    }
    else
    {
      v10 = 0;
      v16[0] = 0;
      while ( 1 )
      {
        v10 = CertEnumCertificatesInStore(*(HCERTSTORE *)(*((_QWORD *)a1 + 10) + 8 * v12), v10);
        if ( !v10 )
        {
          v12 = (unsigned int)(v12 + 1);
          goto LABEL_5;
        }
        v13 = (unsigned int (__fastcall *)(const CERT_CONTEXT *, _DWORD *, _QWORD))*((_QWORD *)a1 + 6);
        if ( (!v13 || v13(v10, v16, *((_QWORD *)a1 + 8)) == 1) && !CertAddCertificateContextToStore(v7, v10, 4u, 0) )
          break;
        ++v11;
      }
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    CertCloseStore(v7, 0);
    if ( v10 )
      CertFreeCertificateContext(v10);
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return v9;
}

```

## disassembly

```asm
0x180038488  mov     [rsp+arg_8], rdx
0x18003848d  push    rbx
0x18003848e  push    rbp
0x18003848f  push    rsi
0x180038490  push    rdi
0x180038491  push    r12
0x180038493  push    r13
0x180038495  push    r14
0x180038497  push    r15
0x180038499  sub     rsp, 48h
0x18003849d  xor     edx, edx; dwEncodingType
0x18003849f  mov     [rsp+88h+var_58], 0
0x1800384a7  mov     r12, r9
0x1800384aa  mov     [rsp+88h+pvPara], 0; pvPara
0x1800384b3  mov     r13, r8
0x1800384b6  mov     rbp, rcx
0x1800384b9  mov     r9d, 200h; dwFlags
0x1800384bf  xor     r8d, r8d; hCryptProv
0x1800384c2  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800384c5  call    cs:__imp_CertOpenStore
0x1800384cb  mov     rsi, rax
0x1800384ce  test    rax, rax
0x1800384d1  jnz     short loc_1800384F1
0x1800384d3  call    cs:__imp_GetLastError
0x1800384d9  mov     ebx, eax
0x1800384db  test    eax, eax
0x1800384dd  jle     loc_1800385A9
0x1800384e3  movzx   ebx, ax
0x1800384e6  or      ebx, 80070000h
0x1800384ec  jmp     loc_1800385A9
0x1800384f1  xor     edi, edi
0x1800384f3  xor     r14d, r14d
0x1800384f6  xor     ebx, ebx
0x1800384f8  cmp     ebx, [rbp+48h]
0x1800384fb  jnb     short loc_180038572
0x1800384fd  xor     edi, edi
0x1800384ff  mov     [rsp+88h+var_58], edi
0x180038503  mov     rcx, [rbp+50h]
0x180038507  mov     rdx, rdi; pPrevCertContext
0x18003850a  mov     rcx, [rcx+rbx*8]; hCertStore
0x18003850e  call    cs:__imp_CertEnumCertificatesInStore
0x180038514  mov     rdi, rax
0x180038517  test    rax, rax
0x18003851a  jz      short loc_180038557
0x18003851c  mov     rax, [rbp+30h]
0x180038520  test    rax, rax
0x180038523  jz      short loc_18003853B
0x180038525  mov     r8, [rbp+40h]
0x180038529  lea     rdx, [rsp+88h+var_58]
0x18003852e  mov     rcx, rdi
0x180038531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038536  cmp     eax, 1
0x180038539  jnz     short loc_180038552
0x18003853b  xor     r9d, r9d; ppStoreContext
0x18003853e  mov     rdx, rdi; pCertContext
0x180038541  mov     rcx, rsi; hCertStore
0x180038544  lea     r8d, [r9+4]; dwAddDisposition
0x180038548  call    cs:__imp_CertAddCertificateContextToStore
0x18003854e  test    eax, eax
0x180038550  jz      short loc_18003855B
0x180038552  inc     r14d
0x180038555  jmp     short loc_180038503
0x180038557  inc     ebx
0x180038559  jmp     short loc_1800384F8
0x18003855b  call    cs:__imp_GetLastError
0x180038561  mov     ebx, eax
0x180038563  test    eax, eax
0x180038565  jle     short loc_180038590
0x180038567  movzx   ebx, ax
0x18003856a  or      ebx, 80070000h
0x180038570  jmp     short loc_180038590
0x180038572  mov     r8, [rsp+88h+arg_8]; void **
0x18003857a  mov     r9, r13; unsigned int *
0x18003857d  mov     edx, 10h; unsigned int
0x180038582  mov     [r12], r14d
0x180038586  mov     rcx, rsi; hCertStore
0x180038589  call    ?SerializeStore@@YAJPEAXKPEAPEAXPEAK@Z; SerializeStore(void *,ulong,void * *,ulong *)
0x18003858e  mov     ebx, eax
0x180038590  xor     edx, edx; dwFlags
0x180038592  mov     rcx, rsi; hCertStore
0x180038595  call    cs:__imp_CertCloseStore
0x18003859b  test    rdi, rdi
0x18003859e  jz      short loc_1800385A9
0x1800385a0  mov     rcx, rdi; pCertContext
0x1800385a3  call    cs:__imp_CertFreeCertificateContext
0x1800385a9  mov     eax, ebx
0x1800385ab  add     rsp, 48h
0x1800385af  pop     r15
0x1800385b1  pop     r14
0x1800385b3  pop     r13
0x1800385b5  pop     r12
0x1800385b7  pop     rdi
0x1800385b8  pop     rsi
0x1800385b9  pop     rbp
0x1800385ba  pop     rbx
0x1800385bb  retn
```
