# LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(void)

- ea: `0x180007b30`
- end: `0x180007b6d`
- name: `?_FreeSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAA_NXZ`
- size: `61`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d60`
- `0x180004340`
- `0x18001a07c`

## callees

- `0x18001d010`

## pseudocode

```c
bool __fastcall LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory(LKRhash::CLKRLinearHashTable *this)
{
  bool result; // al

  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 18) + 8LL))(
    *((_QWORD *)this + 18),
    *((_QWORD *)this + 13),
    3);
  result = 1;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 29) = 0;
  return result;
}

```

## disassembly

```asm
0x180007b30  push    rbx
0x180007b32  sub     rsp, 20h
0x180007b36  mov     rbx, rcx
0x180007b39  mov     r8d, 3
0x180007b3f  mov     rcx, [rcx+90h]
0x180007b46  mov     rdx, [rbx+68h]
0x180007b4a  mov     rax, [rcx]
0x180007b4d  mov     rax, [rax+8]
0x180007b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b56  mov     al, 1
0x180007b58  mov     qword ptr [rbx+68h], 0
0x180007b60  mov     dword ptr [rbx+74h], 0
0x180007b67  add     rsp, 20h
0x180007b6b  pop     rbx
0x180007b6c  retn
```
