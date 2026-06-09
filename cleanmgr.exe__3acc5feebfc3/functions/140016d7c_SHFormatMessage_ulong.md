# SHFormatMessage(ulong,...)

- ea: `0x140016d7c`
- end: `0x140016dd0`
- name: `?SHFormatMessage@@YAPEAGKZZ`
- size: `84`
- prototype: `unsigned __int16 *(DWORD dwMessageId, ...)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140009d34`
- `0x14000a534`
- `0x14000b5bc`
- `0x14000c1f4`
- `0x14000c994`
- `0x140010390`
- `0x140010630`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140016dc0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140016dc0`

## pseudocode

```c
unsigned __int16 *SHFormatMessage(DWORD dwMessageId, ...)
{
  va_list v2; // [rsp+40h] [rbp-18h] BYREF
  WCHAR v3[8]; // [rsp+48h] [rbp-10h] BYREF
  va_list va; // [rsp+68h] [rbp+10h] BYREF

  va_start(va, dwMessageId);
  va_copy(v2, va);
  *(_QWORD *)v3 = 0;
  FormatMessageW(0x900u, 0, dwMessageId, 0, v3, 0, &v2);
  return *(unsigned __int16 **)v3;
}

```

## disassembly

```asm
0x140016d7c  mov     [rsp+arg_0], ecx
0x140016d80  mov     r11, rsp
0x140016d83  mov     [r11+10h], rdx
0x140016d87  mov     [r11+18h], r8
0x140016d8b  mov     [r11+20h], r9
0x140016d8f  sub     rsp, 58h
0x140016d93  lea     rax, [r11+10h]
0x140016d97  xor     edx, edx; lpSource
0x140016d99  mov     [r11-18h], rax
0x140016d9d  mov     r8d, ecx; dwMessageId
0x140016da0  lea     rax, [r11-18h]
0x140016da4  mov     [r11-10h], rdx
0x140016da8  mov     [r11-28h], rax
0x140016dac  xor     r9d, r9d; dwLanguageId
0x140016daf  lea     rax, [r11-10h]
0x140016db3  mov     [rsp+58h+nSize], edx; nSize
0x140016db7  mov     ecx, 900h; dwFlags
0x140016dbc  mov     [r11-38h], rax
0x140016dc0  call    cs:__imp_FormatMessageW
0x140016dc6  mov     rax, qword ptr [rsp+58h+var_10]
0x140016dcb  add     rsp, 58h
0x140016dcf  retn
```
