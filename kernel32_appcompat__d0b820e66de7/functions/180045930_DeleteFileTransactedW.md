# DeleteFileTransactedW

- ea: `0x180045930`
- end: `0x1800459be`
- name: `DeleteFileTransactedW`
- size: `142`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800732e0`

## callees

- `0x180045930`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180045951`
- `ntdll!RtlGetCurrentTransaction` at `0x180045951`
- `ntdll!RtlSetCurrentTransaction` at `0x180045965`
- `ntdll!RtlSetCurrentTransaction` at `0x180045985`
- `ntdll!RtlSetCurrentTransaction` at `0x180045965`
- `ntdll!RtlSetCurrentTransaction` at `0x180045985`
- `ntdll!RtlSetCurrentTransaction` at `0x180083368`
- `ntdll!RtlSetLastWin32Error` at `0x1800459a9`
- `ntdll!RtlSetLastWin32Error` at `0x1800459a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045975`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180045975`

## pseudocode

```c
BOOL __stdcall DeleteFileTransactedW(LPCWSTR lpFileName, HANDLE hTransaction)
{
  BOOL v4; // ebx
  ULONG v6; // ecx

  v4 = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = 6700;
LABEL_6:
    RtlSetLastWin32Error(v6);
    return v4;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v6 = 6725;
    goto LABEL_6;
  }
  RtlSetCurrentTransaction(hTransaction);
  v4 = DeleteFileW(lpFileName);
  RtlSetCurrentTransaction(0);
  return v4;
}

```

## disassembly

```asm
0x180045930  mov     [rsp+arg_0], rbx
0x180045935  mov     [rsp+arg_8], rsi
0x18004593a  push    rdi
0x18004593b  sub     rsp, 20h
0x18004593f  mov     rdi, rdx
0x180045942  mov     rsi, rcx
0x180045945  xor     ebx, ebx
0x180045947  lea     rax, [rdx-1]
0x18004594b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004594f  ja      short loc_1800459A4
0x180045951  call    cs:__imp_RtlGetCurrentTransaction
0x180045958  nop     dword ptr [rax+rax+00h]
0x18004595d  test    rax, rax
0x180045960  jnz     short loc_1800459B7
0x180045962  mov     rcx, rdi
0x180045965  call    cs:__imp_RtlSetCurrentTransaction
0x18004596c  nop     dword ptr [rax+rax+00h]
0x180045971  nop
0x180045972  mov     rcx, rsi; lpFileName
0x180045975  call    cs:__imp_DeleteFileW
0x18004597c  nop     dword ptr [rax+rax+00h]
0x180045981  mov     ebx, eax
0x180045983  xor     ecx, ecx
0x180045985  call    cs:__imp_RtlSetCurrentTransaction
0x18004598c  nop     dword ptr [rax+rax+00h]
0x180045991  mov     eax, ebx
0x180045993  mov     rbx, [rsp+28h+arg_0]
0x180045998  mov     rsi, [rsp+28h+arg_8]
0x18004599d  add     rsp, 20h
0x1800459a1  pop     rdi
0x1800459a2  retn
0x1800459a4  mov     ecx, 1A2Ch; LastError
0x1800459a9  call    cs:__imp_RtlSetLastWin32Error
0x1800459b0  nop     dword ptr [rax+rax+00h]
0x1800459b5  jmp     short loc_180045991
0x1800459b7  mov     ecx, 1A45h
0x1800459bc  jmp     short loc_1800459A9
0x180083358  push    rbp
0x18008335a  sub     rsp, 20h
0x18008335e  mov     rbp, rdx
0x180083361  xor     ecx, ecx
0x180083363  add     rsp, 20h
0x180083367  pop     rbp
0x180083368  jmp     cs:__imp_RtlSetCurrentTransaction
```
