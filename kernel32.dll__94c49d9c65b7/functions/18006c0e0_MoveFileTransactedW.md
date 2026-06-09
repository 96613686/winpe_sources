# MoveFileTransactedW

- ea: `0x18006c0e0`
- end: `0x18006c173`
- name: `MoveFileTransactedW`
- size: `147`
- prototype: `BOOL __stdcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18006c0e0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006c10e`
- `ntdll!RtlGetCurrentTransaction` at `0x18006c10e`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c123`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c150`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c123`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c150`
- `ntdll!RtlSetLastWin32Error` at `0x18006c15d`
- `ntdll!RtlSetLastWin32Error` at `0x18006c15d`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x18006c146`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x18006c146`

## pseudocode

```c
BOOL __stdcall MoveFileTransactedW(
        LPCWSTR lpExistingFileName,
        LPCWSTR lpNewFileName,
        LPPROGRESS_ROUTINE lpProgressRoutine,
        LPVOID lpData,
        DWORD dwFlags,
        HANDLE hTransaction)
{
  int v10; // ebx
  ULONG v11; // ecx

  v10 = 0;
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v11 = 6700;
    goto LABEL_6;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v11 = 6725;
LABEL_6:
    RtlSetLastWin32Error(v11);
    return v10;
  }
  RtlSetCurrentTransaction(hTransaction);
  v10 = MoveFileWithProgressTransactedW(
          lpExistingFileName,
          lpNewFileName,
          lpProgressRoutine,
          lpData,
          dwFlags,
          hTransaction);
  RtlSetCurrentTransaction(0);
  return v10;
}

```

## disassembly

```asm
0x18006c0e0  push    rbx
0x18006c0e2  push    rsi
0x18006c0e3  push    rdi
0x18006c0e4  push    r12
0x18006c0e6  push    r14
0x18006c0e8  push    r15
0x18006c0ea  sub     rsp, 38h
0x18006c0ee  mov     rsi, r9
0x18006c0f1  mov     r14, r8
0x18006c0f4  mov     r15, rdx
0x18006c0f7  mov     r12, rcx
0x18006c0fa  xor     ebx, ebx
0x18006c0fc  mov     rdi, [rsp+68h+hTransaction]
0x18006c104  lea     rax, [rdi-1]
0x18006c108  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c10c  ja      short loc_18006C158
0x18006c10e  call    cs:__imp_RtlGetCurrentTransaction
0x18006c114  test    rax, rax
0x18006c117  jz      short loc_18006C120
0x18006c119  mov     ecx, 1A45h
0x18006c11e  jmp     short loc_18006C15D
0x18006c120  mov     rcx, rdi
0x18006c123  call    cs:__imp_RtlSetCurrentTransaction
0x18006c129  nop
0x18006c12a  mov     [rsp+68h+var_40], rdi
0x18006c12f  mov     eax, [rsp+68h+dwFlags]
0x18006c136  mov     [rsp+68h+var_48], eax
0x18006c13a  mov     r9, rsi
0x18006c13d  mov     r8, r14
0x18006c140  mov     rdx, r15
0x18006c143  mov     rcx, r12
0x18006c146  call    cs:__imp_MoveFileWithProgressTransactedW
0x18006c14c  mov     ebx, eax
0x18006c14e  xor     ecx, ecx
0x18006c150  call    cs:__imp_RtlSetCurrentTransaction
0x18006c156  jmp     short loc_18006C163
0x18006c158  mov     ecx, 1A2Ch; LastError
0x18006c15d  call    cs:__imp_RtlSetLastWin32Error
0x18006c163  mov     eax, ebx
0x18006c165  add     rsp, 38h
0x18006c169  pop     r15
0x18006c16b  pop     r14
0x18006c16d  pop     r12
0x18006c16f  pop     rdi
0x18006c170  pop     rsi
0x18006c171  pop     rbx
0x18006c172  retn
0x18007b871  push    rbp
0x18007b873  sub     rsp, 30h
0x18007b877  mov     rbp, rdx
0x18007b87a  xor     ecx, ecx
0x18007b87c  add     rsp, 30h
0x18007b880  pop     rbp
0x18007b881  jmp     cs:__imp_RtlSetCurrentTransaction
```
