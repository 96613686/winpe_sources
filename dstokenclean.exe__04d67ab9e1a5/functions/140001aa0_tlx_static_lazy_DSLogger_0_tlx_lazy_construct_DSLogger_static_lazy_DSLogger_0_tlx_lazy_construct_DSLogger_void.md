# tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>::~static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>(void)

- ea: `0x140001aa0`
- end: `0x140001b03`
- name: `??1?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@QEAA@XZ`
- size: `99`
- prototype: `int __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400020f0`

## callees

- `0x140001aa0`
- `0x140001dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140001ac8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140001ac8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140001ae0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140001ae0`

## pseudocode

```c
int __fastcall tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>::~static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>(
        LPINIT_ONCE lpInitOnce)
{
  int result; // eax
  _DWORD *v3; // rbx
  BOOL v4; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v5 = 0;
  result = InitOnceBeginInitialize(lpInitOnce, 0, &v4, (LPVOID *)&v5);
  v3 = v5;
  if ( !v5 )
    return InitOnceComplete(lpInitOnce, 0, 0);
  if ( *v5 )
  {
    result = McGenEventUnregister_EventUnregister();
    *v3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001aa0  mov     rax, rsp
0x140001aa3  mov     [rax+18h], rbx
0x140001aa7  push    rdi
0x140001aa8  sub     rsp, 20h
0x140001aac  lea     r9, [rax+10h]; lpContext
0x140001ab0  mov     dword ptr [rax+8], 0
0x140001ab7  lea     r8, [rax+8]; fPending
0x140001abb  mov     qword ptr [rax+10h], 0
0x140001ac3  xor     edx, edx; dwFlags
0x140001ac5  mov     rdi, rcx
0x140001ac8  call    cs:__imp_InitOnceBeginInitialize
0x140001ace  mov     rbx, [rsp+28h+arg_8]
0x140001ad3  test    rbx, rbx
0x140001ad6  jnz     short loc_140001AE8
0x140001ad8  xor     r8d, r8d; lpContext
0x140001adb  xor     edx, edx; dwFlags
0x140001add  mov     rcx, rdi; lpInitOnce
0x140001ae0  call    cs:__imp_InitOnceComplete
0x140001ae6  jmp     short loc_140001AF8
0x140001ae8  cmp     dword ptr [rbx], 0
0x140001aeb  jz      short loc_140001AF8
0x140001aed  call    McGenEventUnregister_EventUnregister
0x140001af2  mov     dword ptr [rbx], 0
0x140001af8  mov     rbx, [rsp+28h+arg_10]
0x140001afd  add     rsp, 20h
0x140001b01  pop     rdi
0x140001b02  retn
```
