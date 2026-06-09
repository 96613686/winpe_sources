# _dynamic_atexit_destructor_for__DSLoggerSingleton__

- ea: `0x18001b920`
- end: `0x18001b978`
- name: `_dynamic_atexit_destructor_for__DSLoggerSingleton__`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bf58`
- `0x18001b920`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b947`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b947`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b967`

## pseudocode

```c
void dynamic_atexit_destructor_for__DSLoggerSingleton__()
{
  WINBOOL v0; // [rsp+30h] [rbp+8h] BYREF
  DSLogger *v1; // [rsp+38h] [rbp+10h] BYREF

  v0 = 0;
  v1 = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, &v0, (LPVOID *)&v1);
  if ( v1 )
    DSLogger::~DSLogger(v1);
  else
    InitOnceComplete(&DSLoggerSingleton, 0, 0);
}

```

## disassembly

```asm
0x18001b920  mov     rax, rsp
0x18001b923  sub     rsp, 28h
0x18001b927  lea     r9, [rax+10h]; lpContext
0x18001b92b  mov     dword ptr [rax+8], 0
0x18001b932  lea     r8, [rax+8]; fPending
0x18001b936  mov     qword ptr [rax+10h], 0
0x18001b93e  xor     edx, edx; dwFlags
0x18001b940  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x18001b947  call    cs:__imp_InitOnceBeginInitialize
0x18001b94d  mov     rcx, [rsp+28h+arg_8]; this
0x18001b952  test    rcx, rcx
0x18001b955  jnz     short loc_18001B96E
0x18001b957  xor     r8d, r8d
0x18001b95a  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>> DSLoggerSingleton
0x18001b961  xor     edx, edx
0x18001b963  add     rsp, 28h
0x18001b967  jmp     cs:__imp_InitOnceComplete
0x18001b96e  call    ??1DSLogger@@QEAA@XZ; DSLogger::~DSLogger(void)
0x18001b973  add     rsp, 28h
0x18001b977  retn
```
