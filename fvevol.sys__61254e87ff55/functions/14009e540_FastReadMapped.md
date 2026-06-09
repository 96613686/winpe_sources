# FastReadMapped

- ea: `0x14009e540`
- end: `0x14009e9aa`
- name: `FastReadMapped`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400bb7e4`

## callees

- `0x140001710`
- `0x140003620`
- `0x140008348`
- `0x1400099d0`
- `0x140009cb4`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x14009e540`
- `0x1400d7b80`
- `0x1400d8170`
- `0x1400dbd00`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x14009e800`
- `ntoskrnl!MmMdlPageContentsState` at `0x14009e849`
- `ntoskrnl!MmMdlPageContentsState` at `0x14009e800`
- `ntoskrnl!MmMdlPageContentsState` at `0x14009e849`
- `ntoskrnl!MmAreMdlPagesCached` at `0x14009e831`
- `ntoskrnl!MmAreMdlPagesCached` at `0x14009e831`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009e630`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009e630`
- `ntoskrnl!KeBugCheckEx` at `0x14009e925`
- `ntoskrnl!KeBugCheckEx` at `0x14009e925`

## string_xrefs

- `0x14009e8ca`: `Filter read fastio request`

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
  __int64 v11; // rdx
  int v12; // edi
  char v13; // r13
  _BOOL8 v14; // rcx
  bool v15; // di
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r12
  __int64 v20; // rdx
  __int64 v21; // rcx
  void *v22; // r12
  void *v23; // rax
  int v24; // ecx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdi
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  _DWORD Size[3]; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v34; // [rsp+48h] [rbp-B8h]
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  void *v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  __int64 v39[32]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+170h] [rbp+70h] BYREF
  __int128 v41; // [rsp+180h] [rbp+80h]

  v2 = *(_QWORD *)(a1 + 184);
  v36 = a2;
  v4 = *(_QWORD *)(*(_QWORD *)(v2 + 40) + 64LL);
  v38 = *(_QWORD *)(v4 + 8);
  if ( (unsigned __int8)BYTE2(*(_DWORD *)(a1 + 120)) )
    v5 = *(_QWORD *)(a1 + 128);
  else
    v5 = 0;
  v6 = *(_QWORD *)(a1 + 8);
  v33 = v5;
  v35 = 0;
  *(_QWORD *)&Size[1] = -1;
  v40 = 0;
  v41 = 0;
  memset(v39, 0, sizeof(v39));
  v7 = 1;
  v8 = *(_DWORD *)(v4 + 808);
  v37 = *(_QWORD *)(v5 + 56);
  if ( v37 )
  {
    if ( (*(_BYTE *)(v6 + 10) & 5) != 0 )
      v9 = *(PVOID *)(v6 + 24);
    else
      v9 = MmMapLockedPagesSpecifyCache((PMDL)v6, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v9 = 0;
    v37 = v6;
  }
  v34 = *(_QWORD *)(v2 + 24);
  Size[0] = *(_DWORD *)(v2 + 8);
  result = FveIsIrpWithEfsOffload(a1, &Size[1], &v35);
  v12 = *(_DWORD *)(a1 + 48);
  v13 = result;
  if ( v12 >= 0 )
  {
    *(_QWORD *)(v33 + 24) = MEMORY[0xFFFFF78000000008];
    if ( (*(_DWORD *)(v4 + 808) & 0xC000) != 0 && !(_BYTE)result )
    {
      v12 = 0;
      if ( v9 )
        memmove(v36, v9, Size[0]);
LABEL_57:
      result = MEMORY[0xFFFFF78000000008];
      *(_QWORD *)(v33 + 32) = MEMORY[0xFFFFF78000000008];
      if ( v12 >= 0 )
        return result;
      goto LABEL_58;
    }
    v14 = (_BYTE)result != 0;
    if ( v14 != (*(_QWORD *)&Size[1] != -1) )
LABEL_51:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    v15 = (v8 & 0x17F) != 0 && (v8 & 0x40) == 0;
    if ( v15 )
    {
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v14, v11)
        && (*(_BYTE *)(v4 + 4419) & 8) != 0
        || (v17 = *(_QWORD *)(v4 + 976), *(_WORD *)(v17 + 10) == 1) )
      {
        v18 = 0;
      }
      else
      {
        v18 = *(unsigned int *)(v17 + 28);
        if ( !(_DWORD)v18 )
          v18 = 1;
      }
      v19 = v34;
      LOBYTE(v16) = v34 < v18 * (unsigned __int64)*(unsigned int *)(v4 + 1308);
    }
    else
    {
      v19 = v34;
      v16 = 0;
    }
    InitializeFilterData(v4, v39, v16, *(_QWORD *)&Size[1], v35, 0);
    LODWORD(v39[14]) = Size[0];
    v39[2] = v19;
    v22 = v36;
    v23 = v36;
    if ( v9 )
      v23 = v9;
    v39[12] = (__int64)v23;
    v39[11] = (__int64)FveFilteredRead;
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v21, v20) )
      v24 = LODWORD(v39[15]) | 5;
    else
      v24 = 5;
    LODWORD(v39[15]) = v24;
    if ( !v15 || (*(_DWORD *)(v4 + 808) & 0xC000) != 0 )
    {
      if ( !v13 )
        goto LABEL_51;
      v24 |= 0x1000u;
      LODWORD(v39[15]) = v24;
    }
    v25 = *(unsigned int *)(v38 + 884);
    if ( *(_BYTE *)(v25 + v38 + 1299) || *(_BYTE *)(v25 + v4 + 1955) )
    {
      v26 = *(_DWORD *)(v4 + 4 * v25 + 1748);
      LODWORD(v39[15]) = v24 | 0x800;
      LODWORD(v39[17]) = v26;
    }
    if ( v9 )
    {
      if ( !*(_DWORD *)(v4 + 4LL * *(unsigned int *)(v38 + 884) + 1712)
        && (v28 = v37, (unsigned int)MmAreMdlPagesCached(v37))
        && (unsigned int)MmMdlPageContentsState(v28, 2) )
      {
        v7 = 0;
        v39[13] = (__int64)v22;
      }
      else
      {
        v39[13] = (__int64)v9;
      }
    }
    else
    {
      v27 = *(_QWORD *)(a1 + 8);
      v39[13] = (__int64)v22;
      if ( !(unsigned int)MmMdlPageContentsState(v27, 2) )
        LODWORD(v39[15]) |= 0x40u;
      v7 = 0;
    }
    FvePerfTraceDevIoCrypto(v4, FVE_PERF_IO_DECRYPT_START, a1, v39[2], v39[14]);
    v12 = FveParseBlockAndFilterEx(v39, &v40);
    FvePerfTraceDevIoCrypto(v4, FVE_PERF_IO_DECRYPT_STOP, a1, v39[2], v39[14]);
    LogFilterTrace((unsigned int)"Filter read fastio request", (unsigned int)&v40, v12, v4, v39[2], v39[14]);
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v30, v29) )
    {
      if ( v12 >= 0 )
      {
        v31 = *(_QWORD *)(v4 + 4752);
        if ( v31 && *(_DWORD *)(v31 + 88) && (HIDWORD(v41) == -1073741662 || DWORD2(v41) == 259) )
          goto LABEL_51;
        goto LABEL_53;
      }
    }
    else if ( v12 >= 0 )
    {
LABEL_53:
      if ( v9 && v7 )
        memmove(v22, v9, Size[0]);
    }
    DeInitializeFilterData(v4, v39);
    goto LABEL_57;
  }
LABEL_58:
  *(_DWORD *)(a1 + 48) = v12;
  *(_QWORD *)(a1 + 56) = 0;
  return result;
}

```

