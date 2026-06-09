# FastReadMapped

- ea: `0x14009d600`
- end: `0x14009da6a`
- name: `FastReadMapped`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400b9714`

## callees

- `0x140001700`
- `0x140003610`
- `0x140008288`
- `0x140009910`
- `0x140009bf4`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x14009d600`
- `0x1400d7f90`
- `0x1400d8584`
- `0x1400d9620`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x14009d8c0`
- `ntoskrnl!MmMdlPageContentsState` at `0x14009d909`
- `ntoskrnl!MmMdlPageContentsState` at `0x14009d8c0`
- `ntoskrnl!MmMdlPageContentsState` at `0x14009d909`
- `ntoskrnl!MmAreMdlPagesCached` at `0x14009d8f1`
- `ntoskrnl!MmAreMdlPagesCached` at `0x14009d8f1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009d6f0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009d6f0`
- `ntoskrnl!KeBugCheckEx` at `0x14009d9e5`
- `ntoskrnl!KeBugCheckEx` at `0x14009d9e5`

## string_xrefs

- `0x14009d98a`: `Filter read fastio request`

## pseudocode

```c
__int64 __fastcall FastReadMapped(__int64 a1, void *a2)
{
  __int64 v2; // r13
  __int64 v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rdi
  char v7; // r15
  int v8; // r12d
  PVOID v9; // r14
  __int64 result; // rax
  int v11; // edi
  char v12; // r13
  _BOOL8 v13; // rcx
  bool v14; // di
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r12
  __int64 v19; // rcx
  void *v20; // r12
  void *v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rax
  _DWORD Size[3]; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v31; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  void *v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int64 v36[32]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+170h] [rbp+70h] BYREF
  __int128 v38; // [rsp+180h] [rbp+80h]

  v2 = *(_QWORD *)(a1 + 184);
  v33 = a2;
  v4 = *(_QWORD *)(*(_QWORD *)(v2 + 40) + 64LL);
  v35 = *(_QWORD *)(v4 + 8);
  if ( (unsigned __int8)BYTE2(*(_DWORD *)(a1 + 120)) )
    v5 = *(_QWORD *)(a1 + 128);
  else
    v5 = 0;
  v6 = *(_QWORD *)(a1 + 8);
  v30 = v5;
  v32 = 0;
  *(_QWORD *)&Size[1] = -1;
  v37 = 0;
  v38 = 0;
  memset(v36, 0, sizeof(v36));
  v7 = 1;
  v8 = *(_DWORD *)(v4 + 808);
  v34 = *(_QWORD *)(v5 + 56);
  if ( v34 )
  {
    if ( (*(_BYTE *)(v6 + 10) & 5) != 0 )
      v9 = *(PVOID *)(v6 + 24);
    else
      v9 = MmMapLockedPagesSpecifyCache((PMDL)v6, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v9 = 0;
    v34 = v6;
  }
  v31 = *(_QWORD *)(v2 + 24);
  Size[0] = *(_DWORD *)(v2 + 8);
  result = FveIsIrpWithEfsOffload(a1, &Size[1], &v32);
  v11 = *(_DWORD *)(a1 + 48);
  v12 = result;
  if ( v11 >= 0 )
  {
    *(_QWORD *)(v30 + 24) = MEMORY[0xFFFFF78000000008];
    if ( (*(_DWORD *)(v4 + 808) & 0xC000) != 0 && !(_BYTE)result )
    {
      v11 = 0;
      if ( v9 )
        memmove(v33, v9, Size[0]);
LABEL_57:
      result = MEMORY[0xFFFFF78000000008];
      *(_QWORD *)(v30 + 32) = MEMORY[0xFFFFF78000000008];
      if ( v11 >= 0 )
        return result;
      goto LABEL_58;
    }
    v13 = (_BYTE)result != 0;
    if ( v13 != (*(_QWORD *)&Size[1] != -1) )
LABEL_51:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    v14 = (v8 & 0x17F) != 0 && (v8 & 0x40) == 0;
    if ( v14 )
    {
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v13)
        && (*(_BYTE *)(v4 + 4403) & 8) != 0
        || (v16 = *(_QWORD *)(v4 + 976), *(_WORD *)(v16 + 10) == 1) )
      {
        v17 = 0;
      }
      else
      {
        v17 = *(unsigned int *)(v16 + 28);
        if ( !(_DWORD)v17 )
          v17 = 1;
      }
      v18 = v31;
      LOBYTE(v15) = v31 < v17 * (unsigned __int64)*(unsigned int *)(v4 + 1308);
    }
    else
    {
      v18 = v31;
      v15 = 0;
    }
    InitializeFilterData(v4, v36, v15, *(_QWORD *)&Size[1], v32, 0);
    LODWORD(v36[14]) = Size[0];
    v36[2] = v18;
    v20 = v33;
    v21 = v33;
    if ( v9 )
      v21 = v9;
    v36[12] = (__int64)v21;
    v36[11] = (__int64)FveFilteredRead;
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v19) )
      v22 = LODWORD(v36[15]) | 5;
    else
      v22 = 5;
    LODWORD(v36[15]) = v22;
    if ( !v14 || (*(_DWORD *)(v4 + 808) & 0xC000) != 0 )
    {
      if ( !v12 )
        goto LABEL_51;
      v22 |= 0x1000u;
      LODWORD(v36[15]) = v22;
    }
    v23 = *(unsigned int *)(v35 + 884);
    if ( *(_BYTE *)(v23 + v35 + 1299) || *(_BYTE *)(v23 + v4 + 1955) )
    {
      v24 = *(_DWORD *)(v4 + 4 * v23 + 1748);
      LODWORD(v36[15]) = v22 | 0x800;
      LODWORD(v36[17]) = v24;
    }
    if ( v9 )
    {
      if ( !*(_DWORD *)(v4 + 4LL * *(unsigned int *)(v35 + 884) + 1712)
        && (v26 = v34, (unsigned int)MmAreMdlPagesCached(v34))
        && (unsigned int)MmMdlPageContentsState(v26, 2) )
      {
        v7 = 0;
        v36[13] = (__int64)v20;
      }
      else
      {
        v36[13] = (__int64)v9;
      }
    }
    else
    {
      v25 = *(_QWORD *)(a1 + 8);
      v36[13] = (__int64)v20;
      if ( !(unsigned int)MmMdlPageContentsState(v25, 2) )
        LODWORD(v36[15]) |= 0x40u;
      v7 = 0;
    }
    FvePerfTraceDevIoCrypto(v4, FVE_PERF_IO_DECRYPT_START, a1, v36[2], v36[14]);
    v11 = FveParseBlockAndFilterEx(v36, &v37);
    FvePerfTraceDevIoCrypto(v4, FVE_PERF_IO_DECRYPT_STOP, a1, v36[2], v36[14]);
    LogFilterTrace((unsigned int)"Filter read fastio request", (unsigned int)&v37, v11, v4, v36[2], v36[14]);
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v27) )
    {
      if ( v11 >= 0 )
      {
        v28 = *(_QWORD *)(v4 + 4736);
        if ( v28 && *(_DWORD *)(v28 + 88) && (HIDWORD(v38) == -1073741662 || DWORD2(v38) == 259) )
          goto LABEL_51;
        goto LABEL_53;
      }
    }
    else if ( v11 >= 0 )
    {
LABEL_53:
      if ( v9 && v7 )
        memmove(v20, v9, Size[0]);
    }
    DeInitializeFilterData(v4, v36);
    goto LABEL_57;
  }
