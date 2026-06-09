# PuCloseDbgPrintFile

- ea: `0x18000244c`
- end: `0x180002523`
- name: `PuCloseDbgPrintFile`
- size: `215`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000290c`

## callees

- `0x18000244c`
- `0x180002de0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800024d7`
- `msvcrt!sprintf_s` at `0x1800024d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024e8`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000248a`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000248a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000249d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000249d`

## pseudocode

```c
__int64 __fastcall PuCloseDbgPrintFile(__int64 a1)
{
  DWORD LastError; // edi
  void *v3; // rcx
  char Buffer[1024]; // [rsp+30h] [rbp-418h] BYREF

  if ( a1 )
  {
    v3 = *(void **)(a1 + 624);
    LastError = 0;
    if ( v3 != (void *)-1LL )
    {
      FlushFileBuffers(v3);
      if ( !CloseHandle(*(HANDLE *)(a1 + 624)) )
      {
        LastError = GetLastError();
        sprintf_s(
          Buffer,
          0x400u,
          "CloseDbgPrintFile() : CloseHandle( %p) failed. Error = %d\n",
          *(const void **)(a1 + 624),
          LastError);
        OutputDebugStringA(Buffer);
      }
      *(_QWORD *)(a1 + 624) = -1;
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000244c  mov     [rsp+arg_8], rbx
0x180002451  push    rdi
0x180002452  sub     rsp, 440h
0x180002459  mov     rax, cs:__security_cookie
0x180002460  xor     rax, rsp
0x180002463  mov     [rsp+448h+var_18], rax
0x18000246b  mov     rbx, rcx
0x18000246e  test    rcx, rcx
0x180002471  jnz     short loc_18000247B
0x180002473  lea     edi, [rcx+57h]
0x180002476  jmp     loc_1800024FF
0x18000247b  mov     rcx, [rcx+270h]; hFile
0x180002482  xor     edi, edi
0x180002484  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002488  jz      short loc_1800024FF
0x18000248a  call    cs:__imp_FlushFileBuffers
0x180002491  nop     dword ptr [rax+rax+00h]
0x180002496  mov     rcx, [rbx+270h]; hObject
0x18000249d  call    cs:__imp_CloseHandle
0x1800024a4  nop     dword ptr [rax+rax+00h]
0x1800024a9  test    eax, eax
0x1800024ab  jnz     short loc_1800024F4
0x1800024ad  call    cs:__imp_GetLastError
0x1800024b4  nop     dword ptr [rax+rax+00h]
0x1800024b9  mov     r9, [rbx+270h]
0x1800024c0  lea     r8, aClosedbgprintf; "CloseDbgPrintFile() : CloseHandle( %p) "...
0x1800024c7  mov     edx, 400h; BufferCount
0x1800024cc  mov     [rsp+448h+var_428], eax
0x1800024d0  lea     rcx, [rsp+448h+Buffer]; Buffer
0x1800024d5  mov     edi, eax
0x1800024d7  call    cs:__imp_sprintf_s
0x1800024de  nop     dword ptr [rax+rax+00h]
0x1800024e3  lea     rcx, [rsp+448h+Buffer]; lpOutputString
0x1800024e8  call    cs:__imp_OutputDebugStringA
0x1800024ef  nop     dword ptr [rax+rax+00h]
0x1800024f4  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh
0x1800024ff  mov     eax, edi
0x180002501  mov     rcx, [rsp+448h+var_18]
0x180002509  xor     rcx, rsp; StackCookie
0x18000250c  call    __security_check_cookie
0x180002511  mov     rbx, [rsp+448h+arg_8]
0x180002519  add     rsp, 440h
0x180002520  pop     rdi
0x180002521  retn
```
