# CopyFileTransactedW

- ea: `0x18006b7a0`
- end: `0x18006b843`
- name: `CopyFileTransactedW`
- size: `163`
- prototype: `BOOL __stdcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, LPBOOL pbCancel, DWORD dwCopyFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18006b7a0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006b7cc`
- `ntdll!RtlGetCurrentTransaction` at `0x18006b7cc`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b7e9`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b81e`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b7e9`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b81e`
- `ntdll!RtlSetLastWin32Error` at `0x18006b7de`
- `ntdll!RtlSetLastWin32Error` at `0x18006b82b`
- `ntdll!RtlSetLastWin32Error` at `0x18006b7de`
- `ntdll!RtlSetLastWin32Error` at `0x18006b82b`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18006b814`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18006b814`

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
0x18006b7a0  push    rbx
0x18006b7a2  push    rsi
0x18006b7a3  push    rdi
0x18006b7a4  push    r12
0x18006b7a6  push    r14
0x18006b7a8  push    r15
0x18006b7aa  sub     rsp, 38h
0x18006b7ae  mov     rsi, r9
0x18006b7b1  mov     r14, r8
0x18006b7b4  mov     r15, rdx
0x18006b7b7  mov     r12, rcx
0x18006b7ba  mov     rdi, [rsp+68h+hTransaction]
0x18006b7c2  lea     rax, [rdi-1]
0x18006b7c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b7ca  ja      short loc_18006B826
0x18006b7cc  call    cs:__imp_RtlGetCurrentTransaction
0x18006b7d2  xor     ebx, ebx
0x18006b7d4  test    rax, rax
0x18006b7d7  jz      short loc_18006B7E6
0x18006b7d9  mov     ecx, 1A45h; LastError
0x18006b7de  call    cs:__imp_RtlSetLastWin32Error
0x18006b7e4  jmp     short loc_18006B833
0x18006b7e6  mov     rcx, rdi
0x18006b7e9  call    cs:__imp_RtlSetCurrentTransaction
0x18006b7ef  nop
0x18006b7f0  mov     eax, [rsp+68h+dwCopyFlags]
0x18006b7f7  mov     [rsp+68h+var_40], eax; dwCopyFlags
0x18006b7fb  mov     rax, [rsp+68h+pbCancel]
0x18006b803  mov     [rsp+68h+var_48], rax; pbCancel
0x18006b808  mov     r9, rsi; lpData
0x18006b80b  mov     r8, r14; lpProgressRoutine
0x18006b80e  mov     rdx, r15; lpNewFileName
0x18006b811  mov     rcx, r12; lpExistingFileName
0x18006b814  call    cs:__imp_CopyFileExW
0x18006b81a  mov     ebx, eax
0x18006b81c  xor     ecx, ecx
0x18006b81e  call    cs:__imp_RtlSetCurrentTransaction
0x18006b824  jmp     short loc_18006B833
0x18006b826  mov     ecx, 1A2Ch; LastError
0x18006b82b  call    cs:__imp_RtlSetLastWin32Error
0x18006b831  xor     ebx, ebx
0x18006b833  mov     eax, ebx
0x18006b835  add     rsp, 38h
0x18006b839  pop     r15
0x18006b83b  pop     r14
0x18006b83d  pop     r12
0x18006b83f  pop     rdi
0x18006b840  pop     rsi
0x18006b841  pop     rbx
0x18006b842  retn
0x18007b871  push    rbp
0x18007b873  sub     rsp, 30h
0x18007b877  mov     rbp, rdx
0x18007b87a  xor     ecx, ecx
0x18007b87c  add     rsp, 30h
0x18007b880  pop     rbp
0x18007b881  jmp     cs:__imp_RtlSetCurrentTransaction
```
