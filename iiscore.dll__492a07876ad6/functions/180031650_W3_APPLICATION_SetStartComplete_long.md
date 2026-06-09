# W3_APPLICATION::SetStartComplete(long)

- ea: `0x180031650`
- end: `0x18003168b`
- name: `?SetStartComplete@W3_APPLICATION@@QEAAXJ@Z`
- size: `59`
- prototype: `void __fastcall(W3_APPLICATION *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180030738`

## callees

- `0x180031650`
- `0x180038010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003167f`

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
0x180031650  push    rbx
0x180031652  sub     rsp, 20h
0x180031656  mov     rbx, rcx
0x180031659  test    edx, edx
0x18003165b  jns     short loc_18003166C
0x18003165d  add     rcx, 8
0x180031661  mov     rax, [rcx]
0x180031664  mov     rax, [rax]
0x180031667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003166c  lea     rcx, [rbx+0C8h]
0x180031673  mov     byte ptr [rbx+0DAh], 1
0x18003167a  add     rsp, 20h
0x18003167e  pop     rbx
0x18003167f  jmp     cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
```
