# DoEKUCheck

- ea: `0x1800a5a18`
- end: `0x1800a5cb1`
- name: `DoEKUCheck`
- size: `665`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f4a8`
- `0x18005067c`
- `0x1800a36ac`

## callees

- `0x18008b5f0`
- `0x18008bf98`
- `0x1800a5a18`
- `0x1800a5d68`
- `0x1800dc9e0`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5b55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5b55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5b8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5b8c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a5b1f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a5b1f`
- `CRYPT32!CertCreateCertificateContext` at `0x1800a5bfe`
- `CRYPT32!CertCreateCertificateContext` at `0x1800a5bfe`
- `CRYPT32!CertFreeCertificateContext` at `0x1800a5c24`
- `CRYPT32!CertFreeCertificateContext` at `0x1800a5c34`
- `CRYPT32!CertFreeCertificateContext` at `0x1800a5c24`
- `CRYPT32!CertFreeCertificateContext` at `0x1800a5c34`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800a5c7f`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800a5c7f`
- `fwpuclnt!IkeextSaGetById1` at `0x1800a5b77`
- `fwpuclnt!IkeextSaGetById1` at `0x1800a5b77`
- `fwpuclnt!WSAQuerySocketSecurity` at `0x1800a5b0f`
- `fwpuclnt!WSAQuerySocketSecurity` at `0x1800a5b0f`

## pseudocode

```c
__int64 __fastcall DoEKUCheck(__int64 a1, __int128 *a2, __int64 a3, _DWORD *a4)
{
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  unsigned int Error; // eax
  DWORD v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9
  UINT32 *v13; // r14
  UINT32 i; // esi
  IKEEXT_PRESHARED_KEY_AUTHENTICATION1 *presharedKey; // rdx
  UINT32 *p_flags; // rax
  const BYTE *v17; // rdx
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v19; // rdi
  int matched; // eax
  DWORD LastError; // eax
  IKEEXT_SA_DETAILS1 *sa; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[24]; // [rsp+50h] [rbp-B0h] BYREF
  UINT64 id; // [rsp+68h] [rbp-98h]
  GUID saLookupContext; // [rsp+7Ch] [rbp-84h] BYREF
  int v28; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v29[8]; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+11Ch] [rbp+1Ch]
  int v31; // [rsp+120h] [rbp+20h]

  memset_0(&v28, 0, 0x98u);
  memset_0(v25, 0, 0x40u);
  sa = 0;
  v24 = 0;
  *a4 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 23, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids, a1);
  v7 = *a2;
  v31 = 1;
  v28 = 2;
  v30 = 0;
  if ( *(_WORD *)a2 == 2 )
  {
    v29[0] = v7;
  }
  else
  {
    v8 = *(__int128 *)((char *)a2 + 12);
    v29[0] = v7;
    *(_OWORD *)((char *)v29 + 12) = v8;
  }
  v24 = 64;
  if ( (unsigned int)WSAQuerySocketSecurity(a1, &v28, 152, v25, &v24, 0, 0) )
  {
    Error = WSAGetLastError();
    v10 = Error;
    if ( Error )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_28;
      v11 = 24;
      v12 = Error;
LABEL_27:
      WPP_SF_d(1035, v11, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids, v12);
      goto LABEL_28;
    }
  }
  AcquireSRWLockShared(&stru_180111D48);
  v10 = IkeextSaGetById1(engineHandle, id, &saLookupContext, &sa);
  ReleaseSRWLockShared(&stru_180111D48);
  if ( v10 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_28;
    v11 = 25;
    v12 = v10;
    goto LABEL_27;
  }
  v13 = 0;
  for ( i = 0; i < sa->ikeCredentials.numCredentials; ++i )
  {
    presharedKey = sa->ikeCredentials.credentials[i].peerCredentials.presharedKey;
    p_flags = &presharedKey[1].flags;
    if ( !presharedKey )
      p_flags = v13;
    v13 = p_flags;
    if ( presharedKey )
    {
      v17 = (const BYTE *)*((_QWORD *)p_flags + 1);
      if ( v17 )
      {
        if ( *p_flags )
        {
          CertificateContext = CertCreateCertificateContext(1u, v17, *p_flags);
          v19 = CertificateContext;
          if ( !CertificateContext )
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
              break;
            v11 = 26;
            v12 = LastError;
            goto LABEL_27;
          }
          matched = MatchCertificateEKU(CertificateContext);
          *a4 = matched;
          if ( matched )
          {
            CertFreeCertificateContext(v19);
            break;
          }
          CertFreeCertificateContext(v19);
        }
      }
    }
  }
LABEL_28:
  if ( sa )
    FwpmFreeMemory0((void **)&sa);
  return v10;
}

```

## disassembly

