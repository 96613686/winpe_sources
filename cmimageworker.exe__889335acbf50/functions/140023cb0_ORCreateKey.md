# ORCreateKey

- ea: `0x140023cb0`
- end: `0x140024304`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021a0c`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x140002b2c`
- `0x140023b78`
- `0x140023cb0`
- `0x140024888`
- `0x140026bbc`
- `0x140026ff0`
- `0x140027044`
- `0x1400270ec`
- `0x140029598`
- `0x14002a1ac`
- `0x14002e8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140023d64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140023d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400242da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400242da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400240aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400240aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140023f32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140023f32`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1400242c2`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1400242c2`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140023ff1`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140023ff1`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x14002409a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x14002409a`

## pseudocode

```c
__int64 __fastcall ORCreateKey(
        __int64 a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 *a6,
        _DWORD *a7)
{
  __int64 *v7; // r12
  __int64 v10; // r15
  __int64 v11; // r13
  int v12; // r14d
  DWORD LastError; // ebx
  __int64 v14; // rsi
  unsigned __int16 v15; // cx
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // r13
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  _WORD *v21; // rax
  __int16 v22; // cx
  _WORD *v23; // rsi
  unsigned __int64 v24; // rbx
  __int16 v25; // r14
  __int64 v26; // rcx
  unsigned __int16 v27; // ax
  __int64 v28; // r10
  __int64 v29; // rsi
  __int16 v30; // r14
  __int64 v31; // rdi
  void *v32; // r15
  __int64 v33; // r10
  ULONG AutoInheritFlags; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  unsigned int v38; // ebx
  void *v39; // rax
  _OWORD *v40; // rax
  __int128 v41; // xmm1
  __int64 v42; // r8
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int64 v46; // rdx
  void *v47; // rcx
  __int64 v49; // [rsp+50h] [rbp-A1h]
  int v50; // [rsp+58h] [rbp-99h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-91h] BYREF
  BOOL IsContainerObject[2]; // [rsp+68h] [rbp-89h]
  __int64 v53; // [rsp+70h] [rbp-81h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+78h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+80h] [rbp-71h]
  __int64 v56; // [rsp+88h] [rbp-69h] BYREF
  __int128 v57; // [rsp+90h] [rbp-61h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-51h] BYREF
  __int128 v59; // [rsp+B0h] [rbp-41h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-31h]
  __int128 v61; // [rsp+D0h] [rbp-21h]
  _BYTE v62[28]; // [rsp+E0h] [rbp-11h]
  unsigned __int16 v63; // [rsp+140h] [rbp+4Fh]

  v7 = a6;
  v53 = 0;
  v56 = 0;
  v50 = 0;
  *a6 = 0;
  v49 = 0;
  LODWORD(v10) = 0;
  SystemTimeAsFileTime = 0;
  v58 = 0;
  CreatorDescriptor = 0;
  v57 = 0;
  NewDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 || (v11 = *(_QWORD *)(a1 + 16), v49 = v11, *(_DWORD *)v11 != -1092567328) )
  {
    LastError = 6;
    goto LABEL_97;
  }
  if ( !a2 )
    goto LABEL_6;
  if ( !*a2 )
    goto LABEL_6;
  v12 = a4 & 2;
  if ( a4 != v12 )
    goto LABEL_6;
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 136));
  LODWORD(v10) = 1;
  *(_QWORD *)IsContainerObject = 1;
  LastError = ORInitUnicodeStringEx(&v57, a2);
  if ( LastError )
    goto LABEL_97;
  v15 = v57;
  if ( (_WORD)v57 )
  {
    do
    {
      if ( *(_WORD *)(*((_QWORD *)&v57 + 1) + 2 * ((unsigned __int64)v15 >> 1) - 2) != 92 )
        break;
      v15 -= 2;
    }
    while ( v15 );
    LOWORD(v57) = v15;
  }
  if ( *(_WORD *)(a1 + 30) )
  {
    LastError = 1018;
    goto LABEL_7;
  }
  if ( !v15 )
    goto LABEL_6;
  LastError = ORParseSubKey(&v57, a1, &v50, &v53);
  if ( LastError )
  {
LABEL_97:
    v14 = v49;
    goto LABEL_98;
  }
  if ( v50 == 2 )
  {
    v16 = v53;
    if ( !v12 )
      goto LABEL_21;
    if ( (*(_BYTE *)(*(_QWORD *)(v53 + 40) + 2LL) & 0x10) != 0 )
    {
      v7 = a6;
LABEL_21:
      if ( v53 != *(_QWORD *)(v11 + 56) )
      {
        v17 = *(_DWORD *)(v53 + 24);
        if ( v17 == -1 )
        {
          LastError = 1450;
        }
        else
        {
          *(_DWORD *)(v53 + 24) = v17 + 1;
          if ( a7 )
            *a7 = 2;
          *v7 = v16;
          LastError = 0;
        }
        goto LABEL_7;
      }
    }
LABEL_6:
    LastError = 87;
LABEL_7:
    v14 = v11;
    goto LABEL_98;
  }
  v18 = v53;
  v19 = *(_QWORD *)(v53 + 40);
  if ( (*(_BYTE *)(v19 + 2) & 0x10) != 0 || (*(_BYTE *)(v19 + 13) & 3) == 1 )
  {
    LastError = 5;
    goto LABEL_97;
  }
  if ( *(_WORD *)(v53 + 32) == 510 )
    goto LABEL_31;
  v20 = 0;
  v21 = a2;
  do
    v22 = *++v21;
  while ( *v21 );
  while ( v21 > a2 )
  {
    v22 = *--v21;
    if ( *v21 != 92 )
      goto LABEL_38;
  }
  if ( v22 == 92 )
    goto LABEL_40;
  do
  {
LABEL_38:
    if ( v21 == a2 )
      break;
    --v21;
    v20 += 2LL;
  }
  while ( *v21 != 92 );
