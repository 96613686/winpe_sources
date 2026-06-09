# DRR_WriteFile

- ea: `0x18000d3cc`
- end: `0x18000d448`
- name: `DRR_WriteFile`
- size: `124`
- prototype: `__int64 __fastcall(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToWrite, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003ad0`

## callees

- `0x18000d3cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d42c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000d40e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000d40e`

## pseudocode

```c
__int64 __fastcall DRR_WriteFile(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToWrite, _DWORD *a4)
{
  DWORD LastError; // esi
  DWORD v9; // edi
  __int64 result; // rax
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  LastError = 0;
  NumberOfBytesWritten = 0;
  v9 = nNumberOfBytesToWrite;
  if ( nNumberOfBytesToWrite )
  {
    while ( WriteFile(hFile, lpBuffer, v9, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten )
      {
        lpBuffer += NumberOfBytesWritten;
        v9 -= NumberOfBytesWritten;
        if ( v9 )
          continue;
      }
      goto LABEL_7;
    }
    LastError = GetLastError();
  }
LABEL_7:
  result = LastError;
  *a4 = nNumberOfBytesToWrite - v9;
  return result;
}

```

## disassembly

```asm
0x18000d3cc  mov     rax, rsp
0x18000d3cf  push    rbx
0x18000d3d0  push    rbp
0x18000d3d1  push    rsi
0x18000d3d2  push    rdi
0x18000d3d3  push    r14
0x18000d3d5  push    r15
0x18000d3d7  sub     rsp, 38h
0x18000d3db  xor     esi, esi
0x18000d3dd  mov     dword ptr [rax+18h], 0
0x18000d3e4  mov     r14, r9
0x18000d3e7  mov     ebx, r8d
0x18000d3ea  mov     rbp, rdx
0x18000d3ed  mov     r15, rcx
0x18000d3f0  mov     edi, r8d
0x18000d3f3  test    r8d, r8d
0x18000d3f6  jz      short loc_18000D434
0x18000d3f8  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000d400  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x18000d405  mov     r8d, edi; nNumberOfBytesToWrite
0x18000d408  mov     rdx, rbp; lpBuffer
0x18000d40b  mov     rcx, r15; hFile
0x18000d40e  call    cs:__imp_WriteFile
0x18000d414  test    eax, eax
0x18000d416  jz      short loc_18000D42C
0x18000d418  mov     ecx, [rsp+68h+NumberOfBytesWritten]
0x18000d41f  test    ecx, ecx
0x18000d421  jz      short loc_18000D434
0x18000d423  add     rbp, rcx
0x18000d426  sub     edi, ecx
0x18000d428  jnz     short loc_18000D3F8
0x18000d42a  jmp     short loc_18000D434
0x18000d42c  call    cs:__imp_GetLastError
0x18000d432  mov     esi, eax
0x18000d434  sub     ebx, edi
0x18000d436  mov     eax, esi
0x18000d438  mov     [r14], ebx
0x18000d43b  add     rsp, 38h
0x18000d43f  pop     r15
0x18000d441  pop     r14
0x18000d443  pop     rdi
0x18000d444  pop     rsi
0x18000d445  pop     rbp
0x18000d446  pop     rbx
0x18000d447  retn
```
