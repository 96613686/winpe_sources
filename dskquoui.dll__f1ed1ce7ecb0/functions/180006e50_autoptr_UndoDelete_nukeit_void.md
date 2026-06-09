# autoptr<UndoDelete>::nukeit(void)

- ea: `0x180006e50`
- end: `0x180006e72`
- name: `?nukeit@?$autoptr@VUndoDelete@@@@EEAAXXZ`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006e50`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall autoptr<UndoDelete>::nukeit(__int64 a1)
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a1 + 16);
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180006e50  sub     rsp, 28h
0x180006e54  mov     rcx, [rcx+10h]
0x180006e58  test    rcx, rcx
0x180006e5b  jz      short loc_180006E6D
0x180006e5d  mov     rax, [rcx]
0x180006e60  mov     edx, 1
0x180006e65  mov     rax, [rax]
0x180006e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6d  add     rsp, 28h
0x180006e71  retn
```