LABEL_40:
  v23 = v21 + 1;
  v24 = v20 + 2;
  if ( *v21 != 92 )
    v23 = v21;
  if ( v23 != a2 )
    v24 = v20;
  if ( v24 > 0x200 )
  {
LABEL_31:
    LastError = 87;
    goto LABEL_97;
  }
  memset_0(&v59, 0, 0x50u);
  LOWORD(v59) = 27502;
  if ( v12 )
    v25 = 16;
  else
    v25 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)((char *)&v59 + 4) = SystemTimeAsFileTime;
  LODWORD(v60) = -1;
  HIDWORD(v60) = -1;
  *(_QWORD *)&v61 = 0xFFFFFFFFLL;
  *((_QWORD *)&v61 + 1) = -1;
  *(_DWORD *)v62 = -1;
  v63 = 0;
  *(_WORD *)&v62[26] = 0;
  v26 = *(_QWORD *)(v49 + 16);
  BYTE12(v59) = 0;
  *(_QWORD *)((char *)&v60 + 4) = 0;
  *(_OWORD *)&v62[4] = 0u;
  *((_QWORD *)&v58 + 1) = v23;
  LOWORD(v58) = v24;
  v53 = v26;
  WORD1(v58) = v24;
  v27 = ORGetCompressedLength(v26, &v58);
  v29 = v27;
  *(_WORD *)&v62[24] = v27;
  if ( v27 >= v24 )
    v30 = v25 & 0xFFDF;
  else
    v30 = v25 | 0x20;
  WORD1(v59) = v30;
  v31 = ORAllocNode(v28, v18);
  if ( !v31 )
  {
    LastError = 8;
    goto LABEL_97;
  }
  v32 = 0;
  if ( pSecurityDescriptor )
  {
    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    {
      LastError = 1338;
LABEL_91:
      v47 = *(void **)(v31 + 120);
      if ( v47 )
        aligned_free(v47);
      aligned_free((void *)v31);
      if ( v32 )
        aligned_free(v32);
      LODWORD(v10) = IsContainerObject[0];
      goto LABEL_97;
    }
    LastError = ORMakeSDRelative(pSecurityDescriptor);
    if ( LastError )
      goto LABEL_91;
  }
  v33 = *(_QWORD *)(*(_QWORD *)(v18 + 96) + 16LL);
  if ( CreatorDescriptor && (*((_BYTE *)CreatorDescriptor + 2) & 4) != 0 )
  {
    AutoInheritFlags = 4216;
  }
  else
  {
    AutoInheritFlags = (*(_WORD *)(v33 + 22) & 0x400 | 0x41E000u) >> 10;
    if ( !CreatorDescriptor )
      goto LABEL_62;
  }
  if ( (*((_BYTE *)CreatorDescriptor + 2) & 0x10) == 0 )
  {
LABEL_62:
    if ( (*(_WORD *)(v33 + 22) & 0x800) != 0 )
      AutoInheritFlags |= 2u;
  }
  if ( !CreatePrivateObjectSecurityWithMultipleInheritance(
          (PSECURITY_DESCRIPTOR)(v33 + 20),
          CreatorDescriptor,
          &NewDescriptor,
          0,
          0,
          IsContainerObject[0],
          AutoInheritFlags,
          0,
          &CmKeyMapping) )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_91;
  }
  LastError = ORProcessSecurityDescriptor(v49, NewDescriptor, &v56);
  if ( LastError )
    goto LABEL_91;
  v35 = v56;
  *(_QWORD *)(v31 + 96) = v56;
  *(_DWORD *)(*(_QWORD *)(v35 + 16) + 12LL) += IsContainerObject[0];
  if ( a3 )
  {
    v36 = -1;
    do
      ++v36;
    while ( a3[v36] );
    v37 = 2 * v36;
    if ( v37 > 0xFFFF )
    {
      LastError = 534;
      goto LABEL_91;
    }
    *(_WORD *)&v62[26] = v37;
    v63 = v37;
    if ( (_WORD)v37 )
    {
      v38 = (unsigned __int16)v37;
      v39 = o__aligned_malloc_0((unsigned __int16)v37, 0x10u);
      *(_QWORD *)(v31 + 120) = v39;
      if ( !v39 )
      {
LABEL_75:
        LastError = 8;
        goto LABEL_91;
      }
      memcpy_0(v39, a3, v38);
    }
  }
  v40 = o__aligned_malloc_0(v29 + 76, 0x10u);
  v32 = v40;
  if ( !v40 )
    goto LABEL_75;
  v41 = v60;
  v42 = v53;
  *v40 = v59;
  v43 = v61;
  v40[1] = v41;
  v44 = *(_OWORD *)v62;
  v40[2] = v43;
  v45 = *(_OWORD *)&v62[12];
  v40[3] = v44;
  *(_OWORD *)((char *)v40 + 60) = v45;
  ORCompressCopyName((char *)v40 + 76, v29 + 76, v42, &v58);
  *(_QWORD *)(v31 + 40) = v32;
  if ( !v18 || *(_WORD *)(v18 + 28) != 29806 || *(_WORD *)(v31 + 28) != 29806 )
  {
    LastError = 87;
    goto LABEL_91;
  }
  ORInsertTreeNodeIntoSubkeyList(v18, v31);
  v46 = *(_QWORD *)(v18 + 40);
  v10 = *(_QWORD *)IsContainerObject;
  *(_DWORD *)(v46 + 20) += IsContainerObject[0];
  *(struct _FILETIME *)(v46 + 4) = SystemTimeAsFileTime;
  if ( (unsigned int)v63 > *(_DWORD *)(v46 + 56) )
    *(_DWORD *)(v46 + 56) = v63;
  if ( (v30 & 0x20) != 0 )
  {
    if ( 2 * v29 > (unsigned __int64)*(unsigned __int16 *)(v46 + 52) )
    {
      LOWORD(v29) = 2 * v29;
LABEL_85:
      *(_WORD *)(v46 + 52) = v29;
    }
  }
  else if ( (unsigned __int16)v29 > *(_WORD *)(v46 + 52) )
  {
    goto LABEL_85;
  }
  *(_QWORD *)(v18 + 168) += v10;
  if ( a7 )
    *a7 = v10;
  v14 = v49;
  LastError = 0;
  *(_DWORD *)(v49 + 180) = v10;
  *(_DWORD *)(v31 + 24) = v10;
  *a6 = v31;
