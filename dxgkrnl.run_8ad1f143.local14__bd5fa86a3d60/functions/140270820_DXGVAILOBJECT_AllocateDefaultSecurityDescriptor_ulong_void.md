# DXGVAILOBJECT::AllocateDefaultSecurityDescriptor(ulong,void * *)

- ea: `0x140270820`
- end: `0x140270a89`
- name: `?AllocateDefaultSecurityDescriptor@DXGVAILOBJECT@@SAJKPEAPEAX@Z`
- size: `617`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1402711ec`
- `0x140271648`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001b9c0`
- `0x1400a0bd0`
- `0x140270820`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14027095d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14027095d`
- `ntoskrnl!RtlInitializeSid` at `0x140270865`
- `ntoskrnl!RtlInitializeSid` at `0x140270865`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402708a1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402708be`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402708a1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1402708be`
- `ntoskrnl!RtlLengthSid` at `0x1402708d4`
- `ntoskrnl!RtlLengthSid` at `0x1402708d4`
- `ntoskrnl!RtlCreateAcl` at `0x1402709a3`
- `ntoskrnl!RtlCreateAcl` at `0x1402709a3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402709e5`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402709e5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140270a23`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140270a23`
- `watchdog!WdLogSingleEntry1` at `0x140270880`
- `watchdog!WdLogSingleEntry1` at `0x14027090d`
- `watchdog!WdLogSingleEntry1` at `0x140270978`
- `watchdog!WdLogSingleEntry1` at `0x1402709be`
- `watchdog!WdLogSingleEntry1` at `0x140270a00`
- `watchdog!WdLogSingleEntry1` at `0x140270a3e`
- `watchdog!WdLogSingleEntry1` at `0x140270880`
- `watchdog!WdLogSingleEntry1` at `0x14027090d`
- `watchdog!WdLogSingleEntry1` at `0x140270978`
- `watchdog!WdLogSingleEntry1` at `0x1402709be`
- `watchdog!WdLogSingleEntry1` at `0x140270a00`
- `watchdog!WdLogSingleEntry1` at `0x140270a3e`

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
0x140270820  mov     [rsp-28h+arg_10], rbx
0x140270825  mov     [rsp-28h+arg_18], rsi
0x14027082a  push    rbp
0x14027082b  push    rdi
0x14027082c  push    r13
0x14027082e  push    r14
0x140270830  push    r15
0x140270832  mov     rbp, rsp
0x140270835  sub     rsp, 70h
0x140270839  mov     rax, cs:__security_cookie
0x140270840  xor     rax, rsp
0x140270843  mov     [rbp+var_8], rax
0x140270847  mov     r14, rdx
0x14027084a  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x140270851  mov     r15d, ecx
0x140270854  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14027085a  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14027085e  mov     r8b, 2; SubAuthorityCount
0x140270861  lea     rcx, [rbp+Sid]; Sid
0x140270865  call    cs:__imp_RtlInitializeSid
0x14027086c  nop     dword ptr [rax+rax+00h]
0x140270871  movsxd  rbx, eax
0x140270874  test    eax, eax
0x140270876  jns     short loc_14027089B
0x140270878  mov     rdx, rbx
0x14027087b  mov     ecx, 3
0x140270880  call    cs:__imp_WdLogSingleEntry1
0x140270887  nop     dword ptr [rax+rax+00h]
0x14027088c  mov     cs:WdLogGlobalForLineNumber, 0E1h
0x140270896  jmp     loc_140270A61
0x14027089b  xor     edx, edx; SubAuthority
0x14027089d  lea     rcx, [rbp+Sid]; Sid
0x1402708a1  call    cs:__imp_RtlSubAuthoritySid
0x1402708a8  nop     dword ptr [rax+rax+00h]
0x1402708ad  mov     ebx, 1
0x1402708b2  lea     rcx, [rbp+Sid]; Sid
0x1402708b6  mov     edx, ebx; SubAuthority
0x1402708b8  mov     dword ptr [rax], 53h ; 'S'
0x1402708be  call    cs:__imp_RtlSubAuthoritySid
0x1402708c5  nop     dword ptr [rax+rax+00h]
0x1402708ca  lea     rcx, [rbp+Sid]; Sid
0x1402708ce  mov     dword ptr [rax], 0
0x1402708d4  call    cs:__imp_RtlLengthSid
0x1402708db  nop     dword ptr [rax+rax+00h]
0x1402708e0  mov     edx, 4B677844h
0x1402708e5  mov     r8d, 100h
0x1402708eb  lea     r13d, [rax+14h]
0x1402708ef  lea     ecx, [r13+28h]
0x1402708f3  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1402708f8  mov     rdi, rax
0x1402708fb  test    rax, rax
0x1402708fe  jnz     short loc_140270958
0x140270900  mov     rbx, 0FFFFFFFFC0000017h
0x140270907  mov     rdx, rbx
0x14027090a  lea     ecx, [rax+6]
0x14027090d  call    cs:__imp_WdLogSingleEntry1
0x140270914  nop     dword ptr [rax+rax+00h]
0x140270919  mov     [rsp+70h+var_30], rdi
0x14027091e  lea     r9, aNewFailedRetur; "new failed. Returning 0x%I64x"
0x140270925  mov     [rsp+70h+var_38], rdi
0x14027092a  or      r8d, 0FFFFFFFFh
0x14027092e  mov     [rsp+70h+var_40], rdi
0x140270933  mov     edx, 40001h
0x140270938  mov     [rsp+70h+var_48], rdi
0x14027093d  xor     ecx, ecx
0x14027093f  mov     [rsp+70h+var_50], rbx
0x140270944  mov     cs:WdLogGlobalForLineNumber, 0F2h
0x14027094e  call    DxgkLogInternalTriageEvent
0x140270953  jmp     loc_140270A61
0x140270958  mov     edx, ebx; Revision
0x14027095a  mov     rcx, rdi; SecurityDescriptor
0x14027095d  call    cs:__imp_RtlCreateSecurityDescriptor
0x140270964  nop     dword ptr [rax+rax+00h]
0x140270969  movsxd  rbx, eax
0x14027096c  test    eax, eax
0x14027096e  jns     short loc_140270993
0x140270970  mov     rdx, rbx
0x140270973  mov     ecx, 3
0x140270978  call    cs:__imp_WdLogSingleEntry1
0x14027097f  nop     dword ptr [rax+rax+00h]
0x140270984  mov     cs:WdLogGlobalForLineNumber, 0FBh
0x14027098e  jmp     loc_140270A54
0x140270993  lea     rsi, [rdi+28h]
0x140270997  mov     r8d, 4; AclRevision
0x14027099d  mov     rcx, rsi; Acl
0x1402709a0  mov     edx, r13d; AclLength
0x1402709a3  call    cs:__imp_RtlCreateAcl
0x1402709aa  nop     dword ptr [rax+rax+00h]
0x1402709af  movsxd  rbx, eax
0x1402709b2  test    eax, eax
0x1402709b4  jns     short loc_1402709D6
0x1402709b6  mov     rdx, rbx
0x1402709b9  mov     ecx, 3
0x1402709be  call    cs:__imp_WdLogSingleEntry1
0x1402709c5  nop     dword ptr [rax+rax+00h]
0x1402709ca  mov     cs:WdLogGlobalForLineNumber, 106h
0x1402709d4  jmp     short loc_140270A54
0x1402709d6  lea     r9, [rbp+Sid]; Sid
0x1402709da  mov     r8d, r15d; AccessMask
0x1402709dd  mov     edx, 4; AceRevision
0x1402709e2  mov     rcx, rsi; Acl
0x1402709e5  call    cs:__imp_RtlAddAccessAllowedAce
0x1402709ec  nop     dword ptr [rax+rax+00h]
0x1402709f1  movsxd  rbx, eax
0x1402709f4  test    eax, eax
0x1402709f6  jns     short loc_140270A18
0x1402709f8  mov     rdx, rbx
0x1402709fb  mov     ecx, 3
0x140270a00  call    cs:__imp_WdLogSingleEntry1
0x140270a07  nop     dword ptr [rax+rax+00h]
0x140270a0c  mov     cs:WdLogGlobalForLineNumber, 113h
0x140270a16  jmp     short loc_140270A54
0x140270a18  xor     r9d, r9d; DaclDefaulted
0x140270a1b  mov     r8, rsi; Dacl
0x140270a1e  mov     dl, 1; DaclPresent
0x140270a20  mov     rcx, rdi; SecurityDescriptor
0x140270a23  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140270a2a  nop     dword ptr [rax+rax+00h]
0x140270a2f  movsxd  rbx, eax
0x140270a32  test    eax, eax
0x140270a34  jns     short loc_140270A5E
0x140270a36  mov     rdx, rbx
0x140270a39  mov     ecx, 3
0x140270a3e  call    cs:__imp_WdLogSingleEntry1
0x140270a45  nop     dword ptr [rax+rax+00h]
0x140270a4a  mov     cs:WdLogGlobalForLineNumber, 11Ch
0x140270a54  mov     rcx, rdi; void *
0x140270a57  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140270a5c  jmp     short loc_140270A61
0x140270a5e  mov     [r14], rdi
0x140270a61  mov     eax, ebx
0x140270a63  mov     rcx, [rbp+var_8]
0x140270a67  xor     rcx, rsp; StackCookie
0x140270a6a  call    __security_check_cookie
0x140270a6f  lea     r11, [rsp+70h+var_s0]
0x140270a74  mov     rbx, [r11+40h]
0x140270a78  mov     rsi, [r11+48h]
0x140270a7c  mov     rsp, r11
0x140270a7f  pop     r15
0x140270a81  pop     r14
0x140270a83  pop     r13
0x140270a85  pop     rdi
0x140270a86  pop     rbp
0x140270a87  retn
```
