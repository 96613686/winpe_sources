# DeleteFileTransactedW

- ea: `0x1800419a0`
- end: `0x180041a0f`
- name: `DeleteFileTransactedW`
- size: `111`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18006bde0`

## callees

- `0x1800419a0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x1800419c1`
- `ntdll!RtlGetCurrentTransaction` at `0x1800419c1`
- `ntdll!RtlSetCurrentTransaction` at `0x1800419cf`
- `ntdll!RtlSetCurrentTransaction` at `0x1800419e3`
- `ntdll!RtlSetCurrentTransaction` at `0x1800419cf`
- `ntdll!RtlSetCurrentTransaction` at `0x1800419e3`
- `ntdll!RtlSetCurrentTransaction` at `0x18007b2cf`
- `ntdll!RtlSetLastWin32Error` at `0x180041a00`
- `ntdll!RtlSetLastWin32Error` at `0x180041a00`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800419d9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800419d9`

## pseudocode

```c
BOOL __stdcall DeleteFileTransactedW(LPCWSTR lpFileName, HANDLE hTransaction)
{
  BOOL v4; // ebx
  ULONG v6; // ecx

  v4 = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = 6700;
LABEL_6:
    RtlSetLastWin32Error(v6);
    return v4;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v6 = 6725;
    goto LABEL_6;
  }
  RtlSetCurrentTransaction(hTransaction);
  v4 = DeleteFileW(lpFileName);
  RtlSetCurrentTransaction(0);
  return v4;
}

```

## disassembly

```asm
0x1800419a0  mov     [rsp+arg_0], rbx
0x1800419a5  mov     [rsp+arg_8], rsi
0x1800419aa  push    rdi
0x1800419ab  sub     rsp, 20h
0x1800419af  mov     rdi, rdx
0x1800419b2  mov     rsi, rcx
0x1800419b5  xor     ebx, ebx
0x1800419b7  lea     rax, [rdx-1]
0x1800419bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800419bf  ja      short loc_1800419FB
0x1800419c1  call    cs:__imp_RtlGetCurrentTransaction
0x1800419c7  test    rax, rax
0x1800419ca  jnz     short loc_180041A08
0x1800419cc  mov     rcx, rdi
0x1800419cf  call    cs:__imp_RtlSetCurrentTransaction
0x1800419d5  nop
0x1800419d6  mov     rcx, rsi; lpFileName
0x1800419d9  call    cs:__imp_DeleteFileW
0x1800419df  mov     ebx, eax
0x1800419e1  xor     ecx, ecx
0x1800419e3  call    cs:__imp_RtlSetCurrentTransaction
0x1800419e9  mov     eax, ebx
0x1800419eb  mov     rbx, [rsp+28h+arg_0]
0x1800419f0  mov     rsi, [rsp+28h+arg_8]
0x1800419f5  add     rsp, 20h
0x1800419f9  pop     rdi
0x1800419fa  retn
0x1800419fb  mov     ecx, 1A2Ch; LastError
0x180041a00  call    cs:__imp_RtlSetLastWin32Error
0x180041a06  jmp     short loc_1800419E9
0x180041a08  mov     ecx, 1A45h
0x180041a0d  jmp     short loc_180041A00
0x18007b2bf  push    rbp
0x18007b2c1  sub     rsp, 20h
0x18007b2c5  mov     rbp, rdx
0x18007b2c8  xor     ecx, ecx
0x18007b2ca  add     rsp, 20h
0x18007b2ce  pop     rbp
0x18007b2cf  jmp     cs:__imp_RtlSetCurrentTransaction
```
