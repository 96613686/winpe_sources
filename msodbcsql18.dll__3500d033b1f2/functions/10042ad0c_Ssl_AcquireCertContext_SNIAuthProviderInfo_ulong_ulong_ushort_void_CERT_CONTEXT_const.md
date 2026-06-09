# Ssl::AcquireCertContext(SNIAuthProviderInfo *,ulong *,ulong,ushort *,void * *,_CERT_CONTEXT const * *)

- ea: `0x10042ad0c`
- end: `0x10042af27`
- name: `?AcquireCertContext@Ssl@@CAKPEAVSNIAuthProviderInfo@@PEAKKPEAGPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `539`
- prototype: `static unsigned int(struct SNIAuthProviderInfo *, unsigned int *, unsigned int, unsigned __int16 *, void **, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10042af30`

## callees

- `0x10042ad0c`
- `0x10042bf14`
- `0x10042ddcc`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042ad88`
- `KERNEL32!GetLastError` at `0x10042ae1c`
- `KERNEL32!GetLastError` at `0x10042ae71`
- `KERNEL32!GetLastError` at `0x10042ad88`
- `KERNEL32!GetLastError` at `0x10042ae1c`
- `KERNEL32!GetLastError` at `0x10042ae71`
- `CRYPT32!CertOpenStore` at `0x10042addd`
- `CRYPT32!CertOpenStore` at `0x10042addd`
- `CRYPT32!CertCloseStore` at `0x10042ae10`
- `CRYPT32!CertCloseStore` at `0x10042ae65`
- `CRYPT32!CertCloseStore` at `0x10042ae10`
- `CRYPT32!CertCloseStore` at `0x10042ae65`
- `CRYPT32!CertOpenSystemStoreA` at `0x10042ae35`
- `CRYPT32!CertOpenSystemStoreA` at `0x10042ae35`
- `CRYPT32!CryptStringToBinaryW` at `0x10042ad7e`
- `CRYPT32!CryptStringToBinaryW` at `0x10042ad7e`

## pseudocode

```c
DWORD __fastcall Ssl::AcquireCertContext(
        struct SNIAuthProviderInfo *a1,
        unsigned int *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        void **a5,
        struct _CERT_CONTEXT **a6)
{
  const WCHAR *v9; // rcx
  int *p_pvFindPara; // rbp
  DWORD v12; // r14d
  HCERTSTORE v13; // rax
  DWORD Certificate; // ebx
  HCERTSTORE v15; // rax
  __int64 (__fastcall *v16)(_QWORD, _QWORD, _QWORD, struct _CERT_CONTEXT **, unsigned int *, unsigned int, unsigned __int16 *); // rax
  _WORD *v17; // rax
  DWORD pcbBinary; // [rsp+40h] [rbp-88h] BYREF
  unsigned int *v19; // [rsp+48h] [rbp-80h]
  int pvFindPara; // [rsp+50h] [rbp-78h] BYREF
  BYTE *v21; // [rsp+58h] [rbp-70h]
  BYTE pbBinary[24]; // [rsp+60h] [rbp-68h] BYREF

  v19 = a2;
  if ( *((_DWORD *)a1 + 16) )
  {
    v9 = (const WCHAR *)*((_QWORD *)a1 + 7);
    pcbBinary = 20;
    if ( !CryptStringToBinaryW(v9, 0, 4u, pbBinary, &pcbBinary, 0, 0) )
      return GetLastError();
    pvFindPara = 20;
    v21 = pbBinary;
    p_pvFindPara = &pvFindPara;
    v12 = 0x10000;
LABEL_7:
    v13 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"MY");
    *a5 = v13;
    if ( v13 )
    {
      Certificate = Ssl::FindAndLoadCertificate(v13, v12, p_pvFindPara, (const struct _CERT_CONTEXT **)a6, 0);
      if ( !Certificate )
        return Certificate;
      CertCloseStore(*a5, 0);
      *a5 = 0;
    }
    else
    {
      Certificate = GetLastError();
      if ( !Certificate )
        return Certificate;
    }
    v15 = CertOpenSystemStoreA(0, "MY");
    *a5 = v15;
    if ( v15 )
    {
      Certificate = Ssl::FindAndLoadCertificate(v15, v12, p_pvFindPara, (const struct _CERT_CONTEXT **)a6, 0);
      if ( Certificate )
      {
        CertCloseStore(*a5, 0);
        *a5 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      Certificate = GetLastError();
      if ( Certificate )
      {
LABEL_15:
        v16 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _CERT_CONTEXT **, unsigned int *, unsigned int, unsigned __int16 *))*((_QWORD *)a1 + 10);
        if ( v16 )
          return v16(*((_QWORD *)a1 + 9), *((unsigned int *)a1 + 16), *((_QWORD *)a1 + 7), a6, v19, a3, a4);
      }
    }
    return Certificate;
  }
  p_pvFindPara = (int *)*((_QWORD *)a1 + 7);
  if ( p_pvFindPara )
  {
    v12 = 524295;
    goto LABEL_7;
  }
  v17 = (_WORD *)*((_QWORD *)a1 + 12);
  if ( v17 && *v17 )
    return Ssl::ImportCertificateFromFile(a1, a4, a3, a5, (const struct _CERT_CONTEXT **)a6);
  if ( (bidGblFlags & 2) != 0 && off_1005E53A0[0] )
    bidTraceW(0, 786432, off_1005E53A0[0], 13);
  return 13;
}

```

## disassembly

```asm
0x10042ad0c  push    rbx
0x10042ad0e  push    rbp
0x10042ad0f  push    rsi
0x10042ad10  push    rdi
0x10042ad11  push    r12
0x10042ad13  push    r13
0x10042ad15  push    r14
0x10042ad17  push    r15
0x10042ad19  sub     rsp, 88h
0x10042ad20  mov     rax, cs:__security_cookie
0x10042ad27  xor     rax, rsp
0x10042ad2a  mov     [rsp+0C8h+var_50], rax
0x10042ad2f  mov     rsi, [rsp+0C8h+arg_20]
0x10042ad37  xor     ebx, ebx
0x10042ad39  mov     r13, r9
0x10042ad3c  mov     r15, [rsp+0C8h+arg_28]
0x10042ad44  mov     r12d, r8d
0x10042ad47  mov     [rsp+0C8h+var_80], rdx
0x10042ad4c  mov     rdi, rcx
0x10042ad4f  cmp     [rcx+40h], ebx
0x10042ad52  jz      short loc_10042ADAE
0x10042ad54  mov     rcx, [rcx+38h]; pszString
0x10042ad58  lea     rax, [rsp+0C8h+var_88]
0x10042ad5d  mov     [rsp+0C8h+pdwFlags], rbx; pdwFlags
0x10042ad62  lea     ebp, [rbx+14h]
0x10042ad65  mov     [rsp+0C8h+pdwSkip], rbx; pdwSkip
0x10042ad6a  lea     r9, [rsp+0C8h+pbBinary]; pbBinary
0x10042ad6f  xor     edx, edx; cchString
0x10042ad71  mov     [rsp+0C8h+var_88], ebp
0x10042ad75  lea     r8d, [rbx+4]; dwFlags
0x10042ad79  mov     [rsp+0C8h+pcbBinary], rax; pcbBinary
0x10042ad7e  call    cs:__imp_CryptStringToBinaryW
0x10042ad84  test    eax, eax
0x10042ad86  jnz     short loc_10042AD93
0x10042ad88  call    cs:__imp_GetLastError
0x10042ad8e  jmp     loc_10042AF06
0x10042ad93  lea     rax, [rsp+0C8h+pbBinary]
0x10042ad98  mov     [rsp+0C8h+pvFindPara], ebp
0x10042ad9c  mov     [rsp+0C8h+var_70], rax
0x10042ada1  lea     rbp, [rsp+0C8h+pvFindPara]
0x10042ada6  mov     r14d, 10000h
0x10042adac  jmp     short loc_10042ADC1
0x10042adae  mov     rbp, [rcx+38h]
0x10042adb2  test    rbp, rbp
0x10042adb5  jz      loc_10042AEB4
0x10042adbb  mov     r14d, 80007h
0x10042adc1  xor     r8d, r8d; hCryptProv
0x10042adc4  lea     rax, aMy_1; "MY"
0x10042adcb  mov     r9d, 28000h; dwFlags
0x10042add1  mov     [rsp+0C8h+pcbBinary], rax; struct _SecHandle **
0x10042add6  lea     edx, [r8+1]; dwEncodingType
0x10042adda  lea     ecx, [rdx+9]; lpszStoreProvider
0x10042addd  call    cs:__imp_CertOpenStore
0x10042ade3  mov     [rsi], rax
0x10042ade6  test    rax, rax
0x10042ade9  jz      short loc_10042AE1C
0x10042adeb  mov     r9, r15; struct _CERT_CONTEXT **
0x10042adee  mov     [rsp+0C8h+pcbBinary], rbx; struct _SecHandle **
0x10042adf3  mov     r8, rbp; pvFindPara
0x10042adf6  mov     edx, r14d; dwFindType
0x10042adf9  mov     rcx, rax; hCertStore
0x10042adfc  call    ?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z; Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,_SecHandle * *)
0x10042ae01  mov     ebx, eax
0x10042ae03  test    eax, eax
0x10042ae05  jz      loc_10042AEB0
0x10042ae0b  mov     rcx, [rsi]; hCertStore
0x10042ae0e  xor     edx, edx; dwFlags
0x10042ae10  call    cs:__imp_CertCloseStore
0x10042ae16  and     qword ptr [rsi], 0
0x10042ae1a  jmp     short loc_10042AE2C
0x10042ae1c  call    cs:__imp_GetLastError
0x10042ae22  mov     ebx, eax
0x10042ae24  test    eax, eax
0x10042ae26  jz      loc_10042AEB0
0x10042ae2c  lea     rdx, szSubsystemProtocol; "MY"
0x10042ae33  xor     ecx, ecx; hProv
0x10042ae35  call    cs:__imp_CertOpenSystemStoreA
0x10042ae3b  mov     [rsi], rax
0x10042ae3e  test    rax, rax
0x10042ae41  jz      short loc_10042AE71
0x10042ae43  and     [rsp+0C8h+pcbBinary], 0
0x10042ae49  mov     r9, r15; struct _CERT_CONTEXT **
0x10042ae4c  mov     r8, rbp; pvFindPara
0x10042ae4f  mov     edx, r14d; dwFindType
0x10042ae52  mov     rcx, rax; hCertStore
0x10042ae55  call    ?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z; Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,_SecHandle * *)
0x10042ae5a  mov     ebx, eax
0x10042ae5c  test    eax, eax
0x10042ae5e  jz      short loc_10042AEB0
0x10042ae60  mov     rcx, [rsi]; hCertStore
0x10042ae63  xor     edx, edx; dwFlags
0x10042ae65  call    cs:__imp_CertCloseStore
0x10042ae6b  and     qword ptr [rsi], 0
0x10042ae6f  jmp     short loc_10042AE7D
0x10042ae71  call    cs:__imp_GetLastError
0x10042ae77  mov     ebx, eax
0x10042ae79  test    eax, eax
0x10042ae7b  jz      short loc_10042AEB0
0x10042ae7d  mov     rax, [rdi+50h]
0x10042ae81  test    rax, rax
0x10042ae84  jz      short loc_10042AEB0
0x10042ae86  mov     rcx, [rsp+0C8h+var_80]
0x10042ae8b  mov     r9, r15
0x10042ae8e  mov     r8, [rdi+38h]
0x10042ae92  mov     edx, [rdi+40h]
0x10042ae95  mov     [rsp+0C8h+pdwFlags], r13
0x10042ae9a  mov     dword ptr [rsp+0C8h+pdwSkip], r12d
0x10042ae9f  mov     [rsp+0C8h+pcbBinary], rcx
0x10042aea4  mov     rcx, [rdi+48h]
0x10042aea8  call    cs:__guard_dispatch_icall_fptr
0x10042aeae  mov     ebx, eax
0x10042aeb0  mov     eax, ebx
0x10042aeb2  jmp     short loc_10042AF06
0x10042aeb4  mov     rax, [rcx+60h]
0x10042aeb8  test    rax, rax
0x10042aebb  jz      short loc_10042AED4
0x10042aebd  cmp     [rax], bx
0x10042aec0  jz      short loc_10042AED4
0x10042aec2  mov     r9, rsi; void **
0x10042aec5  mov     [rsp+0C8h+pcbBinary], r15; struct _CERT_CONTEXT **
0x10042aeca  mov     rdx, r13; unsigned __int16 *
0x10042aecd  call    ?ImportCertificateFromFile@Ssl@@CAKPEAVSNIAuthProviderInfo@@PEAGKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z; Ssl::ImportCertificateFromFile(SNIAuthProviderInfo *,ushort *,ulong,void * *,_CERT_CONTEXT const * *)
0x10042aed2  jmp     short loc_10042AF06
0x10042aed4  test    byte ptr cs:_bidGblFlags, 2
0x10042aedb  mov     edi, 0Dh
0x10042aee0  jz      short loc_10042AF04
0x10042aee2  mov     rcx, cs:off_1005E53A0; "<Ssl::AcquireCertContext|ERR|SNI> Acqui"...
0x10042aee9  test    rcx, rcx
0x10042aeec  jz      short loc_10042AF04
0x10042aeee  mov     r8, cs:off_1005E53A0; "<Ssl::AcquireCertContext|ERR|SNI> Acqui"...
0x10042aef5  mov     r9d, edi
0x10042aef8  mov     edx, 0C0000h
0x10042aefd  xor     ecx, ecx
0x10042aeff  call    _bidTraceW
0x10042af04  mov     eax, edi
0x10042af06  mov     rcx, [rsp+0C8h+var_50]
0x10042af0b  xor     rcx, rsp; StackCookie
0x10042af0e  call    __security_check_cookie
0x10042af13  add     rsp, 88h
0x10042af1a  pop     r15
0x10042af1c  pop     r14
0x10042af1e  pop     r13
0x10042af20  pop     r12
0x10042af22  pop     rdi
0x10042af23  pop     rsi
0x10042af24  pop     rbp
0x10042af25  pop     rbx
0x10042af26  retn
```
