# CreateDirectoryTransactedW

- ea: `0x18006bab0`
- end: `0x18006bb37`
- name: `CreateDirectoryTransactedW`
- size: `135`
- prototype: `BOOL __stdcall(LPCWSTR lpTemplateDirectory, LPCWSTR lpNewDirectory, LPSECURITY_ATTRIBUTES lpSecurityAttributes, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005dd20`

## callees

- `0x18006bab0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006bad4`
- `ntdll!RtlGetCurrentTransaction` at `0x18006bad4`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bae9`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bb16`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bae9`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bb16`
- `ntdll!RtlSetLastWin32Error` at `0x18006bb23`
- `ntdll!RtlSetLastWin32Error` at `0x18006bb23`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006bb0c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006bb0c`
- `api-ms-win-core-file-l2-1-0!CreateDirectoryExW` at `0x18006bafe`
- `api-ms-win-core-file-l2-1-0!CreateDirectoryExW` at `0x18006bafe`

## pseudocode

```c
BOOL __stdcall CreateDirectoryTransactedW(
        LPCWSTR lpTemplateDirectory,
        LPCWSTR lpNewDirectory,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        HANDLE hTransaction)
{
  BOOL v8; // ebx
  ULONG v9; // ecx
  BOOL Directory; // eax

  v8 = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v9 = 6700;
    goto LABEL_9;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v9 = 6725;
LABEL_9:
    RtlSetLastWin32Error(v9);
    return v8;
  }
  RtlSetCurrentTransaction(hTransaction);
  if ( lpTemplateDirectory )
    Directory = CreateDirectoryExW(lpTemplateDirectory, lpNewDirectory, lpSecurityAttributes);
  else
    Directory = CreateDirectoryW(lpNewDirectory, lpSecurityAttributes);
  v8 = Directory;
  RtlSetCurrentTransaction(0);
  return v8;
}

```

## disassembly

```asm
0x18006bab0  push    rbx
0x18006bab2  push    rsi
0x18006bab3  push    rdi
0x18006bab4  push    r14
0x18006bab6  push    r15
0x18006bab8  sub     rsp, 20h
0x18006babc  mov     r15, r9
0x18006babf  mov     rsi, r8
0x18006bac2  mov     r14, rdx
0x18006bac5  mov     rdi, rcx
0x18006bac8  xor     ebx, ebx
0x18006baca  lea     rax, [r9-1]
0x18006bace  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006bad2  ja      short loc_18006BB1E
0x18006bad4  call    cs:__imp_RtlGetCurrentTransaction
0x18006bada  test    rax, rax
0x18006badd  jz      short loc_18006BAE6
0x18006badf  mov     ecx, 1A45h
0x18006bae4  jmp     short loc_18006BB23
0x18006bae6  mov     rcx, r15
0x18006bae9  call    cs:__imp_RtlSetCurrentTransaction
0x18006baef  nop
0x18006baf0  test    rdi, rdi
0x18006baf3  jz      short loc_18006BB06
0x18006baf5  mov     r8, rsi; lpSecurityAttributes
0x18006baf8  mov     rdx, r14; lpNewDirectory
0x18006bafb  mov     rcx, rdi; lpTemplateDirectory
0x18006bafe  call    cs:__imp_CreateDirectoryExW
0x18006bb04  jmp     short loc_18006BB12
0x18006bb06  mov     rdx, rsi; lpSecurityAttributes
0x18006bb09  mov     rcx, r14; lpPathName
0x18006bb0c  call    cs:__imp_CreateDirectoryW
0x18006bb12  mov     ebx, eax
0x18006bb14  xor     ecx, ecx
0x18006bb16  call    cs:__imp_RtlSetCurrentTransaction
0x18006bb1c  jmp     short loc_18006BB29
0x18006bb1e  mov     ecx, 1A2Ch; LastError
0x18006bb23  call    cs:__imp_RtlSetLastWin32Error
0x18006bb29  mov     eax, ebx
0x18006bb2b  add     rsp, 20h
0x18006bb2f  pop     r15
0x18006bb31  pop     r14
0x18006bb33  pop     rdi
0x18006bb34  pop     rsi
0x18006bb35  pop     rbx
0x18006bb36  retn
0x18007b737  push    rbp
0x18007b739  sub     rsp, 20h
0x18007b73d  mov     rbp, rdx
0x18007b740  xor     ecx, ecx
0x18007b742  add     rsp, 20h
0x18007b746  pop     rbp
0x18007b747  jmp     cs:__imp_RtlSetCurrentTransaction
```
