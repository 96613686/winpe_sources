# LsaDbpDecryptAuthDataWithSessionKeyAes(_LSAP_CR_CIPHER_KEY *,uchar,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *,_TRUSTED_DOMAIN_AUTH_INFORMATION *)

- ea: `0x180016e14`
- end: `0x18001700f`
- name: `?LsaDbpDecryptAuthDataWithSessionKeyAes@@YAJPEAU_LSAP_CR_CIPHER_KEY@@EPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES@@PEAU_TRUSTED_DOMAIN_AUTH_INFORMATION@@@Z`
- size: `507`
- prototype: `int(struct _LSAP_CR_CIPHER_KEY *, unsigned __int8, struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *, struct _TRUSTED_DOMAIN_AUTH_INFORMATION *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d210`
- `0x180016d50`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x180016e14`
- `0x180017018`
- `0x180018fa4`
- `0x18001a110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016fc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016fc4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016fd1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016fd1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180016ea1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180016ea1`

## pseudocode

```c
__int64 __fastcall LsaDbpDecryptAuthDataWithSessionKeyAes(
        unsigned __int8 **a1,
        char a2,
        struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *a3,
        struct _TRUSTED_DOMAIN_AUTH_INFORMATION *a4)
{
  char *v4; // rdi
  NTSTATUS v9; // ebx
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  char *v13; // rbx
  __int64 v14; // rbp
  unsigned __int8 *v15; // rbx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v18; // [rsp+78h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  phAlgorithm = 0;
  hMem = 0;
  v18 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
  *(_OWORD *)&a4->IncomingAuthInfos = 0;
  *(_OWORD *)&a4->IncomingPreviousAuthenticationInformation = 0;
  *(_OWORD *)&a4->OutgoingAuthenticationInformation = 0;
  if ( *((_DWORD *)a3 + 20) < 0x208u )
    goto LABEL_17;
  if ( a2 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
    v4 = (char *)*((_QWORD *)a3 + 11);
    v11 = *((_DWORD *)a3 + 20);
  }
  else
  {
    if ( !a1 )
    {
LABEL_17:
      v9 = -1073741811;
LABEL_18:
      LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)a4);
      LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)((unsigned __int64)&a4->OutgoingAuthInfos
                                                                                    & -(__int64)(a4 != 0)));
      goto LABEL_19;
    }
    v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
    if ( v9 < 0 )
      goto LABEL_18;
    v10 = LsaDbpDecryptAuthDataWithSessionKeyAesWorker(
            a1[1],
            *(_DWORD *)a1,
            phAlgorithm,
            a3,
            (unsigned __int8 **)&hMem,
            &v18);
    v4 = (char *)hMem;
    v9 = v10;
    if ( v10 < 0 )
      goto LABEL_18;
    v11 = v18;
  }
  if ( v11 < 0x208 )
    goto LABEL_17;
  v12 = *(unsigned int *)&v4[v11 - 4];
  if ( (unsigned int)v12 > v11 - 520 )
    goto LABEL_17;
  v13 = &v4[v11 - 8];
  v14 = *(unsigned int *)v13;
  if ( (unsigned int)v14 > v11 - 520 - (unsigned int)v12 )
    goto LABEL_17;
  v15 = (unsigned __int8 *)&v13[-v12];
  if ( (int)LsaDbpDsUnmarshalAuthInfoHalf(0, 0, 1u, v15, v12, (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)a4) < 0 )
    goto LABEL_17;
  v9 = LsaDbpDsUnmarshalAuthInfoHalf(
         0,
         0,
         1u,
         &v15[-v14],
         v14,
         (struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)((unsigned __int64)&a4->OutgoingAuthInfos
                                                     & ((unsigned __int128)-(__int128)(unsigned __int64)a4 >> 64)));
  if ( v9 < 0 )
    goto LABEL_17;
