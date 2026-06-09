# CKsOutputPin::InitializeAsyncThread(void)

- ea: `0x180013570`
- end: `0x1800137b0`
- name: `?InitializeAsyncThread@CKsOutputPin@@UEAAJXZ`
- size: `576`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000df50`
- `0x180013570`
- `0x1800137b8`
- `0x18001e720`
- `0x18001f1c4`
- `0x18001f1d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18001361e`
- `KERNEL32!CreateEventW` at `0x18001363b`
- `KERNEL32!CreateEventW` at `0x180013658`
- `KERNEL32!CreateEventW` at `0x18001361e`
- `KERNEL32!CreateEventW` at `0x18001363b`
- `KERNEL32!CreateEventW` at `0x180013658`
- `KERNEL32!CloseHandle` at `0x18001374f`
- `KERNEL32!CloseHandle` at `0x18001376e`
- `KERNEL32!CloseHandle` at `0x18001378d`
- `KERNEL32!CloseHandle` at `0x18001374f`
- `KERNEL32!CloseHandle` at `0x18001376e`
- `KERNEL32!CloseHandle` at `0x18001378d`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::InitializeAsyncThread(CKsOutputPin *this)
{
  struct _ASYNC_ITEM *v2; // rsi
  struct _ASYNC_ITEM *v3; // rax
  signed int v4; // edi
  struct _ASYNC_ITEM *v5; // r14
  CAsyncItemHandler *v6; // rax
  unsigned int v7; // edx
  CAsyncItemHandler *v8; // rax
  HANDLE EventW; // rax
  unsigned int v10; // edx
  CAsyncItemHandler *m_pAsyncItemHandler; // rcx
  void *m_hMarshalEvent; // rcx
  void *m_hFlushEvent; // rcx
  void *m_hFlushCompleteEvent; // rcx
  unsigned int v16; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _ASYNC_ITEM *)operator new(0x30u);
  v3 = (struct _ASYNC_ITEM *)operator new(0x30u);
  v4 = 0;
  v16 = 0;
  v5 = v3;
  v6 = (CAsyncItemHandler *)operator new(0x470u);
  if ( v6 )
  {
    v8 = CAsyncItemHandler::CAsyncItemHandler(v6, &v16);
    v4 = v16;
  }
  else
  {
    v8 = 0;
  }
  this->m_pAsyncItemHandler = v8;
  if ( v4 )
  {
    if ( v8 )
      CAsyncItemHandler::`scalar deleting destructor'(v8, v7);
    operator delete(v2, 0x30u);
    operator delete(v5, 0x30u);
    this->m_pAsyncItemHandler = 0;
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    this->m_hMarshalEvent = CreateEventW(0, 0, 0, 0);
    this->m_hFlushEvent = CreateEventW(0, 0, 0, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    this->m_hFlushCompleteEvent = EventW;
    if ( this->m_pAsyncItemHandler && v2 && v5 && this->m_hMarshalEvent && this->m_hFlushEvent && EventW )
    {
      v5->link.bLink = 0;
      v5->link.fLink = 0;
      v4 = 0;
      v5->remove = 0;
      v5->event = this->m_hFlushEvent;
      v5->itemRoutine = (void (__fastcall *)(ASYNC_ITEM_STATUS, _ASYNC_ITEM *))CKsOutputPin::SynchronizeFlushRoutine;
      v5->context = this;
      v2->link.bLink = 0;
      v2->link.fLink = 0;
      v2->remove = 0;
      v2->event = this->m_hMarshalEvent;
      v2->itemRoutine = CKsOutputPin::MarshalRoutine;
      v2->context = this;
      CAsyncItemHandler::QueueAsyncItem(this->m_pAsyncItemHandler, v5);
      CAsyncItemHandler::QueueAsyncItem(this->m_pAsyncItemHandler, v2);
    }
    else
    {
      v4 = -2147024882;
      operator delete(v2, 0x30u);
      operator delete(v5, 0x30u);
      m_pAsyncItemHandler = this->m_pAsyncItemHandler;
      if ( m_pAsyncItemHandler )
        CAsyncItemHandler::`scalar deleting destructor'(m_pAsyncItemHandler, v10);
      m_hMarshalEvent = this->m_hMarshalEvent;
      this->m_pAsyncItemHandler = 0;
      if ( m_hMarshalEvent )
      {
        CloseHandle(m_hMarshalEvent);
        this->m_hMarshalEvent = 0;
      }
      m_hFlushEvent = this->m_hFlushEvent;
      if ( m_hFlushEvent )
      {
        CloseHandle(m_hFlushEvent);
        this->m_hFlushEvent = 0;
      }
      m_hFlushCompleteEvent = this->m_hFlushCompleteEvent;
      if ( m_hFlushCompleteEvent )
      {
        CloseHandle(m_hFlushCompleteEvent);
        this->m_hFlushCompleteEvent = 0;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013570  push    rbx
0x180013572  push    rbp
0x180013573  push    rsi
0x180013574  push    rdi
0x180013575  push    r14
0x180013577  push    r15
0x180013579  sub     rsp, 28h
0x18001357d  mov     rbx, rcx
0x180013580  mov     r15d, 30h ; '0'
0x180013586  mov     ecx, r15d; Size
0x180013589  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001358e  mov     ecx, r15d; Size
0x180013591  mov     rsi, rax
0x180013594  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013599  xor     ebp, ebp
0x18001359b  mov     ecx, 470h; Size
0x1800135a0  mov     edi, ebp
0x1800135a2  mov     [rsp+58h+arg_0], ebp
0x1800135a6  mov     r14, rax
0x1800135a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800135ae  test    rax, rax
0x1800135b1  jz      short loc_1800135C6
0x1800135b3  lea     rdx, [rsp+58h+arg_0]; unsigned int *
0x1800135b8  mov     rcx, rax; this
0x1800135bb  call    ??0CAsyncItemHandler@@QEAA@PEAK@Z; CAsyncItemHandler::CAsyncItemHandler(ulong *)
0x1800135c0  mov     edi, [rsp+58h+arg_0]
0x1800135c4  jmp     short loc_1800135C9
0x1800135c6  mov     rax, rbp
0x1800135c9  mov     [rbx+3D8h], rax
0x1800135d0  test    edi, edi
0x1800135d2  jz      short loc_180013614
0x1800135d4  test    rax, rax
0x1800135d7  jz      short loc_1800135E1
0x1800135d9  mov     rcx, rax; this
0x1800135dc  call    ??_GCAsyncItemHandler@@QEAAPEAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x1800135e1  mov     rdx, r15; unsigned __int64
0x1800135e4  mov     rcx, rsi; void *
0x1800135e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800135ec  mov     rdx, r15; unsigned __int64
0x1800135ef  mov     rcx, r14; void *
0x1800135f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800135f7  mov     [rbx+3D8h], rbp
0x1800135fe  test    edi, edi
0x180013600  jle     loc_1800137A0
0x180013606  movzx   edi, di
0x180013609  or      edi, 80070000h
0x18001360f  jmp     loc_1800137A0
0x180013614  xor     r9d, r9d; lpName
0x180013617  xor     r8d, r8d; bInitialState
0x18001361a  xor     edx, edx; bManualReset
0x18001361c  xor     ecx, ecx; lpEventAttributes
0x18001361e  call    cs:__imp_CreateEventW
0x180013625  nop     dword ptr [rax+rax+00h]
0x18001362a  xor     r9d, r9d; lpName
0x18001362d  xor     r8d, r8d; bInitialState
0x180013630  xor     edx, edx; bManualReset
0x180013632  mov     [rbx+3B0h], rax
0x180013639  xor     ecx, ecx; lpEventAttributes
0x18001363b  call    cs:__imp_CreateEventW
0x180013642  nop     dword ptr [rax+rax+00h]
0x180013647  xor     r9d, r9d; lpName
0x18001364a  xor     r8d, r8d; bInitialState
0x18001364d  xor     edx, edx; bManualReset
0x18001364f  mov     [rbx+3B8h], rax
0x180013656  xor     ecx, ecx; lpEventAttributes
0x180013658  call    cs:__imp_CreateEventW
0x18001365f  nop     dword ptr [rax+rax+00h]
0x180013664  mov     [rbx+3C0h], rax
0x18001366b  cmp     [rbx+3D8h], rbp
0x180013672  jz      loc_180013710
0x180013678  test    rsi, rsi
0x18001367b  jz      loc_180013710
0x180013681  test    r14, r14
0x180013684  jz      loc_180013710
0x18001368a  cmp     [rbx+3B0h], rbp
0x180013691  jz      short loc_180013710
0x180013693  cmp     [rbx+3B8h], rbp
0x18001369a  jz      short loc_180013710
0x18001369c  test    rax, rax
0x18001369f  jz      short loc_180013710
0x1800136a1  mov     [r14+8], rbp
0x1800136a5  mov     rdx, r14; struct _ASYNC_ITEM *
0x1800136a8  mov     [r14], rbp
0x1800136ab  mov     edi, ebp
0x1800136ad  mov     [r14+10h], bpl
0x1800136b1  mov     rax, [rbx+3B8h]
0x1800136b8  mov     [r14+18h], rax
0x1800136bc  lea     rax, ?SynchronizeFlushRoutine@CKsOutputPin@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin::SynchronizeFlushRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1800136c3  mov     [r14+20h], rax
0x1800136c7  mov     [r14+28h], rbx
0x1800136cb  mov     [rsi+8], rbp
0x1800136cf  mov     [rsi], rbp
0x1800136d2  mov     [rsi+10h], bpl
0x1800136d6  mov     rax, [rbx+3B0h]
0x1800136dd  mov     [rsi+18h], rax
0x1800136e1  lea     rax, ?MarshalRoutine@CKsOutputPin@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin::MarshalRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1800136e8  mov     [rsi+20h], rax
0x1800136ec  mov     [rsi+28h], rbx
0x1800136f0  mov     rcx, [rbx+3D8h]; this
0x1800136f7  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1800136fc  mov     rcx, [rbx+3D8h]; this
0x180013703  mov     rdx, rsi; struct _ASYNC_ITEM *
0x180013706  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18001370b  jmp     loc_1800137A0
0x180013710  mov     rdx, r15; unsigned __int64
0x180013713  mov     rcx, rsi; void *
0x180013716  mov     edi, 8007000Eh
0x18001371b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013720  mov     rdx, r15; unsigned __int64
0x180013723  mov     rcx, r14; void *
0x180013726  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001372b  mov     rcx, [rbx+3D8h]; this
0x180013732  test    rcx, rcx
0x180013735  jz      short loc_18001373C
0x180013737  call    ??_GCAsyncItemHandler@@QEAAPEAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x18001373c  mov     rcx, [rbx+3B0h]; hObject
0x180013743  mov     [rbx+3D8h], rbp
0x18001374a  test    rcx, rcx
0x18001374d  jz      short loc_180013762
0x18001374f  call    cs:__imp_CloseHandle
0x180013756  nop     dword ptr [rax+rax+00h]
0x18001375b  mov     [rbx+3B0h], rbp
0x180013762  mov     rcx, [rbx+3B8h]; hObject
0x180013769  test    rcx, rcx
0x18001376c  jz      short loc_180013781
0x18001376e  call    cs:__imp_CloseHandle
0x180013775  nop     dword ptr [rax+rax+00h]
0x18001377a  mov     [rbx+3B8h], rbp
0x180013781  mov     rcx, [rbx+3C0h]; hObject
0x180013788  test    rcx, rcx
0x18001378b  jz      short loc_1800137A0
0x18001378d  call    cs:__imp_CloseHandle
0x180013794  nop     dword ptr [rax+rax+00h]
0x180013799  mov     [rbx+3C0h], rbp
0x1800137a0  mov     eax, edi
0x1800137a2  add     rsp, 28h
0x1800137a6  pop     r15
0x1800137a8  pop     r14
0x1800137aa  pop     rdi
0x1800137ab  pop     rsi
0x1800137ac  pop     rbp
0x1800137ad  pop     rbx
0x1800137ae  retn
```
