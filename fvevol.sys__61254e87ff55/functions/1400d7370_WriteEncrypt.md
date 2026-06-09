# WriteEncrypt

- ea: `0x1400d7370`
- end: `0x1400d7b74`
- name: `WriteEncrypt`
- size: `2052`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400d67c0`

## callees

- `0x140001710`
- `0x140008348`
- `0x1400094fc`
- `0x1400099d0`
- `0x140009cb4`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x14009e16c`
- `0x1400d7370`
- `0x1400d7b80`
- `0x1400d7c60`
- `0x1400d7dc4`
- `0x1400d8170`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400d7868`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400d7868`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d79cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d7b63`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d79cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d7b63`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d7713`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d7713`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d77c3`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d78de`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d77c3`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d78de`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d788a`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d788a`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d79ba`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7b50`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d79ba`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7b50`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d77fd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d77fd`
- `ntoskrnl!KeBugCheckEx` at `0x1400d73e7`
- `ntoskrnl!KeBugCheckEx` at `0x1400d778f`
- `ntoskrnl!KeBugCheckEx` at `0x1400d78c0`
- `ntoskrnl!KeBugCheckEx` at `0x1400d73e7`
- `ntoskrnl!KeBugCheckEx` at `0x1400d778f`
- `ntoskrnl!KeBugCheckEx` at `0x1400d78c0`

## string_xrefs

- `0x1400d76d3`: `Filter write subrequest`

## pseudocode

```c
__int64 __fastcall WriteEncrypt(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)
{
  __int64 v4; // rdx
  ULONG_PTR v5; // rsi
  __int64 v6; // r13
  __int64 v7; // r14
  char v8; // cl
  int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rcx
  unsigned __int8 *v12; // r15
  char v13; // cl
  unsigned __int8 *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rbx
  _BOOL8 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // edx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  int v34; // ecx
  _QWORD *v35; // rax
  int v36; // edx
  __int64 v37; // rax
  char v38; // [rsp+60h] [rbp-A0h]
  bool v39; // [rsp+61h] [rbp-9Fh]
  bool v40; // [rsp+61h] [rbp-9Fh]
  char v41; // [rsp+62h] [rbp-9Eh]
  char v42; // [rsp+63h] [rbp-9Dh]
  bool v43; // [rsp+64h] [rbp-9Ch]
  __int64 v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+70h] [rbp-90h]
  __int64 v46[32]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v47; // [rsp+180h] [rbp+80h] BYREF
  __int128 v48; // [rsp+190h] [rbp+90h]

  v47 = 0;
  v48 = 0;
  memset(v46, 0, sizeof(v46));
  v5 = *(_QWORD *)(BugCheckParameter2 + 24);
  if ( *(_QWORD *)(v5 + 32) != BugCheckParameter2
    || (v6 = *(_QWORD *)(v5 + 16), v7 = *(_QWORD *)(v6 + 48), BugCheckParameter3 != *(_QWORD *)(v7 + 8))
    || (v8 = *(_BYTE *)(v5 + 136), v5 != v6 + 192LL * (v8 & 0x3F) + 312) )
  {
    KeBugCheckEx(0x120u, 9u, BugCheckParameter2, BugCheckParameter3, *(_QWORD *)(BugCheckParameter2 + 24));
  }
  v45 = *(_DWORD *)(BugCheckParameter2 + 32);
  *(_BYTE *)(v5 + 144) = (*(_BYTE *)(v5 + 144)
                        ^ (*(_BYTE *)(BugCheckParameter2 + 96)
                         ^ *(_BYTE *)(v5 + 144))
                        & 1)
                       & 0xFD;
  if ( (v8 & 0x40) == 0 )
    return WriteIssueDirect(v5);
  v9 = *(_DWORD *)(v7 + 808);
  v10 = *(_QWORD *)(v5 + 40);
  v44 = v10;
  v39 = (v9 & 0x17F) != 0;
  if ( *(_DWORD *)(v7 + 4LL * *(unsigned int *)(BugCheckParameter3 + 884) + 1712) || (v38 = 0, !*(_BYTE *)(v6 + 272)) )
    v38 = 1;
  v11 = *(_QWORD *)(v10 + 8);
  if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
    v12 = *(unsigned __int8 **)(v11 + 24);
  else
    v12 = (unsigned __int8 *)MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000010u);
  if ( v12 )
  {
    v41 = 0;
  }
  else
  {
    ExAcquireFastMutex((PFAST_MUTEX)(v7 + 2120));
    v41 = 1;
    v12 = (unsigned __int8 *)MmMapLockedPagesWithReservedMapping(
                               *(PVOID *)(v7 + 2104),
                               0x72455646u,
                               *(PMDL *)(v10 + 8),
                               MmCached);
    if ( !v12 )
      KeBugCheckEx(0x120u, 1u, 0, 0, 0);
  }
  v42 = 1;
  v43 = (v9 & 0x40) == 0;
  if ( !*(_QWORD *)v5
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDDDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v12[6],
      v12[5],
      *v12,
      v12[1],
      v12[2],
      v12[3],
      v12[4],
      v12[5],
      v12[6],
      v12[7]);
  }
  v13 = v38;
  v14 = (unsigned __int8 *)(*(_QWORD *)(v5 + 96) & 0xFFFFFFFFFFFFFFFCuLL);
  if ( v38 )
  {
    memmove((void *)(*(_QWORD *)(v5 + 96) & 0xFFFFFFFFFFFFFFFCuLL), v12, *(unsigned int *)(v5 + 124));
    v15 = v44;
    if ( v41 )
    {
      MmUnmapReservedMapping(*(PVOID *)(v7 + 2104), 0x72455646u, *(PMDL *)(v44 + 8));
      ExReleaseFastMutex((PFAST_MUTEX)(v7 + 2120));
    }
    v31 = *(_QWORD *)(v44 + 8);
    if ( (*(_BYTE *)(v31 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v31 + 24), *(PMDL *)(v44 + 8));
    v13 = v38;
    v42 = 0;
  }
  else
  {
    v15 = v44;
  }
  if ( (*(_DWORD *)(v7 + 808) & 0xC000) == 0 || *(_BYTE *)(v6 + 276) )
  {
    v16 = *(_QWORD *)(v6 + 280);
    v17 = -1;
    LOBYTE(v4) = *(_BYTE *)(v6 + 276);
    v18 = v16 != -1;
    if ( ((_BYTE)v4 != 0) != v18 )
      goto LABEL_45;
    LOBYTE(v18) = v43 && v39;
    v40 = v43 && v39;
    if ( (_BYTE)v4 )
      v17 = *(_QWORD *)v5 + v16 - *(_QWORD *)(v6 + 64);
    *(_QWORD *)(v5 + 56) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)(v5 + 88) = *(_DWORD *)(v5 + 124);
    if ( v18 )
    {
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v18, v4)
        && (*(_BYTE *)(v7 + 4419) & 8) != 0
        || (v32 = *(_QWORD *)(v7 + 976), *(_WORD *)(v32 + 10) == 1) )
      {
        v30 = 0;
      }
      else
      {
        v30 = *(unsigned int *)(v32 + 28);
        if ( !(_DWORD)v30 )
          v30 = 1;
      }
      LOBYTE(v19) = *(_QWORD *)v5 < v30 * (unsigned __int64)*(unsigned int *)(v7 + 1308);
    }
    else
    {
      v19 = 0;
    }
    InitializeFilterData(v7, v46, v19, v17, *(_QWORD *)(v6 + 288), 0);
    v46[2] = *(_QWORD *)(v5 + 8);
    if ( v38 )
      v12 = v14;
    LODWORD(v46[14]) = *(_DWORD *)(v5 + 124);
    v46[11] = (__int64)FveFilteredWrite;
    v46[12] = (__int64)v12;
    v46[13] = (__int64)v14;
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v21, v20) )
      v22 = LODWORD(v46[15]) | 3;
    else
      v22 = 3;
    LODWORD(v46[15]) = v22;
    if ( !v40 || (*(_DWORD *)(v7 + 808) & 0xC000) != 0 || *(char *)(v5 + 136) < 0 )
    {
      if ( !*(_BYTE *)(v6 + 276) )
        goto LABEL_45;
      v22 |= 0x1000u;
      LODWORD(v46[15]) = v22;
    }
    v23 = *(unsigned int *)(BugCheckParameter3 + 884);
    if ( *(_BYTE *)(v23 + BugCheckParameter3 + 1293) || *(_BYTE *)(v23 + v7 + 1949) )
    {
      v22 |= 0x100u;
      v46[15] = __PAIR64__(*(_DWORD *)(v7 + 4 * v23 + 1724), v22);
    }
    if ( *(_BYTE *)(v23 + BugCheckParameter3 + 1296) || *(_BYTE *)(v23 + v7 + 1952) )
    {
      v33 = *(_DWORD *)(v7 + 4 * v23 + 1736);
      v22 |= 0x200u;
      LODWORD(v46[15]) = v22;
      LODWORD(v46[16]) = v33;
    }
    if ( *(_BYTE *)(v23 + BugCheckParameter3 + 1417) )
    {
      v34 = *(_DWORD *)(BugCheckParameter3 + 4 * v23 + 1396);
      v22 |= 0x400u;
      LODWORD(v46[15]) = v22;
      HIDWORD(v46[16]) = v34;
    }
    v46[18] = v7;
    v46[19] = (__int64)FveDeviceFastAlloc;
    v46[20] = (__int64)FveDeviceFastFree;
    if ( v45 )
    {
      v22 |= 0x80u;
      LODWORD(v46[15]) = v22;
    }
    if ( (*(_DWORD *)(v7 + 808) & 0x100) != 0 )
    {
      v35 = *(_QWORD **)(v7 + 736);
      if ( v35 )
      {
        if ( *v35 )
        {
          v46[9] = *(_QWORD *)(v7 + 736);
          v36 = v22 | 8;
          v46[10] = *(_QWORD *)(v5 + 24);
          LODWORD(v46[15]) = v36;
          if ( (*(_BYTE *)(**(_QWORD **)(v7 + 736) + 48LL) & 1) != 0 )
            LODWORD(v46[15]) = v36 | 0x30;
        }
      }
    }
    v15 = v44;
    FvePerfTraceDevIoCrypto(v7, FVE_PERF_IO_ENCRYPT_START, v44, v46[2], v46[14]);
    v24 = *(_QWORD *)(*(_QWORD *)(v5 + 16) + 192LL);
    if ( v24 )
      v25 = FveTestRwParseBlockAndFilter(v46, v24, &v47);
    else
      v25 = FveParseBlockAndFilterEx(v46, &v47);
    *(_DWORD *)(v5 + 128) = v25;
    FvePerfTraceDevIoCrypto(v7, FVE_PERF_IO_ENCRYPT_STOP, v44, v46[2], v46[14]);
    LogFilterTrace(
      (unsigned int)"Filter write subrequest",
      (unsigned int)&v47,
      *(_DWORD *)(v5 + 128),
      v7,
      v46[2],
      v46[14]);
    if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v27, v26)
      || (v37 = *(_QWORD *)(v7 + 4752)) == 0
      || !*(_DWORD *)(v37 + 88)
      || *(_DWORD *)(v5 + 128) != -1073741662 && DWORD2(v48) != 259 )
    {
      if ( v46[7] )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v7 + 8) + 9272LL), (PVOID)v46[7]);
      memset(v46, 0, sizeof(v46));
      *(_QWORD *)(v5 + 64) = MEMORY[0xFFFFF78000000008];
      goto LABEL_43;
    }
