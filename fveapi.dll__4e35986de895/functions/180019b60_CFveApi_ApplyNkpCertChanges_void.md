# CFveApi::ApplyNkpCertChanges(void)

- ea: `0x180019b60`
- end: `0x180019de4`
- name: `?ApplyNkpCertChanges@CFveApi@@QEAAJXZ`
- size: `644`
- prototype: `__int64 __fastcall(CFveApi *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180017ba0`
- `0x1800ac05c`

## callees

- `0x180009790`
- `0x18000ba30`
- `0x18000d0b0`
- `0x180019b60`
- `0x180019dec`
- `0x180019e74`
- `0x180037f50`
- `0x180044470`
- `0x180058cdc`
- `0x1800d0ff0`
- `0x1800d135c`
- `0x1800d1468`
- `0x1800d19c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c60`
- `CRYPT32!CertCloseStore` at `0x180019dd6`
- `CRYPT32!CertCloseStore` at `0x180120070`
- `CRYPT32!CertCloseStore` at `0x180019dd6`
- `CRYPT32!CertCloseStore` at `0x180120070`
- `CRYPT32!CertOpenStore` at `0x180019cca`
- `CRYPT32!CertOpenStore` at `0x180019cca`
- `CRYPT32!CertFreeCertificateContext` at `0x180019dc3`
- `CRYPT32!CertFreeCertificateContext` at `0x180120058`
- `CRYPT32!CertFreeCertificateContext` at `0x180019dc3`
- `CRYPT32!CertFreeCertificateContext` at `0x180120058`

## pseudocode

```c
__int64 __fastcall CFveApi::ApplyNkpCertChanges(CFveApi *this)
{
  void *v2; // r14
  int v3; // r15d
  CFveApi *v4; // rcx
  signed int IsNkpSupported; // ebx
  int v6; // esi
  int v7; // esi
  signed int LastError; // eax
  HCERTSTORE v9; // rax
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-50h] BYREF
  void *lpMem; // [rsp+60h] [rbp-48h] BYREF
  void *v13; // [rsp+68h] [rbp-40h] BYREF
  HCERTSTORE v14; // [rsp+70h] [rbp-38h]
  unsigned int v15; // [rsp+B8h] [rbp+10h] BYREF
  int v16; // [rsp+C0h] [rbp+18h] BYREF
  int v17; // [rsp+C8h] [rbp+20h] BYREF

  v2 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  pCertContext = 0;
  v17 = 0;
  v16 = 0;
  v3 = 0;
  lpMem = 0;
  IsNkpSupported = CFveApi::IsNkpSupported(this);
  if ( IsNkpSupported < 0 )
    goto LABEL_22;
  if ( *((_BYTE *)this + 1158) )
  {
    v6 = 1;
  }
  else
  {
    IsNkpSupported = CFveApi::ReopenWritable(this, (unsigned __int16 **)&lpMem);
    if ( IsNkpSupported < 0 )
      goto LABEL_22;
    v6 = 1;
    v3 = 1;
  }
  if ( !(unsigned int)CFveApi::AllowNkpManagement(v4) )
    goto LABEL_5;
  v9 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x88000u, L"FVE_NKP");
  v2 = v9;
  v14 = v9;
  if ( v9 )
  {
    IsNkpSupported = CFveApi::FindNkpCert(v9, &pCertContext);
    if ( IsNkpSupported < 0 )
      goto LABEL_22;
    if ( pCertContext )
    {
      IsNkpSupported = CFveApi::GetCertificateHash(pCertContext, &v13, &v15);
      if ( IsNkpSupported < 0 )
        goto LABEL_22;
      v6 = 0;
    }
LABEL_5:
    IsNkpSupported = CFveApi::RemoveUnmatchedNetworkProtectorAuthInfo(this, v6, v13, v15, 4u, 4u, &v17, &v16, 0);
    if ( IsNkpSupported >= 0 )
    {
      v7 = v16;
      if ( !v16
        || (IsNkpSupported = CFveApi::CreateNkp(this, pCertContext), IsNkpSupported >= 0)
        && (IsNkpSupported = CFveApi::GenerateNkpSessionKeys(this), IsNkpSupported >= 0) )
      {
        if ( v17 || v7 )
          IsNkpSupported = CFveApiBase::CommitChangesHelper(this, 0, 0, 0);
      }
    }
    goto LABEL_22;
  }
  LastError = GetLastError();
  IsNkpSupported = LastError;
  if ( LastError > 0 )
    IsNkpSupported = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
  if ( v3 )
    CFveApiBase::Open(this, (const unsigned __int16 *)lpMem, 0, 0);
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( v13 )
    CFveApiBase::ZeroFree(v13, v15);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v2 )
    CertCloseStore(v2, 0);
  return (unsigned int)IsNkpSupported;
}

```