LABEL_58:
  *(_DWORD *)(a1 + 48) = v11;
  *(_QWORD *)(a1 + 56) = 0;
  return result;
}

```

## disassembly

```asm
0x14009d600  mov     [rsp-8+arg_10], rbx
0x14009d605  push    rbp
0x14009d606  push    rsi
0x14009d607  push    rdi
0x14009d608  push    r12
0x14009d60a  push    r13
0x14009d60c  push    r14
0x14009d60e  push    r15
0x14009d610  lea     rbp, [rsp-0A0h]
0x14009d618  sub     rsp, 1A0h
0x14009d61f  mov     rax, cs:__security_cookie
0x14009d626  xor     rax, rsp
0x14009d629  mov     [rbp+0D0h+var_40], rax
0x14009d630  mov     r13, [rcx+0B8h]
0x14009d637  mov     rsi, rcx
0x14009d63a  mov     [rsp+1D0h+var_178], rdx
0x14009d63f  mov     rax, [r13+28h]
0x14009d643  mov     rbx, [rax+40h]
0x14009d647  mov     rax, [rbx+8]
0x14009d64b  mov     [rsp+1D0h+var_168], rax
0x14009d650  mov     eax, [rcx+78h]
0x14009d653  shr     rax, 10h
0x14009d657  test    al, al
0x14009d659  jz      short loc_14009D664
0x14009d65b  mov     r14, [rcx+80h]
0x14009d662  jmp     short loc_14009D667
0x14009d664  xor     r14d, r14d
0x14009d667  mov     rdi, [rcx+8]
0x14009d66b  xorps   xmm0, xmm0
0x14009d66e  lea     rcx, [rsp+1D0h+var_160]; void *
0x14009d673  mov     [rsp+1D0h+var_190], r14
0x14009d678  xor     edx, edx; Val
0x14009d67a  mov     [rsp+1D0h+var_180], 0
0x14009d683  mov     r8d, 100h; Size
0x14009d689  mov     qword ptr [rsp+1D0h+Size+4], 0FFFFFFFFFFFFFFFFh
0x14009d692  movups  [rbp+0D0h+var_60], xmm0
0x14009d696  movups  [rbp+0D0h+var_50], xmm0
0x14009d69d  call    memset
0x14009d6a2  mov     rax, [r14+38h]
0x14009d6a6  mov     r15d, 1
0x14009d6ac  mov     r12d, [rbx+328h]
0x14009d6b3  test    r12d, 17Fh
0x14009d6ba  mov     [rsp+1D0h+var_170], rax
0x14009d6bf  setnz   [rsp+1D0h+var_1A0]
0x14009d6c4  test    rax, rax
0x14009d6c7  jz      short loc_14009D701
0x14009d6c9  test    byte ptr [rdi+0Ah], 5
0x14009d6cd  jz      short loc_14009D6D5
0x14009d6cf  mov     r14, [rdi+18h]
0x14009d6d3  jmp     short loc_14009D709
0x14009d6d5  mov     [rsp+1D0h+Priority], 40000010h; Priority
0x14009d6dd  xor     r9d, r9d; RequestedAddress
0x14009d6e0  mov     r8d, r15d; CacheType
0x14009d6e3  mov     [rsp+1D0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14009d6eb  xor     edx, edx; AccessMode
0x14009d6ed  mov     rcx, rdi; MemoryDescriptorList
0x14009d6f0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14009d6f7  nop     dword ptr [rax+rax+00h]
0x14009d6fc  mov     r14, rax
0x14009d6ff  jmp     short loc_14009D709
0x14009d701  xor     r14d, r14d
0x14009d704  mov     [rsp+1D0h+var_170], rdi
0x14009d709  mov     rax, [r13+18h]
0x14009d70d  lea     r8, [rsp+1D0h+var_180]
0x14009d712  mov     [rsp+1D0h+var_188], rax
0x14009d717  lea     rdx, [rsp+1D0h+Size+4]
0x14009d71c  mov     eax, [r13+8]
0x14009d720  mov     rcx, rsi
0x14009d723  mov     dword ptr [rsp+1D0h+Size], eax
0x14009d727  call    FveIsIrpWithEfsOffload
0x14009d72c  mov     edi, [rsi+30h]
0x14009d72f  mov     r13b, al
0x14009d732  test    edi, edi
0x14009d734  js      loc_14009DA34
0x14009d73a  mov     rax, ds:0FFFFF78000000008h
0x14009d744  test    r12b, 40h
0x14009d748  mov     rcx, [rsp+1D0h+var_190]
0x14009d74d  setz    dil
0x14009d751  mov     [rcx+18h], rax
0x14009d755  test    dword ptr [rbx+328h], 0C000h
0x14009d75f  jz      short loc_14009D788
0x14009d761  test    r13b, r13b
0x14009d764  jnz     short loc_14009D788
0x14009d766  xor     edi, edi
0x14009d768  test    r14, r14
0x14009d76b  jz      loc_14009DA1D
0x14009d771  mov     r8d, dword ptr [rsp+1D0h+Size]; Size
0x14009d776  mov     rdx, r14; Src
0x14009d779  mov     rcx, [rsp+1D0h+var_178]; void *
0x14009d77e  call    memmove
0x14009d783  jmp     loc_14009DA1D
0x14009d788  xor     ecx, ecx
0x14009d78a  test    r13b, r13b
0x14009d78d  setnz   cl
0x14009d790  xor     eax, eax
0x14009d792  cmp     qword ptr [rsp+1D0h+Size+4], 0FFFFFFFFFFFFFFFFh
0x14009d798  setnz   al
0x14009d79b  cmp     ecx, eax
0x14009d79d  jnz     loc_14009D9CD
0x14009d7a3  and     dil, [rsp+1D0h+var_1A0]
0x14009d7a8  jz      short loc_14009D7EF
0x14009d7aa  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14009d7af  test    eax, eax
0x14009d7b1  jz      short loc_14009D7BC
0x14009d7b3  test    byte ptr [rbx+1133h], 8
0x14009d7ba  jnz     short loc_14009D7CA
0x14009d7bc  mov     rax, [rbx+3D0h]
0x14009d7c3  cmp     [rax+0Ah], r15w
0x14009d7c8  jnz     short loc_14009D7CE
0x14009d7ca  xor     eax, eax
0x14009d7cc  jmp     short loc_14009D7D7
0x14009d7ce  mov     eax, [rax+1Ch]
0x14009d7d1  test    eax, eax
0x14009d7d3  cmovz   eax, r15d
0x14009d7d7  mov     ecx, [rbx+51Ch]
0x14009d7dd  mov     r12, [rsp+1D0h+var_188]
0x14009d7e2  imul    rcx, rax
0x14009d7e6  cmp     r12, rcx
0x14009d7e9  setb    r8b
0x14009d7ed  jmp     short loc_14009D7F7
0x14009d7ef  mov     r12, [rsp+1D0h+var_188]
0x14009d7f4  xor     r8d, r8d
0x14009d7f7  mov     rax, [rsp+1D0h+var_180]
0x14009d7fc  lea     rdx, [rsp+1D0h+var_160]
0x14009d801  mov     r9, qword ptr [rsp+1D0h+Size+4]
0x14009d806  mov     rcx, rbx
0x14009d809  mov     qword ptr [rsp+1D0h+Priority], 0
0x14009d812  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rax
0x14009d817  call    InitializeFilterData
0x14009d81c  mov     eax, dword ptr [rsp+1D0h+Size]
0x14009d820  test    r14, r14
0x14009d823  mov     [rbp+0D0h+var_F0], eax
0x14009d826  mov     [rbp+0D0h+var_150], r12
0x14009d82a  mov     r12, [rsp+1D0h+var_178]
0x14009d82f  mov     rax, r12
0x14009d832  cmovnz  rax, r14
0x14009d836  mov     [rbp+0D0h+var_100], rax
0x14009d83a  lea     rax, FveFilteredRead
0x14009d841  mov     [rbp+0D0h+var_108], rax
0x14009d845  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14009d84a  test    eax, eax
0x14009d84c  jz      short loc_14009D856
0x14009d84e  mov     ecx, [rbp+0D0h+var_E8]
0x14009d851  or      ecx, 5
0x14009d854  jmp     short loc_14009D85B
0x14009d856  mov     ecx, 5
0x14009d85b  mov     [rbp+0D0h+var_E8], ecx
0x14009d85e  test    dil, dil
0x14009d861  jz      short loc_14009D86F
0x14009d863  test    dword ptr [rbx+328h], 0C000h
0x14009d86d  jz      short loc_14009D87F
0x14009d86f  test    r13b, r13b
0x14009d872  jz      loc_14009D9CD
0x14009d878  bts     ecx, 0Ch
0x14009d87c  mov     [rbp+0D0h+var_E8], ecx
0x14009d87f  mov     rdx, [rsp+1D0h+var_168]
0x14009d884  mov     eax, [rdx+374h]
0x14009d88a  cmp     byte ptr [rax+rdx+513h], 0
0x14009d892  jnz     short loc_14009D89E
0x14009d894  cmp     byte ptr [rax+rbx+7A3h], 0
0x14009d89c  jz      short loc_14009D8AF
0x14009d89e  mov     eax, [rbx+rax*4+6D4h]
0x14009d8a5  bts     ecx, 0Bh
0x14009d8a9  mov     [rbp+0D0h+var_E8], ecx
0x14009d8ac  mov     [rbp+0D0h+var_D8], eax
0x14009d8af  test    r14, r14
0x14009d8b2  jnz     short loc_14009D8D9
0x14009d8b4  mov     rcx, [rsi+8]
0x14009d8b8  lea     edx, [r14+2]
0x14009d8bc  mov     [rbp+0D0h+var_F8], r12
0x14009d8c0  call    cs:__imp_MmMdlPageContentsState
0x14009d8c7  nop     dword ptr [rax+rax+00h]
0x14009d8cc  test    eax, eax
0x14009d8ce  jnz     short loc_14009D8D4
0x14009d8d0  or      [rbp+0D0h+var_E8], 40h
0x14009d8d4  xor     r15b, r15b
0x14009d8d7  jmp     short loc_14009D926
0x14009d8d9  mov     eax, [rdx+374h]
0x14009d8df  cmp     dword ptr [rbx+rax*4+6B0h], 0
0x14009d8e7  jnz     short loc_14009D922
0x14009d8e9  mov     rdi, [rsp+1D0h+var_170]
0x14009d8ee  mov     rcx, rdi
0x14009d8f1  call    cs:__imp_MmAreMdlPagesCached
0x14009d8f8  nop     dword ptr [rax+rax+00h]
0x14009d8fd  test    eax, eax
0x14009d8ff  jz      short loc_14009D922
0x14009d901  mov     edx, 2
0x14009d906  mov     rcx, rdi
0x14009d909  call    cs:__imp_MmMdlPageContentsState
0x14009d910  nop     dword ptr [rax+rax+00h]
0x14009d915  test    eax, eax
0x14009d917  jz      short loc_14009D922
0x14009d919  xor     r15b, r15b
0x14009d91c  mov     [rbp+0D0h+var_F8], r12
0x14009d920  jmp     short loc_14009D926
0x14009d922  mov     [rbp+0D0h+var_F8], r14
0x14009d926  mov     eax, [rbp+0D0h+var_F0]
0x14009d929  lea     rdx, FVE_PERF_IO_DECRYPT_START
0x14009d930  mov     r9, [rbp+0D0h+var_150]
0x14009d934  mov     r8, rsi
0x14009d937  mov     rcx, rbx
0x14009d93a  mov     [rsp+1D0h+BugCheckOnFailure], eax
0x14009d93e  call    FvePerfTraceDevIoCrypto
0x14009d943  lea     rdx, [rbp+0D0h+var_60]
0x14009d947  lea     rcx, [rsp+1D0h+var_160]
0x14009d94c  call    FveParseBlockAndFilterEx
0x14009d951  mov     ecx, [rbp+0D0h+var_F0]
0x14009d954  lea     rdx, FVE_PERF_IO_DECRYPT_STOP
0x14009d95b  mov     r9, [rbp+0D0h+var_150]
0x14009d95f  mov     r8, rsi
0x14009d962  mov     [rsp+1D0h+BugCheckOnFailure], ecx
0x14009d966  mov     edi, eax
0x14009d968  mov     rcx, rbx
0x14009d96b  call    FvePerfTraceDevIoCrypto
0x14009d970  mov     ecx, [rbp+0D0h+var_F0]
0x14009d973  lea     rdx, [rbp+0D0h+var_60]
0x14009d977  mov     [rsp+1D0h+Priority], ecx
0x14009d97b  mov     r9, rbx
0x14009d97e  mov     rcx, [rbp+0D0h+var_150]
0x14009d982  mov     r8d, edi
0x14009d985  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rcx
0x14009d98a  lea     rcx, aFilterReadFast; "Filter read fastio request"
0x14009d991  call    LogFilterTrace
0x14009d996  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x14009d99b  test    eax, eax
0x14009d99d  jz      short loc_14009D9F2
0x14009d99f  test    edi, edi
0x14009d9a1  js      short loc_14009DA10
0x14009d9a3  mov     rax, [rbx+1280h]
0x14009d9aa  test    rax, rax
0x14009d9ad  jz      short loc_14009D9F6
0x14009d9af  cmp     dword ptr [rax+58h], 0
0x14009d9b3  jz      short loc_14009D9F6
0x14009d9b5  cmp     dword ptr [rbp+0D0h+var_50+0Ch], 0C00000A2h
0x14009d9bf  jz      short loc_14009D9CD
0x14009d9c1  cmp     dword ptr [rbp+0D0h+var_50+8], 103h
0x14009d9cb  jnz     short loc_14009D9F6
0x14009d9cd  xor     r9d, r9d; BugCheckParameter3
0x14009d9d0  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], 0; BugCheckParameter4
0x14009d9d9  xor     r8d, r8d; BugCheckParameter2
0x14009d9dc  mov     ecx, 120h; BugCheckCode
0x14009d9e1  lea     edx, [r9+0Ch]; BugCheckParameter1
0x14009d9e5  call    cs:__imp_KeBugCheckEx
0x14009d9f2  test    edi, edi
0x14009d9f4  js      short loc_14009DA10
0x14009d9f6  test    r14, r14
0x14009d9f9  jz      short loc_14009DA10
0x14009d9fb  test    r15b, r15b
0x14009d9fe  jz      short loc_14009DA10
0x14009da00  mov     r8d, dword ptr [rsp+1D0h+Size]; Size
0x14009da05  mov     rdx, r14; Src
0x14009da08  mov     rcx, r12; void *
0x14009da0b  call    memmove
0x14009da10  lea     rdx, [rsp+1D0h+var_160]
0x14009da15  mov     rcx, rbx
0x14009da18  call    DeInitializeFilterData
0x14009da1d  mov     r8, [rsp+1D0h+var_190]
0x14009da22  mov     rax, ds:0FFFFF78000000008h
0x14009da2c  mov     [r8+20h], rax
0x14009da30  test    edi, edi
0x14009da32  jns     short loc_14009DA3F
0x14009da34  mov     [rsi+30h], edi
0x14009da37  mov     qword ptr [rsi+38h], 0
0x14009da3f  mov     rcx, [rbp+0D0h+var_40]
0x14009da46  xor     rcx, rsp; StackCookie
0x14009da49  call    __security_check_cookie
0x14009da4e  mov     rbx, [rsp+1D0h+arg_10]
0x14009da56  add     rsp, 1A0h
0x14009da5d  pop     r15
0x14009da5f  pop     r14
0x14009da61  pop     r13
0x14009da63  pop     r12
0x14009da65  pop     rdi
0x14009da66  pop     rsi
0x14009da67  pop     rbp
0x14009da68  retn
```
