# GmsapMapLdapErrorToNtStatusEx(ldap *,ulong)

- ea: `0x18000686c`
- end: `0x180006a32`
- name: `?GmsapMapLdapErrorToNtStatusEx@@YAJPEAUldap@@K@Z`
- size: `454`
- prototype: `__int64 __fastcall(LDAP *ld, ULONG LdapError)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007064`

## callees

- `0x1800062b0`
- `0x18000686c`
- `0x18000786c`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800069b2`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800069b2`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800068ad`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800068ad`
- `WLDAP32!__imp_ldap_get_option` at `0x1800068eb`
- `WLDAP32!__imp_ldap_get_option` at `0x180006971`
- `WLDAP32!__imp_ldap_get_option` at `0x1800068eb`
- `WLDAP32!__imp_ldap_get_option` at `0x180006971`
- `WLDAP32!__imp_ldap_memfree` at `0x1800069ca`
- `WLDAP32!__imp_ldap_memfree` at `0x1800069ca`

## pseudocode

```c
signed int __fastcall GmsapMapLdapErrorToNtStatusEx(LDAP *ld, ULONG LdapError)
{
  signed int result; // eax
  PWCHAR v5; // rax
  int v6; // r8d
  ULONG option; // eax
  int v8; // r8d
  _QWORD *v9; // rcx
  PCHAR v10; // rax
  ULONG v11; // eax
  int v12; // [rsp+58h] [rbp+28h] BYREF
  PCHAR outvalue; // [rsp+60h] [rbp+30h] BYREF

  result = 0;
  v12 = 0;
  outvalue = 0;
  if ( !LdapError )
    return result;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v5 = ldap_err2stringW(LdapError);
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v6, LdapError, (__int64)v5);
  }
  if ( ld )
  {
    option = ldap_get_option(ld, 51, &outvalue);
    if ( option )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBu, &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids, option);
        v9 = WPP_GLOBAL_Control;
      }
      v10 = 0;
      outvalue = 0;
    }
    else
    {
      v10 = outvalue;
      v9 = WPP_GLOBAL_Control;
    }
    if ( v10 && v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
      WPP_SF_DS(v9[2], 12, v8, LdapError, (__int64)v10);
    v11 = ldap_get_option(ld, 52, &v12);
    if ( v11 != 52 )
    {
      if ( !v11 )
      {
        result = v12;
        if ( !v12 )
        {
          result = 8341;
          v12 = 8341;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              0xEu,
              &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids,
              LdapError);
            result = v12;
          }
        }
        goto LABEL_22;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xDu, &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids, v11);
    }
  }
  result = LdapMapErrorToWin32(LdapError);
  v12 = result;
LABEL_22:
  if ( outvalue )
  {
    ldap_memfree(outvalue);
    result = v12;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0xC0070000;
  return result;
}

```

## disassembly

