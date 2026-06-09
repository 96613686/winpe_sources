# AdjustTokenPrivileges(ushort const * *,int,bool,ulong,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x140003ce4`
- end: `0x140003dff`
- name: `?AdjustTokenPrivileges@@YA_NPEAPEBGH_NKPEAU_TOKEN_PRIVILEGES@@PEAK@Z`
- size: `283`
- prototype: `bool __fastcall(const unsigned __int16 **, signed int, __int64, __int64, PTOKEN_PRIVILEGES PreviousState, PDWORD ReturnLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006d4c`

## callees

- `0x140003ce4`
- `0x140009820`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140003d37`
- `ADVAPI32!OpenThreadToken` at `0x140003d37`
- `ADVAPI32!OpenProcessToken` at `0x140003d5e`
- `ADVAPI32!OpenProcessToken` at `0x140003d5e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140003dc9`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140003dc9`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140003d84`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140003d84`
- `KERNEL32!GetCurrentProcess` at `0x140003d4e`
- `KERNEL32!GetCurrentProcess` at `0x140003d4e`
- `KERNEL32!GetLastError` at `0x140003d41`
- `KERNEL32!GetLastError` at `0x140003dda`
- `KERNEL32!GetLastError` at `0x140003d41`
- `KERNEL32!GetLastError` at `0x140003dda`
- `KERNEL32!GetCurrentThread` at `0x140003d1e`
- `KERNEL32!GetCurrentThread` at `0x140003d1e`
- `KERNEL32!CloseHandle` at `0x140003d9f`
- `KERNEL32!CloseHandle` at `0x140003dd4`
- `KERNEL32!CloseHandle` at `0x140003d9f`
- `KERNEL32!CloseHandle` at `0x140003dd4`

## pseudocode

```c
bool __fastcall AdjustTokenPrivileges(
        const unsigned __int16 **a1,
        signed int a2,
        __int64 a3,
        __int64 a4,
        PTOKEN_PRIVILEGES PreviousState,
        PDWORD ReturnLength)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int i; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-78h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-70h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
      return 0;
  }
  for ( i = 0; i < a2; ++i )
  {
    if ( !LookupPrivilegeValueW(0, a1[i], &NewState.Privileges[i].Luid) )
    {
      CloseHandle(TokenHandle);
      return 0;
    }
    NewState.Privileges[i].Attributes = 2;
  }
  NewState.PrivilegeCount = a2;
  AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x30u, PreviousState, ReturnLength);
  CloseHandle(TokenHandle);
  return GetLastError() == 0;
}

```

## disassembly

```asm
0x140003ce4  push    rbx
0x140003ce6  push    rbp
0x140003ce7  push    rsi
0x140003ce8  push    rdi
0x140003ce9  push    r14
0x140003ceb  push    r15
0x140003ced  sub     rsp, 78h
0x140003cf1  mov     rax, cs:__security_cookie
0x140003cf8  xor     rax, rsp
0x140003cfb  mov     [rsp+0A8h+var_40], rax
0x140003d00  mov     rbp, [rsp+0A8h+arg_20]
0x140003d08  mov     esi, edx
0x140003d0a  mov     r14, [rsp+0A8h+arg_28]
0x140003d12  mov     r15, rcx
0x140003d15  mov     [rsp+0A8h+TokenHandle], 0
0x140003d1e  call    cs:__imp_GetCurrentThread
0x140003d24  mov     ebx, 28h ; '('
0x140003d29  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x140003d2e  mov     rcx, rax; ThreadHandle
0x140003d31  mov     edx, ebx; DesiredAccess
0x140003d33  lea     r8d, [rbx-27h]; OpenAsSelf
0x140003d37  call    cs:__imp_OpenThreadToken
0x140003d3d  test    eax, eax
0x140003d3f  jnz     short loc_140003D68
0x140003d41  call    cs:__imp_GetLastError
0x140003d47  cmp     eax, 3F0h
0x140003d4c  jnz     short loc_140003DA5
0x140003d4e  call    cs:__imp_GetCurrentProcess
0x140003d54  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x140003d59  mov     edx, ebx; DesiredAccess
0x140003d5b  mov     rcx, rax; ProcessHandle
0x140003d5e  call    cs:__imp_OpenProcessToken
0x140003d64  test    eax, eax
0x140003d66  jz      short loc_140003DA5
0x140003d68  xor     ebx, ebx
0x140003d6a  cmp     ebx, esi
0x140003d6c  jge     short loc_140003DA9
0x140003d6e  movsxd  rdx, ebx
0x140003d71  lea     r8, [rsp+0A8h+NewState.Privileges]
0x140003d76  xor     ecx, ecx; lpSystemName
0x140003d78  lea     rdi, [rdx+rdx*2]
0x140003d7c  mov     rdx, [r15+rdx*8]; lpName
0x140003d80  lea     r8, [r8+rdi*4]; lpLuid
0x140003d84  call    cs:__imp_LookupPrivilegeValueW
0x140003d8a  test    eax, eax
0x140003d8c  jz      short loc_140003D9A
0x140003d8e  mov     [rsp+rdi*4+0A8h+NewState.Privileges.Attributes], 2
0x140003d96  inc     ebx
0x140003d98  jmp     short loc_140003D6A
0x140003d9a  mov     rcx, [rsp+0A8h+TokenHandle]; hObject
0x140003d9f  call    cs:__imp_CloseHandle
0x140003da5  xor     al, al
0x140003da7  jmp     short loc_140003DE5
0x140003da9  mov     rcx, [rsp+0A8h+TokenHandle]; TokenHandle
0x140003dae  lea     r8, [rsp+0A8h+NewState]; NewState
0x140003db3  mov     [rsp+0A8h+ReturnLength], r14; ReturnLength
0x140003db8  mov     r9d, 30h ; '0'; BufferLength
0x140003dbe  xor     edx, edx; DisableAllPrivileges
0x140003dc0  mov     [rsp+0A8h+PreviousState], rbp; PreviousState
0x140003dc5  mov     [rsp+0A8h+NewState.PrivilegeCount], esi
0x140003dc9  call    cs:__imp_AdjustTokenPrivileges
0x140003dcf  mov     rcx, [rsp+0A8h+TokenHandle]; hObject
0x140003dd4  call    cs:__imp_CloseHandle
0x140003dda  call    cs:__imp_GetLastError
0x140003de0  test    eax, eax
0x140003de2  setz    al
0x140003de5  mov     rcx, [rsp+0A8h+var_40]
0x140003dea  xor     rcx, rsp; StackCookie
0x140003ded  call    __security_check_cookie
0x140003df2  add     rsp, 78h
0x140003df6  pop     r15
0x140003df8  pop     r14
0x140003dfa  pop     rdi
0x140003dfb  pop     rsi
0x140003dfc  pop     rbp
0x140003dfd  pop     rbx
0x140003dfe  retn
```
