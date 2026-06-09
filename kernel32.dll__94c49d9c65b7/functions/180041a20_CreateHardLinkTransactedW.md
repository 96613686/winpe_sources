# CreateHardLinkTransactedW

- ea: `0x180041a20`
- end: `0x180041a9c`
- name: `CreateHardLinkTransactedW`
- size: `124`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, LPCWSTR lpExistingFileName, LPSECURITY_ATTRIBUTES lpSecurityAttributes, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180061a40`

## callees

- `0x180041a20`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180041a5d`
- `ntdll!RtlGetCurrentTransaction` at `0x180041a5d`
- `ntdll!RtlSetCurrentTransaction` at `0x180041a7a`
- `ntdll!RtlSetCurrentTransaction` at `0x180041a94`
- `ntdll!RtlSetCurrentTransaction` at `0x180041a7a`
- `ntdll!RtlSetCurrentTransaction` at `0x180041a94`
- `ntdll!RtlSetCurrentTransaction` at `0x18007b2ed`
- `ntdll!RtlSetLastWin32Error` at `0x180041a47`
- `ntdll!RtlSetLastWin32Error` at `0x180041a6f`
- `ntdll!RtlSetLastWin32Error` at `0x180041a47`
- `ntdll!RtlSetLastWin32Error` at `0x180041a6f`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180041a8a`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180041a8a`

## pseudocode

```c
BOOL __stdcall CreateHardLinkTransactedW(
        LPCWSTR lpFileName,
        LPCWSTR lpExistingFileName,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        HANDLE hTransaction)
{
  BOOL HardLinkW; // ebx

  if ( (char *)hTransaction - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    HardLinkW = 0;
    if ( RtlGetCurrentTransaction() )
    {
      RtlSetLastWin32Error(0x1A45u);
    }
    else
    {
      RtlSetCurrentTransaction(hTransaction);
      HardLinkW = CreateHardLinkW(lpFileName, lpExistingFileName, lpSecurityAttributes);
      RtlSetCurrentTransaction(0);
    }
  }
  else
  {
    RtlSetLastWin32Error(0x1A2Cu);
    return 0;
  }
  return HardLinkW;
}

```

## disassembly

```asm
0x180041a20  push    rbx
0x180041a22  push    rsi
0x180041a23  push    rdi
0x180041a24  push    r14
0x180041a26  push    r15
0x180041a28  sub     rsp, 20h
0x180041a2c  mov     rdi, r9
0x180041a2f  mov     rsi, r8
0x180041a32  mov     r14, rdx
0x180041a35  mov     r15, rcx
0x180041a38  lea     rax, [r9-1]
0x180041a3c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041a40  jbe     short loc_180041A5D
0x180041a42  mov     ecx, 1A2Ch; LastError
0x180041a47  call    cs:__imp_RtlSetLastWin32Error
0x180041a4d  xor     ebx, ebx
0x180041a4f  mov     eax, ebx
0x180041a51  add     rsp, 20h
0x180041a55  pop     r15
0x180041a57  pop     r14
0x180041a59  pop     rdi
0x180041a5a  pop     rsi
0x180041a5b  pop     rbx
0x180041a5c  retn
0x180041a5d  call    cs:__imp_RtlGetCurrentTransaction
0x180041a63  xor     ebx, ebx
0x180041a65  test    rax, rax
0x180041a68  jz      short loc_180041A77
0x180041a6a  mov     ecx, 1A45h; LastError
0x180041a6f  call    cs:__imp_RtlSetLastWin32Error
0x180041a75  jmp     short loc_180041A4F
0x180041a77  mov     rcx, rdi
0x180041a7a  call    cs:__imp_RtlSetCurrentTransaction
0x180041a80  nop
0x180041a81  mov     r8, rsi; lpSecurityAttributes
0x180041a84  mov     rdx, r14; lpExistingFileName
0x180041a87  mov     rcx, r15; lpFileName
0x180041a8a  call    cs:__imp_CreateHardLinkW
0x180041a90  mov     ebx, eax
0x180041a92  xor     ecx, ecx
0x180041a94  call    cs:__imp_RtlSetCurrentTransaction
0x180041a9a  jmp     short loc_180041A4F
0x18007b2dd  push    rbp
0x18007b2df  sub     rsp, 20h
0x18007b2e3  mov     rbp, rdx
0x18007b2e6  xor     ecx, ecx
0x18007b2e8  add     rsp, 20h
0x18007b2ec  pop     rbp
0x18007b2ed  jmp     cs:__imp_RtlSetCurrentTransaction
```
