# _snprintf_s<245>(char (&)[245],unsigned __int64,char const *,...)

- ea: `0x180003080`
- end: `0x1800030b5`
- name: `??$_snprintf_s@$0PF@@@YAHAEAY0PF@D_KPEBDZZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800048ec`

## import_xrefs

- `msvcrt!_vsnprintf_s` at `0x1800030aa`
- `msvcrt!_vsnprintf_s` at `0x1800030aa`

## pseudocode

```c
int _snprintf_s<245>(char *a1, size_t a2, const char *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return _vsnprintf_s(a1, 0xF5u, a2, a3, va);
}

```

## disassembly

```asm
0x180003080  mov     r11, rsp
0x180003083  mov     [r11+18h], r8
0x180003087  mov     [r11+20h], r9
0x18000308b  sub     rsp, 48h
0x18000308f  mov     r9, r8; Format
0x180003092  mov     qword ptr [r11-18h], 0
0x18000309a  mov     r8, rdx; MaxCount
0x18000309d  lea     rax, [r11+20h]
0x1800030a1  mov     edx, 0F5h; BufferCount
0x1800030a6  mov     [r11-28h], rax
0x1800030aa  call    cs:__imp__vsnprintf_s
0x1800030b0  add     rsp, 48h
0x1800030b4  retn
```
