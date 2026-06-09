# CFveApi::GenerateNbp(ulong,uchar *)

- ea: `0x180058a40`
- end: `0x180058cd4`
- name: `?GenerateNbp@CFveApi@@QEAAJKPEAE@Z`
- size: `660`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000ca78`
- `0x180067270`

## callees

- `0x180009790`
- `0x18000ba30`
- `0x18000d0b0`
- `0x180058a40`
- `0x180058cdc`
- `0x1800b6964`
- `0x1800d0dc8`
- `0x1800d1258`
- `0x1800d1574`
- `0x1800d19c0`
- `0x18011efc2`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058b08`
- `CRYPT32!CertCloseStore` at `0x180058c9d`
- `CRYPT32!CertCloseStore` at `0x1801214c7`
- `CRYPT32!CertCloseStore` at `0x180058c9d`
- `CRYPT32!CertCloseStore` at `0x1801214c7`
- `CRYPT32!CertOpenStore` at `0x180058aef`
- `CRYPT32!CertOpenStore` at `0x180058aef`
- `CRYPT32!CertFreeCertificateContext` at `0x180058c87`
- `CRYPT32!CertFreeCertificateContext` at `0x1801214af`
- `CRYPT32!CertFreeCertificateContext` at `0x180058c87`
- `CRYPT32!CertFreeCertificateContext` at `0x1801214af`

## pseudocode

```c
__int64 __fastcall CFveApi::GenerateNbp(CFveApi *this, unsigned int a2, unsigned __int8 *a3)
{
  int v6; // r14d
  HCERTSTORE v7; // rsi
  int NbpCert; // ebx
  CFveApi *v9; // rcx
  signed int LastError; // eax
  CFveApi *v11; // rcx
  void *lpMem; // [rsp+58h] [rbp-70h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-68h] BYREF
  int v15; // [rsp+68h] [rbp-60h] BYREF
  int v16; // [rsp+6Ch] [rbp-5Ch] BYREF
  HCERTSTORE v17; // [rsp+70h] [rbp-58h]
  CFveApi *v18; // [rsp+78h] [rbp-50h]
  struct _GUID Buf1; // [rsp+80h] [rbp-48h] BYREF

  v18 = this;
  Buf1 = 0;
  v6 = 0;
  v16 = 0;
  v15 = 0;
  v7 = 0;
  v17 = 0;
  pCertContext = 0;
  lpMem = 0;
  if ( a2 && a3 )
  {
    if ( !*((_BYTE *)this + 1158) )
    {
      NbpCert = CFveApi::ReopenWritable(this, (unsigned __int16 **)&lpMem);
      if ( NbpCert < 0 )
        goto LABEL_20;
      v6 = 1;
    }
    v7 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x88000u, L"FVE_NBP");
    v17 = v7;
    if ( v7 )
    {
      NbpCert = CFveApi::FindNbpCert(v9, v7, a2, a3, &pCertContext);
      if ( NbpCert >= 0 )
      {
        if ( pCertContext )
        {
          NbpCert = CFveApi::RemoveUnmatchedNetworkProtectorAuthInfo(this, 1, a3, a2, 0x20u, 8u, &v16, &v15, &Buf1);
          if ( NbpCert >= 0 )
          {
            if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) || (NbpCert = CFveApi::IsNbpSupported(v11), NbpCert >= 0) )
            {
              NbpCert = CFveApi::CreateNbp(this, pCertContext);
              if ( NbpCert >= 0 )
              {
                if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u)
                  || (NbpCert = CFveApi::DeleteAuthMethod(this, &Buf1, 1), NbpCert >= 0) )
                {
                  NbpCert = CFveApiBase::CommitChangesHelper((__int64)this, 0, 0, 0);
                }
              }
            }
          }
        }
        else
        {
          NbpCert = -2146885628;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      NbpCert = LastError;
      if ( LastError > 0 )
        NbpCert = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    NbpCert = -2147024809;
  }
LABEL_20:
  if ( v6 )
    CFveApiBase::Open(this, (const unsigned __int16 *)lpMem, 0, 0);
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v7 )
    CertCloseStore(v7, 0);
  return (unsigned int)NbpCert;
}

```

