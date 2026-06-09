# DOSReadFile(x,x,x)

- ea: `0x1000ba30`
- end: `0x1000ba5d`
- name: `_DOSReadFile@12`
- size: `45`
- prototype: `int __stdcall(HANDLE hFile, LPVOID lpBuffer, DWORD nNumberOfBytesToRead)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1001da00`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1000ba44`
- `KERNEL32!ReadFile` at `0x1000ba44`

## pseudocode

```c
DWORD __thiscall DOSReadFile(void *this, HANDLE hFile, LPVOID lpBuffer, DWORD nNumberOfBytesToRead)
{
  BOOL v4; // eax
  DWORD v5; // ecx
  DWORD NumberOfBytesRead; // [esp+0h] [ebp-4h] BYREF

  NumberOfBytesRead = (DWORD)this;
  v4 = ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0);
  v5 = NumberOfBytesRead;
  if ( !v4 )
    return 0xFFFF;
  return v5;
}

```

## disassembly

```asm
0x1000ba30  push    ecx
0x1000ba31  push    0; lpOverlapped
0x1000ba33  lea     eax, [esp+8+NumberOfBytesRead]
0x1000ba37  push    eax; lpNumberOfBytesRead
0x1000ba38  push    [esp+0Ch+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1000ba3c  push    [esp+10h+lpBuffer]; lpBuffer
0x1000ba40  push    [esp+14h+hFile]; hFile
0x1000ba44  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x1000ba4a  mov     ecx, [esp+4+NumberOfBytesRead]
0x1000ba4d  test    eax, eax
0x1000ba4f  mov     edx, 0FFFFh
0x1000ba54  cmovz   ecx, edx
0x1000ba57  mov     eax, ecx
0x1000ba59  pop     ecx
0x1000ba5a  retn    0Ch
```