LABEL_98:
  if ( CreatorDescriptor != pSecurityDescriptor && CreatorDescriptor )
    aligned_free(CreatorDescriptor);
  if ( NewDescriptor )
    DestroyPrivateObjectSecurity(&NewDescriptor);
  if ( (_DWORD)v10 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 136));
  return LastError;
}

```

## disassembly

```asm
0x140023cb0  mov     [rsp-8+arg_8], rbx
0x140023cb5  mov     [rsp-8+Src], r8
0x140023cba  push    rbp
0x140023cbb  push    rsi
0x140023cbc  push    rdi
0x140023cbd  push    r12
0x140023cbf  push    r13
0x140023cc1  push    r14
0x140023cc3  push    r15
0x140023cc5  lea     rbp, [rsp-0Fh]
0x140023cca  sub     rsp, 100h
0x140023cd1  mov     r12, [rbp+3Fh+arg_28]
0x140023cd5  xor     r10d, r10d
0x140023cd8  mov     eax, 746Eh
0x140023cdd  mov     [rsp+130h+var_C0], r10
0x140023ce2  xorps   xmm0, xmm0
0x140023ce5  mov     [rbp+3Fh+var_A8], r10
0x140023ce9  xorps   xmm1, xmm1
0x140023cec  mov     [rsp+130h+var_D8], r10d
0x140023cf1  mov     [r12], r10
0x140023cf5  mov     rdi, rdx
0x140023cf8  mov     rsi, rcx
0x140023cfb  mov     [rsp+130h+var_E0], r10
0x140023d00  mov     r15d, r10d
0x140023d03  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x140023d08  movups  [rbp+3Fh+var_90], xmm0
0x140023d0c  mov     [rbp+3Fh+CreatorDescriptor], r10
0x140023d10  movups  [rbp+3Fh+var_A0], xmm1
0x140023d14  mov     [rbp+3Fh+NewDescriptor], r10
0x140023d18  cmp     [rcx+1Ch], ax
0x140023d1c  jnz     loc_140024295
0x140023d22  mov     r13, [rcx+10h]
0x140023d26  mov     [rsp+130h+var_E0], r13
0x140023d2b  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x140023d33  jnz     loc_140024295
0x140023d39  test    rdx, rdx
0x140023d3c  jz      short loc_140023D50
0x140023d3e  cmp     [rdx], r10w
0x140023d42  jz      short loc_140023D50
0x140023d44  mov     r14d, r9d
0x140023d47  and     r14d, 2
0x140023d4b  cmp     r9d, r14d
0x140023d4e  jz      short loc_140023D5D
0x140023d50  mov     ebx, 57h ; 'W'
0x140023d55  mov     rsi, r13
0x140023d58  jmp     loc_14002429F
0x140023d5d  lea     rcx, [r13+88h]; lpCriticalSection
0x140023d64  call    cs:__imp_EnterCriticalSection
0x140023d6b  nop     dword ptr [rax+rax+00h]
0x140023d70  mov     r15d, 1
0x140023d76  lea     rcx, [rbp+3Fh+var_A0]
0x140023d7a  mov     rdx, rdi
0x140023d7d  mov     qword ptr [rsp+130h+var_C8], r15
0x140023d82  call    ORInitUnicodeStringEx
0x140023d87  xor     r10d, r10d
0x140023d8a  mov     ebx, eax
0x140023d8c  test    eax, eax
0x140023d8e  jnz     loc_14002429A
0x140023d94  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x140023d98  lea     r8d, [r15+5Bh]
0x140023d9c  test    cx, cx
0x140023d9f  jz      short loc_140023DC1
0x140023da1  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x140023da5  movzx   eax, cx
0x140023da8  shr     rax, 1
0x140023dab  cmp     [rdx+rax*2-2], r8w
0x140023db1  jnz     short loc_140023DBD
0x140023db3  mov     eax, 0FFFEh
0x140023db8  add     cx, ax
0x140023dbb  jnz     short loc_140023DA5
0x140023dbd  mov     word ptr [rbp+3Fh+var_A0], cx
0x140023dc1  cmp     [rsi+1Eh], r10w
0x140023dc6  jz      short loc_140023DCF
0x140023dc8  mov     ebx, 3FAh
0x140023dcd  jmp     short loc_140023D55
0x140023dcf  test    cx, cx
0x140023dd2  jz      loc_140023D50
0x140023dd8  lea     r9, [rsp+130h+var_C0]
0x140023ddd  mov     rdx, rsi
0x140023de0  lea     r8, [rsp+130h+var_D8]
0x140023de5  lea     rcx, [rbp+3Fh+var_A0]
0x140023de9  call    ORParseSubKey
0x140023dee  xor     r10d, r10d
0x140023df1  mov     ebx, eax
0x140023df3  test    eax, eax
0x140023df5  jnz     loc_14002429A
0x140023dfb  cmp     [rsp+130h+var_D8], 2
0x140023e00  jnz     short loc_140023E61
0x140023e02  mov     rcx, [rsp+130h+var_C0]
0x140023e07  test    r14d, r14d
0x140023e0a  jz      short loc_140023E22
0x140023e0c  mov     rax, [rcx+28h]
0x140023e10  lea     r12d, [rbx+10h]
0x140023e14  test    [rax+2], r12b
0x140023e18  jz      loc_140023D50
0x140023e1e  mov     r12, [rbp+3Fh+arg_28]
0x140023e22  cmp     rcx, [r13+38h]
0x140023e26  jz      loc_140023D50
0x140023e2c  mov     edx, [rcx+18h]
0x140023e2f  or      eax, 0FFFFFFFFh
0x140023e32  cmp     edx, eax
0x140023e34  jnz     short loc_140023E40
0x140023e36  mov     ebx, 5AAh
0x140023e3b  jmp     loc_140023D55
0x140023e40  lea     eax, [rdx+1]
0x140023e43  mov     [rcx+18h], eax
0x140023e46  mov     rax, [rbp+3Fh+arg_30]
0x140023e4a  test    rax, rax
0x140023e4d  jz      short loc_140023E55
0x140023e4f  mov     dword ptr [rax], 2
0x140023e55  mov     [r12], rcx
0x140023e59  mov     ebx, r10d
0x140023e5c  jmp     loc_140023D55
0x140023e61  mov     r13, [rsp+130h+var_C0]
0x140023e66  mov     r12d, 10h
0x140023e6c  mov     rax, [r13+28h]
0x140023e70  test    [rax+2], r12b
0x140023e74  jz      short loc_140023E80
0x140023e76  mov     ebx, 5
0x140023e7b  jmp     loc_14002429A
0x140023e80  mov     al, [rax+0Dh]
0x140023e83  and     al, 3
0x140023e85  cmp     al, r15b
0x140023e88  jz      short loc_140023E76
0x140023e8a  mov     eax, 1FEh
0x140023e8f  cmp     [r13+20h], ax
0x140023e94  jnz     short loc_140023EA0
0x140023e96  mov     ebx, 57h ; 'W'
0x140023e9b  jmp     loc_14002429A
0x140023ea0  mov     rdx, r10
0x140023ea3  mov     rax, rdi
0x140023ea6  add     rax, 2
0x140023eaa  movzx   ecx, word ptr [rax]
0x140023ead  test    cx, cx
0x140023eb0  jnz     short loc_140023EA6
0x140023eb2  mov     r8d, 5Ch ; '\'
0x140023eb8  cmp     rax, rdi
0x140023ebb  jbe     short loc_140023ECC
0x140023ebd  sub     rax, 2
0x140023ec1  movzx   ecx, word ptr [rax]
0x140023ec4  cmp     cx, r8w
0x140023ec8  jnz     short loc_140023ED2
0x140023eca  jmp     short loc_140023EB8
0x140023ecc  cmp     cx, r8w
0x140023ed0  jz      short loc_140023EE5
0x140023ed2  cmp     rax, rdi
0x140023ed5  jz      short loc_140023EE5
0x140023ed7  sub     rax, 2
0x140023edb  add     rdx, 2
0x140023edf  cmp     [rax], r8w
0x140023ee3  jnz     short loc_140023ED2
0x140023ee5  cmp     r8w, [rax]
0x140023ee9  lea     rsi, [rax+2]
0x140023eed  lea     rbx, [rdx+2]
0x140023ef1  cmovnz  rsi, rax
0x140023ef5  cmp     rsi, rdi
0x140023ef8  cmovnz  rbx, rdx
0x140023efc  cmp     rbx, 200h
0x140023f03  ja      short loc_140023E96
0x140023f05  xor     edx, edx; Val
0x140023f07  lea     rcx, [rbp+3Fh+var_80]; void *
0x140023f0b  lea     r8d, [rdx+50h]; Size
0x140023f0f  call    memset_0
0x140023f14  xor     edi, edi
0x140023f16  mov     eax, 6B6Eh
0x140023f1b  mov     word ptr [rbp+3Fh+var_80], ax
0x140023f1f  test    r14d, r14d
0x140023f22  jz      short loc_140023F2A
0x140023f24  movzx   r14d, r12w
0x140023f28  jmp     short loc_140023F2D
0x140023f2a  mov     r14d, edi
0x140023f2d  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140023f32  call    cs:__imp_GetSystemTimeAsFileTime
0x140023f39  nop     dword ptr [rax+rax+00h]
0x140023f3e  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x140023f42  lea     rdx, [rbp+3Fh+var_90]
0x140023f46  mov     r10, [rsp+130h+var_E0]
0x140023f4b  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x140023f4e  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x140023f52  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x140023f55  or      eax, 0FFFFFFFFh
0x140023f58  mov     dword ptr [rbp+3Fh+var_70], eax
0x140023f5b  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x140023f5e  mov     dword ptr [rbp+3Fh+var_60], eax
0x140023f61  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x140023f64  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x140023f67  mov     dword ptr [rbp+3Fh+var_50], eax
0x140023f6a  mov     eax, edi
0x140023f6c  mov     [rbp+3Fh+arg_0], eax
0x140023f6f  mov     [rbp+3Fh+var_36], ax
0x140023f73  mov     rax, [r10+10h]
0x140023f77  mov     rcx, rax
0x140023f7a  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x140023f7e  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x140023f82  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x140023f85  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x140023f89  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x140023f8d  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x140023f91  mov     word ptr [rbp+3Fh+var_90], bx
0x140023f95  mov     [rsp+130h+var_C0], rax
0x140023f9a  mov     word ptr [rbp+3Fh+var_90+2], bx
0x140023f9e  call    ORGetCompressedLength
0x140023fa3  movzx   esi, ax
0x140023fa6  mov     [rbp+3Fh+var_38], si
0x140023faa  cmp     rsi, rbx
0x140023fad  jnb     short loc_140023FB6
0x140023faf  or      r14w, 20h
0x140023fb4  jmp     short loc_140023FBF
0x140023fb6  mov     eax, 0FFDFh
0x140023fbb  and     r14w, ax
0x140023fbf  mov     rdx, r13
0x140023fc2  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x140023fc7  mov     rcx, r10
0x140023fca  call    ORAllocNode
0x140023fcf  xor     r10d, r10d
0x140023fd2  mov     rdi, rax
0x140023fd5  test    rax, rax
0x140023fd8  jnz     short loc_140023FE2
0x140023fda  lea     ebx, [rax+8]
0x140023fdd  jmp     loc_14002429A
0x140023fe2  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x140023fe6  mov     r15, r10
0x140023fe9  test    rbx, rbx
0x140023fec  jz      short loc_140024021
0x140023fee  mov     rcx, rbx; pSecurityDescriptor
0x140023ff1  call    cs:__imp_IsValidSecurityDescriptor
0x140023ff8  nop     dword ptr [rax+rax+00h]
0x140023ffd  test    eax, eax
0x140023fff  jnz     short loc_14002400B
0x140024001  mov     ebx, 53Ah
0x140024006  jmp     loc_14002426B
0x14002400b  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x14002400f  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x140024012  call    ORMakeSDRelative
0x140024017  mov     ebx, eax
0x140024019  test    eax, eax
0x14002401b  jnz     loc_14002426B
0x140024021  mov     rax, [r13+60h]
0x140024025  xor     ebx, ebx
0x140024027  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x14002402b  mov     r10, [rax+10h]
0x14002402f  test    rdx, rdx
0x140024032  jz      short loc_140024041
0x140024034  test    byte ptr [rdx+2], 4
0x140024038  jz      short loc_140024041
0x14002403a  mov     eax, 1078h
0x14002403f  jmp     short loc_140024058
0x140024041  movzx   eax, word ptr [r10+16h]
0x140024046  and     eax, 400h
0x14002404b  or      eax, 41E000h
0x140024050  shr     eax, 0Ah
0x140024053  test    rdx, rdx
0x140024056  jz      short loc_14002405E
0x140024058  test    [rdx+2], r12b
0x14002405c  jnz     short loc_14002406D
0x14002405e  mov     ecx, 800h
0x140024063  test    [r10+16h], cx
0x140024068  jz      short loc_14002406D
0x14002406a  or      eax, 2
0x14002406d  lea     rcx, CmKeyMapping
0x140024074  xor     r9d, r9d; ObjectTypes
0x140024077  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x14002407c  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x140024080  mov     [rsp+130h+Token], rbx; Token
0x140024085  lea     rcx, [r10+14h]; ParentDescriptor
0x140024089  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x14002408d  mov     rax, qword ptr [rsp+130h+var_C8]
0x140024092  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x140024096  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x14002409a  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x1400240a1  nop     dword ptr [rax+rax+00h]
0x1400240a6  test    eax, eax
0x1400240a8  jnz     short loc_1400240C0
0x1400240aa  call    cs:__imp_GetLastError
0x1400240b1  nop     dword ptr [rax+rax+00h]
0x1400240b6  mov     ebx, eax
0x1400240b8  test    eax, eax
0x1400240ba  jnz     loc_14002426B
0x1400240c0  mov     rdx, [rbp+3Fh+NewDescriptor]
0x1400240c4  lea     r8, [rbp+3Fh+var_A8]
0x1400240c8  mov     rcx, [rsp+130h+var_E0]
0x1400240cd  call    ORProcessSecurityDescriptor
0x1400240d2  mov     ebx, eax
0x1400240d4  test    eax, eax
0x1400240d6  jnz     loc_14002426B
0x1400240dc  mov     rax, [rbp+3Fh+var_A8]
0x1400240e0  xor     ebx, ebx
0x1400240e2  mov     [rdi+60h], rax
0x1400240e6  mov     rcx, [rax+10h]
0x1400240ea  mov     rax, qword ptr [rsp+130h+var_C8]
0x1400240ef  add     [rcx+0Ch], eax
0x1400240f2  mov     rcx, [rbp+3Fh+Src]
0x1400240f6  test    rcx, rcx
0x1400240f9  jz      short loc_14002414B
0x1400240fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400240ff  inc     rax
0x140024102  cmp     [rcx+rax*2], bx
0x140024106  jnz     short loc_1400240FF
0x140024108  add     rax, rax
0x14002410b  cmp     rax, 0FFFFh
  ... truncated ...
```
