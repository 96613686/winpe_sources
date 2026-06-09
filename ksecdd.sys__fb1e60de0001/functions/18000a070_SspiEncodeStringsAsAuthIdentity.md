# SspiEncodeStringsAsAuthIdentity

- ea: `0x18000a070`
- end: `0x18000a6bc`
- name: `SspiEncodeStringsAsAuthIdentity`
- size: `1612`
- prototype: `SECURITY_STATUS __stdcall(PCWSTR pszUserName, PCWSTR pszDomainName, PCWSTR pszPackedCredentialsString, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004050`
- `0x180006830`
- `0x180007fc4`
- `0x1800081c4`
- `0x1800085b8`
- `0x180008a04`
- `0x18000a070`
- `0x180010a00`

## import_xrefs

- `ntoskrnl!wcschr` at `0x18000a109`
- `ntoskrnl!wcschr` at `0x18000a188`
- `ntoskrnl!wcschr` at `0x18000a4ef`
- `ntoskrnl!wcschr` at `0x18000a57f`
- `ntoskrnl!wcschr` at `0x18000a109`
- `ntoskrnl!wcschr` at `0x18000a188`
- `ntoskrnl!wcschr` at `0x18000a4ef`
- `ntoskrnl!wcschr` at `0x18000a57f`
- `ntoskrnl!ExAllocatePool2` at `0x18000a14d`
- `ntoskrnl!ExAllocatePool2` at `0x18000a2a6`
- `ntoskrnl!ExAllocatePool2` at `0x18000a3e6`
- `ntoskrnl!ExAllocatePool2` at `0x18000a43a`
- `ntoskrnl!ExAllocatePool2` at `0x18000a495`
- `ntoskrnl!ExAllocatePool2` at `0x18000a546`
- `ntoskrnl!ExAllocatePool2` at `0x18000a14d`
- `ntoskrnl!ExAllocatePool2` at `0x18000a2a6`
- `ntoskrnl!ExAllocatePool2` at `0x18000a3e6`
- `ntoskrnl!ExAllocatePool2` at `0x18000a43a`
- `ntoskrnl!ExAllocatePool2` at `0x18000a495`
- `ntoskrnl!ExAllocatePool2` at `0x18000a546`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiEncodeStringsAsAuthIdentity(
        PCWSTR pszUserName,
        PCWSTR pszDomainName,
        PCWSTR pszPackedCredentialsString,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppAuthIdentity)
{
  const unsigned __int16 *v4; // rsi
  _WORD *v5; // rdi
  PCWSTR v6; // rbx
  const wchar_t **v7; // r12
  unsigned int *v8; // r13
  unsigned int v9; // ebx
  wchar_t *v10; // r15
  __int64 v11; // rdi
  void *Pool2; // rax
  const wchar_t *v13; // r15
  wchar_t *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rsi
  PVOID v17; // r14
  unsigned int i; // edi
  unsigned int v19; // r14d
  unsigned int v20; // eax
  _OWORD *v21; // rax
  void *v22; // rcx
  void *v23; // rdx
  __int64 v24; // r8
  int IsEncodedNullUserName; // eax
  unsigned int v26; // edx
  __int64 v27; // r14
  __int64 v28; // rax
  unsigned int v29; // ecx
  __int64 v30; // rdi
  unsigned int v31; // edx
  __int64 v32; // rax
  unsigned int v33; // eax
  int v34; // r8d
  void *v35; // rax
  PVOID v36; // rax
  unsigned int v37; // eax
  __int64 v38; // r8
  unsigned int v39; // edx
  void *v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rbx
  wchar_t *v43; // rax
  wchar_t *v44; // rax
  int v45; // eax
  PVOID v46; // rdx
  _BYTE *v47; // rcx
  __int64 j; // rax
  unsigned int v50; // [rsp+30h] [rbp-40h] BYREF
  PVOID v51; // [rsp+38h] [rbp-38h]
  wchar_t *v52; // [rsp+40h] [rbp-30h]
  PVOID v53; // [rsp+48h] [rbp-28h] BYREF
  void *v54; // [rsp+50h] [rbp-20h] BYREF
  PVOID v55; // [rsp+58h] [rbp-18h]
  PVOID DataBuffer; // [rsp+60h] [rbp-10h]
  PVOID v57; // [rsp+68h] [rbp-8h]
  int v58; // [rsp+B0h] [rbp+40h] BYREF
  void *Src; // [rsp+C0h] [rbp+50h]
  struct _SEC_WINNT_AUTH_IDENTITY_EXW **v60; // [rsp+C8h] [rbp+58h]

  v60 = (struct _SEC_WINNT_AUTH_IDENTITY_EXW **)ppAuthIdentity;
  Src = (void *)pszPackedCredentialsString;
  v4 = pszDomainName;
  v5 = pszPackedCredentialsString;
  v6 = pszUserName;
  v58 = 0;
  v7 = 0;
  v54 = 0;
  v8 = 0;
  v53 = 0;
  v50 = 0;
  if ( __PAIR128__((unsigned __int64)pszUserName, (unsigned __int64)pszDomainName) == 0 && !pszPackedCredentialsString )
    goto LABEL_3;
  DataBuffer = 0;
  v51 = 0;
  v55 = 0;
  v52 = 0;
  v57 = 0;
  if ( !pszUserName )
    goto LABEL_106;
  v10 = 0;
  if ( *pszUserName && (!pszDomainName || !*pszDomainName) )
  {
    v10 = wcschr(pszUserName, 0x5Cu);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v6[v11] );
      if ( (unsigned int)v11 > 0x7FFD )
      {
LABEL_3:
        v9 = -1073741811;
        return SspNtStatusToSecStatus(v9);
      }
      Pool2 = (void *)ExAllocatePool2(256, (unsigned int)(2 * v11 + 2) + 2LL, 1230267731);
      DataBuffer = Pool2;
      v13 = (const wchar_t *)Pool2;
      if ( !Pool2 )
      {
        v9 = -1073741801;
        return SspNtStatusToSecStatus(v9);
      }
      memmove(Pool2, v6, 2LL * (unsigned int)v11);
      v14 = wcschr(v13, 0x5Cu);
      v10 = v14;
      if ( v14 )
      {
        v4 = (const unsigned __int16 *)DataBuffer;
        v6 = v14 + 1;
        *v14 = 0;
        if ( v14 == (wchar_t *)-2LL )
          goto LABEL_106;
        v10 = v14 + 1;
      }
      v5 = Src;
    }
  }
  if ( !*v6
    || v4 && *v4
    || !(unsigned int)SspiHelperIsEncodedNullUserName(v6) && !(unsigned int)LocalCredIsMarshaledCredentialW(v6) )
  {
    goto LABEL_106;
  }
  if ( v5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v5[v15] );
    if ( (unsigned int)v15 > 0x7FFD )
    {
      v9 = -1073741811;
      v16 = 0;
      v17 = 0;
LABEL_108:
      v41 = -1;
      goto LABEL_109;
    }
  }
  else
  {
    LODWORD(v15) = 0;
  }
  for ( i = 0; i < 8; ++i )
  {
    if ( i >= (unsigned int)v15 )
      break;
    if ( aD[i] != *((_WORD *)Src + i) )
      break;
  }
  v19 = v15 + 8;
  if ( i == 8 )
    v19 = v15;
  if ( !(unsigned int)SspiHelperIsEncodedNullUserName(v6) )
  {
    v20 = LocalCredUnmarshalCredentialW(v6, (enum _CRED_MARSHAL_TYPE *)&v58, &v54);
    v7 = (const wchar_t **)v54;
    if ( v20 )
    {
      v9 = -1073741670;
LABEL_38:
      v16 = 0;
LABEL_39:
      v17 = v16;
      goto LABEL_108;
    }
    if ( v58 != 4 )
      goto LABEL_106;
  }
  v58 = 3;
  v21 = (_OWORD *)ExAllocatePool2(256, 2 * v19 + 2 + 2LL, 1230267731);
  v57 = v21;
  v22 = v21;
  if ( !v21 )
  {
    v9 = -1073741801;
    goto LABEL_38;
  }
  v23 = Src;
  if ( i == 8 )
  {
    v24 = v19;
  }
  else
  {
    v24 = v19 - 8;
    v22 = v21 + 1;
    *v21 = *(_OWORD *)aD;
  }
  memmove(v22, v23, 2 * v24);
  if ( LocalCredUnmarshalCredentialW((const unsigned __int16 *)v57, (enum _CRED_MARSHAL_TYPE *)&v58, &v53) || v58 != 3 )
  {
    IsEncodedNullUserName = SspiHelperIsEncodedNullUserName(v6);
    v8 = (unsigned int *)v53;
    if ( !IsEncodedNullUserName )
      goto LABEL_48;
LABEL_106:
    v17 = v51;
    v9 = SspiHelperConstructAuthdataExWMarshalledW(
           v6,
           v4,
           (const unsigned __int16 *)Src,
           (const unsigned __int16 *)v51,
           v60,
           &v50);
    goto LABEL_107;
  }
  v8 = (unsigned int *)v53;
  v26 = *(_DWORD *)v53;
  if ( *(_DWORD *)v53 < 0x18u )
    goto LABEL_48;
  v27 = *((_QWORD *)v53 + 1);
  if ( *(_WORD *)v27 < 0x18u )
    goto LABEL_48;
  v28 = *(unsigned int *)(v27 + 8);
  if ( (_DWORD)v28 )
  {
    if ( (unsigned int)v28 > v26 )
      goto LABEL_48;
    v29 = *(unsigned __int16 *)(v27 + 12);
    if ( v29 + (unsigned int)v28 >= (unsigned int)v28 )
    {
      if ( v29 + (unsigned int)v28 > v26 )
        goto LABEL_48;
      if ( !(_WORD)v29 )
      {
        v36 = (PVOID)ExAllocatePool2(256, 4, 1230267731);
        v55 = v36;
        if ( !v36 )
          goto LABEL_68;
LABEL_72:
        Src = v36;
        goto LABEL_74;
      }
      if ( v29 < 0x1C )
        goto LABEL_48;
      v30 = v27 + v28;
      if ( *(_WORD *)(v27 + v28) < 0x1Cu )
        goto LABEL_48;
      v31 = *(unsigned __int16 *)(v30 + 2);
      if ( (unsigned __int16)v31 > (unsigned __int16)v29 )
        goto LABEL_48;
      v32 = *(_QWORD *)(v30 + 4) - SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
      if ( !v32 )
        v32 = *(_QWORD *)(v30 + 12) - *((_QWORD *)&SEC_WINNT_AUTH_DATA_TYPE_PASSWORD + 1);
      if ( v32 )
        goto LABEL_106;
      v33 = *(_DWORD *)(v30 + 20);
      if ( v33 > v31 )
        goto LABEL_48;
      v34 = *(unsigned __int16 *)(v30 + 24);
      if ( v34 + v33 >= v33 )
      {
        if ( v34 + v33 > v31 )
          goto LABEL_48;
        v35 = (void *)ExAllocatePool2(256, (unsigned int)(v34 + 4) + 2LL, 1230267731);
        v55 = v35;
        if ( !v35 )
        {
LABEL_68:
          v9 = -1073741801;
          goto LABEL_49;
        }
        memmove(v35, (const void *)(v30 + *(unsigned int *)(v30 + 20)), *(unsigned __int16 *)(v30 + 24));
        v36 = v55;
        goto LABEL_72;
      }
    }
LABEL_70:
    v9 = -1073741675;
    goto LABEL_49;
  }
  Src = 0;
