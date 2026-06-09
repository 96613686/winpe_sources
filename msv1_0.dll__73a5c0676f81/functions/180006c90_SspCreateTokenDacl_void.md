# SspCreateTokenDacl(void *)

- ea: `0x180006c90`
- end: `0x1800076f8`
- name: `?SspCreateTokenDacl@@YAJPEAX@Z`
- size: `2664`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005d30`
- `0x18004b8e4`

## callees

- `0x180006c50`
- `0x180006c90`
- `0x180007700`
- `0x180021f2c`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18006bd74`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006e72`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006e72`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007669`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007669`
- `ntdll!RtlLengthSid` at `0x180007066`
- `ntdll!RtlLengthSid` at `0x180007171`
- `ntdll!RtlLengthSid` at `0x18000727b`
- `ntdll!RtlLengthSid` at `0x18000728a`
- `ntdll!RtlLengthSid` at `0x180007299`
- `ntdll!RtlLengthSid` at `0x1800072a5`
- `ntdll!RtlLengthSid` at `0x1800072e9`
- `ntdll!RtlLengthSid` at `0x180007308`
- `ntdll!RtlLengthSid` at `0x180007066`
- `ntdll!RtlLengthSid` at `0x180007171`
- `ntdll!RtlLengthSid` at `0x18000727b`
- `ntdll!RtlLengthSid` at `0x18000728a`
- `ntdll!RtlLengthSid` at `0x180007299`
- `ntdll!RtlLengthSid` at `0x1800072a5`
- `ntdll!RtlLengthSid` at `0x1800072e9`
- `ntdll!RtlLengthSid` at `0x180007308`
- `ntdll!RtlEqualSid` at `0x1800072c4`
- `ntdll!RtlEqualSid` at `0x1800072db`
- `ntdll!RtlEqualSid` at `0x1800072c4`
- `ntdll!RtlEqualSid` at `0x1800072db`
- `ntdll!NtOpenProcessToken` at `0x180006f7f`
- `ntdll!NtOpenProcessToken` at `0x1800070d7`
- `ntdll!NtOpenProcessToken` at `0x180006f7f`
- `ntdll!NtOpenProcessToken` at `0x1800070d7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800075d9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800075d9`
- `ntdll!NtQueryInformationToken` at `0x180006e9d`
- `ntdll!NtQueryInformationToken` at `0x180006ee7`
- `ntdll!NtQueryInformationToken` at `0x180006fdc`
- `ntdll!NtQueryInformationToken` at `0x180007025`
- `ntdll!NtQueryInformationToken` at `0x1800071e1`
- `ntdll!NtQueryInformationToken` at `0x18000722c`
- `ntdll!NtQueryInformationToken` at `0x180006e9d`
- `ntdll!NtQueryInformationToken` at `0x180006ee7`
- `ntdll!NtQueryInformationToken` at `0x180006fdc`
- `ntdll!NtQueryInformationToken` at `0x180007025`
- `ntdll!NtQueryInformationToken` at `0x1800071e1`
- `ntdll!NtQueryInformationToken` at `0x18000722c`
- `ntdll!NtSetSecurityObject` at `0x180007611`
- `ntdll!NtSetSecurityObject` at `0x180007611`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800073d0`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000741c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007470`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800074bc`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007508`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007559`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800073d0`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000741c`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007470`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800074bc`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007508`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007559`
- `ntdll!RtlCreateAcl` at `0x180007384`
- `ntdll!RtlCreateAcl` at `0x180007384`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007599`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007599`
- `ntdll!NtOpenThreadToken` at `0x180006e62`
- `ntdll!NtOpenThreadToken` at `0x180006e62`
- `ntdll!RtlFreeSid` at `0x180006da9`
- `ntdll!RtlFreeSid` at `0x180006e49`
- `ntdll!RtlFreeSid` at `0x180006da9`
- `ntdll!RtlFreeSid` at `0x180006e49`
- `ntdll!NtClose` at `0x180007673`
- `ntdll!NtClose` at `0x1800076d7`
- `ntdll!NtClose` at `0x180007673`
- `ntdll!NtClose` at `0x1800076d7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180006d5b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180006dfb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180006d5b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180006dfb`

## pseudocode

```c
__int64 __fastcall SspCreateTokenDacl(HANDLE Handle)
{
  void *v2; // rdi
  __int64 v3; // rsi
  PSID *v4; // r14
  PSID *v5; // r15
  NTSTATUS InformationToken; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  PSID *v9; // r13
  void *v10; // rax
  signed __int64 v11; // rbx
  HANDLE v12; // rcx
  SIZE_T v13; // r13
  void *v14; // rax
  signed __int64 v15; // rbx
  PSID *v16; // r13
  ULONG v17; // ebx
  ULONG v18; // ebx
  ULONG v19; // ebx
  ULONG v20; // ebx
  PSID v21; // rdx
  PSID *v22; // r13
  ULONG v23; // eax
  struct _ACL *p_Acl; // r13
  __int64 v25; // rax
  ULONG ReturnLength[2]; // [rsp+68h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+70h] [rbp-98h] BYREF
  HANDLE Handlea; // [rsp+78h] [rbp-90h] BYREF
  int v30; // [rsp+80h] [rbp-88h]
  void *TokenHandle; // [rsp+88h] [rbp-80h] BYREF
  size_t Size; // [rsp+90h] [rbp-78h]
  unsigned int v33; // [rsp+98h] [rbp-70h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-48h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE TokenInformation[128]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v38[128]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v39[128]; // [rsp+1D8h] [rbp+D0h] BYREF
  _ACL Acl; // [rsp+258h] [rbp+150h] BYREF
  PSID Src[10]; // [rsp+458h] [rbp+350h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  ReturnLength[0] = 0;
  Handlea = 0;
  TokenHandle = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v35 = 0;
  LOBYTE(ReturnLength[1]) = 0;
  v33 = 76;
  if ( !NtLmGlobalLocalSystemSid )
  {
    Sid = 0;
    InformationToken = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( InformationToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 116;
LABEL_127:
        WPP_SF_d(v7[2], v8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, (unsigned int)InformationToken);
        goto LABEL_128;
      }
      goto LABEL_128;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&NtLmGlobalLocalSystemSid, (signed __int64)Sid, 0) )
      RtlFreeSid(Sid);
  }
  if ( !NtLmGlobalAliasAdminsSid )
  {
    Sid = 0;
    InformationToken = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
    if ( InformationToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 117;
        goto LABEL_127;
      }
      goto LABEL_128;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&NtLmGlobalAliasAdminsSid, (signed __int64)Sid, 0) )
      RtlFreeSid(Sid);
  }
  InformationToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( InformationToken < 0 )
  {
    Sid = 0;
    if ( InformationToken != -1073741700 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 119;
        goto LABEL_127;
      }
      goto LABEL_128;
    }
  }
  else
  {
    RevertToSelf();
    ReturnLength[0] = 128;
    InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x80u, ReturnLength);
    if ( InformationToken == -1073741789 )
    {
      v2 = (void *)NtLmAllocate(ReturnLength[0]);
      if ( !v2 )
      {
        InformationToken = -1073741670;
        goto LABEL_128;
      }
      Sid = v2;
      InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, v2, ReturnLength[0], ReturnLength);
    }
    else
    {
      Sid = TokenInformation;
    }
    if ( InformationToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 118;
        goto LABEL_127;
      }
      goto LABEL_128;
    }
  }
  if ( !NtLmGlobalProcessUserSid )
  {
    InformationToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &Handlea);
    if ( InformationToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 120;
        goto LABEL_127;
      }
      goto LABEL_128;
    }
    ReturnLength[0] = 128;
    InformationToken = NtQueryInformationToken(Handlea, TokenUser, v38, 0x80u, ReturnLength);
    if ( InformationToken == -1073741789 )
    {
      v4 = (PSID *)NtLmAllocate(ReturnLength[0]);
      if ( !v4 )
      {
        InformationToken = -1073741670;
        goto LABEL_128;
      }
      v9 = v4;
      InformationToken = NtQueryInformationToken(Handlea, TokenUser, v4, ReturnLength[0], ReturnLength);
    }
    else
    {
      v9 = (PSID *)v38;
    }
    if ( InformationToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 121;
        goto LABEL_127;
      }
      goto LABEL_128;
    }
    Size = RtlLengthSid(*v9);
    v10 = (void *)NtLmAllocate(Size);
    v11 = (signed __int64)v10;
    if ( !v10 )
    {
      InformationToken = -1073741670;
      goto LABEL_128;
    }
    memcpy_0(v10, *v9, Size);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&NtLmGlobalProcessUserSid, v11, 0) )
      NtLmFree(v11);
  }
  if ( !NtLmProcessAppContainerCached )
  {
    v12 = Handlea;
    if ( !Handlea )
    {
      InformationToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &Handlea);
      if ( InformationToken < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 122;
          goto LABEL_127;
        }
        goto LABEL_128;
      }
      v12 = Handlea;
    }
    InformationToken = SspGetTokenPackage(
                         v12,
                         (unsigned __int8 *)&ReturnLength[1],
                         (struct _TOKEN_APPCONTAINER_INFORMATION *)Src,
                         &v33);
    if ( InformationToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 123;
        goto LABEL_127;
      }
      goto LABEL_128;
    }
    NtLmProcessAppContainerCached = 1;
    if ( LOBYTE(ReturnLength[1]) )
    {
      v13 = RtlLengthSid(Src[0]);
      v14 = (void *)NtLmAllocate(v13);
      v15 = (signed __int64)v14;
      if ( !v14 )
      {
        InformationToken = -1073741670;
        goto LABEL_128;
      }
      memcpy_0(v14, Src[0], v13);
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&NtLmProcessAppContainerSid, v15, 0) )
        NtLmFree(v15);
    }
  }
  ReturnLength[0] = 128;
  InformationToken = NtQueryInformationToken(Handle, TokenUser, v39, 0x80u, ReturnLength);
  if ( InformationToken == -1073741789 )
  {
    v5 = (PSID *)NtLmAllocate(ReturnLength[0]);
    if ( !v5 )
    {
      InformationToken = -1073741670;
      goto LABEL_128;
    }
    Size = (size_t)v5;
    v16 = v5;
    InformationToken = NtQueryInformationToken(Handle, TokenUser, v5, ReturnLength[0], ReturnLength);
  }
  else
  {
    v16 = (PSID *)v39;
    Size = (size_t)v39;
  }
  if ( InformationToken >= 0 )
  {
    v30 = 0;
    v17 = RtlLengthSid(NtLmGlobalProcessUserSid);
    v18 = RtlLengthSid(NtLmGlobalAliasAdminsSid) + v17;
    v19 = RtlLengthSid(NtLmGlobalLocalSystemSid) + v18;
    v20 = RtlLengthSid(*v16) + v19 + 40;
    if ( Sid )
    {
      if ( !RtlEqualSid(*(PSID *)Sid, NtLmGlobalProcessUserSid) )
      {
        v21 = *v16;
        v22 = (PSID *)Sid;
        if ( !RtlEqualSid(*(PSID *)Sid, v21) )
        {
          v23 = RtlLengthSid(*v22);
          v30 = 1;
          v20 += v23 + 8;
        }
      }
    }
    if ( NtLmProcessAppContainerSid )
      v20 += RtlLengthSid(NtLmProcessAppContainerSid) + 8;
    if ( v20 > 0x200 )
    {
      v25 = NtLmAllocate(v20);
      v3 = v25;
      if ( !v25 )
      {
        InformationToken = -1073741670;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, 0);
        goto LABEL_128;
      }
      p_Acl = (struct _ACL *)v25;
    }
    else
    {
      p_Acl = &Acl;
    }
    InformationToken = RtlCreateAcl(p_Acl, v20, 2u);
    if ( InformationToken >= 0 )
    {
      InformationToken = RtlAddAccessAllowedAce(p_Acl, 2u, 0xF01FFu, NtLmGlobalProcessUserSid);
      if ( InformationToken >= 0 )
      {
        InformationToken = RtlAddAccessAllowedAce(p_Acl, 2u, 0xF01FFu, *(PSID *)Size);
        if ( InformationToken >= 0 )
        {
          if ( v30
            && (InformationToken = RtlAddAccessAllowedAce(p_Acl, 2u, 0xF01FFu, *(PSID *)Sid), InformationToken < 0) )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 129;
              goto LABEL_127;
            }
          }
          else
          {
            InformationToken = RtlAddAccessAllowedAce(p_Acl, 2u, 0xF01FFu, NtLmGlobalAliasAdminsSid);
            if ( InformationToken >= 0 )
            {
              InformationToken = RtlAddAccessAllowedAce(p_Acl, 2u, 0xF01FFu, NtLmGlobalLocalSystemSid);
              if ( InformationToken >= 0 )
              {
                if ( NtLmProcessAppContainerSid
                  && (InformationToken = RtlAddAccessAllowedAce(p_Acl, 2u, 0xF01FFu, NtLmProcessAppContainerSid),
                      InformationToken < 0) )
                {
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v8 = 132;
                    goto LABEL_127;
                  }
                }
                else
                {
                  InformationToken = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( InformationToken >= 0 )
                  {
                    InformationToken = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, p_Acl, 0);
                    if ( InformationToken >= 0 )
                    {
                      InformationToken = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
                      if ( InformationToken < 0 )
                      {
                        v7 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          v8 = 135;
                          goto LABEL_127;
                        }
                      }
                    }
                    else
                    {
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        v8 = 134;
                        goto LABEL_127;
                      }
                    }
                  }
                  else
                  {
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 133;
                      goto LABEL_127;
                    }
                  }
                }
              }
              else
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 131;
                  goto LABEL_127;
                }
              }
            }
            else
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 130;
                goto LABEL_127;
              }
            }
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 128;
            goto LABEL_127;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 127;
          goto LABEL_127;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 126;
        goto LABEL_127;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 124;
      goto LABEL_127;
    }
  }
