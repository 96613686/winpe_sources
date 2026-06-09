# WEBSOCKET_IO_MANAGER::`vector deleting destructor'(uint)

- ea: `0x180003300`
- end: `0x180003352`
- name: `??_EWEBSOCKET_IO_MANAGER@@UEAAPEAXI@Z`
- size: `82`
- prototype: `void *__fastcall(WEBSOCKET_IO_MANAGER *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003300`
- `0x180003fcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000332b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000332b`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall WEBSOCKET_IO_MANAGER::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&WEBSOCKET_IO_MANAGER::`vftable';
  QUEUE::Clear(this + 1);
  DeleteCriticalSection(this + 1);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003300  mov     [rsp+arg_0], rbx
0x180003305  mov     [rsp+arg_8], rsi
0x18000330a  push    rdi
0x18000330b  sub     rsp, 20h
0x18000330f  lea     rax, ??_7WEBSOCKET_IO_MANAGER@@6B@; const WEBSOCKET_IO_MANAGER::`vftable'
0x180003316  mov     rsi, rcx
0x180003319  mov     [rcx], rax
0x18000331c  mov     edi, edx
0x18000331e  add     rcx, 28h ; '('; this
0x180003322  call    ?Clear@QUEUE@@QEAAXXZ; QUEUE::Clear(void)
0x180003327  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000332b  call    cs:__imp_DeleteCriticalSection
0x180003331  test    dil, 1
0x180003335  jz      short loc_18000333F
0x180003337  mov     rcx, rsi; Block
0x18000333a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000333f  mov     rbx, [rsp+28h+arg_0]
0x180003344  mov     rax, rsi
0x180003347  mov     rsi, [rsp+28h+arg_8]
0x18000334c  add     rsp, 20h
0x180003350  pop     rdi
0x180003351  retn
```
