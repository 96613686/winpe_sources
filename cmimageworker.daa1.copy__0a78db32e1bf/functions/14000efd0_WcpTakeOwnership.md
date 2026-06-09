# WcpTakeOwnership

- ea: `0x14000efd0`
- end: `0x14000f0cd`
- name: `WcpTakeOwnership`
- size: `253`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x14000e5a8`
- `0x14000ecc4`

## callees

- `0x14000e284`
- `0x14000efd0`
- `0x14000fa88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f02c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000f004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000f004`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000f01c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000f01c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f0b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f0b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f0a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f0a1`

## pseudocode

```c
__int64 __fastcall WcpTakeOwnership(LPWSTR pObjectName)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // r8
  signed int LastError; // eax
  int v5; // ebx
  NTSTATUS v6; // ebx
  __int64 v7; // r8
  HLOCAL hMem; // [rsp+20h] [rbp-10h] BYREF
  PACL ppDacl; // [rsp+28h] [rbp-8h] BYREF
  int v11; // [rsp+58h] [rbp+28h] BYREF
  int v12; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  ppDacl = 0;
  v11 = 0;
  v12 = 0;
  TokenHandle = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v6 = WcpSetPrivilege(TokenHandle, 9, v3, &v11);
    if ( v6 < 0 || (v6 = WcpSetPrivilege(TokenHandle, 18, v7, &v12), v6 < 0) )
    {
      v5 = v6 | 0x10000000;
    }
    else
    {
      v5 = WcGrantFullAccessToAdmin(pObjectName, &ppDacl, &hMem);
      if ( v5 >= 0 )
        v5 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000efd0  push    rbp
0x14000efd2  push    rbx
0x14000efd3  push    rdi
0x14000efd4  mov     rbp, rsp
0x14000efd7  sub     rsp, 30h
0x14000efdb  mov     rdi, rcx
0x14000efde  mov     [rbp+ppDacl], 0
0x14000efe6  mov     [rbp+arg_8], 0
0x14000efed  mov     [rbp+arg_10], 0
0x14000eff4  mov     [rbp+TokenHandle], 0
0x14000effc  mov     [rbp+hMem], 0
0x14000f004  call    cs:__imp_GetCurrentProcess
0x14000f00b  nop     dword ptr [rax+rax+00h]
0x14000f010  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000f014  mov     edx, 28h ; '('; DesiredAccess
0x14000f019  mov     rcx, rax; ProcessHandle
0x14000f01c  call    cs:__imp_OpenProcessToken
0x14000f023  nop     dword ptr [rax+rax+00h]
0x14000f028  test    eax, eax
0x14000f02a  jnz     short loc_14000F049
0x14000f02c  call    cs:__imp_GetLastError
0x14000f033  nop     dword ptr [rax+rax+00h]
0x14000f038  mov     ebx, eax
0x14000f03a  test    eax, eax
0x14000f03c  jle     short loc_14000F098
0x14000f03e  movzx   ebx, ax
0x14000f041  or      ebx, 80070000h
0x14000f047  jmp     short loc_14000F098
0x14000f049  mov     rcx, [rbp+TokenHandle]
0x14000f04d  lea     r9, [rbp+arg_8]
0x14000f051  mov     edx, 9
0x14000f056  call    WcpSetPrivilege
0x14000f05b  mov     ebx, eax
0x14000f05d  test    eax, eax
0x14000f05f  jns     short loc_14000F067
0x14000f061  bts     ebx, 1Ch
0x14000f065  jmp     short loc_14000F098
0x14000f067  mov     rcx, [rbp+TokenHandle]
0x14000f06b  lea     r9, [rbp+arg_10]
0x14000f06f  mov     edx, 12h
0x14000f074  call    WcpSetPrivilege
0x14000f079  mov     ebx, eax
0x14000f07b  test    eax, eax
0x14000f07d  js      short loc_14000F061
0x14000f07f  lea     r8, [rbp+hMem]; ppSecurityDescriptor
0x14000f083  mov     rcx, rdi; pObjectName
0x14000f086  lea     rdx, [rbp+ppDacl]; ppDacl
0x14000f08a  call    WcGrantFullAccessToAdmin
0x14000f08f  mov     ebx, eax
0x14000f091  xor     eax, eax
0x14000f093  test    ebx, ebx
0x14000f095  cmovns  ebx, eax
0x14000f098  mov     rcx, [rbp+hMem]; hMem
0x14000f09c  test    rcx, rcx
0x14000f09f  jz      short loc_14000F0AD
0x14000f0a1  call    cs:__imp_LocalFree
0x14000f0a8  nop     dword ptr [rax+rax+00h]
0x14000f0ad  mov     rcx, [rbp+TokenHandle]; hObject
0x14000f0b1  test    rcx, rcx
0x14000f0b4  jz      short loc_14000F0C2
0x14000f0b6  call    cs:__imp_CloseHandle
0x14000f0bd  nop     dword ptr [rax+rax+00h]
0x14000f0c2  mov     eax, ebx
0x14000f0c4  add     rsp, 30h
0x14000f0c8  pop     rdi
0x14000f0c9  pop     rbx
0x14000f0ca  pop     rbp
0x14000f0cb  retn
```
