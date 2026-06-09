# GetFullPathNameTransactedW

- ea: `0x18006d250`
- end: `0x18006d2db`
- name: `GetFullPathNameTransactedW`
- size: `139`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18006d250`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006d27c`
- `ntdll!RtlGetCurrentTransaction` at `0x18006d27c`
- `ntdll!RtlSetCurrentTransaction` at `0x18006d299`
- `ntdll!RtlSetCurrentTransaction` at `0x18006d2b6`
- `ntdll!RtlSetCurrentTransaction` at `0x18006d299`
- `ntdll!RtlSetCurrentTransaction` at `0x18006d2b6`
- `ntdll!RtlSetCurrentTransaction` at `0x18007b747`
- `ntdll!RtlSetLastWin32Error` at `0x18006d28e`
- `ntdll!RtlSetLastWin32Error` at `0x18006d2c3`
- `ntdll!RtlSetLastWin32Error` at `0x18006d28e`
- `ntdll!RtlSetLastWin32Error` at `0x18006d2c3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18006d2ac`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18006d2ac`

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
0x18006d250  push    rbx
0x18006d252  push    rsi
0x18006d253  push    rdi
0x18006d254  push    r12
0x18006d256  push    r14
0x18006d258  push    r15
0x18006d25a  sub     rsp, 28h
0x18006d25e  mov     rsi, r9
0x18006d261  mov     r14, r8
0x18006d264  mov     r15d, edx
0x18006d267  mov     r12, rcx
0x18006d26a  mov     rdi, [rsp+58h+hTransaction]
0x18006d272  lea     rax, [rdi-1]
0x18006d276  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006d27a  ja      short loc_18006D2BE
0x18006d27c  call    cs:__imp_RtlGetCurrentTransaction
0x18006d282  xor     ebx, ebx
0x18006d284  test    rax, rax
0x18006d287  jz      short loc_18006D296
0x18006d289  mov     ecx, 1A45h; LastError
0x18006d28e  call    cs:__imp_RtlSetLastWin32Error
0x18006d294  jmp     short loc_18006D2CB
0x18006d296  mov     rcx, rdi
0x18006d299  call    cs:__imp_RtlSetCurrentTransaction
0x18006d29f  nop
0x18006d2a0  mov     r9, rsi; lpFilePart
0x18006d2a3  mov     r8, r14; lpBuffer
0x18006d2a6  mov     edx, r15d; nBufferLength
0x18006d2a9  mov     rcx, r12; lpFileName
0x18006d2ac  call    cs:__imp_GetFullPathNameW
0x18006d2b2  mov     ebx, eax
0x18006d2b4  xor     ecx, ecx
0x18006d2b6  call    cs:__imp_RtlSetCurrentTransaction
0x18006d2bc  jmp     short loc_18006D2CB
0x18006d2be  mov     ecx, 1A2Ch; LastError
0x18006d2c3  call    cs:__imp_RtlSetLastWin32Error
0x18006d2c9  xor     ebx, ebx
0x18006d2cb  mov     eax, ebx
0x18006d2cd  add     rsp, 28h
0x18006d2d1  pop     r15
0x18006d2d3  pop     r14
0x18006d2d5  pop     r12
0x18006d2d7  pop     rdi
0x18006d2d8  pop     rsi
0x18006d2d9  pop     rbx
0x18006d2da  retn
0x18007b737  push    rbp
0x18007b739  sub     rsp, 20h
0x18007b73d  mov     rbp, rdx
0x18007b740  xor     ecx, ecx
0x18007b742  add     rsp, 20h
0x18007b746  pop     rbp
0x18007b747  jmp     cs:__imp_RtlSetCurrentTransaction
```
