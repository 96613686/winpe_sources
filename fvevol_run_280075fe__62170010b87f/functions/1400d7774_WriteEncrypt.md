# WriteEncrypt

- ea: `0x1400d7774`
- end: `0x1400d7f7b`
- name: `WriteEncrypt`
- size: `2055`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400d6ba0`

## callees

- `0x140001700`
- `0x140008288`
- `0x14000943c`
- `0x140009910`
- `0x140009bf4`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x14009c16c`
- `0x1400d7774`
- `0x1400d7f90`
- `0x1400d8070`
- `0x1400d81d4`
- `0x1400d8584`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400d7c6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400d7c6f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d7dd4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d7f6a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d7dd4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d7f6a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d7b1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d7b1a`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d7bca`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d7ce5`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d7bca`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d7ce5`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d7c91`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d7c91`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7dc1`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7f57`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7dc1`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7f57`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d7c04`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d7c04`
- `ntoskrnl!KeBugCheckEx` at `0x1400d77eb`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7b96`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7cc7`
- `ntoskrnl!KeBugCheckEx` at `0x1400d77eb`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7b96`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7cc7`

## string_xrefs

- `0x1400d7ada`: `Filter write subrequest`

## pseudocode

```c
__int64 __fastcall WriteEncrypt(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)
{
  ULONG_PTR v4; // rsi
  __int64 v5; // r13
  __int64 v6; // r14
  char v7; // r8
  int v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned __int8 *v11; // r15
  char v12; // cl
  unsigned __int8 *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // rbx
  char v17; // dl
  _BOOL8 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // ecx
  _QWORD *v33; // rax
  int v34; // edx
  __int64 v35; // rax
  char v36; // [rsp+60h] [rbp-A0h]
  bool v37; // [rsp+61h] [rbp-9Fh]
  bool v38; // [rsp+61h] [rbp-9Fh]
  char v39; // [rsp+62h] [rbp-9Eh]
  char v40; // [rsp+63h] [rbp-9Dh]
  bool v41; // [rsp+64h] [rbp-9Ch]
  __int64 v42; // [rsp+68h] [rbp-98h]
  int v43; // [rsp+70h] [rbp-90h]
  __int64 v44[32]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v45; // [rsp+180h] [rbp+80h] BYREF
  __int128 v46; // [rsp+190h] [rbp+90h]

  v45 = 0;
  v46 = 0;
  memset(v44, 0, sizeof(v44));
  v4 = *(_QWORD *)(BugCheckParameter2 + 24);
  if ( *(_QWORD *)(v4 + 32) != BugCheckParameter2
    || (v5 = *(_QWORD *)(v4 + 16), v6 = *(_QWORD *)(v5 + 48), BugCheckParameter3 != *(_QWORD *)(v6 + 8))
    || (v7 = *(_BYTE *)(v4 + 136), v4 != v5 + 176LL * (v7 & 0x3F) + 296) )
  {
    KeBugCheckEx(0x120u, 9u, BugCheckParameter2, BugCheckParameter3, *(_QWORD *)(BugCheckParameter2 + 24));
  }
  v43 = *(_DWORD *)(BugCheckParameter2 + 32);
  *(_BYTE *)(v4 + 144) = (*(_BYTE *)(v4 + 144)
                        ^ (*(_BYTE *)(BugCheckParameter2 + 96)
                         ^ *(_BYTE *)(v4 + 144))
                        & 1)
                       & 0xFD;
  if ( (v7 & 0x40) == 0 )
    return WriteIssueDirect(v4);
  v8 = *(_DWORD *)(v6 + 808);
  v9 = *(_QWORD *)(v4 + 40);
  v42 = v9;
  v37 = (v8 & 0x17F) != 0;
  if ( *(_DWORD *)(v6 + 4LL * *(unsigned int *)(BugCheckParameter3 + 884) + 1712) || (v36 = 0, !*(_BYTE *)(v5 + 272)) )
    v36 = 1;
  v10 = *(_QWORD *)(v9 + 8);
  if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
    v11 = *(unsigned __int8 **)(v10 + 24);
  else
    v11 = (unsigned __int8 *)MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
  if ( v11 )
  {
    v39 = 0;
  }
  else
  {
    ExAcquireFastMutex((PFAST_MUTEX)(v6 + 2120));
    v39 = 1;
    v11 = (unsigned __int8 *)MmMapLockedPagesWithReservedMapping(
                               *(PVOID *)(v6 + 2104),
                               0x72455646u,
                               *(PMDL *)(v9 + 8),
                               MmCached);
    if ( !v11 )
      KeBugCheckEx(0x120u, 1u, 0, 0, 0);
  }
  v40 = 1;
  v41 = (v8 & 0x40) == 0;
  if ( !*(_QWORD *)v4
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDDDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v11[6],
      v11[5],
      *v11,
      v11[1],
      v11[2],
      v11[3],
      v11[4],
      v11[5],
      v11[6],
      v11[7]);
  }
  v12 = v36;
  v13 = (unsigned __int8 *)(*(_QWORD *)(v4 + 96) & 0xFFFFFFFFFFFFFFFCuLL);
  if ( v36 )
  {
    memmove((void *)(*(_QWORD *)(v4 + 96) & 0xFFFFFFFFFFFFFFFCuLL), v11, *(unsigned int *)(v4 + 124));
    v14 = v42;
    if ( v39 )
    {
      MmUnmapReservedMapping(*(PVOID *)(v6 + 2104), 0x72455646u, *(PMDL *)(v42 + 8));
      ExReleaseFastMutex((PFAST_MUTEX)(v6 + 2120));
    }
    v29 = *(_QWORD *)(v42 + 8);
    if ( (*(_BYTE *)(v29 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v29 + 24), *(PMDL *)(v42 + 8));
    v12 = v36;
    v40 = 0;
  }
  else
  {
    v14 = v42;
  }
  if ( (*(_DWORD *)(v6 + 808) & 0xC000) == 0 || *(_BYTE *)(v5 + 276) )
  {
    v15 = *(_QWORD *)(v5 + 280);
    v16 = -1;
    v17 = *(_BYTE *)(v5 + 276);
    v18 = v15 != -1;
    if ( (v17 != 0) != v18 )
      goto LABEL_45;
    LOBYTE(v18) = v41 && v37;
    v38 = v41 && v37;
    if ( v17 )
      v16 = *(_QWORD *)v4 + v15 - *(_QWORD *)(v5 + 64);
    *(_QWORD *)(v4 + 56) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)(v4 + 88) = *(_DWORD *)(v4 + 124);
    if ( v18 )
    {
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v18)
        && (*(_BYTE *)(v6 + 4403) & 8) != 0
        || (v30 = *(_QWORD *)(v6 + 976), *(_WORD *)(v30 + 10) == 1) )
      {
        v28 = 0;
      }
      else
      {
        v28 = *(unsigned int *)(v30 + 28);
        if ( !(_DWORD)v28 )
          v28 = 1;
      }
      LOBYTE(v19) = *(_QWORD *)v4 < v28 * (unsigned __int64)*(unsigned int *)(v6 + 1308);
    }
    else
    {
      v19 = 0;
    }
    InitializeFilterData(v6, v44, v19, v16, *(_QWORD *)(v5 + 288), 0);
    v44[2] = *(_QWORD *)(v4 + 8);
    if ( v36 )
      v11 = v13;
    LODWORD(v44[14]) = *(_DWORD *)(v4 + 124);
    v44[11] = (__int64)FveFilteredWrite;
    v44[12] = (__int64)v11;
    v44[13] = (__int64)v13;
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v20) )
      v21 = LODWORD(v44[15]) | 3;
    else
      v21 = 3;
    LODWORD(v44[15]) = v21;
    if ( !v38 || (*(_DWORD *)(v6 + 808) & 0xC000) != 0 || *(char *)(v4 + 136) < 0 )
    {
      if ( !*(_BYTE *)(v5 + 276) )
        goto LABEL_45;
      v21 |= 0x1000u;
      LODWORD(v44[15]) = v21;
    }
    v22 = *(unsigned int *)(BugCheckParameter3 + 884);
    if ( *(_BYTE *)(v22 + BugCheckParameter3 + 1293) || *(_BYTE *)(v22 + v6 + 1949) )
    {
      v21 |= 0x100u;
      v44[15] = __PAIR64__(*(_DWORD *)(v6 + 4 * v22 + 1724), v21);
    }
    if ( *(_BYTE *)(v22 + BugCheckParameter3 + 1296) || *(_BYTE *)(v22 + v6 + 1952) )
    {
      v31 = *(_DWORD *)(v6 + 4 * v22 + 1736);
      v21 |= 0x200u;
      LODWORD(v44[15]) = v21;
      LODWORD(v44[16]) = v31;
    }
    if ( *(_BYTE *)(v22 + BugCheckParameter3 + 1417) )
    {
      v32 = *(_DWORD *)(BugCheckParameter3 + 4 * v22 + 1396);
      v21 |= 0x400u;
      LODWORD(v44[15]) = v21;
      HIDWORD(v44[16]) = v32;
    }
    v44[18] = v6;
    v44[19] = (__int64)FveDeviceFastAlloc;
    v44[20] = (__int64)FveDeviceFastFree;
    if ( v43 )
    {
      v21 |= 0x80u;
      LODWORD(v44[15]) = v21;
    }
    if ( (*(_DWORD *)(v6 + 808) & 0x100) != 0 )
    {
      v33 = *(_QWORD **)(v6 + 736);
      if ( v33 )
      {
        if ( *v33 )
        {
          v44[9] = *(_QWORD *)(v6 + 736);
          v34 = v21 | 8;
          v44[10] = *(_QWORD *)(v4 + 24);
          LODWORD(v44[15]) = v34;
          if ( (*(_BYTE *)(**(_QWORD **)(v6 + 736) + 48LL) & 1) != 0 )
            LODWORD(v44[15]) = v34 | 0x30;
        }
      }
    }
    v14 = v42;
    FvePerfTraceDevIoCrypto(v6, FVE_PERF_IO_ENCRYPT_START, v42, v44[2], v44[14]);
    v23 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 192LL);
    if ( v23 )
      v24 = FveTestRwParseBlockAndFilter(v44, v23, &v45);
    else
      v24 = FveParseBlockAndFilterEx(v44, &v45);
    *(_DWORD *)(v4 + 128) = v24;
    FvePerfTraceDevIoCrypto(v6, FVE_PERF_IO_ENCRYPT_STOP, v42, v44[2], v44[14]);
    LogFilterTrace(
      (unsigned int)"Filter write subrequest",
      (unsigned int)&v45,
      *(_DWORD *)(v4 + 128),
      v6,
      v44[2],
      v44[14]);
    if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v25)
      || (v35 = *(_QWORD *)(v6 + 4736)) == 0
      || !*(_DWORD *)(v35 + 88)
      || *(_DWORD *)(v4 + 128) != -1073741662 && DWORD2(v46) != 259 )
    {
      if ( v44[7] )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v6 + 8) + 9024LL), (PVOID)v44[7]);
      memset(v44, 0, sizeof(v44));
      *(_QWORD *)(v4 + 64) = MEMORY[0xFFFFF78000000008];
      goto LABEL_43;
    }
