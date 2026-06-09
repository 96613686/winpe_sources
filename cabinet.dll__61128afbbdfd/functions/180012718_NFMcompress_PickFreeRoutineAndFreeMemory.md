# NFMcompress_PickFreeRoutineAndFreeMemory

- ea: `0x180012718`
- end: `0x18001274b`
- name: `NFMcompress_PickFreeRoutineAndFreeMemory`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800122c0`
- `0x180012630`

## callees

- `0x180012718`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall NFMcompress_PickFreeRoutineAndFreeMemory(
        __int64 (__fastcall *a1)(__int64),
        __int64 (__fastcall *a2)(__int64, __int64),
        __int64 a3,
        __int64 a4)
{
  __int64 result; // rax

  result = (__int64)a2;
  if ( a1 )
    return a1(a4);
  if ( a2 )
    return a2(a3, a4);
  return result;
}

```

## disassembly

```asm
0x180012718  sub     rsp, 28h
0x18001271c  mov     rax, rdx
0x18001271f  mov     rdx, rcx
0x180012722  test    rcx, rcx
0x180012725  jz      short loc_180012737
0x180012727  mov     rcx, r9
0x18001272a  mov     rax, rdx
0x18001272d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012732  add     rsp, 28h
0x180012736  retn
0x180012737  test    rax, rax
0x18001273a  jz      short loc_180012732
0x18001273c  mov     rdx, r9
0x18001273f  mov     rcx, r8
0x180012742  add     rsp, 28h
0x180012746  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
