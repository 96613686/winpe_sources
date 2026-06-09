# PbmmCreateAllocator(VIDMM_PHYSICAL_ADAPTER *,uint,PBMM_SEGMENT_DESC const *,PBMM_PAGE_SIZE,PBMM_ALLOCATOR * *)

- ea: `0x14004b4dc`
- end: `0x14004b741`
- name: `?PbmmCreateAllocator@@YAJPEAUVIDMM_PHYSICAL_ADAPTER@@IPEBUPBMM_SEGMENT_DESC@@W4PBMM_PAGE_SIZE@@PEAPEAUPBMM_ALLOCATOR@@@Z`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400ccb9c`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002ed58`
- `0x14004b4dc`
- `0x14004b748`
- `0x14004bd68`
- `0x14004de8c`
- `0x140059380`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004b5cd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004b5cd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14004b6b5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14004b6b5`
- `watchdog!WdLogSingleEntry0` at `0x14004b638`
- `watchdog!WdLogSingleEntry0` at `0x14004b6ec`
- `watchdog!WdLogSingleEntry0` at `0x14004b638`
- `watchdog!WdLogSingleEntry0` at `0x14004b6ec`
- `watchdog!WdLogSingleEntry1` at `0x14004b510`
- `watchdog!WdLogSingleEntry1` at `0x14004b510`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14004b6a9`

## pseudocode

