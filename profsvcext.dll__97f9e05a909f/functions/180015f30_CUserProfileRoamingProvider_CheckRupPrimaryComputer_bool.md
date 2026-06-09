# CUserProfileRoamingProvider::_CheckRupPrimaryComputer(bool &)

- ea: `0x180015f30`
- end: `0x1800160cb`
- name: `?_CheckRupPrimaryComputer@CUserProfileRoamingProvider@@AEAAJAEA_N@Z`
- size: `411`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *this, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011880`

## callees

- `0x1800043a0`
- `0x180004890`
- `0x1800056e8`
- `0x18000671c`
- `0x180006a9c`
- `0x1800079f0`
- `0x18000f4b0`
- `0x180010f1c`
- `0x180015f30`
- `0x18001b214`
- `0x180020010`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001602a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001602a`

## string_xrefs

- `0x180015f6f`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_CheckRupPrimaryComputer(CUserProfileRoamingProvider *this, bool *a2)
{
  char v3; // di
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // r8
  void *v10; // rax
  const wchar_t *v11; // r8
  signed int v12; // eax
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  int DomainHash; // [rsp+48h] [rbp+28h] BYREF
  int v18; // [rsp+50h] [rbp+30h] BYREF

  LOBYTE(DomainHash) = 0;
  v3 = 1;
  *a2 = 1;
  v6 = CheckTSRoleInstalled((bool *)&DomainHash);
  if ( v6 < 0 )
  {
    v7 = 934;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
    return (unsigned int)v6;
  }
  if ( !(_BYTE)DomainHash )
  {
    v6 = CheckVDIRoleInstalled((bool *)&DomainHash);
    if ( v6 < 0 )
    {
      v7 = 938;
      goto LABEL_3;
    }
    if ( !(_BYTE)DomainHash )
    {
      DomainHash = RUPTelemetry::GetDomainHash();
      v18 = 1;
      RUPTelemetryProvider::RupClientType<unsigned long,unsigned int &>(&v18, &DomainHash);
      LOBYTE(DomainHash) = 0;
      Profile::GetLocalSetting(0, &DomainHash, v9);
      LOBYTE(v18) = 1;
      if ( (_BYTE)DomainHash )
      {
        v10 = (void *)(***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
        v6 = CheckPrimaryComputerRelationship(v10, (bool *)&v18);
        if ( v6 == -2147024846 )
        {
          if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
          {
            v11 = L"running as a cross-forest logon";
LABEL_29:
            McTemplateU0z_EtwEventWriteTransfer(v5, EVENT_PRIMARY_COMPUTER_ENV_ISSUE, v11);
            return 0;
          }
          return 0;
        }
        v3 = v18;
      }
      else
      {
        v6 = 0;
      }
      v12 = LdapMapErrorToWin32(0x20u);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      if ( v6 != v12 )
      {
        if ( v6 < 0 )
        {
          if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x20) != 0 )
            McTemplateU0q_EtwEventWriteTransfer(v13, EVENT_FAILED_PRIMARY_COMPUTER, (unsigned int)v6);
          v7 = 965;
          goto LABEL_3;
        }
        v14 = L"is";
        if ( !v3 )
          v14 = L"is not";
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(v13, EVENT_PRIMARY_COMPUTER_RESULT, v14);
        if ( !v3 )
          *a2 = 0;
      }
      return 0;
    }
  }
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
  {
    v11 = L"running as a terminal server farm";
    goto LABEL_29;
  }
  return 0;
}

