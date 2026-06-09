# RemoveDirectoryTransactedW

- ea: `0x180072fe0`
- end: `0x18007307c`
- name: `RemoveDirectoryTransactedW`
- size: `156`
- prototype: `BOOL __stdcall(LPCWSTR lpPathName, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180063870`

## callees

- `0x180072fe0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180072fff`
- `ntdll!RtlGetCurrentTransaction` at `0x180072fff`
- `ntdll!RtlSetCurrentTransaction` at `0x180073028`
- `ntdll!RtlSetCurrentTransaction` at `0x180073048`
- `ntdll!RtlSetCurrentTransaction` at `0x180073028`
- `ntdll!RtlSetCurrentTransaction` at `0x180073048`
- `ntdll!RtlSetLastWin32Error` at `0x180073017`
- `ntdll!RtlSetLastWin32Error` at `0x18007305b`
- `ntdll!RtlSetLastWin32Error` at `0x180073017`
- `ntdll!RtlSetLastWin32Error` at `0x18007305b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180073038`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180073038`

## pseudocode

```c
BOOL __stdcall RemoveDirectoryTransactedW(LPCWSTR lpPathName, HANDLE hTransaction)
{
  BOOL v4; // ebx

  if ( (char *)hTransaction - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    RtlSetLastWin32Error(0x1A2Cu);
    return 0;
  }
  else
  {
    v4 = 0;
    if ( RtlGetCurrentTransaction() )
    {
      RtlSetLastWin32Error(0x1A45u);
    }
    else
    {
      RtlSetCurrentTransaction(hTransaction);
      v4 = RemoveDirectoryW(lpPathName);
      RtlSetCurrentTransaction(0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180072fe0  mov     [rsp+arg_0], rbx
0x180072fe5  mov     [rsp+arg_8], rsi
0x180072fea  push    rdi
0x180072feb  sub     rsp, 20h
0x180072fef  mov     rdi, rdx
0x180072ff2  mov     rsi, rcx
0x180072ff5  lea     rax, [rdx-1]
0x180072ff9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180072ffd  ja      short loc_180073056
0x180072fff  call    cs:__imp_RtlGetCurrentTransaction
0x180073006  nop     dword ptr [rax+rax+00h]
0x18007300b  xor     ebx, ebx
0x18007300d  test    rax, rax
0x180073010  jz      short loc_180073025
0x180073012  mov     ecx, 1A45h; LastError
0x180073017  call    cs:__imp_RtlSetLastWin32Error
0x18007301e  nop     dword ptr [rax+rax+00h]
0x180073023  jmp     short loc_180073069
0x180073025  mov     rcx, rdi
0x180073028  call    cs:__imp_RtlSetCurrentTransaction
0x18007302f  nop     dword ptr [rax+rax+00h]
0x180073034  nop
0x180073035  mov     rcx, rsi; lpPathName
0x180073038  call    cs:__imp_RemoveDirectoryW
0x18007303f  nop     dword ptr [rax+rax+00h]
0x180073044  mov     ebx, eax
0x180073046  xor     ecx, ecx
0x180073048  call    cs:__imp_RtlSetCurrentTransaction
0x18007304f  nop     dword ptr [rax+rax+00h]
0x180073054  jmp     short loc_180073069
0x180073056  mov     ecx, 1A2Ch; LastError
0x18007305b  call    cs:__imp_RtlSetLastWin32Error
0x180073062  nop     dword ptr [rax+rax+00h]
0x180073067  xor     ebx, ebx
0x180073069  mov     eax, ebx
0x18007306b  mov     rbx, [rsp+28h+arg_0]
0x180073070  mov     rsi, [rsp+28h+arg_8]
0x180073075  add     rsp, 20h
0x180073079  pop     rdi
0x18007307a  retn
0x18008385c  push    rbp
0x18008385e  sub     rsp, 20h
0x180083862  mov     rbp, rdx
0x180083865  xor     ecx, ecx
0x180083867  add     rsp, 20h
0x18008386b  pop     rbp
0x18008386c  jmp     cs:__imp_RtlSetCurrentTransaction
```
