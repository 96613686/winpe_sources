# AdjustTokenPrivileges(ushort const * *,int,bool,ulong,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x18007bf24`
- end: `0x18007c0c5`
- name: `?AdjustTokenPrivileges@@YA_NPEAPEBGH_NKPEAU_TOKEN_PRIVILEGES@@PEAK@Z`
- size: `417`
- prototype: `bool __fastcall(const unsigned __int16 **, int, bool, unsigned int, PTOKEN_PRIVILEGES NewState, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18007b9e8`
- `0x180140058`
- `0x180153a58`
- `0x1801b9670`

## callees

- `0x18007bf24`
- `0x180265240`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18007bf88`
- `ADVAPI32!OpenThreadToken` at `0x18007bf88`
- `ADVAPI32!OpenProcessToken` at `0x18007bfc4`
- `ADVAPI32!OpenProcessToken` at `0x18007bfc4`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18007c001`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18007c001`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18007c045`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18007c045`
- `KERNEL32!CloseHandle` at `0x18007c055`
- `KERNEL32!CloseHandle` at `0x18007c0b5`
- `KERNEL32!CloseHandle` at `0x18007c055`
- `KERNEL32!CloseHandle` at `0x18007c0b5`
- `KERNEL32!GetLastError` at `0x18007bf98`
- `KERNEL32!GetLastError` at `0x18007c061`
- `KERNEL32!GetLastError` at `0x18007bf98`
- `KERNEL32!GetLastError` at `0x18007c061`
- `KERNEL32!GetCurrentThread` at `0x18007bf6a`
- `KERNEL32!GetCurrentThread` at `0x18007bf6a`
- `KERNEL32!GetCurrentProcess` at `0x18007bfaf`
- `KERNEL32!GetCurrentProcess` at `0x18007bfaf`

## pseudocode

```c
bool __fastcall AdjustTokenPrivileges(
        const unsigned __int16 **a1,
        signed int a2,
        unsigned __int8 a3,
        DWORD a4,
        PTOKEN_PRIVILEGES NewState,
        unsigned int *ReturnLength)
{
  int v8; // r15d
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int i; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  const unsigned __int16 **v14; // [rsp+38h] [rbp-48h]
  struct _TOKEN_PRIVILEGES v15[3]; // [rsp+40h] [rbp-40h] BYREF

  v8 = a3;
  v14 = a1;
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
  if ( (_BYTE)v8 || !NewState )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= a2 )
      {
        v15[0].PrivilegeCount = a2;
        AdjustTokenPrivileges(TokenHandle, 0, v15, a4, NewState, ReturnLength);
        goto LABEL_11;
      }
      if ( !LookupPrivilegeValueW(0, v14[i], &v15[0].Privileges[i].Luid) )
        break;
      v15[0].Privileges[i].Attributes = 2 * v8;
    }
    CloseHandle(TokenHandle);
    return 0;
  }
  AdjustTokenPrivileges(TokenHandle, 0, NewState, *ReturnLength, 0, 0);
LABEL_11:
  CloseHandle(TokenHandle);
  return GetLastError() == 0;
}

