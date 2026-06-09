# NFMcompress_PickAllocRoutineAndAllocateMemory

- ea: `0x180012548`
- end: `0x18001256f`
- name: `NFMcompress_PickAllocRoutineAndAllocateMemory`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012328`
- `0x180012414`

## callees

- `0x180012548`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall NFMcompress_PickAllocRoutineAndAllocateMemory(
        __int64 (__fastcall *a1)(_QWORD),
        __int64 (__fastcall *a2)(__int64, _QWORD),
        __int64 a3,
        unsigned int a4)
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
0x180012548  mov     rax, rdx
0x18001254b  mov     rdx, rcx
0x18001254e  test    rcx, rcx
0x180012551  jnz     short loc_180012563
0x180012553  test    rax, rax
0x180012556  jz      short locret_18001256E
0x180012558  mov     edx, r9d
0x18001255b  mov     rcx, r8
0x18001255e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180012563  mov     ecx, r9d
0x180012566  mov     rax, rdx
0x180012569  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001256e  retn
```