## disassembly

```asm
0x180019b60  mov     rax, rsp
0x180019b63  mov     [rax+8], rcx
0x180019b67  push    rbx
0x180019b68  push    rsi
0x180019b69  push    rdi
0x180019b6a  push    r14
0x180019b6c  push    r15
0x180019b6e  sub     rsp, 80h
0x180019b75  mov     rdi, rcx
0x180019b78  xor     r14d, r14d
0x180019b7b  mov     [rax-38h], r14
0x180019b7f  mov     [rax-40h], r14
0x180019b83  mov     [rax+10h], r14d
0x180019b87  mov     [rax-50h], r14
0x180019b8b  mov     [rax+20h], r14d
0x180019b8f  mov     [rax+18h], r14d
0x180019b93  xor     r15d, r15d
0x180019b96  mov     [rax-54h], r15d
0x180019b9a  mov     [rax-48h], r14
0x180019b9e  call    ?IsNkpSupported@CFveApi@@AEAAJXZ; CFveApi::IsNkpSupported(void)
0x180019ba3  mov     ebx, eax
0x180019ba5  mov     [rsp+0A8h+var_58], eax
0x180019ba9  test    eax, eax
0x180019bab  js      loc_180019D5F
0x180019bb1  cmp     [rdi+486h], r15b
0x180019bb8  jz      loc_180019C84
0x180019bbe  lea     esi, [r14+1]
0x180019bc2  call    ?AllowNkpManagement@CFveApi@@AEAAHXZ; CFveApi::AllowNkpManagement(void)
0x180019bc7  test    eax, eax
0x180019bc9  jnz     loc_180019CB0
0x180019bcf  mov     [rsp+0A8h+var_68], 0; struct _GUID *
0x180019bd8  lea     rax, [rsp+0A8h+arg_10]
0x180019be0  mov     [rsp+0A8h+var_70], rax; int *
0x180019be5  lea     rax, [rsp+0A8h+arg_18]
0x180019bed  mov     [rsp+0A8h+var_78], rax; int *
0x180019bf2  mov     eax, 4
0x180019bf7  mov     [rsp+0A8h+var_80], eax; unsigned int
0x180019bfb  mov     dword ptr [rsp+0A8h+pvPara], eax; unsigned int
0x180019bff  mov     r9d, [rsp+0A8h+arg_8]; unsigned int
0x180019c07  mov     r8, [rsp+0A8h+var_40]; void *
0x180019c0c  mov     edx, esi; int
0x180019c0e  mov     rcx, rdi; this
0x180019c11  call    ?RemoveUnmatchedNetworkProtectorAuthInfo@CFveApi@@AEAAJHPEAXKKKPEAH1PEAU_GUID@@@Z; CFveApi::RemoveUnmatchedNetworkProtectorAuthInfo(int,void *,ulong,ulong,ulong,int *,int *,_GUID *)
0x180019c16  mov     ebx, eax
0x180019c18  mov     [rsp+0A8h+var_58], eax
0x180019c1c  test    eax, eax
0x180019c1e  js      loc_180019D5F
0x180019c24  mov     esi, [rsp+0A8h+arg_10]
0x180019c2b  test    esi, esi
0x180019c2d  jnz     loc_180019D32
0x180019c33  cmp     [rsp+0A8h+arg_18], 0
0x180019c3b  jnz     short loc_180019C45
0x180019c3d  test    esi, esi
0x180019c3f  jz      loc_180019D5F
0x180019c45  xor     r9d, r9d
0x180019c48  xor     r8d, r8d
0x180019c4b  xor     edx, edx
0x180019c4d  mov     rcx, rdi
0x180019c50  call    ?CommitChangesHelper@CFveApiBase@@AEAAJ_NW4_FVE_COMMIT_SCENARIO_TYPE@@K@Z; CFveApiBase::CommitChangesHelper(bool,_FVE_COMMIT_SCENARIO_TYPE,ulong)
0x180019c55  mov     ebx, eax
0x180019c57  mov     [rsp+0A8h+var_58], eax
0x180019c5b  jmp     loc_180019D5F
0x180019c60  call    cs:__imp_GetLastError
0x180019c67  nop     dword ptr [rax+rax+00h]
0x180019c6c  mov     ebx, eax
0x180019c6e  test    eax, eax
0x180019c70  jle     short loc_180019C7B
0x180019c72  movzx   ebx, ax
0x180019c75  or      ebx, 80070000h
0x180019c7b  mov     [rsp+0A8h+var_58], ebx
0x180019c7f  jmp     loc_180019D5F
0x180019c84  lea     rdx, [rsp+0A8h+lpMem]; unsigned __int16 **
0x180019c89  mov     rcx, rdi; this
0x180019c8c  call    ?ReopenWritable@CFveApi@@AEAAJPEAPEAG@Z; CFveApi::ReopenWritable(ushort * *)
0x180019c91  mov     ebx, eax
0x180019c93  mov     [rsp+0A8h+var_58], eax
0x180019c97  test    eax, eax
0x180019c99  js      loc_180019D5F
0x180019c9f  mov     esi, 1
0x180019ca4  mov     r15d, esi
0x180019ca7  mov     [rsp+0A8h+var_54], esi
0x180019cab  jmp     loc_180019BC2
0x180019cb0  lea     rax, aFveNkp; "FVE_NKP"
0x180019cb7  mov     [rsp+0A8h+pvPara], rax; pvPara
0x180019cbc  mov     r9d, 88000h; dwFlags
0x180019cc2  xor     r8d, r8d; hCryptProv
0x180019cc5  xor     edx, edx; dwEncodingType
0x180019cc7  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x180019cca  call    cs:__imp_CertOpenStore
0x180019cd1  nop     dword ptr [rax+rax+00h]
0x180019cd6  mov     r14, rax
0x180019cd9  mov     [rsp+0A8h+var_38], rax
0x180019cde  test    rax, rax
0x180019ce1  jz      loc_180019C60
0x180019ce7  lea     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT **
0x180019cec  mov     rcx, rax; hCertStore
0x180019cef  call    ?FindNkpCert@CFveApi@@CAJPEAXPEAPEBU_CERT_CONTEXT@@@Z; CFveApi::FindNkpCert(void *,_CERT_CONTEXT const * *)
0x180019cf4  mov     ebx, eax
0x180019cf6  mov     [rsp+0A8h+var_58], eax
0x180019cfa  test    eax, eax
0x180019cfc  js      short loc_180019D5F
0x180019cfe  cmp     [rsp+0A8h+pCertContext], 0
0x180019d04  jz      loc_180019BCF
0x180019d0a  lea     r8, [rsp+0A8h+arg_8]; unsigned int *
0x180019d12  lea     rdx, [rsp+0A8h+var_40]; void **
0x180019d17  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x180019d1c  call    ?GetCertificateHash@CFveApi@@SAJPEBU_CERT_CONTEXT@@PEAPEAXPEAK@Z; CFveApi::GetCertificateHash(_CERT_CONTEXT const *,void * *,ulong *)
0x180019d21  mov     ebx, eax
0x180019d23  mov     [rsp+0A8h+var_58], eax
0x180019d27  test    eax, eax
0x180019d29  js      short loc_180019D5F
0x180019d2b  xor     esi, esi
0x180019d2d  jmp     loc_180019BCF
0x180019d32  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x180019d37  mov     rcx, rdi; this
0x180019d3a  call    ?CreateNkp@CFveApi@@AEAAJPEBU_CERT_CONTEXT@@@Z; CFveApi::CreateNkp(_CERT_CONTEXT const *)
0x180019d3f  mov     ebx, eax
0x180019d41  mov     [rsp+0A8h+var_58], eax
0x180019d45  test    eax, eax
0x180019d47  js      short loc_180019D5F
0x180019d49  mov     rcx, rdi; this
0x180019d4c  call    ?GenerateNkpSessionKeys@CFveApi@@QEAAJXZ; CFveApi::GenerateNkpSessionKeys(void)
0x180019d51  mov     ebx, eax
0x180019d53  mov     [rsp+0A8h+var_58], eax
0x180019d57  test    eax, eax
0x180019d59  jns     loc_180019C33
0x180019d5f  test    r15d, r15d
0x180019d62  jnz     short loc_180019D99
0x180019d64  mov     rcx, [rsp+0A8h+lpMem]; lpMem
0x180019d69  test    rcx, rcx
0x180019d6c  jnz     short loc_180019DAE
0x180019d6e  mov     rcx, [rsp+0A8h+var_40]; lpMem
0x180019d73  test    rcx, rcx
0x180019d76  jnz     short loc_180019DB5
0x180019d78  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x180019d7d  test    rcx, rcx
0x180019d80  jnz     short loc_180019DC3
0x180019d82  test    r14, r14
0x180019d85  jnz     short loc_180019DD1
0x180019d87  mov     eax, ebx
0x180019d89  add     rsp, 80h
0x180019d90  pop     r15
0x180019d92  pop     r14
0x180019d94  pop     rdi
0x180019d95  pop     rsi
0x180019d96  pop     rbx
0x180019d97  retn
0x180019d99  xor     r9d, r9d; bool
0x180019d9c  xor     r8d, r8d; unsigned int
0x180019d9f  mov     rdx, [rsp+0A8h+lpMem]; unsigned __int16 *
0x180019da4  mov     rcx, rdi; this
0x180019da7  call    ?Open@CFveApiBase@@QEAAJPEBGK_N@Z; CFveApiBase::Open(ushort const *,ulong,bool)
0x180019dac  jmp     short loc_180019D64
0x180019dae  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180019db3  jmp     short loc_180019D6E
0x180019db5  mov     edx, [rsp+0A8h+arg_8]; unsigned __int64
0x180019dbc  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180019dc1  jmp     short loc_180019D78
0x180019dc3  call    cs:__imp_CertFreeCertificateContext
0x180019dca  nop     dword ptr [rax+rax+00h]
0x180019dcf  jmp     short loc_180019D82
0x180019dd1  xor     edx, edx; dwFlags
0x180019dd3  mov     rcx, r14; hCertStore
0x180019dd6  call    cs:__imp_CertCloseStore
0x180019ddd  nop     dword ptr [rax+rax+00h]
0x180019de2  jmp     short loc_180019D87
0x180120005  push    rbp
0x180120007  sub     rsp, 50h
0x18012000b  mov     rbp, rdx
0x18012000e  cmp     dword ptr [rbp+54h], 0
0x180120012  jz      short loc_18012002B
0x180120014  xor     r9d, r9d; bool
0x180120017  xor     r8d, r8d; unsigned int
0x18012001a  mov     rdx, [rbp+60h]; unsigned __int16 *
0x18012001e  mov     rcx, [rbp+0B0h]; this
0x180120025  call    ?Open@CFveApiBase@@QEAAJPEBGK_N@Z; CFveApiBase::Open(ushort const *,ulong,bool)
0x18012002a  nop
0x18012002b  mov     rcx, [rbp+60h]; lpMem
0x18012002f  test    rcx, rcx
0x180120032  jz      short loc_18012003A
0x180120034  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180120039  nop
0x18012003a  mov     rcx, [rbp+68h]; lpMem
0x18012003e  test    rcx, rcx
0x180120041  jz      short loc_18012004F
0x180120043  mov     edx, [rbp+0B8h]; unsigned __int64
0x180120049  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x18012004e  nop
0x18012004f  mov     rcx, [rbp+58h]; pCertContext
0x180120053  test    rcx, rcx
0x180120056  jz      short loc_180120065
0x180120058  call    cs:__imp_CertFreeCertificateContext
0x18012005f  nop     dword ptr [rax+rax+00h]
0x180120064  nop
0x180120065  mov     rcx, [rbp+70h]; hCertStore
0x180120069  test    rcx, rcx
0x18012006c  jz      short loc_180120084
0x18012006e  xor     edx, edx; dwFlags
0x180120070  call    cs:__imp_CertCloseStore
0x180120077  nop     dword ptr [rax+rax+00h]
0x18012007c  mov     qword ptr [rbp+70h], 0
0x180120084  add     rsp, 50h
0x180120088  pop     rbp
0x180120089  retn
```
