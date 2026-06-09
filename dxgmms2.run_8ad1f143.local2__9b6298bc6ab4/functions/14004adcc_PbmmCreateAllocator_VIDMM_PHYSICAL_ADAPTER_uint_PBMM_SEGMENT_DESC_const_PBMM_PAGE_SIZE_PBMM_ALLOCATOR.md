# PbmmCreateAllocator(VIDMM_PHYSICAL_ADAPTER *,uint,PBMM_SEGMENT_DESC const *,PBMM_PAGE_SIZE,PBMM_ALLOCATOR * *)

- ea: `0x14004adcc`
- end: `0x14004b031`
- name: `?PbmmCreateAllocator@@YAJPEAUVIDMM_PHYSICAL_ADAPTER@@IPEBUPBMM_SEGMENT_DESC@@W4PBMM_PAGE_SIZE@@PEAPEAUPBMM_ALLOCATOR@@@Z`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400c703c`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140031178`
- `0x14004adcc`
- `0x14004b038`
- `0x14004b658`
- `0x14004d77c`
- `0x140058ac0`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004aebd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14004aebd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14004afa5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14004afa5`
- `watchdog!WdLogSingleEntry0` at `0x14004af28`
- `watchdog!WdLogSingleEntry0` at `0x14004afdc`
- `watchdog!WdLogSingleEntry0` at `0x14004af28`
- `watchdog!WdLogSingleEntry0` at `0x14004afdc`
- `watchdog!WdLogSingleEntry1` at `0x14004ae00`
- `watchdog!WdLogSingleEntry1` at `0x14004ae00`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14004af99`

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
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // r8d

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
          *(_QWORD *)(WdLogNewEntry5_WdTrace(v22, v21) + 24) = Segment;
          WdLogGlobalForLineNumber = 1176;
        }
      }
      else
      {
        _InterlockedIncrement(&dword_140086850);
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
      _InterlockedIncrement(&dword_14008684C);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1146;
      DxgkLogInternalTriageEvent(v23, 262145, v24, (unsigned int)L"Failed to allocate PBMM_ALLOCATOR", 1146, 0, 0, 0);
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
0x14004adcc  push    rbx
0x14004adce  push    rbp
0x14004adcf  push    rsi
0x14004add0  push    rdi
0x14004add1  push    r12
0x14004add3  push    r13
0x14004add5  push    r14
0x14004add7  push    r15
0x14004add9  sub     rsp, 58h
0x14004addd  mov     r14, [rsp+98h+arg_20]
0x14004ade5  xor     r13d, r13d
0x14004ade8  mov     r15, r8
0x14004adeb  mov     ebp, edx
0x14004aded  mov     rsi, rcx
0x14004adf0  lea     ebx, [r13+20h]
0x14004adf4  mov     [r14], r13
0x14004adf7  cmp     edx, ebx
0x14004adf9  jbe     short loc_14004AE45
0x14004adfb  mov     edx, ebx
0x14004adfd  lea     ecx, [rbx-1Fh]
0x14004ae00  call    cs:__imp_WdLogSingleEntry1
0x14004ae07  nop     dword ptr [rax+rax+00h]
0x14004ae0c  mov     qword ptr [rsp+98h+Depth], r13
0x14004ae11  lea     r9, aSegmentCountEx; "Segment count exceeds maximum segment c"...
0x14004ae18  mov     qword ptr [rsp+98h+Tag], r13
0x14004ae1d  mov     edx, 40000h
0x14004ae22  mov     [rsp+98h+Size], r13
0x14004ae27  mov     qword ptr [rsp+98h+Flags], rbx
0x14004ae2c  mov     cs:WdLogGlobalForLineNumber, 468h
0x14004ae36  call    DxgkLogInternalTriageEvent
0x14004ae3b  mov     eax, 0C000000Dh
0x14004ae40  jmp     loc_14004B01F
0x14004ae45  mov     ebx, r13d
0x14004ae48  cmp     ebx, ebp
0x14004ae4a  jnb     short loc_14004AE64
0x14004ae4c  mov     edx, ebx
0x14004ae4e  mov     ecx, ebx
0x14004ae50  shl     rdx, 4
0x14004ae54  add     rdx, r15
0x14004ae57  call    ValidateSegmentDesc
0x14004ae5c  test    al, al
0x14004ae5e  jz      short loc_14004AE3B
0x14004ae60  inc     ebx
0x14004ae62  jmp     short loc_14004AE48
0x14004ae64  mov     ebx, 0A0h
0x14004ae69  mov     edx, 326D6250h
0x14004ae6e  mov     ecx, ebx
0x14004ae70  lea     r8d, [rbx-60h]
0x14004ae74  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14004ae79  mov     rdi, rax
0x14004ae7c  test    rax, rax
0x14004ae7f  jz      loc_14004AFD0
0x14004ae85  mov     r8d, ebx; Size
0x14004ae88  xor     edx, edx; Val
0x14004ae8a  mov     rcx, rax; void *
0x14004ae8d  call    memset
0x14004ae92  mov     [rsp+98h+Depth], r13w; Depth
0x14004ae98  lea     rcx, [rdi+20h]; Lookaside
0x14004ae9c  mov     [rsp+98h+Tag], 336D6250h; Tag
0x14004aea4  mov     r9d, 1; PoolType
0x14004aeaa  mov     [rsp+98h+Size], 50h ; 'P'; Size
0x14004aeb3  xor     r8d, r8d; Free
0x14004aeb6  xor     edx, edx; Allocate
0x14004aeb8  mov     [rsp+98h+Flags], r13d; Flags
0x14004aebd  call    cs:__imp_ExInitializeLookasideListEx
0x14004aec4  nop     dword ptr [rax+rax+00h]
0x14004aec9  lea     rax, [rdi+80h]
0x14004aed0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004aed7  mov     [rax+8], rax
0x14004aedb  lea     r8d, [rbx+60h]
0x14004aedf  mov     [rax], rax
0x14004aee2  mov     eax, 8
0x14004aee7  mul     rbp
0x14004aeea  mov     edx, 346D6250h
0x14004aeef  mov     [rdi], rsi
0x14004aef2  mov     [rdi+8], ebp
0x14004aef5  cmovb   rax, rcx
0x14004aef9  mov     dword ptr [rdi+90h], 9
0x14004af03  mov     rcx, rax
0x14004af06  mov     dword ptr [rdi+94h], 1FFh
0x14004af10  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14004af15  mov     [rdi+10h], rax
0x14004af19  test    rax, rax
0x14004af1c  jnz     short loc_14004AF6B
0x14004af1e  lock inc cs:dword_140086850
0x14004af25  lea     ecx, [rax+6]
0x14004af28  call    cs:__imp_WdLogSingleEntry0
0x14004af2f  nop     dword ptr [rax+rax+00h]
0x14004af34  mov     qword ptr [rsp+98h+Depth], r13
0x14004af39  lea     r9, aFailedToAlloca_92; "Failed to allocate allocator segment ar"...
0x14004af40  mov     eax, 48Bh
0x14004af45  mov     qword ptr [rsp+98h+Tag], r13
0x14004af4a  mov     [rsp+98h+Size], r13
0x14004af4f  mov     edx, 40001h
0x14004af54  mov     cs:WdLogGlobalForLineNumber, eax
0x14004af5a  mov     qword ptr [rsp+98h+Flags], rax
0x14004af5f  call    DxgkLogInternalTriageEvent
0x14004af64  mov     esi, 0C0000017h
0x14004af69  jmp     short loc_14004AFBF
0x14004af6b  mov     ebx, r13d
0x14004af6e  cmp     ebx, ebp
0x14004af70  jnb     short loc_14004AFC9
0x14004af72  mov     rax, [rdi+10h]
0x14004af76  mov     r8d, ebx; unsigned int
0x14004af79  mov     edx, ebx
0x14004af7b  mov     rcx, rdi; struct PBMM_ALLOCATOR *
0x14004af7e  lea     r9, [rax+rdx*8]; struct PBMM_SEGMENT **
0x14004af82  shl     rdx, 4
0x14004af86  add     rdx, r15; struct PBMM_SEGMENT_DESC *
0x14004af89  call    ?PbmmCreateSegment@@YAJPEAUPBMM_ALLOCATOR@@PEBUPBMM_SEGMENT_DESC@@IPEAPEAUPBMM_SEGMENT@@@Z; PbmmCreateSegment(PBMM_ALLOCATOR *,PBMM_SEGMENT_DESC const *,uint,PBMM_SEGMENT * *)
0x14004af8e  movsxd  rsi, eax
0x14004af91  test    eax, eax
0x14004af93  js      short loc_14004AF99
0x14004af95  inc     ebx
0x14004af97  jmp     short loc_14004AF6E
0x14004af99  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14004afa0  cmp     [rax], r13b
0x14004afa3  jz      short loc_14004AFBF
0x14004afa5  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14004afac  nop     dword ptr [rax+rax+00h]
0x14004afb1  mov     [rax+18h], rsi
0x14004afb5  mov     cs:WdLogGlobalForLineNumber, 498h
0x14004afbf  mov     rcx, rdi; struct PBMM_ALLOCATOR *
0x14004afc2  call    ?PbmmDestroyAllocator@@YAXPEAUPBMM_ALLOCATOR@@@Z; PbmmDestroyAllocator(PBMM_ALLOCATOR *)
0x14004afc7  jmp     short loc_14004B01D
0x14004afc9  mov     [r14], rdi
0x14004afcc  xor     eax, eax
0x14004afce  jmp     short loc_14004B01F
0x14004afd0  lock inc cs:dword_14008684C
0x14004afd7  mov     ecx, 6
0x14004afdc  call    cs:__imp_WdLogSingleEntry0
0x14004afe3  nop     dword ptr [rax+rax+00h]
0x14004afe8  mov     qword ptr [rsp+98h+Depth], r13
0x14004afed  lea     r9, aFailedToAlloca_67; "Failed to allocate PBMM_ALLOCATOR"
0x14004aff4  mov     eax, 47Ah
0x14004aff9  mov     qword ptr [rsp+98h+Tag], r13
0x14004affe  mov     [rsp+98h+Size], r13
0x14004b003  mov     edx, 40001h
0x14004b008  mov     cs:WdLogGlobalForLineNumber, eax
0x14004b00e  mov     qword ptr [rsp+98h+Flags], rax
0x14004b013  call    DxgkLogInternalTriageEvent
0x14004b018  mov     esi, 0C0000017h
0x14004b01d  mov     eax, esi
0x14004b01f  add     rsp, 58h
0x14004b023  pop     r15
0x14004b025  pop     r14
0x14004b027  pop     r13
0x14004b029  pop     r12
0x14004b02b  pop     rdi
0x14004b02c  pop     rsi
0x14004b02d  pop     rbp
0x14004b02e  pop     rbx
0x14004b02f  retn
```
