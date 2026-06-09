# DllEntryPoint

- ea: `0x1800032a4`
- end: `0x1800032d1`
- name: `DllEntryPoint`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d68`

## callees

- `0x180001484`
- `0x1800032a4`
- `0x1800032d8`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  if ( a2 == 1 )
    _security_init_cookie();
  return DllEntryPoint(a1, a2);
}

```

## disassembly

```asm
0x1800032a4  mov     [rsp+arg_0], rbx
0x1800032a9  push    rdi
0x1800032aa  sub     rsp, 20h
0x1800032ae  mov     ebx, edx
0x1800032b0  mov     rdi, rcx
0x1800032b3  cmp     edx, 1
0x1800032b6  jnz     short loc_1800032BD
0x1800032b8  call    __security_init_cookie
0x1800032bd  mov     edx, ebx
0x1800032bf  mov     rcx, rdi
0x1800032c2  mov     rbx, [rsp+28h+arg_0]
0x1800032c7  add     rsp, 20h
0x1800032cb  pop     rdi
0x1800032cc  jmp     _DllEntryPoint
```
