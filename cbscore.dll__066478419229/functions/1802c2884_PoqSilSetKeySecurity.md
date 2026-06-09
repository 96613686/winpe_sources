# PoqSilSetKeySecurity

- ea: `0x1802c2884`
- end: `0x1802c2c30`
- name: `PoqSilSetKeySecurity`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1802c1040`
- `0x1802c5c40`

## callees

- `0x180046198`
- `0x1800a26b0`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1801f7e90`
- `0x1802be3cc`
- `0x1802c2884`
- `0x1802c5684`
- `0x1802d5010`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x1802c2945`
- `ntdll!RtlDuplicateUnicodeString` at `0x1802c2945`
- `ntdll!RtlEqualUnicodeString` at `0x1802c28e4`
- `ntdll!RtlEqualUnicodeString` at `0x1802c28e4`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1802c2ae7`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1802c2ae7`
- `ntdll!RtlFindAceByType` at `0x1802c2bb9`
- `ntdll!RtlFindAceByType` at `0x1802c2bb9`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1802c2a9d`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1802c2a9d`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1802c2a5a`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1802c2a5a`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1802c2b31`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1802c2b31`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1802c2a00`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1802c2a00`

## string_xrefs

- `0x1802c297a`: `RtlDuplicateUnicodeString( 0, &Operation->Path, TempName.GetMutablePointer())`
- `0x1802c2a2e`: `RtlGetControlSecurityDescriptor( Operation->SecurityDescriptor, &Control, &Revision)`
- `0x1802c2b15`: `RtlGetDaclSecurityDescriptor( Operation->SecurityDescriptor, &fDaclPresent, &Dacl, &fDefaulted)`
- `0x1802c2b5f`: `RtlGetSaclSecurityDescriptor( Operation->SecurityDescriptor, &fSaclPresent, &Sacl, &fDefaulted)`
- `0x1802c2a88`: `RtlGetOwnerSecurityDescriptor( Operation->SecurityDescriptor, &Owner, &fDefaulted)`
- `0x1802c2acb`: `RtlGetGroupSecurityDescriptor( Operation->SecurityDescriptor, &Group, &fDefaulted)`
- `0x1802c296c`: `PoqSilSetKeySecurity`
- `0x1802c2a23`: `PoqSilSetKeySecurity`
- `0x1802c2a7d`: `PoqSilSetKeySecurity`
- `0x1802c2ac0`: `PoqSilSetKeySecurity`
- `0x1802c2b0a`: `PoqSilSetKeySecurity`
- `0x1802c2b54`: `PoqSilSetKeySecurity`

## pseudocode

```c
__int64 __fastcall PoqSilSetKeySecurity(__int64 a1, __int64 a2, __int64 a3)
{
  const UNICODE_STRING *v3; // r14
  int v7; // ebx
  NTSTATUS v8; // eax
  __int64 result; // rax
  void *v10; // rcx
  __int64 v11; // r14
  NTSTATUS ControlSecurityDescriptor; // eax
  const char *v13; // rcx
  unsigned int v14; // ebx
  const char *v15; // [rsp+40h] [rbp-69h] BYREF
  const char *v16; // [rsp+48h] [rbp-61h]
  __int64 v17; // [rsp+50h] [rbp-59h]
  const char *v18; // [rsp+58h] [rbp-51h]
  PACL Sacl; // [rsp+60h] [rbp-49h] BYREF
  PSID Group; // [rsp+68h] [rbp-41h] BYREF
  PSID Owner; // [rsp+70h] [rbp-39h] BYREF
  PACL Dacl; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int8 DaclPresent; // [rsp+81h] [rbp-28h] BYREF
  unsigned __int8 SaclPresent[2]; // [rsp+82h] [rbp-27h] BYREF
  WORD Control; // [rsp+84h] [rbp-25h] BYREF
  int v27; // [rsp+88h] [rbp-21h] BYREF
  __int64 v28; // [rsp+90h] [rbp-19h] BYREF
  ULONG Revision; // [rsp+98h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v31; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v32; // [rsp+C0h] [rbp+17h]

  v3 = (const UNICODE_STRING *)(a2 + 8);
  v32 = 0;
  v27 = 0;
  v31 = 0;
  RtlInitLUnicodeStringFromUnicodeString(a2 + 8, &v31);
  if ( !RtlEqualUnicodeString(v3, (PCUNICODE_STRING)(a3 + 72), 1u) )
  {
    v28 = 0;
    DestinationString = 0;
    OperationContext::ClearKeyContext((OperationContext *)a3);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *, __int64 *, _QWORD))(*(_QWORD *)a1 + 48LL))(
           a1,
           2,
           17760319,
           &v31,
           &v28,
           0);
    if ( v7 < 0 )
    {
LABEL_5:
      Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&DestinationString);
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v28);
      return (unsigned int)v7;
    }
    v8 = RtlDuplicateUnicodeString(0, v3, &DestinationString);
    if ( v8 < 0 )
    {
      v17 = 2830;
      v15 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v16 = "PoqSilSetKeySecurity";
      v18 = "RtlDuplicateUnicodeString( 0, &Operation->Path, TempName.GetMutablePointer())";
      v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v27,
             &v15,
             (unsigned int)v8);
      goto LABEL_5;
    }
    OperationContext::TakeOwnership(a3, &DestinationString, &v28);
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&DestinationString);
    Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v28);
  }
  v10 = *(void **)(a2 + 24);
  v11 = *(_QWORD *)(a3 + 96);
  Control = 0;
  Revision = 0;
  Owner = 0;
  Group = 0;
  Dacl = 0;
  Sacl = 0;
  DaclPresent = 0;
  SaclPresent[0] = 0;
  OwnerDefaulted = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(v10, &Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v17 = 2855;
    v15 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v16 = "PoqSilSetKeySecurity";
    v13 = "RtlGetControlSecurityDescriptor( Operation->SecurityDescriptor, &Control, &Revision)";
LABEL_9:
    v18 = v13;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v27,
             &v15,
             (unsigned int)ControlSecurityDescriptor);
  }
  ControlSecurityDescriptor = RtlGetOwnerSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 24), &Owner, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v17 = 2860;
    v15 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v16 = "PoqSilSetKeySecurity";
    v13 = "RtlGetOwnerSecurityDescriptor( Operation->SecurityDescriptor, &Owner, &fDefaulted)";
    goto LABEL_9;
  }
  ControlSecurityDescriptor = RtlGetGroupSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 24), &Group, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v17 = 2865;
    v15 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v16 = "PoqSilSetKeySecurity";
    v13 = "RtlGetGroupSecurityDescriptor( Operation->SecurityDescriptor, &Group, &fDefaulted)";
    goto LABEL_9;
  }
  ControlSecurityDescriptor = RtlGetDaclSecurityDescriptor(
                                *(PSECURITY_DESCRIPTOR *)(a2 + 24),
                                &DaclPresent,
                                &Dacl,
                                &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v17 = 2871;
    v15 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v16 = "PoqSilSetKeySecurity";
    v13 = "RtlGetDaclSecurityDescriptor( Operation->SecurityDescriptor, &fDaclPresent, &Dacl, &fDefaulted)";
    goto LABEL_9;
  }
  ControlSecurityDescriptor = RtlGetSaclSecurityDescriptor(
                                *(PSECURITY_DESCRIPTOR *)(a2 + 24),
                                SaclPresent,
                                &Sacl,
                                &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v17 = 2877;
    v15 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v16 = "PoqSilSetKeySecurity";
    v13 = "RtlGetSaclSecurityDescriptor( Operation->SecurityDescriptor, &fSaclPresent, &Sacl, &fDefaulted)";
    goto LABEL_9;
  }
  v14 = Owner != 0;
  if ( Group )
    v14 |= 2u;
  if ( DaclPresent )
  {
    v14 |= 4u;
    if ( (Control & 0x1000) != 0 )
      v14 |= 0x80000000;
  }
  if ( SaclPresent[0] )
  {
    v14 |= ((Control & 0x2000) << 17) | 8;
    if ( RtlFindAceByType(Sacl, 17) )
      v14 |= 0x10u;
  }
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, PSID, PSID, PACL, PACL))(*(_QWORD *)v11 + 40LL))(
             v11,
             *(_DWORD *)a2 & 1,
             v14,
             Owner,
             Group,
             Dacl,
             Sacl);
  if ( (int)result >= 0 )
  {
    OperationContext::ClearKeyContext((OperationContext *)a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1802c2884  push    rbp
0x1802c2886  push    rbx
0x1802c2887  push    rsi
0x1802c2888  push    rdi
0x1802c2889  push    r12
0x1802c288b  push    r14
0x1802c288d  push    r15
0x1802c288f  lea     rbp, [rsp-27h]
0x1802c2894  sub     rsp, 0D0h
0x1802c289b  mov     rax, cs:__security_cookie
0x1802c28a2  xor     rax, rsp
0x1802c28a5  mov     [rbp+57h+var_38], rax
0x1802c28a9  lea     r14, [rdx+8]
0x1802c28ad  mov     rdi, rdx
0x1802c28b0  mov     rbx, rcx
0x1802c28b3  lea     rdx, [rbp+57h+var_50]
0x1802c28b7  xorps   xmm0, xmm0
0x1802c28ba  xor     eax, eax
0x1802c28bc  xor     r15d, r15d
0x1802c28bf  mov     [rbp+57h+var_40], rax
0x1802c28c3  mov     rcx, r14
0x1802c28c6  mov     [rbp+57h+var_78], r15d
0x1802c28ca  mov     rsi, r8
0x1802c28cd  movups  [rbp+57h+var_50], xmm0
0x1802c28d1  call    RtlInitLUnicodeStringFromUnicodeString
0x1802c28d6  lea     r12d, [r15+1]
0x1802c28da  mov     rcx, r14; String1
0x1802c28dd  mov     r8b, r12b; CaseInsensitive
0x1802c28e0  lea     rdx, [rsi+48h]; String2
0x1802c28e4  call    cs:__imp_RtlEqualUnicodeString
0x1802c28eb  nop     dword ptr [rax+rax+00h]
0x1802c28f0  test    al, al
0x1802c28f2  jnz     loc_1802C29CB
0x1802c28f8  xorps   xmm0, xmm0
0x1802c28fb  mov     [rbp+57h+var_70], r15
0x1802c28ff  mov     rcx, rsi; this
0x1802c2902  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1802c2906  call    ?ClearKeyContext@OperationContext@@QEAAXXZ; OperationContext::ClearKeyContext(void)
0x1802c290b  mov     rax, [rbx]
0x1802c290e  lea     rcx, [rbp+57h+var_70]
0x1802c2912  mov     [rsp+100h+var_D8], r15
0x1802c2917  lea     r9, [rbp+57h+var_50]
0x1802c291b  mov     [rsp+100h+var_E0], rcx
0x1802c2920  lea     edx, [r15+2]
0x1802c2924  mov     r8d, 10F003Fh
0x1802c292a  mov     rcx, rbx
0x1802c292d  mov     rax, [rax+30h]
0x1802c2931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c2936  mov     ebx, eax
0x1802c2938  test    eax, eax
0x1802c293a  js      short loc_1802C2990
0x1802c293c  lea     r8, [rbp+57h+DestinationString]; DestinationString
0x1802c2940  mov     rdx, r14; SourceString
0x1802c2943  xor     ecx, ecx; Flags
0x1802c2945  call    cs:__imp_RtlDuplicateUnicodeString
0x1802c294c  nop     dword ptr [rax+rax+00h]
0x1802c2951  test    eax, eax
0x1802c2953  jns     short loc_1802C29A9
0x1802c2955  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c295c  mov     [rbp+57h+var_B0], 0B0Eh
0x1802c2964  mov     [rbp+57h+var_C0], rcx
0x1802c2968  lea     rdx, [rbp+57h+var_C0]
0x1802c296c  lea     rcx, aPoqsilsetkeyse; "PoqSilSetKeySecurity"
0x1802c2973  mov     r8d, eax
0x1802c2976  mov     [rbp+57h+var_B8], rcx
0x1802c297a  lea     rcx, aRtlduplicateun_4; "RtlDuplicateUnicodeString( 0, &Operatio"...
0x1802c2981  mov     [rbp+57h+var_A8], rcx
0x1802c2985  lea     rcx, [rbp+57h+var_78]
0x1802c2989  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c298e  mov     ebx, eax
0x1802c2990  lea     rcx, [rbp+57h+DestinationString]
0x1802c2994  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1802c2999  lea     rcx, [rbp+57h+var_70]
0x1802c299d  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c29a2  mov     eax, ebx
0x1802c29a4  jmp     loc_1802C2C11
0x1802c29a9  lea     r8, [rbp+57h+var_70]
0x1802c29ad  mov     rcx, rsi
0x1802c29b0  lea     rdx, [rbp+57h+DestinationString]
0x1802c29b4  call    ?TakeOwnership@OperationContext@@QEAAX$$QEAV?$Auto@U_UNICODE_STRING@@@Windows@@$$QEAV?$Auto@PEAUIRtlKey@Rtl@Windows@@@3@@Z; OperationContext::TakeOwnership(Windows::Auto<_UNICODE_STRING> &&,Windows::Auto<Windows::Rtl::IRtlKey *> &&)
0x1802c29b9  lea     rcx, [rbp+57h+DestinationString]
0x1802c29bd  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1802c29c2  lea     rcx, [rbp+57h+var_70]
0x1802c29c6  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c29cb  mov     rcx, [rdi+18h]; SecurityDescriptor
0x1802c29cf  lea     r8, [rbp+57h+Revision]; Revision
0x1802c29d3  mov     r14, [rsi+60h]
0x1802c29d7  lea     rdx, [rbp+57h+Control]; Control
0x1802c29db  mov     [rbp+57h+Control], r15w
0x1802c29e0  mov     [rbp+57h+Revision], r15d
0x1802c29e4  mov     [rbp+57h+Owner], r15
0x1802c29e8  mov     [rbp+57h+Group], r15
0x1802c29ec  mov     [rbp+57h+Dacl], r15
0x1802c29f0  mov     [rbp+57h+Sacl], r15
0x1802c29f4  mov     [rbp+57h+DaclPresent], r15b
0x1802c29f8  mov     [rbp+57h+SaclPresent], r15b
0x1802c29fc  mov     [rbp+57h+OwnerDefaulted], r15b
0x1802c2a00  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1802c2a07  nop     dword ptr [rax+rax+00h]
0x1802c2a0c  test    eax, eax
0x1802c2a0e  jns     short loc_1802C2A4E
0x1802c2a10  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2a17  mov     [rbp+57h+var_B0], 0B27h
0x1802c2a1f  mov     [rbp+57h+var_C0], rcx
0x1802c2a23  lea     rcx, aPoqsilsetkeyse; "PoqSilSetKeySecurity"
0x1802c2a2a  mov     [rbp+57h+var_B8], rcx
0x1802c2a2e  lea     rcx, aRtlgetcontrols_0; "RtlGetControlSecurityDescriptor( Operat"...
0x1802c2a35  mov     [rbp+57h+var_A8], rcx
0x1802c2a39  lea     rdx, [rbp+57h+var_C0]
0x1802c2a3d  lea     rcx, [rbp+57h+var_78]
0x1802c2a41  mov     r8d, eax
0x1802c2a44  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c2a49  jmp     loc_1802C2C11
0x1802c2a4e  mov     rcx, [rdi+18h]; SecurityDescriptor
0x1802c2a52  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x1802c2a56  lea     rdx, [rbp+57h+Owner]; Owner
0x1802c2a5a  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1802c2a61  nop     dword ptr [rax+rax+00h]
0x1802c2a66  test    eax, eax
0x1802c2a68  jns     short loc_1802C2A91
0x1802c2a6a  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2a71  mov     [rbp+57h+var_B0], 0B2Ch
0x1802c2a79  mov     [rbp+57h+var_C0], rcx
0x1802c2a7d  lea     rcx, aPoqsilsetkeyse; "PoqSilSetKeySecurity"
0x1802c2a84  mov     [rbp+57h+var_B8], rcx
0x1802c2a88  lea     rcx, aRtlgetownersec_0; "RtlGetOwnerSecurityDescriptor( Operatio"...
0x1802c2a8f  jmp     short loc_1802C2A35
0x1802c2a91  mov     rcx, [rdi+18h]; SecurityDescriptor
0x1802c2a95  lea     r8, [rbp+57h+OwnerDefaulted]; GroupDefaulted
0x1802c2a99  lea     rdx, [rbp+57h+Group]; Group
0x1802c2a9d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1802c2aa4  nop     dword ptr [rax+rax+00h]
0x1802c2aa9  test    eax, eax
0x1802c2aab  jns     short loc_1802C2AD7
0x1802c2aad  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2ab4  mov     [rbp+57h+var_B0], 0B31h
0x1802c2abc  mov     [rbp+57h+var_C0], rcx
0x1802c2ac0  lea     rcx, aPoqsilsetkeyse; "PoqSilSetKeySecurity"
0x1802c2ac7  mov     [rbp+57h+var_B8], rcx
0x1802c2acb  lea     rcx, aRtlgetgroupsec_1; "RtlGetGroupSecurityDescriptor( Operatio"...
0x1802c2ad2  jmp     loc_1802C2A35
0x1802c2ad7  mov     rcx, [rdi+18h]; SecurityDescriptor
0x1802c2adb  lea     r9, [rbp+57h+OwnerDefaulted]; DaclDefaulted
0x1802c2adf  lea     r8, [rbp+57h+Dacl]; Dacl
0x1802c2ae3  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1802c2ae7  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1802c2aee  nop     dword ptr [rax+rax+00h]
0x1802c2af3  test    eax, eax
0x1802c2af5  jns     short loc_1802C2B21
0x1802c2af7  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2afe  mov     [rbp+57h+var_B0], 0B37h
0x1802c2b06  mov     [rbp+57h+var_C0], rcx
0x1802c2b0a  lea     rcx, aPoqsilsetkeyse; "PoqSilSetKeySecurity"
0x1802c2b11  mov     [rbp+57h+var_B8], rcx
0x1802c2b15  lea     rcx, aRtlgetdaclsecu_0; "RtlGetDaclSecurityDescriptor( Operation"...
0x1802c2b1c  jmp     loc_1802C2A35
0x1802c2b21  mov     rcx, [rdi+18h]; SecurityDescriptor
0x1802c2b25  lea     r9, [rbp+57h+OwnerDefaulted]; SaclDefaulted
0x1802c2b29  lea     r8, [rbp+57h+Sacl]; Sacl
0x1802c2b2d  lea     rdx, [rbp+57h+SaclPresent]; SaclPresent
0x1802c2b31  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1802c2b38  nop     dword ptr [rax+rax+00h]
0x1802c2b3d  test    eax, eax
0x1802c2b3f  jns     short loc_1802C2B6B
0x1802c2b41  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2b48  mov     [rbp+57h+var_B0], 0B3Dh
0x1802c2b50  mov     [rbp+57h+var_C0], rcx
0x1802c2b54  lea     rcx, aPoqsilsetkeyse; "PoqSilSetKeySecurity"
0x1802c2b5b  mov     [rbp+57h+var_B8], rcx
0x1802c2b5f  lea     rcx, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor( Operation"...
0x1802c2b66  jmp     loc_1802C2A35
0x1802c2b6b  cmp     [rbp+57h+Owner], r15
0x1802c2b6f  mov     ebx, r15d
0x1802c2b72  cmovnz  ebx, r12d
0x1802c2b76  cmp     [rbp+57h+Group], r15
0x1802c2b7a  jz      short loc_1802C2B7F
0x1802c2b7c  or      ebx, 2
0x1802c2b7f  cmp     [rbp+57h+DaclPresent], r15b
0x1802c2b83  jz      short loc_1802C2B97
0x1802c2b85  or      ebx, 4
0x1802c2b88  mov     eax, 1000h
0x1802c2b8d  test    [rbp+57h+Control], ax
0x1802c2b91  jz      short loc_1802C2B97
0x1802c2b93  bts     ebx, 1Fh
0x1802c2b97  cmp     [rbp+57h+SaclPresent], r15b
0x1802c2b9b  jz      short loc_1802C2BCD
0x1802c2b9d  movzx   eax, [rbp+57h+Control]
0x1802c2ba1  xor     r8d, r8d
0x1802c2ba4  mov     rcx, [rbp+57h+Sacl]
0x1802c2ba8  and     eax, 2000h
0x1802c2bad  shl     eax, 11h
0x1802c2bb0  or      ebx, eax
0x1802c2bb2  lea     edx, [r8+11h]
0x1802c2bb6  or      ebx, 8
0x1802c2bb9  call    cs:__imp_RtlFindAceByType
0x1802c2bc0  nop     dword ptr [rax+rax+00h]
0x1802c2bc5  test    rax, rax
0x1802c2bc8  jz      short loc_1802C2BCD
0x1802c2bca  or      ebx, 10h
0x1802c2bcd  mov     r9, [rbp+57h+Sacl]
0x1802c2bd1  mov     r8d, ebx
0x1802c2bd4  mov     rax, [r14]
0x1802c2bd7  mov     rcx, r14
0x1802c2bda  mov     edx, [rdi]
0x1802c2bdc  mov     [rsp+100h+var_D0], r9
0x1802c2be1  and     edx, r12d
0x1802c2be4  mov     r9, [rbp+57h+Dacl]
0x1802c2be8  mov     rax, [rax+28h]
0x1802c2bec  mov     [rsp+100h+var_D8], r9
0x1802c2bf1  mov     r9, [rbp+57h+Group]
0x1802c2bf5  mov     [rsp+100h+var_E0], r9
0x1802c2bfa  mov     r9, [rbp+57h+Owner]
0x1802c2bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c2c03  test    eax, eax
0x1802c2c05  js      short loc_1802C2C11
0x1802c2c07  mov     rcx, rsi; this
0x1802c2c0a  call    ?ClearKeyContext@OperationContext@@QEAAXXZ; OperationContext::ClearKeyContext(void)
0x1802c2c0f  xor     eax, eax
0x1802c2c11  mov     rcx, [rbp+57h+var_38]
0x1802c2c15  xor     rcx, rsp; StackCookie
0x1802c2c18  call    __security_check_cookie
0x1802c2c1d  add     rsp, 0D0h
0x1802c2c24  pop     r15
0x1802c2c26  pop     r14
0x1802c2c28  pop     r12
0x1802c2c2a  pop     rdi
0x1802c2c2b  pop     rsi
0x1802c2c2c  pop     rbx
0x1802c2c2d  pop     rbp
0x1802c2c2e  retn
```
