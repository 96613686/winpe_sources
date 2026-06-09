# VIDMM_RECYCLE_HEAP_MGR::Init(VIDMM_PROCESS *,ulong)

- ea: `0x140121540`
- end: `0x14012188c`
- name: `?Init@VIDMM_RECYCLE_HEAP_MGR@@UEAAJPEAVVIDMM_PROCESS@@K@Z`
- size: `844`
- prototype: `__int64 __fastcall(VIDMM_RECYCLE_HEAP_MGR *__hidden this, struct VIDMM_PROCESS *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002bcc0`
- `0x14002bddc`
- `0x140121540`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14012164b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14012177a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14012164b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14012177a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401216bc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401217e2`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401216bc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401217e2`
- `ntoskrnl!KeInitializeEvent` at `0x1401215d2`
- `ntoskrnl!KeInitializeEvent` at `0x1401215d2`
- `watchdog!WdLogSingleEntry0` at `0x140121584`
- `watchdog!WdLogSingleEntry0` at `0x140121609`
- `watchdog!WdLogSingleEntry0` at `0x140121669`
- `watchdog!WdLogSingleEntry0` at `0x1401216e6`
- `watchdog!WdLogSingleEntry0` at `0x140121738`
- `watchdog!WdLogSingleEntry0` at `0x14012180c`
- `watchdog!WdLogSingleEntry0` at `0x140121584`
- `watchdog!WdLogSingleEntry0` at `0x140121609`
- `watchdog!WdLogSingleEntry0` at `0x140121669`
- `watchdog!WdLogSingleEntry0` at `0x1401216e6`
- `watchdog!WdLogSingleEntry0` at `0x140121738`
- `watchdog!WdLogSingleEntry0` at `0x14012180c`
- `watchdog!WdLogSingleEntry1` at `0x14012179c`
- `watchdog!WdLogSingleEntry1` at `0x14012179c`

## string_xrefs

- `0x14012161a`: `Couldn't allocate our range pool lookaside list\n`
- `0x14012167a`: `Couldn't initialize our range pool lookaside list\n`
- `0x1401217ad`: `Couldn't initialize our multirange pool lookaside list. Status = 0x%I64x\n`
- `0x140121749`: `Couldn't allocate our multirange pool lookaside list\n`

## pseudocode

