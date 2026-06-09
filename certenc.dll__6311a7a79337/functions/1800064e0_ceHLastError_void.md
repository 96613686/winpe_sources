# ceHLastError(void)

- ea: `0x1800064e0`
- end: `0x180006510`
- name: `?ceHLastError@@YAJXZ`
- size: `48`
- prototype: `__int64(void)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a70`
- `0x180001d20`
- `0x1800022f0`
- `0x180002580`
- `0x180002b10`
- `0x180002d00`
- `0x180003790`
- `0x180003a30`
- `0x180004c20`
- `0x180004e20`
- `0x18000550c`
- `0x180005984`
- `0x180005b6c`
- `0x180005c48`
- `0x180005cd8`
- `0x180006234`
- `0x180006468`
- `0x180006518`
- `0x18000662c`
- `0x1800067b4`
- `0x180007a70`
- `0x180007c60`

## callees

- `0x1800064e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064e4`

## pseudocode

```c
__int64 ceHLastError(void)
{
  signed int LastError; // eax
  unsigned int v1; // ecx

  LastError = GetLastError();
  v1 = LastError;
  if ( LastError >= 2 )
  {
    v1 = (unsigned __int16)LastError | 0x80070000;
    if ( !(_WORD)LastError )
      return (unsigned int)-2147418113;
  }
  return v1;
}

```

## disassembly

```asm
0x1800064e0  sub     rsp, 28h
0x1800064e4  call    cs:__imp_GetLastError
0x1800064ea  mov     ecx, eax
0x1800064ec  cmp     eax, 2
0x1800064ef  jl      short loc_180006509
0x1800064f1  test    eax, eax
0x1800064f3  jle     short loc_1800064FE
0x1800064f5  movzx   ecx, ax
0x1800064f8  or      ecx, 80070000h
0x1800064fe  test    cx, cx
0x180006501  mov     edx, 8000FFFFh
0x180006506  cmovz   ecx, edx
0x180006509  mov     eax, ecx
0x18000650b  add     rsp, 28h
0x18000650f  retn
```
