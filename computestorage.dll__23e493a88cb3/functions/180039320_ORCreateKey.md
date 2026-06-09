# ORCreateKey

- ea: `0x180039320`
- end: `0x180039974`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800322e4`

## callees

- `0x180003166`
- `0x180003172`
- `0x1800032b8`
- `0x180003bb5`
- `0x180038a10`
- `0x180038e44`
- `0x180038e98`
- `0x180038f40`
- `0x1800391f8`
- `0x180039320`
- `0x180039e70`
- `0x18003c560`
- `0x18003cd60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800393d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800393d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003994a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003994a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003971a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003971a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180039661`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180039661`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180039932`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180039932`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18003970a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18003970a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800395a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800395a2`

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
0x180039320  mov     [rsp-8+arg_8], rbx
0x180039325  mov     [rsp-8+Src], r8
0x18003932a  push    rbp
0x18003932b  push    rsi
0x18003932c  push    rdi
0x18003932d  push    r12
0x18003932f  push    r13
0x180039331  push    r14
0x180039333  push    r15
0x180039335  lea     rbp, [rsp-0Fh]
0x18003933a  sub     rsp, 100h
0x180039341  mov     r12, [rbp+3Fh+arg_28]
0x180039345  xor     r10d, r10d
0x180039348  mov     eax, 746Eh
0x18003934d  mov     [rsp+130h+var_C0], r10
0x180039352  xorps   xmm0, xmm0
0x180039355  mov     [rbp+3Fh+var_A8], r10
0x180039359  xorps   xmm1, xmm1
0x18003935c  mov     [rsp+130h+var_D8], r10d
0x180039361  mov     [r12], r10
0x180039365  mov     rdi, rdx
0x180039368  mov     rsi, rcx
0x18003936b  mov     [rsp+130h+var_E0], r10
0x180039370  mov     r15d, r10d
0x180039373  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x180039378  movups  [rbp+3Fh+var_90], xmm0
0x18003937c  mov     [rbp+3Fh+CreatorDescriptor], r10
0x180039380  movups  [rbp+3Fh+var_A0], xmm1
0x180039384  mov     [rbp+3Fh+NewDescriptor], r10
0x180039388  cmp     [rcx+1Ch], ax
0x18003938c  jnz     loc_180039905
0x180039392  mov     r13, [rcx+10h]
0x180039396  mov     [rsp+130h+var_E0], r13
0x18003939b  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x1800393a3  jnz     loc_180039905
0x1800393a9  test    rdx, rdx
0x1800393ac  jz      short loc_1800393C0
0x1800393ae  cmp     [rdx], r10w
0x1800393b2  jz      short loc_1800393C0
0x1800393b4  mov     r14d, r9d
0x1800393b7  and     r14d, 2
0x1800393bb  cmp     r9d, r14d
0x1800393be  jz      short loc_1800393CD
0x1800393c0  mov     ebx, 57h ; 'W'
0x1800393c5  mov     rsi, r13
0x1800393c8  jmp     loc_18003990F
0x1800393cd  lea     rcx, [r13+88h]; lpCriticalSection
0x1800393d4  call    cs:__imp_EnterCriticalSection
0x1800393db  nop     dword ptr [rax+rax+00h]
0x1800393e0  mov     r15d, 1
0x1800393e6  lea     rcx, [rbp+3Fh+var_A0]
0x1800393ea  mov     rdx, rdi
0x1800393ed  mov     qword ptr [rsp+130h+var_C8], r15
0x1800393f2  call    ORInitUnicodeStringEx
0x1800393f7  xor     r10d, r10d
0x1800393fa  mov     ebx, eax
0x1800393fc  test    eax, eax
0x1800393fe  jnz     loc_18003990A
0x180039404  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x180039408  lea     r8d, [r15+5Bh]
0x18003940c  test    cx, cx
0x18003940f  jz      short loc_180039431
0x180039411  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x180039415  movzx   eax, cx
0x180039418  shr     rax, 1
0x18003941b  cmp     [rdx+rax*2-2], r8w
0x180039421  jnz     short loc_18003942D
0x180039423  mov     eax, 0FFFEh
0x180039428  add     cx, ax
0x18003942b  jnz     short loc_180039415
0x18003942d  mov     word ptr [rbp+3Fh+var_A0], cx
0x180039431  cmp     [rsi+1Eh], r10w
0x180039436  jz      short loc_18003943F
0x180039438  mov     ebx, 3FAh
0x18003943d  jmp     short loc_1800393C5
0x18003943f  test    cx, cx
0x180039442  jz      loc_1800393C0
0x180039448  lea     r9, [rsp+130h+var_C0]
0x18003944d  mov     rdx, rsi
0x180039450  lea     r8, [rsp+130h+var_D8]
0x180039455  lea     rcx, [rbp+3Fh+var_A0]
0x180039459  call    ORParseSubKey
0x18003945e  xor     r10d, r10d
0x180039461  mov     ebx, eax
0x180039463  test    eax, eax
0x180039465  jnz     loc_18003990A
0x18003946b  cmp     [rsp+130h+var_D8], 2
0x180039470  jnz     short loc_1800394D1
0x180039472  mov     rcx, [rsp+130h+var_C0]
0x180039477  test    r14d, r14d
0x18003947a  jz      short loc_180039492
0x18003947c  mov     rax, [rcx+28h]
0x180039480  lea     r12d, [rbx+10h]
0x180039484  test    [rax+2], r12b
0x180039488  jz      loc_1800393C0
0x18003948e  mov     r12, [rbp+3Fh+arg_28]
0x180039492  cmp     rcx, [r13+38h]
0x180039496  jz      loc_1800393C0
0x18003949c  mov     edx, [rcx+18h]
0x18003949f  or      eax, 0FFFFFFFFh
0x1800394a2  cmp     edx, eax
0x1800394a4  jnz     short loc_1800394B0
0x1800394a6  mov     ebx, 5AAh
0x1800394ab  jmp     loc_1800393C5
0x1800394b0  lea     eax, [rdx+1]
0x1800394b3  mov     [rcx+18h], eax
0x1800394b6  mov     rax, [rbp+3Fh+arg_30]
0x1800394ba  test    rax, rax
0x1800394bd  jz      short loc_1800394C5
0x1800394bf  mov     dword ptr [rax], 2
0x1800394c5  mov     [r12], rcx
0x1800394c9  mov     ebx, r10d
0x1800394cc  jmp     loc_1800393C5
0x1800394d1  mov     r13, [rsp+130h+var_C0]
0x1800394d6  mov     r12d, 10h
0x1800394dc  mov     rax, [r13+28h]
0x1800394e0  test    [rax+2], r12b
0x1800394e4  jz      short loc_1800394F0
0x1800394e6  mov     ebx, 5
0x1800394eb  jmp     loc_18003990A
0x1800394f0  mov     al, [rax+0Dh]
0x1800394f3  and     al, 3
0x1800394f5  cmp     al, r15b
0x1800394f8  jz      short loc_1800394E6
0x1800394fa  mov     eax, 1FEh
0x1800394ff  cmp     [r13+20h], ax
0x180039504  jnz     short loc_180039510
0x180039506  mov     ebx, 57h ; 'W'
0x18003950b  jmp     loc_18003990A
0x180039510  mov     rdx, r10
0x180039513  mov     rax, rdi
0x180039516  add     rax, 2
0x18003951a  movzx   ecx, word ptr [rax]
0x18003951d  test    cx, cx
0x180039520  jnz     short loc_180039516
0x180039522  mov     r8d, 5Ch ; '\'
0x180039528  cmp     rax, rdi
0x18003952b  jbe     short loc_18003953C
0x18003952d  sub     rax, 2
0x180039531  movzx   ecx, word ptr [rax]
0x180039534  cmp     cx, r8w
0x180039538  jnz     short loc_180039542
0x18003953a  jmp     short loc_180039528
0x18003953c  cmp     cx, r8w
0x180039540  jz      short loc_180039555
0x180039542  cmp     rax, rdi
0x180039545  jz      short loc_180039555
0x180039547  sub     rax, 2
0x18003954b  add     rdx, 2
0x18003954f  cmp     [rax], r8w
0x180039553  jnz     short loc_180039542
0x180039555  cmp     r8w, [rax]
0x180039559  lea     rsi, [rax+2]
0x18003955d  lea     rbx, [rdx+2]
0x180039561  cmovnz  rsi, rax
0x180039565  cmp     rsi, rdi
0x180039568  cmovnz  rbx, rdx
0x18003956c  cmp     rbx, 200h
0x180039573  ja      short loc_180039506
0x180039575  xor     edx, edx; Val
0x180039577  lea     rcx, [rbp+3Fh+var_80]; void *
0x18003957b  lea     r8d, [rdx+50h]; Size
0x18003957f  call    memset_0
0x180039584  xor     edi, edi
0x180039586  mov     eax, 6B6Eh
0x18003958b  mov     word ptr [rbp+3Fh+var_80], ax
0x18003958f  test    r14d, r14d
0x180039592  jz      short loc_18003959A
0x180039594  movzx   r14d, r12w
0x180039598  jmp     short loc_18003959D
0x18003959a  mov     r14d, edi
0x18003959d  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800395a2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800395a9  nop     dword ptr [rax+rax+00h]
0x1800395ae  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x1800395b2  lea     rdx, [rbp+3Fh+var_90]
0x1800395b6  mov     r10, [rsp+130h+var_E0]
0x1800395bb  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x1800395be  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x1800395c2  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x1800395c5  or      eax, 0FFFFFFFFh
0x1800395c8  mov     dword ptr [rbp+3Fh+var_70], eax
0x1800395cb  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x1800395ce  mov     dword ptr [rbp+3Fh+var_60], eax
0x1800395d1  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x1800395d4  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x1800395d7  mov     dword ptr [rbp+3Fh+var_50], eax
0x1800395da  mov     eax, edi
0x1800395dc  mov     [rbp+3Fh+arg_0], eax
0x1800395df  mov     [rbp+3Fh+var_36], ax
0x1800395e3  mov     rax, [r10+10h]
0x1800395e7  mov     rcx, rax
0x1800395ea  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x1800395ee  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x1800395f2  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x1800395f5  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x1800395f9  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x1800395fd  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x180039601  mov     word ptr [rbp+3Fh+var_90], bx
0x180039605  mov     [rsp+130h+var_C0], rax
0x18003960a  mov     word ptr [rbp+3Fh+var_90+2], bx
0x18003960e  call    ORGetCompressedLength
0x180039613  movzx   esi, ax
0x180039616  mov     [rbp+3Fh+var_38], si
0x18003961a  cmp     rsi, rbx
0x18003961d  jnb     short loc_180039626
0x18003961f  or      r14w, 20h
0x180039624  jmp     short loc_18003962F
0x180039626  mov     eax, 0FFDFh
0x18003962b  and     r14w, ax
0x18003962f  mov     rdx, r13
0x180039632  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x180039637  mov     rcx, r10
0x18003963a  call    ORAllocNode
0x18003963f  xor     r10d, r10d
0x180039642  mov     rdi, rax
0x180039645  test    rax, rax
0x180039648  jnz     short loc_180039652
0x18003964a  lea     ebx, [rax+8]
0x18003964d  jmp     loc_18003990A
0x180039652  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x180039656  mov     r15, r10
0x180039659  test    rbx, rbx
0x18003965c  jz      short loc_180039691
0x18003965e  mov     rcx, rbx; pSecurityDescriptor
0x180039661  call    cs:__imp_IsValidSecurityDescriptor
0x180039668  nop     dword ptr [rax+rax+00h]
0x18003966d  test    eax, eax
0x18003966f  jnz     short loc_18003967B
0x180039671  mov     ebx, 53Ah
0x180039676  jmp     loc_1800398DB
0x18003967b  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x18003967f  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180039682  call    ORMakeSDRelative
0x180039687  mov     ebx, eax
0x180039689  test    eax, eax
0x18003968b  jnz     loc_1800398DB
0x180039691  mov     rax, [r13+60h]
0x180039695  xor     ebx, ebx
0x180039697  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x18003969b  mov     r10, [rax+10h]
0x18003969f  test    rdx, rdx
0x1800396a2  jz      short loc_1800396B1
0x1800396a4  test    byte ptr [rdx+2], 4
0x1800396a8  jz      short loc_1800396B1
0x1800396aa  mov     eax, 1078h
0x1800396af  jmp     short loc_1800396C8
0x1800396b1  movzx   eax, word ptr [r10+16h]
0x1800396b6  and     eax, 400h
0x1800396bb  or      eax, 41E000h
0x1800396c0  shr     eax, 0Ah
0x1800396c3  test    rdx, rdx
0x1800396c6  jz      short loc_1800396CE
0x1800396c8  test    [rdx+2], r12b
0x1800396cc  jnz     short loc_1800396DD
0x1800396ce  mov     ecx, 800h
0x1800396d3  test    [r10+16h], cx
0x1800396d8  jz      short loc_1800396DD
0x1800396da  or      eax, 2
0x1800396dd  lea     rcx, CmKeyMapping
0x1800396e4  xor     r9d, r9d; ObjectTypes
0x1800396e7  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x1800396ec  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x1800396f0  mov     [rsp+130h+Token], rbx; Token
0x1800396f5  lea     rcx, [r10+14h]; ParentDescriptor
0x1800396f9  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x1800396fd  mov     rax, qword ptr [rsp+130h+var_C8]
0x180039702  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x180039706  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x18003970a  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x180039711  nop     dword ptr [rax+rax+00h]
0x180039716  test    eax, eax
0x180039718  jnz     short loc_180039730
0x18003971a  call    cs:__imp_GetLastError
0x180039721  nop     dword ptr [rax+rax+00h]
0x180039726  mov     ebx, eax
0x180039728  test    eax, eax
0x18003972a  jnz     loc_1800398DB
0x180039730  mov     rdx, [rbp+3Fh+NewDescriptor]
0x180039734  lea     r8, [rbp+3Fh+var_A8]
0x180039738  mov     rcx, [rsp+130h+var_E0]
0x18003973d  call    ORProcessSecurityDescriptor
0x180039742  mov     ebx, eax
0x180039744  test    eax, eax
0x180039746  jnz     loc_1800398DB
0x18003974c  mov     rax, [rbp+3Fh+var_A8]
0x180039750  xor     ebx, ebx
0x180039752  mov     [rdi+60h], rax
0x180039756  mov     rcx, [rax+10h]
0x18003975a  mov     rax, qword ptr [rsp+130h+var_C8]
0x18003975f  add     [rcx+0Ch], eax
0x180039762  mov     rcx, [rbp+3Fh+Src]
0x180039766  test    rcx, rcx
0x180039769  jz      short loc_1800397BB
0x18003976b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003976f  inc     rax
0x180039772  cmp     [rcx+rax*2], bx
0x180039776  jnz     short loc_18003976F
0x180039778  add     rax, rax
0x18003977b  cmp     rax, 0FFFFh
  ... truncated ...
```