LABEL_74:
  v37 = *(_DWORD *)(v27 + 16);
  if ( !v37 )
  {
    v51 = 0;
    goto LABEL_82;
  }
  if ( v37 > *v8 )
  {
LABEL_48:
    v9 = -1073741811;
LABEL_49:
    v16 = v52;
    goto LABEL_39;
  }
  v38 = *(unsigned __int16 *)(v27 + 20);
  v39 = v37 + 2 * v38;
  if ( v39 < v37 )
    goto LABEL_70;
  if ( v39 > *v8 )
    goto LABEL_48;
  v40 = (void *)ExAllocatePool2(256, 2 * v38 + 4, 1230267731);
  v51 = v40;
  if ( !v40 )
  {
    v9 = -1073741801;
    v17 = 0;
LABEL_107:
    v16 = v52;
    goto LABEL_108;
  }
  memmove(v40, (const void *)(v27 + *(unsigned int *)(v27 + 16)), 2LL * *(unsigned __int16 *)(v27 + 20));
LABEL_82:
  if ( !v7 || !*v7 || !wcschr(*v7, 0x5Cu) )
  {
LABEL_94:
    v45 = *(_DWORD *)(v27 + 4);
    v4 = (const unsigned __int16 *)&dword_180015B7C;
    if ( (v45 & 0x20000) != 0 )
    {
      v6 = 0;
    }
    else if ( v10 )
    {
      v6 = v10;
    }
    else if ( v7 )
    {
      v6 = *v7;
    }
    else
    {
      v6 = (PCWSTR)&dword_180015B7C;
    }
    if ( (v45 & 0x40000) != 0 )
    {
      v4 = 0;
    }
    else if ( v52 )
    {
      v4 = v52;
    }
    goto LABEL_106;
  }
  v41 = -1;
  v42 = -1;
  v16 = 0;
  do
    ++v42;
  while ( (*v7)[v42] );
  if ( (unsigned int)v42 <= 0x7FFD )
  {
    v43 = (wchar_t *)ExAllocatePool2(256, (unsigned int)(2 * v42 + 2) + 2LL, 1230267731);
    v52 = v43;
    v16 = v43;
    if ( !v43 )
    {
      v9 = -1073741801;
      goto LABEL_89;
    }
    memmove(v43, *v7, 2LL * (unsigned int)v42);
    v44 = wcschr(v16, 0x5Cu);
    v10 = v44;
    if ( v44 )
    {
      *v44 = 0;
      v10 = v44 + 1;
    }
    goto LABEL_94;
  }
  v9 = -1073741811;
