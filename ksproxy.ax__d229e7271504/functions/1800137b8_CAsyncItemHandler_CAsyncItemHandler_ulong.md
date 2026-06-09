# CAsyncItemHandler::CAsyncItemHandler(ulong *)

- ea: `0x1800137b8`
- end: `0x180013abf`
- name: `??0CAsyncItemHandler@@QEAA@PEAK@Z`
- size: `775`
- prototype: `CAsyncItemHandler *__fastcall(CAsyncItemHandler *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013570`
- `0x18001e69c`
- `0x18002fd70`

## callees

- `0x180002b58`
- `0x1800137b8`
- `0x18001c050`
- `0x18001cd38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001385e`
- `KERNEL32!GetLastError` at `0x1800138ce`
- `KERNEL32!GetLastError` at `0x180013923`
- `KERNEL32!GetLastError` at `0x18001397c`
- `KERNEL32!GetLastError` at `0x1800139e2`
- `KERNEL32!GetLastError` at `0x18001385e`
- `KERNEL32!GetLastError` at `0x1800138ce`
- `KERNEL32!GetLastError` at `0x180013923`
- `KERNEL32!GetLastError` at `0x18001397c`
- `KERNEL32!GetLastError` at `0x1800139e2`
- `KERNEL32!CreateEventW` at `0x180013846`
- `KERNEL32!CreateEventW` at `0x180013964`
- `KERNEL32!CreateEventW` at `0x180013846`
- `KERNEL32!CreateEventW` at `0x180013964`
- `KERNEL32!CloseHandle` at `0x180013a33`
- `KERNEL32!CloseHandle` at `0x180013a52`
- `KERNEL32!CloseHandle` at `0x180013a71`
- `KERNEL32!CloseHandle` at `0x180013a90`
- `KERNEL32!CloseHandle` at `0x180013a33`
- `KERNEL32!CloseHandle` at `0x180013a52`
- `KERNEL32!CloseHandle` at `0x180013a71`
- `KERNEL32!CloseHandle` at `0x180013a90`
- `KERNEL32!CreateThread` at `0x1800139c6`
- `KERNEL32!CreateThread` at `0x1800139c6`
- `KERNEL32!CreateSemaphoreW` at `0x1800138b6`
- `KERNEL32!CreateSemaphoreW` at `0x1800138b6`
- `KERNEL32!CreateMutexW` at `0x18001390b`
- `KERNEL32!CreateMutexW` at `0x18001390b`

## pseudocode

