# DOSCreateFile(x,x)

- ea: `0x100268d8`
- end: `0x1002691f`
- name: `_DOSCreateFile@8`
- size: `71`
- prototype: `int __thiscall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10022920`

## callees

- `0x10022871`
- `0x100268d8`
- `0x10032deb`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10026911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10026911`

## pseudocode

```c
int __fastcall DOSCreateFile(WCHAR *lpFileName, _DWORD *a2)
{
  HANDLE FileW; // eax

  if ( NetProtocolType(lpFileName) == 1 )
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
0x100268d8  mov     edi, edi
0x100268da  push    esi
0x100268db  push    edi
0x100268dc  mov     edi, edx
0x100268de  mov     esi, ecx
0x100268e0  call    _NetProtocolType@4; NetProtocolType(x)
0x100268e5  cmp     eax, 1
0x100268e8  jnz     short loc_100268EF
0x100268ea  push    0FFFFFFFDh
0x100268ec  pop     eax
0x100268ed  jmp     short loc_1002691C
0x100268ef  xor     eax, eax
0x100268f1  push    eax; int
0x100268f2  push    80h; int
0x100268f7  push    2; dwCreationDisposition
0x100268f9  push    eax; int
0x100268fa  push    eax; dwShareMode
0x100268fb  push    0C0000000h; dwDesiredAccess
0x10026900  push    esi; lpFileName
0x10026901  call    _JetCreateFileW@28; JetCreateFileW(x,x,x,x,x,x,x)
0x10026906  mov     [edi], eax
0x10026908  cmp     eax, 0FFFFFFFFh
0x1002690b  jz      short loc_10026911
0x1002690d  xor     eax, eax
0x1002690f  jmp     short loc_1002691C
0x10026911  call    ds:__imp__GetLastError@0; GetLastError()
0x10026917  movzx   eax, ax
0x1002691a  neg     eax
0x1002691c  pop     edi
0x1002691d  pop     esi
0x1002691e  retn
```