```asm
0x18000686c  mov     [rsp-18h+arg_0], rbx
0x180006871  push    rbp
0x180006872  push    rdi
0x180006873  push    r14
0x180006875  mov     rbp, rsp
0x180006878  sub     rsp, 30h
0x18000687c  xor     eax, eax
0x18000687e  mov     ebx, edx
0x180006880  mov     [rbp+arg_8], eax
0x180006883  mov     rdi, rcx
0x180006886  mov     [rbp+outvalue], rax
0x18000688a  test    edx, edx
0x18000688c  jz      loc_1800069E5
0x180006892  mov     rax, cs:WPP_GLOBAL_Control
0x180006899  lea     r14, WPP_GLOBAL_Control
0x1800068a0  cmp     rax, r14
0x1800068a3  jz      short loc_1800068D6
0x1800068a5  test    byte ptr [rax+1Ch], 4
0x1800068a9  jz      short loc_1800068D6
0x1800068ab  mov     ecx, edx; err
0x1800068ad  call    cs:__imp_ldap_err2stringW
0x1800068b4  nop     dword ptr [rax+rax+00h]
0x1800068b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068c0  mov     edx, 0Ah
0x1800068c5  mov     r9d, ebx
0x1800068c8  mov     [rsp+30h+var_10], rax
0x1800068cd  mov     rcx, [rcx+10h]
0x1800068d1  call    WPP_SF_DS
0x1800068d6  test    rdi, rdi
0x1800068d9  jz      loc_1800069B0
0x1800068df  lea     r8, [rbp+outvalue]; outvalue
0x1800068e3  mov     edx, 33h ; '3'; option
0x1800068e8  mov     rcx, rdi; ld
0x1800068eb  call    cs:__imp_ldap_get_option
0x1800068f2  nop     dword ptr [rax+rax+00h]
0x1800068f7  test    eax, eax
0x1800068f9  jz      short loc_180006934
0x1800068fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006902  cmp     rcx, r14
0x180006905  jz      short loc_18000692C
0x180006907  test    byte ptr [rcx+1Ch], 4
0x18000690b  jz      short loc_18000692C
0x18000690d  mov     rcx, [rcx+10h]
0x180006911  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x180006918  mov     edx, 0Bh
0x18000691d  mov     r9d, eax
0x180006920  call    WPP_SF_D
0x180006925  mov     rcx, cs:WPP_GLOBAL_Control
0x18000692c  xor     eax, eax
0x18000692e  mov     [rbp+outvalue], rax
0x180006932  jmp     short loc_18000693F
0x180006934  mov     rax, [rbp+outvalue]
0x180006938  mov     rcx, cs:WPP_GLOBAL_Control
0x18000693f  test    rax, rax
0x180006942  jz      short loc_180006965
0x180006944  cmp     rcx, r14
0x180006947  jz      short loc_180006965
0x180006949  test    byte ptr [rcx+1Ch], 4
0x18000694d  jz      short loc_180006965
0x18000694f  mov     rcx, [rcx+10h]
0x180006953  mov     edx, 0Ch
0x180006958  mov     r9d, ebx
0x18000695b  mov     [rsp+30h+var_10], rax
0x180006960  call    WPP_SF_DS
0x180006965  lea     r8, [rbp+arg_8]; outvalue
0x180006969  mov     edx, 34h ; '4'; option
0x18000696e  mov     rcx, rdi; ld
0x180006971  call    cs:__imp_ldap_get_option
0x180006978  nop     dword ptr [rax+rax+00h]
0x18000697d  cmp     eax, 34h ; '4'
0x180006980  jz      short loc_1800069B0
0x180006982  test    eax, eax
0x180006984  jz      short loc_1800069F4
0x180006986  mov     rcx, cs:WPP_GLOBAL_Control
0x18000698d  cmp     rcx, r14
0x180006990  jz      short loc_1800069B0
0x180006992  test    byte ptr [rcx+1Ch], 4
0x180006996  jz      short loc_1800069B0
0x180006998  mov     rcx, [rcx+10h]
0x18000699c  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x1800069a3  mov     edx, 0Dh
0x1800069a8  mov     r9d, eax
0x1800069ab  call    WPP_SF_D
0x1800069b0  mov     ecx, ebx; LdapError
0x1800069b2  call    cs:__imp_LdapMapErrorToWin32
0x1800069b9  nop     dword ptr [rax+rax+00h]
0x1800069be  mov     [rbp+arg_8], eax
0x1800069c1  mov     rcx, [rbp+outvalue]; Block
0x1800069c5  test    rcx, rcx
0x1800069c8  jz      short loc_1800069D9
0x1800069ca  call    cs:__imp_ldap_memfree
0x1800069d1  nop     dword ptr [rax+rax+00h]
0x1800069d6  mov     eax, [rbp+arg_8]
0x1800069d9  test    eax, eax
0x1800069db  jle     short loc_1800069E5
0x1800069dd  movzx   eax, ax
0x1800069e0  or      eax, 0C0070000h
0x1800069e5  mov     rbx, [rsp+30h+arg_0]
0x1800069ea  add     rsp, 30h
0x1800069ee  pop     r14
0x1800069f0  pop     rdi
0x1800069f1  pop     rbp
0x1800069f2  retn
0x1800069f4  mov     eax, [rbp+arg_8]
0x1800069f7  test    eax, eax
0x1800069f9  jnz     short loc_1800069C1
0x1800069fb  mov     eax, 2095h
0x180006a00  mov     [rbp+arg_8], eax
0x180006a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a0a  cmp     rcx, r14
0x180006a0d  jz      short loc_1800069C1
0x180006a0f  test    byte ptr [rcx+1Ch], 4
0x180006a13  jz      short loc_1800069C1
0x180006a15  mov     rcx, [rcx+10h]
0x180006a19  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x180006a20  mov     edx, 0Eh
0x180006a25  mov     r9d, ebx
0x180006a28  call    WPP_SF_D
0x180006a2d  mov     eax, [rbp+arg_8]
0x180006a30  jmp     short loc_1800069C1
```
