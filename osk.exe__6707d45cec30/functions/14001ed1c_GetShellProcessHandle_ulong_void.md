# GetShellProcessHandle(ulong,void * *)

- ea: `0x14001ed1c`
- end: `0x14001ed85`
- name: `?GetShellProcessHandle@@YAJKPEAPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001e0e0`

## callees

- `0x14001ed1c`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x14001ed60`
- `KERNEL32!OpenProcess` at `0x14001ed60`
- `USER32!GetShellWindow` at `0x14001ed2f`
- `USER32!GetShellWindow` at `0x14001ed2f`
- `USER32!GetWindowThreadProcessId` at `0x14001ed4a`
- `USER32!GetWindowThreadProcessId` at `0x14001ed4a`

## pseudocode

```c
__int64 __fastcall GetShellProcessHandle(DWORD a1, void **a2)
{
  HWND ShellWindow; // rax
  HANDLE v4; // rax
  unsigned int v5; // ecx
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF

  dwProcessId = a1;
  *a2 = 0;
  ShellWindow = GetShellWindow();
  if ( !ShellWindow )
    return 2147500037LL;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(ShellWindow, &dwProcessId) )
    return 2147500037LL;
  v4 = OpenProcess(0x80u, 0, dwProcessId);
  v5 = 0;
  *a2 = v4;
  if ( !v4 )
    return (unsigned int)-2147467259;
  return v5;
}

```

## disassembly

```asm
0x14001ed1c  mov     [rsp+dwProcessId], ecx
0x14001ed20  push    rbx
0x14001ed21  sub     rsp, 20h
0x14001ed25  mov     rbx, rdx
0x14001ed28  mov     qword ptr [rdx], 0
0x14001ed2f  call    cs:__imp_GetShellWindow
0x14001ed35  test    rax, rax
0x14001ed38  jz      short loc_14001ED7A
0x14001ed3a  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x14001ed3f  mov     [rsp+28h+dwProcessId], 0
0x14001ed47  mov     rcx, rax; hWnd
0x14001ed4a  call    cs:__imp_GetWindowThreadProcessId
0x14001ed50  test    eax, eax
0x14001ed52  jz      short loc_14001ED7A
0x14001ed54  mov     r8d, [rsp+28h+dwProcessId]; dwProcessId
0x14001ed59  xor     edx, edx; bInheritHandle
0x14001ed5b  mov     ecx, 80h; dwDesiredAccess
0x14001ed60  call    cs:__imp_OpenProcess
0x14001ed66  xor     ecx, ecx
0x14001ed68  mov     edx, 80004005h
0x14001ed6d  test    rax, rax
0x14001ed70  mov     [rbx], rax
0x14001ed73  cmovz   ecx, edx
0x14001ed76  mov     eax, ecx
0x14001ed78  jmp     short loc_14001ED7F
0x14001ed7a  mov     eax, 80004005h
0x14001ed7f  add     rsp, 20h
0x14001ed83  pop     rbx
0x14001ed84  retn
```
