# CopyFileTransactedW

- ea: `0x180072bc0`
- end: `0x180072c88`
- name: `CopyFileTransactedW`
- size: `200`
- prototype: `BOOL __stdcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, LPBOOL pbCancel, DWORD dwCopyFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180072bc0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180072bec`
- `ntdll!RtlGetCurrentTransaction` at `0x180072bec`
- `ntdll!RtlSetCurrentTransaction` at `0x180072c15`
- `ntdll!RtlSetCurrentTransaction` at `0x180072c56`
- `ntdll!RtlSetCurrentTransaction` at `0x180072c15`
- `ntdll!RtlSetCurrentTransaction` at `0x180072c56`
- `ntdll!RtlSetLastWin32Error` at `0x180072c04`
- `ntdll!RtlSetLastWin32Error` at `0x180072c69`
- `ntdll!RtlSetLastWin32Error` at `0x180072c04`
- `ntdll!RtlSetLastWin32Error` at `0x180072c69`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180072c46`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180072c46`

## pseudocode

```c
BOOL __stdcall CopyFileTransactedW(
        LPCWSTR lpExistingFileName,
        LPCWSTR lpNewFileName,
        LPPROGRESS_ROUTINE lpProgressRoutine,
        LPVOID lpData,
        LPBOOL pbCancel,
        DWORD dwCopyFlags,
        HANDLE hTransaction)
{
  BOOL v11; // ebx

  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    RtlSetLastWin32Error(0x1A2Cu);
    return 0;
  }
  else
  {
    v11 = 0;
    if ( RtlGetCurrentTransaction() )
    {
      RtlSetLastWin32Error(0x1A45u);
    }
    else
    {
      RtlSetCurrentTransaction(hTransaction);
      v11 = CopyFileExW(lpExistingFileName, lpNewFileName, lpProgressRoutine, lpData, pbCancel, dwCopyFlags);
      RtlSetCurrentTransaction(0);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180072bc0  push    rbx
0x180072bc2  push    rsi
0x180072bc3  push    rdi
0x180072bc4  push    r12
0x180072bc6  push    r14
0x180072bc8  push    r15
0x180072bca  sub     rsp, 38h
0x180072bce  mov     rsi, r9
0x180072bd1  mov     r14, r8
0x180072bd4  mov     r15, rdx
0x180072bd7  mov     r12, rcx
0x180072bda  mov     rdi, [rsp+68h+hTransaction]
0x180072be2  lea     rax, [rdi-1]
0x180072be6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180072bea  ja      short loc_180072C64
0x180072bec  call    cs:__imp_RtlGetCurrentTransaction
0x180072bf3  nop     dword ptr [rax+rax+00h]
0x180072bf8  xor     ebx, ebx
0x180072bfa  test    rax, rax
0x180072bfd  jz      short loc_180072C12
0x180072bff  mov     ecx, 1A45h; LastError
0x180072c04  call    cs:__imp_RtlSetLastWin32Error
0x180072c0b  nop     dword ptr [rax+rax+00h]
0x180072c10  jmp     short loc_180072C77
0x180072c12  mov     rcx, rdi
0x180072c15  call    cs:__imp_RtlSetCurrentTransaction
0x180072c1c  nop     dword ptr [rax+rax+00h]
0x180072c21  nop
0x180072c22  mov     eax, [rsp+68h+dwCopyFlags]
0x180072c29  mov     [rsp+68h+var_40], eax; dwCopyFlags
0x180072c2d  mov     rax, [rsp+68h+pbCancel]
0x180072c35  mov     [rsp+68h+var_48], rax; pbCancel
0x180072c3a  mov     r9, rsi; lpData
0x180072c3d  mov     r8, r14; lpProgressRoutine
0x180072c40  mov     rdx, r15; lpNewFileName
0x180072c43  mov     rcx, r12; lpExistingFileName
0x180072c46  call    cs:__imp_CopyFileExW
0x180072c4d  nop     dword ptr [rax+rax+00h]
0x180072c52  mov     ebx, eax
0x180072c54  xor     ecx, ecx
0x180072c56  call    cs:__imp_RtlSetCurrentTransaction
0x180072c5d  nop     dword ptr [rax+rax+00h]
0x180072c62  jmp     short loc_180072C77
0x180072c64  mov     ecx, 1A2Ch; LastError
0x180072c69  call    cs:__imp_RtlSetLastWin32Error
0x180072c70  nop     dword ptr [rax+rax+00h]
0x180072c75  xor     ebx, ebx
0x180072c77  mov     eax, ebx
0x180072c79  add     rsp, 38h
0x180072c7d  pop     r15
0x180072c7f  pop     r14
0x180072c81  pop     r12
0x180072c83  pop     rdi
0x180072c84  pop     rsi
0x180072c85  pop     rbx
0x180072c86  retn
0x1800839ad  push    rbp
0x1800839af  sub     rsp, 30h
0x1800839b3  mov     rbp, rdx
0x1800839b6  xor     ecx, ecx
0x1800839b8  add     rsp, 30h
0x1800839bc  pop     rbp
0x1800839bd  jmp     cs:__imp_RtlSetCurrentTransaction
```
