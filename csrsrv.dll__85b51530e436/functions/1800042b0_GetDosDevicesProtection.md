# GetDosDevicesProtection

- ea: `0x1800042b0`
- end: `0x1800049a3`
- name: `GetDosDevicesProtection`
- size: `1779`
- prototype: `NTSTATUS __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003f20`

## callees

- `0x1800035c0`
- `0x1800042b0`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800045ea`
- `ntdll!RtlAllocateHeap` at `0x180004813`
- `ntdll!RtlAllocateHeap` at `0x1800045ea`
- `ntdll!RtlAllocateHeap` at `0x180004813`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180004772`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800048f2`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180004772`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800048f2`
- `ntdll!NtOpenKey` at `0x18000450f`
- `ntdll!NtOpenKey` at `0x18000450f`
- `ntdll!RtlGetAce` at `0x18000469f`
- `ntdll!RtlGetAce` at `0x1800046f4`
- `ntdll!RtlGetAce` at `0x180004748`
- `ntdll!RtlGetAce` at `0x1800048cc`
- `ntdll!RtlGetAce` at `0x18000469f`
- `ntdll!RtlGetAce` at `0x1800046f4`
- `ntdll!RtlGetAce` at `0x180004748`
- `ntdll!RtlGetAce` at `0x1800048cc`
- `ntdll!RtlInitUnicodeString` at `0x1800044d4`
- `ntdll!RtlInitUnicodeString` at `0x180004530`
- `ntdll!RtlInitUnicodeString` at `0x1800044d4`
- `ntdll!RtlInitUnicodeString` at `0x180004530`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180004373`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800043bd`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180004419`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000447f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180004373`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800043bd`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180004419`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000447f`
- `ntdll!RtlLengthSid` at `0x18000459b`
- `ntdll!RtlLengthSid` at `0x1800045ad`
- `ntdll!RtlLengthSid` at `0x1800045c0`
- `ntdll!RtlLengthSid` at `0x1800047d5`
- `ntdll!RtlLengthSid` at `0x1800047e9`
- `ntdll!RtlLengthSid` at `0x18000459b`
- `ntdll!RtlLengthSid` at `0x1800045ad`
- `ntdll!RtlLengthSid` at `0x1800045c0`
- `ntdll!RtlLengthSid` at `0x1800047d5`
- `ntdll!RtlLengthSid` at `0x1800047e9`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000467f`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800046d1`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004725`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000485f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004888`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800048ad`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000467f`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800046d1`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004725`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000485f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180004888`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800048ad`
- `ntdll!NtClose` at `0x180004581`
- `ntdll!NtClose` at `0x180004581`
- `ntdll!RtlFreeSid` at `0x1800043d4`
- `ntdll!RtlFreeSid` at `0x180004430`
- `ntdll!RtlFreeSid` at `0x180004441`
- `ntdll!RtlFreeSid` at `0x180004496`
- `ntdll!RtlFreeSid` at `0x1800044a7`
- `ntdll!RtlFreeSid` at `0x1800044b8`
- `ntdll!RtlFreeSid` at `0x180004608`
- `ntdll!RtlFreeSid` at `0x180004619`
- `ntdll!RtlFreeSid` at `0x18000462a`
- `ntdll!RtlFreeSid` at `0x18000463a`
- `ntdll!RtlFreeSid` at `0x18000478d`
- `ntdll!RtlFreeSid` at `0x18000479e`
- `ntdll!RtlFreeSid` at `0x1800047af`
- `ntdll!RtlFreeSid` at `0x1800047bf`
- `ntdll!RtlFreeSid` at `0x180004921`
- `ntdll!RtlFreeSid` at `0x180004932`
- `ntdll!RtlFreeSid` at `0x180004943`
- `ntdll!RtlFreeSid` at `0x180004953`
- `ntdll!RtlFreeSid` at `0x1800043d4`
- `ntdll!RtlFreeSid` at `0x180004430`
- `ntdll!RtlFreeSid` at `0x180004441`
- `ntdll!RtlFreeSid` at `0x180004496`
- `ntdll!RtlFreeSid` at `0x1800044a7`
- `ntdll!RtlFreeSid` at `0x1800044b8`
- `ntdll!RtlFreeSid` at `0x180004608`
- `ntdll!RtlFreeSid` at `0x180004619`
- `ntdll!RtlFreeSid` at `0x18000462a`
- `ntdll!RtlFreeSid` at `0x18000463a`
- `ntdll!RtlFreeSid` at `0x18000478d`
- `ntdll!RtlFreeSid` at `0x18000479e`
- `ntdll!RtlFreeSid` at `0x1800047af`
- `ntdll!RtlFreeSid` at `0x1800047bf`
- `ntdll!RtlFreeSid` at `0x180004921`
- `ntdll!RtlFreeSid` at `0x180004932`
- `ntdll!RtlFreeSid` at `0x180004943`
- `ntdll!RtlFreeSid` at `0x180004953`
- `ntdll!RtlFreeHeap` at `0x180004910`
- `ntdll!RtlFreeHeap` at `0x180004910`
- `ntdll!RtlCreateAcl` at `0x180004656`
- `ntdll!RtlCreateAcl` at `0x180004836`
- `ntdll!RtlCreateAcl` at `0x180004656`
- `ntdll!RtlCreateAcl` at `0x180004836`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000432e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000432e`
- `ntdll!NtQueryValueKey` at `0x18000455f`
- `ntdll!NtQueryValueKey` at `0x18000455f`

## string_xrefs

- `0x1800044c9`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager`