LABEL_45:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  if ( *(char *)(v5 + 136) < 0 )
    goto LABEL_45;
  *(_DWORD *)(v5 + 128) = 0;
  if ( !v13 )
    memmove(v14, v12, *(unsigned int *)(v5 + 124));
LABEL_43:
  if ( v42 )
  {
    if ( v41 )
    {
      MmUnmapReservedMapping(*(PVOID *)(v7 + 2104), 0x72455646u, *(PMDL *)(v15 + 8));
      ExReleaseFastMutex((PFAST_MUTEX)(v7 + 2120));
    }
    v29 = *(_QWORD *)(v15 + 8);
    if ( (*(_BYTE *)(v29 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v29 + 24), *(PMDL *)(v15 + 8));
  }
  return WriteIssue(v5);
}

```

## disassembly

```asm
0x1400d7370  mov     [rsp-8+arg_10], rbx
0x1400d7375  push    rbp
0x1400d7376  push    rsi
0x1400d7377  push    rdi
0x1400d7378  push    r12
0x1400d737a  push    r13
0x1400d737c  push    r14
0x1400d737e  push    r15
0x1400d7380  lea     rbp, [rsp-0B0h]
0x1400d7388  sub     rsp, 1B0h
0x1400d738f  mov     rax, cs:__security_cookie
0x1400d7396  xor     rax, rsp
0x1400d7399  mov     [rbp+0E0h+var_40], rax
0x1400d73a0  xorps   xmm0, xmm0
0x1400d73a3  mov     rbx, rdx
0x1400d73a6  mov     r12, rcx
0x1400d73a9  xor     edx, edx; Val
0x1400d73ab  lea     rcx, [rbp+0E0h+var_160]; void *
0x1400d73af  mov     r8d, 100h; Size
0x1400d73b5  movups  [rbp+0E0h+var_60], xmm0
0x1400d73bc  movups  [rbp+0E0h+var_50], xmm0
0x1400d73c3  call    memset
0x1400d73c8  mov     rsi, [rbx+18h]
0x1400d73cc  cmp     [rsi+20h], rbx
0x1400d73d0  jz      short loc_1400D73F4
0x1400d73d2  mov     r9, r12; BugCheckParameter3
0x1400d73d5  mov     [rsp+1E0h+BugCheckParameter4], rsi; BugCheckParameter4
0x1400d73da  mov     r8, rbx; BugCheckParameter2
0x1400d73dd  mov     edx, 9; BugCheckParameter1
0x1400d73e2  mov     ecx, 120h; BugCheckCode
0x1400d73e7  call    cs:__imp_KeBugCheckEx
0x1400d73f4  mov     r13, [rsi+10h]
0x1400d73f8  mov     r14, [r13+30h]
0x1400d73fc  cmp     r12, [r14+8]
0x1400d7400  jnz     short loc_1400D73D2
0x1400d7402  movzx   ecx, byte ptr [rsi+88h]
0x1400d7409  mov     eax, ecx
0x1400d740b  and     eax, 3Fh
0x1400d740e  lea     rax, [rax+rax*2]
0x1400d7412  shl     rax, 6
0x1400d7416  add     rax, 138h
0x1400d741c  add     rax, r13
0x1400d741f  cmp     rsi, rax
0x1400d7422  jnz     short loc_1400D73D2
0x1400d7424  mov     eax, [rbx+20h]
0x1400d7427  mov     r10d, 1
0x1400d742d  mov     [rsp+1E0h+var_170], eax
0x1400d7431  mov     al, [rsi+90h]
0x1400d7437  mov     dl, al
0x1400d7439  xor     dl, [rbx+60h]
0x1400d743c  and     dl, r10b
0x1400d743f  xor     dl, al
0x1400d7441  and     dl, 0FDh
0x1400d7444  mov     [rsi+90h], dl
0x1400d744a  test    cl, 40h
0x1400d744d  jz      loc_1400D78FB
0x1400d7453  mov     ebx, [r14+328h]
0x1400d745a  test    ebx, 17Fh
0x1400d7460  mov     rdi, [rsi+28h]
0x1400d7464  setnz   al
0x1400d7467  mov     [rsp+1E0h+var_178], rdi
0x1400d746c  mov     [rsp+1E0h+var_17F], al
0x1400d7470  xor     r9d, r9d; RequestedAddress
0x1400d7473  mov     eax, [r12+374h]
0x1400d747b  cmp     [r14+rax*4+6B0h], r9d
0x1400d7483  jz      loc_1400D77D4
0x1400d7489  mov     [rsp+1E0h+var_180], r10b
0x1400d748e  mov     rcx, [rdi+8]; MemoryDescriptorList
0x1400d7492  test    byte ptr [rcx+0Ah], 5
0x1400d7496  jz      loc_1400D77EB
0x1400d749c  mov     r15, [rcx+18h]
0x1400d74a0  test    r15, r15
0x1400d74a3  jz      loc_1400D7861
0x1400d74a9  mov     [rsp+1E0h+var_17E], r9b
0x1400d74ae  test    bl, 40h
0x1400d74b1  mov     [rsp+1E0h+var_17D], r10b
0x1400d74b6  setz    [rsp+1E0h+var_17C]
0x1400d74bb  cmp     [rsi], r9
0x1400d74be  jz      loc_1400D7908
0x1400d74c4  mov     rdi, [rsi+60h]
0x1400d74c8  mov     cl, [rsp+1E0h+var_180]
0x1400d74cc  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400d74d0  test    cl, cl
0x1400d74d2  jnz     loc_1400D798B
0x1400d74d8  mov     rbx, [rsp+1E0h+var_178]
0x1400d74dd  test    dword ptr [r14+328h], 0C000h
0x1400d74e8  jnz     loc_1400D79DE
0x1400d74ee  mov     r8, [r13+118h]
0x1400d74f5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400d74f9  mov     dl, [r13+114h]
0x1400d7500  cmp     r8, rbx
0x1400d7503  mov     ecx, r9d
0x1400d7506  mov     eax, r9d
0x1400d7509  setnz   cl
0x1400d750c  test    dl, dl
0x1400d750e  setnz   al
0x1400d7511  cmp     eax, ecx
0x1400d7513  jnz     loc_1400D777B
0x1400d7519  mov     cl, [rsp+1E0h+var_17F]
0x1400d751d  and     cl, [rsp+1E0h+var_17C]
0x1400d7521  mov     [rsp+1E0h+var_17F], cl
0x1400d7525  test    dl, dl
0x1400d7527  jnz     loc_1400D7A1B
0x1400d752d  mov     rax, ds:0FFFFF78000000008h
0x1400d7537  mov     [rsi+38h], rax
0x1400d753b  mov     eax, [rsi+7Ch]
0x1400d753e  mov     [rsi+58h], eax
0x1400d7541  test    cl, cl
0x1400d7543  jnz     loc_1400D7818
0x1400d7549  mov     r8d, r9d
0x1400d754c  mov     rax, [r13+120h]
0x1400d7553  lea     rdx, [rbp+0E0h+var_160]
0x1400d7557  mov     qword ptr [rsp+1E0h+Priority], r9
0x1400d755c  mov     rcx, r14
0x1400d755f  mov     r9, rbx
0x1400d7562  mov     [rsp+1E0h+BugCheckParameter4], rax
0x1400d7567  call    InitializeFilterData
0x1400d756c  mov     rax, [rsi+8]
0x1400d7570  cmp     [rsp+1E0h+var_180], 0
0x1400d7575  mov     [rbp+0E0h+var_150], rax
0x1400d7579  mov     eax, [rsi+7Ch]
0x1400d757c  cmovnz  r15, rdi
0x1400d7580  mov     [rbp+0E0h+var_F0], eax
0x1400d7583  lea     rax, FveFilteredWrite
0x1400d758a  mov     [rbp+0E0h+var_108], rax
0x1400d758e  mov     [rbp+0E0h+var_100], r15
0x1400d7592  mov     [rbp+0E0h+var_F8], rdi
0x1400d7596  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d759b  xor     r9d, r9d
0x1400d759e  test    eax, eax
0x1400d75a0  jnz     loc_1400D779C
0x1400d75a6  lea     edx, [rax+3]
0x1400d75a9  mov     [rbp+0E0h+var_E8], edx
0x1400d75ac  cmp     [rsp+1E0h+var_17F], r9b
0x1400d75b1  jz      loc_1400D7A4D
0x1400d75b7  test    dword ptr [r14+328h], 0C000h
0x1400d75c2  jnz     loc_1400D7A4D
0x1400d75c8  cmp     [rsi+88h], r9b
0x1400d75cf  jl      loc_1400D7A4D
0x1400d75d5  mov     ecx, [r12+374h]
0x1400d75dd  cmp     [rcx+r12+50Dh], r9b
0x1400d75e5  jnz     loc_1400D7A66
0x1400d75eb  cmp     [rcx+r14+79Dh], r9b
0x1400d75f3  jnz     loc_1400D7A66
0x1400d75f9  cmp     [rcx+r12+510h], r9b
0x1400d7601  jnz     loc_1400D7A7D
0x1400d7607  cmp     [rcx+r14+7A0h], r9b
0x1400d760f  jnz     loc_1400D7A7D
0x1400d7615  cmp     [rcx+r12+589h], r9b
0x1400d761d  jnz     loc_1400D7A94
0x1400d7623  lea     rax, FveDeviceFastAlloc
0x1400d762a  mov     [rbp+0E0h+var_D0], r14
0x1400d762e  mov     [rbp+0E0h+var_C8], rax
0x1400d7632  lea     rax, FveDeviceFastFree
0x1400d7639  mov     [rbp+0E0h+var_C0], rax
0x1400d763d  cmp     [rsp+1E0h+var_170], r9d
0x1400d7642  jnz     loc_1400D7AAB
0x1400d7648  test    dword ptr [r14+328h], 100h
0x1400d7653  jnz     loc_1400D7AB7
0x1400d7659  mov     eax, [rbp+0E0h+var_F0]
0x1400d765c  lea     rdx, FVE_PERF_IO_ENCRYPT_START
0x1400d7663  mov     rbx, [rsp+1E0h+var_178]
0x1400d7668  mov     rcx, r14
0x1400d766b  mov     r9, [rbp+0E0h+var_150]
0x1400d766f  mov     r8, rbx
0x1400d7672  mov     dword ptr [rsp+1E0h+BugCheckParameter4], eax
0x1400d7676  call    FvePerfTraceDevIoCrypto
0x1400d767b  mov     rax, [rsi+10h]
0x1400d767f  lea     rcx, [rbp+0E0h+var_160]
0x1400d7683  mov     rdx, [rax+0C0h]
0x1400d768a  test    rdx, rdx
0x1400d768d  jnz     loc_1400D7850
0x1400d7693  lea     rdx, [rbp+0E0h+var_60]
0x1400d769a  call    FveParseBlockAndFilterEx
0x1400d769f  mov     [rsi+80h], eax
0x1400d76a5  lea     rdx, FVE_PERF_IO_ENCRYPT_STOP
0x1400d76ac  mov     eax, [rbp+0E0h+var_F0]
0x1400d76af  mov     r8, rbx
0x1400d76b2  mov     r9, [rbp+0E0h+var_150]
0x1400d76b6  mov     rcx, r14
0x1400d76b9  mov     dword ptr [rsp+1E0h+BugCheckParameter4], eax
0x1400d76bd  call    FvePerfTraceDevIoCrypto
0x1400d76c2  mov     eax, [rbp+0E0h+var_F0]
0x1400d76c5  lea     rdx, [rbp+0E0h+var_60]
0x1400d76cc  mov     r8d, [rsi+80h]
0x1400d76d3  lea     rcx, aFilterWriteSub; "Filter write subrequest"
0x1400d76da  mov     [rsp+1E0h+Priority], eax
0x1400d76de  mov     r9, r14
0x1400d76e1  mov     rax, [rbp+0E0h+var_150]
0x1400d76e5  mov     [rsp+1E0h+BugCheckParameter4], rax
0x1400d76ea  call    LogFilterTrace
0x1400d76ef  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d76f4  xor     r9d, r9d
0x1400d76f7  test    eax, eax
0x1400d76f9  jnz     loc_1400D7B01
0x1400d76ff  mov     rdx, [rbp+0E0h+Entry]; Entry
0x1400d7703  test    rdx, rdx
0x1400d7706  jz      short loc_1400D771F
0x1400d7708  mov     rcx, [r14+8]
0x1400d770c  mov     rcx, [rcx+2438h]; Lookaside
0x1400d7713  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d771a  nop     dword ptr [rax+rax+00h]
0x1400d771f  xor     edx, edx; Val
0x1400d7721  lea     rcx, [rbp+0E0h+var_160]; void *
0x1400d7725  mov     r8d, 100h; Size
0x1400d772b  call    memset
0x1400d7730  mov     rax, ds:0FFFFF78000000008h
0x1400d773a  mov     [rsi+40h], rax
0x1400d773e  xor     r9d, r9d
0x1400d7741  cmp     [rsp+1E0h+var_17D], r9b
0x1400d7746  jnz     short loc_1400D77A7
0x1400d7748  mov     rcx, rsi; BugCheckParameter2
0x1400d774b  call    WriteIssue
0x1400d7750  mov     rcx, [rbp+0E0h+var_40]
0x1400d7757  xor     rcx, rsp; StackCookie
0x1400d775a  call    __security_check_cookie
0x1400d775f  mov     rbx, [rsp+1E0h+arg_10]
0x1400d7767  add     rsp, 1B0h
0x1400d776e  pop     r15
0x1400d7770  pop     r14
0x1400d7772  pop     r13
0x1400d7774  pop     r12
0x1400d7776  pop     rdi
0x1400d7777  pop     rsi
0x1400d7778  pop     rbp
0x1400d7779  retn
0x1400d777b  mov     [rsp+1E0h+BugCheckParameter4], r9; BugCheckParameter4
0x1400d7780  xor     r8d, r8d; BugCheckParameter2
0x1400d7783  xor     r9d, r9d; BugCheckParameter3
0x1400d7786  mov     ecx, 120h; BugCheckCode
0x1400d778b  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d778f  call    cs:__imp_KeBugCheckEx
0x1400d779c  mov     edx, [rbp+0E0h+var_E8]
0x1400d779f  or      edx, 3
0x1400d77a2  jmp     loc_1400D75A9
0x1400d77a7  cmp     [rsp+1E0h+var_17E], r9b
0x1400d77ac  jnz     loc_1400D7B40
0x1400d77b2  mov     rcx, [rbx+8]
0x1400d77b6  test    byte ptr [rcx+0Ah], 20h
0x1400d77ba  jz      short loc_1400D7748
0x1400d77bc  mov     rdx, rcx; MemoryDescriptorList
0x1400d77bf  mov     rcx, [rcx+18h]; BaseAddress
0x1400d77c3  call    cs:__imp_MmUnmapLockedPages
0x1400d77ca  nop     dword ptr [rax+rax+00h]
0x1400d77cf  jmp     loc_1400D7748
0x1400d77d4  mov     [rsp+1E0h+var_180], r9b
0x1400d77d9  cmp     [r13+110h], r9b
0x1400d77e0  jnz     loc_1400D748E
0x1400d77e6  jmp     loc_1400D7489
0x1400d77eb  mov     [rsp+1E0h+Priority], 40000010h; Priority
0x1400d77f3  mov     r8d, r10d; CacheType
0x1400d77f6  xor     edx, edx; AccessMode
0x1400d77f8  mov     dword ptr [rsp+1E0h+BugCheckParameter4], r9d; BugCheckOnFailure
0x1400d77fd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d7804  nop     dword ptr [rax+rax+00h]
0x1400d7809  xor     r9d, r9d
0x1400d780c  mov     r15, rax
0x1400d780f  lea     r10d, [r9+1]
0x1400d7813  jmp     loc_1400D74A0
0x1400d7818  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d781d  xor     r9d, r9d
0x1400d7820  test    eax, eax
0x1400d7822  jz      loc_1400D7A2A
0x1400d7828  test    byte ptr [r14+1143h], 8
0x1400d7830  jz      loc_1400D7A2A
0x1400d7836  mov     eax, r9d
0x1400d7839  mov     ecx, [r14+51Ch]
0x1400d7840  imul    rcx, rax
0x1400d7844  cmp     [rsi], rcx
0x1400d7847  setb    r8b
0x1400d784b  jmp     loc_1400D754C
0x1400d7850  lea     r8, [rbp+0E0h+var_60]
0x1400d7857  call    FveTestRwParseBlockAndFilter
0x1400d785c  jmp     loc_1400D769F
0x1400d7861  lea     rcx, [r14+848h]; FastMutex
0x1400d7868  call    cs:__imp_ExAcquireFastMutex
0x1400d786f  nop     dword ptr [rax+rax+00h]
0x1400d7874  mov     r8, [rdi+8]; MemoryDescriptorList
0x1400d7878  mov     r9d, 1; CacheType
0x1400d787e  mov     rcx, [r14+838h]; MappingAddress
0x1400d7885  mov     edx, 72455646h; PoolTag
0x1400d788a  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400d7891  nop     dword ptr [rax+rax+00h]
0x1400d7896  xor     r9d, r9d; BugCheckParameter3
0x1400d7899  mov     r10d, 1
0x1400d789f  mov     [rsp+1E0h+var_17E], r10b
0x1400d78a4  mov     r15, rax
0x1400d78a7  test    rax, rax
0x1400d78aa  jnz     loc_1400D74AE
0x1400d78b0  xor     r8d, r8d; BugCheckParameter2
0x1400d78b3  mov     [rsp+1E0h+BugCheckParameter4], r9; BugCheckParameter4
0x1400d78b8  mov     edx, r10d; BugCheckParameter1
0x1400d78bb  mov     ecx, 120h; BugCheckCode
0x1400d78c0  call    cs:__imp_KeBugCheckEx
0x1400d78cd  mov     rcx, [rbx+8]
0x1400d78d1  test    byte ptr [rcx+0Ah], 20h
0x1400d78d5  jz      short loc_1400D78EA
0x1400d78d7  mov     rdx, rcx; MemoryDescriptorList
0x1400d78da  mov     rcx, [rcx+18h]; BaseAddress
0x1400d78de  call    cs:__imp_MmUnmapLockedPages
  ... truncated ...
```