```asm
0x1800a5a18  mov     [rsp-8+arg_10], rbx
0x1800a5a1d  push    rbp
0x1800a5a1e  push    rsi
0x1800a5a1f  push    rdi
0x1800a5a20  push    r14
0x1800a5a22  push    r15
0x1800a5a24  lea     rbp, [rsp-40h]
0x1800a5a29  sub     rsp, 140h
0x1800a5a30  mov     rax, cs:__security_cookie
0x1800a5a37  xor     rax, rsp
0x1800a5a3a  mov     [rbp+60h+var_30], rax
0x1800a5a3e  mov     rbx, rdx
0x1800a5a41  mov     rdi, rcx
0x1800a5a44  xor     edx, edx; Val
0x1800a5a46  lea     rcx, [rbp+60h+var_D0]; void *
0x1800a5a4a  mov     r8d, 98h; Size
0x1800a5a50  mov     r15, r9
0x1800a5a53  call    memset_0
0x1800a5a58  xor     edx, edx; Val
0x1800a5a5a  lea     rcx, [rsp+160h+var_110]; void *
0x1800a5a5f  lea     r8d, [rdx+40h]; Size
0x1800a5a63  call    memset_0
0x1800a5a68  mov     [rsp+160h+sa], 0
0x1800a5a71  mov     [rsp+160h+var_118], 0
0x1800a5a79  mov     dword ptr [r15], 0
0x1800a5a80  mov     r14b, 8
0x1800a5a83  lea     rsi, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids
0x1800a5a8a  test    byte ptr cs:xmmword_1801119E0+1, r14b
0x1800a5a91  jz      short loc_1800A5AA8
0x1800a5a93  mov     edx, 17h
0x1800a5a98  mov     ecx, 40Bh
0x1800a5a9d  mov     r9, rdi
0x1800a5aa0  mov     r8, rsi
0x1800a5aa3  call    WPP_SF_q
0x1800a5aa8  movups  xmm0, xmmword ptr [rbx]
0x1800a5aab  mov     eax, 2
0x1800a5ab0  mov     [rbp+60h+var_40], 1
0x1800a5ab7  mov     [rbp+60h+var_D0], eax
0x1800a5aba  mov     [rbp+60h+var_44], 0
0x1800a5ac1  cmp     [rbx], ax
0x1800a5ac4  jnz     short loc_1800A5ACD
0x1800a5ac6  movdqu  [rbp+60h+var_C8], xmm0
0x1800a5acb  jmp     short loc_1800A5AD9
0x1800a5acd  movups  xmm1, xmmword ptr [rbx+0Ch]
0x1800a5ad1  movups  [rbp+60h+var_C8], xmm0
0x1800a5ad5  movups  [rbp+60h+var_C8+0Ch], xmm1
0x1800a5ad9  mov     [rsp+160h+var_130], 0
0x1800a5ae2  lea     rax, [rsp+160h+var_118]
0x1800a5ae7  mov     [rsp+160h+var_138], 0
0x1800a5af0  lea     r9, [rsp+160h+var_110]
0x1800a5af5  mov     r8d, 98h
0x1800a5afb  mov     [rsp+160h+var_140], rax
0x1800a5b00  lea     rdx, [rbp+60h+var_D0]
0x1800a5b04  mov     [rsp+160h+var_118], 40h ; '@'
0x1800a5b0c  mov     rcx, rdi
0x1800a5b0f  call    cs:__imp_WSAQuerySocketSecurity
0x1800a5b16  nop     dword ptr [rax+rax+00h]
0x1800a5b1b  test    eax, eax
0x1800a5b1d  jz      short loc_1800A5B4E
0x1800a5b1f  call    cs:__imp_WSAGetLastError
0x1800a5b26  nop     dword ptr [rax+rax+00h]
0x1800a5b2b  mov     ebx, eax
0x1800a5b2d  test    eax, eax
0x1800a5b2f  jz      short loc_1800A5B4E
0x1800a5b31  test    byte ptr cs:xmmword_1801119E0+1, r14b
0x1800a5b38  jz      loc_1800A5C72
0x1800a5b3e  mov     edx, 18h
0x1800a5b43  mov     r9d, eax
0x1800a5b46  mov     r8, rsi
0x1800a5b49  jmp     loc_1800A5C68
0x1800a5b4e  lea     rcx, stru_180111D48; SRWLock
0x1800a5b55  call    cs:__imp_AcquireSRWLockShared
0x1800a5b5c  nop     dword ptr [rax+rax+00h]
0x1800a5b61  mov     rdx, [rsp+160h+id]; id
0x1800a5b66  lea     r9, [rsp+160h+sa]; sa
0x1800a5b6b  mov     rcx, cs:engineHandle; engineHandle
0x1800a5b72  lea     r8, [rsp+160h+saLookupContext]; saLookupContext
0x1800a5b77  call    cs:__imp_IkeextSaGetById1
0x1800a5b7e  nop     dword ptr [rax+rax+00h]
0x1800a5b83  lea     rcx, stru_180111D48; SRWLock
0x1800a5b8a  mov     ebx, eax
0x1800a5b8c  call    cs:__imp_ReleaseSRWLockShared
0x1800a5b93  nop     dword ptr [rax+rax+00h]
0x1800a5b98  test    ebx, ebx
0x1800a5b9a  jz      short loc_1800A5BB3
0x1800a5b9c  test    byte ptr cs:xmmword_1801119E0+1, r14b
0x1800a5ba3  jz      loc_1800A5C72
0x1800a5ba9  mov     edx, 19h
0x1800a5bae  mov     r9d, ebx
0x1800a5bb1  jmp     short loc_1800A5B46
0x1800a5bb3  xor     r14d, r14d
0x1800a5bb6  xor     esi, esi
0x1800a5bb8  mov     rax, [rsp+160h+sa]
0x1800a5bbd  cmp     esi, [rax+78h]
0x1800a5bc0  jnb     loc_1800A5C72
0x1800a5bc6  mov     rax, [rax+80h]
0x1800a5bcd  mov     ecx, esi
0x1800a5bcf  shl     rcx, 5
0x1800a5bd3  mov     rdx, [rcx+rax+18h]
0x1800a5bd8  test    rdx, rdx
0x1800a5bdb  lea     rax, [rdx+28h]
0x1800a5bdf  cmovz   rax, r14
0x1800a5be3  mov     r14, rax
0x1800a5be6  jz      short loc_1800A5C30
0x1800a5be8  mov     rdx, [rax+8]; pbCertEncoded
0x1800a5bec  test    rdx, rdx
0x1800a5bef  jz      short loc_1800A5C30
0x1800a5bf1  mov     r8d, [rax]; cbCertEncoded
0x1800a5bf4  test    r8d, r8d
0x1800a5bf7  jz      short loc_1800A5C30
0x1800a5bf9  mov     ecx, 1; dwCertEncodingType
0x1800a5bfe  call    cs:__imp_CertCreateCertificateContext
0x1800a5c05  nop     dword ptr [rax+rax+00h]
0x1800a5c0a  mov     rdi, rax
0x1800a5c0d  test    rax, rax
0x1800a5c10  jz      short loc_1800A5C42
0x1800a5c12  mov     rcx, rax
0x1800a5c15  call    MatchCertificateEKU
0x1800a5c1a  mov     [r15], eax
0x1800a5c1d  mov     rcx, rdi; pCertContext
0x1800a5c20  test    eax, eax
0x1800a5c22  jnz     short loc_1800A5C34
0x1800a5c24  call    cs:__imp_CertFreeCertificateContext
0x1800a5c2b  nop     dword ptr [rax+rax+00h]
0x1800a5c30  inc     esi
0x1800a5c32  jmp     short loc_1800A5BB8
0x1800a5c34  call    cs:__imp_CertFreeCertificateContext
0x1800a5c3b  nop     dword ptr [rax+rax+00h]
0x1800a5c40  jmp     short loc_1800A5C72
0x1800a5c42  call    cs:__imp_GetLastError
0x1800a5c49  nop     dword ptr [rax+rax+00h]
0x1800a5c4e  mov     ebx, eax
0x1800a5c50  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a5c57  jz      short loc_1800A5C72
0x1800a5c59  mov     edx, 1Ah
0x1800a5c5e  lea     r8, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids
0x1800a5c65  mov     r9d, eax
0x1800a5c68  mov     ecx, 40Bh
0x1800a5c6d  call    WPP_SF_d
0x1800a5c72  cmp     [rsp+160h+sa], 0
0x1800a5c78  jz      short loc_1800A5C8B
0x1800a5c7a  lea     rcx, [rsp+160h+sa]; p
0x1800a5c7f  call    cs:__imp_FwpmFreeMemory0
0x1800a5c86  nop     dword ptr [rax+rax+00h]
0x1800a5c8b  mov     eax, ebx
0x1800a5c8d  mov     rcx, [rbp+60h+var_30]
0x1800a5c91  xor     rcx, rsp; StackCookie
0x1800a5c94  call    __security_check_cookie
0x1800a5c99  mov     rbx, [rsp+160h+arg_10]
0x1800a5ca1  add     rsp, 140h
0x1800a5ca8  pop     r15
0x1800a5caa  pop     r14
0x1800a5cac  pop     rdi
0x1800a5cad  pop     rsi
0x1800a5cae  pop     rbp
0x1800a5caf  retn
```
