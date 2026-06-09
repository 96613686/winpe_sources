# WriteFileData

- ea: `0x180031f6c`
- end: `0x180032095`
- name: `WriteFileData`
- size: `297`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *, WCHAR *, void *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ed04`
- `0x1800597ac`
- `0x18005dfa0`

## callees

- `0x180006fa0`
- `0x180007fc0`
- `0x18000a600`
- `0x180031f6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003202f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003202f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032087`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180032025`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180032025`

## string_xrefs

- `0x180031faf`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180032044`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003205f`: `ReadFile`

## pseudocode

```c
__int64 __fastcall WriteFileData(
        __int64 a1,
        __int64 a2,
        WCHAR *a3,
        WCHAR *a4,
        void *a5,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite)
{
  unsigned int File; // ebx
  const UCHAR *v8; // r9
  const UCHAR *v9; // rax
  bool v10; // zf
  signed int LastError; // eax
  const char *v12; // r9
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-38h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-38h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-18h] BYREF
  HANDLE hFile[2]; // [rsp+48h] [rbp-10h] BYREF

  NumberOfBytesWritten = 0;
  hFile[0] = (HANDLE)-1LL;
  File = GetFile(a1, a2, a3, a4, 0, a5, hFile);
  if ( File )
  {
    v8 = "";
    while ( 1 )
    {
      v9 = v8--;
      v10 = *v8 == 92;
      if ( *v8 == 92 )
        break;
      if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v10 = *v8 == 92;
        break;
      }
    }
    if ( v10 )
      v8 = v9;
    LODWORD(lpOverlapped) = 2201;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", File, v8, lpOverlapped, "GetFile", &Class);
  }
  else if ( WriteFile(hFile[0], lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    File = 0;
  }
  else
  {
    LastError = GetLastError();
    File = LastError;
    if ( LastError > 0 )
      File = (unsigned __int16)LastError | 0xC0070000;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(lpOverlappeda) = 2212;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", File, v12, lpOverlappeda, "ReadFile", &Class);
  }
  if ( hFile[0] != (HANDLE)-1LL )
    CloseHandle(hFile[0]);
  return File;
}

```

## disassembly

```asm
0x180031f6c  mov     r11, rsp
0x180031f6f  push    rbx
0x180031f70  sub     rsp, 50h
0x180031f74  lea     rax, [r11-10h]
0x180031f78  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180031f80  mov     [r11-28h], rax
0x180031f84  mov     rax, [rsp+58h+arg_20]
0x180031f8c  mov     [r11-30h], rax
0x180031f90  mov     byte ptr [rsp+58h+lpOverlapped], 0
0x180031f95  mov     qword ptr [r11-10h], 0FFFFFFFFFFFFFFFFh
0x180031f9d  call    GetFile
0x180031fa2  mov     ebx, eax
0x180031fa4  test    eax, eax
0x180031fa6  jz      short loc_180032002
0x180031fa8  lea     r9, pbInput+24h; ""
0x180031faf  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180031fb6  mov     rax, r9
0x180031fb9  dec     r9
0x180031fbc  cmp     byte ptr [r9], 5Ch ; '\'
0x180031fc0  jz      short loc_180031FCB
0x180031fc2  cmp     r9, rcx
0x180031fc5  ja      short loc_180031FB6
0x180031fc7  cmp     byte ptr [r9], 5Ch ; '\'
0x180031fcb  cmovz   r9, rax
0x180031fcf  lea     rax, Class
0x180031fd6  mov     [rsp+58h+var_28], rax
0x180031fdb  lea     rax, aGetfile; "GetFile"
0x180031fe2  mov     [rsp+58h+var_30], rax
0x180031fe7  mov     dword ptr [rsp+58h+lpOverlapped], 899h
0x180031fef  mov     r8d, ebx
0x180031ff2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180031ff9  xor     ecx, ecx
0x180031ffb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180032000  jmp     short loc_18003207A
0x180032002  mov     r8d, [rsp+58h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18003200a  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003200f  mov     rdx, [rsp+58h+lpBuffer]; lpBuffer
0x180032017  mov     rcx, [rsp+58h+hFile]; hFile
0x18003201c  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180032025  call    cs:__imp_WriteFile
0x18003202b  test    eax, eax
0x18003202d  jnz     short loc_180032078
0x18003202f  call    cs:__imp_GetLastError
0x180032035  mov     ebx, eax
0x180032037  test    eax, eax
0x180032039  jle     short loc_180032044
0x18003203b  movzx   ebx, ax
0x18003203e  or      ebx, 0C0070000h
0x180032044  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003204b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032050  mov     r9, rax
0x180032053  lea     rax, Class
0x18003205a  mov     [rsp+58h+var_28], rax
0x18003205f  lea     rax, aReadfile; "ReadFile"
0x180032066  mov     [rsp+58h+var_30], rax
0x18003206b  mov     dword ptr [rsp+58h+lpOverlapped], 8A4h
0x180032073  jmp     loc_180031FEF
0x180032078  xor     ebx, ebx
0x18003207a  cmp     [rsp+58h+hFile], 0FFFFFFFFFFFFFFFFh
0x180032080  jz      short loc_18003208D
0x180032082  mov     rcx, [rsp+58h+hFile]; hObject
0x180032087  call    cs:__imp_CloseHandle
0x18003208d  mov     eax, ebx
0x18003208f  add     rsp, 50h
0x180032093  pop     rbx
0x180032094  retn
```
