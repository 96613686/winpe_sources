# FileStream::Read(void *,ulong,ulong *)

- ea: `0x180037fe0`
- end: `0x180038016`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `54`
- prototype: `signed int __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180037fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180037ff1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180037ff1`

## pseudocode

```c
signed int __fastcall FileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( ReadFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180037fe0  sub     rsp, 38h
0x180037fe4  mov     rcx, [rcx+8]; hFile
0x180037fe8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180037ff1  call    cs:__imp_ReadFile
0x180037ff7  test    eax, eax
0x180037ff9  jz      short loc_180037FFF
0x180037ffb  xor     eax, eax
0x180037ffd  jmp     short loc_180038011
0x180037fff  call    cs:__imp_GetLastError
0x180038005  test    eax, eax
0x180038007  jle     short loc_180038011
0x180038009  movzx   eax, ax
0x18003800c  or      eax, 80070000h
0x180038011  add     rsp, 38h
0x180038015  retn
```
