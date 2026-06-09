# CheckCallerMatchesSid

- ea: `0x1402f1378`
- end: `0x1402f1668`
- name: `CheckCallerMatchesSid`
- size: `752`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402f3028`

## callees

- `0x14001b9c0`
- `0x1400627a4`
- `0x140093414`
- `0x1400a0bd0`
- `0x1402f1378`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402f142b`
- `ntoskrnl!ExAllocatePool2` at `0x1402f142b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402f13aa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402f13aa`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402f13d6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402f13d6`
- `ntoskrnl!RtlLengthSid` at `0x1402f140f`
- `ntoskrnl!RtlLengthSid` at `0x1402f140f`
- `ntoskrnl!RtlCreateAcl` at `0x1402f147f`
- `ntoskrnl!RtlCreateAcl` at `0x1402f147f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402f14d4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1402f14d4`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402f1513`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402f1513`
- `ntoskrnl!SeAccessCheck` at `0x1402f1618`
- `ntoskrnl!SeAccessCheck` at `0x1402f1618`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402f154d`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402f154d`
- `watchdog!WdLogSingleEntry0` at `0x1402f1562`
- `watchdog!WdLogSingleEntry0` at `0x1402f1562`
- `watchdog!WdLogSingleEntry1` at `0x1402f13f1`
- `watchdog!WdLogSingleEntry1` at `0x1402f1450`
- `watchdog!WdLogSingleEntry1` at `0x1402f149a`
- `watchdog!WdLogSingleEntry1` at `0x1402f14ef`
- `watchdog!WdLogSingleEntry1` at `0x1402f152e`
- `watchdog!WdLogSingleEntry1` at `0x1402f13f1`
- `watchdog!WdLogSingleEntry1` at `0x1402f1450`
- `watchdog!WdLogSingleEntry1` at `0x1402f149a`
- `watchdog!WdLogSingleEntry1` at `0x1402f14ef`
- `watchdog!WdLogSingleEntry1` at `0x1402f152e`

## string_xrefs

- `0x1402f1577`: `RtlValidSecurityDescriptor(&SecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall CheckCallerMatchesSid(PSID Sid)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rsi
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rbx
  NTSTATUS Acl; // eax
  NTSTATUS v8; // esi
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  struct _ACL *v12; // [rsp+50h] [rbp-49h] BYREF
  int AccessStatus; // [rsp+58h] [rbp-41h] BYREF
  DWORD GrantedAccess; // [rsp+5Ch] [rbp-3Dh] BYREF
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // [rsp+60h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v17; // [rsp+88h] [rbp-11h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+90h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+B0h] [rbp+17h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  p_SubjectContext = &SubjectContext;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v17 = 0;
  v2 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = RtlLengthSid(Sid) + 20;
    Pool2 = (struct _ACL *)ExAllocatePool2(256, v4, 1265072196);
    v12 = Pool2;
    v6 = Pool2;
    if ( !Pool2 )
    {
      v3 = -1073741670;
      WdLogSingleEntry1(2, -1073741670);
      WdLogGlobalForLineNumber = 2751;
LABEL_5:
      __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v12);
      goto LABEL_19;
    }
    Acl = RtlCreateAcl(Pool2, v4, 2u);
    v8 = Acl;
    if ( Acl >= 0 )
    {
      v9 = RtlAddAccessAllowedAce(v6, 2u, 0x1F0000u, Sid);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v10 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
        v3 = v10;
        if ( v10 >= 0 )
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
            __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v12);
            v3 = 0;
            goto LABEL_19;
          }
          v3 = AccessStatus;
        }
        else
        {
          WdLogSingleEntry1(2, v10);
          WdLogGlobalForLineNumber = 2757;
        }
        goto LABEL_5;
      }
      WdLogSingleEntry1(2, v9);
      WdLogGlobalForLineNumber = 2756;
    }
    else
    {
      WdLogSingleEntry1(2, Acl);
      WdLogGlobalForLineNumber = 2755;
    }
    __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    v3 = v8;
    goto LABEL_19;
  }
  WdLogSingleEntry1(2, v2);
  WdLogGlobalForLineNumber = 2745;
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&void SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&void SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>(&p_SubjectContext);
  return v3;
}

