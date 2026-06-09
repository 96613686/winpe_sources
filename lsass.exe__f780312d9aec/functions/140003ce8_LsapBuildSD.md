# LsapBuildSD

- ea: `0x140003ce8`
- end: `0x140003e94`
- name: `LsapBuildSD`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140002b9c`

## callees

- `0x1400016c0`
- `0x140001a80`
- `0x140003ce8`
- `0x140004158`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x140003e69`
- `ntdll!NtSetSecurityObject` at `0x140003e69`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140003e3c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x140003e3c`
- `ntdll!RtlCreateAcl` at `0x140003d82`
- `ntdll!RtlCreateAcl` at `0x140003d82`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003da5`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003dc8`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003deb`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003e0a`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003e29`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003da5`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003dc8`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003deb`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003e0a`
- `ntdll!RtlAddAccessAllowedAce` at `0x140003e29`
- `ntdll!RtlLengthSid` at `0x140003d11`
- `ntdll!RtlLengthSid` at `0x140003d20`
- `ntdll!RtlLengthSid` at `0x140003d2f`
- `ntdll!RtlLengthSid` at `0x140003d3e`
- `ntdll!RtlLengthSid` at `0x140003d4d`
- `ntdll!RtlLengthSid` at `0x140003d11`
- `ntdll!RtlLengthSid` at `0x140003d20`
- `ntdll!RtlLengthSid` at `0x140003d2f`
- `ntdll!RtlLengthSid` at `0x140003d3e`
- `ntdll!RtlLengthSid` at `0x140003d4d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140003e53`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x140003e53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003e74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003e74`

## pseudocode

```c
__int64 LsapBuildSD()
{
  void *v0; // rbp
  NTSTATUS Acl; // ebx
  ULONG v2; // ebx
  ULONG v3; // ebx
  ULONG v4; // ebx
  ULONG v5; // ebx
  ULONG v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  struct _ACL *LsaHeap; // rax
  struct _ACL *v10; // rsi
  struct _ACL *v11; // rdi

  v0 = (void *)SpmOpenEvent();
  if ( v0 )
  {
    v2 = RtlLengthSid(gLsapIdentityServicesLpacSid);
    v3 = RtlLengthSid(gLsapAnyPackageSid) + v2;
    v4 = RtlLengthSid(gLsapWorldSid) + v3;
    v5 = RtlLengthSid(gLsapAliasAdminsSid) + v4;
    v6 = RtlLengthSid(gLsapLocalSystemSid) + v5;
    LsaHeap = (struct _ACL *)LsapAllocateLsaHeap(v6 + 88, v7, v8);
    v10 = LsaHeap;
    if ( LsaHeap )
    {
      v11 = LsaHeap + 5;
      Acl = RtlCreateAcl(LsaHeap + 5, v6 + 48, 2u);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v11, 2u, 0xA0000000, gLsapWorldSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v11, 2u, 0x10000000u, gLsapLocalSystemSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v11, 2u, 0xA0020000, gLsapAliasAdminsSid);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v11, 2u, 0xA0000000, gLsapAnyPackageSid);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAce(v11, 2u, 0xA0000000, gLsapIdentityServicesLpacSid);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(v10, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(v10, 1u, v11, 0);
                    if ( Acl >= 0 )
                      Acl = NtSetSecurityObject(v0, 4u, v10);
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      Acl = -1073741670;
    }
    CloseHandle(v0);
    if ( v10 )
      LsapFreeLsaHeap(v10);
  }
  else
  {
    return (unsigned int)-1073741816;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140003ce8  push    rbx
0x140003cea  push    rbp
0x140003ceb  push    rsi
0x140003cec  push    rdi
0x140003ced  push    r14
0x140003cef  sub     rsp, 20h
0x140003cf3  call    SpmOpenEvent
0x140003cf8  mov     rbp, rax
0x140003cfb  test    rax, rax
0x140003cfe  jnz     short loc_140003D0A
0x140003d00  mov     ebx, 0C0000008h
0x140003d05  jmp     loc_140003E87
0x140003d0a  mov     rcx, cs:gLsapIdentityServicesLpacSid; Sid
0x140003d11  call    cs:__imp_RtlLengthSid
0x140003d17  mov     rcx, cs:gLsapAnyPackageSid; Sid
0x140003d1e  mov     ebx, eax
0x140003d20  call    cs:__imp_RtlLengthSid
0x140003d26  mov     rcx, cs:gLsapWorldSid; Sid
0x140003d2d  add     ebx, eax
0x140003d2f  call    cs:__imp_RtlLengthSid
0x140003d35  mov     rcx, cs:gLsapAliasAdminsSid; Sid
0x140003d3c  add     ebx, eax
0x140003d3e  call    cs:__imp_RtlLengthSid
0x140003d44  mov     rcx, cs:gLsapLocalSystemSid; Sid
0x140003d4b  add     ebx, eax
0x140003d4d  call    cs:__imp_RtlLengthSid
0x140003d53  add     ebx, eax
0x140003d55  lea     ecx, [rbx+58h]
0x140003d58  call    LsapAllocateLsaHeap
0x140003d5d  mov     rsi, rax
0x140003d60  test    rax, rax
0x140003d63  jnz     short loc_140003D6F
0x140003d65  mov     ebx, 0C000009Ah
0x140003d6a  jmp     loc_140003E71
0x140003d6f  lea     rdi, [rax+28h]
0x140003d73  mov     r14d, 2
0x140003d79  mov     r8d, r14d; AclRevision
0x140003d7c  lea     edx, [rbx+30h]; AclSize
0x140003d7f  mov     rcx, rdi; Acl
0x140003d82  call    cs:__imp_RtlCreateAcl
0x140003d88  mov     ebx, eax
0x140003d8a  test    eax, eax
0x140003d8c  js      loc_140003E71
0x140003d92  mov     r9, cs:gLsapWorldSid; Sid
0x140003d99  mov     r8d, 0A0000000h; AccessMask
0x140003d9f  mov     edx, r14d; Revision
0x140003da2  mov     rcx, rdi; Acl
0x140003da5  call    cs:__imp_RtlAddAccessAllowedAce
0x140003dab  mov     ebx, eax
0x140003dad  test    eax, eax
0x140003daf  js      loc_140003E71
0x140003db5  mov     r9, cs:gLsapLocalSystemSid; Sid
0x140003dbc  mov     r8d, 10000000h; AccessMask
0x140003dc2  mov     edx, r14d; Revision
0x140003dc5  mov     rcx, rdi; Acl
0x140003dc8  call    cs:__imp_RtlAddAccessAllowedAce
0x140003dce  mov     ebx, eax
0x140003dd0  test    eax, eax
0x140003dd2  js      loc_140003E71
0x140003dd8  mov     r9, cs:gLsapAliasAdminsSid; Sid
0x140003ddf  mov     r8d, 0A0020000h; AccessMask
0x140003de5  mov     edx, r14d; Revision
0x140003de8  mov     rcx, rdi; Acl
0x140003deb  call    cs:__imp_RtlAddAccessAllowedAce
0x140003df1  mov     ebx, eax
0x140003df3  test    eax, eax
0x140003df5  js      short loc_140003E71
0x140003df7  mov     r9, cs:gLsapAnyPackageSid; Sid
0x140003dfe  mov     r8d, 0A0000000h; AccessMask
0x140003e04  mov     edx, r14d; Revision
0x140003e07  mov     rcx, rdi; Acl
0x140003e0a  call    cs:__imp_RtlAddAccessAllowedAce
0x140003e10  mov     ebx, eax
0x140003e12  test    eax, eax
0x140003e14  js      short loc_140003E71
0x140003e16  mov     r9, cs:gLsapIdentityServicesLpacSid; Sid
0x140003e1d  mov     r8d, 0A0000000h; AccessMask
0x140003e23  mov     edx, r14d; Revision
0x140003e26  mov     rcx, rdi; Acl
0x140003e29  call    cs:__imp_RtlAddAccessAllowedAce
0x140003e2f  mov     ebx, eax
0x140003e31  test    eax, eax
0x140003e33  js      short loc_140003E71
0x140003e35  lea     edx, [r14-1]; Revision
0x140003e39  mov     rcx, rsi; SecurityDescriptor
0x140003e3c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140003e42  mov     ebx, eax
0x140003e44  test    eax, eax
0x140003e46  js      short loc_140003E71
0x140003e48  xor     r9d, r9d; DaclDefaulted
0x140003e4b  mov     r8, rdi; Dacl
0x140003e4e  mov     dl, 1; DaclPresent
0x140003e50  mov     rcx, rsi; SecurityDescriptor
0x140003e53  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140003e59  mov     ebx, eax
0x140003e5b  test    eax, eax
0x140003e5d  js      short loc_140003E71
0x140003e5f  mov     r8, rsi; SecurityDescriptor
0x140003e62  lea     edx, [r14+2]; SecurityInformation
0x140003e66  mov     rcx, rbp; Handle
0x140003e69  call    cs:__imp_NtSetSecurityObject
0x140003e6f  mov     ebx, eax
0x140003e71  mov     rcx, rbp; hObject
0x140003e74  call    cs:__imp_CloseHandle
0x140003e7a  test    rsi, rsi
0x140003e7d  jz      short loc_140003E87
0x140003e7f  mov     rcx, rsi
0x140003e82  call    LsapFreeLsaHeap
0x140003e87  mov     eax, ebx
0x140003e89  add     rsp, 20h
0x140003e8d  pop     r14
0x140003e8f  pop     rdi
0x140003e90  pop     rsi
0x140003e91  pop     rbp
0x140003e92  pop     rbx
0x140003e93  retn
```
