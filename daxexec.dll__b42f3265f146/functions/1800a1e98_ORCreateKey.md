# ORCreateKey

- ea: `0x1800a1e98`
- end: `0x1800a24ec`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c9d8`
- `0x18005d0b8`

## callees

- `0x180005886`
- `0x180005892`
- `0x1800059a8`
- `0x18000b126`
- `0x1800a1d6c`
- `0x1800a1e98`
- `0x1800a2730`
- `0x1800a4a54`
- `0x1800a50f4`
- `0x1800a5528`
- `0x1800a557c`
- `0x1800a5624`
- `0x1800a6000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a24c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a24c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1f4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2292`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a211a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a211a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1800a2282`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1800a2282`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800a24aa`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800a24aa`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800a21d9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800a21d9`

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
0x1800a1e98  mov     [rsp-8+arg_8], rbx
0x1800a1e9d  mov     [rsp-8+Src], r8
0x1800a1ea2  push    rbp
0x1800a1ea3  push    rsi
0x1800a1ea4  push    rdi
0x1800a1ea5  push    r12
0x1800a1ea7  push    r13
0x1800a1ea9  push    r14
0x1800a1eab  push    r15
0x1800a1ead  lea     rbp, [rsp-0Fh]
0x1800a1eb2  sub     rsp, 100h
0x1800a1eb9  mov     r12, [rbp+3Fh+arg_28]
0x1800a1ebd  xor     r10d, r10d
0x1800a1ec0  mov     eax, 746Eh
0x1800a1ec5  mov     [rsp+130h+var_C0], r10
0x1800a1eca  xorps   xmm0, xmm0
0x1800a1ecd  mov     [rbp+3Fh+var_A8], r10
0x1800a1ed1  xorps   xmm1, xmm1
0x1800a1ed4  mov     [rsp+130h+var_D8], r10d
0x1800a1ed9  mov     [r12], r10
0x1800a1edd  mov     rdi, rdx
0x1800a1ee0  mov     rsi, rcx
0x1800a1ee3  mov     [rsp+130h+var_E0], r10
0x1800a1ee8  mov     r15d, r10d
0x1800a1eeb  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x1800a1ef0  movups  [rbp+3Fh+var_90], xmm0
0x1800a1ef4  mov     [rbp+3Fh+CreatorDescriptor], r10
0x1800a1ef8  movups  [rbp+3Fh+var_A0], xmm1
0x1800a1efc  mov     [rbp+3Fh+NewDescriptor], r10
0x1800a1f00  cmp     [rcx+1Ch], ax
0x1800a1f04  jnz     loc_1800A247D
0x1800a1f0a  mov     r13, [rcx+10h]
0x1800a1f0e  mov     [rsp+130h+var_E0], r13
0x1800a1f13  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x1800a1f1b  jnz     loc_1800A247D
0x1800a1f21  test    rdx, rdx
0x1800a1f24  jz      short loc_1800A1F38
0x1800a1f26  cmp     [rdx], r10w
0x1800a1f2a  jz      short loc_1800A1F38
0x1800a1f2c  mov     r14d, r9d
0x1800a1f2f  and     r14d, 2
0x1800a1f33  cmp     r9d, r14d
0x1800a1f36  jz      short loc_1800A1F45
0x1800a1f38  mov     ebx, 57h ; 'W'
0x1800a1f3d  mov     rsi, r13
0x1800a1f40  jmp     loc_1800A2487
0x1800a1f45  lea     rcx, [r13+88h]; lpCriticalSection
0x1800a1f4c  call    cs:__imp_EnterCriticalSection
0x1800a1f53  nop     dword ptr [rax+rax+00h]
0x1800a1f58  mov     r15d, 1
0x1800a1f5e  lea     rcx, [rbp+3Fh+var_A0]
0x1800a1f62  mov     rdx, rdi
0x1800a1f65  mov     qword ptr [rsp+130h+var_C8], r15
0x1800a1f6a  call    ORInitUnicodeStringEx
0x1800a1f6f  xor     r10d, r10d
0x1800a1f72  mov     ebx, eax
0x1800a1f74  test    eax, eax
0x1800a1f76  jnz     loc_1800A2482
0x1800a1f7c  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x1800a1f80  lea     r8d, [r15+5Bh]
0x1800a1f84  test    cx, cx
0x1800a1f87  jz      short loc_1800A1FA9
0x1800a1f89  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x1800a1f8d  movzx   eax, cx
0x1800a1f90  shr     rax, 1
0x1800a1f93  cmp     [rdx+rax*2-2], r8w
0x1800a1f99  jnz     short loc_1800A1FA5
0x1800a1f9b  mov     eax, 0FFFEh
0x1800a1fa0  add     cx, ax
0x1800a1fa3  jnz     short loc_1800A1F8D
0x1800a1fa5  mov     word ptr [rbp+3Fh+var_A0], cx
0x1800a1fa9  cmp     [rsi+1Eh], r10w
0x1800a1fae  jz      short loc_1800A1FB7
0x1800a1fb0  mov     ebx, 3FAh
0x1800a1fb5  jmp     short loc_1800A1F3D
0x1800a1fb7  test    cx, cx
0x1800a1fba  jz      loc_1800A1F38
0x1800a1fc0  lea     r9, [rsp+130h+var_C0]
0x1800a1fc5  mov     rdx, rsi
0x1800a1fc8  lea     r8, [rsp+130h+var_D8]
0x1800a1fcd  lea     rcx, [rbp+3Fh+var_A0]
0x1800a1fd1  call    ORParseSubKey
0x1800a1fd6  xor     r10d, r10d
0x1800a1fd9  mov     ebx, eax
0x1800a1fdb  test    eax, eax
0x1800a1fdd  jnz     loc_1800A2482
0x1800a1fe3  cmp     [rsp+130h+var_D8], 2
0x1800a1fe8  jnz     short loc_1800A2049
0x1800a1fea  mov     rcx, [rsp+130h+var_C0]
0x1800a1fef  test    r14d, r14d
0x1800a1ff2  jz      short loc_1800A200A
0x1800a1ff4  mov     rax, [rcx+28h]
0x1800a1ff8  lea     r12d, [rbx+10h]
0x1800a1ffc  test    [rax+2], r12b
0x1800a2000  jz      loc_1800A1F38
0x1800a2006  mov     r12, [rbp+3Fh+arg_28]
0x1800a200a  cmp     rcx, [r13+38h]
0x1800a200e  jz      loc_1800A1F38
0x1800a2014  mov     edx, [rcx+18h]
0x1800a2017  or      eax, 0FFFFFFFFh
0x1800a201a  cmp     edx, eax
0x1800a201c  jnz     short loc_1800A2028
0x1800a201e  mov     ebx, 5AAh
0x1800a2023  jmp     loc_1800A1F3D
0x1800a2028  lea     eax, [rdx+1]
0x1800a202b  mov     [rcx+18h], eax
0x1800a202e  mov     rax, [rbp+3Fh+arg_30]
0x1800a2032  test    rax, rax
0x1800a2035  jz      short loc_1800A203D
0x1800a2037  mov     dword ptr [rax], 2
0x1800a203d  mov     [r12], rcx
0x1800a2041  mov     ebx, r10d
0x1800a2044  jmp     loc_1800A1F3D
0x1800a2049  mov     r13, [rsp+130h+var_C0]
0x1800a204e  mov     r12d, 10h
0x1800a2054  mov     rax, [r13+28h]
0x1800a2058  test    [rax+2], r12b
0x1800a205c  jz      short loc_1800A2068
0x1800a205e  mov     ebx, 5
0x1800a2063  jmp     loc_1800A2482
0x1800a2068  mov     al, [rax+0Dh]
0x1800a206b  and     al, 3
0x1800a206d  cmp     al, r15b
0x1800a2070  jz      short loc_1800A205E
0x1800a2072  mov     eax, 1FEh
0x1800a2077  cmp     [r13+20h], ax
0x1800a207c  jnz     short loc_1800A2088
0x1800a207e  mov     ebx, 57h ; 'W'
0x1800a2083  jmp     loc_1800A2482
0x1800a2088  mov     rdx, r10
0x1800a208b  mov     rax, rdi
0x1800a208e  add     rax, 2
0x1800a2092  movzx   ecx, word ptr [rax]
0x1800a2095  test    cx, cx
0x1800a2098  jnz     short loc_1800A208E
0x1800a209a  mov     r8d, 5Ch ; '\'
0x1800a20a0  cmp     rax, rdi
0x1800a20a3  jbe     short loc_1800A20B4
0x1800a20a5  sub     rax, 2
0x1800a20a9  movzx   ecx, word ptr [rax]
0x1800a20ac  cmp     cx, r8w
0x1800a20b0  jnz     short loc_1800A20BA
0x1800a20b2  jmp     short loc_1800A20A0
0x1800a20b4  cmp     cx, r8w
0x1800a20b8  jz      short loc_1800A20CD
0x1800a20ba  cmp     rax, rdi
0x1800a20bd  jz      short loc_1800A20CD
0x1800a20bf  sub     rax, 2
0x1800a20c3  add     rdx, 2
0x1800a20c7  cmp     [rax], r8w
0x1800a20cb  jnz     short loc_1800A20BA
0x1800a20cd  cmp     r8w, [rax]
0x1800a20d1  lea     rsi, [rax+2]
0x1800a20d5  lea     rbx, [rdx+2]
0x1800a20d9  cmovnz  rsi, rax
0x1800a20dd  cmp     rsi, rdi
0x1800a20e0  cmovnz  rbx, rdx
0x1800a20e4  cmp     rbx, 200h
0x1800a20eb  ja      short loc_1800A207E
0x1800a20ed  xor     edx, edx; Val
0x1800a20ef  lea     rcx, [rbp+3Fh+var_80]; void *
0x1800a20f3  lea     r8d, [rdx+50h]; Size
0x1800a20f7  call    memset_0
0x1800a20fc  xor     edi, edi
0x1800a20fe  mov     eax, 6B6Eh
0x1800a2103  mov     word ptr [rbp+3Fh+var_80], ax
0x1800a2107  test    r14d, r14d
0x1800a210a  jz      short loc_1800A2112
0x1800a210c  movzx   r14d, r12w
0x1800a2110  jmp     short loc_1800A2115
0x1800a2112  mov     r14d, edi
0x1800a2115  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a211a  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a2121  nop     dword ptr [rax+rax+00h]
0x1800a2126  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x1800a212a  lea     rdx, [rbp+3Fh+var_90]
0x1800a212e  mov     r10, [rsp+130h+var_E0]
0x1800a2133  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x1800a2136  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x1800a213a  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x1800a213d  or      eax, 0FFFFFFFFh
0x1800a2140  mov     dword ptr [rbp+3Fh+var_70], eax
0x1800a2143  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x1800a2146  mov     dword ptr [rbp+3Fh+var_60], eax
0x1800a2149  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x1800a214c  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x1800a214f  mov     dword ptr [rbp+3Fh+var_50], eax
0x1800a2152  mov     eax, edi
0x1800a2154  mov     [rbp+3Fh+arg_0], eax
0x1800a2157  mov     [rbp+3Fh+var_36], ax
0x1800a215b  mov     rax, [r10+10h]
0x1800a215f  mov     rcx, rax
0x1800a2162  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x1800a2166  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x1800a216a  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x1800a216d  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x1800a2171  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x1800a2175  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x1800a2179  mov     word ptr [rbp+3Fh+var_90], bx
0x1800a217d  mov     [rsp+130h+var_C0], rax
0x1800a2182  mov     word ptr [rbp+3Fh+var_90+2], bx
0x1800a2186  call    ORGetCompressedLength
0x1800a218b  movzx   esi, ax
0x1800a218e  mov     [rbp+3Fh+var_38], si
0x1800a2192  cmp     rsi, rbx
0x1800a2195  jnb     short loc_1800A219E
0x1800a2197  or      r14w, 20h
0x1800a219c  jmp     short loc_1800A21A7
0x1800a219e  mov     eax, 0FFDFh
0x1800a21a3  and     r14w, ax
0x1800a21a7  mov     rdx, r13
0x1800a21aa  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x1800a21af  mov     rcx, r10
0x1800a21b2  call    ORAllocNode
0x1800a21b7  xor     r10d, r10d
0x1800a21ba  mov     rdi, rax
0x1800a21bd  test    rax, rax
0x1800a21c0  jnz     short loc_1800A21CA
0x1800a21c2  lea     ebx, [rax+8]
0x1800a21c5  jmp     loc_1800A2482
0x1800a21ca  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x1800a21ce  mov     r15, r10
0x1800a21d1  test    rbx, rbx
0x1800a21d4  jz      short loc_1800A2209
0x1800a21d6  mov     rcx, rbx; pSecurityDescriptor
0x1800a21d9  call    cs:__imp_IsValidSecurityDescriptor
0x1800a21e0  nop     dword ptr [rax+rax+00h]
0x1800a21e5  test    eax, eax
0x1800a21e7  jnz     short loc_1800A21F3
0x1800a21e9  mov     ebx, 53Ah
0x1800a21ee  jmp     loc_1800A2453
0x1800a21f3  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x1800a21f7  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800a21fa  call    ORMakeSDRelative
0x1800a21ff  mov     ebx, eax
0x1800a2201  test    eax, eax
0x1800a2203  jnz     loc_1800A2453
0x1800a2209  mov     rax, [r13+60h]
0x1800a220d  xor     ebx, ebx
0x1800a220f  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x1800a2213  mov     r10, [rax+10h]
0x1800a2217  test    rdx, rdx
0x1800a221a  jz      short loc_1800A2229
0x1800a221c  test    byte ptr [rdx+2], 4
0x1800a2220  jz      short loc_1800A2229
0x1800a2222  mov     eax, 1078h
0x1800a2227  jmp     short loc_1800A2240
0x1800a2229  movzx   eax, word ptr [r10+16h]
0x1800a222e  and     eax, 400h
0x1800a2233  or      eax, 41E000h
0x1800a2238  shr     eax, 0Ah
0x1800a223b  test    rdx, rdx
0x1800a223e  jz      short loc_1800A2246
0x1800a2240  test    [rdx+2], r12b
0x1800a2244  jnz     short loc_1800A2255
0x1800a2246  mov     ecx, 800h
0x1800a224b  test    [r10+16h], cx
0x1800a2250  jz      short loc_1800A2255
0x1800a2252  or      eax, 2
0x1800a2255  lea     rcx, CmKeyMapping
0x1800a225c  xor     r9d, r9d; ObjectTypes
0x1800a225f  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x1800a2264  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x1800a2268  mov     [rsp+130h+Token], rbx; Token
0x1800a226d  lea     rcx, [r10+14h]; ParentDescriptor
0x1800a2271  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x1800a2275  mov     rax, qword ptr [rsp+130h+var_C8]
0x1800a227a  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x1800a227e  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x1800a2282  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x1800a2289  nop     dword ptr [rax+rax+00h]
0x1800a228e  test    eax, eax
0x1800a2290  jnz     short loc_1800A22A8
0x1800a2292  call    cs:__imp_GetLastError
0x1800a2299  nop     dword ptr [rax+rax+00h]
0x1800a229e  mov     ebx, eax
0x1800a22a0  test    eax, eax
0x1800a22a2  jnz     loc_1800A2453
0x1800a22a8  mov     rdx, [rbp+3Fh+NewDescriptor]
0x1800a22ac  lea     r8, [rbp+3Fh+var_A8]
0x1800a22b0  mov     rcx, [rsp+130h+var_E0]
0x1800a22b5  call    ORProcessSecurityDescriptor
0x1800a22ba  mov     ebx, eax
0x1800a22bc  test    eax, eax
0x1800a22be  jnz     loc_1800A2453
0x1800a22c4  mov     rax, [rbp+3Fh+var_A8]
0x1800a22c8  xor     ebx, ebx
0x1800a22ca  mov     [rdi+60h], rax
0x1800a22ce  mov     rcx, [rax+10h]
0x1800a22d2  mov     rax, qword ptr [rsp+130h+var_C8]
0x1800a22d7  add     [rcx+0Ch], eax
0x1800a22da  mov     rcx, [rbp+3Fh+Src]
0x1800a22de  test    rcx, rcx
0x1800a22e1  jz      short loc_1800A2333
0x1800a22e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a22e7  inc     rax
0x1800a22ea  cmp     [rcx+rax*2], bx
0x1800a22ee  jnz     short loc_1800A22E7
0x1800a22f0  add     rax, rax
0x1800a22f3  cmp     rax, 0FFFFh
  ... truncated ...
```
