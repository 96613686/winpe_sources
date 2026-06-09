# VIDMM_RECYCLE_HEAP_MGR::Init(VIDMM_PROCESS *,ulong)

- ea: `0x14011dd60`
- end: `0x14011e0ac`
- name: `?Init@VIDMM_RECYCLE_HEAP_MGR@@UEAAJPEAVVIDMM_PROCESS@@K@Z`
- size: `844`
- prototype: `__int64 __fastcall(VIDMM_RECYCLE_HEAP_MGR *__hidden this, struct VIDMM_PROCESS *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002ec00`
- `0x14002ed1c`
- `0x14011dd60`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14011de6b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14011df9a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14011de6b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14011df9a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14011dedc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14011e002`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14011dedc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14011e002`
- `ntoskrnl!KeInitializeEvent` at `0x14011ddf2`
- `ntoskrnl!KeInitializeEvent` at `0x14011ddf2`
- `watchdog!WdLogSingleEntry0` at `0x14011dda4`
- `watchdog!WdLogSingleEntry0` at `0x14011de29`
- `watchdog!WdLogSingleEntry0` at `0x14011de89`
- `watchdog!WdLogSingleEntry0` at `0x14011df06`
- `watchdog!WdLogSingleEntry0` at `0x14011df58`
- `watchdog!WdLogSingleEntry0` at `0x14011e02c`
- `watchdog!WdLogSingleEntry0` at `0x14011dda4`
- `watchdog!WdLogSingleEntry0` at `0x14011de29`
- `watchdog!WdLogSingleEntry0` at `0x14011de89`
- `watchdog!WdLogSingleEntry0` at `0x14011df06`
- `watchdog!WdLogSingleEntry0` at `0x14011df58`
- `watchdog!WdLogSingleEntry0` at `0x14011e02c`
- `watchdog!WdLogSingleEntry1` at `0x14011dfbc`
- `watchdog!WdLogSingleEntry1` at `0x14011dfbc`

## string_xrefs

- `0x14011de3a`: `Couldn't allocate our range pool lookaside list\n`
- `0x14011de9a`: `Couldn't initialize our range pool lookaside list\n`
- `0x14011dfcd`: `Couldn't initialize our multirange pool lookaside list. Status = 0x%I64x\n`
- `0x14011df69`: `Couldn't allocate our multirange pool lookaside list\n`

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
    _InterlockedIncrement(&dword_140086780);
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
    _InterlockedIncrement(&dword_140086780);
    WdLogSingleEntry0(6);
    v7 = 9728;
    v8 = L"Couldn't allocate our range pool lookaside list\n";
    goto LABEL_3;
  }
  LODWORD(v11) = ExInitializeLookasideListEx(v10, 0, 0, PagedPool, 0, 0xB0u, 0x32316956u, 0);
  if ( (int)v11 < 0 )
  {
    _InterlockedIncrement(&dword_140086780);
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
      _InterlockedIncrement(&dword_140086780);
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
    _InterlockedIncrement(&dword_140086780);
    WdLogSingleEntry0(6);
    v7 = 9760;
    v8 = L"Couldn't allocate our multirange pool lookaside list\n";
    goto LABEL_3;
  }
  v17 = ExInitializeLookasideListEx(v16, 0, 0, PagedPool, 0, 0x98u, 0x32316956u, 0);
  v11 = v17;
  if ( v17 < 0 )
  {
    _InterlockedIncrement(&dword_140086780);
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
      _InterlockedIncrement(&dword_140086780);
      WdLogSingleEntry0(6);
      v7 = 9781;
      v8 = L"Couldn't initialize our extra multirange pool elements\n";
      goto LABEL_3;
    }
  }
  v22 = VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListLock;
  *((_DWORD *)this + 405) = 4;
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE((DXGAUTOPUSHLOCKEXCLUSIVE *)v24, v22);
  v23 = (_QWORD *)qword_140086AC8;
  if ( *(struct _LIST_ENTRY **)qword_140086AC8 != &VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead )
    __fastfail(3u);
  *((_QWORD *)this + 201) = qword_140086AC8;
  *((_QWORD *)this + 200) = &VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead;
  *v23 = (char *)this + 1600;
  qword_140086AC8 = (__int64)this + 1600;
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v24);
  return 0;
}

