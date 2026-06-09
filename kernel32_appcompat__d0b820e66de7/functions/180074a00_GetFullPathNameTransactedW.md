# GetFullPathNameTransactedW

- ea: `0x180074a00`
- end: `0x180074ab0`
- name: `GetFullPathNameTransactedW`
- size: `176`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180074a00`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180074a2c`
- `ntdll!RtlGetCurrentTransaction` at `0x180074a2c`
- `ntdll!RtlSetCurrentTransaction` at `0x180074a55`
- `ntdll!RtlSetCurrentTransaction` at `0x180074a7e`
- `ntdll!RtlSetCurrentTransaction` at `0x180074a55`
- `ntdll!RtlSetCurrentTransaction` at `0x180074a7e`
- `ntdll!RtlSetCurrentTransaction` at `0x18008386c`
- `ntdll!RtlSetLastWin32Error` at `0x180074a44`
- `ntdll!RtlSetLastWin32Error` at `0x180074a91`
- `ntdll!RtlSetLastWin32Error` at `0x180074a44`
- `ntdll!RtlSetLastWin32Error` at `0x180074a91`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180074a6e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180074a6e`

## pseudocode

```c
DWORD __stdcall GetFullPathNameTransactedW(
        LPCWSTR lpFileName,
        DWORD nBufferLength,
        LPWSTR lpBuffer,
        LPWSTR *lpFilePart,
        HANDLE hTransaction)
{
  DWORD FullPathNameW; // ebx

  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    RtlSetLastWin32Error(0x1A2Cu);
    return 0;
  }
  else
  {
    FullPathNameW = 0;
    if ( RtlGetCurrentTransaction() )
    {
      RtlSetLastWin32Error(0x1A45u);
    }
    else
    {
      RtlSetCurrentTransaction(hTransaction);
      FullPathNameW = GetFullPathNameW(lpFileName, nBufferLength, lpBuffer, lpFilePart);
      RtlSetCurrentTransaction(0);
    }
  }
  return FullPathNameW;
}

```

## disassembly

```asm
0x180074a00  push    rbx
0x180074a02  push    rsi
0x180074a03  push    rdi
0x180074a04  push    r12
0x180074a06  push    r14
0x180074a08  push    r15
0x180074a0a  sub     rsp, 28h
0x180074a0e  mov     rsi, r9
0x180074a11  mov     r14, r8
0x180074a14  mov     r15d, edx
0x180074a17  mov     r12, rcx
0x180074a1a  mov     rdi, [rsp+58h+hTransaction]
0x180074a22  lea     rax, [rdi-1]
0x180074a26  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180074a2a  ja      short loc_180074A8C
0x180074a2c  call    cs:__imp_RtlGetCurrentTransaction
0x180074a33  nop     dword ptr [rax+rax+00h]
0x180074a38  xor     ebx, ebx
0x180074a3a  test    rax, rax
0x180074a3d  jz      short loc_180074A52
0x180074a3f  mov     ecx, 1A45h; LastError
0x180074a44  call    cs:__imp_RtlSetLastWin32Error
0x180074a4b  nop     dword ptr [rax+rax+00h]
0x180074a50  jmp     short loc_180074A9F
0x180074a52  mov     rcx, rdi
0x180074a55  call    cs:__imp_RtlSetCurrentTransaction
0x180074a5c  nop     dword ptr [rax+rax+00h]
0x180074a61  nop
0x180074a62  mov     r9, rsi; lpFilePart
0x180074a65  mov     r8, r14; lpBuffer
0x180074a68  mov     edx, r15d; nBufferLength
0x180074a6b  mov     rcx, r12; lpFileName
0x180074a6e  call    cs:__imp_GetFullPathNameW
0x180074a75  nop     dword ptr [rax+rax+00h]
0x180074a7a  mov     ebx, eax
0x180074a7c  xor     ecx, ecx
0x180074a7e  call    cs:__imp_RtlSetCurrentTransaction
0x180074a85  nop     dword ptr [rax+rax+00h]
0x180074a8a  jmp     short loc_180074A9F
0x180074a8c  mov     ecx, 1A2Ch; LastError
0x180074a91  call    cs:__imp_RtlSetLastWin32Error
0x180074a98  nop     dword ptr [rax+rax+00h]
0x180074a9d  xor     ebx, ebx
0x180074a9f  mov     eax, ebx
0x180074aa1  add     rsp, 28h
0x180074aa5  pop     r15
0x180074aa7  pop     r14
0x180074aa9  pop     r12
0x180074aab  pop     rdi
0x180074aac  pop     rsi
0x180074aad  pop     rbx
0x180074aae  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
