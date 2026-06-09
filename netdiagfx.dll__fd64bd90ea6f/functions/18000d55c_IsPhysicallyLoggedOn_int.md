# IsPhysicallyLoggedOn(int *)

- ea: `0x18000d55c`
- end: `0x18000d605`
- name: `?IsPhysicallyLoggedOn@@YAJPEAH@Z`
- size: `169`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000e034`

## callees

- `0x18000d55c`
- `0x18002c840`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18000d5ad`
- `ntdll!RtlSubAuthoritySid` at `0x18000d5ad`
- `ntdll!RtlInitializeSid` at `0x18000d59a`
- `ntdll!RtlInitializeSid` at `0x18000d59a`
- `KERNEL32!GetLastError` at `0x18000d5cd`
- `KERNEL32!GetLastError` at `0x18000d5cd`
- `ADVAPI32!CheckTokenMembership` at `0x18000d5c3`
- `ADVAPI32!CheckTokenMembership` at `0x18000d5c3`

## pseudocode

```c
__int64 __fastcall IsPhysicallyLoggedOn(PBOOL IsMember)
{
  NTSTATUS v2; // ebx
  signed int LastError; // eax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-78h] BYREF
  _BYTE Sid[80]; // [rsp+30h] [rbp-68h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 512;
  v2 = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  if ( v2 >= 0 )
  {
    *RtlSubAuthoritySid(Sid, 0) = 1;
    if ( !CheckTokenMembership(0, Sid, IsMember) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d55c  mov     [rsp+arg_8], rbx
0x18000d561  push    rdi
0x18000d562  sub     rsp, 90h
0x18000d569  mov     rax, cs:__security_cookie
0x18000d570  xor     rax, rsp
0x18000d573  mov     [rsp+98h+var_18], rax
0x18000d57b  mov     rdi, rcx
0x18000d57e  mov     dword ptr [rsp+98h+IdentifierAuthority.Value], 0
0x18000d586  lea     rcx, [rsp+98h+Sid]; Sid
0x18000d58b  mov     word ptr [rsp+98h+IdentifierAuthority.Value+4], 200h
0x18000d592  mov     r8b, 1; SubAuthorityCount
0x18000d595  lea     rdx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x18000d59a  call    cs:__imp_RtlInitializeSid
0x18000d5a0  mov     ebx, eax
0x18000d5a2  test    eax, eax
0x18000d5a4  js      short loc_18000D5E2
0x18000d5a6  xor     edx, edx; SubAuthority
0x18000d5a8  lea     rcx, [rsp+98h+Sid]; Sid
0x18000d5ad  call    cs:__imp_RtlSubAuthoritySid
0x18000d5b3  mov     r8, rdi; IsMember
0x18000d5b6  lea     rdx, [rsp+98h+Sid]; SidToCheck
0x18000d5bb  xor     ecx, ecx; TokenHandle
0x18000d5bd  mov     dword ptr [rax], 1
0x18000d5c3  call    cs:__imp_CheckTokenMembership
0x18000d5c9  test    eax, eax
0x18000d5cb  jnz     short loc_18000D5E2
0x18000d5cd  call    cs:__imp_GetLastError
0x18000d5d3  mov     ebx, eax
0x18000d5d5  test    eax, eax
0x18000d5d7  jle     short loc_18000D5E2
0x18000d5d9  movzx   ebx, ax
0x18000d5dc  or      ebx, 80070000h
0x18000d5e2  mov     eax, ebx
0x18000d5e4  mov     rcx, [rsp+98h+var_18]
0x18000d5ec  xor     rcx, rsp; StackCookie
0x18000d5ef  call    __security_check_cookie
0x18000d5f4  mov     rbx, [rsp+98h+arg_8]
0x18000d5fc  add     rsp, 90h
0x18000d603  pop     rdi
0x18000d604  retn
```
