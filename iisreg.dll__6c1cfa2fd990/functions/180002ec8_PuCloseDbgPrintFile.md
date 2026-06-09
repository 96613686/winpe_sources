# PuCloseDbgPrintFile

- ea: `0x180002ec8`
- end: `0x180002f7d`
- name: `PuCloseDbgPrintFile`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f84`

## callees

- `0x180002ec8`
- `0x180003650`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180002f3e`
- `msvcrt!sprintf_s` at `0x180002f3e`
- `KERNEL32!GetLastError` at `0x180002f1a`
- `KERNEL32!GetLastError` at `0x180002f1a`
- `KERNEL32!CloseHandle` at `0x180002f10`
- `KERNEL32!CloseHandle` at `0x180002f10`
- `KERNEL32!FlushFileBuffers` at `0x180002f03`
- `KERNEL32!FlushFileBuffers` at `0x180002f03`
- `KERNEL32!OutputDebugStringA` at `0x180002f49`
- `KERNEL32!OutputDebugStringA` at `0x180002f49`

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
0x180002ec8  mov     [rsp+arg_8], rbx
0x180002ecd  push    rdi
0x180002ece  sub     rsp, 440h
0x180002ed5  mov     rax, cs:__security_cookie
0x180002edc  xor     rax, rsp
0x180002edf  mov     [rsp+448h+var_18], rax
0x180002ee7  mov     rbx, rcx
0x180002eea  test    rcx, rcx
0x180002eed  jnz     short loc_180002EF4
0x180002eef  lea     edi, [rcx+57h]
0x180002ef2  jmp     short loc_180002F5A
0x180002ef4  mov     rcx, [rcx+270h]; hFile
0x180002efb  xor     edi, edi
0x180002efd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002f01  jz      short loc_180002F5A
0x180002f03  call    cs:__imp_FlushFileBuffers
0x180002f09  mov     rcx, [rbx+270h]; hObject
0x180002f10  call    cs:__imp_CloseHandle
0x180002f16  test    eax, eax
0x180002f18  jnz     short loc_180002F4F
0x180002f1a  call    cs:__imp_GetLastError
0x180002f20  mov     r9, [rbx+270h]
0x180002f27  lea     r8, Format; "CloseDbgPrintFile() : CloseHandle( %p) "...
0x180002f2e  mov     edx, 400h; BufferCount
0x180002f33  mov     [rsp+448h+var_428], eax
0x180002f37  lea     rcx, [rsp+448h+Buffer]; Buffer
0x180002f3c  mov     edi, eax
0x180002f3e  call    cs:__imp_sprintf_s
0x180002f44  lea     rcx, [rsp+448h+Buffer]; lpOutputString
0x180002f49  call    cs:__imp_OutputDebugStringA
0x180002f4f  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh
0x180002f5a  mov     eax, edi
0x180002f5c  mov     rcx, [rsp+448h+var_18]
0x180002f64  xor     rcx, rsp; StackCookie
0x180002f67  call    __security_check_cookie
0x180002f6c  mov     rbx, [rsp+448h+arg_8]
0x180002f74  add     rsp, 440h
0x180002f7b  pop     rdi
0x180002f7c  retn
```
