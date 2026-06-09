# VIDMM_RECYCLE_HEAP_MGR::~VIDMM_RECYCLE_HEAP_MGR(void)

- ea: `0x1400f69b8`
- end: `0x1400f6d9c`
- name: `??1VIDMM_RECYCLE_HEAP_MGR@@UEAA@XZ`
- size: `996`
- prototype: `void __fastcall(VIDMM_RECYCLE_HEAP_MGR *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14002e660`

## callees

- `0x140004268`
- `0x14002bcc0`
- `0x14002bddc`
- `0x14002d810`
- `0x14002d86c`
- `0x14002e6c0`
- `0x14003df20`
- `0x140058f50`
- `0x1400f5d04`
- `0x1400f69b8`
- `0x1400f6da4`
- `0x1400f6ebc`
- `0x1400f84a0`
- `0x1400fadb8`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f6b74`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f6b98`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f6b74`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f6b98`
- `ntoskrnl!KeCancelTimer` at `0x1400f6ce8`
- `ntoskrnl!KeCancelTimer` at `0x1400f6ce8`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f6a03`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f6a03`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f6bc5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f6bc5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f6b33`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f6b53`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f6b33`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f6b53`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400f6cfc`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400f6cfc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f6d29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f6d29`
- `watchdog!WdLogSingleEntry0` at `0x1400f6d4f`
- `watchdog!WdLogSingleEntry0` at `0x1400f6d4f`

## pseudocode

