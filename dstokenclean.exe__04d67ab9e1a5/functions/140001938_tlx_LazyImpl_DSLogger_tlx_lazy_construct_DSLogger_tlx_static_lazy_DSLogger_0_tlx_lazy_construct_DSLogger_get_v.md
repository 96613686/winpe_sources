# tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)

- ea: `0x140001938`
- end: `0x1400019af`
- name: `?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ`
- size: `119`
- prototype: `int *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400019b8`

## callees

- `0x140001938`
- `0x140001d98`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140001964`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140001964`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400019a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400019a0`

## pseudocode

```c
int *__fastcall tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
        __int64 a1)
{
  int *v1; // rbx
  BOOL v3; // [rsp+30h] [rbp+8h] BYREF
  int v4; // [rsp+34h] [rbp+Ch]
  int *v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = HIDWORD(a1);
  v3 = 0;
  v5 = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, &v3, (LPVOID *)&v5);
  v1 = v5;
  if ( !v5 )
  {
    dword_140005710 = McGenEventRegister_EventRegister() == 0;
    v1 = &dword_140005710;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_140005710);
  }
  return v1;
}

```

## disassembly

```asm
0x140001938  mov     rax, rsp
0x14000193b  mov     [rax+8], rcx
0x14000193f  push    rbx
0x140001940  sub     rsp, 20h
0x140001944  lea     r9, [rax+10h]; lpContext
0x140001948  mov     dword ptr [rax+8], 0
0x14000194f  lea     r8, [rax+8]; fPending
0x140001953  mov     qword ptr [rax+10h], 0
0x14000195b  xor     edx, edx; dwFlags
0x14000195d  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x140001964  call    cs:__imp_InitOnceBeginInitialize
0x14000196a  mov     rbx, [rsp+28h+arg_8]
0x14000196f  test    rbx, rbx
0x140001972  jnz     short loc_1400019A6
0x140001974  mov     cs:dword_140005710, ebx
0x14000197a  call    McGenEventRegister_EventRegister
0x14000197f  test    eax, eax
0x140001981  jnz     short loc_14000198D
0x140001983  mov     cs:dword_140005710, 1
0x14000198d  lea     rbx, dword_140005710
0x140001994  xor     edx, edx; dwFlags
0x140001996  mov     r8, rbx; lpContext
0x140001999  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1400019a0  call    cs:__imp_InitOnceComplete
0x1400019a6  mov     rax, rbx
0x1400019a9  add     rsp, 20h
0x1400019ad  pop     rbx
0x1400019ae  retn
```
