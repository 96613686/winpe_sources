# IsAuditPrivilegeEnabled(int,int *)

- ea: `0x1800bbc0c`
- end: `0x1800bbd31`
- name: `?IsAuditPrivilegeEnabled@@YAHHPEAH@Z`
- size: `293`
- prototype: `__int64 __fastcall(int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800bbd38`

## callees

- `0x1800bbc0c`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x1800bbcd7`
- `ntdll!NtPrivilegeCheck` at `0x1800bbcd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbc8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bbc9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bbc9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbc84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbc84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbc72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbc72`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bbcaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bbcaa`

## pseudocode

```c
__int64 __fastcall IsAuditPrivilegeEnabled(int a1, int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  NTSTATUS v7; // ebx
  unsigned __int8 Result[8]; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  TokenHandle = 0;
  Result[0] = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( a1 )
  {
    if ( SIDCache.SubAuthority[0] )
    {
      *a2 = SIDCache.SubAuthority[0] != 1;
      return 1;
    }
LABEL_7:
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return 0;
    goto LABEL_8;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    goto LABEL_7;
  }
LABEL_8:
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)21LL;
  RequiredPrivileges.Privilege[0].Attributes = 2;
  v7 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
  CloseHandle(TokenHandle);
  if ( v7 >= 0 )
  {
    if ( a1 )
      SIDCache.SubAuthority[0] = (Result[0] != 0) + 1;
    *a2 = Result[0];
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bbc0c  mov     [rsp-18h+arg_0], rbx
0x1800bbc11  mov     [rsp-18h+arg_10], rsi
0x1800bbc16  push    rbp
0x1800bbc17  push    rdi
0x1800bbc18  push    r15
0x1800bbc1a  mov     rbp, rsp
0x1800bbc1d  sub     rsp, 50h
0x1800bbc21  mov     rax, cs:__security_cookie
0x1800bbc28  xor     rax, rsp
0x1800bbc2b  mov     [rbp+var_8], rax
0x1800bbc2f  xor     eax, eax
0x1800bbc31  mov     [rbp+TokenHandle], 0
0x1800bbc39  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1800bbc3c  xorps   xmm0, xmm0
0x1800bbc3f  mov     [rbp+Result], al
0x1800bbc42  mov     rdi, rdx
0x1800bbc45  mov     esi, ecx
0x1800bbc47  lea     ebx, [rax+8]
0x1800bbc4a  lea     r15d, [rax+1]
0x1800bbc4e  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x1800bbc52  test    ecx, ecx
0x1800bbc54  jz      short loc_1800BBC72
0x1800bbc56  mov     edx, cs:?SIDCache@@3PEAVSID_CACHE@@EA.SubAuthority; SID_CACHE * SIDCache ...
0x1800bbc5c  test    edx, edx
0x1800bbc5e  jz      short loc_1800BBC9B
0x1800bbc60  xor     ecx, ecx
0x1800bbc62  cmp     edx, r15d
0x1800bbc65  setnz   cl
0x1800bbc68  mov     [rdi], ecx
0x1800bbc6a  mov     eax, r15d
0x1800bbc6d  jmp     loc_1800BBD10
0x1800bbc72  call    cs:__imp_GetCurrentThread
0x1800bbc78  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bbc7c  mov     r8d, r15d; OpenAsSelf
0x1800bbc7f  mov     rcx, rax; ThreadHandle
0x1800bbc82  mov     edx, ebx; DesiredAccess
0x1800bbc84  call    cs:__imp_OpenThreadToken
0x1800bbc8a  test    eax, eax
0x1800bbc8c  jnz     short loc_1800BBCB4
0x1800bbc8e  call    cs:__imp_GetLastError
0x1800bbc94  cmp     eax, 3F0h
0x1800bbc99  jnz     short loc_1800BBD0E
0x1800bbc9b  call    cs:__imp_GetCurrentProcess
0x1800bbca1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800bbca5  mov     edx, ebx; DesiredAccess
0x1800bbca7  mov     rcx, rax; ProcessHandle
0x1800bbcaa  call    cs:__imp_OpenProcessToken
0x1800bbcb0  test    eax, eax
0x1800bbcb2  jz      short loc_1800BBD0E
0x1800bbcb4  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800bbcb8  lea     r8, [rbp+Result]; Result
0x1800bbcbc  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800bbcc0  mov     [rbp+RequiredPrivileges.PrivilegeCount], r15d
0x1800bbcc4  mov     [rbp+RequiredPrivileges.Control], r15d
0x1800bbcc8  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 15h
0x1800bbcd0  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x1800bbcd7  call    cs:__imp_NtPrivilegeCheck
0x1800bbcdd  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bbce1  mov     ebx, eax
0x1800bbce3  call    cs:__imp_CloseHandle
0x1800bbce9  test    ebx, ebx
0x1800bbceb  js      short loc_1800BBD0E
0x1800bbced  test    esi, esi
0x1800bbcef  jz      short loc_1800BBD03
0x1800bbcf1  mov     al, [rbp+Result]
0x1800bbcf4  neg     al
0x1800bbcf6  sbb     ecx, ecx
0x1800bbcf8  neg     ecx
0x1800bbcfa  add     ecx, r15d
0x1800bbcfd  mov     cs:?SIDCache@@3PEAVSID_CACHE@@EA.SubAuthority, ecx; SID_CACHE * SIDCache ...
0x1800bbd03  movzx   eax, [rbp+Result]
0x1800bbd07  mov     [rdi], eax
0x1800bbd09  jmp     loc_1800BBC6A
0x1800bbd0e  xor     eax, eax
0x1800bbd10  mov     rcx, [rbp+var_8]
0x1800bbd14  xor     rcx, rsp; StackCookie
0x1800bbd17  call    __security_check_cookie
0x1800bbd1c  lea     r11, [rsp+50h+var_s0]
0x1800bbd21  mov     rbx, [r11+20h]
0x1800bbd25  mov     rsi, [r11+30h]
0x1800bbd29  mov     rsp, r11
0x1800bbd2c  pop     r15
0x1800bbd2e  pop     rdi
0x1800bbd2f  pop     rbp
0x1800bbd30  retn
```
