# ORCreateKey

- ea: `0x18002cdfc`
- end: `0x18002d450`
- name: `ORCreateKey`
- size: `1620`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c9fc`

## callees

- `0x180003542`
- `0x18000354e`
- `0x180003614`
- `0x18000362c`
- `0x18002ccd4`
- `0x18002cdfc`
- `0x18002d694`
- `0x18002f034`
- `0x18002f708`
- `0x18002fa24`
- `0x18002fa78`
- `0x18002fb20`
- `0x18003045c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ceb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ceb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1f6`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18002d1e6`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18002d1e6`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002d40e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002d40e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002d13d`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002d13d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d07e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d07e`

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
0x18002cdfc  mov     [rsp-8+arg_8], rbx
0x18002ce01  mov     [rsp-8+Src], r8
0x18002ce06  push    rbp
0x18002ce07  push    rsi
0x18002ce08  push    rdi
0x18002ce09  push    r12
0x18002ce0b  push    r13
0x18002ce0d  push    r14
0x18002ce0f  push    r15
0x18002ce11  lea     rbp, [rsp-0Fh]
0x18002ce16  sub     rsp, 100h
0x18002ce1d  mov     r12, [rbp+3Fh+arg_28]
0x18002ce21  xor     r10d, r10d
0x18002ce24  mov     eax, 746Eh
0x18002ce29  mov     [rsp+130h+var_C0], r10
0x18002ce2e  xorps   xmm0, xmm0
0x18002ce31  mov     [rbp+3Fh+var_A8], r10
0x18002ce35  xorps   xmm1, xmm1
0x18002ce38  mov     [rsp+130h+var_D8], r10d
0x18002ce3d  mov     [r12], r10
0x18002ce41  mov     rdi, rdx
0x18002ce44  mov     rsi, rcx
0x18002ce47  mov     [rsp+130h+var_E0], r10
0x18002ce4c  mov     r15d, r10d
0x18002ce4f  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r10
0x18002ce54  movups  [rbp+3Fh+var_90], xmm0
0x18002ce58  mov     [rbp+3Fh+CreatorDescriptor], r10
0x18002ce5c  movups  [rbp+3Fh+var_A0], xmm1
0x18002ce60  mov     [rbp+3Fh+NewDescriptor], r10
0x18002ce64  cmp     [rcx+1Ch], ax
0x18002ce68  jnz     loc_18002D3E1
0x18002ce6e  mov     r13, [rcx+10h]
0x18002ce72  mov     [rsp+130h+var_E0], r13
0x18002ce77  cmp     dword ptr [r13+0], 0BEE0BEE0h
0x18002ce7f  jnz     loc_18002D3E1
0x18002ce85  test    rdx, rdx
0x18002ce88  jz      short loc_18002CE9C
0x18002ce8a  cmp     [rdx], r10w
0x18002ce8e  jz      short loc_18002CE9C
0x18002ce90  mov     r14d, r9d
0x18002ce93  and     r14d, 2
0x18002ce97  cmp     r9d, r14d
0x18002ce9a  jz      short loc_18002CEA9
0x18002ce9c  mov     ebx, 57h ; 'W'
0x18002cea1  mov     rsi, r13
0x18002cea4  jmp     loc_18002D3EB
0x18002cea9  lea     rcx, [r13+88h]; lpCriticalSection
0x18002ceb0  call    cs:__imp_EnterCriticalSection
0x18002ceb7  nop     dword ptr [rax+rax+00h]
0x18002cebc  mov     r15d, 1
0x18002cec2  lea     rcx, [rbp+3Fh+var_A0]
0x18002cec6  mov     rdx, rdi
0x18002cec9  mov     qword ptr [rsp+130h+var_C8], r15
0x18002cece  call    ORInitUnicodeStringEx
0x18002ced3  xor     r10d, r10d
0x18002ced6  mov     ebx, eax
0x18002ced8  test    eax, eax
0x18002ceda  jnz     loc_18002D3E6
0x18002cee0  movzx   ecx, word ptr [rbp+3Fh+var_A0]
0x18002cee4  lea     r8d, [r15+5Bh]
0x18002cee8  test    cx, cx
0x18002ceeb  jz      short loc_18002CF0D
0x18002ceed  mov     rdx, qword ptr [rbp+3Fh+var_A0+8]
0x18002cef1  movzx   eax, cx
0x18002cef4  shr     rax, 1
0x18002cef7  cmp     [rdx+rax*2-2], r8w
0x18002cefd  jnz     short loc_18002CF09
0x18002ceff  mov     eax, 0FFFEh
0x18002cf04  add     cx, ax
0x18002cf07  jnz     short loc_18002CEF1
0x18002cf09  mov     word ptr [rbp+3Fh+var_A0], cx
0x18002cf0d  cmp     [rsi+1Eh], r10w
0x18002cf12  jz      short loc_18002CF1B
0x18002cf14  mov     ebx, 3FAh
0x18002cf19  jmp     short loc_18002CEA1
0x18002cf1b  test    cx, cx
0x18002cf1e  jz      loc_18002CE9C
0x18002cf24  lea     r9, [rsp+130h+var_C0]
0x18002cf29  mov     rdx, rsi
0x18002cf2c  lea     r8, [rsp+130h+var_D8]
0x18002cf31  lea     rcx, [rbp+3Fh+var_A0]
0x18002cf35  call    ORParseSubKey
0x18002cf3a  xor     r10d, r10d
0x18002cf3d  mov     ebx, eax
0x18002cf3f  test    eax, eax
0x18002cf41  jnz     loc_18002D3E6
0x18002cf47  cmp     [rsp+130h+var_D8], 2
0x18002cf4c  jnz     short loc_18002CFAD
0x18002cf4e  mov     rcx, [rsp+130h+var_C0]
0x18002cf53  test    r14d, r14d
0x18002cf56  jz      short loc_18002CF6E
0x18002cf58  mov     rax, [rcx+28h]
0x18002cf5c  lea     r12d, [rbx+10h]
0x18002cf60  test    [rax+2], r12b
0x18002cf64  jz      loc_18002CE9C
0x18002cf6a  mov     r12, [rbp+3Fh+arg_28]
0x18002cf6e  cmp     rcx, [r13+38h]
0x18002cf72  jz      loc_18002CE9C
0x18002cf78  mov     edx, [rcx+18h]
0x18002cf7b  or      eax, 0FFFFFFFFh
0x18002cf7e  cmp     edx, eax
0x18002cf80  jnz     short loc_18002CF8C
0x18002cf82  mov     ebx, 5AAh
0x18002cf87  jmp     loc_18002CEA1
0x18002cf8c  lea     eax, [rdx+1]
0x18002cf8f  mov     [rcx+18h], eax
0x18002cf92  mov     rax, [rbp+3Fh+arg_30]
0x18002cf96  test    rax, rax
0x18002cf99  jz      short loc_18002CFA1
0x18002cf9b  mov     dword ptr [rax], 2
0x18002cfa1  mov     [r12], rcx
0x18002cfa5  mov     ebx, r10d
0x18002cfa8  jmp     loc_18002CEA1
0x18002cfad  mov     r13, [rsp+130h+var_C0]
0x18002cfb2  mov     r12d, 10h
0x18002cfb8  mov     rax, [r13+28h]
0x18002cfbc  test    [rax+2], r12b
0x18002cfc0  jz      short loc_18002CFCC
0x18002cfc2  mov     ebx, 5
0x18002cfc7  jmp     loc_18002D3E6
0x18002cfcc  mov     al, [rax+0Dh]
0x18002cfcf  and     al, 3
0x18002cfd1  cmp     al, r15b
0x18002cfd4  jz      short loc_18002CFC2
0x18002cfd6  mov     eax, 1FEh
0x18002cfdb  cmp     [r13+20h], ax
0x18002cfe0  jnz     short loc_18002CFEC
0x18002cfe2  mov     ebx, 57h ; 'W'
0x18002cfe7  jmp     loc_18002D3E6
0x18002cfec  mov     rdx, r10
0x18002cfef  mov     rax, rdi
0x18002cff2  add     rax, 2
0x18002cff6  movzx   ecx, word ptr [rax]
0x18002cff9  test    cx, cx
0x18002cffc  jnz     short loc_18002CFF2
0x18002cffe  mov     r8d, 5Ch ; '\'
0x18002d004  cmp     rax, rdi
0x18002d007  jbe     short loc_18002D018
0x18002d009  sub     rax, 2
0x18002d00d  movzx   ecx, word ptr [rax]
0x18002d010  cmp     cx, r8w
0x18002d014  jnz     short loc_18002D01E
0x18002d016  jmp     short loc_18002D004
0x18002d018  cmp     cx, r8w
0x18002d01c  jz      short loc_18002D031
0x18002d01e  cmp     rax, rdi
0x18002d021  jz      short loc_18002D031
0x18002d023  sub     rax, 2
0x18002d027  add     rdx, 2
0x18002d02b  cmp     [rax], r8w
0x18002d02f  jnz     short loc_18002D01E
0x18002d031  cmp     r8w, [rax]
0x18002d035  lea     rsi, [rax+2]
0x18002d039  lea     rbx, [rdx+2]
0x18002d03d  cmovnz  rsi, rax
0x18002d041  cmp     rsi, rdi
0x18002d044  cmovnz  rbx, rdx
0x18002d048  cmp     rbx, 200h
0x18002d04f  ja      short loc_18002CFE2
0x18002d051  xor     edx, edx; Val
0x18002d053  lea     rcx, [rbp+3Fh+var_80]; void *
0x18002d057  lea     r8d, [rdx+50h]; Size
0x18002d05b  call    memset_0
0x18002d060  xor     edi, edi
0x18002d062  mov     eax, 6B6Eh
0x18002d067  mov     word ptr [rbp+3Fh+var_80], ax
0x18002d06b  test    r14d, r14d
0x18002d06e  jz      short loc_18002D076
0x18002d070  movzx   r14d, r12w
0x18002d074  jmp     short loc_18002D079
0x18002d076  mov     r14d, edi
0x18002d079  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002d07e  call    cs:__imp_GetSystemTimeAsFileTime
0x18002d085  nop     dword ptr [rax+rax+00h]
0x18002d08a  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18002d08e  lea     rdx, [rbp+3Fh+var_90]
0x18002d092  mov     r10, [rsp+130h+var_E0]
0x18002d097  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x18002d09a  mov     eax, [rsp+130h+SystemTimeAsFileTime.dwHighDateTime]
0x18002d09e  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x18002d0a1  or      eax, 0FFFFFFFFh
0x18002d0a4  mov     dword ptr [rbp+3Fh+var_70], eax
0x18002d0a7  mov     dword ptr [rbp+3Fh+var_70+0Ch], eax
0x18002d0aa  mov     dword ptr [rbp+3Fh+var_60], eax
0x18002d0ad  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x18002d0b0  mov     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x18002d0b3  mov     dword ptr [rbp+3Fh+var_50], eax
0x18002d0b6  mov     eax, edi
0x18002d0b8  mov     [rbp+3Fh+arg_0], eax
0x18002d0bb  mov     [rbp+3Fh+var_36], ax
0x18002d0bf  mov     rax, [r10+10h]
0x18002d0c3  mov     rcx, rax
0x18002d0c6  mov     byte ptr [rbp+3Fh+var_80+0Ch], dil
0x18002d0ca  mov     qword ptr [rbp+3Fh+var_70+4], rdi
0x18002d0ce  mov     dword ptr [rbp+3Fh+var_60+4], edi
0x18002d0d1  mov     qword ptr [rbp+3Fh+var_50+4], rdi
0x18002d0d5  mov     qword ptr [rbp+3Fh+var_50+0Ch], rdi
0x18002d0d9  mov     qword ptr [rbp+3Fh+var_90+8], rsi
0x18002d0dd  mov     word ptr [rbp+3Fh+var_90], bx
0x18002d0e1  mov     [rsp+130h+var_C0], rax
0x18002d0e6  mov     word ptr [rbp+3Fh+var_90+2], bx
0x18002d0ea  call    ORGetCompressedLength
0x18002d0ef  movzx   esi, ax
0x18002d0f2  mov     [rbp+3Fh+var_38], si
0x18002d0f6  cmp     rsi, rbx
0x18002d0f9  jnb     short loc_18002D102
0x18002d0fb  or      r14w, 20h
0x18002d100  jmp     short loc_18002D10B
0x18002d102  mov     eax, 0FFDFh
0x18002d107  and     r14w, ax
0x18002d10b  mov     rdx, r13
0x18002d10e  mov     word ptr [rbp+3Fh+var_80+2], r14w
0x18002d113  mov     rcx, r10
0x18002d116  call    ORAllocNode
0x18002d11b  xor     r10d, r10d
0x18002d11e  mov     rdi, rax
0x18002d121  test    rax, rax
0x18002d124  jnz     short loc_18002D12E
0x18002d126  lea     ebx, [rax+8]
0x18002d129  jmp     loc_18002D3E6
0x18002d12e  mov     rbx, [rbp+3Fh+pSecurityDescriptor]
0x18002d132  mov     r15, r10
0x18002d135  test    rbx, rbx
0x18002d138  jz      short loc_18002D16D
0x18002d13a  mov     rcx, rbx; pSecurityDescriptor
0x18002d13d  call    cs:__imp_IsValidSecurityDescriptor
0x18002d144  nop     dword ptr [rax+rax+00h]
0x18002d149  test    eax, eax
0x18002d14b  jnz     short loc_18002D157
0x18002d14d  mov     ebx, 53Ah
0x18002d152  jmp     loc_18002D3B7
0x18002d157  lea     rdx, [rbp+3Fh+CreatorDescriptor]
0x18002d15b  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18002d15e  call    ORMakeSDRelative
0x18002d163  mov     ebx, eax
0x18002d165  test    eax, eax
0x18002d167  jnz     loc_18002D3B7
0x18002d16d  mov     rax, [r13+60h]
0x18002d171  xor     ebx, ebx
0x18002d173  mov     rdx, [rbp+3Fh+CreatorDescriptor]; CreatorDescriptor
0x18002d177  mov     r10, [rax+10h]
0x18002d17b  test    rdx, rdx
0x18002d17e  jz      short loc_18002D18D
0x18002d180  test    byte ptr [rdx+2], 4
0x18002d184  jz      short loc_18002D18D
0x18002d186  mov     eax, 1078h
0x18002d18b  jmp     short loc_18002D1A4
0x18002d18d  movzx   eax, word ptr [r10+16h]
0x18002d192  and     eax, 400h
0x18002d197  or      eax, 41E000h
0x18002d19c  shr     eax, 0Ah
0x18002d19f  test    rdx, rdx
0x18002d1a2  jz      short loc_18002D1AA
0x18002d1a4  test    [rdx+2], r12b
0x18002d1a8  jnz     short loc_18002D1B9
0x18002d1aa  mov     ecx, 800h
0x18002d1af  test    [r10+16h], cx
0x18002d1b4  jz      short loc_18002D1B9
0x18002d1b6  or      eax, 2
0x18002d1b9  lea     rcx, CmKeyMapping
0x18002d1c0  xor     r9d, r9d; ObjectTypes
0x18002d1c3  mov     [rsp+130h+GenericMapping], rcx; GenericMapping
0x18002d1c8  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x18002d1cc  mov     [rsp+130h+Token], rbx; Token
0x18002d1d1  lea     rcx, [r10+14h]; ParentDescriptor
0x18002d1d5  mov     [rsp+130h+AutoInheritFlags], eax; AutoInheritFlags
0x18002d1d9  mov     rax, qword ptr [rsp+130h+var_C8]
0x18002d1de  mov     [rsp+130h+IsContainerObject], eax; IsContainerObject
0x18002d1e2  mov     [rsp+130h+GuidCount], ebx; GuidCount
0x18002d1e6  call    cs:__imp_CreatePrivateObjectSecurityWithMultipleInheritance
0x18002d1ed  nop     dword ptr [rax+rax+00h]
0x18002d1f2  test    eax, eax
0x18002d1f4  jnz     short loc_18002D20C
0x18002d1f6  call    cs:__imp_GetLastError
0x18002d1fd  nop     dword ptr [rax+rax+00h]
0x18002d202  mov     ebx, eax
0x18002d204  test    eax, eax
0x18002d206  jnz     loc_18002D3B7
0x18002d20c  mov     rdx, [rbp+3Fh+NewDescriptor]
0x18002d210  lea     r8, [rbp+3Fh+var_A8]
0x18002d214  mov     rcx, [rsp+130h+var_E0]
0x18002d219  call    ORProcessSecurityDescriptor
0x18002d21e  mov     ebx, eax
0x18002d220  test    eax, eax
0x18002d222  jnz     loc_18002D3B7
0x18002d228  mov     rax, [rbp+3Fh+var_A8]
0x18002d22c  xor     ebx, ebx
0x18002d22e  mov     [rdi+60h], rax
0x18002d232  mov     rcx, [rax+10h]
0x18002d236  mov     rax, qword ptr [rsp+130h+var_C8]
0x18002d23b  add     [rcx+0Ch], eax
0x18002d23e  mov     rcx, [rbp+3Fh+Src]
0x18002d242  test    rcx, rcx
0x18002d245  jz      short loc_18002D297
0x18002d247  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d24b  inc     rax
0x18002d24e  cmp     [rcx+rax*2], bx
0x18002d252  jnz     short loc_18002D24B
0x18002d254  add     rax, rax
0x18002d257  cmp     rax, 0FFFFh
  ... truncated ...
```
