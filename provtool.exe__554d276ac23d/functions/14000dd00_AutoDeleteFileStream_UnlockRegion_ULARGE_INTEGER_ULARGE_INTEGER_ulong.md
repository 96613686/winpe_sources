# AutoDeleteFileStream::UnlockRegion(_ULARGE_INTEGER,_ULARGE_INTEGER,ulong)

- ea: `0x14000dd00`
- end: `0x14000dd19`
- name: `?UnlockRegion@AutoDeleteFileStream@@UEAAJT_ULARGE_INTEGER@@0K@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *__hidden this, union _ULARGE_INTEGER, union _ULARGE_INTEGER, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::UnlockRegion(
        AutoDeleteFileStream *this,
        union _ULARGE_INTEGER a2,
        union _ULARGE_INTEGER a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, union _ULARGE_INTEGER, union _ULARGE_INTEGER))(**((_QWORD **)this + 6) + 88LL))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x14000dd00  sub     rsp, 38h
0x14000dd04  mov     rcx, [rcx+30h]
0x14000dd08  mov     rax, [rcx]
0x14000dd0b  mov     rax, [rax+58h]
0x14000dd0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd14  add     rsp, 38h
0x14000dd18  retn
```
