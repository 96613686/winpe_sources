# CheckCallerMatchesSid

- ea: `0x1402ea8c8`
- end: `0x1402eabb8`
- name: `CheckCallerMatchesSid`
- size: `752`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402ec578`

## callees

- `0x14001b890`
- `0x1400623f4`
- `0x14009294c`
- `0x1400a0100`
- `0x1402ea8c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402ea97b`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea97b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402ea8fa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402ea8fa`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402ea926`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402ea926`
- `ntoskrnl!RtlLengthSid` at `0x1402ea95f`
- `ntoskrnl!RtlLengthSid` at `0x1402ea95f`
- `ntoskrnl!RtlCreateAcl` at `0x1402ea9cf`
- `ntoskrnl!RtlCreateAcl` at `0x1402ea9cf`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402eaa24`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402eaa24`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402eaa63`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402eaa63`
- `ntoskrnl!SeAccessCheck` at `0x1402eab68`
- `ntoskrnl!SeAccessCheck` at `0x1402eab68`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402eaa9d`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402eaa9d`
- `watchdog!WdLogSingleEntry0` at `0x1402eaab2`
- `watchdog!WdLogSingleEntry0` at `0x1402eaab2`
- `watchdog!WdLogSingleEntry1` at `0x1402ea941`
- `watchdog!WdLogSingleEntry1` at `0x1402ea9a0`
- `watchdog!WdLogSingleEntry1` at `0x1402ea9ea`
- `watchdog!WdLogSingleEntry1` at `0x1402eaa3f`
- `watchdog!WdLogSingleEntry1` at `0x1402eaa7e`
- `watchdog!WdLogSingleEntry1` at `0x1402ea941`
- `watchdog!WdLogSingleEntry1` at `0x1402ea9a0`
- `watchdog!WdLogSingleEntry1` at `0x1402ea9ea`
- `watchdog!WdLogSingleEntry1` at `0x1402eaa3f`
- `watchdog!WdLogSingleEntry1` at `0x1402eaa7e`

## string_xrefs