```c
__int64 __fastcall VIDMM_RECYCLE_HEAP_MGR::Init(VIDMM_RECYCLE_HEAP_MGR *this, struct VIDMM_PROCESS *a2, int a3)
{
  struct _KEVENT *v4; // rax
  int v5; // ecx
  int v6; // r8d
  __int64 v7; // rax
  const wchar_t *v8; // r9
  struct _LOOKASIDE_LIST_EX *v10; // rax
  __int64 v11; // rdi
  int v12; // ecx
  int v13; // r8d
  unsigned __int64 i; // rdi
  PVOID v15; // rax
  struct _LOOKASIDE_LIST_EX *v16; // rax
  NTSTATUS v17; // eax
  int v18; // ecx
  int v19; // r8d
  unsigned __int64 j; // rdi
  PVOID v21; // rax
  struct DXGPUSHLOCK *v22; // rdx
  _QWORD *v23; // rcx
  _BYTE v24[72]; // [rsp+50h] [rbp-48h] BYREF

  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 423) = a3;
  v4 = (struct _KEVENT *)operator new(24, 808544598, 64);
  *((_QWORD *)this + 199) = v4;
  if ( !v4 )
  {
    _InterlockedIncrement(&dword_140087760);
    WdLogSingleEntry0(6);
    v7 = 9714;
    v8 = L"Couldn't allocate our shutdown event\n";
LABEL_3:
    WdLogGlobalForLineNumber = v7;
    DxgkLogInternalTriageEvent(v5, 262145, v6, (_DWORD)v8, v7, 0, 0, 0);
    return 3221225495LL;
  }
  KeInitializeEvent(v4, NotificationEvent, 0);
  v10 = (struct _LOOKASIDE_LIST_EX *)operator new(96, 808544598, 64);
  *((_QWORD *)this + 164) = v10;
  if ( !v10 )
  {
    _InterlockedIncrement(&dword_140087760);
    WdLogSingleEntry0(6);
    v7 = 9728;
    v8 = L"Couldn't allocate our range pool lookaside list\n";
    goto LABEL_3;
  }
  LODWORD(v11) = ExInitializeLookasideListEx(v10, 0, 0, PagedPool, 0, 0xB0u, 0x32316956u, 0);
  if ( (int)v11 < 0 )
  {
    _InterlockedIncrement(&dword_140087760);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 9737;
    DxgkLogInternalTriageEvent(
      v12,
      262145,
      v13,
      (unsigned int)L"Couldn't initialize our range pool lookaside list\n",
      9737,
      0,
      0,
      0);
    return (unsigned int)v11;
  }
  for ( i = 0; i < 4; ++i )
  {
    v15 = ExAllocateFromLookasideListEx(*((PLOOKASIDE_LIST_EX *)this + 164));
    *((_QWORD *)this + i + 203) = v15;
    if ( !v15 )
    {
      _InterlockedIncrement(&dword_140087760);
      WdLogSingleEntry0(6);
      v7 = 9749;
      v8 = L"Couldn't initialize our extra range pool elements\n";
      goto LABEL_3;
    }
  }
  *((_DWORD *)this + 404) = 4;
  v16 = (struct _LOOKASIDE_LIST_EX *)operator new(96, 808544598, 64);
  *((_QWORD *)this + 165) = v16;
  if ( !v16 )
  {
    _InterlockedIncrement(&dword_140087760);
    WdLogSingleEntry0(6);
    v7 = 9760;
    v8 = L"Couldn't allocate our multirange pool lookaside list\n";
    goto LABEL_3;
  }
  v17 = ExInitializeLookasideListEx(v16, 0, 0, PagedPool, 0, 0x98u, 0x32316956u, 0);
  v11 = v17;
  if ( v17 < 0 )
  {
    _InterlockedIncrement(&dword_140087760);
    WdLogSingleEntry1(6, v17);
    WdLogGlobalForLineNumber = 9769;
    DxgkLogInternalTriageEvent(
      v18,
      262145,
      v19,
      (unsigned int)L"Couldn't initialize our multirange pool lookaside list. Status = 0x%I64x\n",
      v11,
      0,
      0,
      0);
    return (unsigned int)v11;
  }
  for ( j = 0; j < 4; ++j )
  {
    v21 = ExAllocateFromLookasideListEx(*((PLOOKASIDE_LIST_EX *)this + 165));
    *((_QWORD *)this + j + 207) = v21;
    if ( !v21 )
    {
      _InterlockedIncrement(&dword_140087760);
      WdLogSingleEntry0(6);
      v7 = 9781;
      v8 = L"Couldn't initialize our extra multirange pool elements\n";
      goto LABEL_3;
    }
  }
  v22 = VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock;
  *((_DWORD *)this + 405) = 4;
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE((DXGAUTOPUSHLOCKEXCLUSIVE *)v24, v22);
  v23 = (_QWORD *)qword_140087AA8;
  if ( *(struct _LIST_ENTRY **)qword_140087AA8 != &VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead )
    __fastfail(3u);
  *((_QWORD *)this + 201) = qword_140087AA8;
  *((_QWORD *)this + 200) = &VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead;
  *v23 = (char *)this + 1600;
  qword_140087AA8 = (__int64)this + 1600;
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v24);
  return 0;
}

```

## disassembly

