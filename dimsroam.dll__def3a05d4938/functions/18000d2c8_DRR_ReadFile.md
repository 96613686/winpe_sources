# DRR_ReadFile

- ea: `0x18000d2c8`
- end: `0x18000d344`
- name: `DRR_ReadFile`
- size: `124`
- prototype: `__int64 __fastcall(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToRead, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800036c8`

## callees

- `0x18000d2c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d328`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d30a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d30a`

## pseudocode

```c
__int64 __fastcall DRR_ReadFile(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToRead, _DWORD *a4)
{
  DWORD LastError; // esi
  DWORD v9; // edi
  __int64 result; // rax
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  LastError = 0;
  NumberOfBytesRead = 0;
  v9 = nNumberOfBytesToRead;
  if ( nNumberOfBytesToRead )
  {
    while ( ReadFile(hFile, lpBuffer, v9, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead )
      {
        lpBuffer += NumberOfBytesRead;
        v9 -= NumberOfBytesRead;
        if ( v9 )
          continue;
      }
      goto LABEL_7;
    }
    LastError = GetLastError();
  }
LABEL_7:
  result = LastError;
  *a4 = nNumberOfBytesToRead - v9;
  return result;
}

```

## disassembly

```asm
0x18000d2c8  mov     rax, rsp
0x18000d2cb  push    rbx
0x18000d2cc  push    rbp
0x18000d2cd  push    rsi
0x18000d2ce  push    rdi
0x18000d2cf  push    r14
0x18000d2d1  push    r15
0x18000d2d3  sub     rsp, 38h
0x18000d2d7  xor     esi, esi
0x18000d2d9  mov     dword ptr [rax+18h], 0
0x18000d2e0  mov     r14, r9
0x18000d2e3  mov     ebx, r8d
0x18000d2e6  mov     rbp, rdx
0x18000d2e9  mov     r15, rcx
0x18000d2ec  mov     edi, r8d
0x18000d2ef  test    r8d, r8d
0x18000d2f2  jz      short loc_18000D330
0x18000d2f4  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d2fc  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x18000d301  mov     r8d, edi; nNumberOfBytesToRead
0x18000d304  mov     rdx, rbp; lpBuffer
0x18000d307  mov     rcx, r15; hFile
0x18000d30a  call    cs:__imp_ReadFile
0x18000d310  test    eax, eax
0x18000d312  jz      short loc_18000D328
0x18000d314  mov     ecx, [rsp+68h+NumberOfBytesRead]
0x18000d31b  test    ecx, ecx
0x18000d31d  jz      short loc_18000D330
0x18000d31f  add     rbp, rcx
0x18000d322  sub     edi, ecx
0x18000d324  jnz     short loc_18000D2F4
0x18000d326  jmp     short loc_18000D330
0x18000d328  call    cs:__imp_GetLastError
0x18000d32e  mov     esi, eax
0x18000d330  sub     ebx, edi
0x18000d332  mov     eax, esi
0x18000d334  mov     [r14], ebx
0x18000d337  add     rsp, 38h
0x18000d33b  pop     r15
0x18000d33d  pop     r14
0x18000d33f  pop     rdi
0x18000d340  pop     rsi
0x18000d341  pop     rbp
0x18000d342  pop     rbx
0x18000d343  retn
```
