# std::unique_ptr<uus::Session,std::default_delete<uus::Session>>::~unique_ptr<uus::Session,std::default_delete<uus::Session>>(void)

- ea: `0x180003590`
- end: `0x1800035a9`
- name: `??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003448`
- `0x180003b68`
- `0x18000a8ec`

## callees

- `0x180003590`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180003590  mov     rcx, [rcx]
0x180003593  test    rcx, rcx
0x180003596  jz      short locret_1800035A8
0x180003598  mov     rax, [rcx]
0x18000359b  mov     edx, 1
0x1800035a0  mov     rax, [rax]
0x1800035a3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a8  retn
```
