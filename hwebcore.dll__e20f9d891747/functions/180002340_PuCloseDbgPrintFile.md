# PuCloseDbgPrintFile

- ea: `0x180002340`
- end: `0x1800023f5`
- name: `PuCloseDbgPrintFile`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002788`

## callees

- `0x180002340`
- `0x180002be0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800023b6`
- `msvcrt!sprintf_s` at `0x1800023b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023c1`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000237b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000237b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002388`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002388`

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
0x180002340  mov     [rsp+arg_8], rbx
0x180002345  push    rdi
0x180002346  sub     rsp, 440h
0x18000234d  mov     rax, cs:__security_cookie
0x180002354  xor     rax, rsp
0x180002357  mov     [rsp+448h+var_18], rax
0x18000235f  mov     rbx, rcx
0x180002362  test    rcx, rcx
0x180002365  jnz     short loc_18000236C
0x180002367  lea     edi, [rcx+57h]
0x18000236a  jmp     short loc_1800023D2
0x18000236c  mov     rcx, [rcx+270h]; hFile
0x180002373  xor     edi, edi
0x180002375  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002379  jz      short loc_1800023D2
0x18000237b  call    cs:__imp_FlushFileBuffers
0x180002381  mov     rcx, [rbx+270h]; hObject
0x180002388  call    cs:__imp_CloseHandle
0x18000238e  test    eax, eax
0x180002390  jnz     short loc_1800023C7
0x180002392  call    cs:__imp_GetLastError
0x180002398  mov     r9, [rbx+270h]
0x18000239f  lea     r8, aClosedbgprintf; "CloseDbgPrintFile() : CloseHandle( %p) "...
0x1800023a6  mov     edx, 400h; BufferCount
0x1800023ab  mov     [rsp+448h+var_428], eax
0x1800023af  lea     rcx, [rsp+448h+Buffer]; Buffer
0x1800023b4  mov     edi, eax
0x1800023b6  call    cs:__imp_sprintf_s
0x1800023bc  lea     rcx, [rsp+448h+Buffer]; lpOutputString
0x1800023c1  call    cs:__imp_OutputDebugStringA
0x1800023c7  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh
0x1800023d2  mov     eax, edi
0x1800023d4  mov     rcx, [rsp+448h+var_18]
0x1800023dc  xor     rcx, rsp; StackCookie
0x1800023df  call    __security_check_cookie
0x1800023e4  mov     rbx, [rsp+448h+arg_8]
0x1800023ec  add     rsp, 440h
0x1800023f3  pop     rdi
0x1800023f4  retn
```
