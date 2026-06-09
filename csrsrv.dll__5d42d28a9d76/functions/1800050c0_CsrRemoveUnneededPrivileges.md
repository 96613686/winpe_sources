# CsrRemoveUnneededPrivileges

- ea: `0x1800050c0`
- end: `0x18000516c`
- name: `CsrRemoveUnneededPrivileges`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004a20`

## callees

- `0x1800050c0`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x180005137`
- `ntdll!NtAdjustPrivilegesToken` at `0x180005137`
- `ntdll!NtOpenProcessToken` at `0x1800050f5`
- `ntdll!NtOpenProcessToken` at `0x1800050f5`
- `ntdll!NtClose` at `0x18000514a`
- `ntdll!NtClose` at `0x18000514a`

## pseudocode

```c
NTSTATUS CsrRemoveUnneededPrivileges()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState = 0;
  result = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2000000u, &TokenHandle);
  if ( result >= 0 )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)31LL;
    NewState.Privileges[0].Attributes = 4;
    v1 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0, 0, 0);
    NtClose(TokenHandle);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800050c0  push    rbx
0x1800050c2  sub     rsp, 50h
0x1800050c6  mov     rax, cs:__security_cookie
0x1800050cd  xor     rax, rsp
0x1800050d0  mov     [rsp+58h+var_10], rax
0x1800050d5  xorps   xmm0, xmm0
0x1800050d8  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800050dd  xor     ebx, ebx
0x1800050df  mov     edx, 2000000h; DesiredAccess
0x1800050e4  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800050eb  mov     [rsp+58h+TokenHandle], rbx
0x1800050f0  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x1800050f5  call    cs:__imp_NtOpenProcessToken
0x1800050fc  nop     dword ptr [rax+rax+00h]
0x180005101  test    eax, eax
0x180005103  js      short loc_180005158
0x180005105  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000510a  lea     r8, [rsp+58h+NewState]; NewState
0x18000510f  mov     [rsp+58h+ReturnLength], rbx; ReturnLength
0x180005114  xor     r9d, r9d; BufferLength
0x180005117  xor     edx, edx; DisableAllPrivileges
0x180005119  mov     [rsp+58h+PreviousState], rbx; PreviousState
0x18000511e  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x180005126  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 1Fh
0x18000512f  mov     [rsp+58h+NewState.Privileges.Attributes], 4
0x180005137  call    cs:__imp_NtAdjustPrivilegesToken
0x18000513e  nop     dword ptr [rax+rax+00h]
0x180005143  mov     rcx, [rsp+58h+TokenHandle]; Handle
0x180005148  mov     ebx, eax
0x18000514a  call    cs:__imp_NtClose
0x180005151  nop     dword ptr [rax+rax+00h]
0x180005156  mov     eax, ebx
0x180005158  mov     rcx, [rsp+58h+var_10]
0x18000515d  xor     rcx, rsp; StackCookie
0x180005160  call    __security_check_cookie
0x180005165  add     rsp, 50h
0x180005169  pop     rbx
0x18000516a  retn
```
