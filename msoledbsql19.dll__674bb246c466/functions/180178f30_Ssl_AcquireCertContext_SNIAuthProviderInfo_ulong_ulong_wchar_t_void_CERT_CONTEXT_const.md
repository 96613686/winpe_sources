# Ssl::AcquireCertContext(SNIAuthProviderInfo *,ulong *,ulong,wchar_t *,void * *,_CERT_CONTEXT const * *)

- ea: `0x180178f30`
- end: `0x18017912b`
- name: `?AcquireCertContext@Ssl@@CAKPEAVSNIAuthProviderInfo@@PEAKKPEA_WPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `507`
- prototype: `unsigned int __fastcall(struct SNIAuthProviderInfo *, unsigned int *, unsigned int, wchar_t *, void **, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180179140`

## callees

- `0x180003d80`
- `0x180178f30`
- `0x18017a770`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180178fd7`
- `KERNEL32!GetLastError` at `0x180179068`
- `KERNEL32!GetLastError` at `0x1801790c3`
- `KERNEL32!GetLastError` at `0x180178fd7`
- `KERNEL32!GetLastError` at `0x180179068`
- `KERNEL32!GetLastError` at `0x1801790c3`
- `CRYPT32!CertOpenStore` at `0x180179026`
- `CRYPT32!CertOpenStore` at `0x180179026`
- `CRYPT32!CertCloseStore` at `0x180179059`
- `CRYPT32!CertCloseStore` at `0x1801790b4`
- `CRYPT32!CertCloseStore` at `0x180179059`
- `CRYPT32!CertCloseStore` at `0x1801790b4`
- `CRYPT32!CertOpenSystemStoreA` at `0x180179081`
- `CRYPT32!CertOpenSystemStoreA` at `0x180179081`
- `CRYPT32!CryptStringToBinaryW` at `0x180178fcd`
- `CRYPT32!CryptStringToBinaryW` at `0x180178fcd`

## pseudocode

```c
DWORD __fastcall Ssl::AcquireCertContext(
        struct SNIAuthProviderInfo *a1,
        unsigned int *a2,
        int a3,
        wchar_t *a4,
        void **a5,
        struct _CERT_CONTEXT **a6)
{
  WCHAR *p_pvFindPara; // rbp
  DWORD v11; // r15d
  HCERTSTORE v12; // rax
  DWORD Certificate; // ebx
  HCERTSTORE v14; // rax
  __int64 (__fastcall *v15)(_QWORD, _QWORD, _QWORD, struct _CERT_CONTEXT **, unsigned int *, int, wchar_t *); // rax
  __int128 pvFindPara; // [rsp+48h] [rbp-80h] BYREF
  DWORD pcbBinary; // [rsp+58h] [rbp-70h] BYREF
  BYTE pbBinary[24]; // [rsp+60h] [rbp-68h] BYREF

  pvFindPara = 0;
  if ( a2 )
    *a2 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  p_pvFindPara = (WCHAR *)*((_QWORD *)a1 + 8);
  if ( *((_DWORD *)a1 + 18) )
  {
    pcbBinary = 20;
    if ( !CryptStringToBinaryW(p_pvFindPara, 0, 4u, pbBinary, &pcbBinary, 0, 0) )
      return GetLastError();
    LODWORD(pvFindPara) = 20;
    *((_QWORD *)&pvFindPara + 1) = pbBinary;
    p_pvFindPara = (WCHAR *)&pvFindPara;
    v11 = 0x10000;
  }
  else
  {
    v11 = 524295;
  }
  v12 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"MY");
  *a5 = v12;
  if ( v12 )
  {
    Certificate = Ssl::FindAndLoadCertificate(v12, v11, p_pvFindPara, (const struct _CERT_CONTEXT **)a6, 0);
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
  v14 = CertOpenSystemStoreA(0, "MY");
  *a5 = v14;
  if ( v14 )
  {
    Certificate = Ssl::FindAndLoadCertificate(v14, v11, p_pvFindPara, (const struct _CERT_CONTEXT **)a6, 0);
    if ( Certificate )
    {
      CertCloseStore(*a5, 0);
      *a5 = 0;
      goto LABEL_20;
    }
  }
  else
  {
    Certificate = GetLastError();
    if ( Certificate )
    {
LABEL_20:
      v15 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _CERT_CONTEXT **, unsigned int *, int, wchar_t *))*((_QWORD *)a1 + 11);
      if ( v15 )
        return v15(*((_QWORD *)a1 + 10), *((unsigned int *)a1 + 18), *((_QWORD *)a1 + 8), a6, a2, a3, a4);
    }
  }
  return Certificate;
}

```

## disassembly

```asm
0x180178f30  push    rbx
0x180178f32  push    rbp
0x180178f33  push    rsi
0x180178f34  push    rdi
0x180178f35  push    r12
0x180178f37  push    r13
0x180178f39  push    r14
0x180178f3b  sub     rsp, 90h
0x180178f42  mov     rax, cs:__security_cookie
0x180178f49  xor     rax, rsp
0x180178f4c  mov     [rsp+0C8h+var_50], rax
0x180178f51  mov     rdi, [rsp+0C8h+arg_20]
0x180178f59  xor     ebx, ebx
0x180178f5b  mov     r14, [rsp+0C8h+arg_28]
0x180178f63  xorps   xmm0, xmm0
0x180178f66  mov     [rsp+0C8h+var_88], r9
0x180178f6b  mov     r13d, r8d
0x180178f6e  mov     r12, rdx
0x180178f71  mov     rsi, rcx
0x180178f74  movups  [rsp+0C8h+pvFindPara], xmm0
0x180178f79  test    rdx, rdx
0x180178f7c  jz      short loc_180178F80
0x180178f7e  mov     [rdx], ebx
0x180178f80  test    rdi, rdi
0x180178f83  jz      short loc_180178F88
0x180178f85  mov     [rdi], rbx
0x180178f88  test    r14, r14
0x180178f8b  jz      short loc_180178F90
0x180178f8d  mov     [r14], rbx
0x180178f90  mov     rbp, [rcx+40h]
0x180178f94  mov     [rsp+0C8h+var_40], r15
0x180178f9c  cmp     [rcx+48h], ebx
0x180178f9f  jz      short loc_180179001
0x180178fa1  mov     [rsp+0C8h+pdwFlags], rbx; pdwFlags
0x180178fa6  lea     rax, [rsp+0C8h+var_70]
0x180178fab  mov     [rsp+0C8h+pdwSkip], rbx; pdwSkip
0x180178fb0  lea     r9, [rsp+0C8h+pbBinary]; pbBinary
0x180178fb5  xor     edx, edx; cchString
0x180178fb7  mov     [rsp+0C8h+pcbBinary], rax; pcbBinary
0x180178fbc  mov     r8d, 4; dwFlags
0x180178fc2  mov     [rsp+0C8h+var_70], 14h
0x180178fca  mov     rcx, rbp; pszString
0x180178fcd  call    cs:__imp_CryptStringToBinaryW
0x180178fd3  test    eax, eax
0x180178fd5  jnz     short loc_180178FE2
0x180178fd7  call    cs:__imp_GetLastError
0x180178fdd  jmp     loc_180179104
0x180178fe2  lea     rax, [rsp+0C8h+pbBinary]
0x180178fe7  mov     dword ptr [rsp+0C8h+pvFindPara], 14h
0x180178fef  mov     qword ptr [rsp+0C8h+pvFindPara+8], rax
0x180178ff4  lea     rbp, [rsp+0C8h+pvFindPara]
0x180178ff9  mov     r15d, 10000h
0x180178fff  jmp     short loc_180179007
0x180179001  mov     r15d, 80007h
0x180179007  lea     rax, aMy_0; "MY"
0x18017900e  mov     r9d, 28000h; dwFlags
0x180179014  xor     r8d, r8d; hCryptProv
0x180179017  mov     [rsp+0C8h+pcbBinary], rax; pvPara
0x18017901c  mov     edx, 1; dwEncodingType
0x180179021  mov     ecx, 0Ah; lpszStoreProvider
0x180179026  call    cs:__imp_CertOpenStore
0x18017902c  mov     [rdi], rax
0x18017902f  test    rax, rax
0x180179032  jz      short loc_180179068
0x180179034  mov     r9, r14; struct _CERT_CONTEXT **
0x180179037  mov     [rsp+0C8h+pcbBinary], rbx; struct _SecHandle **
0x18017903c  mov     r8, rbp; pvFindPara
0x18017903f  mov     edx, r15d; dwFindType
0x180179042  mov     rcx, rax; hCertStore
0x180179045  call    ?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z; Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,_SecHandle * *)
0x18017904a  mov     ebx, eax
0x18017904c  test    eax, eax
0x18017904e  jz      loc_180179102
0x180179054  mov     rcx, [rdi]; hCertStore
0x180179057  xor     edx, edx; dwFlags
0x180179059  call    cs:__imp_CertCloseStore
0x18017905f  mov     qword ptr [rdi], 0
0x180179066  jmp     short loc_180179078
0x180179068  call    cs:__imp_GetLastError
0x18017906e  mov     ebx, eax
0x180179070  test    eax, eax
0x180179072  jz      loc_180179102
0x180179078  lea     rdx, szSubsystemProtocol; "MY"
0x18017907f  xor     ecx, ecx; hProv
0x180179081  call    cs:__imp_CertOpenSystemStoreA
0x180179087  mov     [rdi], rax
0x18017908a  test    rax, rax
0x18017908d  jz      short loc_1801790C3
0x18017908f  mov     r9, r14; struct _CERT_CONTEXT **
0x180179092  mov     [rsp+0C8h+pcbBinary], 0; struct _SecHandle **
0x18017909b  mov     r8, rbp; pvFindPara
0x18017909e  mov     edx, r15d; dwFindType
0x1801790a1  mov     rcx, rax; hCertStore
0x1801790a4  call    ?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z; Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,_SecHandle * *)
0x1801790a9  mov     ebx, eax
0x1801790ab  test    eax, eax
0x1801790ad  jz      short loc_180179102
0x1801790af  mov     rcx, [rdi]; hCertStore
0x1801790b2  xor     edx, edx; dwFlags
0x1801790b4  call    cs:__imp_CertCloseStore
0x1801790ba  mov     qword ptr [rdi], 0
0x1801790c1  jmp     short loc_1801790CF
0x1801790c3  call    cs:__imp_GetLastError
0x1801790c9  mov     ebx, eax
0x1801790cb  test    eax, eax
0x1801790cd  jz      short loc_180179102
0x1801790cf  mov     rax, [rsi+58h]
0x1801790d3  test    rax, rax
0x1801790d6  jz      short loc_180179102
0x1801790d8  mov     rcx, [rsp+0C8h+var_88]
0x1801790dd  mov     r9, r14
0x1801790e0  mov     r8, [rsi+40h]
0x1801790e4  mov     edx, [rsi+48h]
0x1801790e7  mov     [rsp+0C8h+pdwFlags], rcx
0x1801790ec  mov     rcx, [rsi+50h]
0x1801790f0  mov     dword ptr [rsp+0C8h+pdwSkip], r13d
0x1801790f5  mov     [rsp+0C8h+pcbBinary], r12
0x1801790fa  call    cs:__guard_dispatch_icall_fptr
0x180179100  mov     ebx, eax
0x180179102  mov     eax, ebx
0x180179104  mov     r15, [rsp+0C8h+var_40]
0x18017910c  mov     rcx, [rsp+0C8h+var_50]
0x180179111  xor     rcx, rsp; StackCookie
0x180179114  call    __security_check_cookie
0x180179119  add     rsp, 90h
0x180179120  pop     r14
0x180179122  pop     r13
0x180179124  pop     r12
0x180179126  pop     rdi
0x180179127  pop     rsi
0x180179128  pop     rbp
0x180179129  pop     rbx
0x18017912a  retn
```