LABEL_45:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  if ( *(char *)(v4 + 136) < 0 )
    goto LABEL_45;
  *(_DWORD *)(v4 + 128) = 0;
  if ( !v12 )
    memmove(v13, v11, *(unsigned int *)(v4 + 124));
LABEL_43:
  if ( v40 )
  {
    if ( v39 )
    {
      MmUnmapReservedMapping(*(PVOID *)(v6 + 2104), 0x72455646u, *(PMDL *)(v14 + 8));
      ExReleaseFastMutex((PFAST_MUTEX)(v6 + 2120));
    }
    v27 = *(_QWORD *)(v14 + 8);
    if ( (*(_BYTE *)(v27 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v27 + 24), *(PMDL *)(v14 + 8));
  }
  return WriteIssue(v4);
}

```

## disassembly

```asm
0x1400d7774  mov     [rsp-8+arg_10], rbx
0x1400d7779  push    rbp
0x1400d777a  push    rsi
0x1400d777b  push    rdi
0x1400d777c  push    r12
0x1400d777e  push    r13
0x1400d7780  push    r14
0x1400d7782  push    r15
0x1400d7784  lea     rbp, [rsp-0B0h]
0x1400d778c  sub     rsp, 1B0h
0x1400d7793  mov     rax, cs:__security_cookie
0x1400d779a  xor     rax, rsp
0x1400d779d  mov     [rbp+0E0h+var_40], rax
0x1400d77a4  xorps   xmm0, xmm0
0x1400d77a7  mov     rbx, rdx
0x1400d77aa  mov     r12, rcx
0x1400d77ad  xor     edx, edx; Val
0x1400d77af  lea     rcx, [rbp+0E0h+var_160]; void *
0x1400d77b3  mov     r8d, 100h; Size
0x1400d77b9  movups  [rbp+0E0h+var_60], xmm0
0x1400d77c0  movups  [rbp+0E0h+var_50], xmm0
0x1400d77c7  call    memset
0x1400d77cc  mov     rsi, [rbx+18h]
0x1400d77d0  cmp     [rsi+20h], rbx
0x1400d77d4  jz      short loc_1400D77F8
0x1400d77d6  mov     r9, r12; BugCheckParameter3
0x1400d77d9  mov     [rsp+1E0h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400d77de  mov     r8, rbx; BugCheckParameter2
0x1400d77e1  mov     edx, 9; BugCheckParameter1
0x1400d77e6  mov     ecx, 120h; BugCheckCode
0x1400d77eb  call    cs:__imp_KeBugCheckEx
0x1400d77f8  mov     r13, [rsi+10h]
0x1400d77fc  mov     r14, [r13+30h]
0x1400d7800  cmp     r12, [r14+8]
0x1400d7804  jnz     short loc_1400D77D6
0x1400d7806  movzx   r8d, byte ptr [rsi+88h]
0x1400d780e  mov     eax, r8d
0x1400d7811  and     eax, 3Fh
0x1400d7814  imul    rcx, rax, 0B0h
0x1400d781b  add     rcx, 128h
0x1400d7822  add     rcx, r13
0x1400d7825  cmp     rsi, rcx
0x1400d7828  jnz     short loc_1400D77D6
0x1400d782a  mov     eax, [rbx+20h]
0x1400d782d  mov     r10d, 1
0x1400d7833  mov     [rsp+1E0h+var_170], eax
0x1400d7837  mov     al, [rsi+90h]
0x1400d783d  mov     dl, al
0x1400d783f  xor     dl, [rbx+60h]
0x1400d7842  and     dl, r10b
0x1400d7845  xor     dl, al
0x1400d7847  and     dl, 0FDh
0x1400d784a  mov     [rsi+90h], dl
0x1400d7850  test    r8b, 40h
0x1400d7854  jz      loc_1400D7D02
0x1400d785a  mov     ebx, [r14+328h]
0x1400d7861  test    ebx, 17Fh
0x1400d7867  mov     rdi, [rsi+28h]
0x1400d786b  setnz   al
0x1400d786e  mov     [rsp+1E0h+var_178], rdi
0x1400d7873  mov     [rsp+1E0h+var_17F], al
0x1400d7877  xor     r9d, r9d; RequestedAddress
0x1400d787a  mov     eax, [r12+374h]
0x1400d7882  cmp     [r14+rax*4+6B0h], r9d
0x1400d788a  jz      loc_1400D7BDB
0x1400d7890  mov     [rsp+1E0h+var_180], r10b
0x1400d7895  mov     rcx, [rdi+8]; MemoryDescriptorList
0x1400d7899  test    byte ptr [rcx+0Ah], 5
0x1400d789d  jz      loc_1400D7BF2
0x1400d78a3  mov     r15, [rcx+18h]
0x1400d78a7  test    r15, r15
0x1400d78aa  jz      loc_1400D7C68
0x1400d78b0  mov     [rsp+1E0h+var_17E], r9b
0x1400d78b5  test    bl, 40h
0x1400d78b8  mov     [rsp+1E0h+var_17D], r10b
0x1400d78bd  setz    [rsp+1E0h+var_17C]
0x1400d78c2  cmp     [rsi], r9
0x1400d78c5  jz      loc_1400D7D0F
0x1400d78cb  mov     rdi, [rsi+60h]
0x1400d78cf  mov     cl, [rsp+1E0h+var_180]
0x1400d78d3  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400d78d7  test    cl, cl
0x1400d78d9  jnz     loc_1400D7D92
0x1400d78df  mov     rbx, [rsp+1E0h+var_178]
0x1400d78e4  test    dword ptr [r14+328h], 0C000h
0x1400d78ef  jnz     loc_1400D7DE5
0x1400d78f5  mov     r8, [r13+118h]
0x1400d78fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400d7900  mov     dl, [r13+114h]
0x1400d7907  cmp     r8, rbx
0x1400d790a  mov     ecx, r9d
0x1400d790d  mov     eax, r9d
0x1400d7910  setnz   cl
0x1400d7913  test    dl, dl
0x1400d7915  setnz   al
0x1400d7918  cmp     eax, ecx
0x1400d791a  jnz     loc_1400D7B82
0x1400d7920  mov     cl, [rsp+1E0h+var_17F]
0x1400d7924  and     cl, [rsp+1E0h+var_17C]
0x1400d7928  mov     [rsp+1E0h+var_17F], cl
0x1400d792c  test    dl, dl
0x1400d792e  jnz     loc_1400D7E22
0x1400d7934  mov     rax, ds:0FFFFF78000000008h
0x1400d793e  mov     [rsi+38h], rax
0x1400d7942  mov     eax, [rsi+7Ch]
0x1400d7945  mov     [rsi+58h], eax
0x1400d7948  test    cl, cl
0x1400d794a  jnz     loc_1400D7C1F
0x1400d7950  mov     r8d, r9d
0x1400d7953  mov     rax, [r13+120h]
0x1400d795a  lea     rdx, [rbp+0E0h+var_160]
0x1400d795e  mov     qword ptr [rsp+1E0h+Priority], r9
0x1400d7963  mov     rcx, r14
0x1400d7966  mov     r9, rbx
0x1400d7969  mov     [rsp+1E0h+BugCheckParameter4], rax
0x1400d796e  call    InitializeFilterData
0x1400d7973  mov     rax, [rsi+8]
0x1400d7977  cmp     [rsp+1E0h+var_180], 0
0x1400d797c  mov     [rbp+0E0h+var_150], rax
0x1400d7980  mov     eax, [rsi+7Ch]
0x1400d7983  cmovnz  r15, rdi
0x1400d7987  mov     [rbp+0E0h+var_F0], eax
0x1400d798a  lea     rax, FveFilteredWrite
0x1400d7991  mov     [rbp+0E0h+var_108], rax
0x1400d7995  mov     [rbp+0E0h+var_100], r15
0x1400d7999  mov     [rbp+0E0h+var_F8], rdi
0x1400d799d  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d79a2  xor     r9d, r9d
0x1400d79a5  test    eax, eax
0x1400d79a7  jnz     loc_1400D7BA3
0x1400d79ad  lea     edx, [rax+3]
0x1400d79b0  mov     [rbp+0E0h+var_E8], edx
0x1400d79b3  cmp     [rsp+1E0h+var_17F], r9b
0x1400d79b8  jz      loc_1400D7E54
0x1400d79be  test    dword ptr [r14+328h], 0C000h
0x1400d79c9  jnz     loc_1400D7E54
0x1400d79cf  cmp     [rsi+88h], r9b
0x1400d79d6  jl      loc_1400D7E54
0x1400d79dc  mov     ecx, [r12+374h]
0x1400d79e4  cmp     [rcx+r12+50Dh], r9b
0x1400d79ec  jnz     loc_1400D7E6D
0x1400d79f2  cmp     [rcx+r14+79Dh], r9b
0x1400d79fa  jnz     loc_1400D7E6D
0x1400d7a00  cmp     [rcx+r12+510h], r9b
0x1400d7a08  jnz     loc_1400D7E84
0x1400d7a0e  cmp     [rcx+r14+7A0h], r9b
0x1400d7a16  jnz     loc_1400D7E84
0x1400d7a1c  cmp     [rcx+r12+589h], r9b
0x1400d7a24  jnz     loc_1400D7E9B
0x1400d7a2a  lea     rax, FveDeviceFastAlloc
0x1400d7a31  mov     [rbp+0E0h+var_D0], r14
0x1400d7a35  mov     [rbp+0E0h+var_C8], rax
0x1400d7a39  lea     rax, FveDeviceFastFree
0x1400d7a40  mov     [rbp+0E0h+var_C0], rax
0x1400d7a44  cmp     [rsp+1E0h+var_170], r9d
0x1400d7a49  jnz     loc_1400D7EB2
0x1400d7a4f  test    dword ptr [r14+328h], 100h
0x1400d7a5a  jnz     loc_1400D7EBE
0x1400d7a60  mov     eax, [rbp+0E0h+var_F0]
0x1400d7a63  lea     rdx, FVE_PERF_IO_ENCRYPT_START
0x1400d7a6a  mov     rbx, [rsp+1E0h+var_178]
0x1400d7a6f  mov     rcx, r14
0x1400d7a72  mov     r9, [rbp+0E0h+var_150]
0x1400d7a76  mov     r8, rbx
0x1400d7a79  mov     dword ptr [rsp+1E0h+BugCheckParameter4], eax
0x1400d7a7d  call    FvePerfTraceDevIoCrypto
0x1400d7a82  mov     rax, [rsi+10h]
0x1400d7a86  lea     rcx, [rbp+0E0h+var_160]
0x1400d7a8a  mov     rdx, [rax+0C0h]
0x1400d7a91  test    rdx, rdx
0x1400d7a94  jnz     loc_1400D7C57
0x1400d7a9a  lea     rdx, [rbp+0E0h+var_60]
0x1400d7aa1  call    FveParseBlockAndFilterEx
0x1400d7aa6  mov     [rsi+80h], eax
0x1400d7aac  lea     rdx, FVE_PERF_IO_ENCRYPT_STOP
0x1400d7ab3  mov     eax, [rbp+0E0h+var_F0]
0x1400d7ab6  mov     r8, rbx
0x1400d7ab9  mov     r9, [rbp+0E0h+var_150]
0x1400d7abd  mov     rcx, r14
0x1400d7ac0  mov     dword ptr [rsp+1E0h+BugCheckParameter4], eax
0x1400d7ac4  call    FvePerfTraceDevIoCrypto
0x1400d7ac9  mov     eax, [rbp+0E0h+var_F0]
0x1400d7acc  lea     rdx, [rbp+0E0h+var_60]
0x1400d7ad3  mov     r8d, [rsi+80h]
0x1400d7ada  lea     rcx, aFilterWriteSub; "Filter write subrequest"
0x1400d7ae1  mov     [rsp+1E0h+Priority], eax
0x1400d7ae5  mov     r9, r14
0x1400d7ae8  mov     rax, [rbp+0E0h+var_150]
0x1400d7aec  mov     [rsp+1E0h+BugCheckParameter4], rax
0x1400d7af1  call    LogFilterTrace
0x1400d7af6  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d7afb  xor     r9d, r9d
0x1400d7afe  test    eax, eax
0x1400d7b00  jnz     loc_1400D7F08
0x1400d7b06  mov     rdx, [rbp+0E0h+Entry]; Entry
0x1400d7b0a  test    rdx, rdx
0x1400d7b0d  jz      short loc_1400D7B26
0x1400d7b0f  mov     rcx, [r14+8]
0x1400d7b13  mov     rcx, [rcx+2340h]; Lookaside
0x1400d7b1a  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d7b21  nop     dword ptr [rax+rax+00h]
0x1400d7b26  xor     edx, edx; Val
0x1400d7b28  lea     rcx, [rbp+0E0h+var_160]; void *
0x1400d7b2c  mov     r8d, 100h; Size
0x1400d7b32  call    memset
0x1400d7b37  mov     rax, ds:0FFFFF78000000008h
0x1400d7b41  mov     [rsi+40h], rax
0x1400d7b45  xor     r9d, r9d
0x1400d7b48  cmp     [rsp+1E0h+var_17D], r9b
0x1400d7b4d  jnz     short loc_1400D7BAE
0x1400d7b4f  mov     rcx, rsi; BugCheckParameter2
0x1400d7b52  call    WriteIssue
0x1400d7b57  mov     rcx, [rbp+0E0h+var_40]
0x1400d7b5e  xor     rcx, rsp; StackCookie
0x1400d7b61  call    __security_check_cookie
0x1400d7b66  mov     rbx, [rsp+1E0h+arg_10]
0x1400d7b6e  add     rsp, 1B0h
0x1400d7b75  pop     r15
0x1400d7b77  pop     r14
0x1400d7b79  pop     r13
0x1400d7b7b  pop     r12
0x1400d7b7d  pop     rdi
0x1400d7b7e  pop     rsi
0x1400d7b7f  pop     rbp
0x1400d7b80  retn
0x1400d7b82  mov     [rsp+1E0h+BugCheckParameter4], r9; BugCheckParameter4
0x1400d7b87  xor     r8d, r8d; BugCheckParameter2
0x1400d7b8a  xor     r9d, r9d; BugCheckParameter3
0x1400d7b8d  mov     ecx, 120h; BugCheckCode
0x1400d7b92  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d7b96  call    cs:__imp_KeBugCheckEx
0x1400d7ba3  mov     edx, [rbp+0E0h+var_E8]
0x1400d7ba6  or      edx, 3
0x1400d7ba9  jmp     loc_1400D79B0
0x1400d7bae  cmp     [rsp+1E0h+var_17E], r9b
0x1400d7bb3  jnz     loc_1400D7F47
0x1400d7bb9  mov     rcx, [rbx+8]
0x1400d7bbd  test    byte ptr [rcx+0Ah], 20h
0x1400d7bc1  jz      short loc_1400D7B4F
0x1400d7bc3  mov     rdx, rcx; MemoryDescriptorList
0x1400d7bc6  mov     rcx, [rcx+18h]; BaseAddress
0x1400d7bca  call    cs:__imp_MmUnmapLockedPages
0x1400d7bd1  nop     dword ptr [rax+rax+00h]
0x1400d7bd6  jmp     loc_1400D7B4F
0x1400d7bdb  mov     [rsp+1E0h+var_180], r9b
0x1400d7be0  cmp     [r13+110h], r9b
0x1400d7be7  jnz     loc_1400D7895
0x1400d7bed  jmp     loc_1400D7890
0x1400d7bf2  mov     [rsp+1E0h+Priority], 40000010h; Priority
0x1400d7bfa  mov     r8d, r10d; CacheType
0x1400d7bfd  xor     edx, edx; AccessMode
0x1400d7bff  mov     dword ptr [rsp+1E0h+BugCheckParameter4], r9d; BugCheckOnFailure
0x1400d7c04  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d7c0b  nop     dword ptr [rax+rax+00h]
0x1400d7c10  xor     r9d, r9d
0x1400d7c13  mov     r15, rax
0x1400d7c16  lea     r10d, [r9+1]
0x1400d7c1a  jmp     loc_1400D78A7
0x1400d7c1f  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d7c24  xor     r9d, r9d
0x1400d7c27  test    eax, eax
0x1400d7c29  jz      loc_1400D7E31
0x1400d7c2f  test    byte ptr [r14+1133h], 8
0x1400d7c37  jz      loc_1400D7E31
0x1400d7c3d  mov     eax, r9d
0x1400d7c40  mov     ecx, [r14+51Ch]
0x1400d7c47  imul    rcx, rax
0x1400d7c4b  cmp     [rsi], rcx
0x1400d7c4e  setb    r8b
0x1400d7c52  jmp     loc_1400D7953
0x1400d7c57  lea     r8, [rbp+0E0h+var_60]
0x1400d7c5e  call    FveTestRwParseBlockAndFilter
0x1400d7c63  jmp     loc_1400D7AA6
0x1400d7c68  lea     rcx, [r14+848h]; FastMutex
0x1400d7c6f  call    cs:__imp_ExAcquireFastMutex
0x1400d7c76  nop     dword ptr [rax+rax+00h]
0x1400d7c7b  mov     r8, [rdi+8]; MemoryDescriptorList
0x1400d7c7f  mov     r9d, 1; CacheType
0x1400d7c85  mov     rcx, [r14+838h]; MappingAddress
0x1400d7c8c  mov     edx, 72455646h; PoolTag
0x1400d7c91  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400d7c98  nop     dword ptr [rax+rax+00h]
0x1400d7c9d  xor     r9d, r9d; BugCheckParameter3
0x1400d7ca0  mov     r10d, 1
0x1400d7ca6  mov     [rsp+1E0h+var_17E], r10b
0x1400d7cab  mov     r15, rax
0x1400d7cae  test    rax, rax
0x1400d7cb1  jnz     loc_1400D78B5
0x1400d7cb7  xor     r8d, r8d; BugCheckParameter2
0x1400d7cba  mov     [rsp+1E0h+BugCheckParameter4], r9; BugCheckParameter4
0x1400d7cbf  mov     edx, r10d; BugCheckParameter1
0x1400d7cc2  mov     ecx, 120h; BugCheckCode
0x1400d7cc7  call    cs:__imp_KeBugCheckEx
0x1400d7cd4  mov     rcx, [rbx+8]
0x1400d7cd8  test    byte ptr [rcx+0Ah], 20h
0x1400d7cdc  jz      short loc_1400D7CF1
0x1400d7cde  mov     rdx, rcx; MemoryDescriptorList
0x1400d7ce1  mov     rcx, [rcx+18h]; BaseAddress
0x1400d7ce5  call    cs:__imp_MmUnmapLockedPages
0x1400d7cec  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
