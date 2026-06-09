# WriteToFile(void *,ushort const *)

- ea: `0x18002e0a4`
- end: `0x18002e153`
- name: `?WriteToFile@@YAJPEAXPEBG@Z`
- size: `175`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002d0d8`

## callees

- `0x180018d18`
- `0x18002df68`
- `0x18002e0a4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002e10d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002e10d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e130`

## pseudocode

```c
__int64 __fastcall WriteToFile(char *hFile, LPCWCH lpWideCharStr)
{
  int LastErrorAsHResult; // ebx
  __int64 v5; // rdi
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF
  LPCVOID lpBuffer; // [rsp+60h] [rbp+18h] BYREF

  lpBuffer = 0;
  NumberOfBytesWritten = 0;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL && lpWideCharStr )
  {
    LastErrorAsHResult = UnicodeToAnsiString(lpWideCharStr, (char **)&lpBuffer);
    if ( LastErrorAsHResult >= 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( lpWideCharStr[v5] );
      if ( !WriteFile(hFile, lpBuffer, v5, &NumberOfBytesWritten, 0) && (_DWORD)v5 != NumberOfBytesWritten )
        LastErrorAsHResult = GetLastErrorAsHResult();
    }
    if ( lpBuffer )
      LocalFree((HLOCAL)lpBuffer);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x18002e0a4  mov     r11, rsp
0x18002e0a7  mov     [r11+10h], rbx
0x18002e0ab  mov     [r11+20h], rsi
0x18002e0af  push    rdi
0x18002e0b0  push    r14
0x18002e0b2  push    r15
0x18002e0b4  sub     rsp, 30h
0x18002e0b8  xor     r15d, r15d
0x18002e0bb  lea     rax, [rcx-1]
0x18002e0bf  mov     [r11+18h], r15
0x18002e0c3  mov     rsi, rdx
0x18002e0c6  mov     [r11+8], r15d
0x18002e0ca  mov     r14, rcx
0x18002e0cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e0d1  ja      short loc_18002E138
0x18002e0d3  test    rdx, rdx
0x18002e0d6  jz      short loc_18002E138
0x18002e0d8  lea     rdx, [r11+18h]; char **
0x18002e0dc  mov     rcx, rsi; lpWideCharStr
0x18002e0df  call    ?UnicodeToAnsiString@@YAJPEAGPEAPEAD@Z; UnicodeToAnsiString(ushort *,char * *)
0x18002e0e4  mov     ebx, eax
0x18002e0e6  test    eax, eax
0x18002e0e8  js      short loc_18002E124
0x18002e0ea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002e0ee  inc     rdi
0x18002e0f1  cmp     [rsi+rdi*2], r15w
0x18002e0f6  jnz     short loc_18002E0EE
0x18002e0f8  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x18002e0fd  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002e102  mov     r8d, edi; nNumberOfBytesToWrite
0x18002e105  mov     [rsp+48h+lpOverlapped], r15; lpOverlapped
0x18002e10a  mov     rcx, r14; hFile
0x18002e10d  call    cs:__imp_WriteFile
0x18002e113  test    eax, eax
0x18002e115  jnz     short loc_18002E124
0x18002e117  cmp     edi, [rsp+48h+NumberOfBytesWritten]
0x18002e11b  jz      short loc_18002E124
0x18002e11d  call    GetLastErrorAsHResult
0x18002e122  mov     ebx, eax
0x18002e124  cmp     [rsp+48h+lpBuffer], r15
0x18002e129  jz      short loc_18002E13D
0x18002e12b  mov     rcx, [rsp+48h+lpBuffer]; hMem
0x18002e130  call    cs:__imp_LocalFree
0x18002e136  jmp     short loc_18002E13D
0x18002e138  mov     ebx, 80070057h
0x18002e13d  mov     rsi, [rsp+48h+arg_18]
0x18002e142  mov     eax, ebx
0x18002e144  mov     rbx, [rsp+48h+arg_8]
0x18002e149  add     rsp, 30h
0x18002e14d  pop     r15
0x18002e14f  pop     r14
0x18002e151  pop     rdi
0x18002e152  retn
```
