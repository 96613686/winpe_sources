# ORCreateKey

- ea: `0x1800a05f8`
- end: `0x1800a0c76`
- name: `ORCreateKey`
- size: `1662`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005af8c`
- `0x18005b634`

## callees

- `0x180006036`
- `0x180006042`
- `0x180006158`
- `0x18000b3c9`
- `0x1800a04d8`
- `0x1800a05f8`
- `0x1800a0eb8`
- `0x1800a3328`
- `0x1800a3aa0`
- `0x1800a3e9c`
- `0x1800a3f44`
- `0x1800a4858`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a06ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a06ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0c4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a0860`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a0860`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1800a0a01`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x1800a0a01`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800a0c34`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800a0c34`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800a0952`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800a0952`

## pseudocode

```c
__int64 __fastcall ORCreateKey(
        __int64 a1,
        _WORD *a2,
        void *a3,
        int a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        _QWORD *a6,
        _DWORD *a7)
{
  _QWORD *v7; // r12
  __int64 v10; // r13
  int v11; // r14d
  int v12; // r15d
  DWORD LastError; // ebx
  unsigned __int16 v14; // cx
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rax
  __int16 v18; // bx
  _WORD *v19; // rax
  __int16 v20; // cx
  unsigned __int64 v21; // rcx
  _WORD *v22; // rsi
  unsigned __int64 v23; // r12
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // r15
  unsigned __int16 v26; // di
  int v27; // eax
  unsigned __int64 v28; // rdx
  __int64 v29; // rcx
  __int16 v30; // bx
  __int64 v31; // r12
  __int64 v32; // rsi
  PSECURITY_DESCRIPTOR v33; // rbx
  ULONG AutoInheritFlags; // eax
  __int64 v35; // rax
  _WORD *v36; // r12
  __int64 v37; // r15
  void *v38; // rax
  unsigned __int64 v39; // r12
  unsigned __int64 v40; // rbx
  __m128i *v41; // rax
  __m128i v42; // xmm1
  unsigned __int64 v43; // r8
  __m128i v44; // xmm0
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 *v47; // rax
  void *v48; // rcx
  __int64 v50; // [rsp+50h] [rbp-A1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-99h] BYREF
  unsigned __int64 v52; // [rsp+60h] [rbp-91h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+68h] [rbp-89h] BYREF
  void *Block; // [rsp+70h] [rbp-81h]
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+78h] [rbp-79h]
  __m128i v56; // [rsp+80h] [rbp-71h] BYREF
  __m128i v57; // [rsp+90h] [rbp-61h]
  __m128i v58; // [rsp+A0h] [rbp-51h]
  __m128i v59; // [rsp+B0h] [rbp-41h]
  __int64 v60; // [rsp+C0h] [rbp-31h]
  __int32 v61; // [rsp+C8h] [rbp-29h]
  __int64 v62; // [rsp+D0h] [rbp-21h] BYREF
  __int128 v63; // [rsp+D8h] [rbp-19h] BYREF
  __int128 v64; // [rsp+E8h] [rbp-9h] BYREF
  unsigned __int64 v65; // [rsp+140h] [rbp+4Fh] BYREF
  void *Src; // [rsp+150h] [rbp+5Fh]

  Src = a3;
  v7 = a6;
  v50 = 0;
  v62 = 0;
  LODWORD(v65) = 0;
  *a6 = 0;
  v10 = 0;
  v11 = 0;
  Block = 0;
  v52 = 0;
  v64 = 0;
  SystemTimeAsFileTime = 0;
  v63 = 0;
  CreatorDescriptor = 0;
  NewDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) != 29806 || (v10 = *(_QWORD *)(a1 + 16), *(_DWORD *)v10 != -1092567328) )
  {
    LastError = 6;
    goto LABEL_102;
  }
  if ( !a2 )
    goto LABEL_6;
  if ( !*a2 )
    goto LABEL_6;
  v12 = a4 & 2;
  if ( a4 != v12 )
    goto LABEL_6;
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
  v11 = 1;
  LastError = ORInitUnicodeStringEx(&v63, a2);
  if ( LastError )
    goto LABEL_102;
  v14 = v63;
  if ( (_WORD)v63 )
  {
    do
    {
      if ( *(_WORD *)(*((_QWORD *)&v63 + 1) + 2 * ((unsigned __int64)v14 >> 1) - 2) != 92 )
        break;
      v14 -= 2;
    }
    while ( v14 );
    LOWORD(v63) = v14;
  }
  if ( *(_WORD *)(a1 + 30) )
  {
    LastError = 1018;
    goto LABEL_102;
  }
  if ( !v14 )
    goto LABEL_6;
  LastError = ORParseSubKey(&v63, a1, &v65, &v50);
  if ( LastError )
    goto LABEL_102;
  v15 = v50;
  if ( (_DWORD)v65 == 2 )
  {
    if ( (!v12 || (*(_BYTE *)(*(_QWORD *)(v50 + 40) + 2LL) & 0x10) != 0) && v50 != *(_QWORD *)(v10 + 56) )
    {
      v16 = *(_DWORD *)(v50 + 24);
      if ( v16 == -1 )
      {
        LastError = 1450;
        goto LABEL_102;
      }
      *(_DWORD *)(v50 + 24) = v16 + 1;
      if ( a7 )
        *a7 = 2;
      *v7 = v15;
LABEL_25:
      LastError = 0;
      goto LABEL_102;
    }
    goto LABEL_6;
  }
  v17 = *(_QWORD *)(v50 + 40);
  v18 = 16;
  if ( (*(_BYTE *)(v17 + 2) & 0x10) != 0 || (*(_BYTE *)(v17 + 13) & 3) == 1 )
  {
    LastError = 5;
    goto LABEL_102;
  }
  if ( *(_WORD *)(v50 + 32) == 510 )
    goto LABEL_6;
  v19 = a2;
  do
    v20 = *++v19;
  while ( *v19 );
  while ( v19 > a2 )
  {
    v20 = *--v19;
    if ( *v19 != 92 )
      goto LABEL_36;
  }
  if ( v20 == 92 )
    goto LABEL_40;
