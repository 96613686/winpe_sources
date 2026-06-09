# CreateSymbolicLinkTransactedW

- ea: `0x180059990`
- end: `0x180059a04`
- name: `CreateSymbolicLinkTransactedW`
- size: `116`
- prototype: `BOOLEAN __stdcall(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18006bd20`

## callees

- `0x180059990`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x1800599b4`
- `ntdll!RtlGetCurrentTransaction` at `0x1800599b4`
- `ntdll!RtlSetCurrentTransaction` at `0x1800599c9`
- `ntdll!RtlSetCurrentTransaction` at `0x1800599e3`
- `ntdll!RtlSetCurrentTransaction` at `0x1800599c9`
- `ntdll!RtlSetCurrentTransaction` at `0x1800599e3`
- `ntdll!RtlSetLastWin32Error` at `0x1800599f0`
- `ntdll!RtlSetLastWin32Error` at `0x1800599f0`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x1800599d9`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x1800599d9`

## pseudocode

```c
BOOLEAN __stdcall CreateSymbolicLinkTransactedW(
        LPCWSTR lpSymlinkFileName,
        LPCWSTR lpTargetFileName,
        DWORD dwFlags,
        HANDLE hTransaction)
{
  BOOLEAN SymbolicLinkW; // bl
  ULONG v9; // ecx

  SymbolicLinkW = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v9 = 6700;
    goto LABEL_6;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v9 = 6725;
LABEL_6:
    RtlSetLastWin32Error(v9);
    return SymbolicLinkW;
  }
  RtlSetCurrentTransaction(hTransaction);
  SymbolicLinkW = CreateSymbolicLinkW(lpSymlinkFileName, lpTargetFileName, dwFlags);
  RtlSetCurrentTransaction(0);
  return SymbolicLinkW;
}

```

## disassembly

```asm
0x180059990  push    rbx
0x180059992  push    rsi
0x180059993  push    rdi
0x180059994  push    r14
0x180059996  push    r15
0x180059998  sub     rsp, 20h
0x18005999c  mov     rdi, r9
0x18005999f  mov     esi, r8d
0x1800599a2  mov     r14, rdx
0x1800599a5  mov     r15, rcx
0x1800599a8  xor     bl, bl
0x1800599aa  lea     rax, [r9-1]
0x1800599ae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800599b2  ja      short loc_1800599EB
0x1800599b4  call    cs:__imp_RtlGetCurrentTransaction
0x1800599ba  test    rax, rax
0x1800599bd  jz      short loc_1800599C6
0x1800599bf  mov     ecx, 1A45h
0x1800599c4  jmp     short loc_1800599F0
0x1800599c6  mov     rcx, rdi
0x1800599c9  call    cs:__imp_RtlSetCurrentTransaction
0x1800599cf  nop
0x1800599d0  mov     r8d, esi; dwFlags
0x1800599d3  mov     rdx, r14; lpTargetFileName
0x1800599d6  mov     rcx, r15; lpSymlinkFileName
0x1800599d9  call    cs:__imp_CreateSymbolicLinkW
0x1800599df  mov     bl, al
0x1800599e1  xor     ecx, ecx
0x1800599e3  call    cs:__imp_RtlSetCurrentTransaction
0x1800599e9  jmp     short loc_1800599F6
0x1800599eb  mov     ecx, 1A2Ch; LastError
0x1800599f0  call    cs:__imp_RtlSetLastWin32Error
0x1800599f6  mov     al, bl
0x1800599f8  add     rsp, 20h
0x1800599fc  pop     r15
0x1800599fe  pop     r14
0x180059a00  pop     rdi
0x180059a01  pop     rsi
0x180059a02  pop     rbx
0x180059a03  retn
0x18007b737  push    rbp
0x18007b739  sub     rsp, 20h
0x18007b73d  mov     rbp, rdx
0x18007b740  xor     ecx, ecx
0x18007b742  add     rsp, 20h
0x18007b746  pop     rbp
0x18007b747  jmp     cs:__imp_RtlSetCurrentTransaction
```
