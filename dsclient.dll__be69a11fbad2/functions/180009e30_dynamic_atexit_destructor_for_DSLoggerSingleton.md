# _dynamic_atexit_destructor_for__DSLoggerSingleton__

- ea: `0x180009e30`
- end: `0x180009e9b`
- name: `_dynamic_atexit_destructor_for__DSLoggerSingleton__`
- size: `107`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002020`
- `0x180009e30`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009e7e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e58`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e58`

## pseudocode

```c
int dynamic_atexit_destructor_for__DSLoggerSingleton__()
{
  int result; // eax
  _DWORD *v1; // rbx
  BOOL fPending; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp+10h] BYREF

  fPending = 0;
  Context = 0;
  result = InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
  v1 = Context;
  if ( !Context )
    return InitOnceComplete(&DSLoggerSingleton, 0, 0);
  if ( *(_DWORD *)Context )
  {
    result = McGenEventUnregister_EventUnregister();
    *v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009e30  mov     [rsp+arg_10], rbx
0x180009e35  push    rdi
0x180009e36  sub     rsp, 20h
0x180009e3a  xor     edi, edi
0x180009e3c  lea     r9, [rsp+28h+Context]; lpContext
0x180009e41  lea     r8, [rsp+28h+fPending]; fPending
0x180009e46  mov     [rsp+28h+fPending], edi
0x180009e4a  xor     edx, edx; dwFlags
0x180009e4c  mov     [rsp+28h+Context], rdi
0x180009e51  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180009e58  call    cs:__imp_InitOnceBeginInitialize
0x180009e5e  mov     rbx, [rsp+28h+Context]
0x180009e63  test    rbx, rbx
0x180009e66  jnz     short loc_180009E85
0x180009e68  xor     r8d, r8d
0x180009e6b  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>> DSLoggerSingleton
0x180009e72  xor     edx, edx
0x180009e74  mov     rbx, [rsp+28h+arg_10]
0x180009e79  add     rsp, 20h
0x180009e7d  pop     rdi
0x180009e7e  jmp     cs:__imp_InitOnceComplete
0x180009e85  cmp     [rbx], edi
0x180009e87  jz      short loc_180009E90
0x180009e89  call    McGenEventUnregister_EventUnregister
0x180009e8e  mov     [rbx], edi
0x180009e90  mov     rbx, [rsp+28h+arg_10]
0x180009e95  add     rsp, 20h
0x180009e99  pop     rdi
0x180009e9a  retn
```
