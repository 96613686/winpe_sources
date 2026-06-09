# GetCompressedFileSizeTransactedW

- ea: `0x1800733b0`
- end: `0x18007343a`
- name: `GetCompressedFileSizeTransactedW`
- size: `138`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073340`

## callees

- `0x1800733b0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x1800733d0`
- `ntdll!RtlGetCurrentTransaction` at `0x1800733d0`
- `ntdll!RtlSetCurrentTransaction` at `0x1800733eb`
- `ntdll!RtlSetCurrentTransaction` at `0x18007340e`
- `ntdll!RtlSetCurrentTransaction` at `0x1800733eb`
- `ntdll!RtlSetCurrentTransaction` at `0x18007340e`
- `ntdll!RtlSetLastWin32Error` at `0x180073421`
- `ntdll!RtlSetLastWin32Error` at `0x180073421`
- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x1800733fe`
- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x1800733fe`

## pseudocode

```c
DWORD __stdcall GetCompressedFileSizeTransactedW(LPCWSTR lpFileName, LPDWORD lpFileSizeHigh, HANDLE hTransaction)
{
  DWORD CompressedFileSizeW; // ebx
  ULONG v7; // ecx

  CompressedFileSizeW = -1;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v7 = 6700;
    goto LABEL_6;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v7 = 6725;
LABEL_6:
    RtlSetLastWin32Error(v7);
    return CompressedFileSizeW;
  }
  RtlSetCurrentTransaction(hTransaction);
  CompressedFileSizeW = GetCompressedFileSizeW(lpFileName, lpFileSizeHigh);
  RtlSetCurrentTransaction(0);
  return CompressedFileSizeW;
}

```

## disassembly

```asm
0x1800733b0  push    rbx
0x1800733b2  push    rsi
0x1800733b3  push    rdi
0x1800733b4  push    r14
0x1800733b6  sub     rsp, 28h
0x1800733ba  mov     rdi, r8
0x1800733bd  mov     rsi, rdx
0x1800733c0  mov     r14, rcx
0x1800733c3  or      ebx, 0FFFFFFFFh
0x1800733c6  lea     rax, [r8-1]
0x1800733ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800733ce  ja      short loc_18007341C
0x1800733d0  call    cs:__imp_RtlGetCurrentTransaction
0x1800733d7  nop     dword ptr [rax+rax+00h]
0x1800733dc  test    rax, rax
0x1800733df  jz      short loc_1800733E8
0x1800733e1  mov     ecx, 1A45h
0x1800733e6  jmp     short loc_180073421
0x1800733e8  mov     rcx, rdi
0x1800733eb  call    cs:__imp_RtlSetCurrentTransaction
0x1800733f2  nop     dword ptr [rax+rax+00h]
0x1800733f7  nop
0x1800733f8  mov     rdx, rsi; lpFileSizeHigh
0x1800733fb  mov     rcx, r14; lpFileName
0x1800733fe  call    cs:__imp_GetCompressedFileSizeW
0x180073405  nop     dword ptr [rax+rax+00h]
0x18007340a  mov     ebx, eax
0x18007340c  xor     ecx, ecx
0x18007340e  call    cs:__imp_RtlSetCurrentTransaction
0x180073415  nop     dword ptr [rax+rax+00h]
0x18007341a  jmp     short loc_18007342D
0x18007341c  mov     ecx, 1A2Ch; LastError
0x180073421  call    cs:__imp_RtlSetLastWin32Error
0x180073428  nop     dword ptr [rax+rax+00h]
0x18007342d  mov     eax, ebx
0x18007342f  add     rsp, 28h
0x180073433  pop     r14
0x180073435  pop     rdi
0x180073436  pop     rsi
0x180073437  pop     rbx
0x180073438  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
