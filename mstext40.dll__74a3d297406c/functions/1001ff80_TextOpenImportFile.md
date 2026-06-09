# TextOpenImportFile

- ea: `0x1001ff80`
- end: `0x10020073`
- name: `TextOpenImportFile`
- size: `243`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1001fcd0`

## callees

- `0x1000b9b0`
- `0x1001d550`
- `0x1001d570`
- `0x1001d770`
- `0x1001ff80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10020030`
- `KERNEL32!GetLastError` at `0x10020030`
- `KERNEL32!GetFileSize` at `0x10020022`
- `KERNEL32!GetFileSize` at `0x10020022`

## pseudocode

```c
int __stdcall TextOpenImportFile(LPCWSTR lpFileName, _DWORD *a2, int a3)
{
  int **v3; // esi
  int v4; // eax
  int v5; // ecx
  int result; // eax
  int v7; // eax
  DWORD FileSize; // eax

  if ( a3 == 3 )
  {
    v3 = (int **)(a2 + 1);
    v4 = BFOpenFile(lpFileName, 18, a2 + 1);
    v5 = v4;
    if ( !v4 || v4 == -5 && (a2[2] = 1, (v5 = BFOpenFile(lpFileName, 16, v3)) == 0) )
    {
      BFSetFilePosition(*v3, 2, 0);
      BFGetFilePosition(*v3, a2 + 5);
      BFSetFilePosition(*v3, 0, 0);
      return 0;
    }
    goto LABEL_12;
  }
  v7 = DOSOpenFile(lpFileName, 18, a2);
  v5 = v7;
  if ( v7 )
  {
    if ( v7 != -5 || (a2[2] = 1, (v5 = DOSOpenFile(lpFileName, 16, a2)) != 0) )
    {
LABEL_12:
      if ( v5 == -4 )
        return -1807;
      if ( v5 == -2 )
        return -1811;
      result = -1032;
      if ( v5 == -3 )
        return -1023;
      return result;
    }
  }
  FileSize = GetFileSize((HANDLE)*a2, 0);
  a2[5] = FileSize;
  if ( FileSize != -1 )
    return 0;
  GetLastError();
  return -1032;
}

```

## disassembly

```asm
0x1001ff80  cmp     [esp+arg_8], 3
0x1001ff85  push    esi
0x1001ff86  push    edi
0x1001ff87  jnz     short loc_1001FFEC
0x1001ff89  mov     edi, [esp+8+arg_4]
0x1001ff8d  lea     esi, [edi+4]
0x1001ff90  push    esi; int
0x1001ff91  push    12h; int
0x1001ff93  push    [esp+10h+lpFileName]; lpFileName
0x1001ff97  call    _BFOpenFile@12; BFOpenFile(x,x,x)
0x1001ff9c  mov     ecx, eax
0x1001ff9e  test    ecx, ecx
0x1001ffa0  jz      short loc_1001FFC4
0x1001ffa2  cmp     ecx, 0FFFFFFFBh
0x1001ffa5  jnz     loc_10020040
0x1001ffab  push    esi; int
0x1001ffac  push    10h; int
0x1001ffae  push    [esp+10h+lpFileName]; lpFileName
0x1001ffb2  mov     dword ptr [edi+8], 1
0x1001ffb9  call    _BFOpenFile@12; BFOpenFile(x,x,x)
0x1001ffbe  mov     ecx, eax
0x1001ffc0  test    ecx, ecx
0x1001ffc2  jnz     short loc_10020040
0x1001ffc4  push    0; lDistanceToMove
0x1001ffc6  push    2; int
0x1001ffc8  push    dword ptr [esi]; int
0x1001ffca  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x1001ffcf  lea     ecx, [edi+14h]
0x1001ffd2  push    ecx
0x1001ffd3  push    dword ptr [esi]
0x1001ffd5  call    _BFGetFilePosition@8; BFGetFilePosition(x,x)
0x1001ffda  push    0; lDistanceToMove
0x1001ffdc  push    0; int
0x1001ffde  push    dword ptr [esi]; int
0x1001ffe0  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x1001ffe5  pop     edi
0x1001ffe6  xor     eax, eax
0x1001ffe8  pop     esi
0x1001ffe9  retn    0Ch
0x1001ffec  mov     esi, [esp+8+arg_4]
0x1001fff0  mov     edi, [esp+8+lpFileName]
0x1001fff4  push    esi; int
0x1001fff5  push    12h; int
0x1001fff7  push    edi; lpFileName
0x1001fff8  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x1001fffd  mov     ecx, eax
0x1001ffff  test    ecx, ecx
0x10020001  jz      short loc_1002001E
0x10020003  cmp     ecx, 0FFFFFFFBh
0x10020006  jnz     short loc_10020040
0x10020008  push    esi; int
0x10020009  push    10h; int
0x1002000b  push    edi; lpFileName
0x1002000c  mov     dword ptr [esi+8], 1
0x10020013  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x10020018  mov     ecx, eax
0x1002001a  test    ecx, ecx
0x1002001c  jnz     short loc_10020040
0x1002001e  push    0; lpFileSizeHigh
0x10020020  push    dword ptr [esi]; hFile
0x10020022  call    ds:__imp__GetFileSize@8; GetFileSize(x,x)
0x10020028  mov     [esi+14h], eax
0x1002002b  cmp     eax, 0FFFFFFFFh
0x1002002e  jnz     short loc_1001FFE5
0x10020030  call    ds:__imp__GetLastError@0; GetLastError()
0x10020036  pop     edi
0x10020037  mov     eax, 0FFFFFBF8h
0x1002003c  pop     esi
0x1002003d  retn    0Ch
0x10020040  cmp     ecx, 0FFFFFFFCh
0x10020043  jnz     short loc_1002004F
0x10020045  pop     edi
0x10020046  mov     eax, 0FFFFF8F1h
0x1002004b  pop     esi
0x1002004c  retn    0Ch
0x1002004f  cmp     ecx, 0FFFFFFFEh
0x10020052  jnz     short loc_1002005E
0x10020054  pop     edi
0x10020055  mov     eax, 0FFFFF8EDh
0x1002005a  pop     esi
0x1002005b  retn    0Ch
0x1002005e  cmp     ecx, 0FFFFFFFDh
0x10020061  mov     eax, 0FFFFFBF8h
0x10020066  mov     edx, 0FFFFFC01h
0x1002006b  pop     edi
0x1002006c  cmovz   eax, edx
0x1002006f  pop     esi
0x10020070  retn    0Ch
```