LABEL_19:
  if ( !a2 && v4 )
    LocalFree(v4);
  BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
      (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016e14  mov     rax, rsp
0x180016e17  mov     [rax+8], rbx
0x180016e1b  push    rbp
0x180016e1c  push    rsi
0x180016e1d  push    rdi
0x180016e1e  push    r14
0x180016e20  push    r15
0x180016e22  sub     rsp, 40h
0x180016e26  xor     edi, edi
0x180016e28  mov     qword ptr [rax-38h], 0
0x180016e30  mov     [rax+18h], rdi
0x180016e34  mov     rsi, r9
0x180016e37  mov     [rax+10h], edi
0x180016e3a  mov     rbp, r8
0x180016e3d  mov     r15b, dl
0x180016e40  mov     r14, rcx
0x180016e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e4a  test    byte ptr [rcx+1Ch], 2
0x180016e4e  jz      short loc_180016E63
0x180016e50  mov     rcx, [rcx+10h]
0x180016e54  lea     edx, [rdi+42h]
0x180016e57  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180016e5e  call    WPP_SF_
0x180016e63  xorps   xmm0, xmm0
0x180016e66  movups  xmmword ptr [rsi], xmm0
0x180016e69  movups  xmmword ptr [rsi+10h], xmm0
0x180016e6d  movups  xmmword ptr [rsi+20h], xmm0
0x180016e71  cmp     dword ptr [rbp+50h], 208h
0x180016e78  jb      loc_180016F98
0x180016e7e  test    r15b, r15b
0x180016e81  jnz     short loc_180016EF4
0x180016e83  test    r14, r14
0x180016e86  jz      loc_180016F98
0x180016e8c  mov     r9d, 8; dwFlags
0x180016e92  lea     rdx, pszAlgId; "SHA512"
0x180016e99  xor     r8d, r8d; pszImplementation
0x180016e9c  lea     rcx, [rsp+68h+phAlgorithm]; phAlgorithm
0x180016ea1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180016ea7  mov     ebx, eax
0x180016ea9  test    eax, eax
0x180016eab  js      loc_180016F9D
0x180016eb1  mov     r8, [rsp+68h+phAlgorithm]; void *
0x180016eb6  lea     rax, [rsp+68h+arg_8]
0x180016ebb  mov     edx, [r14]; unsigned int
0x180016ebe  mov     r9, rbp; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *
0x180016ec1  mov     rcx, [r14+8]; unsigned __int8 *
0x180016ec5  mov     [rsp+68h+var_40], rax; unsigned int *
0x180016eca  lea     rax, [rsp+68h+hMem]
0x180016ed2  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x180016ed7  call    ?LsaDbpDecryptAuthDataWithSessionKeyAesWorker@@YAJPEAEKPEAXPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES@@PEAPEAEPEAK@Z; LsaDbpDecryptAuthDataWithSessionKeyAesWorker(uchar *,ulong,void *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *,uchar * *,ulong *)
0x180016edc  mov     rdi, [rsp+68h+hMem]
0x180016ee4  mov     ebx, eax
0x180016ee6  test    eax, eax
0x180016ee8  js      loc_180016F9D
0x180016eee  mov     eax, [rsp+68h+arg_8]
0x180016ef2  jmp     short loc_180016F20
0x180016ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180016efb  test    dword ptr [rcx+1Ch], 100h
0x180016f02  jz      short loc_180016F19
0x180016f04  mov     rcx, [rcx+10h]
0x180016f08  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180016f0f  mov     edx, 43h ; 'C'
0x180016f14  call    WPP_SF_
0x180016f19  mov     rdi, [rbp+58h]
0x180016f1d  mov     eax, [rbp+50h]
0x180016f20  cmp     eax, 208h
0x180016f25  jb      short loc_180016F98
0x180016f27  mov     r8d, eax
0x180016f2a  lea     ecx, [rax-208h]
0x180016f30  mov     edx, [r8+rdi-4]
0x180016f35  cmp     edx, ecx
0x180016f37  ja      short loc_180016F98
0x180016f39  lea     rbx, [rdi-8]
0x180016f3d  sub     ecx, edx
0x180016f3f  add     rbx, r8
0x180016f42  mov     ebp, [rbx]
0x180016f44  cmp     ebp, ecx
0x180016f46  ja      short loc_180016F98
0x180016f48  sub     rbx, rdx
0x180016f4b  mov     [rsp+68h+var_40], rsi; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x180016f50  mov     dword ptr [rsp+68h+var_48], edx; unsigned int
0x180016f54  mov     r9, rbx; unsigned __int8 *
0x180016f57  xor     edx, edx; unsigned __int8
0x180016f59  mov     r8b, 1; unsigned __int8
0x180016f5c  xor     ecx, ecx; void *
0x180016f5e  call    ?LsaDbpDsUnmarshalAuthInfoHalf@@YAJPEAXEEPEAEKPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsUnmarshalAuthInfoHalf(void *,uchar,uchar,uchar *,ulong,_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x180016f63  test    eax, eax
0x180016f65  js      short loc_180016F98
0x180016f67  lea     rcx, [rsi+18h]
0x180016f6b  mov     rax, rsi
0x180016f6e  neg     rax
0x180016f71  mov     r8b, 1; unsigned __int8
0x180016f74  sbb     rdx, rdx
0x180016f77  sub     rbx, rbp
0x180016f7a  and     rdx, rcx
0x180016f7d  mov     r9, rbx; unsigned __int8 *
0x180016f80  mov     [rsp+68h+var_40], rdx; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x180016f85  xor     ecx, ecx; void *
0x180016f87  xor     edx, edx; unsigned __int8
0x180016f89  mov     dword ptr [rsp+68h+var_48], ebp; unsigned int
0x180016f8d  call    ?LsaDbpDsUnmarshalAuthInfoHalf@@YAJPEAXEEPEAEKPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsUnmarshalAuthInfoHalf(void *,uchar,uchar,uchar *,ulong,_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x180016f92  mov     ebx, eax
0x180016f94  test    eax, eax
0x180016f96  jns     short loc_180016FB7
0x180016f98  mov     ebx, 0C000000Dh
0x180016f9d  mov     rcx, rsi; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x180016fa0  call    ?LsaDbpDsFreeUnmarshalAuthInfoHalf@@YAXPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsFreeUnmarshalAuthInfoHalf(_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x180016fa5  lea     rax, [rsi+18h]
0x180016fa9  neg     rsi
0x180016fac  sbb     rcx, rcx
0x180016faf  and     rcx, rax; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x180016fb2  call    ?LsaDbpDsFreeUnmarshalAuthInfoHalf@@YAXPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsFreeUnmarshalAuthInfoHalf(_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x180016fb7  test    r15b, r15b
0x180016fba  jnz     short loc_180016FCA
0x180016fbc  test    rdi, rdi
0x180016fbf  jz      short loc_180016FCA
0x180016fc1  mov     rcx, rdi; hMem
0x180016fc4  call    cs:__imp_LocalFree
0x180016fca  mov     rcx, [rsp+68h+phAlgorithm]; hAlgorithm
0x180016fcf  xor     edx, edx; dwFlags
0x180016fd1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180016fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fde  test    byte ptr [rcx+1Ch], 2
0x180016fe2  jz      short loc_180016FFC
0x180016fe4  mov     rcx, [rcx+10h]
0x180016fe8  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x180016fef  mov     edx, 44h ; 'D'
0x180016ff4  mov     r9d, ebx
0x180016ff7  call    WPP_SF_d
0x180016ffc  mov     eax, ebx
0x180016ffe  mov     rbx, [rsp+68h+arg_0]
0x180017003  add     rsp, 40h
0x180017007  pop     r15
0x180017009  pop     r14
0x18001700b  pop     rdi
0x18001700c  pop     rsi
0x18001700d  pop     rbp
0x18001700e  retn
```
