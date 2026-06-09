# CreateDirectoryTransactedW

- ea: `0x180072f20`
- end: `0x180072fcc`
- name: `CreateDirectoryTransactedW`
- size: `172`
- prototype: `BOOL __stdcall(LPCWSTR lpTemplateDirectory, LPCWSTR lpNewDirectory, LPSECURITY_ATTRIBUTES lpSecurityAttributes, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800637c0`

## callees

- `0x180072f20`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180072f44`
- `ntdll!RtlGetCurrentTransaction` at `0x180072f44`
- `ntdll!RtlSetCurrentTransaction` at `0x180072f5f`
- `ntdll!RtlSetCurrentTransaction` at `0x180072f9e`
- `ntdll!RtlSetCurrentTransaction` at `0x180072f5f`
- `ntdll!RtlSetCurrentTransaction` at `0x180072f9e`
- `ntdll!RtlSetLastWin32Error` at `0x180072fb1`
- `ntdll!RtlSetLastWin32Error` at `0x180072fb1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180072f8e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180072f8e`
- `api-ms-win-core-file-l2-1-0!CreateDirectoryExW` at `0x180072f7a`
- `api-ms-win-core-file-l2-1-0!CreateDirectoryExW` at `0x180072f7a`

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
0x180072f20  push    rbx
0x180072f22  push    rsi
0x180072f23  push    rdi
0x180072f24  push    r14
0x180072f26  push    r15
0x180072f28  sub     rsp, 20h
0x180072f2c  mov     r15, r9
0x180072f2f  mov     rsi, r8
0x180072f32  mov     r14, rdx
0x180072f35  mov     rdi, rcx
0x180072f38  xor     ebx, ebx
0x180072f3a  lea     rax, [r9-1]
0x180072f3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180072f42  ja      short loc_180072FAC
0x180072f44  call    cs:__imp_RtlGetCurrentTransaction
0x180072f4b  nop     dword ptr [rax+rax+00h]
0x180072f50  test    rax, rax
0x180072f53  jz      short loc_180072F5C
0x180072f55  mov     ecx, 1A45h
0x180072f5a  jmp     short loc_180072FB1
0x180072f5c  mov     rcx, r15
0x180072f5f  call    cs:__imp_RtlSetCurrentTransaction
0x180072f66  nop     dword ptr [rax+rax+00h]
0x180072f6b  nop
0x180072f6c  test    rdi, rdi
0x180072f6f  jz      short loc_180072F88
0x180072f71  mov     r8, rsi; lpSecurityAttributes
0x180072f74  mov     rdx, r14; lpNewDirectory
0x180072f77  mov     rcx, rdi; lpTemplateDirectory
0x180072f7a  call    cs:__imp_CreateDirectoryExW
0x180072f81  nop     dword ptr [rax+rax+00h]
0x180072f86  jmp     short loc_180072F9A
0x180072f88  mov     rdx, rsi; lpSecurityAttributes
0x180072f8b  mov     rcx, r14; lpPathName
0x180072f8e  call    cs:__imp_CreateDirectoryW
0x180072f95  nop     dword ptr [rax+rax+00h]
0x180072f9a  mov     ebx, eax
0x180072f9c  xor     ecx, ecx
0x180072f9e  call    cs:__imp_RtlSetCurrentTransaction
0x180072fa5  nop     dword ptr [rax+rax+00h]
0x180072faa  jmp     short loc_180072FBD
0x180072fac  mov     ecx, 1A2Ch; LastError
0x180072fb1  call    cs:__imp_RtlSetLastWin32Error
0x180072fb8  nop     dword ptr [rax+rax+00h]
0x180072fbd  mov     eax, ebx
0x180072fbf  add     rsp, 20h
0x180072fc3  pop     r15
0x180072fc5  pop     r14
0x180072fc7  pop     rdi
0x180072fc8  pop     rsi
0x180072fc9  pop     rbx
0x180072fca  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