```c
CAsyncItemHandler *__fastcall CAsyncItemHandler::CAsyncItemHandler(CAsyncItemHandler *this, unsigned int *a2)
{
  unsigned int *lpThreadId; // r14
  struct _ITEM_LIST_HEAD *p_m_eventList; // rbp
  DWORD LastError; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  USHORT v9; // dx
  HANDLE EventW; // rax
  HANDLE SemaphoreW; // rax
  DWORD v12; // eax
  HANDLE MutexW; // rax
  DWORD v14; // eax
  HANDLE v15; // rax
  DWORD v16; // eax
  HANDLE Thread; // rax
  DWORD v18; // eax
  void *m_hWakeupEvent; // rcx
  void *m_hSlotSemaphore; // rcx
  void *m_hItemMutex; // rcx
  void *m_AsyncEvent; // rcx

  lpThreadId = &this->m_threadId;
  p_m_eventList = &this->m_eventList;
  *(_QWORD *)&this->m_arrayCount = 0;
  this->m_AsyncEvent = 0;
  this->m_hWakeupEvent = 0;
  this->m_hSlotSemaphore = 0;
  this->m_hItemMutex = 0;
  this->m_hThread = 0;
  this->m_threadId = 0;
  LastError = ItemListInitialize(&this->m_eventList);
  v7 = LastError;
  if ( LastError )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_8;
    v9 = 199;
    goto LABEL_7;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  this->m_hWakeupEvent = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      v9 = 200;
LABEL_7:
      WPP_SF_d(v8[2], v9, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, LastError);
    }
  }
LABEL_8:
  this->m_hEvents[this->m_arrayCount++] = this->m_hWakeupEvent;
  if ( v7 )
    goto LABEL_25;
  SemaphoreW = CreateSemaphoreW(0, 63, 63, 0);
  this->m_hSlotSemaphore = SemaphoreW;
  if ( !SemaphoreW )
  {
    v12 = GetLastError();
    v7 = v12;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xC9u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v12);
    if ( v7 )
      goto LABEL_25;
  }
  MutexW = CreateMutexW(0, 0, 0);
  this->m_hItemMutex = MutexW;
  if ( !MutexW )
  {
    v14 = GetLastError();
    v7 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCAu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v14);
    if ( v7 )
      goto LABEL_25;
  }
  v15 = CreateEventW(0, 0, 1, 0);
  this->m_AsyncEvent = v15;
  if ( !v15 )
  {
    v16 = GetLastError();
    v7 = v16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCBu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v16);
    if ( v7 )
      goto LABEL_25;
  }
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CAsyncItemHandler::AsyncItemProc, this, 0, lpThreadId);
  this->m_hThread = Thread;
  if ( !Thread )
  {
    v18 = GetLastError();
    v7 = v18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCCu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v18);
    if ( v7 )
    {
LABEL_25:
      ItemListCleanup(p_m_eventList);
      m_hWakeupEvent = this->m_hWakeupEvent;
      this->m_arrayCount = 0;
      if ( m_hWakeupEvent )
      {
        CloseHandle(m_hWakeupEvent);
        this->m_hWakeupEvent = 0;
      }
      m_hSlotSemaphore = this->m_hSlotSemaphore;
      if ( m_hSlotSemaphore )
      {
        CloseHandle(m_hSlotSemaphore);
        this->m_hSlotSemaphore = 0;
      }
      m_hItemMutex = this->m_hItemMutex;
      if ( m_hItemMutex )
      {
        CloseHandle(m_hItemMutex);
        this->m_hItemMutex = 0;
      }
      m_AsyncEvent = this->m_AsyncEvent;
      if ( m_AsyncEvent )
      {
        CloseHandle(m_AsyncEvent);
        this->m_AsyncEvent = 0;
      }
    }
  }
  if ( a2 )
    *a2 = v7;
  return this;
}

```

## disassembly

