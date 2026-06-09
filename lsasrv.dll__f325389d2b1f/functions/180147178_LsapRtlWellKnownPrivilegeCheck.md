# LsapRtlWellKnownPrivilegeCheck

- ea: `0x180147178`
- end: `0x1801472e1`
- name: `LsapRtlWellKnownPrivilegeCheck`
- size: `361`
- prototype: `__int64 __fastcall(PVOID HandleId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180090b64`

## callees

- `0x1800b86d0`
- `0x180147178`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x18014722f`
- `ntdll!NtPrivilegeCheck` at `0x18014722f`
- `ntdll!NtClose` at `0x1801472b4`
- `ntdll!NtClose` at `0x1801472b4`
- `ntdll!NtOpenThreadToken` at `0x1801471f0`
- `ntdll!NtOpenThreadToken` at `0x1801471f0`
- `ntdll!RtlInitUnicodeString` at `0x18014724c`
- `ntdll!RtlInitUnicodeString` at `0x18014724c`
- `ntdll!NtPrivilegeObjectAuditAlarm` at `0x180147279`
- `ntdll!NtPrivilegeObjectAuditAlarm` at `0x180147279`
- `RPCRT4!RpcRevertToSelf` at `0x180147291`
- `RPCRT4!RpcRevertToSelf` at `0x180147291`
- `RPCRT4!I_RpcMapWin32Status` at `0x1801471c7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014729f`
- `RPCRT4!I_RpcMapWin32Status` at `0x1801471c7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18014729f`
- `RPCRT4!RpcImpersonateClient` at `0x1801471b9`
- `RPCRT4!RpcImpersonateClient` at `0x1801471b9`

## pseudocode

```c
__int64 __fastcall LsapRtlWellKnownPrivilegeCheck(PVOID HandleId)
{
  RPC_STATUS v2; // eax
  int v3; // ebx
  RPC_STATUS v4; // eax
  unsigned __int8 Result[8]; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-20h] BYREF

  Result[0] = 0;
  TokenHandle = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  DestinationString = 0;
  v2 = RpcImpersonateClient(0);
  v3 = I_RpcMapWin32Status(v2);
  if ( v3 >= 0 )
  {
    v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v3 >= 0 )
    {
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = (LUID)8LL;
      RequiredPrivileges.Privilege[0].Attributes = 0;
      v3 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
      if ( v3 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"LSA");
        NtPrivilegeObjectAuditAlarm(
          &DestinationString,
          HandleId,
          TokenHandle,
          0x1000000u,
          &RequiredPrivileges,
          Result[0]);
        if ( !Result[0] )
          v3 = -1073741727;
      }
    }
    v4 = RpcRevertToSelf();
    I_RpcMapWin32Status(v4);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180147178  mov     [rsp-8+arg_8], rbx
0x18014717d  mov     [rsp-8+arg_10], rdi
0x180147182  push    rbp
0x180147183  mov     rbp, rsp
0x180147186  sub     rsp, 70h
0x18014718a  mov     rax, cs:__security_cookie
0x180147191  xor     rax, rsp
0x180147194  mov     [rbp+var_8], rax
0x180147198  xorps   xmm0, xmm0
0x18014719b  mov     [rbp+Result], 0
0x18014719f  mov     rdi, rcx
0x1801471a2  mov     [rbp+TokenHandle], 0
0x1801471aa  xor     eax, eax
0x1801471ac  xor     ecx, ecx; BindingHandle
0x1801471ae  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x1801471b2  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1801471b5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1801471b9  call    cs:__imp_RpcImpersonateClient
0x1801471c0  nop     dword ptr [rax+rax+00h]
0x1801471c5  mov     ecx, eax; Status
0x1801471c7  call    cs:__imp_I_RpcMapWin32Status
0x1801471ce  nop     dword ptr [rax+rax+00h]
0x1801471d3  mov     ebx, eax
0x1801471d5  test    eax, eax
0x1801471d7  js      loc_1801472AB
0x1801471dd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1801471e1  mov     r8b, 1; OpenAsSelf
0x1801471e4  mov     edx, 8; DesiredAccess
0x1801471e9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1801471f0  call    cs:__imp_NtOpenThreadToken
0x1801471f7  nop     dword ptr [rax+rax+00h]
0x1801471fc  mov     ebx, eax
0x1801471fe  test    eax, eax
0x180147200  js      loc_180147291
0x180147206  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18014720a  lea     r8, [rbp+Result]; Result
0x18014720e  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180147212  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180147219  mov     [rbp+RequiredPrivileges.Control], 1
0x180147220  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 8
0x180147228  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x18014722f  call    cs:__imp_NtPrivilegeCheck
0x180147236  nop     dword ptr [rax+rax+00h]
0x18014723b  mov     ebx, eax
0x18014723d  test    eax, eax
0x18014723f  js      short loc_180147291
0x180147241  lea     rdx, aLsa; "LSA"
0x180147248  lea     rcx, [rbp+DestinationString]; DestinationString
0x18014724c  call    cs:__imp_RtlInitUnicodeString
0x180147253  nop     dword ptr [rax+rax+00h]
0x180147258  mov     al, [rbp+Result]
0x18014725b  lea     rcx, [rbp+DestinationString]; SubsystemName
0x18014725f  mov     r8, [rbp+TokenHandle]; ClientToken
0x180147263  mov     r9d, 1000000h; DesiredAccess
0x180147269  mov     [rsp+70h+AccessGranted], al; AccessGranted
0x18014726d  mov     rdx, rdi; HandleId
0x180147270  lea     rax, [rbp+RequiredPrivileges]
0x180147274  mov     [rsp+70h+Privileges], rax; Privileges
0x180147279  call    cs:__imp_NtPrivilegeObjectAuditAlarm
0x180147280  nop     dword ptr [rax+rax+00h]
0x180147285  cmp     [rbp+Result], 0
0x180147289  mov     eax, 0C0000061h
0x18014728e  cmovz   ebx, eax
0x180147291  call    cs:__imp_RpcRevertToSelf
0x180147298  nop     dword ptr [rax+rax+00h]
0x18014729d  mov     ecx, eax; Status
0x18014729f  call    cs:__imp_I_RpcMapWin32Status
0x1801472a6  nop     dword ptr [rax+rax+00h]
0x1801472ab  mov     rcx, [rbp+TokenHandle]; Handle
0x1801472af  test    rcx, rcx
0x1801472b2  jz      short loc_1801472C0
0x1801472b4  call    cs:__imp_NtClose
0x1801472bb  nop     dword ptr [rax+rax+00h]
0x1801472c0  mov     eax, ebx
0x1801472c2  mov     rcx, [rbp+var_8]
0x1801472c6  xor     rcx, rsp; StackCookie
0x1801472c9  call    __security_check_cookie
0x1801472ce  lea     r11, [rsp+70h+var_s0]
0x1801472d3  mov     rbx, [r11+18h]
0x1801472d7  mov     rdi, [r11+20h]
0x1801472db  mov     rsp, r11
0x1801472de  pop     rbp
0x1801472df  retn
```