## disassembly

```asm
0x14009e540  mov     [rsp-8+arg_10], rbx
0x14009e545  push    rbp
0x14009e546  push    rsi
0x14009e547  push    rdi
0x14009e548  push    r12
0x14009e54a  push    r13
0x14009e54c  push    r14
0x14009e54e  push    r15
0x14009e550  lea     rbp, [rsp-0A0h]
0x14009e558  sub     rsp, 1A0h
0x14009e55f  mov     rax, cs:__security_cookie
0x14009e566  xor     rax, rsp
0x14009e569  mov     [rbp+0D0h+var_40], rax
0x14009e570  mov     r13, [rcx+0B8h]
0x14009e577  mov     rsi, rcx
0x14009e57a  mov     [rsp+1D0h+var_178], rdx
0x14009e57f  mov     rax, [r13+28h]
0x14009e583  mov     rbx, [rax+40h]
0x14009e587  mov     rax, [rbx+8]
0x14009e58b  mov     [rsp+1D0h+var_168], rax
0x14009e590  mov     eax, [rcx+78h]
0x14009e593  shr     rax, 10h
0x14009e597  test    al, al
0x14009e599  jz      short loc_14009E5A4
0x14009e59b  mov     r14, [rcx+80h]
0x14009e5a2  jmp     short loc_14009E5A7
0x14009e5a4  xor     r14d, r14d
0x14009e5a7  mov     rdi, [rcx+8]
0x14009e5ab  xorps   xmm0, xmm0
0x14009e5ae  lea     rcx, [rsp+1D0h+var_160]; void *
0x14009e5b3  mov     [rsp+1D0h+var_190], r14
0x14009e5b8  xor     edx, edx; Val
0x14009e5ba  mov     [rsp+1D0h+var_180], 0
0x14009e5c3  mov     r8d, 100h; Size
0x14009e5c9  mov     qword ptr [rsp+1D0h+Size+4], 0FFFFFFFFFFFFFFFFh
0x14009e5d2  movups  [rbp+0D0h+var_60], xmm0
0x14009e5d6  movups  [rbp+0D0h+var_50], xmm0
0x14009e5dd  call    memset
0x14009e5e2  mov     rax, [r14+38h]
0x14009e5e6  mov     r15d, 1
0x14009e5ec  mov     r12d, [rbx+328h]
0x14009e5f3  test    r12d, 17Fh
0x14009e5fa  mov     [rsp+1D0h+var_170], rax
0x14009e5ff  setnz   [rsp+1D0h+var_1A0]
0x14009e604  test    rax, rax
0x14009e607  jz      short loc_14009E641
0x14009e609  test    byte ptr [rdi+0Ah], 5
0x14009e60d  jz      short loc_14009E615
0x14009e60f  mov     r14, [rdi+18h]
0x14009e613  jmp     short loc_14009E649
0x14009e615  mov     [rsp+1D0h+Priority], 40000010h; Priority
0x14009e61d  xor     r9d, r9d; RequestedAddress
0x14009e620  mov     r8d, r15d; CacheType
0x14009e623  mov     [rsp+1D0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14009e62b  xor     edx, edx; AccessMode
0x14009e62d  mov     rcx, rdi; MemoryDescriptorList
0x14009e630  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14009e637  nop     dword ptr [rax+rax+00h]
0x14009e63c  mov     r14, rax
0x14009e63f  jmp     short loc_14009E649
0x14009e641  xor     r14d, r14d
0x14009e644  mov     [rsp+1D0h+var_170], rdi
0x14009e649  mov     rax, [r13+18h]
0x14009e64d  lea     r8, [rsp+1D0h+var_180]
0x14009e652  mov     [rsp+1D0h+var_188], rax
0x14009e657  lea     rdx, [rsp+1D0h+Size+4]
0x14009e65c  mov     eax, [r13+8]
0x14009e660  mov     rcx, rsi
0x14009e663  mov     dword ptr [rsp+1D0h+Size], eax
0x14009e667  call    FveIsIrpWithEfsOffload
0x14009e66c  mov     edi, [rsi+30h]
0x14009e66f  mov     r13b, al
0x14009e672  test    edi, edi
0x14009e674  js      loc_14009E974
0x14009e67a  mov     rax, ds:0FFFFF78000000008h
0x14009e684  test    r12b, 40h
0x14009e688  mov     rcx, [rsp+1D0h+var_190]
0x14009e68d  setz    dil
0x14009e691  mov     [rcx+18h], rax
0x14009e695  test    dword ptr [rbx+328h], 0C000h
0x14009e69f  jz      short loc_14009E6C8
0x14009e6a1  test    r13b, r13b
0x14009e6a4  jnz     short loc_14009E6C8
0x14009e6a6  xor     edi, edi
0x14009e6a8  test    r14, r14
0x14009e6ab  jz      loc_14009E95D
0x14009e6b1  mov     r8d, dword ptr [rsp+1D0h+Size]; Size
0x14009e6b6  mov     rdx, r14; Src
0x14009e6b9  mov     rcx, [rsp+1D0h+var_178]; void *
0x14009e6be  call    memmove
0x14009e6c3  jmp     loc_14009E95D
0x14009e6c8  xor     ecx, ecx
0x14009e6ca  test    r13b, r13b
0x14009e6cd  setnz   cl
0x14009e6d0  xor     eax, eax
0x14009e6d2  cmp     qword ptr [rsp+1D0h+Size+4], 0FFFFFFFFFFFFFFFFh
0x14009e6d8  setnz   al
0x14009e6db  cmp     ecx, eax
0x14009e6dd  jnz     loc_14009E90D
0x14009e6e3  and     dil, [rsp+1D0h+var_1A0]
0x14009e6e8  jz      short loc_14009E72F
0x14009e6ea  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14009e6ef  test    eax, eax
0x14009e6f1  jz      short loc_14009E6FC
0x14009e6f3  test    byte ptr [rbx+1143h], 8
0x14009e6fa  jnz     short loc_14009E70A
0x14009e6fc  mov     rax, [rbx+3D0h]
0x14009e703  cmp     [rax+0Ah], r15w
0x14009e708  jnz     short loc_14009E70E
0x14009e70a  xor     eax, eax
0x14009e70c  jmp     short loc_14009E717
0x14009e70e  mov     eax, [rax+1Ch]
0x14009e711  test    eax, eax
0x14009e713  cmovz   eax, r15d
0x14009e717  mov     ecx, [rbx+51Ch]
0x14009e71d  mov     r12, [rsp+1D0h+var_188]
0x14009e722  imul    rcx, rax
0x14009e726  cmp     r12, rcx
0x14009e729  setb    r8b
0x14009e72d  jmp     short loc_14009E737
0x14009e72f  mov     r12, [rsp+1D0h+var_188]
0x14009e734  xor     r8d, r8d
0x14009e737  mov     rax, [rsp+1D0h+var_180]
0x14009e73c  lea     rdx, [rsp+1D0h+var_160]
0x14009e741  mov     r9, qword ptr [rsp+1D0h+Size+4]
0x14009e746  mov     rcx, rbx
0x14009e749  mov     qword ptr [rsp+1D0h+Priority], 0
0x14009e752  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rax
0x14009e757  call    InitializeFilterData
0x14009e75c  mov     eax, dword ptr [rsp+1D0h+Size]
0x14009e760  test    r14, r14
0x14009e763  mov     [rbp+0D0h+var_F0], eax
0x14009e766  mov     [rbp+0D0h+var_150], r12
0x14009e76a  mov     r12, [rsp+1D0h+var_178]
0x14009e76f  mov     rax, r12
0x14009e772  cmovnz  rax, r14
0x14009e776  mov     [rbp+0D0h+var_100], rax
0x14009e77a  lea     rax, FveFilteredRead
0x14009e781  mov     [rbp+0D0h+var_108], rax
0x14009e785  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14009e78a  test    eax, eax
0x14009e78c  jz      short loc_14009E796
0x14009e78e  mov     ecx, [rbp+0D0h+var_E8]
0x14009e791  or      ecx, 5
0x14009e794  jmp     short loc_14009E79B
0x14009e796  mov     ecx, 5
0x14009e79b  mov     [rbp+0D0h+var_E8], ecx
0x14009e79e  test    dil, dil
0x14009e7a1  jz      short loc_14009E7AF
0x14009e7a3  test    dword ptr [rbx+328h], 0C000h
0x14009e7ad  jz      short loc_14009E7BF
0x14009e7af  test    r13b, r13b
0x14009e7b2  jz      loc_14009E90D
0x14009e7b8  bts     ecx, 0Ch
0x14009e7bc  mov     [rbp+0D0h+var_E8], ecx
0x14009e7bf  mov     rdx, [rsp+1D0h+var_168]
0x14009e7c4  mov     eax, [rdx+374h]
0x14009e7ca  cmp     byte ptr [rax+rdx+513h], 0
0x14009e7d2  jnz     short loc_14009E7DE
0x14009e7d4  cmp     byte ptr [rax+rbx+7A3h], 0
0x14009e7dc  jz      short loc_14009E7EF
0x14009e7de  mov     eax, [rbx+rax*4+6D4h]
0x14009e7e5  bts     ecx, 0Bh
0x14009e7e9  mov     [rbp+0D0h+var_E8], ecx
0x14009e7ec  mov     [rbp+0D0h+var_D8], eax
0x14009e7ef  test    r14, r14
0x14009e7f2  jnz     short loc_14009E819
0x14009e7f4  mov     rcx, [rsi+8]
0x14009e7f8  lea     edx, [r14+2]
0x14009e7fc  mov     [rbp+0D0h+var_F8], r12
0x14009e800  call    cs:__imp_MmMdlPageContentsState
0x14009e807  nop     dword ptr [rax+rax+00h]
0x14009e80c  test    eax, eax
0x14009e80e  jnz     short loc_14009E814
0x14009e810  or      [rbp+0D0h+var_E8], 40h
0x14009e814  xor     r15b, r15b
0x14009e817  jmp     short loc_14009E866
0x14009e819  mov     eax, [rdx+374h]
0x14009e81f  cmp     dword ptr [rbx+rax*4+6B0h], 0
0x14009e827  jnz     short loc_14009E862
0x14009e829  mov     rdi, [rsp+1D0h+var_170]
0x14009e82e  mov     rcx, rdi
0x14009e831  call    cs:__imp_MmAreMdlPagesCached
0x14009e838  nop     dword ptr [rax+rax+00h]
0x14009e83d  test    eax, eax
0x14009e83f  jz      short loc_14009E862
0x14009e841  mov     edx, 2
0x14009e846  mov     rcx, rdi
0x14009e849  call    cs:__imp_MmMdlPageContentsState
0x14009e850  nop     dword ptr [rax+rax+00h]
0x14009e855  test    eax, eax
0x14009e857  jz      short loc_14009E862
0x14009e859  xor     r15b, r15b
0x14009e85c  mov     [rbp+0D0h+var_F8], r12
0x14009e860  jmp     short loc_14009E866
0x14009e862  mov     [rbp+0D0h+var_F8], r14
0x14009e866  mov     eax, [rbp+0D0h+var_F0]
0x14009e869  lea     rdx, FVE_PERF_IO_DECRYPT_START
0x14009e870  mov     r9, [rbp+0D0h+var_150]
0x14009e874  mov     r8, rsi
0x14009e877  mov     rcx, rbx
0x14009e87a  mov     [rsp+1D0h+BugCheckOnFailure], eax
0x14009e87e  call    FvePerfTraceDevIoCrypto
0x14009e883  lea     rdx, [rbp+0D0h+var_60]
0x14009e887  lea     rcx, [rsp+1D0h+var_160]
0x14009e88c  call    FveParseBlockAndFilterEx
0x14009e891  mov     ecx, [rbp+0D0h+var_F0]
0x14009e894  lea     rdx, FVE_PERF_IO_DECRYPT_STOP
0x14009e89b  mov     r9, [rbp+0D0h+var_150]
0x14009e89f  mov     r8, rsi
0x14009e8a2  mov     [rsp+1D0h+BugCheckOnFailure], ecx
0x14009e8a6  mov     edi, eax
0x14009e8a8  mov     rcx, rbx
0x14009e8ab  call    FvePerfTraceDevIoCrypto
0x14009e8b0  mov     ecx, [rbp+0D0h+var_F0]
0x14009e8b3  lea     rdx, [rbp+0D0h+var_60]
0x14009e8b7  mov     [rsp+1D0h+Priority], ecx
0x14009e8bb  mov     r9, rbx
0x14009e8be  mov     rcx, [rbp+0D0h+var_150]
0x14009e8c2  mov     r8d, edi
0x14009e8c5  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rcx
0x14009e8ca  lea     rcx, aFilterReadFast; "Filter read fastio request"
0x14009e8d1  call    LogFilterTrace
0x14009e8d6  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x14009e8db  test    eax, eax
0x14009e8dd  jz      short loc_14009E932
0x14009e8df  test    edi, edi
0x14009e8e1  js      short loc_14009E950
0x14009e8e3  mov     rax, [rbx+1290h]
0x14009e8ea  test    rax, rax
0x14009e8ed  jz      short loc_14009E936
0x14009e8ef  cmp     dword ptr [rax+58h], 0
0x14009e8f3  jz      short loc_14009E936
0x14009e8f5  cmp     dword ptr [rbp+0D0h+var_50+0Ch], 0C00000A2h
0x14009e8ff  jz      short loc_14009E90D
0x14009e901  cmp     dword ptr [rbp+0D0h+var_50+8], 103h
0x14009e90b  jnz     short loc_14009E936
0x14009e90d  xor     r9d, r9d; BugCheckParameter3
0x14009e910  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], 0; BugCheckParameter4
0x14009e919  xor     r8d, r8d; BugCheckParameter2
0x14009e91c  mov     ecx, 120h; BugCheckCode
0x14009e921  lea     edx, [r9+0Ch]; BugCheckParameter1
0x14009e925  call    cs:__imp_KeBugCheckEx
0x14009e932  test    edi, edi
0x14009e934  js      short loc_14009E950
0x14009e936  test    r14, r14
0x14009e939  jz      short loc_14009E950
0x14009e93b  test    r15b, r15b
0x14009e93e  jz      short loc_14009E950
0x14009e940  mov     r8d, dword ptr [rsp+1D0h+Size]; Size
0x14009e945  mov     rdx, r14; Src
0x14009e948  mov     rcx, r12; void *
0x14009e94b  call    memmove
0x14009e950  lea     rdx, [rsp+1D0h+var_160]
0x14009e955  mov     rcx, rbx
0x14009e958  call    DeInitializeFilterData
0x14009e95d  mov     r8, [rsp+1D0h+var_190]
0x14009e962  mov     rax, ds:0FFFFF78000000008h
0x14009e96c  mov     [r8+20h], rax
0x14009e970  test    edi, edi
0x14009e972  jns     short loc_14009E97F
0x14009e974  mov     [rsi+30h], edi
0x14009e977  mov     qword ptr [rsi+38h], 0
0x14009e97f  mov     rcx, [rbp+0D0h+var_40]
0x14009e986  xor     rcx, rsp; StackCookie
0x14009e989  call    __security_check_cookie
0x14009e98e  mov     rbx, [rsp+1D0h+arg_10]
0x14009e996  add     rsp, 1A0h
0x14009e99d  pop     r15
0x14009e99f  pop     r14
0x14009e9a1  pop     r13
0x14009e9a3  pop     r12
0x14009e9a5  pop     rdi
0x14009e9a6  pop     rsi
0x14009e9a7  pop     rbp
0x14009e9a8  retn
```
