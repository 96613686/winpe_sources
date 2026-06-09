# std::default_delete<CPortClient>::operator()(CPortClient *)

- ea: `0x18001518c`
- end: `0x1800151b0`
- name: `??R?$default_delete@VCPortClient@@@std@@QEBAXPEAVCPortClient@@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b864`
- `0x18000b880`

## callees

- `0x18001518c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall std::default_delete<CPortClient>::operator()(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 result; // rax

  if ( a2 )
    return (**a2)(a2, 1);
  return result;
}

```

## disassembly

```asm
0x18001518c  sub     rsp, 28h
0x180015190  mov     r8, rdx
0x180015193  test    rdx, rdx
0x180015196  jz      short loc_1800151AB
0x180015198  mov     rax, [rdx]
0x18001519b  mov     rcx, r8
0x18001519e  mov     edx, 1
0x1800151a3  mov     rax, [rax]
0x1800151a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ab  add     rsp, 28h
0x1800151af  retn
```
