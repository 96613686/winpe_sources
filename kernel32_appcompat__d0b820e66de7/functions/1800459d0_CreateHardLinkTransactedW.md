# CreateHardLinkTransactedW

- ea: `0x1800459d0`
- end: `0x180045a71`
- name: `CreateHardLinkTransactedW`
- size: `161`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, LPCWSTR lpExistingFileName, LPSECURITY_ATTRIBUTES lpSecurityAttributes, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180068430`

## callees

- `0x1800459d0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180045a14`
- `ntdll!RtlGetCurrentTransaction` at `0x180045a14`
- `ntdll!RtlSetCurrentTransaction` at `0x180045a3d`
- `ntdll!RtlSetCurrentTransaction` at `0x180045a63`
- `ntdll!RtlSetCurrentTransaction` at `0x180045a3d`
- `ntdll!RtlSetCurrentTransaction` at `0x180045a63`
- `ntdll!RtlSetCurrentTransaction` at `0x18008338b`
- `ntdll!RtlSetLastWin32Error` at `0x1800459f7`
- `ntdll!RtlSetLastWin32Error` at `0x180045a2c`
- `ntdll!RtlSetLastWin32Error` at `0x1800459f7`
- `ntdll!RtlSetLastWin32Error` at `0x180045a2c`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180045a53`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180045a53`

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
0x1800459d0  push    rbx
0x1800459d2  push    rsi
0x1800459d3  push    rdi
0x1800459d4  push    r14
0x1800459d6  push    r15
0x1800459d8  sub     rsp, 20h
0x1800459dc  mov     rdi, r9
0x1800459df  mov     rsi, r8
0x1800459e2  mov     r14, rdx
0x1800459e5  mov     r15, rcx
0x1800459e8  lea     rax, [r9-1]
0x1800459ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800459f0  jbe     short loc_180045A14
0x1800459f2  mov     ecx, 1A2Ch; LastError
0x1800459f7  call    cs:__imp_RtlSetLastWin32Error
0x1800459fe  nop     dword ptr [rax+rax+00h]
0x180045a03  xor     ebx, ebx
0x180045a05  mov     eax, ebx
0x180045a07  add     rsp, 20h
0x180045a0b  pop     r15
0x180045a0d  pop     r14
0x180045a0f  pop     rdi
0x180045a10  pop     rsi
0x180045a11  pop     rbx
0x180045a12  retn
0x180045a14  call    cs:__imp_RtlGetCurrentTransaction
0x180045a1b  nop     dword ptr [rax+rax+00h]
0x180045a20  xor     ebx, ebx
0x180045a22  test    rax, rax
0x180045a25  jz      short loc_180045A3A
0x180045a27  mov     ecx, 1A45h; LastError
0x180045a2c  call    cs:__imp_RtlSetLastWin32Error
0x180045a33  nop     dword ptr [rax+rax+00h]
0x180045a38  jmp     short loc_180045A05
0x180045a3a  mov     rcx, rdi
0x180045a3d  call    cs:__imp_RtlSetCurrentTransaction
0x180045a44  nop     dword ptr [rax+rax+00h]
0x180045a49  nop
0x180045a4a  mov     r8, rsi; lpSecurityAttributes
0x180045a4d  mov     rdx, r14; lpExistingFileName
0x180045a50  mov     rcx, r15; lpFileName
0x180045a53  call    cs:__imp_CreateHardLinkW
0x180045a5a  nop     dword ptr [rax+rax+00h]
0x180045a5f  mov     ebx, eax
0x180045a61  xor     ecx, ecx
0x180045a63  call    cs:__imp_RtlSetCurrentTransaction
0x180045a6a  nop     dword ptr [rax+rax+00h]
0x180045a6f  jmp     short loc_180045A05
0x18008337b  push    rbp
0x18008337d  sub     rsp, 20h
0x180083381  mov     rbp, rdx
0x180083384  xor     ecx, ecx
0x180083386  add     rsp, 20h
0x18008338a  pop     rbp
0x18008338b  jmp     cs:__imp_RtlSetCurrentTransaction
```
