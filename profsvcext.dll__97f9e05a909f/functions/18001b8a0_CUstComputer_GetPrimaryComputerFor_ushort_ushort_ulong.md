# CUstComputer::GetPrimaryComputerFor(ushort *,ushort * * *,ulong &)

- ea: `0x18001b8a0`
- end: `0x18001bb30`
- name: `?GetPrimaryComputerFor@CUstComputer@@SAJPEAGPEAPEAPEAGAEAK@Z`
- size: `656`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 ***, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b214`

## callees

- `0x18000a8f0`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001b8a0`
- `0x18001c284`
- `0x18001c41c`
- `0x18001c50c`
- `0x18001d0ac`
- `0x18001d328`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x18001bae5`
- `WLDAP32!__imp_ldap_unbind` at `0x18001bae5`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001b915`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001b915`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b94e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b9c1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001ba2b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b94e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b9c1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001ba2b`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001b9ee`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001b9ee`
- `WLDAP32!__imp_ldap_connect` at `0x18001b984`
- `WLDAP32!__imp_ldap_connect` at `0x18001b984`
- `WLDAP32!__imp_ldap_initW` at `0x18001b907`
- `WLDAP32!__imp_ldap_initW` at `0x18001b907`

## pseudocode

```c
__int64 __fastcall CUstComputer::GetPrimaryComputerFor(
        unsigned __int16 *a1,
        unsigned __int16 ***a2,
        unsigned int *a3,
        __int64 a4)
{
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // r14
  LDAP *v9; // rbp
  ULONG LastError; // ebx
  signed int v11; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // r9
  signed int v14; // ebx
  ULONG v15; // esi
  signed int v16; // eax
  ULONG v17; // esi
  signed int v18; // eax
  int SchemaNamingContext; // eax
  ULONG v20; // eax
  unsigned __int16 *v22; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  *a3 = 0;
  v5 = 0;
  v22 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_ab0185983553356c12180ac14bccd298_Traceguids, a4);
  }
  v9 = ldap_initW(a1, 0x185u);
  if ( v9 )
    goto LABEL_11;
  LastError = LdapGetLastError();
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ab0185983553356c12180ac14bccd298_Traceguids, LastError);
  }
  v11 = LdapMapErrorToWin32(LastError);
  v14 = v11;
  if ( v11 > 0 )
    v14 = (unsigned __int16)v11 | 0x80070000;
  if ( v14 >= 0 )
  {
LABEL_11:
    v14 = CUstComputer::_SetConnectionOptions(v9);
    if ( v14 >= 0 )
    {
      v14 = 0;
      v15 = ldap_connect(v9, 0);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v15);
        }
        v16 = LdapMapErrorToWin32(v15);
        v14 = v16;
        if ( v16 > 0 )
          v14 = (unsigned __int16)v16 | 0x80070000;
      }
      if ( v14 >= 0 )
      {
        v14 = 0;
        v17 = ldap_bind_sW(v9, 0, 0, 0x486u);
        if ( v17 )
        {
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v17);
          }
          v18 = LdapMapErrorToWin32(v17);
          v14 = v18;
          if ( v18 > 0 )
            v14 = (unsigned __int16)v18 | 0x80070000;
        }
        if ( v14 >= 0 )
        {
          v14 = CUstUtil::ConvertDomainNameToDn(a1, &v22);
          if ( v14 >= 0 )
          {
            SchemaNamingContext = CUstUtil::GetSchemaNamingContext(&v23);
            v5 = v23;
            v14 = SchemaNamingContext;
            if ( SchemaNamingContext >= 0 )
              v14 = CUstComputer::_VerifySchemaSupport(v9, v23);
          }
          v4 = v22;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v13);
  }
  if ( v14 >= 0 )
    v14 = CUstComputer::_SearchAD(v9, v4, a2, a3);
  if ( v4 )
    operator delete(v4, v12);
  if ( v5 )
    operator delete(v5, v12);
  if ( v9 )
  {
    v20 = ldap_unbind(v9);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v20);
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001b8a0  mov     [rsp+arg_0], rbx
0x18001b8a5  push    rbp
0x18001b8a6  push    rsi
0x18001b8a7  push    rdi
0x18001b8a8  push    r12
0x18001b8aa  push    r13
0x18001b8ac  push    r14
0x18001b8ae  push    r15
0x18001b8b0  sub     rsp, 20h
0x18001b8b4  xor     edi, edi
0x18001b8b6  mov     dword ptr [r8], 0
0x18001b8bd  xor     r14d, r14d
0x18001b8c0  mov     [rsp+58h+arg_10], rdi
0x18001b8c5  mov     [rsp+58h+arg_18], r14
0x18001b8ca  mov     r12, r8
0x18001b8cd  mov     r13, rdx
0x18001b8d0  mov     r15, rcx
0x18001b8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8da  lea     rax, WPP_GLOBAL_Control
0x18001b8e1  cmp     rcx, rax
0x18001b8e4  jz      short loc_18001B8FF
0x18001b8e6  test    byte ptr [rcx+1Ch], 8
0x18001b8ea  jz      short loc_18001B8FF
0x18001b8ec  mov     rcx, [rcx+10h]
0x18001b8f0  lea     edx, [rdi+22h]
0x18001b8f3  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001b8fa  call    WPP_SF_
0x18001b8ff  mov     edx, 185h; PortNumber
0x18001b904  mov     rcx, r15; HostName
0x18001b907  call    cs:__imp_ldap_initW
0x18001b90d  mov     rbp, rax
0x18001b910  test    rax, rax
0x18001b913  jnz     short loc_18001B96B
0x18001b915  call    cs:__imp_LdapGetLastError
0x18001b91b  mov     ebx, eax
0x18001b91d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b924  lea     rax, WPP_GLOBAL_Control
0x18001b92b  cmp     rcx, rax
0x18001b92e  jz      short loc_18001B94C
0x18001b930  test    byte ptr [rcx+1Ch], 1
0x18001b934  jz      short loc_18001B94C
0x18001b936  mov     rcx, [rcx+10h]
0x18001b93a  lea     edx, [rbp+0Ch]
0x18001b93d  mov     r9d, ebx
0x18001b940  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001b947  call    WPP_SF_d
0x18001b94c  mov     ecx, ebx; LdapError
0x18001b94e  call    cs:__imp_LdapMapErrorToWin32
0x18001b954  mov     ebx, eax
0x18001b956  test    eax, eax
0x18001b958  jle     short loc_18001B963
0x18001b95a  movzx   ebx, ax
0x18001b95d  or      ebx, 80070000h
0x18001b963  test    ebx, ebx
0x18001b965  js      loc_18001BA7E
0x18001b96b  mov     rcx, rbp; ld
0x18001b96e  call    ?_SetConnectionOptions@CUstComputer@@KAJPEAUldap@@@Z; CUstComputer::_SetConnectionOptions(ldap *)
0x18001b973  mov     ebx, eax
0x18001b975  test    eax, eax
0x18001b977  js      loc_18001BA7E
0x18001b97d  xor     edx, edx; timeout
0x18001b97f  mov     rcx, rbp; ld
0x18001b982  xor     ebx, ebx
0x18001b984  call    cs:__imp_ldap_connect
0x18001b98a  mov     esi, eax
0x18001b98c  test    eax, eax
0x18001b98e  jz      short loc_18001B9D6
0x18001b990  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b997  lea     rax, WPP_GLOBAL_Control
0x18001b99e  cmp     rcx, rax
0x18001b9a1  jz      short loc_18001B9BF
0x18001b9a3  test    byte ptr [rcx+1Ch], 1
0x18001b9a7  jz      short loc_18001B9BF
0x18001b9a9  mov     rcx, [rcx+10h]
0x18001b9ad  lea     edx, [rbx+0Fh]
0x18001b9b0  mov     r9d, esi
0x18001b9b3  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001b9ba  call    WPP_SF_d
0x18001b9bf  mov     ecx, esi; LdapError
0x18001b9c1  call    cs:__imp_LdapMapErrorToWin32
0x18001b9c7  mov     ebx, eax
0x18001b9c9  test    eax, eax
0x18001b9cb  jle     short loc_18001B9D6
0x18001b9cd  movzx   ebx, ax
0x18001b9d0  or      ebx, 80070000h
0x18001b9d6  test    ebx, ebx
0x18001b9d8  js      loc_18001BA7E
0x18001b9de  mov     r9d, 486h; method
0x18001b9e4  xor     r8d, r8d; cred
0x18001b9e7  xor     edx, edx; dn
0x18001b9e9  mov     rcx, rbp; ld
0x18001b9ec  xor     ebx, ebx
0x18001b9ee  call    cs:__imp_ldap_bind_sW
0x18001b9f4  mov     esi, eax
0x18001b9f6  test    eax, eax
0x18001b9f8  jz      short loc_18001BA40
0x18001b9fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba01  lea     rax, WPP_GLOBAL_Control
0x18001ba08  cmp     rcx, rax
0x18001ba0b  jz      short loc_18001BA29
0x18001ba0d  test    byte ptr [rcx+1Ch], 1
0x18001ba11  jz      short loc_18001BA29
0x18001ba13  mov     rcx, [rcx+10h]
0x18001ba17  lea     edx, [rbx+10h]
0x18001ba1a  mov     r9d, esi
0x18001ba1d  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001ba24  call    WPP_SF_d
0x18001ba29  mov     ecx, esi; LdapError
0x18001ba2b  call    cs:__imp_LdapMapErrorToWin32
0x18001ba31  mov     ebx, eax
0x18001ba33  test    eax, eax
0x18001ba35  jle     short loc_18001BA40
0x18001ba37  movzx   ebx, ax
0x18001ba3a  or      ebx, 80070000h
0x18001ba40  test    ebx, ebx
0x18001ba42  js      short loc_18001BA7E
0x18001ba44  lea     rdx, [rsp+58h+arg_10]; unsigned __int16 **
0x18001ba49  mov     rcx, r15; unsigned __int16 *
0x18001ba4c  call    ?ConvertDomainNameToDn@CUstUtil@@SAJPEAGPEAPEAG@Z; CUstUtil::ConvertDomainNameToDn(ushort *,ushort * *)
0x18001ba51  mov     ebx, eax
0x18001ba53  test    eax, eax
0x18001ba55  js      short loc_18001BA79
0x18001ba57  lea     rcx, [rsp+58h+arg_18]; unsigned __int16 **
0x18001ba5c  call    ?GetSchemaNamingContext@CUstUtil@@SAJPEAPEAG@Z; CUstUtil::GetSchemaNamingContext(ushort * *)
0x18001ba61  mov     r14, [rsp+58h+arg_18]
0x18001ba66  mov     ebx, eax
0x18001ba68  test    eax, eax
0x18001ba6a  js      short loc_18001BA79
0x18001ba6c  mov     rdx, r14; unsigned __int16 *
0x18001ba6f  mov     rcx, rbp; ld
0x18001ba72  call    ?_VerifySchemaSupport@CUstComputer@@KAJPEAUldap@@PEAG@Z; CUstComputer::_VerifySchemaSupport(ldap *,ushort *)
0x18001ba77  mov     ebx, eax
0x18001ba79  mov     rdi, [rsp+58h+arg_10]
0x18001ba7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba85  lea     rsi, WPP_GLOBAL_Control
0x18001ba8c  cmp     rcx, rsi
0x18001ba8f  jz      short loc_18001BAAC
0x18001ba91  test    byte ptr [rcx+1Ch], 8
0x18001ba95  jz      short loc_18001BAAC
0x18001ba97  mov     rcx, [rcx+10h]
0x18001ba9b  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001baa2  mov     edx, 23h ; '#'
0x18001baa7  call    WPP_SF_
0x18001baac  test    ebx, ebx
0x18001baae  js      short loc_18001BAC3
0x18001bab0  mov     r9, r12; unsigned int *
0x18001bab3  mov     r8, r13; unsigned __int16 ***
0x18001bab6  mov     rdx, rdi; base
0x18001bab9  mov     rcx, rbp; struct ldap *
0x18001babc  call    ?_SearchAD@CUstComputer@@KAJPEAUldap@@PEAGPEAPEAPEAGAEAK@Z; CUstComputer::_SearchAD(ldap *,ushort *,ushort * * *,ulong &)
0x18001bac1  mov     ebx, eax
0x18001bac3  test    rdi, rdi
0x18001bac6  jz      short loc_18001BAD0
0x18001bac8  mov     rcx, rdi; void *
0x18001bacb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bad0  test    r14, r14
0x18001bad3  jz      short loc_18001BADD
0x18001bad5  mov     rcx, r14; void *
0x18001bad8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001badd  test    rbp, rbp
0x18001bae0  jz      short loc_18001BB19
0x18001bae2  mov     rcx, rbp; ld
0x18001bae5  call    cs:__imp_ldap_unbind
0x18001baeb  test    eax, eax
0x18001baed  jz      short loc_18001BB19
0x18001baef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baf6  cmp     rcx, rsi
0x18001baf9  jz      short loc_18001BB19
0x18001bafb  test    byte ptr [rcx+1Ch], 1
0x18001baff  jz      short loc_18001BB19
0x18001bb01  mov     rcx, [rcx+10h]
0x18001bb05  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001bb0c  mov     edx, 21h ; '!'
0x18001bb11  mov     r9d, eax
0x18001bb14  call    WPP_SF_d
0x18001bb19  mov     eax, ebx
0x18001bb1b  mov     rbx, [rsp+58h+arg_0]
0x18001bb20  add     rsp, 20h
0x18001bb24  pop     r15
0x18001bb26  pop     r14
0x18001bb28  pop     r13
0x18001bb2a  pop     r12
0x18001bb2c  pop     rdi
0x18001bb2d  pop     rsi
0x18001bb2e  pop     rbp
0x18001bb2f  retn
```