```

## disassembly

```asm
0x1402f1378  push    rbp
0x1402f137a  push    rbx
0x1402f137b  push    rsi
0x1402f137c  push    r14
0x1402f137e  lea     rbp, [rsp-3Fh]
0x1402f1383  sub     rsp, 0D8h
0x1402f138a  mov     rax, cs:__security_cookie
0x1402f1391  xor     rax, rsp
0x1402f1394  mov     [rbp+57h+var_30], rax
0x1402f1398  xorps   xmm0, xmm0
0x1402f139b  mov     r14, rcx
0x1402f139e  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1402f13a2  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1402f13a6  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1402f13aa  call    cs:__imp_SeCaptureSubjectContext
0x1402f13b1  nop     dword ptr [rax+rax+00h]
0x1402f13b6  xorps   xmm0, xmm0
0x1402f13b9  lea     rax, [rbp+57h+SubjectContext]
0x1402f13bd  mov     [rbp+57h+var_90], rax
0x1402f13c1  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402f13c5  xor     eax, eax
0x1402f13c7  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1402f13cb  mov     [rbp+57h+var_68], rax
0x1402f13cf  movups  [rbp+57h+var_78], xmm0
0x1402f13d3  lea     edx, [rax+1]; Revision
0x1402f13d6  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402f13dd  nop     dword ptr [rax+rax+00h]
0x1402f13e2  movsxd  rbx, eax
0x1402f13e5  test    eax, eax
0x1402f13e7  jns     short loc_1402F140C
0x1402f13e9  mov     rdx, rbx
0x1402f13ec  mov     ecx, 2
0x1402f13f1  call    cs:__imp_WdLogSingleEntry1
0x1402f13f8  nop     dword ptr [rax+rax+00h]
0x1402f13fd  mov     cs:WdLogGlobalForLineNumber, 0AB9h
0x1402f1407  jmp     loc_1402F1643
0x1402f140c  mov     rcx, r14; Sid
0x1402f140f  call    cs:__imp_RtlLengthSid
0x1402f1416  nop     dword ptr [rax+rax+00h]
0x1402f141b  mov     ecx, 100h
0x1402f1420  mov     r8d, 4B677844h
0x1402f1426  lea     esi, [rax+14h]
0x1402f1429  mov     edx, esi
0x1402f142b  call    cs:__imp_ExAllocatePool2
0x1402f1432  nop     dword ptr [rax+rax+00h]
0x1402f1437  mov     [rbp+57h+var_A0], rax
0x1402f143b  mov     rbx, rax
0x1402f143e  test    rax, rax
0x1402f1441  jnz     short loc_1402F1474
0x1402f1443  mov     rbx, 0FFFFFFFFC000009Ah
0x1402f144a  lea     ecx, [rax+2]
0x1402f144d  mov     rdx, rbx
0x1402f1450  call    cs:__imp_WdLogSingleEntry1
0x1402f1457  nop     dword ptr [rax+rax+00h]
0x1402f145c  mov     cs:WdLogGlobalForLineNumber, 0ABFh
0x1402f1466  lea     rcx, [rbp+57h+var_A0]
0x1402f146a  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402f146f  jmp     loc_1402F1643
0x1402f1474  mov     r8d, 2; AclRevision
0x1402f147a  mov     edx, esi; AclLength
0x1402f147c  mov     rcx, rbx; Acl
0x1402f147f  call    cs:__imp_RtlCreateAcl
0x1402f1486  nop     dword ptr [rax+rax+00h]
0x1402f148b  movsxd  rsi, eax
0x1402f148e  test    eax, eax
0x1402f1490  jns     short loc_1402F14C0
0x1402f1492  mov     rdx, rsi
0x1402f1495  mov     ecx, 2
0x1402f149a  call    cs:__imp_WdLogSingleEntry1
0x1402f14a1  nop     dword ptr [rax+rax+00h]
0x1402f14a6  mov     cs:WdLogGlobalForLineNumber, 0AC3h
0x1402f14b0  lea     rcx, [rbp+57h+var_A0]
0x1402f14b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402f14b9  mov     ebx, esi
0x1402f14bb  jmp     loc_1402F1643
0x1402f14c0  mov     r9, r14; Sid
0x1402f14c3  mov     edx, 2; AceRevision
0x1402f14c8  mov     r14d, 1F0000h
0x1402f14ce  mov     rcx, rbx; Acl
0x1402f14d1  mov     r8d, r14d; AccessMask
0x1402f14d4  call    cs:__imp_RtlAddAccessAllowedAce
0x1402f14db  nop     dword ptr [rax+rax+00h]
0x1402f14e0  movsxd  rsi, eax
0x1402f14e3  test    eax, eax
0x1402f14e5  jns     short loc_1402F1507
0x1402f14e7  mov     rdx, rsi
0x1402f14ea  mov     ecx, 2
0x1402f14ef  call    cs:__imp_WdLogSingleEntry1
0x1402f14f6  nop     dword ptr [rax+rax+00h]
0x1402f14fb  mov     cs:WdLogGlobalForLineNumber, 0AC4h
0x1402f1505  jmp     short loc_1402F14B0
0x1402f1507  xor     r9d, r9d; DaclDefaulted
0x1402f150a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402f150e  mov     r8, rbx; Dacl
0x1402f1511  mov     dl, 1; DaclPresent
0x1402f1513  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402f151a  nop     dword ptr [rax+rax+00h]
0x1402f151f  movsxd  rbx, eax
0x1402f1522  test    eax, eax
0x1402f1524  jns     short loc_1402F1549
0x1402f1526  mov     rdx, rbx
0x1402f1529  mov     ecx, 2
0x1402f152e  call    cs:__imp_WdLogSingleEntry1
0x1402f1535  nop     dword ptr [rax+rax+00h]
0x1402f153a  mov     cs:WdLogGlobalForLineNumber, 0AC5h
0x1402f1544  jmp     loc_1402F1466
0x1402f1549  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402f154d  call    cs:__imp_RtlValidSecurityDescriptor
0x1402f1554  nop     dword ptr [rax+rax+00h]
0x1402f1559  test    al, al
0x1402f155b  jnz     short loc_1402F15B9
0x1402f155d  mov     ecx, 1
0x1402f1562  call    cs:__imp_WdLogSingleEntry0
0x1402f1569  nop     dword ptr [rax+rax+00h]
0x1402f156e  mov     [rsp+0F0h+GrantedAccess], 0
0x1402f1577  lea     r9, aRtlvalidsecuri; "RtlValidSecurityDescriptor(&SecurityDes"...
0x1402f157e  mov     qword ptr [rsp+0F0h+AccessMode], 0
0x1402f1587  mov     eax, 0AC6h
0x1402f158c  mov     [rsp+0F0h+GenericMapping], 0
0x1402f1595  or      r8d, 0FFFFFFFFh
0x1402f1599  mov     [rsp+0F0h+Privileges], 0
0x1402f15a2  mov     edx, 40002h
0x1402f15a7  xor     ecx, ecx
0x1402f15a9  mov     qword ptr [rsp+0F0h+PreviouslyGrantedAccess], rax
0x1402f15ae  mov     cs:WdLogGlobalForLineNumber, eax
0x1402f15b4  call    DxgkLogInternalTriageEvent
0x1402f15b9  mov     eax, 20000h
0x1402f15be  mov     [rbp+57h+var_40.GenericAll], r14d
0x1402f15c2  mov     [rbp+57h+var_40.GenericRead], eax
0x1402f15c5  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1402f15c9  mov     [rbp+57h+var_40.GenericWrite], eax
0x1402f15cc  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1402f15d0  mov     [rbp+57h+var_40.GenericExecute], eax
0x1402f15d3  mov     r9d, r14d; DesiredAccess
0x1402f15d6  lea     rax, [rbp+57h+var_98]
0x1402f15da  mov     [rbp+57h+var_94], 0
0x1402f15e1  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x1402f15e6  xor     r8d, r8d; SubjectContextLocked
0x1402f15e9  lea     rax, [rbp+57h+var_94]
0x1402f15ed  mov     [rbp+57h+var_98], 0
0x1402f15f4  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x1402f15f9  lea     rax, [rbp+57h+var_40]
0x1402f15fd  mov     [rsp+0F0h+AccessMode], 1; AccessMode
0x1402f1602  mov     [rsp+0F0h+GenericMapping], rax; GenericMapping
0x1402f1607  mov     [rsp+0F0h+Privileges], 0; Privileges
0x1402f1610  mov     [rsp+0F0h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1402f1618  call    cs:__imp_SeAccessCheck
0x1402f161f  nop     dword ptr [rax+rax+00h]
0x1402f1624  test    al, al
0x1402f1626  jnz     short loc_1402F1638
0x1402f1628  cmp     cs:?g_OSTestSigningEnabled@@3EA, al; uchar g_OSTestSigningEnabled
0x1402f162e  jnz     short loc_1402F1638
0x1402f1630  mov     ebx, [rbp+57h+var_98]
0x1402f1633  jmp     loc_1402F1466
0x1402f1638  lea     rcx, [rbp+57h+var_A0]
0x1402f163c  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402f1641  xor     ebx, ebx
0x1402f1643  lea     rcx, [rbp+57h+var_90]
0x1402f1647  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_SUBJECT_CONTEXT@@$$A6AXPEAU1@@Z$1?SeReleaseSubjectContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_SUBJECT_CONTEXT *,void (_SECURITY_SUBJECT_CONTEXT *),&SeReleaseSubjectContext(_SECURITY_SUBJECT_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_SUBJECT_CONTEXT *,_SECURITY_SUBJECT_CONTEXT *,0,std::nullptr_t>>(void)
0x1402f164c  mov     eax, ebx
0x1402f164e  mov     rcx, [rbp+57h+var_30]
0x1402f1652  xor     rcx, rsp; StackCookie
0x1402f1655  call    __security_check_cookie
0x1402f165a  add     rsp, 0D8h
0x1402f1661  pop     r14
0x1402f1663  pop     rsi
0x1402f1664  pop     rbx
0x1402f1665  pop     rbp
0x1402f1666  retn
```