```c
void __fastcall VIDMM_RECYCLE_HEAP_MGR::~VIDMM_RECYCLE_HEAP_MGR(VIDMM_RECYCLE_HEAP_MGR *this)
{
  __int64 v2; // rcx
  char *v3; // rcx
  __int64 v4; // rax
  char **v5; // rdx
  VIDMM_RECYCLE_HEAP_MGR *v6; // rcx
  VIDMM_RECYCLE_HEAP_MGR *v7; // rdi
  struct VIDMM_RECYCLE_RANGE *v8; // r14
  unsigned __int8 v9; // dl
  _QWORD *v10; // rdi
  _QWORD *v11; // rax
  VIDMM_RECYCLE_RANGE *v12; // rsi
  unsigned __int8 v13; // dl
  unsigned __int64 i; // rdi
  void *v15; // rdx
  void *v16; // rdx
  struct _LOOKASIDE_LIST_EX *v17; // rcx
  struct _LOOKASIDE_LIST_EX *v18; // rcx
  void *v19; // rcx
  int v20; // ecx
  int v21; // r8d
  bool v22; // [rsp+50h] [rbp-49h] BYREF
  int v23; // [rsp+54h] [rbp-45h] BYREF
  char *v24; // [rsp+58h] [rbp-41h] BYREF
  char v25; // [rsp+60h] [rbp-39h]
  _BYTE v26[24]; // [rsp+68h] [rbp-31h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+80h] [rbp-19h] BYREF

  *(_QWORD *)this = &VIDMM_RECYCLE_HEAP_MGR::`vftable';
  v2 = *((_QWORD *)this + 1);
  memset(&ApcState, 0, sizeof(ApcState));
  KeStackAttachProcess(*(PRKPROCESS *)(v2 + 16), &ApcState);
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)v26,
    VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock);
  v3 = (char *)this + 1600;
  v4 = *((_QWORD *)this + 200);
  if ( v4 )
  {
    if ( *(char **)(v4 + 8) != v3 || (v5 = (char **)*((_QWORD *)this + 201), *v5 != v3) )
      __fastfail(3u);
    *v5 = (char *)v4;
    *(_QWORD *)(v4 + 8) = v5;
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v26);
  v25 = 0;
  v24 = (char *)this + 1328;
  if ( this == (VIDMM_RECYCLE_HEAP_MGR *)-1328LL )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 633;
    DxgkLogInternalTriageEvent(v20, 262146, v21, (unsigned int)L"m_pMutex != NULL", 633, 0, 0, 0);
  }
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v24);
  _InterlockedExchange((volatile __int32 *)this + 396, 1);
  v6 = (VIDMM_RECYCLE_HEAP_MGR *)*((unsigned int *)this + 384);
  if ( (_DWORD)v6 && !KeCancelTimer((PKTIMER)((char *)this + 1376)) )
  {
    KeFlushQueuedDpcs();
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v24);
    KeWaitForSingleObject(*((PVOID *)this + 199), Executive, 0, 0, 0);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v24);
  }
  v7 = (VIDMM_RECYCLE_HEAP_MGR *)*((_QWORD *)this + 193);
  while ( v7 != (VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 1544) )
  {
    v8 = (VIDMM_RECYCLE_HEAP_MGR *)((char *)v7 - 104);
    v7 = *(VIDMM_RECYCLE_HEAP_MGR **)v7;
    VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(v6, v8);
    v22 = 0;
    VIDMM_RECYCLE_RANGE::FinalizedUnlock(v8, &v22);
    if ( !v22 )
    {
      v6 = (VIDMM_RECYCLE_HEAP_MGR *)*((_QWORD *)v8 + 17);
      if ( v6 )
        VIDMM_RECYCLE_MULTIRANGE::MergeSubrangesWherePossible(v6, v9);
    }
  }
  v10 = (_QWORD *)((char *)this + 1560);
  while ( 1 )
  {
    v11 = (_QWORD *)*v10;
    if ( (_QWORD *)*v10 == v10 )
      break;
    v12 = (VIDMM_RECYCLE_RANGE *)(v11 - 13);
    VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(v6, (struct VIDMM_RECYCLE_RANGE *)(v11 - 13));
    v23 = 0;
    VIDMM_RECYCLE_RANGE::DebouncedDecommit(v12, (enum VIDMM_RECYCLE_BLOCK_SHRINK_RESULT *)&v23);
    if ( !v23 )
    {
      v6 = (VIDMM_RECYCLE_HEAP_MGR *)*((_QWORD *)v12 + 17);
      if ( v6 )
        VIDMM_RECYCLE_MULTIRANGE::MergeSubrangesWherePossible(v6, v13);
    }
  }
  for ( i = 0; i < 4; ++i )
  {
    v15 = (void *)*((_QWORD *)this + i + 203);
    if ( v15 )
      ExFreeToLookasideListEx(*((PLOOKASIDE_LIST_EX *)this + 164), v15);
    v16 = (void *)*((_QWORD *)this + i + 207);
    if ( v16 )
      ExFreeToLookasideListEx(*((PLOOKASIDE_LIST_EX *)this + 165), v16);
  }
  v17 = (struct _LOOKASIDE_LIST_EX *)*((_QWORD *)this + 164);
  if ( v17 )
  {
    ExDeleteLookasideListEx(v17);
    operator delete(*((void **)this + 164));
  }
  v18 = (struct _LOOKASIDE_LIST_EX *)*((_QWORD *)this + 165);
  if ( v18 )
  {
    ExDeleteLookasideListEx(v18);
    operator delete(*((void **)this + 165));
  }
  v19 = (void *)*((_QWORD *)this + 199);
  if ( v19 )
    operator delete(v19);
  KeUnstackDetachProcess(&ApcState);
  if ( v25 )
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v24);
  DXGFASTMUTEX::~DXGFASTMUTEX((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 1328));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 1240));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 1168));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 1096));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 1024));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 952));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 880));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 808));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 736));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 664));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 592));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 520));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 448));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 376));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 304));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 232));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 160));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 88));
  VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP((VIDMM_RECYCLE_HEAP_MGR *)((char *)this + 16));
  *(_QWORD *)this = &VIDMM_HEAP_INTERFACE::`vftable';
}

```

## disassembly

