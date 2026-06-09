# DOSCreateFile(x,x)

- ea: `0x1000b410`
- end: `0x1000b461`
- name: `_DOSCreateFile@8`
- size: `81`
- prototype: `int __stdcall(LPCWSTR lpFileName, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000cbf0`
- `0x1000fc70`
- `0x100133f0`
- `0x1001ad40`
- `0x1001d9a0`
- `0x1001ede0`

## callees

- `0x1000b410`
- `0x1000e350`
- `0x1002a920`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000b451`
- `KERNEL32!GetLastError` at `0x1000b451`

## pseudocode

```c
int __stdcall DOSCreateFile(LPCWSTR lpFileName, _DWORD *a2)
{
  HANDLE FileW; // eax

  if ( NetProtocolType((int)lpFileName) == 1 )
    return -3;
  FileW = JetCreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 128, 0);
  *a2 = FileW;
  if ( FileW == (HANDLE)-1 )
    return -(unsigned __int16)GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x1000b410  push    [esp+lpFileName]
0x1000b414  call    _NetProtocolType@4; NetProtocolType(x)
0x1000b419  cmp     eax, 1
0x1000b41c  jnz     short loc_1000B426
0x1000b41e  mov     eax, 0FFFFFFFDh
0x1000b423  retn    8
0x1000b426  push    0; hTemplateFile
0x1000b428  push    80h; int
0x1000b42d  push    2; dwCreationDisposition
0x1000b42f  push    0; lpSecurityAttributes
0x1000b431  push    0; dwShareMode
0x1000b433  push    0C0000000h; dwDesiredAccess
0x1000b438  push    [esp+18h+lpFileName]; lpFileName
0x1000b43c  call    _JetCreateFileW@28; JetCreateFileW(x,x,x,x,x,x,x)
0x1000b441  mov     ecx, [esp+arg_4]
0x1000b445  mov     [ecx], eax
0x1000b447  cmp     eax, 0FFFFFFFFh
0x1000b44a  jz      short loc_1000B451
0x1000b44c  xor     eax, eax
0x1000b44e  retn    8
0x1000b451  call    ds:__imp__GetLastError@0; GetLastError()
0x1000b457  and     eax, 0FFFFh
0x1000b45c  neg     eax
0x1000b45e  retn    8
```
