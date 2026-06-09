# DXGVAILOBJECT::AllocateDefaultSecurityDescriptor(ulong,void * *)

- ea: `0x14026b260`
- end: `0x14026b4c9`
- name: `?AllocateDefaultSecurityDescriptor@DXGVAILOBJECT@@SAJKPEAPEAX@Z`
- size: `617`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14026bc2c`
- `0x14026c088`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001b890`
- `0x1400a0100`
- `0x14026b260`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14026b39d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14026b39d`
- `ntoskrnl!RtlInitializeSid` at `0x14026b2a5`
- `ntoskrnl!RtlInitializeSid` at `0x14026b2a5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14026b2e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14026b2fe`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14026b2e1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14026b2fe`
- `ntoskrnl!RtlLengthSid` at `0x14026b314`
- `ntoskrnl!RtlLengthSid` at `0x14026b314`
- `ntoskrnl!RtlCreateAcl` at `0x14026b3e3`
- `ntoskrnl!RtlCreateAcl` at `0x14026b3e3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14026b425`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14026b425`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14026b463`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14026b463`
- `watchdog!WdLogSingleEntry1` at `0x14026b2c0`
- `watchdog!WdLogSingleEntry1` at `0x14026b34d`
- `watchdog!WdLogSingleEntry1` at `0x14026b3b8`
- `watchdog!WdLogSingleEntry1` at `0x14026b3fe`
- `watchdog!WdLogSingleEntry1` at `0x14026b440`
- `watchdog!WdLogSingleEntry1` at `0x14026b47e`
- `watchdog!WdLogSingleEntry1` at `0x14026b2c0`
- `watchdog!WdLogSingleEntry1` at `0x14026b34d`
- `watchdog!WdLogSingleEntry1` at `0x14026b3b8`
- `watchdog!WdLogSingleEntry1` at `0x14026b3fe`
- `watchdog!WdLogSingleEntry1` at `0x14026b440`
- `watchdog!WdLogSingleEntry1` at `0x14026b47e`

## pseudocode

```c
__int64 __fastcall DXGVAILOBJECT::AllocateDefaultSecurityDescriptor(ACCESS_MASK AccessMask, struct _ACL **a2)
{
  NTSTATUS SecurityDescriptor; // ebx
  ULONG v5; // eax
  ULONG v6; // r13d
  struct _ACL *v7; // rax
  struct _ACL *v8; // rdi
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-20h] BYREF
  _BYTE Sid[16]; // [rsp+58h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  SecurityDescriptor = RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  if ( SecurityDescriptor >= 0 )
  {
    *RtlSubAuthoritySid(Sid, 0) = 83;
    *RtlSubAuthoritySid(Sid, 1u) = 0;
    v5 = RtlLengthSid(Sid);
    v6 = v5 + 20;
    v7 = (struct _ACL *)operator new[](v5 + 60, 1265072196, 256);
    v8 = v7;
    if ( v7 )
    {
      SecurityDescriptor = RtlCreateSecurityDescriptor(v7, 1u);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlCreateAcl(v8 + 5, v6, 4u);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlAddAccessAllowedAce(v8 + 5, 4u, AccessMask, Sid);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = RtlSetDaclSecurityDescriptor(v8, 1u, v8 + 5, 0);
            if ( SecurityDescriptor >= 0 )
            {
              *a2 = v8;
              return (unsigned int)SecurityDescriptor;
            }
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 284;
          }
          else
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 275;
          }
        }
        else
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 262;
        }
      }
      else
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 251;
      }
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v8);
    }
    else
    {
      SecurityDescriptor = -1073741801;
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 242;
      DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"new failed. Returning 0x%I64x", -1073741801, 0, 0, 0, 0);
    }
  }
  else
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 225;
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14026b260  mov     [rsp-28h+arg_10], rbx
0x14026b265  mov     [rsp-28h+arg_18], rsi
0x14026b26a  push    rbp
0x14026b26b  push    rdi
0x14026b26c  push    r13
0x14026b26e  push    r14
0x14026b270  push    r15
0x14026b272  mov     rbp, rsp
0x14026b275  sub     rsp, 70h
0x14026b279  mov     rax, cs:__security_cookie
0x14026b280  xor     rax, rsp
0x14026b283  mov     [rbp+var_8], rax
0x14026b287  mov     r14, rdx
0x14026b28a  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x14026b291  mov     r15d, ecx
0x14026b294  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14026b29a  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14026b29e  mov     r8b, 2; SubAuthorityCount
0x14026b2a1  lea     rcx, [rbp+Sid]; Sid
0x14026b2a5  call    cs:__imp_RtlInitializeSid
0x14026b2ac  nop     dword ptr [rax+rax+00h]
0x14026b2b1  movsxd  rbx, eax
0x14026b2b4  test    eax, eax
0x14026b2b6  jns     short loc_14026B2DB
0x14026b2b8  mov     rdx, rbx
0x14026b2bb  mov     ecx, 3
0x14026b2c0  call    cs:__imp_WdLogSingleEntry1
0x14026b2c7  nop     dword ptr [rax+rax+00h]
0x14026b2cc  mov     cs:WdLogGlobalForLineNumber, 0E1h
0x14026b2d6  jmp     loc_14026B4A1
0x14026b2db  xor     edx, edx; SubAuthority
0x14026b2dd  lea     rcx, [rbp+Sid]; Sid
0x14026b2e1  call    cs:__imp_RtlSubAuthoritySid
0x14026b2e8  nop     dword ptr [rax+rax+00h]
0x14026b2ed  mov     ebx, 1
0x14026b2f2  lea     rcx, [rbp+Sid]; Sid
0x14026b2f6  mov     edx, ebx; SubAuthority
0x14026b2f8  mov     dword ptr [rax], 53h ; 'S'
0x14026b2fe  call    cs:__imp_RtlSubAuthoritySid
0x14026b305  nop     dword ptr [rax+rax+00h]
0x14026b30a  lea     rcx, [rbp+Sid]; Sid
0x14026b30e  mov     dword ptr [rax], 0
0x14026b314  call    cs:__imp_RtlLengthSid
0x14026b31b  nop     dword ptr [rax+rax+00h]
0x14026b320  mov     edx, 4B677844h
0x14026b325  mov     r8d, 100h
0x14026b32b  lea     r13d, [rax+14h]
0x14026b32f  lea     ecx, [r13+28h]
0x14026b333  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14026b338  mov     rdi, rax
0x14026b33b  test    rax, rax
0x14026b33e  jnz     short loc_14026B398
0x14026b340  mov     rbx, 0FFFFFFFFC0000017h
0x14026b347  mov     rdx, rbx
0x14026b34a  lea     ecx, [rax+6]
0x14026b34d  call    cs:__imp_WdLogSingleEntry1
0x14026b354  nop     dword ptr [rax+rax+00h]
0x14026b359  mov     [rsp+70h+var_30], rdi
0x14026b35e  lea     r9, aNewFailedRetur; "new failed. Returning 0x%I64x"
0x14026b365  mov     [rsp+70h+var_38], rdi
0x14026b36a  or      r8d, 0FFFFFFFFh
0x14026b36e  mov     [rsp+70h+var_40], rdi
0x14026b373  mov     edx, 40001h
0x14026b378  mov     [rsp+70h+var_48], rdi
0x14026b37d  xor     ecx, ecx
0x14026b37f  mov     [rsp+70h+var_50], rbx
0x14026b384  mov     cs:WdLogGlobalForLineNumber, 0F2h
0x14026b38e  call    DxgkLogInternalTriageEvent
0x14026b393  jmp     loc_14026B4A1
0x14026b398  mov     edx, ebx; Revision
0x14026b39a  mov     rcx, rdi; SecurityDescriptor
0x14026b39d  call    cs:__imp_RtlCreateSecurityDescriptor
0x14026b3a4  nop     dword ptr [rax+rax+00h]
0x14026b3a9  movsxd  rbx, eax
0x14026b3ac  test    eax, eax
0x14026b3ae  jns     short loc_14026B3D3
0x14026b3b0  mov     rdx, rbx
0x14026b3b3  mov     ecx, 3
0x14026b3b8  call    cs:__imp_WdLogSingleEntry1
0x14026b3bf  nop     dword ptr [rax+rax+00h]
0x14026b3c4  mov     cs:WdLogGlobalForLineNumber, 0FBh
0x14026b3ce  jmp     loc_14026B494
0x14026b3d3  lea     rsi, [rdi+28h]
0x14026b3d7  mov     r8d, 4; AclRevision
0x14026b3dd  mov     rcx, rsi; Acl
0x14026b3e0  mov     edx, r13d; AclLength
0x14026b3e3  call    cs:__imp_RtlCreateAcl
0x14026b3ea  nop     dword ptr [rax+rax+00h]
0x14026b3ef  movsxd  rbx, eax
0x14026b3f2  test    eax, eax
0x14026b3f4  jns     short loc_14026B416
0x14026b3f6  mov     rdx, rbx
0x14026b3f9  mov     ecx, 3
0x14026b3fe  call    cs:__imp_WdLogSingleEntry1
0x14026b405  nop     dword ptr [rax+rax+00h]
0x14026b40a  mov     cs:WdLogGlobalForLineNumber, 106h
0x14026b414  jmp     short loc_14026B494
0x14026b416  lea     r9, [rbp+Sid]; Sid
0x14026b41a  mov     r8d, r15d; AccessMask
0x14026b41d  mov     edx, 4; AceRevision
0x14026b422  mov     rcx, rsi; Acl
0x14026b425  call    cs:__imp_RtlAddAccessAllowedAce
0x14026b42c  nop     dword ptr [rax+rax+00h]
0x14026b431  movsxd  rbx, eax
0x14026b434  test    eax, eax
0x14026b436  jns     short loc_14026B458
0x14026b438  mov     rdx, rbx
0x14026b43b  mov     ecx, 3
0x14026b440  call    cs:__imp_WdLogSingleEntry1
0x14026b447  nop     dword ptr [rax+rax+00h]
0x14026b44c  mov     cs:WdLogGlobalForLineNumber, 113h
0x14026b456  jmp     short loc_14026B494
0x14026b458  xor     r9d, r9d; DaclDefaulted
0x14026b45b  mov     r8, rsi; Dacl
0x14026b45e  mov     dl, 1; DaclPresent
0x14026b460  mov     rcx, rdi; SecurityDescriptor
0x14026b463  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14026b46a  nop     dword ptr [rax+rax+00h]
0x14026b46f  movsxd  rbx, eax
0x14026b472  test    eax, eax
0x14026b474  jns     short loc_14026B49E
0x14026b476  mov     rdx, rbx
0x14026b479  mov     ecx, 3
0x14026b47e  call    cs:__imp_WdLogSingleEntry1
0x14026b485  nop     dword ptr [rax+rax+00h]
0x14026b48a  mov     cs:WdLogGlobalForLineNumber, 11Ch
0x14026b494  mov     rcx, rdi; void *
0x14026b497  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14026b49c  jmp     short loc_14026B4A1
0x14026b49e  mov     [r14], rdi
0x14026b4a1  mov     eax, ebx
0x14026b4a3  mov     rcx, [rbp+var_8]
0x14026b4a7  xor     rcx, rsp; StackCookie
0x14026b4aa  call    __security_check_cookie
0x14026b4af  lea     r11, [rsp+70h+var_s0]
0x14026b4b4  mov     rbx, [r11+40h]
0x14026b4b8  mov     rsi, [r11+48h]
0x14026b4bc  mov     rsp, r11
0x14026b4bf  pop     r15
0x14026b4c1  pop     r14
0x14026b4c3  pop     r13
0x14026b4c5  pop     rdi
0x14026b4c6  pop     rbp
0x14026b4c7  retn
```
