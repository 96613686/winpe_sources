# DOSWriteFile(x,x,x)

- ea: `0x100269a4`
- end: `0x100269ce`
- name: `_DOSWriteFile@12`
- size: `42`
- prototype: `int __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x10022920`
- `0x10025b48`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x100269b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x100269b5`

## pseudocode

```c
DWORD __fastcall DOSWriteFile(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  BOOL v3; // eax
  DWORD v4; // ecx
  DWORD NumberOfBytesWritten; // [esp+0h] [ebp-4h] BYREF

  NumberOfBytesWritten = (DWORD)hFile;
  v3 = WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
  v4 = NumberOfBytesWritten;
  if ( !v3 )
    return 0xFFFF;
  return v4;
}

```

## disassembly

```asm
0x100269a4  mov     edi, edi
0x100269a6  push    ebp
0x100269a7  mov     ebp, esp
0x100269a9  push    ecx
0x100269aa  push    0; lpOverlapped
0x100269ac  lea     eax, [ebp+NumberOfBytesWritten]
0x100269af  push    eax; lpNumberOfBytesWritten
0x100269b0  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x100269b3  push    edx; lpBuffer
0x100269b4  push    ecx; hFile
0x100269b5  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x100269bb  mov     ecx, [ebp+NumberOfBytesWritten]
0x100269be  test    eax, eax
0x100269c0  mov     edx, 0FFFFh
0x100269c5  cmovz   ecx, edx
0x100269c8  mov     eax, ecx
0x100269ca  leave
0x100269cb  retn    4
```
