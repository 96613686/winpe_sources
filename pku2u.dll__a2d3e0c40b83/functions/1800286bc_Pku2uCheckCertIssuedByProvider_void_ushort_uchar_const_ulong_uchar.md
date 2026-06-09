# Pku2uCheckCertIssuedByProvider(void *,ushort,uchar * const,ulong *,uchar * *)

- ea: `0x1800286bc`
- end: `0x180028919`
- name: `?Pku2uCheckCertIssuedByProvider@@YAJPEAXGQEAEPEAKPEAPEAE@Z`
- size: `605`
- prototype: `__int64 __fastcall(void *, __int64, unsigned __int8 *const, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028920`

## callees

- `0x180014ba0`
- `0x1800178d0`
- `0x180018870`
- `0x1800210f0`
- `0x180023ce0`
- `0x1800286bc`
- `0x18002b408`
- `0x180044f8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028812`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288d8`
- `CRYPT32!CertOpenStore` at `0x180028775`
- `CRYPT32!CertOpenStore` at `0x180028775`
- `CRYPT32!CertFindCertificateInStore` at `0x180028804`
- `CRYPT32!CertFindCertificateInStore` at `0x180028804`
- `CRYPT32!CertFreeCertificateContext` at `0x1800288e6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800288e6`
- `CRYPT32!CertCloseStore` at `0x1800288f6`
- `CRYPT32!CertCloseStore` at `0x1800288f6`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstMapCertificateToProvider` at `0x18002885a`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstMapCertificateToProvider` at `0x18002885a`

## pseudocode

```c
__int64 __fastcall Pku2uCheckCertIssuedByProvider(
        void *a1,
        __int64 a2,
        unsigned __int8 *const a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  const CERT_CONTEXT *v5; // rdi
  signed int v8; // ebx
  HCERTSTORE v9; // r14
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int LastError; // eax
  __int64 v13; // r9
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  PCCERT_CONTEXT CertificateInStore; // rax
  signed int v17; // eax
  unsigned __int8 *v18; // rax
  unsigned int cbCertEncoded; // eax
  HANDLE v20; // rsi
  int v22; // [rsp+30h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-38h] BYREF
  __int128 pvFindPara; // [rsp+40h] [rbp-30h] BYREF
  __int128 v25; // [rsp+50h] [rbp-20h] BYREF

  v5 = 0;
  *a4 = 0;
  hObject = 0;
  *a5 = 0;
  v22 = 0;
  pvFindPara = 0;
  v25 = 0;
  v8 = Pku2uImpersonateToken2(a1, &hObject, &v22);
  if ( v8 < 0 )
  {
    v9 = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 101;
LABEL_5:
      WPP_SF_d(v10[2], v11, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, (unsigned int)v8);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  v9 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x1C000u, L"My");
  if ( !v9 )
  {
    LastError = GetLastError();
    v13 = (unsigned int)LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0xC0070000;
    else
      v8 = LastError;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_28;
    v15 = 102;
    goto LABEL_13;
  }
  LODWORD(pvFindPara) = 20;
  *((_QWORD *)&pvFindPara + 1) = a3;
  CertificateInStore = CertFindCertificateInStore(v9, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
  v5 = CertificateInStore;
  if ( !CertificateInStore )
  {
    v17 = GetLastError();
    v13 = (unsigned int)v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0xC0070000;
    else
      v8 = v17;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_28;
    v15 = 103;
LABEL_13:
    WPP_SF_dd(v14[2], v15, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v13, v8);
    goto LABEL_28;
  }
  v8 = IntPstMapCertificateToProvider(CertificateInStore, &v25, 0);
  if ( v8 >= 0 )
  {
    v18 = (unsigned __int8 *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v5->cbCertEncoded);
    *a5 = v18;
    if ( v18 )
    {
      cbCertEncoded = v5->cbCertEncoded;
      *a4 = cbCertEncoded;
      memcpy_0(*a5, v5->pbCertEncoded, cbCertEncoded);
      v8 = 0;
    }
    else
    {
      v8 = -1073741801;
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 104;
      goto LABEL_5;
    }
  }
LABEL_28:
  v20 = hObject;
  if ( v22 )
    Pku2uRevertImpersonation(hObject);
  if ( v20 )
    CloseHandle(v20);
  if ( v5 )
    CertFreeCertificateContext(v5);
  if ( v9 )
    CertCloseStore(v9, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800286bc  push    rbp
0x1800286be  push    rbx
0x1800286bf  push    rsi
0x1800286c0  push    rdi
0x1800286c1  push    r12
0x1800286c3  push    r14
0x1800286c5  push    r15
0x1800286c7  mov     rbp, rsp
0x1800286ca  sub     rsp, 70h
0x1800286ce  mov     rax, cs:__security_cookie
0x1800286d5  xor     rax, rsp
0x1800286d8  mov     [rbp+var_10], rax
0x1800286dc  mov     rsi, [rbp+arg_20]
0x1800286e0  lea     rdx, [rbp+hObject]; void **
0x1800286e4  xor     edi, edi
0x1800286e6  mov     r12, r8
0x1800286e9  xorps   xmm0, xmm0
0x1800286ec  mov     [r9], edi
0x1800286ef  xorps   xmm1, xmm1
0x1800286f2  mov     [rbp+hObject], rdi
0x1800286f6  lea     r8, [rbp+var_40]; int *
0x1800286fa  mov     [rsi], rdi
0x1800286fd  mov     r15, r9
0x180028700  mov     [rbp+var_40], edi
0x180028703  movups  [rbp+pvFindPara], xmm0
0x180028707  movups  [rbp+var_20], xmm1
0x18002870b  call    ?Pku2uImpersonateToken2@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken2(void *,void * *,int *)
0x180028710  mov     ebx, eax
0x180028712  test    eax, eax
0x180028714  jns     short loc_180028755
0x180028716  xor     r14d, r14d
0x180028719  mov     rcx, cs:WPP_GLOBAL_Control
0x180028720  lea     rax, WPP_GLOBAL_Control
0x180028727  cmp     rcx, rax
0x18002872a  jz      loc_1800288BE
0x180028730  test    byte ptr [rcx+1Ch], 1
0x180028734  jz      loc_1800288BE
0x18002873a  lea     edx, [rdi+65h]
0x18002873d  mov     rcx, [rcx+10h]
0x180028741  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x180028748  mov     r9d, ebx
0x18002874b  call    WPP_SF_d
0x180028750  jmp     loc_1800288BE
0x180028755  xor     r8d, r8d; hCryptProv
0x180028758  lea     rax, aMy; "My"
0x18002875f  mov     ebx, 10001h
0x180028764  mov     [rsp+70h+pvPara], rax; pvPara
0x180028769  mov     r9d, 1C000h; dwFlags
0x18002876f  mov     edx, ebx; dwEncodingType
0x180028771  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180028775  call    cs:__imp_CertOpenStore
0x18002877b  mov     r14, rax
0x18002877e  test    rax, rax
0x180028781  jnz     short loc_1800287DD
0x180028783  call    cs:__imp_GetLastError
0x180028789  mov     r9d, eax
0x18002878c  test    eax, eax
0x18002878e  jg      short loc_180028794
0x180028790  mov     ebx, eax
0x180028792  jmp     short loc_18002879E
0x180028794  movzx   ebx, r9w
0x180028798  or      ebx, 0C0070000h
0x18002879e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287a5  lea     rax, WPP_GLOBAL_Control
0x1800287ac  cmp     rcx, rax
0x1800287af  jz      loc_1800288BE
0x1800287b5  test    byte ptr [rcx+1Ch], 2
0x1800287b9  jz      loc_1800288BE
0x1800287bf  mov     edx, 66h ; 'f'
0x1800287c4  mov     rcx, [rcx+10h]
0x1800287c8  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x1800287cf  mov     dword ptr [rsp+70h+pvPara], ebx
0x1800287d3  call    WPP_SF_dd
0x1800287d8  jmp     loc_1800288BE
0x1800287dd  lea     rax, [rbp+pvFindPara]
0x1800287e1  mov     [rsp+70h+pPrevCertContext], rdi; pPrevCertContext
0x1800287e6  mov     r9d, 10000h; dwFindType
0x1800287ec  mov     [rsp+70h+pvPara], rax; pvFindPara
0x1800287f1  xor     r8d, r8d; dwFindFlags
0x1800287f4  mov     dword ptr [rbp+pvFindPara], 14h
0x1800287fb  mov     edx, ebx; dwCertEncodingType
0x1800287fd  mov     qword ptr [rbp+pvFindPara+8], r12
0x180028801  mov     rcx, r14; hCertStore
0x180028804  call    cs:__imp_CertFindCertificateInStore
0x18002880a  mov     rdi, rax
0x18002880d  test    rax, rax
0x180028810  jnz     short loc_180028850
0x180028812  call    cs:__imp_GetLastError
0x180028818  mov     r9d, eax
0x18002881b  test    eax, eax
0x18002881d  jg      short loc_180028823
0x18002881f  mov     ebx, eax
0x180028821  jmp     short loc_18002882D
0x180028823  movzx   ebx, r9w
0x180028827  or      ebx, 0C0070000h
0x18002882d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028834  lea     rax, WPP_GLOBAL_Control
0x18002883b  cmp     rcx, rax
0x18002883e  jz      short loc_1800288BE
0x180028840  test    byte ptr [rcx+1Ch], 2
0x180028844  jz      short loc_1800288BE
0x180028846  mov     edx, 67h ; 'g'
0x18002884b  jmp     loc_1800287C4
0x180028850  xor     r8d, r8d
0x180028853  lea     rdx, [rbp+var_20]
0x180028857  mov     rcx, rdi
0x18002885a  call    cs:__imp_IntPstMapCertificateToProvider
0x180028860  mov     ebx, eax
0x180028862  test    eax, eax
0x180028864  jns     short loc_180028889
0x180028866  mov     rcx, cs:WPP_GLOBAL_Control
0x18002886d  lea     rax, WPP_GLOBAL_Control
0x180028874  cmp     rcx, rax
0x180028877  jz      short loc_1800288BE
0x180028879  test    byte ptr [rcx+1Ch], 2
0x18002887d  jz      short loc_1800288BE
0x18002887f  mov     edx, 68h ; 'h'
0x180028884  jmp     loc_18002873D
0x180028889  mov     edx, [rdi+10h]; unsigned __int64
0x18002888c  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180028893  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180028898  mov     [rsi], rax
0x18002889b  test    rax, rax
0x18002889e  jnz     short loc_1800288A7
0x1800288a0  mov     ebx, 0C0000017h
0x1800288a5  jmp     short loc_1800288BE
0x1800288a7  mov     eax, [rdi+10h]
0x1800288aa  mov     [r15], eax
0x1800288ad  mov     r8d, eax; Size
0x1800288b0  mov     rdx, [rdi+8]; Src
0x1800288b4  mov     rcx, [rsi]; void *
0x1800288b7  call    memcpy_0
0x1800288bc  xor     ebx, ebx
0x1800288be  cmp     [rbp+var_40], 0
0x1800288c2  mov     rsi, [rbp+hObject]
0x1800288c6  jz      short loc_1800288D0
0x1800288c8  mov     rcx, rsi; Token
0x1800288cb  call    ?Pku2uRevertImpersonation@@YAXPEAX@Z; Pku2uRevertImpersonation(void *)
0x1800288d0  test    rsi, rsi
0x1800288d3  jz      short loc_1800288DE
0x1800288d5  mov     rcx, rsi; hObject
0x1800288d8  call    cs:__imp_CloseHandle
0x1800288de  test    rdi, rdi
0x1800288e1  jz      short loc_1800288EC
0x1800288e3  mov     rcx, rdi; pCertContext
0x1800288e6  call    cs:__imp_CertFreeCertificateContext
0x1800288ec  test    r14, r14
0x1800288ef  jz      short loc_1800288FC
0x1800288f1  xor     edx, edx; dwFlags
0x1800288f3  mov     rcx, r14; hCertStore
0x1800288f6  call    cs:__imp_CertCloseStore
0x1800288fc  mov     eax, ebx
0x1800288fe  mov     rcx, [rbp+var_10]
0x180028902  xor     rcx, rsp; StackCookie
0x180028905  call    __security_check_cookie
0x18002890a  add     rsp, 70h
0x18002890e  pop     r15
0x180028910  pop     r14
0x180028912  pop     r12
0x180028914  pop     rdi
0x180028915  pop     rsi
0x180028916  pop     rbx
0x180028917  pop     rbp
0x180028918  retn
```
