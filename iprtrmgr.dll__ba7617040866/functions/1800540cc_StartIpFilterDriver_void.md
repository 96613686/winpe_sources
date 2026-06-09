# StartIpFilterDriver(void)

- ea: `0x1800540cc`
- end: `0x180054164`
- name: `?StartIpFilterDriver@@YAKXZ`
- size: `152`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180054828`

## callees

- `0x1800540cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800540ed`
- `KERNEL32!GetLastError` at `0x180054146`
- `KERNEL32!GetLastError` at `0x1800540ed`
- `KERNEL32!GetLastError` at `0x180054146`
- `ADVAPI32!StartServiceW` at `0x180054128`
- `ADVAPI32!StartServiceW` at `0x180054128`
- `ADVAPI32!OpenSCManagerW` at `0x1800540df`
- `ADVAPI32!OpenSCManagerW` at `0x1800540df`
- `ADVAPI32!CloseServiceHandle` at `0x180054116`
- `ADVAPI32!CloseServiceHandle` at `0x180054133`
- `ADVAPI32!CloseServiceHandle` at `0x18005413c`
- `ADVAPI32!CloseServiceHandle` at `0x180054116`
- `ADVAPI32!CloseServiceHandle` at `0x180054133`
- `ADVAPI32!CloseServiceHandle` at `0x18005413c`
- `ADVAPI32!OpenServiceW` at `0x180054105`
- `ADVAPI32!OpenServiceW` at `0x180054105`

## pseudocode

```c
DWORD StartIpFilterDriver(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbp
  DWORD LastError; // edi
  BOOL started; // ebx

  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v1 = v0;
  if ( !v0 )
    return GetLastError();
  v3 = OpenServiceW(v0, L"IPFILTERDRIVER", 0xF01FFu);
  v4 = v3;
  if ( !v3 )
  {
    CloseServiceHandle(v1);
    return GetLastError();
  }
  LastError = 0;
  started = StartServiceW(v3, 0, 0);
  CloseServiceHandle(v4);
  CloseServiceHandle(v1);
  if ( started )
    return LastError;
  LastError = GetLastError();
  if ( LastError != 1056 )
    return LastError;
  else
    return 0;
}

```

## disassembly

```asm
0x1800540cc  push    rbx
0x1800540ce  push    rbp
0x1800540cf  push    rsi
0x1800540d0  push    rdi
0x1800540d1  sub     rsp, 28h
0x1800540d5  xor     edx, edx; lpDatabaseName
0x1800540d7  xor     ecx, ecx; lpMachineName
0x1800540d9  mov     r8d, 0F003Fh; dwDesiredAccess
0x1800540df  call    cs:__imp_OpenSCManagerW
0x1800540e5  mov     rsi, rax
0x1800540e8  test    rax, rax
0x1800540eb  jnz     short loc_1800540F5
0x1800540ed  call    cs:__imp_GetLastError
0x1800540f3  jmp     short loc_18005415B
0x1800540f5  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800540fb  lea     rdx, aIpfilterdriver; "IPFILTERDRIVER"
0x180054102  mov     rcx, rsi; hSCManager
0x180054105  call    cs:__imp_OpenServiceW
0x18005410b  mov     rbp, rax
0x18005410e  test    rax, rax
0x180054111  jnz     short loc_18005411E
0x180054113  mov     rcx, rsi; hSCObject
0x180054116  call    cs:__imp_CloseServiceHandle
0x18005411c  jmp     short loc_1800540ED
0x18005411e  xor     r8d, r8d; lpServiceArgVectors
0x180054121  xor     edx, edx; dwNumServiceArgs
0x180054123  mov     rcx, rbp; hService
0x180054126  xor     edi, edi
0x180054128  call    cs:__imp_StartServiceW
0x18005412e  mov     rcx, rbp; hSCObject
0x180054131  mov     ebx, eax
0x180054133  call    cs:__imp_CloseServiceHandle
0x180054139  mov     rcx, rsi; hSCObject
0x18005413c  call    cs:__imp_CloseServiceHandle
0x180054142  test    ebx, ebx
0x180054144  jnz     short loc_180054159
0x180054146  call    cs:__imp_GetLastError
0x18005414c  mov     edi, eax
0x18005414e  cmp     eax, 420h
0x180054153  jnz     short loc_180054159
0x180054155  xor     eax, eax
0x180054157  jmp     short loc_18005415B
0x180054159  mov     eax, edi
0x18005415b  add     rsp, 28h
0x18005415f  pop     rdi
0x180054160  pop     rsi
0x180054161  pop     rbp
0x180054162  pop     rbx
0x180054163  retn
```