LABEL_36:
  v21 = 0;
  do
  {
    if ( v19 == a2 )
      break;
    --v19;
    v21 += 2LL;
  }
  while ( *v19 != 92 );
  v52 = v21;
LABEL_40:
  v22 = v19 + 1;
  if ( *v19 != 92 )
    v22 = v19;
  v23 = v52 + 2;
  if ( v22 != a2 )
    v23 = v52;
  if ( v23 > 0x200 )
  {
LABEL_6:
    LastError = 87;
    goto LABEL_102;
  }
  memset_0(&v56, 0, 0x50u);
  v56.m128i_i16[0] = 27502;
  if ( !v12 )
    v18 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v24 = *(_QWORD *)(v10 + 16);
  LOWORD(v25) = 0;
  v59.m128i_i32[1] &= 0xFFFF0000;
  *(struct _FILETIME *)((char *)v56.m128i_i64 + 4) = SystemTimeAsFileTime;
  v57.m128i_i32[0] = -1;
  v57.m128i_i32[3] = -1;
  v58.m128i_i32[0] = -1;
  v58.m128i_i32[3] = -1;
  v59.m128i_i32[0] = -1;
  v26 = v23;
  v27 = *(_DWORD *)(v24 + 24) + (*(_DWORD *)(v24 + 20) << 12);
  v28 = (unsigned __int64)(unsigned __int16)v23 >> 1;
  v56.m128i_i8[12] = 0;
  *(__int64 *)((char *)v57.m128i_i64 + 4) = 0;
  *(__int64 *)((char *)v58.m128i_i64 + 4) = 0xFFFFFFFF00000000uLL;
  HIWORD(v61) = 0;
  v59.m128i_i64[1] = 0;
  LODWORD(v60) = 0;
  v52 = v24;
  *((_QWORD *)&v64 + 1) = v22;
  LOWORD(v64) = v23;
  WORD1(v64) = v23;
  if ( v27 != 4097 )
  {
    v29 = 0;
    if ( v28 )
    {
      while ( LOBYTE(v22[v29]) == v22[v29] )
      {
        if ( ++v29 == v28 )
          goto LABEL_51;
      }
    }
    else
    {
LABEL_51:
      v26 = (unsigned __int16)v23 >> 1;
    }
  }
  LOWORD(v61) = v26;
  v65 = v26;
  if ( v26 >= v23 )
    v30 = v18 & 0xFFDF;
  else
    v30 = v18 | 0x20;
  v31 = v50;
  v56.m128i_i16[1] = v30;
  v32 = ORAllocNode(v10, v50);
  if ( !v32 )
  {
    LastError = 8;
    goto LABEL_102;
  }
  v33 = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
    goto LABEL_61;
  if ( IsValidSecurityDescriptor(pSecurityDescriptor) )
  {
    LastError = ORMakeSDRelative(v33);
    if ( LastError )
      goto LABEL_97;
LABEL_61:
    LastError = 0;
    AutoInheritFlags = 4216;
    if ( (!CreatorDescriptor || (*((_BYTE *)CreatorDescriptor + 2) & 4) == 0)
      && (*(_WORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 96) + 16LL) + 22LL) & 0x400) != 0 )
    {
      AutoInheritFlags = 4217;
    }
    if ( (!CreatorDescriptor || (*((_BYTE *)CreatorDescriptor + 2) & 0x10) == 0)
      && (*(_WORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 96) + 16LL) + 22LL) & 0x800) != 0 )
    {
      AutoInheritFlags |= 2u;
    }
    if ( !CreatePrivateObjectSecurityWithMultipleInheritance(
            (PSECURITY_DESCRIPTOR)(*(_QWORD *)(*(_QWORD *)(v31 + 96) + 16LL) + 20LL),
            CreatorDescriptor,
            &NewDescriptor,
            0,
            0,
            1,
            AutoInheritFlags,
            0,
            &CmKeyMapping) )
      LastError = GetLastError();
    if ( LastError )
      goto LABEL_97;
    LastError = ORProcessSecurityDescriptor(v10, NewDescriptor, &v62);
    if ( LastError )
      goto LABEL_97;
    v35 = v62;
    v36 = Src;
    *(_QWORD *)(v32 + 96) = v62;
    ++*(_DWORD *)(*(_QWORD *)(v35 + 16) + 12LL);
    if ( v36 )
    {
      v37 = -1;
      do
        ++v37;
      while ( v36[v37] );
      v25 = 2 * v37;
      if ( v25 > 0xFFFF )
        goto LABEL_96;
      HIWORD(v61) = v25;
      if ( (_WORD)v25 )
      {
        v38 = o__aligned_malloc_0((unsigned __int16)v25, 0x10u);
        *(_QWORD *)(v32 + 120) = v38;
        if ( !v38 )
        {
LABEL_82:
          LastError = 8;
          goto LABEL_97;
        }
        memcpy_0(v38, v36, (unsigned __int16)v25);
      }
    }
    v39 = v65;
    v40 = v65 + 76;
    if ( v65 < 0xFFFFFFFFFFFFFFB4uLL )
    {
      v41 = (__m128i *)o__aligned_malloc_0(v65 + 76, 0x10u);
      Block = v41;
      if ( !v41 )
        goto LABEL_82;
      v42 = v58;
      v43 = v52;
      *v41 = v56;
      v41[1] = v57;
      v44 = v59;
      v41[2] = v42;
      v42.m128i_i64[0] = v60;
      v41[3] = v44;
      v41[4].m128i_i64[0] = v42.m128i_i64[0];
      v41[4].m128i_i32[2] = v61;
      ORCompressCopyName((char *)&v41[4].m128i_u64[1] + 4, v40, v43, &v64);
      v45 = v50;
      *(_QWORD *)(v32 + 40) = Block;
      if ( *(_WORD *)(v45 + 28) != 29806 || *(_WORD *)(v32 + 28) != 29806 )
      {
        LastError = 87;
        goto LABEL_97;
      }
      ORInsertTreeNodeIntoSubkeyList(v45, v32);
      v46 = *(_QWORD *)(v45 + 40);
      ++*(_DWORD *)(v46 + 20);
      *(struct _FILETIME *)(v46 + 4) = SystemTimeAsFileTime;
      if ( (unsigned int)(unsigned __int16)v25 > *(_DWORD *)(v46 + 56) )
        *(_DWORD *)(v46 + 56) = (unsigned __int16)v25;
      if ( (_mm_cvtsi128_si32(_mm_srli_si128(v56, 2)) & 0x20) != 0 )
      {
        if ( 2 * v39 > *(unsigned __int16 *)(v46 + 52) )
        {
          v26 *= 2;
LABEL_91:
          *(_WORD *)(v46 + 52) = v26;
        }
      }
      else if ( v26 > *(_WORD *)(v46 + 52) )
      {
        goto LABEL_91;
      }
      ++*(_QWORD *)(v45 + 168);
      if ( a7 )
        *a7 = 1;
      v47 = a6;
      *(_DWORD *)(v10 + 180) = 1;
      *(_DWORD *)(v32 + 24) = 1;
      *v47 = v32;
      goto LABEL_25;
    }
