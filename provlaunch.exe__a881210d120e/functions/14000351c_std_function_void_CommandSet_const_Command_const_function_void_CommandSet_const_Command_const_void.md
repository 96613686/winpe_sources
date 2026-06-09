# std::function<void (CommandSet const &,Command const &)>::~function<void (CommandSet const &,Command const &)>(void)

- ea: `0x14000351c`
- end: `0x14000354e`
- name: `??1?$function@$$A6AXAEBUCommandSet@@AEBUCommand@@@Z@std@@QEAA@XZ`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a9bb`
- `0x14000aa99`
- `0x14000aaab`

## callees

- `0x14000351c`
- `0x14000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::function<void (CommandSet const &,Command const &)>::~function<void (CommandSet const &,Command const &)>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 24);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000351c  push    rbx
0x14000351e  sub     rsp, 20h
0x140003522  mov     rbx, rcx
0x140003525  mov     rcx, [rcx+18h]
0x140003529  test    rcx, rcx
0x14000352c  jz      short loc_140003548
0x14000352e  mov     rax, [rcx]
0x140003531  cmp     rcx, rbx
0x140003534  setnz   dl
0x140003537  mov     rax, [rax+20h]
0x14000353b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003540  mov     qword ptr [rbx+18h], 0
0x140003548  add     rsp, 20h
0x14000354c  pop     rbx
0x14000354d  retn
```
