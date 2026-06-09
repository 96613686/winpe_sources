# _std::_Uninit_move_Dock___Dock___std::allocator_Dock__Dock__::_1_::catch$0

- ea: `0x18001d18e`
- end: `0x18001d1c1`
- name: `_std::_Uninit_move_Dock___Dock___std::allocator_Dock__Dock__::_1_::catch$0`
- size: `51`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800020bd`
- `0x180010a94`
- `0x18001d18e`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_Dock___Dock___std::allocator_Dock__Dock__::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 2936 )
    std::_Dest_val<std::allocator<Dock>,Dock>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18001d18e  mov     [rsp+arg_8], rdx
0x18001d193  push    rbx
0x18001d194  push    rbp
0x18001d195  sub     rsp, 28h
0x18001d199  mov     rbp, rdx
0x18001d19c  mov     rbx, [rbp+48h]
0x18001d1a0  jmp     short loc_18001D1B1
0x18001d1a2  mov     rdx, rbx
0x18001d1a5  call    ??$_Dest_val@V?$allocator@VDock@@@std@@VDock@@@std@@YAXAEAV?$allocator@VDock@@@0@PEAVDock@@@Z; std::_Dest_val<std::allocator<Dock>,Dock>(std::allocator<Dock> &,Dock *)
0x18001d1aa  add     rbx, 0B78h
0x18001d1b1  cmp     rbx, [rbp+40h]
0x18001d1b5  jnz     short loc_18001D1A2
0x18001d1b7  xor     edx, edx; pThrowInfo
0x18001d1b9  xor     ecx, ecx; pExceptionObject
0x18001d1bb  call    _CxxThrowException_0
```
