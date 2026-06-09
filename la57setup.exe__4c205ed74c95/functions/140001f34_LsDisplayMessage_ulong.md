# LsDisplayMessage(ulong,...)

- ea: `0x140001f34`
- end: `0x140001fbe`
- name: `?LsDisplayMessage@@YAXKZZ`
- size: `138`
- prototype: `void(signed int dwMessageId, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ca4`
- `0x140001e14`

## callees

- `0x140001f34`
- `0x140001fc4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140001f88`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140001f88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001fb3`

## pseudocode

```c
void LsDisplayMessage(signed int dwMessageId, ...)
{
  DWORD v1; // eax
  va_list v2; // [rsp+40h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-10h] BYREF
  va_list va; // [rsp+68h] [rbp+10h] BYREF

  va_start(va, dwMessageId);
  va_copy(v2, va);
  hMem[0] = 0;
  v1 = FormatMessageW(0x900u, 0, dwMessageId, 0, (LPWSTR)hMem, 0, &v2);
  v2 = 0;
  if ( v1 )
  {
    LsDisplayString((LPCWCH)hMem[0], dwMessageId < 0);
    LocalFree(hMem[0]);
  }
}

```

## disassembly

```asm
0x140001f34  mov     [rsp+arg_0], ecx
0x140001f38  mov     r11, rsp
0x140001f3b  mov     [r11+10h], rdx
0x140001f3f  mov     [r11+18h], r8
0x140001f43  mov     [r11+20h], r9
0x140001f47  sub     rsp, 58h
0x140001f4b  lea     rax, [r11+10h]
0x140001f4f  mov     qword ptr [r11-18h], 0
0x140001f57  mov     [r11-18h], rax
0x140001f5b  mov     r8d, ecx; dwMessageId
0x140001f5e  lea     rax, [r11-18h]
0x140001f62  mov     qword ptr [r11-10h], 0
0x140001f6a  mov     [r11-28h], rax
0x140001f6e  xor     r9d, r9d; dwLanguageId
0x140001f71  lea     rax, [r11-10h]
0x140001f75  mov     [rsp+58h+nSize], 0; nSize
0x140001f7d  xor     edx, edx; lpSource
0x140001f7f  mov     [r11-38h], rax
0x140001f83  mov     ecx, 900h; dwFlags
0x140001f88  call    cs:__imp_FormatMessageW
0x140001f8e  mov     [rsp+58h+var_18], 0
0x140001f97  test    eax, eax
0x140001f99  jz      short loc_140001FB9
0x140001f9b  mov     rcx, [rsp+58h+hMem]; lpWideCharStr
0x140001fa0  xor     edx, edx
0x140001fa2  cmp     [rsp+58h+arg_0], edx
0x140001fa6  setl    dl; int
0x140001fa9  call    ?LsDisplayString@@YAXPEBGH@Z; LsDisplayString(ushort const *,int)
0x140001fae  mov     rcx, [rsp+58h+hMem]; hMem
0x140001fb3  call    cs:__imp_LocalFree
0x140001fb9  add     rsp, 58h
0x140001fbd  retn
```
