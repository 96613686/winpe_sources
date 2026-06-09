# rasWriteFile

- ea: `0x18003b31c`
- end: `0x18003b3e1`
- name: `rasWriteFile`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005af0`

## callees

- `0x18003b31c`
- `0x18003b3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b383`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b337`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b39d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b3ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b337`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b39d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b3ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b375`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b375`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18003b390`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18003b390`

## pseudocode

```c
BOOL __fastcall rasWriteFile(__int64 a1)
{
  void *v2; // rcx
  BOOL result; // eax
  int v4; // ebp
  HANDLE FileW; // rax
  void *v6; // rdi
  _QWORD *i; // rsi

  v2 = *(void **)(a1 + 24);
  if ( v2 != (void *)-1LL )
  {
    result = CloseHandle(v2);
    if ( !result )
      return result;
    *(_QWORD *)(a1 + 24) = -1;
  }
  v4 = 1;
  FileW = CreateFileW((LPCWSTR)(a1 + 52), 0xC0000000, 1u, 0, 2u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    GetLastError();
  }
  else
  {
    if ( GetFileType(FileW) == 1 )
    {
      for ( i = **(_QWORD ***)a1; i != *(_QWORD **)a1; i = (_QWORD *)*i )
      {
        if ( !(unsigned int)rasPutFileLine(v6) )
        {
          v4 = 0;
          break;
        }
      }
      CloseHandle(v6);
      result = v4;
      goto LABEL_15;
    }
    CloseHandle(v6);
  }
  result = 0;
LABEL_15:
  *(_QWORD *)(a1 + 24) = -1;
  return result;
}

```

## disassembly

```asm
0x18003b31c  push    rbx
0x18003b31e  push    rbp
0x18003b31f  push    rsi
0x18003b320  push    rdi
0x18003b321  push    r14
0x18003b323  sub     rsp, 40h
0x18003b327  mov     rbx, rcx
0x18003b32a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003b32e  mov     rcx, [rcx+18h]; hObject
0x18003b332  cmp     rcx, r14
0x18003b335  jz      short loc_18003B349
0x18003b337  call    cs:__imp_CloseHandle
0x18003b33d  test    eax, eax
0x18003b33f  jz      loc_18003B3D6
0x18003b345  mov     [rbx+18h], r14
0x18003b349  xor     r9d, r9d; lpSecurityAttributes
0x18003b34c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18003b355  lea     rcx, [rbx+34h]; lpFileName
0x18003b359  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003b361  mov     edx, 0C0000000h; dwDesiredAccess
0x18003b366  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18003b36e  lea     ebp, [r9+1]
0x18003b372  mov     r8d, ebp; dwShareMode
0x18003b375  call    cs:__imp_CreateFileW
0x18003b37b  mov     rdi, rax
0x18003b37e  cmp     rax, r14
0x18003b381  jnz     short loc_18003B38D
0x18003b383  call    cs:__imp_GetLastError
0x18003b389  xor     eax, eax
0x18003b38b  jmp     short loc_18003B3D2
0x18003b38d  mov     rcx, rdi; hFile
0x18003b390  call    cs:__imp_GetFileType
0x18003b396  cmp     eax, ebp
0x18003b398  jz      short loc_18003B3A5
0x18003b39a  mov     rcx, rdi; hObject
0x18003b39d  call    cs:__imp_CloseHandle
0x18003b3a3  jmp     short loc_18003B389
0x18003b3a5  mov     rax, [rbx]
0x18003b3a8  mov     rsi, [rax]
0x18003b3ab  cmp     rsi, [rbx]
0x18003b3ae  jz      short loc_18003B3C7
0x18003b3b0  mov     rdx, [rsi+10h]
0x18003b3b4  mov     rcx, rdi; hFile
0x18003b3b7  call    rasPutFileLine
0x18003b3bc  test    eax, eax
0x18003b3be  jz      short loc_18003B3C5
0x18003b3c0  mov     rsi, [rsi]
0x18003b3c3  jmp     short loc_18003B3AB
0x18003b3c5  xor     ebp, ebp
0x18003b3c7  mov     rcx, rdi; hObject
0x18003b3ca  call    cs:__imp_CloseHandle
0x18003b3d0  mov     eax, ebp
0x18003b3d2  mov     [rbx+18h], r14
0x18003b3d6  add     rsp, 40h
0x18003b3da  pop     r14
0x18003b3dc  pop     rdi
0x18003b3dd  pop     rsi
0x18003b3de  pop     rbp
0x18003b3df  pop     rbx
0x18003b3e0  retn
```
