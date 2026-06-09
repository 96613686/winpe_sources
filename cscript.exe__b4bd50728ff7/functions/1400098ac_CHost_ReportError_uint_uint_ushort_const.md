# CHost::ReportError(uint,uint,ushort const *)

- ea: `0x1400098ac`
- end: `0x1400098cd`
- name: `?ReportError@CHost@@QEAAJIIPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(CHost *__hidden this, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400069d0`
- `0x1400097d0`
- `0x14000a420`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall CHost::ReportError(CHost *this, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  return (*(__int64 (__fastcall **)(CHost *, __int64, __int64, const unsigned __int16 *, const OLECHAR *))(*(_QWORD *)this + 8LL))(
           this,
           a2,
           a3,
           a4,
           &Default);
}

```

## disassembly

```asm
0x1400098ac  sub     rsp, 38h
0x1400098b0  mov     rax, [rcx]
0x1400098b3  lea     r10, Default
0x1400098ba  mov     [rsp+38h+var_18], r10
0x1400098bf  mov     rax, [rax+8]
0x1400098c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098c8  add     rsp, 38h
0x1400098cc  retn
```
