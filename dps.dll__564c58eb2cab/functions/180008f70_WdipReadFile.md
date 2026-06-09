# WdipReadFile

- ea: `0x180008f70`
- end: `0x18000903e`
- name: `WdipReadFile`
- size: `206`
- prototype: `__int64 __fastcall(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToRead, _DWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013214`
- `0x1800137a8`
- `0x180017b20`
- `0x180018680`

## callees

- `0x180008f70`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fbe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008fb4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008fb4`

## string_xrefs

- `0x18000901d`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x180009016`: `WdipReadFile`

## pseudocode

```c
__int64 __fastcall WdipReadFile(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToRead, _DWORD *a4)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  *a4 = 0;
  while ( 1 )
  {
    if ( !ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
          (int)L"WdipReadFile",
          1013,
          (int)L"Error = %d",
          v9);
        return v9;
      }
    }
    v10 = NumberOfBytesRead;
    if ( !NumberOfBytesRead )
      break;
    *a4 += NumberOfBytesRead;
    v9 = 0;
    nNumberOfBytesToRead -= v10;
    if ( !nNumberOfBytesToRead )
      return v9;
    lpBuffer += v10;
  }
  v9 = -2147467259;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
    (int)L"WdipReadFile",
    1016,
    (int)L"Error = %d",
    5);
  return v9;
}

```

## disassembly

```asm
0x180008f70  mov     [rsp+arg_0], rbx
0x180008f75  mov     [rsp+arg_10], rbp
0x180008f7a  push    rsi
0x180008f7b  push    rdi
0x180008f7c  push    r14
0x180008f7e  sub     rsp, 30h
0x180008f82  mov     r14, r9
0x180008f85  mov     [rsp+48h+NumberOfBytesRead], 0
0x180008f8d  mov     edi, r8d
0x180008f90  mov     dword ptr [r9], 0
0x180008f97  mov     rsi, rdx
0x180008f9a  mov     rbp, rcx
0x180008f9d  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008fa2  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180008fab  mov     r8d, edi; nNumberOfBytesToRead
0x180008fae  mov     rdx, rsi; lpBuffer
0x180008fb1  mov     rcx, rbp; hFile
0x180008fb4  call    cs:__imp_ReadFile
0x180008fba  test    eax, eax
0x180008fbc  jnz     short loc_180008FD7
0x180008fbe  call    cs:__imp_GetLastError
0x180008fc4  mov     ebx, eax
0x180008fc6  test    eax, eax
0x180008fc8  jle     short loc_180008FD3
0x180008fca  movzx   ebx, ax
0x180008fcd  or      ebx, 80070000h
0x180008fd3  test    ebx, ebx
0x180008fd5  js      short loc_180008FED
0x180008fd7  mov     eax, [rsp+48h+NumberOfBytesRead]
0x180008fdb  test    eax, eax
0x180008fdd  jz      short loc_180008FFC
0x180008fdf  add     [r14], eax
0x180008fe2  xor     ebx, ebx
0x180008fe4  sub     edi, eax
0x180008fe6  jz      short loc_180009029
0x180008fe8  add     rsi, rax
0x180008feb  jmp     short loc_180008F9D
0x180008fed  movzx   eax, bx
0x180008ff0  mov     r8d, 3F5h
0x180008ff6  mov     dword ptr [rsp+48h+lpOverlapped], eax
0x180008ffa  jmp     short loc_18000900F
0x180008ffc  mov     ebx, 80004005h
0x180009001  mov     dword ptr [rsp+48h+lpOverlapped], 4005h; Args
0x180009009  mov     r8d, 3F8h; int
0x18000900f  lea     r9, aErrorD; "Error = %d"
0x180009016  lea     rdx, aWdipreadfile; "WdipReadFile"
0x18000901d  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009024  call    WdipTraceError
0x180009029  mov     rbp, [rsp+48h+arg_10]
0x18000902e  mov     eax, ebx
0x180009030  mov     rbx, [rsp+48h+arg_0]
0x180009035  add     rsp, 30h
0x180009039  pop     r14
0x18000903b  pop     rdi
0x18000903c  pop     rsi
0x18000903d  retn
```
