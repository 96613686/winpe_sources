# CKsOutputPin2::InitializeAsyncThread(void)

- ea: `0x18002fd70`
- end: `0x180030043`
- name: `?InitializeAsyncThread@CKsOutputPin2@@UEAAJXZ`
- size: `723`
- prototype: `__int64 __fastcall(CKsOutputPin2 *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x18000df50`
- `0x1800137b8`
- `0x18001e720`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18002fd70`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18002fe1d`
- `KERNEL32!CreateEventW` at `0x18002fe3a`
- `KERNEL32!CreateEventW` at `0x18002fe57`
- `KERNEL32!CreateEventW` at `0x18002fe74`
- `KERNEL32!CreateEventW` at `0x18002fe1d`
- `KERNEL32!CreateEventW` at `0x18002fe3a`
- `KERNEL32!CreateEventW` at `0x18002fe57`
- `KERNEL32!CreateEventW` at `0x18002fe74`
- `KERNEL32!CloseHandle` at `0x18002ffb9`
- `KERNEL32!CloseHandle` at `0x18002ffd8`
- `KERNEL32!CloseHandle` at `0x18002fff7`
- `KERNEL32!CloseHandle` at `0x180030016`
- `KERNEL32!CloseHandle` at `0x18002ffb9`
- `KERNEL32!CloseHandle` at `0x18002ffd8`
- `KERNEL32!CloseHandle` at `0x18002fff7`
- `KERNEL32!CloseHandle` at `0x180030016`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::InitializeAsyncThread(CKsOutputPin2 *this)
{
  signed int v2; // edi
  CAsyncItemHandler *v3; // rax
  CAsyncItemHandler *v4; // rax
  struct _ASYNC_ITEM *v6; // rdi
  struct _ASYNC_ITEM *v7; // rsi
  struct _ASYNC_ITEM *v8; // r14
  HANDLE EventW; // rax
  unsigned int v10; // ebp
  CAsyncItemHandler *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  unsigned int v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = 0;
  v2 = 0;
  v3 = (CAsyncItemHandler *)operator new(0x470u);
  if ( v3 )
  {
    v4 = CAsyncItemHandler::CAsyncItemHandler(v3, &v16);
    v2 = v16;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 123) = v4;
  if ( v2 )
  {
    if ( v4 )
      CAsyncItemHandler::`scalar deleting destructor'(v4);
    *((_QWORD *)this + 123) = 0;
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
    return (unsigned int)v2;
  }
  else
  {
    v6 = (struct _ASYNC_ITEM *)operator new(0x30u);
    v7 = (struct _ASYNC_ITEM *)operator new(0x30u);
    v8 = (struct _ASYNC_ITEM *)operator new(0x30u);
    *((_QWORD *)this + 118) = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 139) = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 119) = CreateEventW(0, 0, 0, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 120) = EventW;
    if ( *((_QWORD *)this + 123)
      && v6
      && v7
      && *((_QWORD *)this + 118)
      && *((_QWORD *)this + 139)
      && *((_QWORD *)this + 119)
      && EventW )
    {
      v7->link.bLink = 0;
      v7->link.fLink = 0;
      v10 = 0;
      v7->remove = 0;
      v7->event = (void *)*((_QWORD *)this + 119);
      v7->itemRoutine = (void (__fastcall *)(ASYNC_ITEM_STATUS, _ASYNC_ITEM *))CKsOutputPin::SynchronizeFlushRoutine;
      v7->context = this;
      v8->link.bLink = 0;
      v8->link.fLink = 0;
      v8->remove = 0;
      v8->event = (void *)*((_QWORD *)this + 139);
      v8->itemRoutine = CKsOutputPin2::DeviceQueueItem;
      v8->context = this;
      v6->link.bLink = 0;
      v6->link.fLink = 0;
      v6->remove = 0;
      v6->event = (void *)*((_QWORD *)this + 118);
      v6->itemRoutine = CKsOutputPin::MarshalRoutine;
      v6->context = this;
      CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)this + 123), v7);
      CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)this + 123), v6);
      CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)this + 123), v8);
    }
    else
    {
      v10 = -2147024882;
      operator delete(v6);
      operator delete(v7);
      v11 = (CAsyncItemHandler *)*((_QWORD *)this + 123);
      if ( v11 )
        CAsyncItemHandler::`scalar deleting destructor'(v11);
      v12 = (void *)*((_QWORD *)this + 118);
      *((_QWORD *)this + 123) = 0;
      if ( v12 )
      {
        CloseHandle(v12);
        *((_QWORD *)this + 118) = 0;
      }
      v13 = (void *)*((_QWORD *)this + 139);
      if ( v13 )
      {
        CloseHandle(v13);
        *((_QWORD *)this + 139) = 0;
      }
      v14 = (void *)*((_QWORD *)this + 119);
      if ( v14 )
      {
        CloseHandle(v14);
        *((_QWORD *)this + 119) = 0;
      }
      v15 = (void *)*((_QWORD *)this + 120);
      if ( v15 )
      {
        CloseHandle(v15);
        *((_QWORD *)this + 120) = 0;
      }
    }
    return v10;
  }
}

