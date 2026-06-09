# _snprintf_s<17>(char (&)[17],unsigned __int64,char const *,...)

- ea: `0x180003044`
- end: `0x180003079`
- name: `??$_snprintf_s@$0BB@@@YAHAEAY0BB@D_KPEBDZZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800047f8`

## import_xrefs

- `msvcrt!_vsnprintf_s` at `0x18000306e`
- `msvcrt!_vsnprintf_s` at `0x18000306e`

## pseudocode

```c
int _snprintf_s<17>(char *a1, size_t a2, const char *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return _vsnprintf_s(a1, 0x11u, a2, a3, va);
}

```

## disassembly

```asm
0x180003044  mov     r11, rsp
0x180003047  mov     [r11+18h], r8
0x18000304b  mov     [r11+20h], r9
0x18000304f  sub     rsp, 48h
0x180003053  mov     r9, r8; Format
0x180003056  mov     qword ptr [r11-18h], 0
0x18000305e  mov     r8, rdx; MaxCount
0x180003061  lea     rax, [r11+20h]
0x180003065  mov     edx, 11h; BufferCount
0x18000306a  mov     [r11-28h], rax
0x18000306e  call    cs:__imp__vsnprintf_s
0x180003074  add     rsp, 48h
0x180003078  retn
```
