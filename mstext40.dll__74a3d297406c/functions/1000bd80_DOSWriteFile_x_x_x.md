# DOSWriteFile(x,x,x)

- ea: `0x1000bd80`
- end: `0x1000bdad`
- name: `_DOSWriteFile@12`
- size: `45`
- prototype: `int __stdcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1000cbf0`
- `0x1000fc70`
- `0x1001ad40`
- `0x1001c420`
- `0x1001d440`
- `0x1001da60`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1000bd94`
- `KERNEL32!WriteFile` at `0x1000bd94`

## pseudocode

```c
DWORD __thiscall DOSWriteFile(void *this, HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  BOOL v4; // eax
  DWORD v5; // ecx
  DWORD NumberOfBytesWritten; // [esp+0h] [ebp-4h] BYREF

  NumberOfBytesWritten = (DWORD)this;
  v4 = WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
  v5 = NumberOfBytesWritten;
  if ( !v4 )
    return 0xFFFF;
  return v5;
}

```

## disassembly

```asm
0x1000bd80  push    ecx
0x1000bd81  push    0; lpOverlapped
0x1000bd83  lea     eax, [esp+8+NumberOfBytesWritten]
0x1000bd87  push    eax; lpNumberOfBytesWritten
0x1000bd88  push    [esp+0Ch+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1000bd8c  push    [esp+10h+lpBuffer]; lpBuffer
0x1000bd90  push    [esp+14h+hFile]; hFile
0x1000bd94  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x1000bd9a  mov     ecx, [esp+4+NumberOfBytesWritten]
0x1000bd9d  test    eax, eax
0x1000bd9f  mov     edx, 0FFFFh
0x1000bda4  cmovz   ecx, edx
0x1000bda7  mov     eax, ecx
0x1000bda9  pop     ecx
0x1000bdaa  retn    0Ch
```
