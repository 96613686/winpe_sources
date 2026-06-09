# std::unique_ptr<uus::Session,std::default_delete<uus::Session>>::~unique_ptr<uus::Session,std::default_delete<uus::Session>>(void)

- ea: `0x180008e50`
- end: `0x180008e71`
- name: `??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dac3`

## callees

- `0x180008e50`
- `0x18000e010`

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
0x180008e50  sub     rsp, 28h
0x180008e54  mov     rcx, [rcx]
0x180008e57  test    rcx, rcx
0x180008e5a  jz      short loc_180008E6C
0x180008e5c  mov     rax, [rcx]
0x180008e5f  mov     edx, 1
0x180008e64  mov     rax, [rax]
0x180008e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6c  add     rsp, 28h
0x180008e70  retn
```