```

## disassembly

```asm
0x180015f30  mov     [rsp-18h+arg_0], rbx
0x180015f35  mov     [rsp-18h+arg_18], rsi
0x180015f3a  push    rbp
0x180015f3b  push    rdi
0x180015f3c  push    r14; int
0x180015f3e  mov     rbp, rsp
0x180015f41  sub     rsp, 20h
0x180015f45  mov     r14, rcx
0x180015f48  mov     byte ptr [rbp+arg_8], 0
0x180015f4c  mov     edi, 1
0x180015f51  lea     rcx, [rbp+arg_8]; bool *
0x180015f55  mov     [rdx], dil
0x180015f58  mov     rsi, rdx
0x180015f5b  call    ?CheckTSRoleInstalled@@YAJAEA_N@Z; CheckTSRoleInstalled(bool &)
0x180015f60  mov     ebx, eax
0x180015f62  test    eax, eax
0x180015f64  jns     short loc_180015F85
0x180015f66  mov     edx, 3A6h; void *
0x180015f6b  mov     rcx, [rbp+18h]; this
0x180015f6f  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180015f76  mov     r9d, ebx; char *
0x180015f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f7e  mov     eax, ebx
0x180015f80  jmp     loc_1800160B8
0x180015f85  cmp     byte ptr [rbp+arg_8], 0
0x180015f89  jnz     loc_18001609A
0x180015f8f  lea     rcx, [rbp+arg_8]; bool *
0x180015f93  call    ?CheckVDIRoleInstalled@@YAJAEA_N@Z; CheckVDIRoleInstalled(bool &)
0x180015f98  mov     ebx, eax
0x180015f9a  test    eax, eax
0x180015f9c  jns     short loc_180015FA5
0x180015f9e  mov     edx, 3AAh
0x180015fa3  jmp     short loc_180015F6B
0x180015fa5  cmp     byte ptr [rbp+arg_8], 0
0x180015fa9  jnz     loc_18001609A
0x180015faf  call    RUPTelemetry__GetDomainHash
0x180015fb4  lea     rdx, [rbp+arg_8]
0x180015fb8  mov     [rbp+arg_8], eax
0x180015fbb  lea     rcx, [rbp+arg_10]
0x180015fbf  mov     [rbp+arg_10], edi
0x180015fc2  call    ??$RupClientType@KAEAI@RUPTelemetryProvider@@SAX$$QEAKAEAI@Z; RUPTelemetryProvider::RupClientType<ulong,uint &>(ulong &&,uint &)
0x180015fc7  lea     rdx, [rbp+arg_8]
0x180015fcb  mov     byte ptr [rbp+arg_8], 0
0x180015fcf  xor     ecx, ecx
0x180015fd1  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180015fd6  cmp     byte ptr [rbp+arg_8], 0
0x180015fda  mov     byte ptr [rbp+arg_10], dil
0x180015fde  jz      short loc_180016023
0x180015fe0  mov     rcx, [r14+8]
0x180015fe4  mov     rax, [rcx]
0x180015fe7  mov     rax, [rax]
0x180015fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fef  mov     rcx, rax; TokenHandle
0x180015ff2  lea     rdx, [rbp+arg_10]; bool *
0x180015ff6  call    ?CheckPrimaryComputerRelationship@@YAJPEAXAEA_N@Z; CheckPrimaryComputerRelationship(void *,bool &)
0x180015ffb  mov     ebx, eax
0x180015ffd  cmp     eax, 80070032h
0x180016002  jnz     short loc_18001601D
0x180016004  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x18001600b  jz      loc_1800160B6
0x180016011  lea     r8, aRunningAsACros; "running as a cross-forest logon"
0x180016018  jmp     loc_1800160AA
0x18001601d  mov     dil, byte ptr [rbp+arg_10]
0x180016021  jmp     short loc_180016025
0x180016023  xor     ebx, ebx
0x180016025  mov     ecx, 20h ; ' '; LdapError
0x18001602a  call    cs:__imp_LdapMapErrorToWin32
0x180016030  test    eax, eax
0x180016032  jle     short loc_18001603C
0x180016034  movzx   eax, ax
0x180016037  or      eax, 80070000h
0x18001603c  cmp     ebx, eax
0x18001603e  jz      short loc_1800160B6
0x180016040  test    ebx, ebx
0x180016042  jns     short loc_180016066
0x180016044  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 20h
0x18001604b  jz      short loc_18001605C
0x18001604d  mov     r8d, ebx
0x180016050  lea     rdx, EVENT_FAILED_PRIMARY_COMPUTER
0x180016057  call    McTemplateU0q_EtwEventWriteTransfer
0x18001605c  mov     edx, 3C5h
0x180016061  jmp     loc_180015F6B
0x180016066  test    dil, dil
0x180016069  lea     r8, aIs; "is"
0x180016070  lea     rax, aIsNot; "is not"
0x180016077  cmovz   r8, rax
0x18001607b  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180016082  jz      short loc_180016090
0x180016084  lea     rdx, EVENT_PRIMARY_COMPUTER_RESULT
0x18001608b  call    McTemplateU0z_EtwEventWriteTransfer
0x180016090  test    dil, dil
0x180016093  jnz     short loc_1800160B6
0x180016095  mov     [rsi], dil
0x180016098  jmp     short loc_1800160B6
0x18001609a  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800160a1  jz      short loc_1800160B6
0x1800160a3  lea     r8, aRunningAsATerm; "running as a terminal server farm"
0x1800160aa  lea     rdx, EVENT_PRIMARY_COMPUTER_ENV_ISSUE
0x1800160b1  call    McTemplateU0z_EtwEventWriteTransfer
0x1800160b6  xor     eax, eax
0x1800160b8  mov     rbx, [rsp+20h+arg_0]
0x1800160bd  mov     rsi, [rsp+20h+arg_18]
0x1800160c2  add     rsp, 20h
0x1800160c6  pop     r14
0x1800160c8  pop     rdi
0x1800160c9  pop     rbp
0x1800160ca  retn
```