```

## disassembly

```asm
0x18007bf24  mov     [rsp-38h+arg_8], rbx
0x18007bf29  push    rbp
0x18007bf2a  push    rsi
0x18007bf2b  push    rdi
0x18007bf2c  push    r12
0x18007bf2e  push    r13
0x18007bf30  push    r14
0x18007bf32  push    r15
0x18007bf34  mov     rbp, rsp
0x18007bf37  sub     rsp, 80h
0x18007bf3e  mov     rax, cs:__security_cookie
0x18007bf45  xor     rax, rsp
0x18007bf48  mov     [rbp+var_10], rax
0x18007bf4c  mov     rdi, [rbp+NewState]
0x18007bf50  mov     r13d, r9d
0x18007bf53  mov     r14, [rbp+arg_28]
0x18007bf57  mov     r12d, edx
0x18007bf5a  movzx   r15d, r8b
0x18007bf5e  mov     [rbp+var_48], rcx
0x18007bf62  mov     [rbp+TokenHandle], 0
0x18007bf6a  call    cs:__imp_GetCurrentThread
0x18007bf71  nop     dword ptr [rax+rax+00h]
0x18007bf76  mov     ebx, 28h ; '('
0x18007bf7b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18007bf7f  mov     rcx, rax; ThreadHandle
0x18007bf82  mov     edx, ebx; DesiredAccess
0x18007bf84  lea     r8d, [rbx-27h]; OpenAsSelf
0x18007bf88  call    cs:__imp_OpenThreadToken
0x18007bf8f  nop     dword ptr [rax+rax+00h]
0x18007bf94  test    eax, eax
0x18007bf96  jnz     short loc_18007BFD8
0x18007bf98  call    cs:__imp_GetLastError
0x18007bf9f  nop     dword ptr [rax+rax+00h]
0x18007bfa4  cmp     eax, 3F0h
0x18007bfa9  jnz     loc_18007C0C1
0x18007bfaf  call    cs:__imp_GetCurrentProcess
0x18007bfb6  nop     dword ptr [rax+rax+00h]
0x18007bfbb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007bfbf  mov     edx, ebx; DesiredAccess
0x18007bfc1  mov     rcx, rax; ProcessHandle
0x18007bfc4  call    cs:__imp_OpenProcessToken
0x18007bfcb  nop     dword ptr [rax+rax+00h]
0x18007bfd0  test    eax, eax
0x18007bfd2  jz      loc_18007C0C1
0x18007bfd8  test    r15b, r15b
0x18007bfdb  jz      short loc_18007C022
0x18007bfdd  xor     ebx, ebx
0x18007bfdf  cmp     ebx, r12d
0x18007bfe2  jge     loc_18007C09A
0x18007bfe8  mov     rax, [rbp+var_48]
0x18007bfec  lea     r8, [rbp+var_3C]
0x18007bff0  movsxd  rdx, ebx
0x18007bff3  xor     ecx, ecx; lpSystemName
0x18007bff5  lea     rsi, [rdx+rdx*2]
0x18007bff9  mov     rdx, [rax+rdx*8]; lpName
0x18007bffd  lea     r8, [r8+rsi*4]; lpLuid
0x18007c001  call    cs:__imp_LookupPrivilegeValueW
0x18007c008  nop     dword ptr [rax+rax+00h]
0x18007c00d  test    eax, eax
0x18007c00f  jz      loc_18007C0B1
0x18007c015  mov     eax, r15d
0x18007c018  add     eax, eax
0x18007c01a  mov     [rbp+rsi*4+var_34], eax
0x18007c01e  inc     ebx
0x18007c020  jmp     short loc_18007BFDF
0x18007c022  test    rdi, rdi
0x18007c025  jz      short loc_18007BFDD
0x18007c027  mov     r9d, [r14]; BufferLength
0x18007c02a  mov     r8, rdi; NewState
0x18007c02d  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x18007c036  mov     [rsp+80h+PreviousState], 0; PreviousState
0x18007c03f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007c043  xor     edx, edx; DisableAllPrivileges
0x18007c045  call    cs:__imp_AdjustTokenPrivileges
0x18007c04c  nop     dword ptr [rax+rax+00h]
0x18007c051  mov     rcx, [rbp+TokenHandle]; hObject
0x18007c055  call    cs:__imp_CloseHandle
0x18007c05c  nop     dword ptr [rax+rax+00h]
0x18007c061  call    cs:__imp_GetLastError
0x18007c068  nop     dword ptr [rax+rax+00h]
0x18007c06d  test    eax, eax
0x18007c06f  setz    al
0x18007c072  mov     rcx, [rbp+var_10]
0x18007c076  xor     rcx, rsp; StackCookie
0x18007c079  call    __security_check_cookie
0x18007c07e  mov     rbx, [rsp+80h+arg_8]
0x18007c086  add     rsp, 80h
0x18007c08d  pop     r15
0x18007c08f  pop     r14
0x18007c091  pop     r13
0x18007c093  pop     r12
0x18007c095  pop     rdi
0x18007c096  pop     rsi
0x18007c097  pop     rbp
0x18007c098  retn
0x18007c09a  mov     [rsp+80h+ReturnLength], r14
0x18007c09f  lea     r8, [rbp+var_40]
0x18007c0a3  mov     [rsp+80h+PreviousState], rdi
0x18007c0a8  mov     r9d, r13d
0x18007c0ab  mov     [rbp+var_40], r12d
0x18007c0af  jmp     short loc_18007C03F
0x18007c0b1  mov     rcx, [rbp+TokenHandle]; hObject
0x18007c0b5  call    cs:__imp_CloseHandle
0x18007c0bc  nop     dword ptr [rax+rax+00h]
0x18007c0c1  xor     al, al
0x18007c0c3  jmp     short loc_18007C072
```