## disassembly

```asm
0x180058a40  mov     r11, rsp
0x180058a43  mov     [r11+20h], rbx
0x180058a47  push    rsi
0x180058a48  push    rdi
0x180058a49  push    r12
0x180058a4b  push    r14
0x180058a4d  push    r15
0x180058a4f  sub     rsp, 0A0h
0x180058a56  mov     rax, cs:__security_cookie
0x180058a5d  xor     rax, rsp
0x180058a60  mov     [rsp+0C8h+var_38], rax
0x180058a68  mov     r12, r8
0x180058a6b  mov     r15d, edx
0x180058a6e  mov     rdi, rcx
0x180058a71  mov     [rsp+0C8h+var_50], rcx
0x180058a76  xorps   xmm0, xmm0
0x180058a79  movups  xmmword ptr [r11-48h], xmm0
0x180058a7e  xor     r14d, r14d
0x180058a81  mov     [r11-74h], r14d
0x180058a85  mov     [r11-5Ch], r14d
0x180058a89  mov     [r11-60h], r14d
0x180058a8d  xor     esi, esi
0x180058a8f  mov     [r11-58h], rsi
0x180058a93  mov     [r11-68h], rsi
0x180058a97  mov     [r11-70h], rsi
0x180058a9b  test    edx, edx
0x180058a9d  jz      loc_180058C4D
0x180058aa3  test    r8, r8
0x180058aa6  jz      loc_180058C4D
0x180058aac  cmp     [rcx+486h], sil
0x180058ab3  jnz     short loc_180058AD5
0x180058ab5  lea     rdx, [r11-70h]; unsigned __int16 **
0x180058ab9  call    ?ReopenWritable@CFveApi@@AEAAJPEAPEAG@Z; CFveApi::ReopenWritable(ushort * *)
0x180058abe  mov     ebx, eax
0x180058ac0  mov     [rsp+0C8h+var_78], eax
0x180058ac4  test    eax, eax
0x180058ac6  js      loc_180058C56
0x180058acc  lea     r14d, [rsi+1]
0x180058ad0  mov     [rsp+0C8h+var_74], r14d
0x180058ad5  lea     rax, aFveNbp; "FVE_NBP"
0x180058adc  mov     [rsp+0C8h+pvPara], rax; pvPara
0x180058ae1  mov     r9d, 88000h; dwFlags
0x180058ae7  xor     r8d, r8d; hCryptProv
0x180058aea  xor     edx, edx; dwEncodingType
0x180058aec  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x180058aef  call    cs:__imp_CertOpenStore
0x180058af6  nop     dword ptr [rax+rax+00h]
0x180058afb  mov     rsi, rax
0x180058afe  mov     [rsp+0C8h+var_58], rax
0x180058b03  test    rax, rax
0x180058b06  jnz     short loc_180058B2C
0x180058b08  call    cs:__imp_GetLastError
0x180058b0f  nop     dword ptr [rax+rax+00h]
0x180058b14  mov     ebx, eax
0x180058b16  test    eax, eax
0x180058b18  jle     loc_180058C52
0x180058b1e  movzx   ebx, ax
0x180058b21  or      ebx, 80070000h
0x180058b27  jmp     loc_180058C52
0x180058b2c  lea     rax, [rsp+0C8h+pCertContext]
0x180058b31  mov     [rsp+0C8h+pvPara], rax; struct _CERT_CONTEXT **
0x180058b36  mov     r9, r12; unsigned __int8 *
0x180058b39  mov     r8d, r15d; unsigned int
0x180058b3c  mov     rdx, rsi; void *
0x180058b3f  call    ?FindNbpCert@CFveApi@@AEAAJPEAXKPEAEPEAPEBU_CERT_CONTEXT@@@Z; CFveApi::FindNbpCert(void *,ulong,uchar *,_CERT_CONTEXT const * *)
0x180058b44  mov     ebx, eax
0x180058b46  mov     [rsp+0C8h+var_78], eax
0x180058b4a  test    eax, eax
0x180058b4c  js      loc_180058C56
0x180058b52  cmp     [rsp+0C8h+pCertContext], 0
0x180058b58  jnz     short loc_180058B64
0x180058b5a  mov     ebx, 80092004h
0x180058b5f  jmp     loc_180058C52
0x180058b64  lea     rax, [rsp+0C8h+Buf1]
0x180058b6c  mov     [rsp+0C8h+var_88], rax; struct _GUID *
0x180058b71  lea     rax, [rsp+0C8h+var_60]
0x180058b76  mov     [rsp+0C8h+var_90], rax; int *
0x180058b7b  lea     rax, [rsp+0C8h+var_5C]
0x180058b80  mov     [rsp+0C8h+var_98], rax; int *
0x180058b85  mov     [rsp+0C8h+var_A0], 8; unsigned int
0x180058b8d  mov     dword ptr [rsp+0C8h+pvPara], 20h ; ' '; unsigned int
0x180058b95  mov     r9d, r15d; unsigned int
0x180058b98  mov     r8, r12; void *
0x180058b9b  mov     edx, 1; int
0x180058ba0  mov     rcx, rdi; this
0x180058ba3  call    ?RemoveUnmatchedNetworkProtectorAuthInfo@CFveApi@@AEAAJHPEAXKKKPEAH1PEAU_GUID@@@Z; CFveApi::RemoveUnmatchedNetworkProtectorAuthInfo(int,void *,ulong,ulong,ulong,int *,int *,_GUID *)
0x180058ba8  mov     ebx, eax
0x180058baa  mov     [rsp+0C8h+var_78], eax
0x180058bae  test    eax, eax
0x180058bb0  js      loc_180058C56
0x180058bb6  mov     r15d, 10h
0x180058bbc  mov     r8d, r15d; Size
0x180058bbf  lea     rdx, GUID_NULL; Buf2
0x180058bc6  lea     rcx, [rsp+0C8h+Buf1]; Buf1
0x180058bce  call    memcmp_0
0x180058bd3  test    eax, eax
0x180058bd5  jnz     short loc_180058BE6
0x180058bd7  call    ?IsNbpSupported@CFveApi@@AEAAJXZ; CFveApi::IsNbpSupported(void)
0x180058bdc  mov     ebx, eax
0x180058bde  mov     [rsp+0C8h+var_78], eax
0x180058be2  test    eax, eax
0x180058be4  js      short loc_180058C56
0x180058be6  mov     rdx, [rsp+0C8h+pCertContext]; struct _CERT_CONTEXT *
0x180058beb  mov     rcx, rdi; this
0x180058bee  call    ?CreateNbp@CFveApi@@AEAAJPEBU_CERT_CONTEXT@@@Z; CFveApi::CreateNbp(_CERT_CONTEXT const *)
0x180058bf3  mov     ebx, eax
0x180058bf5  mov     [rsp+0C8h+var_78], eax
0x180058bf9  test    eax, eax
0x180058bfb  js      short loc_180058C56
0x180058bfd  mov     r8, r15; Size
0x180058c00  lea     rdx, GUID_NULL; Buf2
0x180058c07  lea     rcx, [rsp+0C8h+Buf1]; Buf1
0x180058c0f  call    memcmp_0
0x180058c14  test    eax, eax
0x180058c16  jz      short loc_180058C35
0x180058c18  mov     r8b, 1; bool
0x180058c1b  lea     rdx, [rsp+0C8h+Buf1]; struct _GUID *
0x180058c23  mov     rcx, rdi; this
0x180058c26  call    ?DeleteAuthMethod@CFveApi@@QEAAJPEBU_GUID@@_N@Z; CFveApi::DeleteAuthMethod(_GUID const *,bool)
0x180058c2b  mov     ebx, eax
0x180058c2d  mov     [rsp+0C8h+var_78], eax
0x180058c31  test    eax, eax
0x180058c33  js      short loc_180058C56
0x180058c35  xor     r9d, r9d
0x180058c38  xor     r8d, r8d
0x180058c3b  xor     edx, edx
0x180058c3d  mov     rcx, rdi
0x180058c40  call    ?CommitChangesHelper@CFveApiBase@@AEAAJ_NW4_FVE_COMMIT_SCENARIO_TYPE@@K@Z; CFveApiBase::CommitChangesHelper(bool,_FVE_COMMIT_SCENARIO_TYPE,ulong)
0x180058c45  mov     ebx, eax
0x180058c47  mov     [rsp+0C8h+var_78], eax
0x180058c4b  jmp     short loc_180058C56
0x180058c4d  mov     ebx, 80070057h
0x180058c52  mov     [rsp+0C8h+var_78], ebx
0x180058c56  test    r14d, r14d
0x180058c59  jz      short loc_180058C6E
0x180058c5b  xor     r9d, r9d; bool
0x180058c5e  xor     r8d, r8d; unsigned int
0x180058c61  mov     rdx, [rsp+0C8h+lpMem]; unsigned __int16 *
0x180058c66  mov     rcx, rdi; this
0x180058c69  call    ?Open@CFveApiBase@@QEAAJPEBGK_N@Z; CFveApiBase::Open(ushort const *,ulong,bool)
0x180058c6e  mov     rcx, [rsp+0C8h+lpMem]; lpMem
0x180058c73  test    rcx, rcx
0x180058c76  jz      short loc_180058C7D
0x180058c78  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180058c7d  mov     rcx, [rsp+0C8h+pCertContext]; pCertContext
0x180058c82  test    rcx, rcx
0x180058c85  jz      short loc_180058C93
0x180058c87  call    cs:__imp_CertFreeCertificateContext
0x180058c8e  nop     dword ptr [rax+rax+00h]
0x180058c93  test    rsi, rsi
0x180058c96  jz      short loc_180058CA9
0x180058c98  xor     edx, edx; dwFlags
0x180058c9a  mov     rcx, rsi; hCertStore
0x180058c9d  call    cs:__imp_CertCloseStore
0x180058ca4  nop     dword ptr [rax+rax+00h]
0x180058ca9  mov     eax, ebx
0x180058cab  mov     rcx, [rsp+0C8h+var_38]
0x180058cb3  xor     rcx, rsp; StackCookie
0x180058cb6  call    __security_check_cookie
0x180058cbb  mov     rbx, [rsp+0C8h+arg_18]
0x180058cc3  add     rsp, 0A0h
0x180058cca  pop     r15
0x180058ccc  pop     r14
0x180058cce  pop     r12
0x180058cd0  pop     rdi
0x180058cd1  pop     rsi
0x180058cd2  retn
0x180121474  push    rbp
0x180121476  sub     rsp, 50h
0x18012147a  mov     rbp, rdx
0x18012147d  cmp     dword ptr [rbp+54h], 0
0x180121481  jz      short loc_180121497
0x180121483  xor     r9d, r9d; bool
0x180121486  xor     r8d, r8d; unsigned int
0x180121489  mov     rdx, [rbp+58h]; unsigned __int16 *
0x18012148d  mov     rcx, [rbp+78h]; this
0x180121491  call    ?Open@CFveApiBase@@QEAAJPEBGK_N@Z; CFveApiBase::Open(ushort const *,ulong,bool)
0x180121496  nop
0x180121497  mov     rcx, [rbp+58h]; lpMem
0x18012149b  test    rcx, rcx
0x18012149e  jz      short loc_1801214A6
0x1801214a0  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1801214a5  nop
0x1801214a6  mov     rcx, [rbp+60h]; pCertContext
0x1801214aa  test    rcx, rcx
0x1801214ad  jz      short loc_1801214BC
0x1801214af  call    cs:__imp_CertFreeCertificateContext
0x1801214b6  nop     dword ptr [rax+rax+00h]
0x1801214bb  nop
0x1801214bc  mov     rcx, [rbp+70h]; hCertStore
0x1801214c0  test    rcx, rcx
0x1801214c3  jz      short loc_1801214DB
0x1801214c5  xor     edx, edx; dwFlags
0x1801214c7  call    cs:__imp_CertCloseStore
0x1801214ce  nop     dword ptr [rax+rax+00h]
0x1801214d3  mov     qword ptr [rbp+70h], 0
0x1801214db  add     rsp, 50h
0x1801214df  pop     rbp
0x1801214e0  retn
```
