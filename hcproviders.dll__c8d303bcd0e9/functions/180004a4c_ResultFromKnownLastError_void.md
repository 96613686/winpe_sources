# ResultFromKnownLastError(void)

- ea: `0x180004a4c`
- end: `0x180004a78`
- name: `?ResultFromKnownLastError@@YAJXZ`
- size: `44`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001490`
- `0x1800015b0`
- `0x180001ea0`
- `0x180002300`
- `0x180002770`
- `0x180008bec`
- `0x180008d00`

## callees

- `0x180004a4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a50`

## pseudocode

```c
signed int ResultFromKnownLastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180004a4c  sub     rsp, 28h
0x180004a50  call    cs:__imp_GetLastError
0x180004a57  nop     dword ptr [rax+rax+00h]
0x180004a5c  test    eax, eax
0x180004a5e  jle     short loc_180004A68
0x180004a60  movzx   eax, ax
0x180004a63  or      eax, 80070000h
0x180004a68  test    eax, eax
0x180004a6a  mov     ecx, 80004005h
0x180004a6f  cmovns  eax, ecx
0x180004a72  add     rsp, 28h
0x180004a76  retn
```