```asm
0x140121540  push    rbx
0x140121542  push    rbp
0x140121543  push    rsi
0x140121544  push    rdi
0x140121545  sub     rsp, 78h
0x140121549  mov     [rcx+8], rdx
0x14012154d  mov     ebp, 40h ; '@'
0x140121552  mov     [rcx+69Ch], r8d
0x140121559  mov     rbx, rcx
0x14012155c  mov     r8d, ebp
0x14012155f  mov     edx, 30316956h
0x140121564  lea     ecx, [rbp-28h]
0x140121567  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14012156c  xor     esi, esi
0x14012156e  mov     [rbx+638h], rax
0x140121575  test    rax, rax
0x140121578  jnz     short loc_1401215CA
0x14012157a  lock inc cs:dword_140087760
0x140121581  lea     ecx, [rbp-3Ah]
0x140121584  call    cs:__imp_WdLogSingleEntry0
0x14012158b  nop     dword ptr [rax+rax+00h]
0x140121590  mov     eax, 25F2h
0x140121595  lea     r9, aCouldnTAllocat_26; "Couldn't allocate our shutdown event\n"
0x14012159c  mov     qword ptr [rsp+98h+Depth], rsi
0x1401215a1  mov     edx, 40001h
0x1401215a6  mov     qword ptr [rsp+98h+Tag], rsi
0x1401215ab  mov     [rsp+98h+Size], rsi
0x1401215b0  mov     qword ptr [rsp+98h+Flags], rax
0x1401215b5  mov     cs:WdLogGlobalForLineNumber, eax
0x1401215bb  call    DxgkLogInternalTriageEvent
0x1401215c0  mov     eax, 0C0000017h
0x1401215c5  jmp     loc_140121882
0x1401215ca  xor     r8d, r8d; State
0x1401215cd  xor     edx, edx; Type
0x1401215cf  mov     rcx, rax; Event
0x1401215d2  call    cs:__imp_KeInitializeEvent
0x1401215d9  nop     dword ptr [rax+rax+00h]
0x1401215de  mov     r8, rbp
0x1401215e1  mov     edx, 30316956h
0x1401215e6  mov     ecx, 60h ; '`'
0x1401215eb  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401215f0  mov     [rbx+520h], rax
0x1401215f7  mov     rcx, rax; Lookaside
0x1401215fa  test    rax, rax
0x1401215fd  jnz     short loc_140121626
0x1401215ff  lock inc cs:dword_140087760
0x140121606  lea     ecx, [rax+6]
0x140121609  call    cs:__imp_WdLogSingleEntry0
0x140121610  nop     dword ptr [rax+rax+00h]
0x140121615  mov     eax, 2600h
0x14012161a  lea     r9, aCouldnTAllocat_54; "Couldn't allocate our range pool lookas"...
0x140121621  jmp     loc_14012159C
0x140121626  mov     [rsp+98h+Depth], si; Depth
0x14012162b  mov     r9d, 1; PoolType
0x140121631  mov     [rsp+98h+Tag], 32316956h; Tag
0x140121639  xor     r8d, r8d; Free
0x14012163c  mov     [rsp+98h+Size], 0B0h; Size
0x140121645  xor     edx, edx; Allocate
0x140121647  mov     [rsp+98h+Flags], esi; Flags
0x14012164b  call    cs:__imp_ExInitializeLookasideListEx
0x140121652  nop     dword ptr [rax+rax+00h]
0x140121657  mov     edi, eax
0x140121659  test    eax, eax
0x14012165b  jns     short loc_1401216AC
0x14012165d  lock inc cs:dword_140087760
0x140121664  mov     ecx, 6
0x140121669  call    cs:__imp_WdLogSingleEntry0
0x140121670  nop     dword ptr [rax+rax+00h]
0x140121675  mov     qword ptr [rsp+98h+Depth], rsi
0x14012167a  lea     r9, aCouldnTInitial_1; "Couldn't initialize our range pool look"...
0x140121681  mov     eax, 2609h
0x140121686  mov     qword ptr [rsp+98h+Tag], rsi
0x14012168b  mov     [rsp+98h+Size], rsi
0x140121690  mov     cs:WdLogGlobalForLineNumber, eax
0x140121696  mov     qword ptr [rsp+98h+Flags], rax
0x14012169b  mov     edx, 40001h
0x1401216a0  call    DxgkLogInternalTriageEvent
0x1401216a5  mov     eax, edi
0x1401216a7  jmp     loc_140121882
0x1401216ac  mov     rdi, rsi
0x1401216af  cmp     rdi, 4
0x1401216b3  jnb     short loc_140121703
0x1401216b5  mov     rcx, [rbx+520h]; Lookaside
0x1401216bc  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401216c3  nop     dword ptr [rax+rax+00h]
0x1401216c8  mov     [rbx+rdi*8+658h], rax
0x1401216d0  test    rax, rax
0x1401216d3  jz      short loc_1401216DA
0x1401216d5  inc     rdi
0x1401216d8  jmp     short loc_1401216AF
0x1401216da  lock inc cs:dword_140087760
0x1401216e1  mov     ecx, 6
0x1401216e6  call    cs:__imp_WdLogSingleEntry0
0x1401216ed  nop     dword ptr [rax+rax+00h]
0x1401216f2  mov     eax, 2615h
0x1401216f7  lea     r9, aCouldnTInitial_4; "Couldn't initialize our extra range poo"...
0x1401216fe  jmp     loc_14012159C
0x140121703  mov     r8, rbp
0x140121706  mov     dword ptr [rbx+650h], 4
0x140121710  mov     edx, 30316956h
0x140121715  mov     ecx, 60h ; '`'
0x14012171a  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14012171f  mov     [rbx+528h], rax
0x140121726  mov     rcx, rax; Lookaside
0x140121729  test    rax, rax
0x14012172c  jnz     short loc_140121755
0x14012172e  lock inc cs:dword_140087760
0x140121735  lea     ecx, [rax+6]
0x140121738  call    cs:__imp_WdLogSingleEntry0
0x14012173f  nop     dword ptr [rax+rax+00h]
0x140121744  mov     eax, 2620h
0x140121749  lea     r9, aCouldnTAllocat_3; "Couldn't allocate our multirange pool l"...
0x140121750  jmp     loc_14012159C
0x140121755  mov     [rsp+98h+Depth], si; Depth
0x14012175a  mov     r9d, 1; PoolType
0x140121760  mov     [rsp+98h+Tag], 32316956h; Tag
0x140121768  xor     r8d, r8d; Free
0x14012176b  mov     [rsp+98h+Size], 98h; Size
0x140121774  xor     edx, edx; Allocate
0x140121776  mov     [rsp+98h+Flags], esi; Flags
0x14012177a  call    cs:__imp_ExInitializeLookasideListEx
0x140121781  nop     dword ptr [rax+rax+00h]
0x140121786  movsxd  rdi, eax
0x140121789  test    eax, eax
0x14012178b  jns     short loc_1401217D2
0x14012178d  lock inc cs:dword_140087760
0x140121794  mov     rdx, rdi
0x140121797  mov     ecx, 6
0x14012179c  call    cs:__imp_WdLogSingleEntry1
0x1401217a3  nop     dword ptr [rax+rax+00h]
0x1401217a8  mov     qword ptr [rsp+98h+Depth], rsi
0x1401217ad  lea     r9, aCouldnTInitial_5; "Couldn't initialize our multirange pool"...
0x1401217b4  mov     qword ptr [rsp+98h+Tag], rsi
0x1401217b9  mov     [rsp+98h+Size], rsi
0x1401217be  mov     qword ptr [rsp+98h+Flags], rdi
0x1401217c3  mov     cs:WdLogGlobalForLineNumber, 2629h
0x1401217cd  jmp     loc_14012169B
0x1401217d2  mov     rdi, rsi
0x1401217d5  cmp     rdi, 4
0x1401217d9  jnb     short loc_140121829
0x1401217db  mov     rcx, [rbx+528h]; Lookaside
0x1401217e2  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401217e9  nop     dword ptr [rax+rax+00h]
0x1401217ee  mov     [rbx+rdi*8+678h], rax
0x1401217f6  test    rax, rax
0x1401217f9  jz      short loc_140121800
0x1401217fb  inc     rdi
0x1401217fe  jmp     short loc_1401217D5
0x140121800  lock inc cs:dword_140087760
0x140121807  mov     ecx, 6
0x14012180c  call    cs:__imp_WdLogSingleEntry0
0x140121813  nop     dword ptr [rax+rax+00h]
0x140121818  mov     eax, 2635h
0x14012181d  lea     r9, aCouldnTInitial; "Couldn't initialize our extra multirang"...
0x140121824  jmp     loc_14012159C
0x140121829  mov     rdx, cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA; struct DXGPUSHLOCK *
0x140121830  lea     rcx, [rsp+98h+var_48]; this
0x140121835  mov     dword ptr [rbx+654h], 4
0x14012183f  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x140121844  mov     rcx, cs:qword_140087AA8
0x14012184b  lea     rdx, ?_GlobalHeapManagerListHead@VIDMM_RECYCLE_HEAP_MGR@@0U_LIST_ENTRY@@A; _LIST_ENTRY VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead
0x140121852  cmp     [rcx], rdx
0x140121855  jz      short loc_14012185E
0x140121857  mov     ecx, 3
0x14012185c  int     29h; Win8: RtlFailFast(ecx)
0x14012185e  lea     rax, [rbx+640h]
0x140121865  mov     [rax+8], rcx
0x140121869  mov     [rax], rdx
0x14012186c  mov     [rcx], rax
0x14012186f  lea     rcx, [rsp+98h+var_48]; this
0x140121874  mov     cs:qword_140087AA8, rax
0x14012187b  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140121880  xor     eax, eax
0x140121882  add     rsp, 78h
0x140121886  pop     rdi
0x140121887  pop     rsi
0x140121888  pop     rbp
0x140121889  pop     rbx
0x14012188a  retn
```
