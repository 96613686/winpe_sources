# GetFullPathNameTransactedA

- ea: `0x18005db80`
- end: `0x18005dc03`
- name: `GetFullPathNameTransactedA`
- size: `131`
- prototype: `DWORD __stdcall(LPCSTR lpFileName, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18005db80`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18005dbae`
- `ntdll!RtlGetCurrentTransaction` at `0x18005dbae`
- `ntdll!RtlSetCurrentTransaction` at `0x18005dbc3`
- `ntdll!RtlSetCurrentTransaction` at `0x18005dbe0`
- `ntdll!RtlSetCurrentTransaction` at `0x18005dbc3`
- `ntdll!RtlSetCurrentTransaction` at `0x18005dbe0`
- `ntdll!RtlSetLastWin32Error` at `0x18005dbed`
- `ntdll!RtlSetLastWin32Error` at `0x18005dbed`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18005dbd6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18005dbd6`

## pseudocode

```c
DWORD __stdcall GetFullPathNameTransactedA(
        LPCSTR lpFileName,
        DWORD nBufferLength,
        LPSTR lpBuffer,
        LPSTR *lpFilePart,
        HANDLE hTransaction)
{
  DWORD FullPathNameA; // ebx
  ULONG v10; // ecx

  FullPathNameA = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v10 = 6700;
    goto LABEL_6;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v10 = 6725;
LABEL_6:
    RtlSetLastWin32Error(v10);
    return FullPathNameA;
  }
  RtlSetCurrentTransaction(hTransaction);
  FullPathNameA = GetFullPathNameA(lpFileName, nBufferLength, lpBuffer, lpFilePart);
  RtlSetCurrentTransaction(0);
  return FullPathNameA;
}

```

## disassembly

```asm
0x18005db80  push    rbx
0x18005db82  push    rsi
0x18005db83  push    rdi
0x18005db84  push    r12
0x18005db86  push    r14
0x18005db88  push    r15
0x18005db8a  sub     rsp, 28h
0x18005db8e  mov     rsi, r9
0x18005db91  mov     r14, r8
0x18005db94  mov     r15d, edx
0x18005db97  mov     r12, rcx
0x18005db9a  xor     ebx, ebx
0x18005db9c  mov     rdi, [rsp+58h+hTransaction]
0x18005dba4  lea     rax, [rdi-1]
0x18005dba8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005dbac  ja      short loc_18005DBE8
0x18005dbae  call    cs:__imp_RtlGetCurrentTransaction
0x18005dbb4  test    rax, rax
0x18005dbb7  jz      short loc_18005DBC0
0x18005dbb9  mov     ecx, 1A45h
0x18005dbbe  jmp     short loc_18005DBED
0x18005dbc0  mov     rcx, rdi
0x18005dbc3  call    cs:__imp_RtlSetCurrentTransaction
0x18005dbc9  nop
0x18005dbca  mov     r9, rsi; lpFilePart
0x18005dbcd  mov     r8, r14; lpBuffer
0x18005dbd0  mov     edx, r15d; nBufferLength
0x18005dbd3  mov     rcx, r12; lpFileName
0x18005dbd6  call    cs:__imp_GetFullPathNameA
0x18005dbdc  mov     ebx, eax
0x18005dbde  xor     ecx, ecx
0x18005dbe0  call    cs:__imp_RtlSetCurrentTransaction
0x18005dbe6  jmp     short loc_18005DBF3
0x18005dbe8  mov     ecx, 1A2Ch; LastError
0x18005dbed  call    cs:__imp_RtlSetLastWin32Error
0x18005dbf3  mov     eax, ebx
0x18005dbf5  add     rsp, 28h
0x18005dbf9  pop     r15
0x18005dbfb  pop     r14
0x18005dbfd  pop     r12
0x18005dbff  pop     rdi
0x18005dc00  pop     rsi
0x18005dc01  pop     rbx
0x18005dc02  retn
0x18007b737  push    rbp
0x18007b739  sub     rsp, 20h
0x18007b73d  mov     rbp, rdx
0x18007b740  xor     ecx, ecx
0x18007b742  add     rsp, 20h
0x18007b746  pop     rbp
0x18007b747  jmp     cs:__imp_RtlSetCurrentTransaction
```
