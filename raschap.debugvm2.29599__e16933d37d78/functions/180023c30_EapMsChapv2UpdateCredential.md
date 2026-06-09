# EapMsChapv2UpdateCredential

- ea: `0x180023c30`
- end: `0x180023d6c`
- name: `EapMsChapv2UpdateCredential`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016280`
- `0x180016ee0`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x18001e494`
- `0x180023c30`
- `0x180023e30`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180023d1c`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x180023d1c`

## pseudocode

```c
__int64 __fastcall EapMsChapv2UpdateCredential(__int64 a1, unsigned int a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  unsigned int UserDataWithEncPwd; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+20h] [rbp-58h] BYREF
  _DWORD v16[2]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  v16[1] = 0;
  pProtectionType = CredUnprotected;
  *(_QWORD *)a6 = 0;
  UserDataWithEncPwd = MsChapv2SaveDomainUsername(a5, a1, a2);
  v11 = UserDataWithEncPwd;
  if ( UserDataWithEncPwd )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v11;
    v13 = 46;
  }
  else
  {
    v16[0] = 2 * a4;
    v17 = a3;
    UserDataWithEncPwd = AllocateUserDataWithEncPwd(a5, a6, v16);
    v11 = UserDataWithEncPwd;
    if ( !UserDataWithEncPwd )
    {
      if ( CredIsProtectedW((LPWSTR)(*(_QWORD *)a6 + 788LL), &pProtectionType)
        && (unsigned int)(pProtectionType - 1) <= 1 )
      {
        *(_DWORD *)(*(_QWORD *)a6 + 4LL) |= 0x200u;
      }
      goto LABEL_13;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v11;
    v13 = 47;
  }
  WPP_SF_d(v12[2], v13, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, UserDataWithEncPwd);
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180023c30  push    rbx
0x180023c32  push    rbp
0x180023c33  push    rsi
0x180023c34  push    rdi
0x180023c35  push    r14
0x180023c37  push    r15
0x180023c39  sub     rsp, 48h
0x180023c3d  mov     r14d, r9d
0x180023c40  mov     rbp, r8
0x180023c43  mov     ebx, edx
0x180023c45  mov     rsi, rcx
0x180023c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c4f  lea     r15, WPP_GLOBAL_Control
0x180023c56  cmp     rcx, r15
0x180023c59  jz      short loc_180023C70
0x180023c5b  mov     rcx, [rcx+10h]
0x180023c5f  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180023c66  mov     edx, 2Dh ; '-'
0x180023c6b  call    WPP_SF_
0x180023c70  mov     rdi, [rsp+78h+arg_28]
0x180023c78  mov     r8d, ebx
0x180023c7b  mov     rcx, [rsp+78h+arg_20]
0x180023c83  mov     rdx, rsi
0x180023c86  mov     [rsp+78h+var_4C], 0
0x180023c8e  mov     [rsp+78h+pProtectionType], 0
0x180023c96  mov     qword ptr [rdi], 0
0x180023c9d  call    MsChapv2SaveDomainUsername
0x180023ca2  mov     ebx, eax
0x180023ca4  test    eax, eax
0x180023ca6  jz      short loc_180023CD2
0x180023ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180023caf  cmp     rcx, r15
0x180023cb2  jz      loc_180023D5D
0x180023cb8  mov     edx, 2Eh ; '.'
0x180023cbd  mov     rcx, [rcx+10h]
0x180023cc1  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180023cc8  mov     r9d, eax
0x180023ccb  call    WPP_SF_d
0x180023cd0  jmp     short loc_180023D39
0x180023cd2  mov     rcx, [rsp+78h+arg_20]
0x180023cda  lea     eax, [r14+r14]
0x180023cde  lea     r8, [rsp+78h+var_50]
0x180023ce3  mov     [rsp+78h+var_50], eax
0x180023ce7  mov     rdx, rdi
0x180023cea  mov     [rsp+78h+var_48], rbp
0x180023cef  call    AllocateUserDataWithEncPwd
0x180023cf4  mov     ebx, eax
0x180023cf6  test    eax, eax
0x180023cf8  jz      short loc_180023D0D
0x180023cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d01  cmp     rcx, r15
0x180023d04  jz      short loc_180023D5D
0x180023d06  mov     edx, 2Fh ; '/'
0x180023d0b  jmp     short loc_180023CBD
0x180023d0d  mov     rcx, [rdi]
0x180023d10  lea     rdx, [rsp+78h+pProtectionType]; pProtectionType
0x180023d15  add     rcx, 314h; pszProtectedCredentials
0x180023d1c  call    cs:__imp_CredIsProtectedW
0x180023d22  test    eax, eax
0x180023d24  jz      short loc_180023D39
0x180023d26  mov     eax, [rsp+78h+pProtectionType]
0x180023d2a  dec     eax
0x180023d2c  cmp     eax, 1
0x180023d2f  ja      short loc_180023D39
0x180023d31  mov     rax, [rdi]
0x180023d34  bts     dword ptr [rax+4], 9
0x180023d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d40  cmp     rcx, r15
0x180023d43  jz      short loc_180023D5D
0x180023d45  mov     rcx, [rcx+10h]
0x180023d49  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180023d50  mov     edx, 30h ; '0'
0x180023d55  mov     r9d, ebx
0x180023d58  call    WPP_SF_d
0x180023d5d  mov     eax, ebx
0x180023d5f  add     rsp, 48h
0x180023d63  pop     r15
0x180023d65  pop     r14
0x180023d67  pop     rdi
0x180023d68  pop     rsi
0x180023d69  pop     rbp
0x180023d6a  pop     rbx
0x180023d6b  retn
```
