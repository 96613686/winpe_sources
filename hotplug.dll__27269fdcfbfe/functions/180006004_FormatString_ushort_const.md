# FormatString(ushort const *,...)

- ea: `0x180006004`
- end: `0x180006071`
- name: `?FormatString@@YAPEAGPEBGZZ`
- size: `109`
- prototype: `unsigned __int16 *(LPCVOID lpSource, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000312c`
- `0x180005724`
- `0x180005c80`

## callees

- `0x180006004`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180006059`
- `KERNEL32!FormatMessageW` at `0x180006059`

## pseudocode

```c
unsigned __int16 *FormatString(LPCVOID lpSource, ...)
{
  va_list v2; // [rsp+40h] [rbp-18h] BYREF
  WCHAR v3[8]; // [rsp+48h] [rbp-10h] BYREF
  va_list va; // [rsp+68h] [rbp+10h] BYREF

  va_start(va, lpSource);
  va_copy(v2, va);
  *(_QWORD *)v3 = 0;
  if ( FormatMessageW(0x500u, lpSource, 0, 0, v3, 0, &v2) )
    return *(unsigned __int16 **)v3;
  else
    return 0;
}

```

## disassembly

```asm
0x180006004  mov     r11, rsp
0x180006007  mov     [r11+8], rcx
0x18000600b  mov     [r11+10h], rdx
0x18000600f  mov     [r11+18h], r8
0x180006013  mov     [r11+20h], r9
0x180006017  sub     rsp, 58h
0x18000601b  lea     rax, [r11+10h]
0x18000601f  mov     qword ptr [r11-18h], 0
0x180006027  mov     [r11-18h], rax
0x18000602b  mov     rdx, rcx; lpSource
0x18000602e  lea     rax, [r11-18h]
0x180006032  mov     qword ptr [r11-10h], 0
0x18000603a  mov     [r11-28h], rax
0x18000603e  xor     r9d, r9d; dwLanguageId
0x180006041  lea     rax, [r11-10h]
0x180006045  mov     [rsp+58h+nSize], 0; nSize
0x18000604d  xor     r8d, r8d; dwMessageId
0x180006050  mov     [r11-38h], rax
0x180006054  mov     ecx, 500h; dwFlags
0x180006059  call    cs:__imp_FormatMessageW
0x18000605f  test    eax, eax
0x180006061  jnz     short loc_180006067
0x180006063  xor     eax, eax
0x180006065  jmp     short loc_18000606C
0x180006067  mov     rax, qword ptr [rsp+58h+var_10]
0x18000606c  add     rsp, 58h
0x180006070  retn
```
