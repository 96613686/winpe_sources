# CreateSymbolicLinkTransactedW

- ea: `0x18005f110`
- end: `0x18005f1a3`
- name: `CreateSymbolicLinkTransactedW`
- size: `147`
- prototype: `BOOLEAN __stdcall(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180073210`

## callees

- `0x18005f110`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18005f134`
- `ntdll!RtlGetCurrentTransaction` at `0x18005f134`
- `ntdll!RtlSetCurrentTransaction` at `0x18005f14f`
- `ntdll!RtlSetCurrentTransaction` at `0x18005f175`
- `ntdll!RtlSetCurrentTransaction` at `0x18005f14f`
- `ntdll!RtlSetCurrentTransaction` at `0x18005f175`
- `ntdll!RtlSetLastWin32Error` at `0x18005f188`
- `ntdll!RtlSetLastWin32Error` at `0x18005f188`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18005f165`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18005f165`

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
0x18005f110  push    rbx
0x18005f112  push    rsi
0x18005f113  push    rdi
0x18005f114  push    r14
0x18005f116  push    r15
0x18005f118  sub     rsp, 20h
0x18005f11c  mov     rdi, r9
0x18005f11f  mov     esi, r8d
0x18005f122  mov     r14, rdx
0x18005f125  mov     r15, rcx
0x18005f128  xor     bl, bl
0x18005f12a  lea     rax, [r9-1]
0x18005f12e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f132  ja      short loc_18005F183
0x18005f134  call    cs:__imp_RtlGetCurrentTransaction
0x18005f13b  nop     dword ptr [rax+rax+00h]
0x18005f140  test    rax, rax
0x18005f143  jz      short loc_18005F14C
0x18005f145  mov     ecx, 1A45h
0x18005f14a  jmp     short loc_18005F188
0x18005f14c  mov     rcx, rdi
0x18005f14f  call    cs:__imp_RtlSetCurrentTransaction
0x18005f156  nop     dword ptr [rax+rax+00h]
0x18005f15b  nop
0x18005f15c  mov     r8d, esi; dwFlags
0x18005f15f  mov     rdx, r14; lpTargetFileName
0x18005f162  mov     rcx, r15; lpSymlinkFileName
0x18005f165  call    cs:__imp_CreateSymbolicLinkW
0x18005f16c  nop     dword ptr [rax+rax+00h]
0x18005f171  mov     bl, al
0x18005f173  xor     ecx, ecx
0x18005f175  call    cs:__imp_RtlSetCurrentTransaction
0x18005f17c  nop     dword ptr [rax+rax+00h]
0x18005f181  jmp     short loc_18005F194
0x18005f183  mov     ecx, 1A2Ch; LastError
0x18005f188  call    cs:__imp_RtlSetLastWin32Error
0x18005f18f  nop     dword ptr [rax+rax+00h]
0x18005f194  mov     al, bl
0x18005f196  add     rsp, 20h
0x18005f19a  pop     r15
0x18005f19c  pop     r14
0x18005f19e  pop     rdi
0x18005f19f  pop     rsi
0x18005f1a0  pop     rbx
0x18005f1a1  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
