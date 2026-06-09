# NfsDeviceOpen

- ea: `0x18002c904`
- end: `0x18002c95e`
- name: `NfsDeviceOpen`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002bfe0`
- `0x18002c288`
- `0x18002c874`

## callees

- `0x18002c904`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c940`
- `KERNEL32!GetLastError` at `0x18002c940`
- `KERNEL32!CreateFileW` at `0x18002c92e`
- `KERNEL32!CreateFileW` at `0x18002c92e`

## pseudocode

```c
__int64 __fastcall NfsDeviceOpen(const WCHAR *a1, DWORD a2, __int64 *a3)
{
  DWORD LastError; // ebx
  __int64 v5; // rdi
  HANDLE FileW; // rsi

  LastError = 0;
  v5 = -1;
  FileW = CreateFileW(a1, a2, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW != (HANDLE)-1LL || (LastError = GetLastError()) == 0 )
    v5 = (__int64)FileW;
  *a3 = v5;
  return LastError;
}

```

## disassembly

```asm
0x18002c904  push    rbx
0x18002c906  push    rsi
0x18002c907  push    rdi
0x18002c908  push    r14
0x18002c90a  sub     rsp, 48h
0x18002c90e  mov     r14, r8
0x18002c911  xor     ebx, ebx
0x18002c913  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18002c918  xor     r9d, r9d; lpSecurityAttributes
0x18002c91b  mov     [rsp+68h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x18002c923  xor     r8d, r8d; dwShareMode
0x18002c926  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c92e  call    cs:__imp_CreateFileW
0x18002c934  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c938  mov     rsi, rax
0x18002c93b  cmp     rax, rdi
0x18002c93e  jnz     short loc_18002C94C
0x18002c940  call    cs:__imp_GetLastError
0x18002c946  mov     ebx, eax
0x18002c948  test    eax, eax
0x18002c94a  jnz     short loc_18002C94F
0x18002c94c  mov     rdi, rsi
0x18002c94f  mov     [r14], rdi
0x18002c952  mov     eax, ebx
0x18002c954  add     rsp, 48h
0x18002c958  pop     r14
0x18002c95a  pop     rdi
0x18002c95b  pop     rsi
0x18002c95c  pop     rbx
0x18002c95d  retn
```
