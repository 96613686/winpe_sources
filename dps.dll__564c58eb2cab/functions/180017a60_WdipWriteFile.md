# WdipWriteFile

- ea: `0x180017a60`
- end: `0x180017b17`
- name: `WdipWriteFile`
- size: `183`
- prototype: `__int64 __fastcall(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToWrite, _DWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013e68`
- `0x1800141a4`
- `0x1800180f4`
- `0x180018848`

## callees

- `0x180009090`
- `0x180017a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017aa4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017aa4`

## string_xrefs

- `0x180017af0`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x180017ae9`: `WdipWriteFile`

## pseudocode

```c
__int64 __fastcall WdipWriteFile(HANDLE hFile, char *lpBuffer, DWORD nNumberOfBytesToWrite, _DWORD *a4)
{
  unsigned int v8; // ebx
  signed int LastError; // eax
  __int64 v10; // rax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  *a4 = 0;
  while ( 1 )
  {
    if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      v8 = 0;
      goto LABEL_7;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
      break;
LABEL_7:
    v10 = NumberOfBytesWritten;
    *a4 += NumberOfBytesWritten;
    nNumberOfBytesToWrite -= v10;
    if ( !nNumberOfBytesToWrite )
      return v8;
    lpBuffer += v10;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
    (int)L"WdipWriteFile",
    958,
    (int)L"Error = %d",
    v8);
  return v8;
}

```

## disassembly

```asm
0x180017a60  mov     [rsp+arg_0], rbx
0x180017a65  mov     [rsp+arg_10], rbp
0x180017a6a  push    rsi
0x180017a6b  push    rdi
0x180017a6c  push    r14
0x180017a6e  sub     rsp, 30h
0x180017a72  mov     r14, r9
0x180017a75  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180017a7d  mov     edi, r8d
0x180017a80  mov     dword ptr [r9], 0
0x180017a87  mov     rsi, rdx
0x180017a8a  mov     rbp, rcx
0x180017a8d  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180017a92  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180017a9b  mov     r8d, edi; nNumberOfBytesToWrite
0x180017a9e  mov     rdx, rsi; lpBuffer
0x180017aa1  mov     rcx, rbp; hFile
0x180017aa4  call    cs:__imp_WriteFile
0x180017aaa  test    eax, eax
0x180017aac  jz      short loc_180017AB2
0x180017aae  xor     ebx, ebx
0x180017ab0  jmp     short loc_180017ACB
0x180017ab2  call    cs:__imp_GetLastError
0x180017ab8  mov     ebx, eax
0x180017aba  test    eax, eax
0x180017abc  jle     short loc_180017AC7
0x180017abe  movzx   ebx, ax
0x180017ac1  or      ebx, 80070000h
0x180017ac7  test    ebx, ebx
0x180017ac9  js      short loc_180017ADB
0x180017acb  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x180017acf  add     [r14], eax
0x180017ad2  sub     edi, eax
0x180017ad4  jz      short loc_180017B02
0x180017ad6  add     rsi, rax
0x180017ad9  jmp     short loc_180017A8D
0x180017adb  movzx   ecx, bx
0x180017ade  lea     r9, aErrorD; "Error = %d"
0x180017ae5  mov     dword ptr [rsp+48h+lpOverlapped], ecx; Args
0x180017ae9  lea     rdx, aWdipwritefile; "WdipWriteFile"
0x180017af0  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180017af7  mov     r8d, 3BEh; int
0x180017afd  call    WdipTraceError
0x180017b02  mov     rbp, [rsp+48h+arg_10]
0x180017b07  mov     eax, ebx
0x180017b09  mov     rbx, [rsp+48h+arg_0]
0x180017b0e  add     rsp, 30h
0x180017b12  pop     r14
0x180017b14  pop     rdi
0x180017b15  pop     rsi
0x180017b16  retn
```
