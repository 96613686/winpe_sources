# RegSecCheckRemotePerfAccess

- ea: `0x1800180b4`
- end: `0x1800181e6`
- name: `RegSecCheckRemotePerfAccess`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a8d0`

## callees

- `0x180007740`
- `0x1800180b4`
- `0x1800181ec`

## import_xrefs

- `ntdll!NtAccessCheck` at `0x180018199`
- `ntdll!NtAccessCheck` at `0x180018199`
- `ntdll!NtOpenThreadToken` at `0x180018118`
- `ntdll!NtOpenThreadToken` at `0x180018118`
- `ntdll!NtClose` at `0x1800181bd`
- `ntdll!NtClose` at `0x1800181bd`
- `ntdll!RtlFreeHeap` at `0x180018134`
- `ntdll!RtlFreeHeap` at `0x1800181b3`
- `ntdll!RtlFreeHeap` at `0x180018134`
- `ntdll!RtlFreeHeap` at `0x1800181b3`

## pseudocode

```c
_BOOL8 RegSecCheckRemotePerfAccess()
{
  PSECURITY_DESCRIPTOR PerfGateSD; // rdi
  NTSTATUS v2; // ebx
  ULONG ReturnLength; // [rsp+40h] [rbp-29h] BYREF
  int AccessStatus; // [rsp+44h] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-19h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-9h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  PerfGateSD = RegSecGetPerfGateSD();
  if ( !PerfGateSD )
    return 0;
  if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle) < 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, PerfGateSD);
    return 0;
  }
  ReturnLength = 68;
  v2 = NtAccessCheck(
         PerfGateSD,
         TokenHandle,
         0x2000000u,
         &RemoteRegistryMappings,
         &PrivilegeSet,
         &ReturnLength,
         &GrantedAccess,
         &AccessStatus);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, PerfGateSD);
  NtClose(TokenHandle);
  if ( v2 < 0 || AccessStatus < 0 )
    return 0;
  return (GrantedAccess & 3) != 0;
}

```

## disassembly

```asm
0x1800180b4  mov     [rsp-8+arg_0], rbx
0x1800180b9  mov     [rsp-8+arg_8], rdi
0x1800180be  push    rbp
0x1800180bf  lea     rbp, [rsp-57h]
0x1800180c4  sub     rsp, 0C0h
0x1800180cb  mov     rax, cs:__security_cookie
0x1800180d2  xor     rax, rsp
0x1800180d5  mov     [rbp+57h+var_10], rax
0x1800180d9  mov     [rbp+57h+var_78], 0
0x1800180e0  mov     [rbp+57h+var_7C], 0
0x1800180e7  mov     [rbp+57h+TokenHandle], 0
0x1800180ef  mov     [rbp+57h+var_80], 0
0x1800180f6  call    RegSecGetPerfGateSD
0x1800180fb  mov     rdi, rax
0x1800180fe  test    rax, rax
0x180018101  jz      short loc_18001813A
0x180018103  mov     ebx, 2000000h
0x180018108  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001810c  mov     edx, ebx; DesiredAccess
0x18001810e  mov     r8b, 1; OpenAsSelf
0x180018111  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180018118  call    cs:__imp_NtOpenThreadToken
0x18001811e  test    eax, eax
0x180018120  jns     short loc_18001815D
0x180018122  mov     rcx, gs:60h
0x18001812b  mov     r8, rdi; P
0x18001812e  xor     edx, edx; Flags
0x180018130  mov     rcx, [rcx+30h]; HeapHandle
0x180018134  call    cs:__imp_RtlFreeHeap
0x18001813a  xor     eax, eax
0x18001813c  mov     rcx, [rbp+57h+var_10]
0x180018140  xor     rcx, rsp; StackCookie
0x180018143  call    __security_check_cookie
0x180018148  lea     r11, [rsp+0C0h+var_s0]
0x180018150  mov     rbx, [r11+10h]
0x180018154  mov     rdi, [r11+18h]
0x180018158  mov     rsp, r11
0x18001815b  pop     rbp
0x18001815c  retn
0x18001815d  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180018161  lea     rax, [rbp+57h+var_7C]
0x180018165  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18001816a  lea     r9, RemoteRegistryMappings; GenericMapping
0x180018171  lea     rax, [rbp+57h+var_78]
0x180018175  mov     [rbp+57h+var_80], 44h ; 'D'
0x18001817c  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180018181  mov     r8d, ebx; DesiredAccess
0x180018184  lea     rax, [rbp+57h+var_80]
0x180018188  mov     rcx, rdi; SecurityDescriptor
0x18001818b  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180018190  lea     rax, [rbp+57h+var_60]
0x180018194  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x180018199  call    cs:__imp_NtAccessCheck
0x18001819f  mov     rcx, gs:60h
0x1800181a8  mov     r8, rdi; P
0x1800181ab  xor     edx, edx; Flags
0x1800181ad  mov     ebx, eax
0x1800181af  mov     rcx, [rcx+30h]; HeapHandle
0x1800181b3  call    cs:__imp_RtlFreeHeap
0x1800181b9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800181bd  call    cs:__imp_NtClose
0x1800181c3  test    ebx, ebx
0x1800181c5  js      loc_18001813A
0x1800181cb  cmp     [rbp+57h+var_7C], 0
0x1800181cf  jl      loc_18001813A
0x1800181d5  test    byte ptr [rbp+57h+var_78], 3
0x1800181d9  mov     eax, 0
0x1800181de  setnz   al
0x1800181e1  jmp     loc_18001813C
```