```

## disassembly

```asm
0x14011dd60  push    rbx
0x14011dd62  push    rbp
0x14011dd63  push    rsi
0x14011dd64  push    rdi
0x14011dd65  sub     rsp, 78h
0x14011dd69  mov     [rcx+8], rdx
0x14011dd6d  mov     ebp, 40h ; '@'
0x14011dd72  mov     [rcx+69Ch], r8d
0x14011dd79  mov     rbx, rcx
0x14011dd7c  mov     r8d, ebp
0x14011dd7f  mov     edx, 30316956h
0x14011dd84  lea     ecx, [rbp-28h]
0x14011dd87  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011dd8c  xor     esi, esi
0x14011dd8e  mov     [rbx+638h], rax
0x14011dd95  test    rax, rax
0x14011dd98  jnz     short loc_14011DDEA
0x14011dd9a  lock inc cs:dword_140086780
0x14011dda1  lea     ecx, [rbp-3Ah]
0x14011dda4  call    cs:__imp_WdLogSingleEntry0
0x14011ddab  nop     dword ptr [rax+rax+00h]
0x14011ddb0  mov     eax, 25F2h
0x14011ddb5  lea     r9, aCouldnTAllocat_24; "Couldn't allocate our shutdown event\n"
0x14011ddbc  mov     qword ptr [rsp+98h+Depth], rsi
0x14011ddc1  mov     edx, 40001h
0x14011ddc6  mov     qword ptr [rsp+98h+Tag], rsi
0x14011ddcb  mov     [rsp+98h+Size], rsi
0x14011ddd0  mov     qword ptr [rsp+98h+Flags], rax
0x14011ddd5  mov     cs:WdLogGlobalForLineNumber, eax
0x14011dddb  call    DxgkLogInternalTriageEvent
0x14011dde0  mov     eax, 0C0000017h
0x14011dde5  jmp     loc_14011E0A2
0x14011ddea  xor     r8d, r8d; State
0x14011dded  xor     edx, edx; Type
0x14011ddef  mov     rcx, rax; Event
0x14011ddf2  call    cs:__imp_KeInitializeEvent
0x14011ddf9  nop     dword ptr [rax+rax+00h]
0x14011ddfe  mov     r8, rbp
0x14011de01  mov     edx, 30316956h
0x14011de06  mov     ecx, 60h ; '`'
0x14011de0b  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011de10  mov     [rbx+520h], rax
0x14011de17  mov     rcx, rax; Lookaside
0x14011de1a  test    rax, rax
0x14011de1d  jnz     short loc_14011DE46
0x14011de1f  lock inc cs:dword_140086780
0x14011de26  lea     ecx, [rax+6]
0x14011de29  call    cs:__imp_WdLogSingleEntry0
0x14011de30  nop     dword ptr [rax+rax+00h]
0x14011de35  mov     eax, 2600h
0x14011de3a  lea     r9, aCouldnTAllocat_50; "Couldn't allocate our range pool lookas"...
0x14011de41  jmp     loc_14011DDBC
0x14011de46  mov     [rsp+98h+Depth], si; Depth
0x14011de4b  mov     r9d, 1; PoolType
0x14011de51  mov     [rsp+98h+Tag], 32316956h; Tag
0x14011de59  xor     r8d, r8d; Free
0x14011de5c  mov     [rsp+98h+Size], 0B0h; Size
0x14011de65  xor     edx, edx; Allocate
0x14011de67  mov     [rsp+98h+Flags], esi; Flags
0x14011de6b  call    cs:__imp_ExInitializeLookasideListEx
0x14011de72  nop     dword ptr [rax+rax+00h]
0x14011de77  mov     edi, eax
0x14011de79  test    eax, eax
0x14011de7b  jns     short loc_14011DECC
0x14011de7d  lock inc cs:dword_140086780
0x14011de84  mov     ecx, 6
0x14011de89  call    cs:__imp_WdLogSingleEntry0
0x14011de90  nop     dword ptr [rax+rax+00h]
0x14011de95  mov     qword ptr [rsp+98h+Depth], rsi
0x14011de9a  lea     r9, aCouldnTInitial_1; "Couldn't initialize our range pool look"...
0x14011dea1  mov     eax, 2609h
0x14011dea6  mov     qword ptr [rsp+98h+Tag], rsi
0x14011deab  mov     [rsp+98h+Size], rsi
0x14011deb0  mov     cs:WdLogGlobalForLineNumber, eax
0x14011deb6  mov     qword ptr [rsp+98h+Flags], rax
0x14011debb  mov     edx, 40001h
0x14011dec0  call    DxgkLogInternalTriageEvent
0x14011dec5  mov     eax, edi
0x14011dec7  jmp     loc_14011E0A2
0x14011decc  mov     rdi, rsi
0x14011decf  cmp     rdi, 4
0x14011ded3  jnb     short loc_14011DF23
0x14011ded5  mov     rcx, [rbx+520h]; Lookaside
0x14011dedc  call    cs:__imp_ExAllocateFromLookasideListEx
0x14011dee3  nop     dword ptr [rax+rax+00h]
0x14011dee8  mov     [rbx+rdi*8+658h], rax
0x14011def0  test    rax, rax
0x14011def3  jz      short loc_14011DEFA
0x14011def5  inc     rdi
0x14011def8  jmp     short loc_14011DECF
0x14011defa  lock inc cs:dword_140086780
0x14011df01  mov     ecx, 6
0x14011df06  call    cs:__imp_WdLogSingleEntry0
0x14011df0d  nop     dword ptr [rax+rax+00h]
0x14011df12  mov     eax, 2615h
0x14011df17  lea     r9, aCouldnTInitial_4; "Couldn't initialize our extra range poo"...
0x14011df1e  jmp     loc_14011DDBC
0x14011df23  mov     r8, rbp
0x14011df26  mov     dword ptr [rbx+650h], 4
0x14011df30  mov     edx, 30316956h
0x14011df35  mov     ecx, 60h ; '`'
0x14011df3a  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011df3f  mov     [rbx+528h], rax
0x14011df46  mov     rcx, rax; Lookaside
0x14011df49  test    rax, rax
0x14011df4c  jnz     short loc_14011DF75
0x14011df4e  lock inc cs:dword_140086780
0x14011df55  lea     ecx, [rax+6]
0x14011df58  call    cs:__imp_WdLogSingleEntry0
0x14011df5f  nop     dword ptr [rax+rax+00h]
0x14011df64  mov     eax, 2620h
0x14011df69  lea     r9, aCouldnTAllocat_3; "Couldn't allocate our multirange pool l"...
0x14011df70  jmp     loc_14011DDBC
0x14011df75  mov     [rsp+98h+Depth], si; Depth
0x14011df7a  mov     r9d, 1; PoolType
0x14011df80  mov     [rsp+98h+Tag], 32316956h; Tag
0x14011df88  xor     r8d, r8d; Free
0x14011df8b  mov     [rsp+98h+Size], 98h; Size
0x14011df94  xor     edx, edx; Allocate
0x14011df96  mov     [rsp+98h+Flags], esi; Flags
0x14011df9a  call    cs:__imp_ExInitializeLookasideListEx
0x14011dfa1  nop     dword ptr [rax+rax+00h]
0x14011dfa6  movsxd  rdi, eax
0x14011dfa9  test    eax, eax
0x14011dfab  jns     short loc_14011DFF2
0x14011dfad  lock inc cs:dword_140086780
0x14011dfb4  mov     rdx, rdi
0x14011dfb7  mov     ecx, 6
0x14011dfbc  call    cs:__imp_WdLogSingleEntry1
0x14011dfc3  nop     dword ptr [rax+rax+00h]
0x14011dfc8  mov     qword ptr [rsp+98h+Depth], rsi
0x14011dfcd  lea     r9, aCouldnTInitial_5; "Couldn't initialize our multirange pool"...
0x14011dfd4  mov     qword ptr [rsp+98h+Tag], rsi
0x14011dfd9  mov     [rsp+98h+Size], rsi
0x14011dfde  mov     qword ptr [rsp+98h+Flags], rdi
0x14011dfe3  mov     cs:WdLogGlobalForLineNumber, 2629h
0x14011dfed  jmp     loc_14011DEBB
0x14011dff2  mov     rdi, rsi
0x14011dff5  cmp     rdi, 4
0x14011dff9  jnb     short loc_14011E049
0x14011dffb  mov     rcx, [rbx+528h]; Lookaside
0x14011e002  call    cs:__imp_ExAllocateFromLookasideListEx
0x14011e009  nop     dword ptr [rax+rax+00h]
0x14011e00e  mov     [rbx+rdi*8+678h], rax
0x14011e016  test    rax, rax
0x14011e019  jz      short loc_14011E020
0x14011e01b  inc     rdi
0x14011e01e  jmp     short loc_14011DFF5
0x14011e020  lock inc cs:dword_140086780
0x14011e027  mov     ecx, 6
0x14011e02c  call    cs:__imp_WdLogSingleEntry0
0x14011e033  nop     dword ptr [rax+rax+00h]
0x14011e038  mov     eax, 2635h
0x14011e03d  lea     r9, aCouldnTInitial; "Couldn't initialize our extra multirang"...
0x14011e044  jmp     loc_14011DDBC
0x14011e049  mov     rdx, cs:?_GlobalHeapManagerListLock@VIDMM_RECYCLE_HEAP_MGR@@0PEAVDXGPUSHLOCK@@EA; struct DXGPUSHLOCK *
0x14011e050  lea     rcx, [rsp+98h+var_48]; this
0x14011e055  mov     dword ptr [rbx+654h], 4
0x14011e05f  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x14011e064  mov     rcx, cs:qword_140086AC8
0x14011e06b  lea     rdx, ?_GlobalHeapManagerListHead@VIDMM_RECYCLE_HEAP_MGR@@0U_LIST_ENTRY@@A; _LIST_ENTRY VIDMM_RECYCLE_HEAP_MGR::_GlobalHeapManagerListHead
0x14011e072  cmp     [rcx], rdx
0x14011e075  jz      short loc_14011E07E
0x14011e077  mov     ecx, 3
0x14011e07c  int     29h; Win8: RtlFailFast(ecx)
0x14011e07e  lea     rax, [rbx+640h]
0x14011e085  mov     [rax+8], rcx
0x14011e089  mov     [rax], rdx
0x14011e08c  mov     [rcx], rax
0x14011e08f  lea     rcx, [rsp+98h+var_48]; this
0x14011e094  mov     cs:qword_140086AC8, rax
0x14011e09b  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14011e0a0  xor     eax, eax
0x14011e0a2  add     rsp, 78h
0x14011e0a6  pop     rdi
0x14011e0a7  pop     rsi
0x14011e0a8  pop     rbp
0x14011e0a9  pop     rbx
0x14011e0aa  retn
```
