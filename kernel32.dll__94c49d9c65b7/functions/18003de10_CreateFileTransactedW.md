# CreateFileTransactedW

- ea: `0x18003de10`
- end: `0x18003df3f`
- name: `CreateFileTransactedW`
- size: `303`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile, HANDLE hTransaction, PUSHORT pusMiniVersion, PVOID lpExtendedParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006b850`

## callees

- `0x18003de10`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18003de51`
- `ntdll!RtlGetCurrentTransaction` at `0x18003de51`
- `ntdll!RtlSetCurrentTransaction` at `0x18003de6d`
- `ntdll!RtlSetCurrentTransaction` at `0x18003debf`
- `ntdll!RtlSetCurrentTransaction` at `0x18007b0b7`
- `ntdll!RtlSetCurrentTransaction` at `0x18003de6d`
- `ntdll!RtlSetCurrentTransaction` at `0x18003debf`
- `ntdll!RtlSetCurrentTransaction` at `0x18007b0b7`
- `ntdll!RtlSetLastWin32Error` at `0x18003df33`
- `ntdll!RtlSetLastWin32Error` at `0x18003df33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003deaf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003deaf`

## pseudocode

```c
HANDLE __stdcall CreateFileTransactedW(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile,
        HANDLE hTransaction,
        PUSHORT pusMiniVersion,
        PVOID lpExtendedParameter)
{
  unsigned __int16 TxFsContext; // di
  HANDLE FileW; // rbx
  ULONG v17; // ecx

  if ( lpExtendedParameter )
  {
    v17 = 87;
LABEL_12:
    RtlSetLastWin32Error(v17);
    return (HANDLE)-1LL;
  }
  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v17 = 6700;
    goto LABEL_12;
  }
  if ( RtlGetCurrentTransaction() )
  {
    v17 = 6725;
    goto LABEL_12;
  }
  TxFsContext = 0;
  RtlSetCurrentTransaction(hTransaction);
  if ( pusMiniVersion )
  {
    TxFsContext = NtCurrentTeb()->TxFsContext;
    NtCurrentTeb()->TxFsContext = *pusMiniVersion;
  }
  FileW = CreateFileW(
            lpFileName,
            dwDesiredAccess,
            dwShareMode,
            lpSecurityAttributes,
            dwCreationDisposition,
            dwFlagsAndAttributes,
            hTemplateFile);
  RtlSetCurrentTransaction(0);
  if ( pusMiniVersion )
    NtCurrentTeb()->TxFsContext = TxFsContext;
  return FileW;
}

```

## disassembly

```asm
0x18003de10  push    rbx
0x18003de12  push    rsi
0x18003de13  push    rdi
0x18003de14  push    r12
0x18003de16  push    r13
0x18003de18  push    r14
0x18003de1a  push    r15
0x18003de1c  sub     rsp, 50h
0x18003de20  mov     r14, r9
0x18003de23  mov     r15d, r8d
0x18003de26  mov     r12d, edx
0x18003de29  mov     r13, rcx
0x18003de2c  cmp     [rsp+88h+lpExtendedParameter], 0
0x18003de35  jnz     loc_18003DF0C
0x18003de3b  mov     rbx, [rsp+88h+hTransaction]
0x18003de43  lea     rax, [rbx-1]
0x18003de47  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003de4b  ja      loc_18003DF2E
0x18003de51  call    cs:__imp_RtlGetCurrentTransaction
0x18003de57  test    rax, rax
0x18003de5a  jnz     loc_18003DF13
0x18003de60  xor     edi, edi
0x18003de62  mov     word ptr [rsp+88h+lpExtendedParameter], di
0x18003de6a  mov     rcx, rbx
0x18003de6d  call    cs:__imp_RtlSetCurrentTransaction
0x18003de73  mov     rsi, [rsp+88h+pusMiniVersion]
0x18003de7b  test    rsi, rsi
0x18003de7e  jnz     short loc_18003DEDD
0x18003de80  mov     rax, [rsp+88h+hTemplateFile]
0x18003de88  mov     [rsp+88h+var_58], rax; hTemplateFile
0x18003de8d  mov     eax, [rsp+88h+dwFlagsAndAttributes]
0x18003de94  mov     [rsp+88h+var_60], eax; dwFlagsAndAttributes
0x18003de98  mov     eax, [rsp+88h+dwCreationDisposition]
0x18003de9f  mov     [rsp+88h+var_68], eax; dwCreationDisposition
0x18003dea3  mov     r9, r14; lpSecurityAttributes
0x18003dea6  mov     r8d, r15d; dwShareMode
0x18003dea9  mov     edx, r12d; dwDesiredAccess
0x18003deac  mov     rcx, r13; lpFileName
0x18003deaf  call    cs:__imp_CreateFileW
0x18003deb5  mov     rbx, rax
0x18003deb8  mov     [rsp+88h+var_48], rax
0x18003debd  xor     ecx, ecx
0x18003debf  call    cs:__imp_RtlSetCurrentTransaction
0x18003dec5  test    rsi, rsi
0x18003dec8  jnz     short loc_18003DF1A
0x18003deca  mov     rax, rbx
0x18003decd  add     rsp, 50h
0x18003ded1  pop     r15
0x18003ded3  pop     r14
0x18003ded5  pop     r13
0x18003ded7  pop     r12
0x18003ded9  pop     rdi
0x18003deda  pop     rsi
0x18003dedb  pop     rbx
0x18003dedc  retn
0x18003dedd  mov     rax, gs:30h
0x18003dee6  movzx   edi, word ptr [rax+2E8h]
0x18003deed  mov     word ptr [rsp+88h+lpExtendedParameter], di
0x18003def5  movzx   ecx, word ptr [rsi]
0x18003def8  mov     rax, gs:30h
0x18003df01  mov     [rax+2E8h], ecx
0x18003df07  jmp     loc_18003DE80
0x18003df0c  mov     ecx, 57h ; 'W'
0x18003df11  jmp     short loc_18003DF33
0x18003df13  mov     ecx, 1A45h
0x18003df18  jmp     short loc_18003DF33
0x18003df1a  movzx   ecx, di
0x18003df1d  mov     rax, gs:30h
0x18003df26  mov     [rax+2E8h], ecx
0x18003df2c  jmp     short loc_18003DECA
0x18003df2e  mov     ecx, 1A2Ch; LastError
0x18003df33  call    cs:__imp_RtlSetLastWin32Error
0x18003df39  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003df3d  jmp     short loc_18003DECA
0x18007b0ac  push    rbp
0x18007b0ae  sub     rsp, 40h
0x18007b0b2  mov     rbp, rdx
0x18007b0b5  xor     ecx, ecx
0x18007b0b7  call    cs:__imp_RtlSetCurrentTransaction
0x18007b0bd  cmp     qword ptr [rbp+0D0h], 0
0x18007b0c5  jz      short loc_18007B0DD
0x18007b0c7  mov     rcx, gs:30h
0x18007b0d0  movzx   eax, word ptr [rbp+0D8h]
0x18007b0d7  mov     [rcx+2E8h], eax
0x18007b0dd  add     rsp, 40h
0x18007b0e1  pop     rbp
0x18007b0e2  retn
```