LABEL_89:
  v17 = v51;
LABEL_109:
  if ( DataBuffer )
    SspiLocalFree(DataBuffer);
  if ( v7 )
    SspiLocalFree(v7);
  if ( v8 )
    SspiLocalFree(v8);
  v46 = v55;
  if ( v55 )
  {
    do
      ++v41;
    while ( *((_WORD *)v55 + v41) );
    v47 = v55;
    for ( j = 2LL * (unsigned int)v41; j; --j )
      *v47++ = 0;
    SspiLocalFree(v46);
  }
  if ( v17 )
    SspiLocalFree(v17);
  if ( v16 )
    SspiLocalFree(v16);
  if ( v57 )
    SspiLocalFree(v57);
  return SspNtStatusToSecStatus(v9);
}

```

## disassembly

```asm
0x18000a070  mov     [rsp-38h+arg_8], rbx
0x18000a075  mov     [rsp-38h+arg_18], r9
0x18000a07a  mov     [rsp-38h+Src], r8
0x18000a07f  push    rbp
0x18000a080  push    rsi
0x18000a081  push    rdi
0x18000a082  push    r12
0x18000a084  push    r13
0x18000a086  push    r14
0x18000a088  push    r15
0x18000a08a  mov     rbp, rsp
0x18000a08d  sub     rsp, 70h
0x18000a091  mov     rsi, rdx
0x18000a094  mov     rdi, r8
0x18000a097  xor     edx, edx
0x18000a099  mov     rbx, rcx
0x18000a09c  mov     [rbp+arg_0], edx
0x18000a09f  mov     r12d, edx
0x18000a0a2  mov     [rbp+var_20], rdx
0x18000a0a6  mov     r13d, edx
0x18000a0a9  mov     [rbp+var_28], rdx
0x18000a0ad  mov     [rbp+var_40], edx
0x18000a0b0  test    rcx, rcx
0x18000a0b3  jnz     short loc_18000A0C9
0x18000a0b5  test    rsi, rsi
0x18000a0b8  jnz     short loc_18000A0C9
0x18000a0ba  test    r8, r8
0x18000a0bd  jnz     short loc_18000A0C9
0x18000a0bf  mov     ebx, 0C000000Dh
0x18000a0c4  jmp     loc_18000A69C
0x18000a0c9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a0cd  mov     [rbp+DataBuffer], rdx
0x18000a0d1  mov     [rbp+var_38], rdx
0x18000a0d5  mov     [rbp+var_18], rdx
0x18000a0d9  mov     [rbp+var_30], rdx
0x18000a0dd  mov     [rbp+var_8], rdx
0x18000a0e1  test    rbx, rbx
0x18000a0e4  jz      loc_18000A5E0
0x18000a0ea  mov     r15, rdx
0x18000a0ed  cmp     [rcx], dx
0x18000a0f0  jz      loc_18000A1B9
0x18000a0f6  test    rsi, rsi
0x18000a0f9  jz      short loc_18000A104
0x18000a0fb  cmp     [rsi], dx
0x18000a0fe  jnz     loc_18000A1B9
0x18000a104  mov     edx, 5Ch ; '\'; Ch
0x18000a109  call    cs:__imp_wcschr
0x18000a110  nop     dword ptr [rax+rax+00h]
0x18000a115  xor     edx, edx
0x18000a117  mov     r15, rax
0x18000a11a  test    rax, rax
0x18000a11d  jz      loc_18000A1B9
0x18000a123  mov     rdi, r14
0x18000a126  inc     rdi
0x18000a129  cmp     [rbx+rdi*2], dx
0x18000a12d  jnz     short loc_18000A126
0x18000a12f  cmp     edi, 7FFDh
0x18000a135  ja      short loc_18000A0BF
0x18000a137  lea     edx, ds:2[rdi*2]
0x18000a13e  mov     ecx, 100h
0x18000a143  add     rdx, 2
0x18000a147  mov     r8d, 49546553h
0x18000a14d  call    cs:__imp_ExAllocatePool2
0x18000a154  nop     dword ptr [rax+rax+00h]
0x18000a159  mov     [rbp+DataBuffer], rax
0x18000a15d  mov     r15, rax
0x18000a160  test    rax, rax
0x18000a163  jnz     short loc_18000A16F
0x18000a165  mov     ebx, 0C0000017h
0x18000a16a  jmp     loc_18000A69C
0x18000a16f  mov     r8d, edi
0x18000a172  mov     rdx, rbx; Src
0x18000a175  add     r8, r8; Size
0x18000a178  mov     rcx, r15; void *
0x18000a17b  call    memmove
0x18000a180  mov     edx, 5Ch ; '\'; Ch
0x18000a185  mov     rcx, r15; Str
0x18000a188  call    cs:__imp_wcschr
0x18000a18f  nop     dword ptr [rax+rax+00h]
0x18000a194  xor     edx, edx
0x18000a196  mov     r15, rax
0x18000a199  test    rax, rax
0x18000a19c  jz      short loc_18000A1B5
0x18000a19e  mov     rsi, [rbp+DataBuffer]
0x18000a1a2  lea     rbx, [rax+2]
0x18000a1a6  mov     [rax], dx
0x18000a1a9  test    rbx, rbx
0x18000a1ac  jz      loc_18000A5E0
0x18000a1b2  mov     r15, rbx
0x18000a1b5  mov     rdi, [rbp+Src]
0x18000a1b9  cmp     [rbx], dx
0x18000a1bc  jz      loc_18000A5E0
0x18000a1c2  test    rsi, rsi
0x18000a1c5  jz      short loc_18000A1D0
0x18000a1c7  cmp     [rsi], dx
0x18000a1ca  jnz     loc_18000A5E0
0x18000a1d0  mov     rcx, rbx; unsigned __int16 *
0x18000a1d3  call    ?SspiHelperIsEncodedNullUserName@@YAHPEBG@Z; SspiHelperIsEncodedNullUserName(ushort const *)
0x18000a1d8  test    eax, eax
0x18000a1da  jnz     short loc_18000A1EC
0x18000a1dc  mov     rcx, rbx; unsigned __int16 *
0x18000a1df  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x18000a1e4  test    eax, eax
0x18000a1e6  jz      loc_18000A5E0
0x18000a1ec  xor     eax, eax
0x18000a1ee  test    rdi, rdi
0x18000a1f1  jz      short loc_18000A217
0x18000a1f3  mov     rdx, r14
0x18000a1f6  inc     rdx
0x18000a1f9  cmp     [rdi+rdx*2], ax
0x18000a1fd  jnz     short loc_18000A1F6
0x18000a1ff  cmp     edx, 7FFDh
0x18000a205  jbe     short loc_18000A219
0x18000a207  mov     ebx, 0C000000Dh
0x18000a20c  mov     rsi, rax
0x18000a20f  mov     r14, rax
0x18000a212  jmp     loc_18000A60E
0x18000a217  mov     edx, eax
0x18000a219  mov     r8, [rbp+Src]
0x18000a21d  mov     edi, eax
0x18000a21f  cmp     edi, edx
0x18000a221  jnb     short loc_18000A23F
0x18000a223  mov     ecx, edi
0x18000a225  lea     r9, aD; "@@D\a\b"
0x18000a22c  movzx   eax, word ptr [r8+rcx*2]
0x18000a231  cmp     [r9+rcx*2], ax
0x18000a236  jnz     short loc_18000A23F
0x18000a238  inc     edi
0x18000a23a  cmp     edi, 8
0x18000a23d  jb      short loc_18000A21F
0x18000a23f  lea     r14d, [rdx+8]
0x18000a243  cmp     edi, 8
0x18000a246  mov     rcx, rbx; unsigned __int16 *
0x18000a249  cmovz   r14d, edx
0x18000a24d  call    ?SspiHelperIsEncodedNullUserName@@YAHPEBG@Z; SspiHelperIsEncodedNullUserName(ushort const *)
0x18000a252  test    eax, eax
0x18000a254  jnz     short loc_18000A288
0x18000a256  lea     r8, [rbp+var_20]; void **
0x18000a25a  mov     rcx, rbx; unsigned __int16 *
0x18000a25d  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x18000a261  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x18000a266  mov     r12, [rbp+var_20]
0x18000a26a  test    eax, eax
0x18000a26c  jz      short loc_18000A27E
0x18000a26e  mov     ebx, 0C000009Ah
0x18000a273  mov     rsi, r13
0x18000a276  mov     r14, rsi
0x18000a279  jmp     loc_18000A60E
0x18000a27e  cmp     [rbp+arg_0], 4
0x18000a282  jnz     loc_18000A5E0
0x18000a288  lea     edx, ds:2[r14*2]
0x18000a290  mov     [rbp+arg_0], 3
0x18000a297  add     rdx, 2
0x18000a29b  mov     ecx, 100h
0x18000a2a0  mov     r8d, 49546553h
0x18000a2a6  call    cs:__imp_ExAllocatePool2
0x18000a2ad  nop     dword ptr [rax+rax+00h]
0x18000a2b2  mov     [rbp+var_8], rax
0x18000a2b6  mov     rcx, rax; void *
0x18000a2b9  test    rax, rax
0x18000a2bc  jnz     short loc_18000A2C5
0x18000a2be  mov     ebx, 0C0000017h
0x18000a2c3  jmp     short loc_18000A273
0x18000a2c5  mov     rdx, [rbp+Src]; Src
0x18000a2c9  cmp     edi, 8
0x18000a2cc  jz      short loc_18000A2E3
0x18000a2ce  movups  xmm0, xmmword ptr cs:aD; "@@D\a\b"
0x18000a2d5  lea     r8d, [r14-8]
0x18000a2d9  add     rcx, 10h
0x18000a2dd  movdqu  xmmword ptr [rax], xmm0
0x18000a2e1  jmp     short loc_18000A2E6
0x18000a2e3  mov     r8d, r14d
0x18000a2e6  add     r8, r8; Size
0x18000a2e9  call    memmove
0x18000a2ee  mov     rcx, [rbp+var_8]; unsigned __int16 *
0x18000a2f2  lea     r8, [rbp+var_28]; void **
0x18000a2f6  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x18000a2fa  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x18000a2ff  xor     edi, edi
0x18000a301  test    eax, eax
0x18000a303  jz      short loc_18000A327
0x18000a305  mov     rcx, rbx; unsigned __int16 *
0x18000a308  call    ?SspiHelperIsEncodedNullUserName@@YAHPEBG@Z; SspiHelperIsEncodedNullUserName(ushort const *)
0x18000a30d  mov     r13, [rbp+var_28]
0x18000a311  test    eax, eax
0x18000a313  jnz     loc_18000A5E0
0x18000a319  mov     ebx, 0C000000Dh
0x18000a31e  mov     rsi, [rbp+var_30]
0x18000a322  jmp     loc_18000A276
0x18000a327  cmp     [rbp+arg_0], 3
0x18000a32b  jnz     short loc_18000A305
0x18000a32d  mov     r13, [rbp+var_28]
0x18000a331  mov     eax, 18h
0x18000a336  mov     edx, [r13+0]
0x18000a33a  cmp     edx, eax
0x18000a33c  jb      short loc_18000A319
0x18000a33e  mov     r14, [r13+8]
0x18000a342  cmp     [r14], ax
0x18000a346  jb      short loc_18000A319
0x18000a348  mov     eax, [r14+8]
0x18000a34c  test    eax, eax
0x18000a34e  jz      loc_18000A455
0x18000a354  cmp     eax, edx
0x18000a356  ja      short loc_18000A319
0x18000a358  movzx   ecx, word ptr [r14+0Ch]
0x18000a35d  lea     r8d, [rcx+rax]
0x18000a361  cmp     r8d, eax
0x18000a364  jb      loc_18000A420
0x18000a36a  cmp     r8d, edx
0x18000a36d  ja      short loc_18000A319
0x18000a36f  test    cx, cx
0x18000a372  jz      loc_18000A42A
0x18000a378  cmp     ecx, 1Ch
0x18000a37b  jb      short loc_18000A319
0x18000a37d  lea     rdi, [r14+rax]
0x18000a381  cmp     word ptr [rdi], 1Ch
0x18000a385  jb      short loc_18000A319
0x18000a387  movzx   edx, word ptr [rdi+2]
0x18000a38b  cmp     dx, cx
0x18000a38e  ja      short loc_18000A319
0x18000a390  mov     rax, [rdi+4]
0x18000a394  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x18000a39b  jnz     short loc_18000A3A8
0x18000a39d  mov     rax, [rdi+0Ch]
0x18000a3a1  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD+8
0x18000a3a8  test    rax, rax
0x18000a3ab  jnz     loc_18000A5E0
0x18000a3b1  mov     eax, [rdi+14h]
0x18000a3b4  mov     ecx, edx
0x18000a3b6  cmp     eax, edx
0x18000a3b8  ja      loc_18000A319
0x18000a3be  movzx   r8d, word ptr [rdi+18h]
0x18000a3c3  lea     edx, [r8+rax]
0x18000a3c7  cmp     edx, eax
0x18000a3c9  jb      short loc_18000A420
0x18000a3cb  cmp     edx, ecx
0x18000a3cd  ja      loc_18000A319
0x18000a3d3  lea     edx, [r8+4]
0x18000a3d7  mov     ecx, 100h
0x18000a3dc  add     rdx, 2
0x18000a3e0  mov     r8d, 49546553h
0x18000a3e6  call    cs:__imp_ExAllocatePool2
0x18000a3ed  nop     dword ptr [rax+rax+00h]
0x18000a3f2  mov     [rbp+var_18], rax
0x18000a3f6  test    rax, rax
0x18000a3f9  jnz     short loc_18000A405
0x18000a3fb  mov     ebx, 0C0000017h
0x18000a400  jmp     loc_18000A31E
0x18000a405  mov     edx, [rdi+14h]
0x18000a408  mov     rcx, rax; void *
0x18000a40b  movzx   r8d, word ptr [rdi+18h]; Size
0x18000a410  add     rdx, rdi; Src
0x18000a413  call    memmove
0x18000a418  mov     rax, [rbp+var_18]
0x18000a41c  xor     edi, edi
0x18000a41e  jmp     short loc_18000A44F
0x18000a420  mov     ebx, 0C0000095h
0x18000a425  jmp     loc_18000A31E
0x18000a42a  mov     edx, 4
0x18000a42f  mov     ecx, 100h
0x18000a434  mov     r8d, 49546553h
0x18000a43a  call    cs:__imp_ExAllocatePool2
0x18000a441  nop     dword ptr [rax+rax+00h]
0x18000a446  mov     [rbp+var_18], rax
0x18000a44a  test    rax, rax
0x18000a44d  jz      short loc_18000A3FB
0x18000a44f  mov     [rbp+Src], rax
0x18000a453  jmp     short loc_18000A459
0x18000a455  mov     [rbp+Src], rdi
0x18000a459  mov     eax, [r14+10h]
0x18000a45d  test    eax, eax
0x18000a45f  jz      short loc_18000A4D0
0x18000a461  mov     ecx, [r13+0]
0x18000a465  cmp     eax, ecx
0x18000a467  ja      loc_18000A319
0x18000a46d  movzx   r8d, word ptr [r14+14h]
0x18000a472  lea     edx, [rax+r8*2]
0x18000a476  cmp     edx, eax
0x18000a478  jb      short loc_18000A420
0x18000a47a  cmp     edx, ecx
0x18000a47c  ja      loc_18000A319
0x18000a482  lea     rdx, ds:4[r8*2]
0x18000a48a  mov     ecx, 100h
0x18000a48f  mov     r8d, 49546553h
0x18000a495  call    cs:__imp_ExAllocatePool2
0x18000a49c  nop     dword ptr [rax+rax+00h]
0x18000a4a1  mov     [rbp+var_38], rax
0x18000a4a5  test    rax, rax
0x18000a4a8  jnz     short loc_18000A4B7
0x18000a4aa  mov     ebx, 0C0000017h
0x18000a4af  mov     r14, rax
0x18000a4b2  jmp     loc_18000A60A
0x18000a4b7  movzx   r8d, word ptr [r14+14h]
0x18000a4bc  mov     rcx, rax; void *
0x18000a4bf  mov     edx, [r14+10h]
0x18000a4c3  add     r8, r8; Size
0x18000a4c6  add     rdx, r14; Src
0x18000a4c9  call    memmove
0x18000a4ce  jmp     short loc_18000A4D4
0x18000a4d0  mov     [rbp+var_38], rdi
  ... truncated ...
```