```asm
0x1400f69b8  push    rbp
0x1400f69ba  push    rbx
0x1400f69bb  push    rsi
0x1400f69bc  push    rdi
0x1400f69bd  push    r14
0x1400f69bf  push    r15
0x1400f69c1  lea     rbp, [rsp-2Fh]
0x1400f69c6  sub     rsp, 0C8h
0x1400f69cd  mov     rax, cs:__security_cookie
0x1400f69d4  xor     rax, rsp
0x1400f69d7  mov     [rbp+57h+var_40], rax
0x1400f69db  xorps   xmm0, xmm0
0x1400f69de  lea     rax, ??_7VIDMM_RECYCLE_HEAP_MGR@@6B@; const VIDMM_RECYCLE_HEAP_MGR::`vftable'
0x1400f69e5  mov     [rcx], rax
0x1400f69e8  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1400f69ec  mov     rbx, rcx
0x1400f69ef  mov     rcx, [rcx+8]
0x1400f69f3  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1400f69f7  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400f69fb  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1400f69ff  mov     rcx, [rcx+10h]; PROCESS
0x1400f6a03  call    cs:__imp_KeStackAttachProcess
0x1400f6a0a  nop     dword ptr [rax+rax+00h]
0x1400f6a0f  mov     rdx, cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA; struct DXGPUSHLOCK *
0x1400f6a16  lea     rcx, [rbp+57h+var_88]; this
0x1400f6a1a  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400f6a1f  lea     rcx, [rbx+640h]
0x1400f6a26  mov     rax, [rcx]
0x1400f6a29  test    rax, rax
0x1400f6a2c  jz      short loc_1400F6A4C
0x1400f6a2e  cmp     [rax+8], rcx
0x1400f6a32  jnz     loc_1400F6D43
0x1400f6a38  mov     rdx, [rcx+8]
0x1400f6a3c  cmp     [rdx], rcx
0x1400f6a3f  jnz     loc_1400F6D43
0x1400f6a45  mov     [rdx], rax
0x1400f6a48  mov     [rax+8], rdx
0x1400f6a4c  lea     rcx, [rbp+57h+var_88]; this
0x1400f6a50  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400f6a55  lea     r15, [rbx+530h]
0x1400f6a5c  mov     [rbp+57h+var_90], 0
0x1400f6a60  mov     [rbp+57h+var_98], r15
0x1400f6a64  test    r15, r15
0x1400f6a67  jz      loc_1400F6D4A
0x1400f6a6d  lea     rcx, [rbp+57h+var_98]; this
0x1400f6a71  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400f6a76  mov     eax, 1
0x1400f6a7b  xchg    eax, [rbx+630h]
0x1400f6a81  mov     ecx, [rbx+600h]; this
0x1400f6a87  test    ecx, ecx
0x1400f6a89  jnz     loc_1400F6CE1
0x1400f6a8f  lea     rsi, [rbx+608h]
0x1400f6a96  mov     rdi, [rsi]
0x1400f6a99  cmp     rdi, rsi
0x1400f6a9c  jz      short loc_1400F6AD6
0x1400f6a9e  lea     r14, [rdi-68h]
0x1400f6aa2  mov     rdi, [rdi]
0x1400f6aa5  mov     rdx, r14; struct VIDMM_RECYCLE_RANGE *
0x1400f6aa8  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x1400f6aad  lea     rdx, [rbp+57h+var_A0]; bool *
0x1400f6ab1  mov     [rbp+57h+var_A0], 0
0x1400f6ab5  mov     rcx, r14; this
0x1400f6ab8  call    ?FinalizedUnlock@VIDMM_RECYCLE_RANGE@@QEAAXAEA_N@Z; VIDMM_RECYCLE_RANGE::FinalizedUnlock(bool &)
0x1400f6abd  cmp     [rbp+57h+var_A0], 0
0x1400f6ac1  jnz     short loc_1400F6A99
0x1400f6ac3  mov     rcx, [r14+88h]; this
0x1400f6aca  test    rcx, rcx
0x1400f6acd  jz      short loc_1400F6A99
0x1400f6acf  call    ?MergeSubrangesWherePossible@VIDMM_RECYCLE_MULTIRANGE@@QEAAEE@Z; VIDMM_RECYCLE_MULTIRANGE::MergeSubrangesWherePossible(uchar)
0x1400f6ad4  jmp     short loc_1400F6A99
0x1400f6ad6  lea     rdi, [rbx+618h]
0x1400f6add  mov     rax, [rdi]
0x1400f6ae0  cmp     rax, rdi
0x1400f6ae3  jz      short loc_1400F6B1D
0x1400f6ae5  lea     rsi, [rax-68h]
0x1400f6ae9  mov     rdx, rsi; struct VIDMM_RECYCLE_RANGE *
0x1400f6aec  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x1400f6af1  lea     rdx, [rbp+57h+var_9C]; enum VIDMM_RECYCLE_BLOCK_SHRINK_RESULT *
0x1400f6af5  mov     [rbp+57h+var_9C], 0
0x1400f6afc  mov     rcx, rsi; this
0x1400f6aff  call    ?DebouncedDecommit@VIDMM_RECYCLE_RANGE@@QEAAXAEAW4VIDMM_RECYCLE_BLOCK_SHRINK_RESULT@@@Z; VIDMM_RECYCLE_RANGE::DebouncedDecommit(VIDMM_RECYCLE_BLOCK_SHRINK_RESULT &)
0x1400f6b04  cmp     [rbp+57h+var_9C], 0
0x1400f6b08  jnz     short loc_1400F6ADD
0x1400f6b0a  mov     rcx, [rsi+88h]; this
0x1400f6b11  test    rcx, rcx
0x1400f6b14  jz      short loc_1400F6ADD
0x1400f6b16  call    ?MergeSubrangesWherePossible@VIDMM_RECYCLE_MULTIRANGE@@QEAAEE@Z; VIDMM_RECYCLE_MULTIRANGE::MergeSubrangesWherePossible(uchar)
0x1400f6b1b  jmp     short loc_1400F6ADD
0x1400f6b1d  xor     edi, edi
0x1400f6b1f  mov     rdx, [rbx+rdi*8+658h]; Entry
0x1400f6b27  test    rdx, rdx
0x1400f6b2a  jz      short loc_1400F6B3F
0x1400f6b2c  mov     rcx, [rbx+520h]; Lookaside
0x1400f6b33  call    cs:__imp_ExFreeToLookasideListEx
0x1400f6b3a  nop     dword ptr [rax+rax+00h]
0x1400f6b3f  mov     rdx, [rbx+rdi*8+678h]; Entry
0x1400f6b47  test    rdx, rdx
0x1400f6b4a  jz      short loc_1400F6B5F
0x1400f6b4c  mov     rcx, [rbx+528h]; Lookaside
0x1400f6b53  call    cs:__imp_ExFreeToLookasideListEx
0x1400f6b5a  nop     dword ptr [rax+rax+00h]
0x1400f6b5f  inc     rdi
0x1400f6b62  cmp     rdi, 4
0x1400f6b66  jb      short loc_1400F6B1F
0x1400f6b68  mov     rcx, [rbx+520h]; Lookaside
0x1400f6b6f  test    rcx, rcx
0x1400f6b72  jz      short loc_1400F6B8C
0x1400f6b74  call    cs:__imp_ExDeleteLookasideListEx
0x1400f6b7b  nop     dword ptr [rax+rax+00h]
0x1400f6b80  mov     rcx, [rbx+520h]; void *
0x1400f6b87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f6b8c  mov     rcx, [rbx+528h]; Lookaside
0x1400f6b93  test    rcx, rcx
0x1400f6b96  jz      short loc_1400F6BB0
0x1400f6b98  call    cs:__imp_ExDeleteLookasideListEx
0x1400f6b9f  nop     dword ptr [rax+rax+00h]
0x1400f6ba4  mov     rcx, [rbx+528h]; void *
0x1400f6bab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f6bb0  mov     rcx, [rbx+638h]; void *
0x1400f6bb7  test    rcx, rcx
0x1400f6bba  jz      short loc_1400F6BC1
0x1400f6bbc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f6bc1  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1400f6bc5  call    cs:__imp_KeUnstackDetachProcess
0x1400f6bcc  nop     dword ptr [rax+rax+00h]
0x1400f6bd1  cmp     [rbp+57h+var_90], 0
0x1400f6bd5  jz      short loc_1400F6BE0
0x1400f6bd7  lea     rcx, [rbp+57h+var_98]; this
0x1400f6bdb  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1400f6be0  mov     rcx, r15; this
0x1400f6be3  call    ??1DXGFASTMUTEX@@QEAA@XZ; DXGFASTMUTEX::~DXGFASTMUTEX(void)
0x1400f6be8  lea     rcx, [rbx+4D8h]; this
0x1400f6bef  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6bf4  lea     rcx, [rbx+490h]; this
0x1400f6bfb  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c00  lea     rcx, [rbx+448h]; this
0x1400f6c07  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c0c  lea     rcx, [rbx+400h]; this
0x1400f6c13  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c18  lea     rcx, [rbx+3B8h]; this
0x1400f6c1f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c24  lea     rcx, [rbx+370h]; this
0x1400f6c2b  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c30  lea     rcx, [rbx+328h]; this
0x1400f6c37  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c3c  lea     rcx, [rbx+2E0h]; this
0x1400f6c43  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c48  lea     rcx, [rbx+298h]; this
0x1400f6c4f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c54  lea     rcx, [rbx+250h]; this
0x1400f6c5b  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c60  lea     rcx, [rbx+208h]; this
0x1400f6c67  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c6c  lea     rcx, [rbx+1C0h]; this
0x1400f6c73  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c78  lea     rcx, [rbx+178h]; this
0x1400f6c7f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c84  lea     rcx, [rbx+130h]; this
0x1400f6c8b  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c90  lea     rcx, [rbx+0E8h]; this
0x1400f6c97  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6c9c  lea     rcx, [rbx+0A0h]; this
0x1400f6ca3  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6ca8  lea     rcx, [rbx+58h]; this
0x1400f6cac  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6cb1  lea     rcx, [rbx+10h]; this
0x1400f6cb5  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f6cba  lea     rax, ??_7VIDMM_HEAP_INTERFACE@@6B@; const VIDMM_HEAP_INTERFACE::`vftable'
0x1400f6cc1  mov     [rbx], rax
0x1400f6cc4  mov     rcx, [rbp+57h+var_40]
0x1400f6cc8  xor     rcx, rsp; StackCookie
0x1400f6ccb  call    __security_check_cookie
0x1400f6cd0  add     rsp, 0C8h
0x1400f6cd7  pop     r15
0x1400f6cd9  pop     r14
0x1400f6cdb  pop     rdi
0x1400f6cdc  pop     rsi
0x1400f6cdd  pop     rbx
0x1400f6cde  pop     rbp
0x1400f6cdf  retn
0x1400f6ce1  lea     rcx, [rbx+560h]; PKTIMER
0x1400f6ce8  call    cs:__imp_KeCancelTimer
0x1400f6cef  nop     dword ptr [rax+rax+00h]
0x1400f6cf4  test    al, al
0x1400f6cf6  jnz     loc_1400F6A8F
0x1400f6cfc  call    cs:__imp_KeFlushQueuedDpcs
0x1400f6d03  nop     dword ptr [rax+rax+00h]
0x1400f6d08  lea     rcx, [rbp+57h+var_98]; this
0x1400f6d0c  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1400f6d11  mov     rcx, [rbx+638h]; Object
0x1400f6d18  xor     r9d, r9d; Alertable
0x1400f6d1b  xor     r8d, r8d; WaitMode
0x1400f6d1e  mov     [rsp+0F0h+Timeout], 0; Timeout
0x1400f6d27  xor     edx, edx; WaitReason
0x1400f6d29  call    cs:__imp_KeWaitForSingleObject
0x1400f6d30  nop     dword ptr [rax+rax+00h]
0x1400f6d35  lea     rcx, [rbp+57h+var_98]; this
0x1400f6d39  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400f6d3e  jmp     loc_1400F6A8F
0x1400f6d43  mov     ecx, 3
0x1400f6d48  int     29h; Win8: RtlFailFast(ecx)
0x1400f6d4a  mov     ecx, 1
0x1400f6d4f  call    cs:__imp_WdLogSingleEntry0
0x1400f6d56  nop     dword ptr [rax+rax+00h]
0x1400f6d5b  mov     [rsp+0F0h+var_B8], 0
0x1400f6d64  lea     r9, aMPmutexNull; "m_pMutex != NULL"
0x1400f6d6b  mov     eax, 279h
0x1400f6d70  mov     [rsp+0F0h+var_C0], 0
0x1400f6d79  mov     [rsp+0F0h+var_C8], 0
0x1400f6d82  mov     edx, 40002h
0x1400f6d87  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f6d8d  mov     [rsp+0F0h+Timeout], rax
0x1400f6d92  call    DxgkLogInternalTriageEvent
0x1400f6d97  jmp     loc_1400F6A6D
```