LABEL_96:
    LastError = 534;
    goto LABEL_97;
  }
  LastError = 1338;
LABEL_97:
  v48 = *(void **)(v32 + 120);
  if ( v48 )
    aligned_free(v48);
  aligned_free((void *)v32);
  if ( Block )
    aligned_free(Block);
LABEL_102:
  if ( CreatorDescriptor != pSecurityDescriptor && CreatorDescriptor )
    aligned_free(CreatorDescriptor);
  if ( NewDescriptor )
    DestroyPrivateObjectSecurity(&NewDescriptor);
  if ( v11 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 136));
  return LastError;
}

```

## disassembly

```asm
0x1800a05f8  mov     [rsp-8+arg_8], rbx
0x1800a05fd  mov     [rsp-8+Src], r8
0x1800a0602  push    rbp
0x1800a0603  push    rsi
0x1800a0604  push    rdi
0x1800a0605  push    r12
0x1800a0607  push    r13
0x1800a0609  push    r14
0x1800a060b  push    r15
0x1800a060d  lea     rbp, [rsp-0Fh]
0x1800a0612  sub     rsp, 100h
0x1800a0619  mov     r12, [rbp+3Fh+arg_28]
0x1800a061d  xor     r8d, r8d
0x1800a0620  mov     eax, 746Eh
0x1800a0625  mov     [rsp+130h+var_E0], r8
0x1800a062a  xorps   xmm0, xmm0
0x1800a062d  mov     [rbp+3Fh+var_60], r8
0x1800a0631  xorps   xmm1, xmm1
0x1800a0634  mov     dword ptr [rbp+3Fh+arg_0], r8d
0x1800a0638  mov     [r12], r8
0x1800a063c  mov     rdi, rdx
0x1800a063f  mov     rsi, rcx
0x1800a0642  mov     r13d, r8d
0x1800a0645  mov     r14d, r8d
0x1800a0648  mov     [rsp+130h+Block], r8
0x1800a064d  mov     [rsp+130h+var_D0], r8
0x1800a0652  movups  [rbp+3Fh+var_48], xmm0
0x1800a0656  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r8
0x1800a065b  movups  [rbp+3Fh+var_58], xmm1
0x1800a065f  mov     [rbp+3Fh+CreatorDescriptor], r8
0x1800a0663  mov     [rsp+130h+NewDescriptor], r8
0x1800a0668  cmp     [rcx+1Ch], ax
0x1800a066c  jnz     loc_1800A0C0D
0x1800a0672  mov     r13, [rcx+10h]
0x1800a0676  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x1800a067e  jnz     loc_1800A0C0D
0x1800a0684  test    rdx, rdx
0x1800a0687  jz      short loc_1800A069B
0x1800a0689  cmp     [rdx], r8w
0x1800a068d  jz      short loc_1800A069B
0x1800a068f  mov     r15d, r9d
0x1800a0692  and     r15d, 2
0x1800a0696  cmp     r9d, r15d
0x1800a0699  jz      short loc_1800A06A5
0x1800a069b  mov     ebx, 57h ; 'W'
0x1800a06a0  jmp     loc_1800A0C12
0x1800a06a5  lea     rcx, [r13+88h]; lpCriticalSection
0x1800a06ac  call    cs:__imp_EnterCriticalSection
0x1800a06b3  nop     dword ptr [rax+rax+00h]
0x1800a06b8  mov     rdx, rdi
0x1800a06bb  lea     rcx, [rbp+3Fh+var_58]
0x1800a06bf  mov     r14d, 1
0x1800a06c5  call    ORInitUnicodeStringEx
0x1800a06ca  xor     r8d, r8d
0x1800a06cd  mov     ebx, eax
0x1800a06cf  test    eax, eax
0x1800a06d1  jnz     loc_1800A0C12
0x1800a06d7  movzx   ecx, word ptr [rbp+3Fh+var_58]
0x1800a06db  lea     r9d, [r14+5Bh]
0x1800a06df  test    cx, cx
0x1800a06e2  jz      short loc_1800A0704
0x1800a06e4  mov     rdx, qword ptr [rbp+3Fh+var_58+8]
0x1800a06e8  movzx   eax, cx
0x1800a06eb  shr     rax, 1
0x1800a06ee  cmp     [rdx+rax*2-2], r9w
0x1800a06f4  jnz     short loc_1800A0700
0x1800a06f6  mov     eax, 0FFFEh
0x1800a06fb  add     cx, ax
0x1800a06fe  jnz     short loc_1800A06E8
0x1800a0700  mov     word ptr [rbp+3Fh+var_58], cx
0x1800a0704  cmp     [rsi+1Eh], r8w
0x1800a0709  jz      short loc_1800A0715
0x1800a070b  mov     ebx, 3FAh
0x1800a0710  jmp     loc_1800A0C12
0x1800a0715  test    cx, cx
0x1800a0718  jz      short loc_1800A069B
0x1800a071a  lea     r9, [rsp+130h+var_E0]
0x1800a071f  mov     rdx, rsi
0x1800a0722  lea     r8, [rbp+3Fh+arg_0]
0x1800a0726  lea     rcx, [rbp+3Fh+var_58]
0x1800a072a  call    ORParseSubKey
0x1800a072f  xor     r8d, r8d
0x1800a0732  mov     ebx, eax
0x1800a0734  test    eax, eax
0x1800a0736  jnz     loc_1800A0C12
0x1800a073c  cmp     dword ptr [rbp+3Fh+arg_0], 2
0x1800a0740  mov     rcx, [rsp+130h+var_E0]
0x1800a0745  jnz     short loc_1800A079B
0x1800a0747  test    r15d, r15d
0x1800a074a  jz      short loc_1800A075C
0x1800a074c  mov     rax, [rcx+28h]
0x1800a0750  lea     edx, [rbx+10h]
0x1800a0753  test    [rax+2], dl
0x1800a0756  jz      loc_1800A069B
0x1800a075c  cmp     rcx, [r13+38h]
0x1800a0760  jz      loc_1800A069B
0x1800a0766  mov     edx, [rcx+18h]
0x1800a0769  or      eax, 0FFFFFFFFh
0x1800a076c  cmp     edx, eax
0x1800a076e  jnz     short loc_1800A077A
0x1800a0770  mov     ebx, 5AAh
0x1800a0775  jmp     loc_1800A0C12
0x1800a077a  lea     eax, [rdx+1]
0x1800a077d  mov     [rcx+18h], eax
0x1800a0780  mov     rax, [rbp+3Fh+arg_30]
0x1800a0784  test    rax, rax
0x1800a0787  jz      short loc_1800A078F
0x1800a0789  mov     dword ptr [rax], 2
0x1800a078f  mov     [r12], rcx
0x1800a0793  mov     ebx, r8d
0x1800a0796  jmp     loc_1800A0C12
0x1800a079b  mov     rax, [rcx+28h]
0x1800a079f  mov     ebx, 10h
0x1800a07a4  test    [rax+2], bl
0x1800a07a7  jz      short loc_1800A07B3
0x1800a07a9  mov     ebx, 5
0x1800a07ae  jmp     loc_1800A0C12
0x1800a07b3  mov     al, [rax+0Dh]
0x1800a07b6  and     al, 3
0x1800a07b8  cmp     al, r14b
0x1800a07bb  jz      short loc_1800A07A9
0x1800a07bd  mov     eax, 1FEh
0x1800a07c2  cmp     [rcx+20h], ax
0x1800a07c6  jz      loc_1800A069B
0x1800a07cc  mov     rax, rdi
0x1800a07cf  add     rax, 2
0x1800a07d3  movzx   ecx, word ptr [rax]
0x1800a07d6  test    cx, cx
0x1800a07d9  jnz     short loc_1800A07CF
0x1800a07db  mov     edx, 5Ch ; '\'
0x1800a07e0  cmp     rax, rdi
0x1800a07e3  jbe     short loc_1800A07F3
0x1800a07e5  sub     rax, 2
0x1800a07e9  movzx   ecx, word ptr [rax]
0x1800a07ec  cmp     cx, dx
0x1800a07ef  jnz     short loc_1800A07F8
0x1800a07f1  jmp     short loc_1800A07E0
0x1800a07f3  cmp     cx, dx
0x1800a07f6  jz      short loc_1800A0812
0x1800a07f8  mov     rcx, r8
0x1800a07fb  cmp     rax, rdi
0x1800a07fe  jz      short loc_1800A080D
0x1800a0800  sub     rax, 2
0x1800a0804  add     rcx, 2
0x1800a0808  cmp     [rax], dx
0x1800a080b  jnz     short loc_1800A07FB
0x1800a080d  mov     [rsp+130h+var_D0], rcx
0x1800a0812  cmp     dx, [rax]
0x1800a0815  lea     rsi, [rax+2]
0x1800a0819  cmovnz  rsi, rax
0x1800a081d  mov     rax, [rsp+130h+var_D0]
0x1800a0822  cmp     rsi, rdi
0x1800a0825  lea     r12, [rax+2]
0x1800a0829  cmovnz  r12, rax
0x1800a082d  cmp     r12, 200h
0x1800a0834  ja      loc_1800A069B
0x1800a083a  xor     edx, edx; Val
0x1800a083c  lea     rcx, [rbp+3Fh+var_B0]; void *
0x1800a0840  lea     r8d, [rdx+50h]; Size
0x1800a0844  call    memset_0
0x1800a0849  xor     edi, edi
0x1800a084b  mov     eax, 6B6Eh
0x1800a0850  mov     word ptr [rbp+3Fh+var_B0], ax
0x1800a0854  test    r15d, r15d
0x1800a0857  jnz     short loc_1800A085B
0x1800a0859  mov     ebx, edi
0x1800a085b  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a0860  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a0867  nop     dword ptr [rax+rax+00h]
0x1800a086c  mov     rcx, [r13+10h]
0x1800a0870  xor     r8d, r8d
0x1800a0873  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x1800a0877  movzx   r15d, r8w
0x1800a087b  and     dword ptr [rbp+3Fh+var_80+4], 0FFFF0000h
0x1800a0882  mov     dword ptr [rbp+3Fh+var_B0+4], eax
0x1800a0885  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x1800a0889  mov     dword ptr [rbp+3Fh+var_B0+8], eax
0x1800a088c  or      eax, 0FFFFFFFFh
0x1800a088f  mov     dword ptr [rbp+3Fh+var_A0], eax
0x1800a0892  mov     dword ptr [rbp+3Fh+var_A0+0Ch], eax
0x1800a0895  mov     dword ptr [rbp+3Fh+var_90], eax
0x1800a0898  mov     dword ptr [rbp+3Fh+var_90+8], eax
0x1800a089b  mov     dword ptr [rbp+3Fh+var_90+0Ch], eax
0x1800a089e  mov     dword ptr [rbp+3Fh+var_80], eax
0x1800a08a1  mov     eax, [rcx+14h]
0x1800a08a4  movzx   edi, r12w
0x1800a08a8  shl     eax, 0Ch
0x1800a08ab  mov     edx, edi
0x1800a08ad  add     eax, [rcx+18h]
0x1800a08b0  shr     rdx, 1
0x1800a08b3  mov     byte ptr [rbp+3Fh+var_B0+0Ch], r8b
0x1800a08b7  mov     qword ptr [rbp+3Fh+var_A0+4], r8
0x1800a08bb  mov     dword ptr [rbp+3Fh+var_90+4], r8d
0x1800a08bf  mov     word ptr [rbp+3Fh+var_68+2], r8w
0x1800a08c4  mov     qword ptr [rbp+3Fh+var_80+8], r8
0x1800a08c8  mov     dword ptr [rbp+3Fh+var_70], r8d
0x1800a08cc  mov     [rsp+130h+var_D0], rcx
0x1800a08d1  mov     qword ptr [rbp+3Fh+var_48+8], rsi
0x1800a08d5  mov     word ptr [rbp+3Fh+var_48], di
0x1800a08d9  mov     word ptr [rbp+3Fh+var_48+2], di
0x1800a08dd  cmp     eax, 1001h
0x1800a08e2  jz      short loc_1800A0901
0x1800a08e4  mov     ecx, r8d
0x1800a08e7  test    rdx, rdx
0x1800a08ea  jz      short loc_1800A08FE
0x1800a08ec  movzx   eax, byte ptr [rsi+rcx*2]
0x1800a08f0  cmp     ax, [rsi+rcx*2]
0x1800a08f4  jnz     short loc_1800A0901
0x1800a08f6  add     rcx, r14
0x1800a08f9  cmp     rcx, rdx
0x1800a08fc  jnz     short loc_1800A08EC
0x1800a08fe  movzx   edi, dx
0x1800a0901  movzx   eax, di
0x1800a0904  mov     word ptr [rbp+3Fh+var_68], di
0x1800a0908  mov     [rbp+3Fh+arg_0], rax
0x1800a090c  cmp     rax, r12
0x1800a090f  jnb     short loc_1800A0917
0x1800a0911  or      bx, 20h
0x1800a0915  jmp     short loc_1800A091F
0x1800a0917  mov     eax, 0FFDFh
0x1800a091c  and     bx, ax
0x1800a091f  mov     r12, [rsp+130h+var_E0]
0x1800a0924  mov     rcx, r13
0x1800a0927  mov     rdx, r12
0x1800a092a  mov     word ptr [rbp+3Fh+var_B0+2], bx
0x1800a092e  call    ORAllocNode
0x1800a0933  xor     r8d, r8d
0x1800a0936  mov     rsi, rax
0x1800a0939  test    rax, rax
0x1800a093c  jnz     short loc_1800A0946
0x1800a093e  lea     ebx, [rax+8]
0x1800a0941  jmp     loc_1800A0C12
0x1800a0946  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x1800a094a  test    rbx, rbx
0x1800a094d  jz      short loc_1800A0985
0x1800a094f  mov     rcx, rbx; pSecurityDescriptor
0x1800a0952  call    cs:__imp_IsValidSecurityDescriptor
0x1800a0959  nop     dword ptr [rax+rax+00h]
0x1800a095e  test    eax, eax
0x1800a0960  jnz     short loc_1800A096C
0x1800a0962  mov     ebx, 53Ah
0x1800a0967  jmp     loc_1800A0BE3
0x1800a096c  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x1800a0970  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800a0973  call    ORMakeSDRelative
0x1800a0978  xor     r8d, r8d
0x1800a097b  mov     ebx, eax
0x1800a097d  test    eax, eax
0x1800a097f  jnz     loc_1800A0BE3
0x1800a0985  mov     rax, [r12+60h]
0x1800a098a  mov     ebx, r8d
0x1800a098d  mov     r12, [rbp+3Fh+CreatorDescriptor]
0x1800a0991  mov     rcx, [rax+10h]
0x1800a0995  mov     eax, 1078h
0x1800a099a  add     rcx, 14h; ParentDescriptor
0x1800a099e  test    r12, r12
0x1800a09a1  jz      short loc_1800A09AB
0x1800a09a3  test    byte ptr [r12+2], 4
0x1800a09a9  jnz     short loc_1800A09BC
0x1800a09ab  mov     edx, 400h
0x1800a09b0  test    [rcx+2], dx
0x1800a09b4  mov     edx, 1079h
0x1800a09b9  cmovnz  eax, edx
0x1800a09bc  test    r12, r12
0x1800a09bf  jz      short loc_1800A09C9
0x1800a09c1  test    byte ptr [r12+2], 10h
0x1800a09c7  jnz     short loc_1800A09D7
0x1800a09c9  mov     edx, 800h
0x1800a09ce  test    [rcx+2], dx
0x1800a09d2  jz      short loc_1800A09D7
0x1800a09d4  or      eax, 2
0x1800a09d7  lea     rdx, CmKeyMapping
0x1800a09de  xor     r9d, r9d; ObjectTypes
0x1800a09e1  mov     [rsp+130h+GenericMapping], rdx; GenericMapping
0x1800a09e6  mov     rdx, r12; CreatorDescriptor
0x1800a09e9  mov     [rsp+130h+Token], r8; Token
0x1800a09ee  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x1800a09f2  mov     [rsp+130h+IsContainerObject], r14d; IsContainerObject
0x1800a09f7  mov     [rsp+130h+GuidCount], r8d; GuidCount
0x1800a09fc  lea     r8, [rsp+130h+NewDescriptor]; NewDescriptor
0x1800a0a01  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x1800a0a08  nop     dword ptr [rax+rax+00h]
0x1800a0a0d  test    eax, eax
0x1800a0a0f  jnz     short loc_1800A0A1F
0x1800a0a11  call    cs:__imp_GetLastError
0x1800a0a18  nop     dword ptr [rax+rax+00h]
0x1800a0a1d  mov     ebx, eax
0x1800a0a1f  test    ebx, ebx
0x1800a0a21  jnz     loc_1800A0BE3
0x1800a0a27  mov     rdx, [rsp+130h+NewDescriptor]
0x1800a0a2c  lea     r8, [rbp+3Fh+var_60]
0x1800a0a30  mov     rcx, r13
0x1800a0a33  call    ORProcessSecurityDescriptor
0x1800a0a38  xor     r8d, r8d
0x1800a0a3b  mov     ebx, eax
0x1800a0a3d  test    eax, eax
0x1800a0a3f  jnz     loc_1800A0BE3
0x1800a0a45  mov     rax, [rbp+3Fh+var_60]
0x1800a0a49  mov     r12, [rbp+3Fh+Src]
0x1800a0a4d  mov     [rsi+60h], rax
  ... truncated ...
```