## pseudocode

```c
NTSTATUS __fastcall GetDosDevicesProtection(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS result; // eax
  NTSTATUS Acl; // ebx
  char v4; // bl
  ULONG v5; // ebx
  ULONG v6; // ebx
  ULONG v7; // ebx
  struct _ACL *Heap; // rax
  struct _ACL *v9; // rsi
  ULONG v10; // ebx
  ULONG v11; // ebx
  struct _ACL *v12; // rax
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v14; // [rsp+68h] [rbp-98h] BYREF
  PVOID Ace; // [rsp+70h] [rbp-90h] BYREF
  PSID v16; // [rsp+78h] [rbp-88h] BYREF
  PSID v17; // [rsp+80h] [rbp-80h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp-78h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+D8h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+E0h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v24; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v26; // [rsp+F4h] [rbp-Ch]
  int v27; // [rsp+FCh] [rbp-4h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Ace = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 256;
  *(_DWORD *)v24.Value = 0;
  *(_WORD *)&v24.Value[4] = 768;
  Sid = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  DestinationString = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  result = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( result >= 0 )
  {
    result = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( result >= 0 )
    {
      Acl = RtlAllocateAndInitializeSid(&v23, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v14);
      if ( Acl < 0 )
      {
        RtlFreeSid(Sid);
        return Acl;
      }
      Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v16);
      if ( Acl < 0 )
      {
        RtlFreeSid(Sid);
        RtlFreeSid(v14);
        return Acl;
      }
      Acl = RtlAllocateAndInitializeSid(&v24, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v17);
      if ( Acl < 0 )
      {
        RtlFreeSid(Sid);
        RtlFreeSid(v14);
        RtlFreeSid(v16);
        return Acl;
      }
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
        goto LABEL_26;
      v4 = 0;
      RtlInitUnicodeString(&DestinationString, L"ProtectionMode");
      if ( NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x40u,
             &ResultLength) >= 0
        && v26 == 4
        && v27 )
      {
        v4 = v27;
      }
      NtClose(KeyHandle);
      if ( (v4 & 3) != 0 )
      {
        v5 = RtlLengthSid(v16);
        v6 = RtlLengthSid(v17) + v5;
        v7 = RtlLengthSid(Sid) + 44 + v6;
        Heap = (struct _ACL *)RtlAllocateHeap(CsrHeap, (CsrBaseTag + 1310720) | 8, v7);
        v9 = Heap;
        if ( !Heap )
        {
LABEL_16:
          Acl = -1073741801;
          RtlFreeSid(Sid);
          RtlFreeSid(v14);
          RtlFreeSid(v16);
          RtlFreeSid(v17);
          goto LABEL_35;
        }
        Acl = RtlCreateAcl(Heap, v7, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v9, 2u, 0x10000000u, Sid);
          if ( Acl >= 0 )
          {
            Acl = RtlGetAce(v9, 0, &Ace);
            if ( Acl >= 0 )
            {
              *((_BYTE *)Ace + 1) |= 3u;
              Acl = RtlAddAccessAllowedAce(v9, 2u, 0x10000000u, v16);
              if ( Acl >= 0 )
              {
                Acl = RtlGetAce(v9, 1u, &Ace);
                if ( Acl >= 0 )
                {
                  *((_BYTE *)Ace + 1) |= 3u;
                  Acl = RtlAddAccessAllowedAce(v9, 2u, 0x10000000u, v17);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlGetAce(v9, 2u, &Ace);
                    if ( Acl >= 0 )
                    {
                      *((_BYTE *)Ace + 1) |= 0xBu;
                      Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v9, 0);
                      if ( Acl >= 0 )
                      {
                        RtlFreeSid(Sid);
                        RtlFreeSid(v14);
                        RtlFreeSid(v16);
                        RtlFreeSid(v17);
                        return Acl;
                      }
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
LABEL_26:
        v10 = 2 * RtlLengthSid(v14);
        v11 = RtlLengthSid(Sid) + 44 + v10;
        v12 = (struct _ACL *)RtlAllocateHeap(CsrHeap, (CsrBaseTag + 1310720) | 8, v11);
        v9 = v12;
        if ( !v12 )
          goto LABEL_16;
        Acl = RtlCreateAcl(v12, v11, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v9, 2u, 0xE0000000, v14);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v9, 2u, 0x10000000u, Sid);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAce(v9, 2u, 0x10000000u, v14);
              if ( Acl >= 0 )
              {
                Acl = RtlGetAce(v9, 2u, &Ace);
                if ( Acl >= 0 )
                {
                  *((_BYTE *)Ace + 1) |= 0xBu;
                  Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v9, 0);
                  if ( Acl >= 0 )
                  {
LABEL_34:
                    RtlFreeSid(Sid);
                    RtlFreeSid(v14);
                    RtlFreeSid(v16);
                    RtlFreeSid(v17);
                    if ( Acl >= 0 )
                      return Acl;
LABEL_35:
                    CsrpLogFailure("GetDosDevicesProtection");
                    return Acl;
                  }
                }
              }
            }
          }
        }
      }
      RtlFreeHeap(CsrHeap, 0, v9);
      goto LABEL_34;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800042b0  mov     [rsp-8+arg_10], rsi
0x1800042b5  mov     [rsp-8+arg_18], rdi
0x1800042ba  push    rbp
0x1800042bb  lea     rbp, [rsp-40h]
0x1800042c0  sub     rsp, 140h
0x1800042c7  mov     rax, cs:__security_cookie
0x1800042ce  xor     rax, rsp
0x1800042d1  mov     [rbp+40h+var_10], rax
0x1800042d5  xor     esi, esi
0x1800042d7  mov     word ptr [rbp+40h+IdentifierAuthority.Value+4], 500h
0x1800042dd  xorps   xmm0, xmm0
0x1800042e0  mov     [rsp+140h+Ace], rsi
0x1800042e5  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1800042e9  xor     eax, eax
0x1800042eb  mov     dword ptr [rbp+40h+IdentifierAuthority.Value], esi
0x1800042ee  mov     edx, 1; Revision
0x1800042f3  mov     dword ptr [rbp+40h+var_60.Value], esi
0x1800042f6  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1800042fa  mov     rdi, rcx
0x1800042fd  mov     word ptr [rbp+40h+var_60.Value+4], 100h
0x180004303  mov     dword ptr [rbp+40h+var_58.Value], esi
0x180004306  mov     word ptr [rbp+40h+var_58.Value+4], 300h
0x18000430c  mov     [rsp+140h+var_E0], rsi
0x180004311  mov     [rsp+140h+var_D8], rsi
0x180004316  mov     [rbp+40h+var_C0], rsi
0x18000431a  mov     [rsp+140h+var_C8], rsi
0x18000431f  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x180004323  mov     [rbp+40h+ResultLength], esi
0x180004326  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18000432a  mov     [rbp+40h+KeyHandle], rsi
0x18000432e  call    cs:__imp_RtlCreateSecurityDescriptor
0x180004335  nop     dword ptr [rax+rax+00h]
0x18000433a  test    eax, eax
0x18000433c  js      loc_180004981
0x180004342  lea     rax, [rsp+140h+var_E0]
0x180004347  xor     r9d, r9d; SubAuthority1
0x18000434a  mov     [rsp+140h+Sid], rax; Sid
0x18000434f  lea     rcx, [rbp+40h+IdentifierAuthority]; IdentifierAuthority
0x180004353  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x180004357  mov     r8d, 12h; SubAuthority0
0x18000435d  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x180004361  mov     dl, 1; SubAuthorityCount
0x180004363  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x180004367  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x18000436b  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18000436f  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x180004373  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000437a  nop     dword ptr [rax+rax+00h]
0x18000437f  test    eax, eax
0x180004381  js      loc_180004981
0x180004387  lea     rax, [rsp+140h+var_D8]
0x18000438c  mov     [rsp+140h+arg_8], rbx
0x180004394  mov     [rsp+140h+Sid], rax; Sid
0x180004399  lea     rcx, [rbp+40h+var_60]; IdentifierAuthority
0x18000439d  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x1800043a1  xor     r9d, r9d; SubAuthority1
0x1800043a4  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x1800043a8  xor     r8d, r8d; SubAuthority0
0x1800043ab  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x1800043af  mov     dl, 1; SubAuthorityCount
0x1800043b1  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x1800043b5  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x1800043b9  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x1800043bd  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800043c4  nop     dword ptr [rax+rax+00h]
0x1800043c9  mov     ebx, eax
0x1800043cb  test    eax, eax
0x1800043cd  jns     short loc_1800043E5
0x1800043cf  mov     rcx, [rsp+140h+var_E0]; Sid
0x1800043d4  call    cs:__imp_RtlFreeSid
0x1800043db  nop     dword ptr [rax+rax+00h]
0x1800043e0  jmp     loc_180004977
0x1800043e5  lea     rax, [rsp+140h+var_C8]
0x1800043ea  mov     r9d, 220h; SubAuthority1
0x1800043f0  mov     [rsp+140h+Sid], rax; Sid
0x1800043f5  lea     rcx, [rbp+40h+IdentifierAuthority]; IdentifierAuthority
0x1800043f9  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x1800043fd  mov     r8d, 20h ; ' '; SubAuthority0
0x180004403  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x180004407  mov     dl, 2; SubAuthorityCount
0x180004409  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x18000440d  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x180004411  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x180004415  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x180004419  call    cs:__imp_RtlAllocateAndInitializeSid
0x180004420  nop     dword ptr [rax+rax+00h]
0x180004425  mov     ebx, eax
0x180004427  test    eax, eax
0x180004429  jns     short loc_180004452
0x18000442b  mov     rcx, [rsp+140h+var_E0]; Sid
0x180004430  call    cs:__imp_RtlFreeSid
0x180004437  nop     dword ptr [rax+rax+00h]
0x18000443c  mov     rcx, [rsp+140h+var_D8]; Sid
0x180004441  call    cs:__imp_RtlFreeSid
0x180004448  nop     dword ptr [rax+rax+00h]
0x18000444d  jmp     loc_180004977
0x180004452  lea     rax, [rbp+40h+var_C0]
0x180004456  xor     r9d, r9d; SubAuthority1
0x180004459  mov     [rsp+140h+Sid], rax; Sid
0x18000445e  lea     rcx, [rbp+40h+var_58]; IdentifierAuthority
0x180004462  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x180004466  xor     r8d, r8d; SubAuthority0
0x180004469  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x18000446d  mov     dl, 1; SubAuthorityCount
0x18000446f  mov     [rsp+140h+SubAuthority5], esi; SubAuthority5
0x180004473  mov     [rsp+140h+SubAuthority4], esi; SubAuthority4
0x180004477  mov     [rsp+140h+SubAuthority3], esi; SubAuthority3
0x18000447b  mov     [rsp+140h+SubAuthority2], esi; SubAuthority2
0x18000447f  call    cs:__imp_RtlAllocateAndInitializeSid
0x180004486  nop     dword ptr [rax+rax+00h]
0x18000448b  mov     ebx, eax
0x18000448d  test    eax, eax
0x18000448f  jns     short loc_1800044C9
0x180004491  mov     rcx, [rsp+140h+var_E0]; Sid
0x180004496  call    cs:__imp_RtlFreeSid
0x18000449d  nop     dword ptr [rax+rax+00h]
0x1800044a2  mov     rcx, [rsp+140h+var_D8]; Sid
0x1800044a7  call    cs:__imp_RtlFreeSid
0x1800044ae  nop     dword ptr [rax+rax+00h]
0x1800044b3  mov     rcx, [rsp+140h+var_C8]; Sid
0x1800044b8  call    cs:__imp_RtlFreeSid
0x1800044bf  nop     dword ptr [rax+rax+00h]
0x1800044c4  jmp     loc_180004977
0x1800044c9  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800044d0  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1800044d4  call    cs:__imp_RtlInitUnicodeString
0x1800044db  nop     dword ptr [rax+rax+00h]
0x1800044e0  lea     rax, [rbp+40h+DestinationString]
0x1800044e4  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1800044eb  xorps   xmm0, xmm0
0x1800044ee  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1800044f2  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1800044f6  mov     [rbp+40h+ObjectAttributes.RootDirectory], rsi
0x1800044fa  mov     edx, 20019h; DesiredAccess
0x1800044ff  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x180004506  lea     rcx, [rbp+40h+KeyHandle]; KeyHandle
0x18000450a  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000450f  call    cs:__imp_NtOpenKey
0x180004516  nop     dword ptr [rax+rax+00h]
0x18000451b  test    eax, eax
0x18000451d  js      loc_1800047D0
0x180004523  lea     rdx, aProtectionmode; "ProtectionMode"
0x18000452a  mov     ebx, esi
0x18000452c  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x180004530  call    cs:__imp_RtlInitUnicodeString
0x180004537  nop     dword ptr [rax+rax+00h]
0x18000453c  mov     rcx, [rbp+40h+KeyHandle]; KeyHandle
0x180004540  lea     rax, [rbp+40h+ResultLength]
0x180004544  mov     qword ptr [rsp+140h+SubAuthority3], rax; ResultLength
0x180004549  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x18000454d  mov     r8d, 2; KeyValueInformationClass
0x180004553  mov     [rsp+140h+SubAuthority2], 40h ; '@'; Length
0x18000455b  lea     rdx, [rbp+40h+DestinationString]; ValueName
0x18000455f  call    cs:__imp_NtQueryValueKey
0x180004566  nop     dword ptr [rax+rax+00h]
0x18000456b  test    eax, eax
0x18000456d  js      short loc_18000457D
0x18000456f  cmp     [rbp+40h+var_4C], 4
0x180004573  jnz     short loc_18000457D
0x180004575  mov     eax, [rbp+40h+var_44]
0x180004578  test    eax, eax
0x18000457a  cmovnz  ebx, eax
0x18000457d  mov     rcx, [rbp+40h+KeyHandle]; Handle
0x180004581  call    cs:__imp_NtClose
0x180004588  nop     dword ptr [rax+rax+00h]
0x18000458d  test    bl, 3
0x180004590  jz      loc_1800047D0
0x180004596  mov     rcx, [rsp+140h+var_C8]; Sid
0x18000459b  call    cs:__imp_RtlLengthSid
0x1800045a2  nop     dword ptr [rax+rax+00h]
0x1800045a7  mov     rcx, [rbp+40h+var_C0]; Sid
0x1800045ab  mov     ebx, eax
0x1800045ad  call    cs:__imp_RtlLengthSid
0x1800045b4  nop     dword ptr [rax+rax+00h]
0x1800045b9  mov     rcx, [rsp+140h+var_E0]; Sid
0x1800045be  add     ebx, eax
0x1800045c0  call    cs:__imp_RtlLengthSid
0x1800045c7  nop     dword ptr [rax+rax+00h]
0x1800045cc  mov     edx, cs:CsrBaseTag
0x1800045d2  add     eax, 2Ch ; ','
0x1800045d5  mov     rcx, cs:CsrHeap; HeapHandle
0x1800045dc  add     ebx, eax
0x1800045de  add     edx, 140000h
0x1800045e4  mov     r8d, ebx; Size
0x1800045e7  or      edx, 8; Flags
0x1800045ea  call    cs:__imp_RtlAllocateHeap
0x1800045f1  nop     dword ptr [rax+rax+00h]
0x1800045f6  mov     rsi, rax
0x1800045f9  test    rax, rax
0x1800045fc  jnz     short loc_18000464B
0x1800045fe  mov     rcx, [rsp+140h+var_E0]; Sid
0x180004603  mov     ebx, 0C0000017h
0x180004608  call    cs:__imp_RtlFreeSid
0x18000460f  nop     dword ptr [rax+rax+00h]
0x180004614  mov     rcx, [rsp+140h+var_D8]; Sid
0x180004619  call    cs:__imp_RtlFreeSid
0x180004620  nop     dword ptr [rax+rax+00h]
0x180004625  mov     rcx, [rsp+140h+var_C8]; Sid
0x18000462a  call    cs:__imp_RtlFreeSid
0x180004631  nop     dword ptr [rax+rax+00h]
0x180004636  mov     rcx, [rbp+40h+var_C0]; Sid
0x18000463a  call    cs:__imp_RtlFreeSid
0x180004641  nop     dword ptr [rax+rax+00h]
0x180004646  jmp     loc_180004963
0x18000464b  mov     r8d, 2; AclRevision
0x180004651  mov     edx, ebx; AclLength
0x180004653  mov     rcx, rsi; Acl
0x180004656  call    cs:__imp_RtlCreateAcl
0x18000465d  nop     dword ptr [rax+rax+00h]
0x180004662  mov     ebx, eax
0x180004664  test    eax, eax
0x180004666  js      loc_180004904
0x18000466c  mov     r9, [rsp+140h+var_E0]; Sid
0x180004671  mov     edx, 2; AceRevision
0x180004676  mov     r8d, 10000000h; AccessMask
0x18000467c  mov     rcx, rsi; Acl
0x18000467f  call    cs:__imp_RtlAddAccessAllowedAce
0x180004686  nop     dword ptr [rax+rax+00h]
0x18000468b  mov     ebx, eax
0x18000468d  test    eax, eax
0x18000468f  js      loc_180004904
0x180004695  lea     r8, [rsp+140h+Ace]; Ace
0x18000469a  xor     edx, edx; AceIndex
0x18000469c  mov     rcx, rsi; Acl
0x18000469f  call    cs:__imp_RtlGetAce
0x1800046a6  nop     dword ptr [rax+rax+00h]
0x1800046ab  mov     ebx, eax
0x1800046ad  test    eax, eax
0x1800046af  js      loc_180004904
0x1800046b5  mov     rax, [rsp+140h+Ace]
0x1800046ba  mov     edx, 2; AceRevision
0x1800046bf  mov     r8d, 10000000h; AccessMask
0x1800046c5  mov     rcx, rsi; Acl
0x1800046c8  or      byte ptr [rax+1], 3
0x1800046cc  mov     r9, [rsp+140h+var_C8]; Sid
0x1800046d1  call    cs:__imp_RtlAddAccessAllowedAce
0x1800046d8  nop     dword ptr [rax+rax+00h]
0x1800046dd  mov     ebx, eax
0x1800046df  test    eax, eax
0x1800046e1  js      loc_180004904
0x1800046e7  lea     r8, [rsp+140h+Ace]; Ace
0x1800046ec  mov     edx, 1; AceIndex
0x1800046f1  mov     rcx, rsi; Acl
0x1800046f4  call    cs:__imp_RtlGetAce
0x1800046fb  nop     dword ptr [rax+rax+00h]
0x180004700  mov     ebx, eax
0x180004702  test    eax, eax
0x180004704  js      loc_180004904
0x18000470a  mov     rax, [rsp+140h+Ace]
0x18000470f  mov     edx, 2; AceRevision
0x180004714  mov     r8d, 10000000h; AccessMask
0x18000471a  mov     rcx, rsi; Acl
0x18000471d  or      byte ptr [rax+1], 3
0x180004721  mov     r9, [rbp+40h+var_C0]; Sid
0x180004725  call    cs:__imp_RtlAddAccessAllowedAce
0x18000472c  nop     dword ptr [rax+rax+00h]
0x180004731  mov     ebx, eax
0x180004733  test    eax, eax
0x180004735  js      loc_180004904
0x18000473b  lea     r8, [rsp+140h+Ace]; Ace
0x180004740  mov     edx, 2; AceIndex
0x180004745  mov     rcx, rsi; Acl
0x180004748  call    cs:__imp_RtlGetAce
0x18000474f  nop     dword ptr [rax+rax+00h]
0x180004754  mov     ebx, eax
0x180004756  test    eax, eax
0x180004758  js      loc_180004904
0x18000475e  mov     rax, [rsp+140h+Ace]
0x180004763  xor     r9d, r9d; DaclDefaulted
0x180004766  mov     r8, rsi; Dacl
0x180004769  mov     dl, 1; DaclPresent
0x18000476b  mov     rcx, rdi; SecurityDescriptor
0x18000476e  or      byte ptr [rax+1], 0Bh
0x180004772  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180004779  nop     dword ptr [rax+rax+00h]
0x18000477e  mov     ebx, eax
0x180004780  test    eax, eax
0x180004782  js      loc_180004904
0x180004788  mov     rcx, [rsp+140h+var_E0]; Sid
0x18000478d  call    cs:__imp_RtlFreeSid
0x180004794  nop     dword ptr [rax+rax+00h]
0x180004799  mov     rcx, [rsp+140h+var_D8]; Sid
0x18000479e  call    cs:__imp_RtlFreeSid
0x1800047a5  nop     dword ptr [rax+rax+00h]
0x1800047aa  mov     rcx, [rsp+140h+var_C8]; Sid
0x1800047af  call    cs:__imp_RtlFreeSid
0x1800047b6  nop     dword ptr [rax+rax+00h]
0x1800047bb  mov     rcx, [rbp+40h+var_C0]; Sid
0x1800047bf  call    cs:__imp_RtlFreeSid
0x1800047c6  nop     dword ptr [rax+rax+00h]
0x1800047cb  jmp     loc_180004977
0x1800047d0  mov     rcx, [rsp+140h+var_D8]; Sid
0x1800047d5  call    cs:__imp_RtlLengthSid
0x1800047dc  nop     dword ptr [rax+rax+00h]
0x1800047e1  mov     rcx, [rsp+140h+var_E0]; Sid
0x1800047e6  lea     ebx, [rax+rax]
0x1800047e9  call    cs:__imp_RtlLengthSid
0x1800047f0  nop     dword ptr [rax+rax+00h]
0x1800047f5  mov     edx, cs:CsrBaseTag
0x1800047fb  add     eax, 2Ch ; ','
  ... truncated ...
```
