# SetFileAttributesTransactedW

- ea: `0x180073770`
- end: `0x1800737f7`
- name: `SetFileAttributesTransactedW`
- size: `135`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, DWORD dwFileAttributes, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180073710`

## callees

- `0x180073770`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18007378e`
- `ntdll!RtlGetCurrentTransaction` at `0x18007378e`
- `ntdll!RtlSetCurrentTransaction` at `0x1800737a9`
- `ntdll!RtlSetCurrentTransaction` at `0x1800737cb`
- `ntdll!RtlSetCurrentTransaction` at `0x1800737a9`
- `ntdll!RtlSetCurrentTransaction` at `0x1800737cb`
- `ntdll!RtlSetLastWin32Error` at `0x1800737de`
- `ntdll!RtlSetLastWin32Error` at `0x1800737de`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800737bb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800737bb`

## pseudocode

```c
BOOL __stdcall SetFileAttributesTransactedW(LPCWSTR lpFileName, DWORD dwFileAttributes, HANDLE hTransaction)
{
  BOOL v6; // ebx
  ULONG v7; // ecx

  v6 = 0;
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
    return v6;
  }
  RtlSetCurrentTransaction(hTransaction);
  v6 = SetFileAttributesW(lpFileName, dwFileAttributes);
  RtlSetCurrentTransaction(0);
  return v6;
}

```

## disassembly

```asm
0x180073770  push    rbx
0x180073772  push    rsi
0x180073773  push    rdi
0x180073774  push    r14
0x180073776  sub     rsp, 28h
0x18007377a  mov     rdi, r8
0x18007377d  mov     esi, edx
0x18007377f  mov     r14, rcx
0x180073782  xor     ebx, ebx
0x180073784  lea     rax, [r8-1]
0x180073788  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007378c  ja      short loc_1800737D9
0x18007378e  call    cs:__imp_RtlGetCurrentTransaction
0x180073795  nop     dword ptr [rax+rax+00h]
0x18007379a  test    rax, rax
0x18007379d  jz      short loc_1800737A6
0x18007379f  mov     ecx, 1A45h
0x1800737a4  jmp     short loc_1800737DE
0x1800737a6  mov     rcx, rdi
0x1800737a9  call    cs:__imp_RtlSetCurrentTransaction
0x1800737b0  nop     dword ptr [rax+rax+00h]
0x1800737b5  nop
0x1800737b6  mov     edx, esi; dwFileAttributes
0x1800737b8  mov     rcx, r14; lpFileName
0x1800737bb  call    cs:__imp_SetFileAttributesW
0x1800737c2  nop     dword ptr [rax+rax+00h]
0x1800737c7  mov     ebx, eax
0x1800737c9  xor     ecx, ecx
0x1800737cb  call    cs:__imp_RtlSetCurrentTransaction
0x1800737d2  nop     dword ptr [rax+rax+00h]
0x1800737d7  jmp     short loc_1800737EA
0x1800737d9  mov     ecx, 1A2Ch; LastError
0x1800737de  call    cs:__imp_RtlSetLastWin32Error
0x1800737e5  nop     dword ptr [rax+rax+00h]
0x1800737ea  mov     eax, ebx
0x1800737ec  add     rsp, 28h
0x1800737f0  pop     r14
0x1800737f2  pop     rdi
0x1800737f3  pop     rsi
0x1800737f4  pop     rbx
0x1800737f5  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
