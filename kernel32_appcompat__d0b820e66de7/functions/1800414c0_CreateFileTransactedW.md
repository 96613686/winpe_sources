# CreateFileTransactedW

- ea: `0x1800414c0`
- end: `0x18004160e`
- name: `CreateFileTransactedW`
- size: `334`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile, HANDLE hTransaction, PUSHORT pusMiniVersion, PVOID lpExtendedParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180072c90`

## callees

- `0x1800414c0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180041501`
- `ntdll!RtlGetCurrentTransaction` at `0x180041501`
- `ntdll!RtlSetCurrentTransaction` at `0x180041523`
- `ntdll!RtlSetCurrentTransaction` at `0x180041581`
- `ntdll!RtlSetCurrentTransaction` at `0x18008311b`
- `ntdll!RtlSetCurrentTransaction` at `0x180041523`
- `ntdll!RtlSetCurrentTransaction` at `0x180041581`
- `ntdll!RtlSetCurrentTransaction` at `0x18008311b`
- `ntdll!RtlSetLastWin32Error` at `0x1800415fc`
- `ntdll!RtlSetLastWin32Error` at `0x1800415fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004156b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004156b`

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
0x1800414c0  push    rbx
0x1800414c2  push    rsi
0x1800414c3  push    rdi
0x1800414c4  push    r12
0x1800414c6  push    r13
0x1800414c8  push    r14
0x1800414ca  push    r15
0x1800414cc  sub     rsp, 50h
0x1800414d0  mov     r14, r9
0x1800414d3  mov     r15d, r8d
0x1800414d6  mov     r12d, edx
0x1800414d9  mov     r13, rcx
0x1800414dc  cmp     [rsp+88h+lpExtendedParameter], 0
0x1800414e5  jnz     loc_1800415D5
0x1800414eb  mov     rbx, [rsp+88h+hTransaction]
0x1800414f3  lea     rax, [rbx-1]
0x1800414f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800414fb  ja      loc_1800415F7
0x180041501  call    cs:__imp_RtlGetCurrentTransaction
0x180041508  nop     dword ptr [rax+rax+00h]
0x18004150d  test    rax, rax
0x180041510  jnz     loc_1800415DC
0x180041516  xor     edi, edi
0x180041518  mov     word ptr [rsp+88h+lpExtendedParameter], di
0x180041520  mov     rcx, rbx
0x180041523  call    cs:__imp_RtlSetCurrentTransaction
0x18004152a  nop     dword ptr [rax+rax+00h]
0x18004152f  mov     rsi, [rsp+88h+pusMiniVersion]
0x180041537  test    rsi, rsi
0x18004153a  jnz     short loc_1800415A6
0x18004153c  mov     rax, [rsp+88h+hTemplateFile]
0x180041544  mov     [rsp+88h+var_58], rax; hTemplateFile
0x180041549  mov     eax, [rsp+88h+dwFlagsAndAttributes]
0x180041550  mov     [rsp+88h+var_60], eax; dwFlagsAndAttributes
0x180041554  mov     eax, [rsp+88h+dwCreationDisposition]
0x18004155b  mov     [rsp+88h+var_68], eax; dwCreationDisposition
0x18004155f  mov     r9, r14; lpSecurityAttributes
0x180041562  mov     r8d, r15d; dwShareMode
0x180041565  mov     edx, r12d; dwDesiredAccess
0x180041568  mov     rcx, r13; lpFileName
0x18004156b  call    cs:__imp_CreateFileW
0x180041572  nop     dword ptr [rax+rax+00h]
0x180041577  mov     rbx, rax
0x18004157a  mov     [rsp+88h+var_48], rax
0x18004157f  xor     ecx, ecx
0x180041581  call    cs:__imp_RtlSetCurrentTransaction
0x180041588  nop     dword ptr [rax+rax+00h]
0x18004158d  test    rsi, rsi
0x180041590  jnz     short loc_1800415E3
0x180041592  mov     rax, rbx
0x180041595  add     rsp, 50h
0x180041599  pop     r15
0x18004159b  pop     r14
0x18004159d  pop     r13
0x18004159f  pop     r12
0x1800415a1  pop     rdi
0x1800415a2  pop     rsi
0x1800415a3  pop     rbx
0x1800415a4  retn
0x1800415a6  mov     rax, gs:30h
0x1800415af  movzx   edi, word ptr [rax+2E8h]
0x1800415b6  mov     word ptr [rsp+88h+lpExtendedParameter], di
0x1800415be  movzx   ecx, word ptr [rsi]
0x1800415c1  mov     rax, gs:30h
0x1800415ca  mov     [rax+2E8h], ecx
0x1800415d0  jmp     loc_18004153C
0x1800415d5  mov     ecx, 57h ; 'W'
0x1800415da  jmp     short loc_1800415FC
0x1800415dc  mov     ecx, 1A45h
0x1800415e1  jmp     short loc_1800415FC
0x1800415e3  movzx   ecx, di
0x1800415e6  mov     rax, gs:30h
0x1800415ef  mov     [rax+2E8h], ecx
0x1800415f5  jmp     short loc_180041592
0x1800415f7  mov     ecx, 1A2Ch; LastError
0x1800415fc  call    cs:__imp_RtlSetLastWin32Error
0x180041603  nop     dword ptr [rax+rax+00h]
0x180041608  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004160c  jmp     short loc_180041592
0x180083110  push    rbp
0x180083112  sub     rsp, 40h
0x180083116  mov     rbp, rdx
0x180083119  xor     ecx, ecx
0x18008311b  call    cs:__imp_RtlSetCurrentTransaction
0x180083122  nop     dword ptr [rax+rax+00h]
0x180083127  cmp     qword ptr [rbp+0D0h], 0
0x18008312f  jz      short loc_180083147
0x180083131  mov     rcx, gs:30h
0x18008313a  movzx   eax, word ptr [rbp+0D8h]
0x180083141  mov     [rcx+2E8h], eax
0x180083147  add     rsp, 40h
0x18008314b  pop     rbp
0x18008314c  retn
```
