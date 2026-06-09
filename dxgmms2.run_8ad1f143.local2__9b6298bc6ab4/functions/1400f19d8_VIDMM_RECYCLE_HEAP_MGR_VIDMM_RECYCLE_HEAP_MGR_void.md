# VIDMM_RECYCLE_HEAP_MGR::~VIDMM_RECYCLE_HEAP_MGR(void)

- ea: `0x1400f19d8`
- end: `0x1400f1dbc`
- name: `??1VIDMM_RECYCLE_HEAP_MGR@@UEAA@XZ`
- size: `996`
- prototype: `void __fastcall(VIDMM_RECYCLE_HEAP_MGR *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140030a80`

## callees

- `0x1400045ec`
- `0x14002ec00`
- `0x14002ed1c`
- `0x14002faf0`
- `0x14002fb4c`
- `0x140030ae0`
- `0x14003f5a4`
- `0x140058680`
- `0x1400f0d24`
- `0x1400f19d8`
- `0x1400f1dc4`
- `0x1400f1edc`
- `0x1400f34c0`
- `0x1400f5dd8`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f1b94`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f1bb8`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f1b94`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400f1bb8`
- `ntoskrnl!KeCancelTimer` at `0x1400f1d08`
- `ntoskrnl!KeCancelTimer` at `0x1400f1d08`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f1a23`
- `ntoskrnl!KeStackAttachProcess` at `0x1400f1a23`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f1be5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400f1be5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f1b53`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f1b73`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f1b53`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f1b73`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400f1d1c`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400f1d1c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f1d49`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f1d49`
- `watchdog!WdLogSingleEntry0` at `0x1400f1d6f`
- `watchdog!WdLogSingleEntry0` at `0x1400f1d6f`

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
0x1400f19d8  push    rbp
0x1400f19da  push    rbx
0x1400f19db  push    rsi
0x1400f19dc  push    rdi
0x1400f19dd  push    r14
0x1400f19df  push    r15
0x1400f19e1  lea     rbp, [rsp-2Fh]
0x1400f19e6  sub     rsp, 0C8h
0x1400f19ed  mov     rax, cs:__security_cookie
0x1400f19f4  xor     rax, rsp
0x1400f19f7  mov     [rbp+57h+var_40], rax
0x1400f19fb  xorps   xmm0, xmm0
0x1400f19fe  lea     rax, ??_7VIDMM_RECYCLE_HEAP_MGR@@6B@; const VIDMM_RECYCLE_HEAP_MGR::`vftable'
0x1400f1a05  mov     [rcx], rax
0x1400f1a08  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1400f1a0c  mov     rbx, rcx
0x1400f1a0f  mov     rcx, [rcx+8]
0x1400f1a13  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1400f1a17  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400f1a1b  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1400f1a1f  mov     rcx, [rcx+10h]; PROCESS
0x1400f1a23  call    cs:__imp_KeStackAttachProcess
0x1400f1a2a  nop     dword ptr [rax+rax+00h]
0x1400f1a2f  mov     rdx, cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA; struct DXGPUSHLOCK *
0x1400f1a36  lea     rcx, [rbp+57h+var_88]; this
0x1400f1a3a  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400f1a3f  lea     rcx, [rbx+640h]
0x1400f1a46  mov     rax, [rcx]
0x1400f1a49  test    rax, rax
0x1400f1a4c  jz      short loc_1400F1A6C
0x1400f1a4e  cmp     [rax+8], rcx
0x1400f1a52  jnz     loc_1400F1D63
0x1400f1a58  mov     rdx, [rcx+8]
0x1400f1a5c  cmp     [rdx], rcx
0x1400f1a5f  jnz     loc_1400F1D63
0x1400f1a65  mov     [rdx], rax
0x1400f1a68  mov     [rax+8], rdx
0x1400f1a6c  lea     rcx, [rbp+57h+var_88]; this
0x1400f1a70  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400f1a75  lea     r15, [rbx+530h]
0x1400f1a7c  mov     [rbp+57h+var_90], 0
0x1400f1a80  mov     [rbp+57h+var_98], r15
0x1400f1a84  test    r15, r15
0x1400f1a87  jz      loc_1400F1D6A
0x1400f1a8d  lea     rcx, [rbp+57h+var_98]; this
0x1400f1a91  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400f1a96  mov     eax, 1
0x1400f1a9b  xchg    eax, [rbx+630h]
0x1400f1aa1  mov     ecx, [rbx+600h]; this
0x1400f1aa7  test    ecx, ecx
0x1400f1aa9  jnz     loc_1400F1D01
0x1400f1aaf  lea     rsi, [rbx+608h]
0x1400f1ab6  mov     rdi, [rsi]
0x1400f1ab9  cmp     rdi, rsi
0x1400f1abc  jz      short loc_1400F1AF6
0x1400f1abe  lea     r14, [rdi-68h]
0x1400f1ac2  mov     rdi, [rdi]
0x1400f1ac5  mov     rdx, r14; struct VIDMM_RECYCLE_RANGE *
0x1400f1ac8  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x1400f1acd  lea     rdx, [rbp+57h+var_A0]; bool *
0x1400f1ad1  mov     [rbp+57h+var_A0], 0
0x1400f1ad5  mov     rcx, r14; this
0x1400f1ad8  call    ?FinalizedUnlock@VIDMM_RECYCLE_RANGE@@QEAAXAEA_N@Z; VIDMM_RECYCLE_RANGE::FinalizedUnlock(bool &)
0x1400f1add  cmp     [rbp+57h+var_A0], 0
0x1400f1ae1  jnz     short loc_1400F1AB9
0x1400f1ae3  mov     rcx, [r14+88h]; this
0x1400f1aea  test    rcx, rcx
0x1400f1aed  jz      short loc_1400F1AB9
0x1400f1aef  call    ?MergeSubrangesWherePossible@VIDMM_RECYCLE_MULTIRANGE@@QEAAEE@Z; VIDMM_RECYCLE_MULTIRANGE::MergeSubrangesWherePossible(uchar)
0x1400f1af4  jmp     short loc_1400F1AB9
0x1400f1af6  lea     rdi, [rbx+618h]
0x1400f1afd  mov     rax, [rdi]
0x1400f1b00  cmp     rax, rdi
0x1400f1b03  jz      short loc_1400F1B3D
0x1400f1b05  lea     rsi, [rax-68h]
0x1400f1b09  mov     rdx, rsi; struct VIDMM_RECYCLE_RANGE *
0x1400f1b0c  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x1400f1b11  lea     rdx, [rbp+57h+var_9C]; enum VIDMM_RECYCLE_BLOCK_SHRINK_RESULT *
0x1400f1b15  mov     [rbp+57h+var_9C], 0
0x1400f1b1c  mov     rcx, rsi; this
0x1400f1b1f  call    ?DebouncedDecommit@VIDMM_RECYCLE_RANGE@@QEAAXAEAW4VIDMM_RECYCLE_BLOCK_SHRINK_RESULT@@@Z; VIDMM_RECYCLE_RANGE::DebouncedDecommit(VIDMM_RECYCLE_BLOCK_SHRINK_RESULT &)
0x1400f1b24  cmp     [rbp+57h+var_9C], 0
0x1400f1b28  jnz     short loc_1400F1AFD
0x1400f1b2a  mov     rcx, [rsi+88h]; this
0x1400f1b31  test    rcx, rcx
0x1400f1b34  jz      short loc_1400F1AFD
0x1400f1b36  call    ?MergeSubrangesWherePossible@VIDMM_RECYCLE_MULTIRANGE@@QEAAEE@Z; VIDMM_RECYCLE_MULTIRANGE::MergeSubrangesWherePossible(uchar)
0x1400f1b3b  jmp     short loc_1400F1AFD
0x1400f1b3d  xor     edi, edi
0x1400f1b3f  mov     rdx, [rbx+rdi*8+658h]; Entry
0x1400f1b47  test    rdx, rdx
0x1400f1b4a  jz      short loc_1400F1B5F
0x1400f1b4c  mov     rcx, [rbx+520h]; Lookaside
0x1400f1b53  call    cs:__imp_ExFreeToLookasideListEx
0x1400f1b5a  nop     dword ptr [rax+rax+00h]
0x1400f1b5f  mov     rdx, [rbx+rdi*8+678h]; Entry
0x1400f1b67  test    rdx, rdx
0x1400f1b6a  jz      short loc_1400F1B7F
0x1400f1b6c  mov     rcx, [rbx+528h]; Lookaside
0x1400f1b73  call    cs:__imp_ExFreeToLookasideListEx
0x1400f1b7a  nop     dword ptr [rax+rax+00h]
0x1400f1b7f  inc     rdi
0x1400f1b82  cmp     rdi, 4
0x1400f1b86  jb      short loc_1400F1B3F
0x1400f1b88  mov     rcx, [rbx+520h]; Lookaside
0x1400f1b8f  test    rcx, rcx
0x1400f1b92  jz      short loc_1400F1BAC
0x1400f1b94  call    cs:__imp_ExDeleteLookasideListEx
0x1400f1b9b  nop     dword ptr [rax+rax+00h]
0x1400f1ba0  mov     rcx, [rbx+520h]; void *
0x1400f1ba7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f1bac  mov     rcx, [rbx+528h]; Lookaside
0x1400f1bb3  test    rcx, rcx
0x1400f1bb6  jz      short loc_1400F1BD0
0x1400f1bb8  call    cs:__imp_ExDeleteLookasideListEx
0x1400f1bbf  nop     dword ptr [rax+rax+00h]
0x1400f1bc4  mov     rcx, [rbx+528h]; void *
0x1400f1bcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f1bd0  mov     rcx, [rbx+638h]; void *
0x1400f1bd7  test    rcx, rcx
0x1400f1bda  jz      short loc_1400F1BE1
0x1400f1bdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400f1be1  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1400f1be5  call    cs:__imp_KeUnstackDetachProcess
0x1400f1bec  nop     dword ptr [rax+rax+00h]
0x1400f1bf1  cmp     [rbp+57h+var_90], 0
0x1400f1bf5  jz      short loc_1400F1C00
0x1400f1bf7  lea     rcx, [rbp+57h+var_98]; this
0x1400f1bfb  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1400f1c00  mov     rcx, r15; this
0x1400f1c03  call    ??1DXGFASTMUTEX@@QEAA@XZ; DXGFASTMUTEX::~DXGFASTMUTEX(void)
0x1400f1c08  lea     rcx, [rbx+4D8h]; this
0x1400f1c0f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c14  lea     rcx, [rbx+490h]; this
0x1400f1c1b  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c20  lea     rcx, [rbx+448h]; this
0x1400f1c27  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c2c  lea     rcx, [rbx+400h]; this
0x1400f1c33  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c38  lea     rcx, [rbx+3B8h]; this
0x1400f1c3f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c44  lea     rcx, [rbx+370h]; this
0x1400f1c4b  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c50  lea     rcx, [rbx+328h]; this
0x1400f1c57  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c5c  lea     rcx, [rbx+2E0h]; this
0x1400f1c63  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c68  lea     rcx, [rbx+298h]; this
0x1400f1c6f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c74  lea     rcx, [rbx+250h]; this
0x1400f1c7b  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c80  lea     rcx, [rbx+208h]; this
0x1400f1c87  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c8c  lea     rcx, [rbx+1C0h]; this
0x1400f1c93  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1c98  lea     rcx, [rbx+178h]; this
0x1400f1c9f  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1ca4  lea     rcx, [rbx+130h]; this
0x1400f1cab  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1cb0  lea     rcx, [rbx+0E8h]; this
0x1400f1cb7  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1cbc  lea     rcx, [rbx+0A0h]; this
0x1400f1cc3  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1cc8  lea     rcx, [rbx+58h]; this
0x1400f1ccc  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1cd1  lea     rcx, [rbx+10h]; this
0x1400f1cd5  call    ??1VIDMM_RECYCLE_HEAP@@QEAA@XZ; VIDMM_RECYCLE_HEAP::~VIDMM_RECYCLE_HEAP(void)
0x1400f1cda  lea     rax, ??_7VIDMM_HEAP_INTERFACE@@6B@; const VIDMM_HEAP_INTERFACE::`vftable'
0x1400f1ce1  mov     [rbx], rax
0x1400f1ce4  mov     rcx, [rbp+57h+var_40]
0x1400f1ce8  xor     rcx, rsp; StackCookie
0x1400f1ceb  call    __security_check_cookie
0x1400f1cf0  add     rsp, 0C8h
0x1400f1cf7  pop     r15
0x1400f1cf9  pop     r14
0x1400f1cfb  pop     rdi
0x1400f1cfc  pop     rsi
0x1400f1cfd  pop     rbx
0x1400f1cfe  pop     rbp
0x1400f1cff  retn
0x1400f1d01  lea     rcx, [rbx+560h]; PKTIMER
0x1400f1d08  call    cs:__imp_KeCancelTimer
0x1400f1d0f  nop     dword ptr [rax+rax+00h]
0x1400f1d14  test    al, al
0x1400f1d16  jnz     loc_1400F1AAF
0x1400f1d1c  call    cs:__imp_KeFlushQueuedDpcs
0x1400f1d23  nop     dword ptr [rax+rax+00h]
0x1400f1d28  lea     rcx, [rbp+57h+var_98]; this
0x1400f1d2c  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1400f1d31  mov     rcx, [rbx+638h]; Object
0x1400f1d38  xor     r9d, r9d; Alertable
0x1400f1d3b  xor     r8d, r8d; WaitMode
0x1400f1d3e  mov     [rsp+0F0h+Timeout], 0; Timeout
0x1400f1d47  xor     edx, edx; WaitReason
0x1400f1d49  call    cs:__imp_KeWaitForSingleObject
0x1400f1d50  nop     dword ptr [rax+rax+00h]
0x1400f1d55  lea     rcx, [rbp+57h+var_98]; this
0x1400f1d59  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400f1d5e  jmp     loc_1400F1AAF
0x1400f1d63  mov     ecx, 3
0x1400f1d68  int     29h; Win8: RtlFailFast(ecx)
0x1400f1d6a  mov     ecx, 1
0x1400f1d6f  call    cs:__imp_WdLogSingleEntry0
0x1400f1d76  nop     dword ptr [rax+rax+00h]
0x1400f1d7b  mov     [rsp+0F0h+var_B8], 0
0x1400f1d84  lea     r9, aMPmutexNull; "m_pMutex != NULL"
0x1400f1d8b  mov     eax, 279h
0x1400f1d90  mov     [rsp+0F0h+var_C0], 0
0x1400f1d99  mov     [rsp+0F0h+var_C8], 0
0x1400f1da2  mov     edx, 40002h
0x1400f1da7  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f1dad  mov     [rsp+0F0h+Timeout], rax
0x1400f1db2  call    DxgkLogInternalTriageEvent
0x1400f1db7  jmp     loc_1400F1A8D
```