- `0x1402eaac7`: `RtlValidSecurityDescriptor(&SecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall CheckCallerMatchesSid(PSID Sid)
{
  NTSTATUS v2; // ebx
  __int64 v3; // rsi
  struct _ACL *Pool2; // rax
  struct _ACL *v5; // rbx
  NTSTATUS Acl; // esi
  struct _ACL *v8; // [rsp+50h] [rbp-49h] BYREF
  int AccessStatus; // [rsp+58h] [rbp-41h] BYREF
  DWORD GrantedAccess; // [rsp+5Ch] [rbp-3Dh] BYREF
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // [rsp+60h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v13; // [rsp+88h] [rbp-11h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+90h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+B0h] [rbp+17h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  p_SubjectContext = &SubjectContext;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v13 = 0;
  v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v2 >= 0 )
  {
    v3 = RtlLengthSid(Sid) + 20;
    Pool2 = (struct _ACL *)ExAllocatePool2(256, v3, 1265072196);
    v8 = Pool2;
    v5 = Pool2;
    if ( !Pool2 )
    {
      v2 = -1073741670;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2751;
LABEL_5:
      __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v8);
      goto LABEL_19;
    }
    Acl = RtlCreateAcl(Pool2, v3, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v5, 2u, 0x1F0000u, Sid);
      if ( Acl >= 0 )
      {
        v2 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v5, 0);
        if ( v2 >= 0 )
        {
          if ( !RtlValidSecurityDescriptor(SecurityDescriptor) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2758;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"RtlValidSecurityDescriptor(&SecurityDescriptor)",
              2758,
              0,
              0,
              0,
              0);
          }
          GenericMapping.GenericAll = 2031616;
          GenericMapping.GenericRead = 0x20000;
          GenericMapping.GenericWrite = 0x20000;
          GenericMapping.GenericExecute = 0x20000;
          GrantedAccess = 0;
          AccessStatus = 0;
          if ( SeAccessCheck(
                 SecurityDescriptor,
                 &SubjectContext,
                 0,
                 0x1F0000u,
                 0,
                 0,
                 &GenericMapping,
                 1,
                 &GrantedAccess,
                 &AccessStatus)
            || g_OSTestSigningEnabled )
          {
            __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v8);
            v2 = 0;
            goto LABEL_19;
          }
          v2 = AccessStatus;
        }
        else
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2757;
        }
        goto LABEL_5;
      }
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2756;
    }
    else
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2755;
    }
    __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v8);
    v2 = Acl;
    goto LABEL_19;
  }
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 2745;
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&void SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&void SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>(&p_SubjectContext);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1402ea8c8  push    rbp
0x1402ea8ca  push    rbx
0x1402ea8cb  push    rsi
0x1402ea8cc  push    r14
0x1402ea8ce  lea     rbp, [rsp-3Fh]
0x1402ea8d3  sub     rsp, 0D8h
0x1402ea8da  mov     rax, cs:__security_cookie
0x1402ea8e1  xor     rax, rsp
0x1402ea8e4  mov     [rbp+57h+var_30], rax
0x1402ea8e8  xorps   xmm0, xmm0
0x1402ea8eb  mov     r14, rcx
0x1402ea8ee  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1402ea8f2  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1402ea8f6  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1402ea8fa  call    cs:__imp_SeCaptureSubjectContext
0x1402ea901  nop     dword ptr [rax+rax+00h]
0x1402ea906  xorps   xmm0, xmm0
0x1402ea909  lea     rax, [rbp+57h+SubjectContext]
0x1402ea90d  mov     [rbp+57h+var_90], rax
0x1402ea911  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402ea915  xor     eax, eax
0x1402ea917  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1402ea91b  mov     [rbp+57h+var_68], rax
0x1402ea91f  movups  [rbp+57h+var_78], xmm0
0x1402ea923  lea     edx, [rax+1]; Revision
0x1402ea926  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402ea92d  nop     dword ptr [rax+rax+00h]
0x1402ea932  movsxd  rbx, eax
0x1402ea935  test    eax, eax
0x1402ea937  jns     short loc_1402EA95C
0x1402ea939  mov     rdx, rbx
0x1402ea93c  mov     ecx, 2
0x1402ea941  call    cs:__imp_WdLogSingleEntry1
0x1402ea948  nop     dword ptr [rax+rax+00h]
0x1402ea94d  mov     cs:WdLogGlobalForLineNumber, 0AB9h
0x1402ea957  jmp     loc_1402EAB93
0x1402ea95c  mov     rcx, r14; Sid
0x1402ea95f  call    cs:__imp_RtlLengthSid
0x1402ea966  nop     dword ptr [rax+rax+00h]
0x1402ea96b  mov     ecx, 100h
0x1402ea970  mov     r8d, 4B677844h
0x1402ea976  lea     esi, [rax+14h]
0x1402ea979  mov     edx, esi
0x1402ea97b  call    cs:__imp_ExAllocatePool2
0x1402ea982  nop     dword ptr [rax+rax+00h]
0x1402ea987  mov     [rbp+57h+var_A0], rax
0x1402ea98b  mov     rbx, rax
0x1402ea98e  test    rax, rax
0x1402ea991  jnz     short loc_1402EA9C4
0x1402ea993  mov     rbx, 0FFFFFFFFC000009Ah
0x1402ea99a  lea     ecx, [rax+2]
0x1402ea99d  mov     rdx, rbx
0x1402ea9a0  call    cs:__imp_WdLogSingleEntry1
0x1402ea9a7  nop     dword ptr [rax+rax+00h]
0x1402ea9ac  mov     cs:WdLogGlobalForLineNumber, 0ABFh
0x1402ea9b6  lea     rcx, [rbp+57h+var_A0]
0x1402ea9ba  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402ea9bf  jmp     loc_1402EAB93
0x1402ea9c4  mov     r8d, 2; AclRevision
0x1402ea9ca  mov     edx, esi; AclLength
0x1402ea9cc  mov     rcx, rbx; Acl
0x1402ea9cf  call    cs:__imp_RtlCreateAcl
0x1402ea9d6  nop     dword ptr [rax+rax+00h]
0x1402ea9db  movsxd  rsi, eax
0x1402ea9de  test    eax, eax
0x1402ea9e0  jns     short loc_1402EAA10
0x1402ea9e2  mov     rdx, rsi
0x1402ea9e5  mov     ecx, 2
0x1402ea9ea  call    cs:__imp_WdLogSingleEntry1
0x1402ea9f1  nop     dword ptr [rax+rax+00h]
0x1402ea9f6  mov     cs:WdLogGlobalForLineNumber, 0AC3h
0x1402eaa00  lea     rcx, [rbp+57h+var_A0]
0x1402eaa04  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402eaa09  mov     ebx, esi
0x1402eaa0b  jmp     loc_1402EAB93
0x1402eaa10  mov     r9, r14; Sid
0x1402eaa13  mov     edx, 2; AceRevision
0x1402eaa18  mov     r14d, 1F0000h
0x1402eaa1e  mov     rcx, rbx; Acl
0x1402eaa21  mov     r8d, r14d; AccessMask
0x1402eaa24  call    cs:__imp_RtlAddAccessAllowedAce
0x1402eaa2b  nop     dword ptr [rax+rax+00h]
0x1402eaa30  movsxd  rsi, eax
0x1402eaa33  test    eax, eax
0x1402eaa35  jns     short loc_1402EAA57
0x1402eaa37  mov     rdx, rsi
0x1402eaa3a  mov     ecx, 2
0x1402eaa3f  call    cs:__imp_WdLogSingleEntry1
0x1402eaa46  nop     dword ptr [rax+rax+00h]
0x1402eaa4b  mov     cs:WdLogGlobalForLineNumber, 0AC4h
0x1402eaa55  jmp     short loc_1402EAA00
0x1402eaa57  xor     r9d, r9d; DaclDefaulted
0x1402eaa5a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402eaa5e  mov     r8, rbx; Dacl
0x1402eaa61  mov     dl, 1; DaclPresent
0x1402eaa63  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402eaa6a  nop     dword ptr [rax+rax+00h]
0x1402eaa6f  movsxd  rbx, eax
0x1402eaa72  test    eax, eax
0x1402eaa74  jns     short loc_1402EAA99
0x1402eaa76  mov     rdx, rbx
0x1402eaa79  mov     ecx, 2
0x1402eaa7e  call    cs:__imp_WdLogSingleEntry1
0x1402eaa85  nop     dword ptr [rax+rax+00h]
0x1402eaa8a  mov     cs:WdLogGlobalForLineNumber, 0AC5h
0x1402eaa94  jmp     loc_1402EA9B6
0x1402eaa99  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402eaa9d  call    cs:__imp_RtlValidSecurityDescriptor
0x1402eaaa4  nop     dword ptr [rax+rax+00h]
0x1402eaaa9  test    al, al
0x1402eaaab  jnz     short loc_1402EAB09
0x1402eaaad  mov     ecx, 1
0x1402eaab2  call    cs:__imp_WdLogSingleEntry0
0x1402eaab9  nop     dword ptr [rax+rax+00h]
0x1402eaabe  mov     [rsp+0F0h+GrantedAccess], 0
0x1402eaac7  lea     r9, aRtlvalidsecuri; "RtlValidSecurityDescriptor(&SecurityDes"...
0x1402eaace  mov     qword ptr [rsp+0F0h+AccessMode], 0
0x1402eaad7  mov     eax, 0AC6h
0x1402eaadc  mov     [rsp+0F0h+GenericMapping], 0
0x1402eaae5  or      r8d, 0FFFFFFFFh
0x1402eaae9  mov     [rsp+0F0h+Privileges], 0
0x1402eaaf2  mov     edx, 40002h
0x1402eaaf7  xor     ecx, ecx
0x1402eaaf9  mov     qword ptr [rsp+0F0h+PreviouslyGrantedAccess], rax
0x1402eaafe  mov     cs:WdLogGlobalForLineNumber, eax
0x1402eab04  call    DxgkLogInternalTriageEvent
0x1402eab09  mov     eax, 20000h
0x1402eab0e  mov     [rbp+57h+var_40.GenericAll], r14d
0x1402eab12  mov     [rbp+57h+var_40.GenericRead], eax
0x1402eab15  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1402eab19  mov     [rbp+57h+var_40.GenericWrite], eax
0x1402eab1c  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402eab20  mov     [rbp+57h+var_40.GenericExecute], eax
0x1402eab23  mov     r9d, r14d; DesiredAccess
0x1402eab26  lea     rax, [rbp+57h+var_98]
0x1402eab2a  mov     [rbp+57h+var_94], 0
0x1402eab31  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x1402eab36  xor     r8d, r8d; SubjectContextLocked
0x1402eab39  lea     rax, [rbp+57h+var_94]
0x1402eab3d  mov     [rbp+57h+var_98], 0
0x1402eab44  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x1402eab49  lea     rax, [rbp+57h+var_40]
0x1402eab4d  mov     [rsp+0F0h+AccessMode], 1; AccessMode
0x1402eab52  mov     [rsp+0F0h+GenericMapping], rax; GenericMapping
0x1402eab57  mov     [rsp+0F0h+Privileges], 0; Privileges
0x1402eab60  mov     [rsp+0F0h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1402eab68  call    cs:__imp_SeAccessCheck
0x1402eab6f  nop     dword ptr [rax+rax+00h]
0x1402eab74  test    al, al
0x1402eab76  jnz     short loc_1402EAB88
0x1402eab78  cmp     cs:?g_OSTestSigningEnabled@@3EA, al; uchar g_OSTestSigningEnabled
0x1402eab7e  jnz     short loc_1402EAB88
0x1402eab80  mov     ebx, [rbp+57h+var_98]
0x1402eab83  jmp     loc_1402EA9B6
0x1402eab88  lea     rcx, [rbp+57h+var_A0]
0x1402eab8c  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402eab91  xor     ebx, ebx
0x1402eab93  lea     rcx, [rbp+57h+var_90]
0x1402eab97  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_SUBJECT_CONTEXT@@$$A6AXPEAU1@@Z$1?SeReleaseSubjectContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>(void)
0x1402eab9c  mov     eax, ebx
0x1402eab9e  mov     rcx, [rbp+57h+var_30]
0x1402eaba2  xor     rcx, rsp; StackCookie
0x1402eaba5  call    __security_check_cookie
0x1402eabaa  add     rsp, 0D8h
0x1402eabb1  pop     r14
0x1402eabb3  pop     rsi
0x1402eabb4  pop     rbx
0x1402eabb5  pop     rbp
0x1402eabb6  retn
```
