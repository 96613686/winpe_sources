# DOSFileSize(x,x)

- ea: `0x1000b640`
- end: `0x1000b6cc`
- name: `_DOSFileSize@8`
- size: `140`
- prototype: `int __stdcall(LPCWSTR lpFileName, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100108e0`
- `0x1001c140`

## callees

- `0x1000b640`
- `0x1000e350`
- `0x1002a920`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1000b6a8`
- `KERNEL32!SetFilePointer` at `0x1000b6b1`
- `KERNEL32!SetFilePointer` at `0x1000b69b`
- `KERNEL32!CloseHandle` at `0x1000b6bb`
- `KERNEL32!CloseHandle` at `0x1000b6bb`
- `KERNEL32!GetLastError` at `0x1000b68d`
- `KERNEL32!GetLastError` at `0x1000b68d`

## pseudocode

```c
int __stdcall DOSFileSize(LPCWSTR lpFileName, DWORD *a2)
{
  HANDLE FileW; // eax
  void *v4; // edi
  DWORD v5; // eax

  if ( NetProtocolType(lpFileName) )
  {
    *a2 = 0x2000;
    return 1;
  }
  else
  {
    *a2 = 0;
    FileW = JetCreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 128, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1 )
    {
      GetLastError();
      return 0;
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      v5 = SetFilePointer(v4, 0, 0, 1u);
      if ( v5 != -1 )
        *a2 = v5;
      CloseHandle(v4);
      return 1;
    }
  }
}

```

## disassembly

```asm
0x1000b640  push    esi
0x1000b641  mov     esi, [esp+4+lpFileName]
0x1000b645  push    esi
0x1000b646  call    _NetProtocolType@4; NetProtocolType(x)
0x1000b64b  test    eax, eax
0x1000b64d  jz      short loc_1000B662
0x1000b64f  mov     eax, [esp+4+arg_4]
0x1000b653  pop     esi
0x1000b654  mov     dword ptr [eax], 2000h
0x1000b65a  mov     eax, 1
0x1000b65f  retn    8
0x1000b662  push    ebx
0x1000b663  mov     ebx, [esp+8+arg_4]
0x1000b667  push    edi
0x1000b668  push    0; hTemplateFile
0x1000b66a  push    80h; int
0x1000b66f  push    3; dwCreationDisposition
0x1000b671  push    0; lpSecurityAttributes
0x1000b673  push    3; dwShareMode
0x1000b675  push    80000000h; dwDesiredAccess
0x1000b67a  push    esi; lpFileName
0x1000b67b  mov     dword ptr [ebx], 0
0x1000b681  call    _JetCreateFileW@28; JetCreateFileW(x,x,x,x,x,x,x)
0x1000b686  mov     edi, eax
0x1000b688  cmp     edi, 0FFFFFFFFh
0x1000b68b  jnz     short loc_1000B69B
0x1000b68d  call    ds:__imp__GetLastError@0; GetLastError()
0x1000b693  pop     edi
0x1000b694  pop     ebx
0x1000b695  xor     eax, eax
0x1000b697  pop     esi
0x1000b698  retn    8
0x1000b69b  mov     esi, ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1000b6a1  push    2; dwMoveMethod
0x1000b6a3  push    0; lpDistanceToMoveHigh
0x1000b6a5  push    0; lDistanceToMove
0x1000b6a7  push    edi; hFile
0x1000b6a8  call    esi ; SetFilePointer(x,x,x,x); SetFilePointer(x,x,x,x)
0x1000b6aa  push    1; dwMoveMethod
0x1000b6ac  push    0; lpDistanceToMoveHigh
0x1000b6ae  push    0; lDistanceToMove
0x1000b6b0  push    edi; hFile
0x1000b6b1  call    esi ; SetFilePointer(x,x,x,x); SetFilePointer(x,x,x,x)
0x1000b6b3  cmp     eax, 0FFFFFFFFh
0x1000b6b6  jz      short loc_1000B6BA
0x1000b6b8  mov     [ebx], eax
0x1000b6ba  push    edi; hObject
0x1000b6bb  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000b6c1  pop     edi
0x1000b6c2  pop     ebx
0x1000b6c3  mov     eax, 1
0x1000b6c8  pop     esi
0x1000b6c9  retn    8
```
