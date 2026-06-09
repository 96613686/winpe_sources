# VIDMM_GLOBAL::VidMmInitializePagingProcess(void)

- ea: `0x1400bea60`
- end: `0x1400bedf9`
- name: `?VidMmInitializePagingProcess@VIDMM_GLOBAL@@QEAAJXZ`
- size: `921`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140047250`

## callees

- `0x140003490`
- `0x140004268`
- `0x140054a20`
- `0x140058f50`
- `0x140059030`
- `0x14009edf0`
- `0x1400b6f68`
- `0x1400bea60`
- `0x1400c32e0`
- `0x1400c6c64`
- `0x1400c88d0`
- `0x1400e177c`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400beab3`
- `ntoskrnl!KeStackAttachProcess` at `0x1400beab3`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400bedca`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400bedca`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400bea9a`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bebaa`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bebaa`
- `watchdog!WdLogSingleEntry0` at `0x1400beada`
- `watchdog!WdLogSingleEntry0` at `0x1400beb34`
- `watchdog!WdLogSingleEntry0` at `0x1400bebcf`
- `watchdog!WdLogSingleEntry0` at `0x1400bec1c`
- `watchdog!WdLogSingleEntry0` at `0x1400bec4a`
- `watchdog!WdLogSingleEntry0` at `0x1400beada`
- `watchdog!WdLogSingleEntry0` at `0x1400beb34`
- `watchdog!WdLogSingleEntry0` at `0x1400bebcf`
- `watchdog!WdLogSingleEntry0` at `0x1400bec1c`
- `watchdog!WdLogSingleEntry0` at `0x1400bec4a`
- `watchdog!WdLogSingleEntry1` at `0x1400bec94`
- `watchdog!WdLogSingleEntry1` at `0x1400bed49`
- `watchdog!WdLogSingleEntry1` at `0x1400bec94`
- `watchdog!WdLogSingleEntry1` at `0x1400bed49`

## string_xrefs

- `0x1400beb45`: `Failed to create scheduler system devices`
- `0x1400bec5b`: `Failed to create paging fence objects`
- `0x1400bed5a`: `Failed to create scheduling logs. ntStatus=0x%.8x`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::VidMmInitializePagingProcess(VIDMM_GLOBAL *this)
{
  __int64 v2; // rdi
  int v3; // ecx
  int v4; // r8d
  __int64 v5; // rax
  const wchar_t *v6; // r9
  __int64 v7; // rax
  struct VIDMM_PAGING *v8; // rbx
  int v9; // ecx
  int v10; // r8d
  unsigned int i; // ebx
  int inited; // eax
  __int64 v13; // rax
  __int64 v14; // rbp
  unsigned int j; // ebx
  struct _VIDSCH_NODE **v16; // r8
  unsigned int v17; // edx
  struct _VIDSCH_NODE **v18; // rax
  int NodeSchedulingLog; // eax
  unsigned int k; // ebx
  _DWORD *v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-A8h]
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-78h] BYREF

  *((_BYTE *)this + 37229) = 1;
  memset(&ApcState, 0, sizeof(ApcState));
  KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
  LODWORD(v2) = VIDMM_PAGING_PROCESS::InitPagingProcess((VIDMM_GLOBAL *)((char *)this + 36672), this);
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25232;
    v6 = L"Failed to initialize paging process";
    goto LABEL_3;
  }
  LODWORD(v2) = VidSchCreateSystemDevices(*(struct _VIDSCH_GLOBAL **)(*((_QWORD *)this + 2) + 744LL));
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25243;
    v6 = L"Failed to create scheduler system devices";
    goto LABEL_3;
  }
  LODWORD(v2) = VIDMM_DEVICE::CreatePagingProcessPagingQueues(*((VIDMM_DEVICE **)this + 4585));
  if ( (int)v2 < 0 )
    goto LABEL_35;
  v7 = operator new(184, 1833789782, 64);
  v8 = (struct VIDMM_PAGING *)v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = this;
    *(_QWORD *)(v7 + 8) = *(_QWORD *)this;
    *(_QWORD *)(v7 + 48) = v7;
    *(_QWORD *)(v7 + 56) = 0;
    *(_QWORD *)(v7 + 64) = 0;
    *(_DWORD *)(v7 + 80) = 0;
    *(_QWORD *)(v7 + 176) = 1;
    KeInitializeSemaphore((PRKSEMAPHORE)(v7 + 16), 1, 1);
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 6) = v8;
  if ( !v8 )
  {
    _InterlockedAdd(&dword_1400878AC, 1u);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 25261;
    DxgkLogInternalTriageEvent(
      v9,
      262145,
      v10,
      (unsigned int)L"Failed to allocate memory for VIDMM_PAGING structure",
      25261,
      0,
      0,
      0);
    goto LABEL_35;
  }
  LODWORD(v2) = VidMmInitializePaging(v8);
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25270;
    v6 = L"Failed to init paging structure and DMA pools.\n";
    goto LABEL_3;
  }
  LODWORD(v2) = VIDMM_GLOBAL::CreatePagingFenceObjects(this);
  if ( (int)v2 < 0 )
  {
    WdLogSingleEntry0(1);
    v5 = 25281;
    v6 = L"Failed to create paging fence objects";
LABEL_3:
    v23 = v5;
    WdLogGlobalForLineNumber = v5;
LABEL_4:
    DxgkLogInternalTriageEvent(v3, 0x40000, v4, (_DWORD)v6, v23, 0, 0, 0);
    goto LABEL_35;
  }
  for ( i = 0; i < *((_DWORD *)this + 778); ++i )
  {
    inited = VIDMM_GLOBAL::InitPagingProcessVaSpace(this, 0, i, 0);
    v2 = inited;
    if ( inited < 0 )
    {
      WdLogSingleEntry1(1, inited);
      v6 = L"Failed to initialize paging process VA space. ntStatus=0x%.8x";
      v23 = v2;
      WdLogGlobalForLineNumber = 25297;
      goto LABEL_4;
    }
  }
  v13 = *((_QWORD *)this + 2);
  *((_BYTE *)this + 37229) = 1;
  v14 = *(_QWORD *)(v13 + 744);
  if ( *(int *)(*(_QWORD *)(v14 + 16) + 3132LL) >= 2500 )
  {
    for ( j = 0; j < *(_DWORD *)(v14 + 88); ++j )
    {
      v16 = *(struct _VIDSCH_NODE ***)(v14 + 776);
      v17 = *(_DWORD *)(v14 + 848);
      v18 = &v16[j];
      if ( j >= v17 )
        v18 = *(struct _VIDSCH_NODE ***)(v14 + 776);
      if ( (*((_DWORD *)*v18 + 3) & 2) != 0 )
      {
        if ( j < v17 )
          v16 += j;
        NodeSchedulingLog = VidSchiCreateNodeSchedulingLog(*v16, 0x800u);
        v2 = NodeSchedulingLog;
        if ( NodeSchedulingLog < 0 )
        {
          WdLogSingleEntry1(1, NodeSchedulingLog);
          v6 = L"Failed to create scheduling logs. ntStatus=0x%.8x";
          v23 = v2;
          WdLogGlobalForLineNumber = 25315;
          goto LABEL_4;
        }
      }
    }
  }
  LODWORD(v2) = 0;
LABEL_35:
  for ( k = 0; k < *((_DWORD *)this + 778); ++k )
  {
    v21 = *(_DWORD **)(*((_QWORD *)this + 4560) + 8LL * k);
    if ( v21[335] == 1 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v21 + 344LL))(v21);
  }
  *((_BYTE *)this + 37229) = 0;
  KeUnstackDetachProcess(&ApcState);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400bea60  push    rbx
0x1400bea62  push    rbp
0x1400bea63  push    rsi
0x1400bea64  push    rdi
0x1400bea65  push    r14
0x1400bea67  push    r15
0x1400bea69  sub     rsp, 98h
0x1400bea70  mov     rax, cs:__security_cookie
0x1400bea77  xor     rax, rsp
0x1400bea7a  mov     [rsp+0C8h+var_48], rax
0x1400bea82  xorps   xmm0, xmm0
0x1400bea85  lea     rdx, [rsp+0C8h+ApcState]; ApcState
0x1400bea8a  mov     rsi, rcx
0x1400bea8d  mov     r15d, 1
0x1400bea93  mov     [rcx+916Dh], r15b
0x1400bea9a  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1400beaa1  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink], xmm0
0x1400beaa6  movups  xmmword ptr [rsp+0C8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400beaab  mov     rcx, [rcx]; PROCESS
0x1400beaae  movups  xmmword ptr [rsp+0C8h+ApcState.Process], xmm0
0x1400beab3  call    cs:__imp_KeStackAttachProcess
0x1400beaba  nop     dword ptr [rax+rax+00h]
0x1400beabf  lea     rcx, [rsi+8F40h]; this
0x1400beac6  mov     rdx, rsi; struct VIDMM_GLOBAL *
0x1400beac9  call    ?InitPagingProcess@VIDMM_PAGING_PROCESS@@QEAAJPEAVVIDMM_GLOBAL@@@Z; VIDMM_PAGING_PROCESS::InitPagingProcess(VIDMM_GLOBAL *)
0x1400beace  xor     r14d, r14d
0x1400bead1  mov     edi, eax
0x1400bead3  test    eax, eax
0x1400bead5  jns     short loc_1400BEB1B
0x1400bead7  mov     ecx, r15d
0x1400beada  call    cs:__imp_WdLogSingleEntry0
0x1400beae1  nop     dword ptr [rax+rax+00h]
0x1400beae6  mov     eax, 6290h
0x1400beaeb  lea     r9, aFailedToInitia_25; "Failed to initialize paging process"
0x1400beaf2  mov     [rsp+0C8h+var_90], r14
0x1400beaf7  mov     [rsp+0C8h+var_98], r14
0x1400beafc  mov     [rsp+0C8h+var_A0], r14
0x1400beb01  mov     [rsp+0C8h+var_A8], rax
0x1400beb06  mov     cs:WdLogGlobalForLineNumber, eax
0x1400beb0c  mov     edx, 40000h
0x1400beb11  call    DxgkLogInternalTriageEvent
0x1400beb16  jmp     loc_1400BED82
0x1400beb1b  mov     rcx, [rsi+10h]
0x1400beb1f  mov     rcx, [rcx+2E8h]
0x1400beb26  call    VidSchCreateSystemDevices
0x1400beb2b  mov     edi, eax
0x1400beb2d  test    eax, eax
0x1400beb2f  jns     short loc_1400BEB4E
0x1400beb31  mov     ecx, r15d
0x1400beb34  call    cs:__imp_WdLogSingleEntry0
0x1400beb3b  nop     dword ptr [rax+rax+00h]
0x1400beb40  mov     eax, 629Bh
0x1400beb45  lea     r9, aFailedToCreate_2; "Failed to create scheduler system devic"...
0x1400beb4c  jmp     short loc_1400BEAF2
0x1400beb4e  mov     rcx, [rsi+8F48h]; this
0x1400beb55  call    ?CreatePagingProcessPagingQueues@VIDMM_DEVICE@@QEAAJXZ; VIDMM_DEVICE::CreatePagingProcessPagingQueues(void)
0x1400beb5a  mov     edi, eax
0x1400beb5c  test    eax, eax
0x1400beb5e  js      loc_1400BED82
0x1400beb64  mov     ecx, 0B8h
0x1400beb69  mov     edx, 6D4D6956h
0x1400beb6e  lea     r8d, [rcx-78h]
0x1400beb72  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400beb77  mov     rbx, rax
0x1400beb7a  test    rax, rax
0x1400beb7d  jz      short loc_1400BEBB8
0x1400beb7f  mov     [rax], rsi
0x1400beb82  lea     rcx, [rbx+10h]; Semaphore
0x1400beb86  mov     rax, [rsi]
0x1400beb89  mov     r8d, r15d; Limit
0x1400beb8c  mov     [rbx+8], rax
0x1400beb90  mov     edx, r15d; Count
0x1400beb93  mov     [rbx+30h], rbx
0x1400beb97  mov     [rbx+38h], r14
0x1400beb9b  mov     [rbx+40h], r14
0x1400beb9f  mov     [rbx+50h], r14d
0x1400beba3  mov     [rbx+0B0h], r15
0x1400bebaa  call    cs:__imp_KeInitializeSemaphore
0x1400bebb1  nop     dword ptr [rax+rax+00h]
0x1400bebb6  jmp     short loc_1400BEBBB
0x1400bebb8  mov     rbx, r14
0x1400bebbb  mov     [rsi+30h], rbx
0x1400bebbf  test    rbx, rbx
0x1400bebc2  jnz     short loc_1400BEC0B
0x1400bebc4  lock add cs:dword_1400878AC, r15d
0x1400bebcc  lea     ecx, [rbx+6]
0x1400bebcf  call    cs:__imp_WdLogSingleEntry0
0x1400bebd6  nop     dword ptr [rax+rax+00h]
0x1400bebdb  mov     [rsp+0C8h+var_90], r14
0x1400bebe0  lea     r9, aFailedToAlloca_75; "Failed to allocate memory for VIDMM_PAG"...
0x1400bebe7  mov     eax, 62ADh
0x1400bebec  mov     [rsp+0C8h+var_98], r14
0x1400bebf1  mov     [rsp+0C8h+var_A0], r14
0x1400bebf6  mov     edx, 40001h
0x1400bebfb  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bec01  mov     [rsp+0C8h+var_A8], rax
0x1400bec06  jmp     loc_1400BEB11
0x1400bec0b  mov     rcx, rbx; struct VIDMM_PAGING *
0x1400bec0e  call    ?VidMmInitializePaging@@YAJPEAUVIDMM_PAGING@@@Z; VidMmInitializePaging(VIDMM_PAGING *)
0x1400bec13  mov     edi, eax
0x1400bec15  test    eax, eax
0x1400bec17  jns     short loc_1400BEC39
0x1400bec19  mov     ecx, r15d
0x1400bec1c  call    cs:__imp_WdLogSingleEntry0
0x1400bec23  nop     dword ptr [rax+rax+00h]
0x1400bec28  mov     eax, 62B6h
0x1400bec2d  lea     r9, aFailedToInitPa; "Failed to init paging structure and DMA"...
0x1400bec34  jmp     loc_1400BEAF2
0x1400bec39  mov     rcx, rsi; this
0x1400bec3c  call    ?CreatePagingFenceObjects@VIDMM_GLOBAL@@QEAAJXZ; VIDMM_GLOBAL::CreatePagingFenceObjects(void)
0x1400bec41  mov     edi, eax
0x1400bec43  test    eax, eax
0x1400bec45  jns     short loc_1400BEC67
0x1400bec47  mov     ecx, r15d
0x1400bec4a  call    cs:__imp_WdLogSingleEntry0
0x1400bec51  nop     dword ptr [rax+rax+00h]
0x1400bec56  mov     eax, 62C1h
0x1400bec5b  lea     r9, aFailedToCreate_6; "Failed to create paging fence objects"
0x1400bec62  jmp     loc_1400BEAF2
0x1400bec67  mov     ebx, r14d
0x1400bec6a  cmp     ebx, [rsi+0C28h]
0x1400bec70  jnb     short loc_1400BECCA
0x1400bec72  xor     r9d, r9d; bool
0x1400bec75  mov     r8d, ebx; unsigned int
0x1400bec78  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bec7a  mov     rcx, rsi; this
0x1400bec7d  call    ?InitPagingProcessVaSpace@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_N@Z; VIDMM_GLOBAL::InitPagingProcessVaSpace(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,bool)
0x1400bec82  movsxd  rdi, eax
0x1400bec85  test    eax, eax
0x1400bec87  js      short loc_1400BEC8E
0x1400bec89  add     ebx, r15d
0x1400bec8c  jmp     short loc_1400BEC6A
0x1400bec8e  mov     rdx, rdi
0x1400bec91  mov     ecx, r15d
0x1400bec94  call    cs:__imp_WdLogSingleEntry1
0x1400bec9b  nop     dword ptr [rax+rax+00h]
0x1400beca0  mov     [rsp+0C8h+var_90], r14
0x1400beca5  lea     r9, aFailedToInitia_9; "Failed to initialize paging process VA "...
0x1400becac  mov     [rsp+0C8h+var_98], r14
0x1400becb1  mov     [rsp+0C8h+var_A0], r14
0x1400becb6  mov     [rsp+0C8h+var_A8], rdi
0x1400becbb  mov     cs:WdLogGlobalForLineNumber, 62D1h
0x1400becc5  jmp     loc_1400BEB0C
0x1400becca  mov     rax, [rsi+10h]
0x1400becce  mov     [rsi+916Dh], r15b
0x1400becd5  mov     rbp, [rax+2E8h]
0x1400becdc  mov     rax, [rbp+10h]
0x1400bece0  cmp     dword ptr [rax+0C3Ch], 9C4h
0x1400becea  jl      loc_1400BED7F
0x1400becf0  mov     ebx, r14d
0x1400becf3  cmp     ebx, [rbp+58h]
0x1400becf6  jnb     loc_1400BED7F
0x1400becfc  mov     r8, [rbp+308h]
0x1400bed03  mov     edx, [rbp+350h]
0x1400bed09  mov     r9d, ebx
0x1400bed0c  lea     rax, [r8+r9*8]
0x1400bed10  cmp     ebx, edx
0x1400bed12  jb      short loc_1400BED17
0x1400bed14  mov     rax, r8
0x1400bed17  mov     rax, [rax]
0x1400bed1a  mov     ecx, [rax+0Ch]
0x1400bed1d  test    cl, 2
0x1400bed20  jz      short loc_1400BED3E
0x1400bed22  cmp     ebx, edx
0x1400bed24  jnb     short loc_1400BED2A
0x1400bed26  lea     r8, [r8+r9*8]
0x1400bed2a  mov     rcx, [r8]; struct _VIDSCH_NODE *
0x1400bed2d  mov     edx, 800h
0x1400bed32  call    VidSchiCreateNodeSchedulingLog
0x1400bed37  movsxd  rdi, eax
0x1400bed3a  test    eax, eax
0x1400bed3c  js      short loc_1400BED43
0x1400bed3e  add     ebx, r15d
0x1400bed41  jmp     short loc_1400BECF3
0x1400bed43  mov     rdx, rdi
0x1400bed46  mov     ecx, r15d
0x1400bed49  call    cs:__imp_WdLogSingleEntry1
0x1400bed50  nop     dword ptr [rax+rax+00h]
0x1400bed55  mov     [rsp+0C8h+var_90], r14
0x1400bed5a  lea     r9, aFailedToCreate_11; "Failed to create scheduling logs. ntSta"...
0x1400bed61  mov     [rsp+0C8h+var_98], r14
0x1400bed66  mov     [rsp+0C8h+var_A0], r14
0x1400bed6b  mov     [rsp+0C8h+var_A8], rdi
0x1400bed70  mov     cs:WdLogGlobalForLineNumber, 62E3h
0x1400bed7a  jmp     loc_1400BEB0C
0x1400bed7f  mov     edi, r14d
0x1400bed82  mov     ebx, r14d
0x1400bed85  cmp     [rsi+0C28h], r14d
0x1400bed8c  jbe     short loc_1400BEDBE
0x1400bed8e  mov     rax, [rsi+8E80h]
0x1400bed95  mov     ecx, ebx
0x1400bed97  mov     rcx, [rax+rcx*8]
0x1400bed9b  cmp     [rcx+53Ch], r15d
0x1400beda2  jnz     short loc_1400BEDB3
0x1400beda4  mov     rax, [rcx]
0x1400beda7  mov     rax, [rax+158h]
0x1400bedae  call    _guard_dispatch_icall
0x1400bedb3  add     ebx, r15d
0x1400bedb6  cmp     ebx, [rsi+0C28h]
0x1400bedbc  jb      short loc_1400BED8E
0x1400bedbe  lea     rcx, [rsp+0C8h+ApcState]; ApcState
0x1400bedc3  mov     [rsi+916Dh], r14b
0x1400bedca  call    cs:__imp_KeUnstackDetachProcess
0x1400bedd1  nop     dword ptr [rax+rax+00h]
0x1400bedd6  mov     eax, edi
0x1400bedd8  mov     rcx, [rsp+0C8h+var_48]
0x1400bede0  xor     rcx, rsp; StackCookie
0x1400bede3  call    __security_check_cookie
0x1400bede8  add     rsp, 98h
0x1400bedef  pop     r15
0x1400bedf1  pop     r14
0x1400bedf3  pop     rdi
0x1400bedf4  pop     rsi
0x1400bedf5  pop     rbp
0x1400bedf6  pop     rbx
0x1400bedf7  retn
```