```asm
0x1800137b8  push    rbx
0x1800137ba  push    rbp
0x1800137bb  push    rsi
0x1800137bc  push    rdi
0x1800137bd  push    r12
0x1800137bf  push    r13
0x1800137c1  push    r14
0x1800137c3  push    r15
0x1800137c5  sub     rsp, 38h
0x1800137c9  xor     r15d, r15d
0x1800137cc  lea     r14, [rcx+468h]
0x1800137d3  lea     rbp, [rcx+418h]
0x1800137da  mov     [rcx+400h], r15
0x1800137e1  mov     [rcx+410h], r15
0x1800137e8  mov     rbx, rcx
0x1800137eb  mov     [rcx+448h], r15
0x1800137f2  mov     rsi, rdx
0x1800137f5  mov     [rcx+450h], r15
0x1800137fc  mov     [rcx+458h], r15
0x180013803  mov     [rcx+460h], r15
0x18001380a  mov     rcx, rbp; struct _ITEM_LIST_HEAD *
0x18001380d  mov     [r14], r15d
0x180013810  call    ?ItemListInitialize@@YAKPEAU_ITEM_LIST_HEAD@@@Z; ItemListInitialize(_ITEM_LIST_HEAD *)
0x180013815  lea     r13, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x18001381c  mov     edi, eax
0x18001381e  lea     r12, WPP_GLOBAL_Control
0x180013825  test    eax, eax
0x180013827  jz      short loc_18001383C
0x180013829  mov     rcx, cs:WPP_GLOBAL_Control
0x180013830  cmp     rcx, r12
0x180013833  jz      short loc_18001388C
0x180013835  mov     edx, 0C7h
0x18001383a  jmp     short loc_18001387D
0x18001383c  xor     r9d, r9d; lpName
0x18001383f  xor     r8d, r8d; bInitialState
0x180013842  xor     edx, edx; bManualReset
0x180013844  xor     ecx, ecx; lpEventAttributes
0x180013846  call    cs:__imp_CreateEventW
0x18001384d  nop     dword ptr [rax+rax+00h]
0x180013852  mov     [rbx+448h], rax
0x180013859  test    rax, rax
0x18001385c  jnz     short loc_18001388C
0x18001385e  call    cs:__imp_GetLastError
0x180013865  nop     dword ptr [rax+rax+00h]
0x18001386a  mov     edi, eax
0x18001386c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013873  cmp     rcx, r12
0x180013876  jz      short loc_18001388C
0x180013878  mov     edx, 0C8h
0x18001387d  mov     rcx, [rcx+10h]
0x180013881  mov     r9d, eax
0x180013884  mov     r8, r13
0x180013887  call    WPP_SF_d
0x18001388c  mov     ecx, [rbx+400h]
0x180013892  mov     rax, [rbx+448h]
0x180013899  mov     [rbx+rcx*8], rax
0x18001389d  inc     dword ptr [rbx+400h]
0x1800138a3  test    edi, edi
0x1800138a5  jnz     loc_180013A18
0x1800138ab  lea     edx, [rdi+3Fh]; lInitialCount
0x1800138ae  xor     r9d, r9d; lpName
0x1800138b1  mov     r8d, edx; lMaximumCount
0x1800138b4  xor     ecx, ecx; lpSemaphoreAttributes
0x1800138b6  call    cs:__imp_CreateSemaphoreW
0x1800138bd  nop     dword ptr [rax+rax+00h]
0x1800138c2  mov     [rbx+450h], rax
0x1800138c9  test    rax, rax
0x1800138cc  jnz     short loc_180013904
0x1800138ce  call    cs:__imp_GetLastError
0x1800138d5  nop     dword ptr [rax+rax+00h]
0x1800138da  mov     edi, eax
0x1800138dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138e3  cmp     rcx, r12
0x1800138e6  jz      short loc_1800138FC
0x1800138e8  mov     rcx, [rcx+10h]
0x1800138ec  mov     edx, 0C9h
0x1800138f1  mov     r9d, eax
0x1800138f4  mov     r8, r13
0x1800138f7  call    WPP_SF_d
0x1800138fc  test    edi, edi
0x1800138fe  jnz     loc_180013A18
0x180013904  xor     r8d, r8d; lpName
0x180013907  xor     edx, edx; bInitialOwner
0x180013909  xor     ecx, ecx; lpMutexAttributes
0x18001390b  call    cs:__imp_CreateMutexW
0x180013912  nop     dword ptr [rax+rax+00h]
0x180013917  mov     [rbx+458h], rax
0x18001391e  test    rax, rax
0x180013921  jnz     short loc_180013959
0x180013923  call    cs:__imp_GetLastError
0x18001392a  nop     dword ptr [rax+rax+00h]
0x18001392f  mov     edi, eax
0x180013931  mov     rcx, cs:WPP_GLOBAL_Control
0x180013938  cmp     rcx, r12
0x18001393b  jz      short loc_180013951
0x18001393d  mov     rcx, [rcx+10h]
0x180013941  mov     edx, 0CAh
0x180013946  mov     r9d, eax
0x180013949  mov     r8, r13
0x18001394c  call    WPP_SF_d
0x180013951  test    edi, edi
0x180013953  jnz     loc_180013A18
0x180013959  xor     r9d, r9d; lpName
0x18001395c  xor     edx, edx; bManualReset
0x18001395e  xor     ecx, ecx; lpEventAttributes
0x180013960  lea     r8d, [r9+1]; bInitialState
0x180013964  call    cs:__imp_CreateEventW
0x18001396b  nop     dword ptr [rax+rax+00h]
0x180013970  mov     [rbx+410h], rax
0x180013977  test    rax, rax
0x18001397a  jnz     short loc_1800139AE
0x18001397c  call    cs:__imp_GetLastError
0x180013983  nop     dword ptr [rax+rax+00h]
0x180013988  mov     edi, eax
0x18001398a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013991  cmp     rcx, r12
0x180013994  jz      short loc_1800139AA
0x180013996  mov     rcx, [rcx+10h]
0x18001399a  mov     edx, 0CBh
0x18001399f  mov     r9d, eax
0x1800139a2  mov     r8, r13
0x1800139a5  call    WPP_SF_d
0x1800139aa  test    edi, edi
0x1800139ac  jnz     short loc_180013A18
0x1800139ae  mov     [rsp+78h+lpThreadId], r14; lpThreadId
0x1800139b3  lea     r8, ?AsyncItemProc@CAsyncItemHandler@@KAKPEAV1@@Z; lpStartAddress
0x1800139ba  mov     r9, rbx; lpParameter
0x1800139bd  mov     [rsp+78h+dwCreationFlags], r15d; dwCreationFlags
0x1800139c2  xor     edx, edx; dwStackSize
0x1800139c4  xor     ecx, ecx; lpThreadAttributes
0x1800139c6  call    cs:__imp_CreateThread
0x1800139cd  nop     dword ptr [rax+rax+00h]
0x1800139d2  mov     [rbx+460h], rax
0x1800139d9  test    rax, rax
0x1800139dc  jnz     loc_180013AA3
0x1800139e2  call    cs:__imp_GetLastError
0x1800139e9  nop     dword ptr [rax+rax+00h]
0x1800139ee  mov     edi, eax
0x1800139f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139f7  cmp     rcx, r12
0x1800139fa  jz      short loc_180013A10
0x1800139fc  mov     rcx, [rcx+10h]
0x180013a00  mov     edx, 0CCh
0x180013a05  mov     r9d, eax
0x180013a08  mov     r8, r13
0x180013a0b  call    WPP_SF_d
0x180013a10  test    edi, edi
0x180013a12  jz      loc_180013AA3
0x180013a18  mov     rcx, rbp; struct _ITEM_LIST_HEAD *
0x180013a1b  call    ?ItemListCleanup@@YAXPEAU_ITEM_LIST_HEAD@@@Z; ItemListCleanup(_ITEM_LIST_HEAD *)
0x180013a20  mov     rcx, [rbx+448h]; hObject
0x180013a27  mov     [rbx+400h], r15d
0x180013a2e  test    rcx, rcx
0x180013a31  jz      short loc_180013A46
0x180013a33  call    cs:__imp_CloseHandle
0x180013a3a  nop     dword ptr [rax+rax+00h]
0x180013a3f  mov     [rbx+448h], r15
0x180013a46  mov     rcx, [rbx+450h]; hObject
0x180013a4d  test    rcx, rcx
0x180013a50  jz      short loc_180013A65
0x180013a52  call    cs:__imp_CloseHandle
0x180013a59  nop     dword ptr [rax+rax+00h]
0x180013a5e  mov     [rbx+450h], r15
0x180013a65  mov     rcx, [rbx+458h]; hObject
0x180013a6c  test    rcx, rcx
0x180013a6f  jz      short loc_180013A84
0x180013a71  call    cs:__imp_CloseHandle
0x180013a78  nop     dword ptr [rax+rax+00h]
0x180013a7d  mov     [rbx+458h], r15
0x180013a84  mov     rcx, [rbx+410h]; hObject
0x180013a8b  test    rcx, rcx
0x180013a8e  jz      short loc_180013AA3
0x180013a90  call    cs:__imp_CloseHandle
0x180013a97  nop     dword ptr [rax+rax+00h]
0x180013a9c  mov     [rbx+410h], r15
0x180013aa3  test    rsi, rsi
0x180013aa6  jz      short loc_180013AAA
0x180013aa8  mov     [rsi], edi
0x180013aaa  mov     rax, rbx
0x180013aad  add     rsp, 38h
0x180013ab1  pop     r15
0x180013ab3  pop     r14
0x180013ab5  pop     r13
0x180013ab7  pop     r12
0x180013ab9  pop     rdi
0x180013aba  pop     rsi
0x180013abb  pop     rbp
0x180013abc  pop     rbx
0x180013abd  retn
```