```c
__int64 __fastcall PbmmCreateAllocator(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned __int64 v6; // rbp
  int v8; // ecx
  int v9; // r8d
  unsigned int i; // ebx
  char *v12; // rax
  char *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // ecx
  int v17; // r8d
  unsigned int v18; // esi
  unsigned int j; // ebx
  int Segment; // eax
  __int64 v21; // rcx
  int v22; // ecx
  int v23; // r8d

  v6 = a2;
  *a5 = 0;
  if ( a2 <= 0x20 )
  {
    for ( i = 0; i < (unsigned int)v6; ++i )
    {
      if ( !(unsigned __int8)ValidateSegmentDesc(i, a3 + 16LL * i) )
        return 3221225485LL;
    }
    v12 = (char *)operator new(160, 846029392, 64);
    v13 = v12;
    if ( v12 )
    {
      memset(v12, 0, 0xA0u);
      ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 32), 0, 0, PagedPool, 0, 0x50u, 0x336D6250u, 0);
      *((_QWORD *)v13 + 17) = v13 + 128;
      *((_QWORD *)v13 + 16) = v13 + 128;
      v14 = 8 * v6;
      *(_QWORD *)v13 = a1;
      *((_DWORD *)v13 + 2) = v6;
      if ( !is_mul_ok(v6, 8u) )
        v14 = -1;
      *((_DWORD *)v13 + 36) = 9;
      *((_DWORD *)v13 + 37) = 511;
      v15 = operator new[](v14, 879583824, 256);
      *((_QWORD *)v13 + 2) = v15;
      if ( v15 )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= (unsigned int)v6 )
          {
            *a5 = v13;
            return 0;
          }
          Segment = PbmmCreateSegment(
                      (struct PBMM_ALLOCATOR *)v13,
                      (const struct PBMM_SEGMENT_DESC *)(a3 + 16LL * j),
                      j,
                      (struct PBMM_SEGMENT **)(*((_QWORD *)v13 + 2) + 8LL * j));
          v18 = Segment;
          if ( Segment < 0 )
            break;
        }
        if ( g_IsInternalReleaseOrDbg )
        {
          *(_QWORD *)(WdLogNewEntry5_WdTrace(v21) + 24) = Segment;
          WdLogGlobalForLineNumber = 1176;
        }
      }
      else
      {
        _InterlockedIncrement(&dword_140087830);
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 1163;
        DxgkLogInternalTriageEvent(
          v16,
          262145,
          v17,
          (unsigned int)L"Failed to allocate allocator segment array",
          1163,
          0,
          0,
          0);
        v18 = -1073741801;
      }
      PbmmDestroyAllocator((struct PBMM_ALLOCATOR *)v13);
    }
    else
    {
      _InterlockedIncrement(&dword_14008782C);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1146;
      DxgkLogInternalTriageEvent(v22, 262145, v23, (unsigned int)L"Failed to allocate PBMM_ALLOCATOR", 1146, 0, 0, 0);
      return (unsigned int)-1073741801;
    }
    return v18;
  }
  else
  {
    WdLogSingleEntry1(1, 32);
    WdLogGlobalForLineNumber = 1128;
    DxgkLogInternalTriageEvent(
      v8,
      0x40000,
      v9,
      (unsigned int)L"Segment count exceeds maximum segment count (%u)",
      32,
      0,
      0,
      0);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14004b4dc  push    rbx
0x14004b4de  push    rbp
0x14004b4df  push    rsi
0x14004b4e0  push    rdi
0x14004b4e1  push    r12
0x14004b4e3  push    r13
0x14004b4e5  push    r14
0x14004b4e7  push    r15
0x14004b4e9  sub     rsp, 58h
0x14004b4ed  mov     r14, [rsp+98h+arg_20]
0x14004b4f5  xor     r13d, r13d
0x14004b4f8  mov     r15, r8
0x14004b4fb  mov     ebp, edx
0x14004b4fd  mov     rsi, rcx
0x14004b500  lea     ebx, [r13+20h]
0x14004b504  mov     [r14], r13
0x14004b507  cmp     edx, ebx
0x14004b509  jbe     short loc_14004B555
0x14004b50b  mov     edx, ebx
0x14004b50d  lea     ecx, [rbx-1Fh]
0x14004b510  call    cs:__imp_WdLogSingleEntry1
0x14004b517  nop     dword ptr [rax+rax+00h]
0x14004b51c  mov     qword ptr [rsp+98h+Depth], r13
0x14004b521  lea     r9, aSegmentCountEx; "Segment count exceeds maximum segment c"...
0x14004b528  mov     qword ptr [rsp+98h+Tag], r13
0x14004b52d  mov     edx, 40000h
0x14004b532  mov     [rsp+98h+Size], r13
0x14004b537  mov     qword ptr [rsp+98h+Flags], rbx
0x14004b53c  mov     cs:WdLogGlobalForLineNumber, 468h
0x14004b546  call    DxgkLogInternalTriageEvent
0x14004b54b  mov     eax, 0C000000Dh
0x14004b550  jmp     loc_14004B72F
0x14004b555  mov     ebx, r13d
0x14004b558  cmp     ebx, ebp
0x14004b55a  jnb     short loc_14004B574
0x14004b55c  mov     edx, ebx
0x14004b55e  mov     ecx, ebx
0x14004b560  shl     rdx, 4
0x14004b564  add     rdx, r15
0x14004b567  call    ValidateSegmentDesc
0x14004b56c  test    al, al
0x14004b56e  jz      short loc_14004B54B
0x14004b570  inc     ebx
0x14004b572  jmp     short loc_14004B558
0x14004b574  mov     ebx, 0A0h
0x14004b579  mov     edx, 326D6250h
0x14004b57e  mov     ecx, ebx
0x14004b580  lea     r8d, [rbx-60h]
0x14004b584  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14004b589  mov     rdi, rax
0x14004b58c  test    rax, rax
0x14004b58f  jz      loc_14004B6E0
0x14004b595  mov     r8d, ebx; Size
0x14004b598  xor     edx, edx; Val
0x14004b59a  mov     rcx, rax; void *
0x14004b59d  call    memset
0x14004b5a2  mov     [rsp+98h+Depth], r13w; Depth
0x14004b5a8  lea     rcx, [rdi+20h]; Lookaside
0x14004b5ac  mov     [rsp+98h+Tag], 336D6250h; Tag
0x14004b5b4  mov     r9d, 1; PoolType
0x14004b5ba  mov     [rsp+98h+Size], 50h ; 'P'; Size
0x14004b5c3  xor     r8d, r8d; Free
0x14004b5c6  xor     edx, edx; Allocate
0x14004b5c8  mov     [rsp+98h+Flags], r13d; Flags
0x14004b5cd  call    cs:__imp_ExInitializeLookasideListEx
0x14004b5d4  nop     dword ptr [rax+rax+00h]
0x14004b5d9  lea     rax, [rdi+80h]
0x14004b5e0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004b5e7  mov     [rax+8], rax
0x14004b5eb  lea     r8d, [rbx+60h]
0x14004b5ef  mov     [rax], rax
0x14004b5f2  mov     eax, 8
0x14004b5f7  mul     rbp
0x14004b5fa  mov     edx, 346D6250h
0x14004b5ff  mov     [rdi], rsi
0x14004b602  mov     [rdi+8], ebp
0x14004b605  cmovb   rax, rcx
0x14004b609  mov     dword ptr [rdi+90h], 9
0x14004b613  mov     rcx, rax
0x14004b616  mov     dword ptr [rdi+94h], 1FFh
0x14004b620  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14004b625  mov     [rdi+10h], rax
0x14004b629  test    rax, rax
0x14004b62c  jnz     short loc_14004B67B
0x14004b62e  lock inc cs:dword_140087830
0x14004b635  lea     ecx, [rax+6]
0x14004b638  call    cs:__imp_WdLogSingleEntry0
0x14004b63f  nop     dword ptr [rax+rax+00h]
0x14004b644  mov     qword ptr [rsp+98h+Depth], r13
0x14004b649  lea     r9, aFailedToAlloca_96; "Failed to allocate allocator segment ar"...
0x14004b650  mov     eax, 48Bh
0x14004b655  mov     qword ptr [rsp+98h+Tag], r13
0x14004b65a  mov     [rsp+98h+Size], r13
0x14004b65f  mov     edx, 40001h
0x14004b664  mov     cs:WdLogGlobalForLineNumber, eax
0x14004b66a  mov     qword ptr [rsp+98h+Flags], rax
0x14004b66f  call    DxgkLogInternalTriageEvent
0x14004b674  mov     esi, 0C0000017h
0x14004b679  jmp     short loc_14004B6CF
0x14004b67b  mov     ebx, r13d
0x14004b67e  cmp     ebx, ebp
0x14004b680  jnb     short loc_14004B6D9
0x14004b682  mov     rax, [rdi+10h]
0x14004b686  mov     r8d, ebx; unsigned int
0x14004b689  mov     edx, ebx
0x14004b68b  mov     rcx, rdi; struct PBMM_ALLOCATOR *
0x14004b68e  lea     r9, [rax+rdx*8]; struct PBMM_SEGMENT **
0x14004b692  shl     rdx, 4
0x14004b696  add     rdx, r15; struct PBMM_SEGMENT_DESC *
0x14004b699  call    ?PbmmCreateSegment@@YAJPEAUPBMM_ALLOCATOR@@PEBUPBMM_SEGMENT_DESC@@IPEAPEAUPBMM_SEGMENT@@@Z; PbmmCreateSegment(PBMM_ALLOCATOR *,PBMM_SEGMENT_DESC const *,uint,PBMM_SEGMENT * *)
0x14004b69e  movsxd  rsi, eax
0x14004b6a1  test    eax, eax
0x14004b6a3  js      short loc_14004B6A9
0x14004b6a5  inc     ebx
0x14004b6a7  jmp     short loc_14004B67E
0x14004b6a9  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14004b6b0  cmp     [rax], r13b
0x14004b6b3  jz      short loc_14004B6CF
0x14004b6b5  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14004b6bc  nop     dword ptr [rax+rax+00h]
0x14004b6c1  mov     [rax+18h], rsi
0x14004b6c5  mov     cs:WdLogGlobalForLineNumber, 498h
0x14004b6cf  mov     rcx, rdi; struct PBMM_ALLOCATOR *
0x14004b6d2  call    ?PbmmDestroyAllocator@@YAXPEAUPBMM_ALLOCATOR@@@Z; PbmmDestroyAllocator(PBMM_ALLOCATOR *)
0x14004b6d7  jmp     short loc_14004B72D
0x14004b6d9  mov     [r14], rdi
0x14004b6dc  xor     eax, eax
0x14004b6de  jmp     short loc_14004B72F
0x14004b6e0  lock inc cs:dword_14008782C
0x14004b6e7  mov     ecx, 6
0x14004b6ec  call    cs:__imp_WdLogSingleEntry0
0x14004b6f3  nop     dword ptr [rax+rax+00h]
0x14004b6f8  mov     qword ptr [rsp+98h+Depth], r13
0x14004b6fd  lea     r9, aFailedToAlloca_71; "Failed to allocate PBMM_ALLOCATOR"
0x14004b704  mov     eax, 47Ah
0x14004b709  mov     qword ptr [rsp+98h+Tag], r13
0x14004b70e  mov     [rsp+98h+Size], r13
0x14004b713  mov     edx, 40001h
0x14004b718  mov     cs:WdLogGlobalForLineNumber, eax
0x14004b71e  mov     qword ptr [rsp+98h+Flags], rax
0x14004b723  call    DxgkLogInternalTriageEvent
0x14004b728  mov     esi, 0C0000017h
0x14004b72d  mov     eax, esi
0x14004b72f  add     rsp, 58h
0x14004b733  pop     r15
0x14004b735  pop     r14
0x14004b737  pop     r13
0x14004b739  pop     r12
0x14004b73b  pop     rdi
0x14004b73c  pop     rsi
0x14004b73d  pop     rbp
0x14004b73e  pop     rbx
0x14004b73f  retn
```
