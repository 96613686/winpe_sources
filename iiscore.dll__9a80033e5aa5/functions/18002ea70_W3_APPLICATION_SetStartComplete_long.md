# W3_APPLICATION::SetStartComplete(long)

- ea: `0x18002ea70`
- end: `0x18002eaa6`
- name: `?SetStartComplete@W3_APPLICATION@@QEAAXJ@Z`
- size: `54`
- prototype: `void __fastcall(W3_APPLICATION *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002dcb8`

## callees

- `0x18002ea70`
- `0x180035010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ea9f`

## pseudocode

```c
void __fastcall W3_APPLICATION::SetStartComplete(W3_APPLICATION *this, int a2)
{
  if ( a2 < 0 )
    (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  *((_BYTE *)this + 218) = 1;
  CReaderWriterLock3::WriteUnlock((W3_APPLICATION *)((char *)this + 200));
}

```

## disassembly

```asm
0x18002ea70  push    rbx
0x18002ea72  sub     rsp, 20h
0x18002ea76  mov     rbx, rcx
0x18002ea79  test    edx, edx
0x18002ea7b  jns     short loc_18002EA8C
0x18002ea7d  add     rcx, 8
0x18002ea81  mov     rax, [rcx]
0x18002ea84  mov     rax, [rax]
0x18002ea87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea8c  lea     rcx, [rbx+0C8h]
0x18002ea93  mov     byte ptr [rbx+0DAh], 1
0x18002ea9a  add     rsp, 20h
0x18002ea9e  pop     rbx
0x18002ea9f  jmp     cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
```