LABEL_128:
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    NtClose(TokenHandle);
  }
  if ( v5 )
    NtLmFree(v5);
  if ( v4 )
    NtLmFree(v4);
  if ( v2 )
    NtLmFree(v2);
  if ( v3 )
    NtLmFree(v3);
  if ( Handlea )
    NtClose(Handlea);
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x180006c90  mov     r11, rsp
0x180006c93  push    rbp
0x180006c94  push    rbx
0x180006c95  lea     rbp, [r11-3D8h]
0x180006c9c  sub     rsp, 4C8h
0x180006ca3  mov     rax, cs:__security_cookie
0x180006caa  xor     rax, rsp
0x180006cad  mov     [rbp+3D0h+var_30], rax
0x180006cb4  mov     [r11+10h], rsi
0x180006cb8  xor     eax, eax
0x180006cba  mov     [r11+18h], rdi
0x180006cbe  xorps   xmm0, xmm0
0x180006cc1  mov     [r11+20h], r12
0x180006cc5  mov     r12, rcx
0x180006cc8  mov     [r11-18h], r13
0x180006ccc  xor     r13d, r13d
0x180006ccf  cmp     cs:NtLmGlobalLocalSystemSid, rax
0x180006cd6  mov     edi, r13d
0x180006cd9  mov     [r11-20h], r14
0x180006cdd  mov     esi, r13d
0x180006ce0  mov     [r11-28h], r15
0x180006ce4  mov     r14d, r13d
0x180006ce7  mov     r15d, r13d
0x180006cea  mov     [rsp+4D0h+ReturnLength], r13d
0x180006cef  mov     [rsp+4D0h+Handle], r13
0x180006cf4  mov     [rbp+3D0h+TokenHandle], r13
0x180006cf8  mov     dword ptr [rbp+3D0h+IdentifierAuthority.Value], r13d
0x180006cfc  mov     word ptr [rbp+3D0h+IdentifierAuthority.Value+4], 500h
0x180006d02  movups  [rbp+3D0h+SecurityDescriptor], xmm0
0x180006d06  mov     [rbp+3D0h+var_418], rax
0x180006d0a  movups  [rbp+3D0h+var_428], xmm0
0x180006d0e  mov     byte ptr [rsp+4D0h+ReturnLength+4], al
0x180006d12  mov     [rbp+3D0h+var_440], 4Ch ; 'L'
0x180006d19  jnz     loc_180006DAF
0x180006d1f  lea     rax, [rsp+4D0h+Sid]
0x180006d24  mov     [rsp+4D0h+Sid], r13
0x180006d29  mov     [rsp+50h], rax; Sid
0x180006d2e  lea     rcx, [rbp+3D0h+IdentifierAuthority]; IdentifierAuthority
0x180006d32  mov     [rsp+4D0h+SubAuthority7], r13d; SubAuthority7
0x180006d37  xor     r9d, r9d; SubAuthority1
0x180006d3a  mov     [rsp+4D0h+SubAuthority6], r13d; SubAuthority6
0x180006d3f  mov     r8d, 12h; SubAuthority0
0x180006d45  mov     [rsp+4D0h+SubAuthority5], r13d; SubAuthority5
0x180006d4a  mov     dl, 1; SubAuthorityCount
0x180006d4c  mov     [rsp+4D0h+SubAuthority4], r13d; SubAuthority4
0x180006d51  mov     [rsp+4D0h+SubAuthority3], r13d; SubAuthority3
0x180006d56  mov     [rsp+4D0h+SubAuthority2], r13d; SubAuthority2
0x180006d5b  call    cs:__imp_RtlAllocateAndInitializeSid
0x180006d61  mov     ebx, eax
0x180006d63  test    eax, eax
0x180006d65  jns     short loc_180006D92
0x180006d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d6e  lea     rax, WPP_GLOBAL_Control
0x180006d75  cmp     rcx, rax
0x180006d78  jz      loc_18000764E
0x180006d7e  test    byte ptr [rcx+1Ch], 1
0x180006d82  jz      loc_18000764E
0x180006d88  mov     edx, 74h ; 't'
0x180006d8d  jmp     loc_18000763B
0x180006d92  mov     rcx, [rsp+4D0h+Sid]
0x180006d97  xor     eax, eax
0x180006d99  lock cmpxchg cs:NtLmGlobalLocalSystemSid, rcx
0x180006da2  jz      short loc_180006DAF
0x180006da4  mov     rcx, [rsp+4D0h+Sid]; Sid
0x180006da9  call    cs:__imp_RtlFreeSid
0x180006daf  cmp     cs:NtLmGlobalAliasAdminsSid, rsi
0x180006db6  jnz     loc_180006E4F
0x180006dbc  lea     rax, [rsp+4D0h+Sid]
0x180006dc1  mov     [rsp+4D0h+Sid], r13
0x180006dc6  mov     [rsp+50h], rax; Sid
0x180006dcb  lea     rcx, [rbp+3D0h+IdentifierAuthority]; IdentifierAuthority
0x180006dcf  mov     [rsp+4D0h+SubAuthority7], r13d; SubAuthority7
0x180006dd4  mov     r9d, 220h; SubAuthority1
0x180006dda  mov     [rsp+4D0h+SubAuthority6], r13d; SubAuthority6
0x180006ddf  mov     r8d, 20h ; ' '; SubAuthority0
0x180006de5  mov     [rsp+4D0h+SubAuthority5], r13d; SubAuthority5
0x180006dea  mov     dl, 2; SubAuthorityCount
0x180006dec  mov     [rsp+4D0h+SubAuthority4], r13d; SubAuthority4
0x180006df1  mov     [rsp+4D0h+SubAuthority3], r13d; SubAuthority3
0x180006df6  mov     [rsp+4D0h+SubAuthority2], r13d; SubAuthority2
0x180006dfb  call    cs:__imp_RtlAllocateAndInitializeSid
0x180006e01  mov     ebx, eax
0x180006e03  test    eax, eax
0x180006e05  jns     short loc_180006E32
0x180006e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e0e  lea     rax, WPP_GLOBAL_Control
0x180006e15  cmp     rcx, rax
0x180006e18  jz      loc_18000764E
0x180006e1e  test    byte ptr [rcx+1Ch], 1
0x180006e22  jz      loc_18000764E
0x180006e28  mov     edx, 75h ; 'u'
0x180006e2d  jmp     loc_18000763B
0x180006e32  mov     rcx, [rsp+4D0h+Sid]
0x180006e37  xor     eax, eax
0x180006e39  lock cmpxchg cs:NtLmGlobalAliasAdminsSid, rcx
0x180006e42  jz      short loc_180006E4F
0x180006e44  mov     rcx, [rsp+4D0h+Sid]; Sid
0x180006e49  call    cs:__imp_RtlFreeSid
0x180006e4f  lea     r9, [rbp+3D0h+TokenHandle]; TokenHandle
0x180006e53  mov     r8b, 1; OpenAsSelf
0x180006e56  mov     edx, 0Ch; DesiredAccess
0x180006e5b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006e62  call    cs:__imp_NtOpenThreadToken
0x180006e68  mov     ebx, eax
0x180006e6a  test    eax, eax
0x180006e6c  js      loc_180006F29
0x180006e72  call    cs:__imp_RevertToSelf
0x180006e78  mov     rcx, [rbp+3D0h+TokenHandle]; TokenHandle
0x180006e7c  lea     rax, [rsp+4D0h+ReturnLength]
0x180006e81  mov     r9d, 80h; TokenInformationLength
0x180006e87  mov     qword ptr [rsp+4D0h+SubAuthority2], rax; ReturnLength
0x180006e8c  lea     r8, [rbp+3D0h+TokenInformation]; TokenInformation
0x180006e90  mov     [rsp+4D0h+ReturnLength], 80h
0x180006e98  mov     edx, 1; TokenInformationClass
0x180006e9d  call    cs:__imp_NtQueryInformationToken
0x180006ea3  mov     ebx, eax
0x180006ea5  cmp     eax, 0C0000023h
0x180006eaa  jnz     short loc_180006EF1
0x180006eac  mov     ecx, [rsp+4D0h+ReturnLength]; uBytes
0x180006eb0  call    NtLmAllocate
0x180006eb5  mov     rdi, rax
0x180006eb8  test    rax, rax
0x180006ebb  jnz     short loc_180006EC7
0x180006ebd  mov     ebx, 0C000009Ah
0x180006ec2  jmp     loc_18000764E
0x180006ec7  mov     r9d, [rsp+4D0h+ReturnLength]; TokenInformationLength
0x180006ecc  lea     rax, [rsp+4D0h+ReturnLength]
0x180006ed1  mov     rcx, [rbp+3D0h+TokenHandle]; TokenHandle
0x180006ed5  mov     r8, rdi; TokenInformation
0x180006ed8  mov     edx, 1; TokenInformationClass
0x180006edd  mov     qword ptr [rsp+4D0h+SubAuthority2], rax; ReturnLength
0x180006ee2  mov     [rsp+4D0h+Sid], rdi
0x180006ee7  call    cs:__imp_NtQueryInformationToken
0x180006eed  mov     ebx, eax
0x180006eef  jmp     short loc_180006EFA
0x180006ef1  lea     rax, [rbp+3D0h+TokenInformation]
0x180006ef5  mov     [rsp+4D0h+Sid], rax
0x180006efa  test    ebx, ebx
0x180006efc  jns     short loc_180006F61
0x180006efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f05  lea     rax, WPP_GLOBAL_Control
0x180006f0c  cmp     rcx, rax
0x180006f0f  jz      loc_18000764E
0x180006f15  test    byte ptr [rcx+1Ch], 1
0x180006f19  jz      loc_18000764E
0x180006f1f  mov     edx, 76h ; 'v'
0x180006f24  jmp     loc_18000763B
0x180006f29  mov     [rsp+4D0h+Sid], r13
0x180006f2e  cmp     ebx, 0C000007Ch
0x180006f34  jz      short loc_180006F61
0x180006f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f3d  lea     rax, WPP_GLOBAL_Control
0x180006f44  cmp     rcx, rax
0x180006f47  jz      loc_18000764E
0x180006f4d  test    byte ptr [rcx+1Ch], 1
0x180006f51  jz      loc_18000764E
0x180006f57  mov     edx, 77h ; 'w'
0x180006f5c  jmp     loc_18000763B
0x180006f61  cmp     cs:NtLmGlobalProcessUserSid, rsi
0x180006f68  jnz     loc_1800070B0
0x180006f6e  lea     r8, [rsp+4D0h+Handle]; TokenHandle
0x180006f73  mov     edx, 8; DesiredAccess
0x180006f78  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180006f7f  call    cs:__imp_NtOpenProcessToken
0x180006f85  mov     ebx, eax
0x180006f87  test    eax, eax
0x180006f89  jns     short loc_180006FB6
0x180006f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f92  lea     rax, WPP_GLOBAL_Control
0x180006f99  cmp     rcx, rax
0x180006f9c  jz      loc_18000764E
0x180006fa2  test    byte ptr [rcx+1Ch], 1
0x180006fa6  jz      loc_18000764E
0x180006fac  mov     edx, 78h ; 'x'
0x180006fb1  jmp     loc_18000763B
0x180006fb6  mov     rcx, [rsp+4D0h+Handle]; TokenHandle
0x180006fbb  lea     rax, [rsp+4D0h+ReturnLength]
0x180006fc0  mov     r9d, 80h; TokenInformationLength
0x180006fc6  mov     qword ptr [rsp+4D0h+SubAuthority2], rax; ReturnLength
0x180006fcb  lea     r8, [rbp+3D0h+var_380]; TokenInformation
0x180006fcf  mov     [rsp+4D0h+ReturnLength], 80h
0x180006fd7  mov     edx, 1; TokenInformationClass
0x180006fdc  call    cs:__imp_NtQueryInformationToken
0x180006fe2  mov     ebx, eax
0x180006fe4  cmp     eax, 0C0000023h
0x180006fe9  jnz     short loc_18000702F
0x180006feb  mov     ecx, [rsp+4D0h+ReturnLength]; uBytes
0x180006fef  call    NtLmAllocate
0x180006ff4  mov     r14, rax
0x180006ff7  test    rax, rax
0x180006ffa  jnz     short loc_180007006
0x180006ffc  mov     ebx, 0C000009Ah
0x180007001  jmp     loc_18000764E
0x180007006  mov     r9d, [rsp+4D0h+ReturnLength]; TokenInformationLength
0x18000700b  lea     rax, [rsp+4D0h+ReturnLength]
0x180007010  mov     rcx, [rsp+4D0h+Handle]; TokenHandle
0x180007015  mov     r8, r14; TokenInformation
0x180007018  mov     edx, 1; TokenInformationClass
0x18000701d  mov     qword ptr [rsp+4D0h+SubAuthority2], rax; ReturnLength
0x180007022  mov     r13, r14
0x180007025  call    cs:__imp_NtQueryInformationToken
0x18000702b  mov     ebx, eax
0x18000702d  jmp     short loc_180007033
0x18000702f  lea     r13, [rbp+3D0h+var_380]
0x180007033  test    ebx, ebx
0x180007035  jns     short loc_180007062
0x180007037  mov     rcx, cs:WPP_GLOBAL_Control
0x18000703e  lea     rax, WPP_GLOBAL_Control
0x180007045  cmp     rcx, rax
0x180007048  jz      loc_18000764E
0x18000704e  test    byte ptr [rcx+1Ch], 1
0x180007052  jz      loc_18000764E
0x180007058  mov     edx, 79h ; 'y'
0x18000705d  jmp     loc_18000763B
0x180007062  mov     rcx, [r13+0]; Sid
0x180007066  call    cs:__imp_RtlLengthSid
0x18000706c  mov     eax, eax
0x18000706e  mov     ecx, eax; uBytes
0x180007070  mov     [rbp+3D0h+Size], rax
0x180007074  call    NtLmAllocate
0x180007079  mov     rbx, rax
0x18000707c  test    rax, rax
0x18000707f  jnz     short loc_18000708B
0x180007081  mov     ebx, 0C000009Ah
0x180007086  jmp     loc_18000764E
0x18000708b  mov     r8, [rbp+3D0h+Size]; Size
0x18000708f  mov     rcx, rbx; void *
0x180007092  mov     rdx, [r13+0]; Src
0x180007096  call    memcpy_0
0x18000709b  xor     eax, eax
0x18000709d  lock cmpxchg cs:NtLmGlobalProcessUserSid, rbx
0x1800070a6  jz      short loc_1800070B0
0x1800070a8  mov     rcx, rbx
0x1800070ab  call    NtLmFree
0x1800070b0  cmp     cs:?NtLmProcessAppContainerCached@@3HA, esi; int NtLmProcessAppContainerCached
0x1800070b6  jnz     loc_1800071BA
0x1800070bc  mov     rcx, [rsp+4D0h+Handle]
0x1800070c1  test    rcx, rcx
0x1800070c4  jnz     short loc_180007113
0x1800070c6  lea     r8, [rsp+4D0h+Handle]; TokenHandle
0x1800070cb  mov     edx, 8; DesiredAccess
0x1800070d0  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800070d7  call    cs:__imp_NtOpenProcessToken
0x1800070dd  mov     ebx, eax
0x1800070df  test    eax, eax
0x1800070e1  jns     short loc_18000710E
0x1800070e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070ea  lea     rax, WPP_GLOBAL_Control
0x1800070f1  cmp     rcx, rax
0x1800070f4  jz      loc_18000764E
0x1800070fa  test    byte ptr [rcx+1Ch], 1
0x1800070fe  jz      loc_18000764E
0x180007104  mov     edx, 7Ah ; 'z'
0x180007109  jmp     loc_18000763B
0x18000710e  mov     rcx, [rsp+4D0h+Handle]; TokenHandle
0x180007113  lea     r9, [rbp+3D0h+var_440]; unsigned int *
0x180007117  lea     r8, [rbp+3D0h+Src]; struct _TOKEN_APPCONTAINER_INFORMATION *
0x18000711e  lea     rdx, [rsp+4D0h+ReturnLength+4]; unsigned __int8 *
0x180007123  call    ?SspGetTokenPackage@@YAJPEAXPEAEPEAU_TOKEN_APPCONTAINER_INFORMATION@@PEAK@Z; SspGetTokenPackage(void *,uchar *,_TOKEN_APPCONTAINER_INFORMATION *,ulong *)
0x180007128  mov     ebx, eax
0x18000712a  test    eax, eax
0x18000712c  jns     short loc_180007159
0x18000712e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007135  lea     rax, WPP_GLOBAL_Control
0x18000713c  cmp     rcx, rax
0x18000713f  jz      loc_18000764E
0x180007145  test    byte ptr [rcx+1Ch], 1
0x180007149  jz      loc_18000764E
0x18000714f  mov     edx, 7Bh ; '{'
0x180007154  jmp     loc_18000763B
0x180007159  mov     cs:?NtLmProcessAppContainerCached@@3HA, 1; int NtLmProcessAppContainerCached
0x180007163  cmp     byte ptr [rsp+4D0h+ReturnLength+4], sil
0x180007168  jz      short loc_1800071BA
0x18000716a  mov     rcx, [rbp+3D0h+Src]; Sid
0x180007171  call    cs:__imp_RtlLengthSid
0x180007177  mov     ecx, eax; uBytes
0x180007179  mov     r13d, eax
0x18000717c  call    NtLmAllocate
0x180007181  mov     rbx, rax
0x180007184  test    rax, rax
0x180007187  jnz     short loc_180007193
0x180007189  mov     ebx, 0C000009Ah
0x18000718e  jmp     loc_18000764E
0x180007193  mov     rdx, [rbp+3D0h+Src]; Src
0x18000719a  mov     r8, r13; Size
0x18000719d  mov     rcx, rbx; void *
0x1800071a0  call    memcpy_0
0x1800071a5  xor     eax, eax
0x1800071a7  lock cmpxchg cs:?NtLmProcessAppContainerSid@@3PEAXEA, rbx; void * NtLmProcessAppContainerSid
0x1800071b0  jz      short loc_1800071BA
0x1800071b2  mov     rcx, rbx
0x1800071b5  call    NtLmFree
0x1800071ba  lea     rax, [rsp+4D0h+ReturnLength]
0x1800071bf  mov     [rsp+4D0h+ReturnLength], 80h
0x1800071c7  mov     r9d, 80h; TokenInformationLength
0x1800071cd  mov     qword ptr [rsp+4D0h+SubAuthority2], rax; ReturnLength
0x1800071d2  lea     r8, [rbp+3D0h+var_300]; TokenInformation
0x1800071d9  mov     edx, 1; TokenInformationClass
0x1800071de  mov     rcx, r12; TokenHandle
0x1800071e1  call    cs:__imp_NtQueryInformationToken
  ... truncated ...
```
