# LiveUserDebugServices::GetUnloadedModuleListInfo(unsigned __int64,unsigned __int64 *,ulong *,ulong *)

- ea: `0x180422ad0`
- end: `0x180422cdd`
- name: `?GetUnloadedModuleListInfo@LiveUserDebugServices@@UEAAJ_KPEA_KPEAK2@Z`
- size: `525`
- prototype: `int(LiveUserDebugServices *__hidden this, unsigned __int64, unsigned __int64 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800c2004`
- `0x1800f0f40`
- `0x180422ad0`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180422c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180422c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180422c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180422c1a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180422b89`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180422bb4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180422be1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180422b89`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180422bb4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180422be1`

## pseudocode

```c
__int64 __fastcall LiveUserDebugServices::GetUnloadedModuleListInfo(
        LiveUserDebugServices *this,
        __int64 a2,
        unsigned __int64 *a3,
        unsigned int *a4,
        unsigned int *lpBuffer)
{
  __int64 result; // rax

  *a3 = 0;
  result = 2147500034LL;
  *a4 = 0;
  *lpBuffer = 0;
  return result;
}

```

## disassembly

```asm
0x180422ad0  push    rbp
0x180422ad2  push    rbx
0x180422ad3  push    rsi
0x180422ad4  push    rdi
0x180422ad5  push    r14
0x180422ad7  lea     rbp, [rsp-90h]
0x180422adf  sub     rsp, 190h
0x180422ae6  mov     rax, cs:__security_cookie
0x180422aed  xor     rax, rsp
0x180422af0  mov     [rbp+0B0h+var_30], rax
0x180422af7  mov     rax, cs:qword_18082DD28
0x180422afe  mov     r14, r9
0x180422b01  mov     rbx, [rbp+0B0h+lpBuffer]
0x180422b08  mov     rsi, r8
0x180422b0b  mov     rdi, rdx
0x180422b0e  test    rax, rax
0x180422b11  jz      loc_180422C3B
0x180422b17  mov     [rsp+1B0h+lpBaseAddress], 0
0x180422b20  mov     [rsp+1B0h+var_170], 0
0x180422b29  mov     [rsp+1B0h+var_168], 0
0x180422b32  mov     [rsp+1B0h+Buffer], 0
0x180422b3b  mov     [rsp+1B0h+NumberOfBytesRead], 0
0x180422b44  test    rdx, rdx
0x180422b47  jnz     short loc_180422B53
0x180422b49  mov     eax, 80070057h
0x180422b4e  jmp     loc_180422CBF
0x180422b53  mov     rax, cs:qword_18082DD28
0x180422b5a  lea     r8, [rsp+1B0h+var_168]
0x180422b5f  lea     rdx, [rsp+1B0h+var_170]
0x180422b64  lea     rcx, [rsp+1B0h+lpBaseAddress]
0x180422b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180422b6e  mov     rdx, [rsp+1B0h+lpBaseAddress]; lpBaseAddress
0x180422b73  lea     rax, [rsp+1B0h+NumberOfBytesRead]
0x180422b78  mov     r9d, 4; nSize
0x180422b7e  mov     [rsp+1B0h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180422b83  mov     r8, rbx; lpBuffer
0x180422b86  mov     rcx, rdi; hProcess
0x180422b89  call    cs:__imp_ReadProcessMemory
0x180422b90  nop     dword ptr [rax+rax+00h]
0x180422b95  test    eax, eax
0x180422b97  jz      short loc_180422C00
0x180422b99  mov     rdx, [rsp+1B0h+var_170]; lpBaseAddress
0x180422b9e  lea     rax, [rsp+1B0h+NumberOfBytesRead]
0x180422ba3  mov     r9d, 4; nSize
0x180422ba9  mov     [rsp+1B0h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180422bae  mov     r8, r14; lpBuffer
0x180422bb1  mov     rcx, rdi; hProcess
0x180422bb4  call    cs:__imp_ReadProcessMemory
0x180422bbb  nop     dword ptr [rax+rax+00h]
0x180422bc0  test    eax, eax
0x180422bc2  jz      short loc_180422C00
0x180422bc4  mov     rdx, [rsp+1B0h+var_168]; lpBaseAddress
0x180422bc9  lea     rax, [rsp+1B0h+NumberOfBytesRead]
0x180422bce  mov     r9d, 8; nSize
0x180422bd4  mov     [rsp+1B0h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180422bd9  lea     r8, [rsp+1B0h+Buffer]; lpBuffer
0x180422bde  mov     rcx, rdi; hProcess
0x180422be1  call    cs:__imp_ReadProcessMemory
0x180422be8  nop     dword ptr [rax+rax+00h]
0x180422bed  test    eax, eax
0x180422bef  jz      short loc_180422C00
0x180422bf1  mov     rax, [rsp+1B0h+Buffer]
0x180422bf6  mov     [rsi], rax
0x180422bf9  xor     eax, eax
0x180422bfb  jmp     loc_180422CBF
0x180422c00  call    cs:__imp_GetLastError
0x180422c07  nop     dword ptr [rax+rax+00h]
0x180422c0c  test    eax, eax
0x180422c0e  jnz     short loc_180422C1A
0x180422c10  mov     eax, 80004005h
0x180422c15  jmp     loc_180422CBF
0x180422c1a  call    cs:__imp_GetLastError
0x180422c21  nop     dword ptr [rax+rax+00h]
0x180422c26  test    eax, eax
0x180422c28  jle     loc_180422CBF
0x180422c2e  movzx   eax, ax
0x180422c31  or      eax, 80070000h
0x180422c36  jmp     loc_180422CBF
0x180422c3b  mov     rax, cs:qword_18082DD20
0x180422c42  test    rax, rax
0x180422c45  jz      short loc_180422CA6
0x180422c47  xor     edx, edx; Val
0x180422c49  lea     rcx, [rsp+1B0h+var_150]; void *
0x180422c4e  mov     r8d, 11Ch; Size
0x180422c54  call    memset
0x180422c59  lea     rcx, [rsp+1B0h+var_150]; struct _OSVERSIONINFOEXW *
0x180422c5e  mov     dil, 1
0x180422c61  call    ?GetOsVerInfo@@YAJPEAU_OSVERSIONINFOEXW@@@Z; GetOsVerInfo(_OSVERSIONINFOEXW *)
0x180422c66  test    eax, eax
0x180422c68  jnz     short loc_180422C76
0x180422c6a  cmp     [rsp+1B0h+var_150.dwBuildNumber], 1A2Ch
0x180422c72  setb    dil
0x180422c76  mov     rax, cs:qword_18082DD20
0x180422c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180422c82  mov     [rsi], rax
0x180422c85  mov     dword ptr [r14], 10h
0x180422c8c  mov     dword ptr [rbx], 68h ; 'h'
0x180422c92  test    dil, dil
0x180422c95  jz      loc_180422BF9
0x180422c9b  mov     dword ptr [rbx], 60h ; '`'
0x180422ca1  jmp     loc_180422BF9
0x180422ca6  mov     qword ptr [r8], 0
0x180422cad  mov     eax, 80004002h
0x180422cb2  mov     dword ptr [r9], 0
0x180422cb9  mov     dword ptr [rbx], 0
0x180422cbf  mov     rcx, [rbp+0B0h+var_30]
0x180422cc6  xor     rcx, rsp; StackCookie
0x180422cc9  call    __security_check_cookie
0x180422cce  add     rsp, 190h
0x180422cd5  pop     r14
0x180422cd7  pop     rdi
0x180422cd8  pop     rsi
0x180422cd9  pop     rbx
0x180422cda  pop     rbp
0x180422cdb  retn
```
