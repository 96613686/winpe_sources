# swprintf_s<260>(ushort (&)[260],ushort const *,...)

- ea: `0x1800047c4`
- end: `0x1800047f6`
- name: `??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800058b8`
- `0x180007668`
- `0x180008074`

## import_xrefs

- `msvcrt!vswprintf_s` at `0x1800047eb`
- `msvcrt!vswprintf_s` at `0x1800047eb`

## pseudocode

```c
int swprintf_s<260>(wchar_t *a1, const wchar_t *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  return vswprintf_s(a1, 0x104u, a2, va);
}

```

## disassembly

```asm
0x1800047c4  mov     rax, rsp
0x1800047c7  mov     [rax+10h], rdx
0x1800047cb  mov     [rax+18h], r8
0x1800047cf  mov     [rax+20h], r9
0x1800047d3  sub     rsp, 38h
0x1800047d7  mov     r8, rdx; Format
0x1800047da  mov     qword ptr [rax-18h], 0
0x1800047e2  mov     edx, 104h; BufferCount
0x1800047e7  lea     r9, [rax+18h]; ArgList
0x1800047eb  call    cs:__imp_vswprintf_s
0x1800047f1  add     rsp, 38h
0x1800047f5  retn
```