```

## disassembly

```asm
0x18002fd70  mov     [rsp+arg_8], rbx
0x18002fd75  mov     [rsp+arg_10], rbp
0x18002fd7a  push    rsi
0x18002fd7b  push    rdi
0x18002fd7c  push    r12
0x18002fd7e  push    r14
0x18002fd80  push    r15
0x18002fd82  sub     rsp, 20h
0x18002fd86  mov     rbx, rcx
0x18002fd89  xor     r15d, r15d
0x18002fd8c  mov     ecx, 470h; Size
0x18002fd91  mov     [rsp+48h+arg_0], r15d
0x18002fd96  mov     edi, r15d
0x18002fd99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fd9e  test    rax, rax
0x18002fda1  jz      short loc_18002FDB6
0x18002fda3  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x18002fda8  mov     rcx, rax; this
0x18002fdab  call    ??0CAsyncItemHandler@@QEAA@PEAK@Z; CAsyncItemHandler::CAsyncItemHandler(ulong *)
0x18002fdb0  mov     edi, [rsp+48h+arg_0]
0x18002fdb4  jmp     short loc_18002FDB9
0x18002fdb6  mov     rax, r15
0x18002fdb9  mov     [rbx+3D8h], rax
0x18002fdc0  test    edi, edi
0x18002fdc2  jz      short loc_18002FDEC
0x18002fdc4  test    rax, rax
0x18002fdc7  jz      short loc_18002FDD1
0x18002fdc9  mov     rcx, rax; this
0x18002fdcc  call    ??_GCAsyncItemHandler@@QEAAPEAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x18002fdd1  mov     [rbx+3D8h], r15
0x18002fdd8  test    edi, edi
0x18002fdda  jle     short loc_18002FDE5
0x18002fddc  movzx   edi, di
0x18002fddf  or      edi, 80070000h
0x18002fde5  mov     eax, edi
0x18002fde7  jmp     loc_18003002B
0x18002fdec  mov     r12d, 30h ; '0'
0x18002fdf2  mov     ecx, r12d; Size
0x18002fdf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fdfa  mov     ecx, r12d; Size
0x18002fdfd  mov     rdi, rax
0x18002fe00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fe05  mov     ecx, r12d; Size
0x18002fe08  mov     rsi, rax
0x18002fe0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fe10  xor     r9d, r9d; lpName
0x18002fe13  xor     r8d, r8d; bInitialState
0x18002fe16  xor     edx, edx; bManualReset
0x18002fe18  xor     ecx, ecx; lpEventAttributes
0x18002fe1a  mov     r14, rax
0x18002fe1d  call    cs:__imp_CreateEventW
0x18002fe24  nop     dword ptr [rax+rax+00h]
0x18002fe29  xor     r9d, r9d; lpName
0x18002fe2c  xor     r8d, r8d; bInitialState
0x18002fe2f  xor     edx, edx; bManualReset
0x18002fe31  mov     [rbx+3B0h], rax
0x18002fe38  xor     ecx, ecx; lpEventAttributes
0x18002fe3a  call    cs:__imp_CreateEventW
0x18002fe41  nop     dword ptr [rax+rax+00h]
0x18002fe46  xor     r9d, r9d; lpName
0x18002fe49  xor     r8d, r8d; bInitialState
0x18002fe4c  xor     edx, edx; bManualReset
0x18002fe4e  mov     [rbx+458h], rax
0x18002fe55  xor     ecx, ecx; lpEventAttributes
0x18002fe57  call    cs:__imp_CreateEventW
0x18002fe5e  nop     dword ptr [rax+rax+00h]
0x18002fe63  xor     r9d, r9d; lpName
0x18002fe66  xor     r8d, r8d; bInitialState
0x18002fe69  xor     edx, edx; bManualReset
0x18002fe6b  mov     [rbx+3B8h], rax
0x18002fe72  xor     ecx, ecx; lpEventAttributes
0x18002fe74  call    cs:__imp_CreateEventW
0x18002fe7b  nop     dword ptr [rax+rax+00h]
0x18002fe80  mov     [rbx+3C0h], rax
0x18002fe87  cmp     [rbx+3D8h], r15
0x18002fe8e  jz      loc_18002FF7A
0x18002fe94  test    rdi, rdi
0x18002fe97  jz      loc_18002FF7A
0x18002fe9d  test    rsi, rsi
0x18002fea0  jz      loc_18002FF7A
0x18002fea6  cmp     [rbx+3B0h], r15
0x18002fead  jz      loc_18002FF7A
0x18002feb3  cmp     [rbx+458h], r15
0x18002feba  jz      loc_18002FF7A
0x18002fec0  cmp     [rbx+3B8h], r15
0x18002fec7  jz      loc_18002FF7A
0x18002fecd  test    rax, rax
0x18002fed0  jz      loc_18002FF7A
0x18002fed6  mov     [rsi+8], r15
0x18002feda  mov     rdx, rsi; struct _ASYNC_ITEM *
0x18002fedd  mov     [rsi], r15
0x18002fee0  mov     ebp, r15d
0x18002fee3  mov     [rsi+10h], r15b
0x18002fee7  mov     rax, [rbx+3B8h]
0x18002feee  mov     [rsi+18h], rax
0x18002fef2  lea     rax, ?SynchronizeFlushRoutine@CKsOutputPin@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin::SynchronizeFlushRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x18002fef9  mov     [rsi+20h], rax
0x18002fefd  mov     [rsi+28h], rbx
0x18002ff01  mov     [r14+8], r15
0x18002ff05  mov     [r14], r15
0x18002ff08  mov     [r14+10h], r15b
0x18002ff0c  mov     rax, [rbx+458h]
0x18002ff13  mov     [r14+18h], rax
0x18002ff17  lea     rax, ?DeviceQueueItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin2::DeviceQueueItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x18002ff1e  mov     [r14+20h], rax
0x18002ff22  mov     [r14+28h], rbx
0x18002ff26  mov     [rdi+8], r15
0x18002ff2a  mov     [rdi], r15
0x18002ff2d  mov     [rdi+10h], r15b
0x18002ff31  mov     rax, [rbx+3B0h]
0x18002ff38  mov     [rdi+18h], rax
0x18002ff3c  lea     rax, ?MarshalRoutine@CKsOutputPin@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin::MarshalRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x18002ff43  mov     [rdi+20h], rax
0x18002ff47  mov     [rdi+28h], rbx
0x18002ff4b  mov     rcx, [rbx+3D8h]; this
0x18002ff52  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18002ff57  mov     rcx, [rbx+3D8h]; this
0x18002ff5e  mov     rdx, rdi; struct _ASYNC_ITEM *
0x18002ff61  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18002ff66  mov     rcx, [rbx+3D8h]; this
0x18002ff6d  mov     rdx, r14; struct _ASYNC_ITEM *
0x18002ff70  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18002ff75  jmp     loc_180030029
0x18002ff7a  mov     rdx, r12; unsigned __int64
0x18002ff7d  mov     rcx, rdi; void *
0x18002ff80  mov     ebp, 8007000Eh
0x18002ff85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ff8a  mov     rdx, r12; unsigned __int64
0x18002ff8d  mov     rcx, rsi; void *
0x18002ff90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ff95  mov     rcx, [rbx+3D8h]; this
0x18002ff9c  test    rcx, rcx
0x18002ff9f  jz      short loc_18002FFA6
0x18002ffa1  call    ??_GCAsyncItemHandler@@QEAAPEAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x18002ffa6  mov     rcx, [rbx+3B0h]; hObject
0x18002ffad  mov     [rbx+3D8h], r15
0x18002ffb4  test    rcx, rcx
0x18002ffb7  jz      short loc_18002FFCC
0x18002ffb9  call    cs:__imp_CloseHandle
0x18002ffc0  nop     dword ptr [rax+rax+00h]
0x18002ffc5  mov     [rbx+3B0h], r15
0x18002ffcc  mov     rcx, [rbx+458h]; hObject
0x18002ffd3  test    rcx, rcx
0x18002ffd6  jz      short loc_18002FFEB
0x18002ffd8  call    cs:__imp_CloseHandle
0x18002ffdf  nop     dword ptr [rax+rax+00h]
0x18002ffe4  mov     [rbx+458h], r15
0x18002ffeb  mov     rcx, [rbx+3B8h]; hObject
0x18002fff2  test    rcx, rcx
0x18002fff5  jz      short loc_18003000A
0x18002fff7  call    cs:__imp_CloseHandle
0x18002fffe  nop     dword ptr [rax+rax+00h]
0x180030003  mov     [rbx+3B8h], r15
0x18003000a  mov     rcx, [rbx+3C0h]; hObject
0x180030011  test    rcx, rcx
0x180030014  jz      short loc_180030029
0x180030016  call    cs:__imp_CloseHandle
0x18003001d  nop     dword ptr [rax+rax+00h]
0x180030022  mov     [rbx+3C0h], r15
0x180030029  mov     eax, ebp
0x18003002b  mov     rbx, [rsp+48h+arg_8]
0x180030030  mov     rbp, [rsp+48h+arg_10]
0x180030035  add     rsp, 20h
0x180030039  pop     r15
0x18003003b  pop     r14
0x18003003d  pop     r12
0x18003003f  pop     rdi
0x180030040  pop     rsi
0x180030041  retn
```
