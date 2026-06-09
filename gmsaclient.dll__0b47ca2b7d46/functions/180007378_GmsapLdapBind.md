# GmsapLdapBind

- ea: `0x180007378`
- end: `0x180007646`
- name: `GmsapLdapBind`
- size: `718`
- prototype: `__int64 __usercall@<rax>(PWSTR HostName@<rcx>, int invalue)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800025b0`
- `0x180003200`

## callees

- `0x180007378`
- `0x18000764c`
- `0x18000796c`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x180007626`
- `WLDAP32!__imp_ldap_unbind` at `0x180007626`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000743e`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000749e`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180007504`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000755c`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000743e`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000749e`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180007504`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000755c`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800073db`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800073db`
- `WLDAP32!__imp_ldap_bind_sW` at `0x1800075b9`
- `WLDAP32!__imp_ldap_bind_sW` at `0x1800075b9`
- `WLDAP32!__imp_ldap_err2stringW` at `0x18000740c`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180007473`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800074d3`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180007539`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180007591`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800075e6`
- `WLDAP32!__imp_ldap_err2stringW` at `0x18000740c`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180007473`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800074d3`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180007539`
- `WLDAP32!__imp_ldap_err2stringW` at `0x180007591`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1800075e6`
- `WLDAP32!__imp_ldap_initW` at `0x1800073c7`
- `WLDAP32!__imp_ldap_initW` at `0x1800073c7`

## pseudocode

```c
__int64 __fastcall GmsapLdapBind(PWSTR HostName, __int64 a2, LDAP **a3, __int64 a4, int invalue)
{
  WCHAR *v6; // rsi
  LDAP *v8; // rax
  ULONG LastError; // ebx
  PWCHAR v10; // rax
  int v11; // r8d
  int v12; // edx
  LDAP *v13; // rcx
  LDAP *v14; // rcx
  int v15; // r9d
  int v16; // edi
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = a2;
  invalue = 0;
  v6 = HostName;
  if ( !a3 )
    return 3221225485LL;
  if ( !HostName )
  {
    *a3 = 0;
    return 3221225485LL;
  }
  if ( *HostName == 92 && HostName[1] == 92 )
    v6 = HostName + 2;
  v8 = ldap_initW(v6, 0x185u);
  *a3 = v8;
  if ( !v8 )
  {
    LastError = LdapGetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = ldap_err2stringW(LastError);
      v12 = 15;
LABEL_32:
      v15 = (int)v6;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  invalue = 1;
  LastError = ldap_set_optionW(v8, 152, &invalue);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = ldap_err2stringW(LastError);
      v12 = 16;
      goto LABEL_32;
    }
LABEL_34:
    v16 = GmsapMapLdapErrorToNtStatus(LastError);
    if ( v16 < 0 )
    {
      if ( *a3 )
      {
        ldap_unbind(*a3);
        *a3 = 0;
      }
    }
    return (unsigned int)v16;
  }
  v13 = *a3;
  invalue = 1;
  LastError = ldap_set_optionW(v13, 150, &invalue);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = ldap_err2stringW(LastError);
      v12 = 17;
      goto LABEL_32;
    }
    goto LABEL_34;
  }
  v14 = *a3;
  invalue = 0;
  LastError = ldap_set_optionW(v14, 8, &invalue);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = ldap_err2stringW(LastError);
      v12 = 18;
      goto LABEL_32;
    }
    goto LABEL_34;
  }
  LastError = ldap_set_optionW(*a3, 59, &v17);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = ldap_err2stringW(LastError);
      v15 = v17;
      v12 = 19;
LABEL_33:
      WPP_SF_SlS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v11, v15, LastError, (__int64)v10);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v16 = 0;
  LastError = ldap_bind_sW(*a3, 0, 0, 0x486u);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = ldap_err2stringW(LastError);
      v12 = 20;
      goto LABEL_32;
    }
    goto LABEL_34;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180007378  mov     rax, rsp
0x18000737b  mov     [rax+10h], rdx
0x18000737f  push    rbx
0x180007380  push    rsi
0x180007381  push    rdi
0x180007382  push    r14
0x180007384  sub     rsp, 38h
0x180007388  mov     dword ptr [rax+28h], 0
0x18000738f  mov     r14, r8
0x180007392  mov     rsi, rcx
0x180007395  test    r8, r8
0x180007398  jnz     short loc_1800073A4
0x18000739a  mov     eax, 0C000000Dh
0x18000739f  jmp     loc_18000763B
0x1800073a4  test    rsi, rsi
0x1800073a7  jnz     short loc_1800073AE
0x1800073a9  mov     [r8], rsi
0x1800073ac  jmp     short loc_18000739A
0x1800073ae  cmp     word ptr [rcx], 5Ch ; '\'
0x1800073b2  jnz     short loc_1800073BF
0x1800073b4  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1800073b9  jnz     short loc_1800073BF
0x1800073bb  add     rsi, 4
0x1800073bf  mov     edx, 185h; PortNumber
0x1800073c4  mov     rcx, rsi; HostName
0x1800073c7  call    cs:__imp_ldap_initW
0x1800073ce  nop     dword ptr [rax+rax+00h]
0x1800073d3  mov     [r14], rax
0x1800073d6  test    rax, rax
0x1800073d9  jnz     short loc_180007422
0x1800073db  call    cs:__imp_LdapGetLastError
0x1800073e2  nop     dword ptr [rax+rax+00h]
0x1800073e7  mov     ebx, eax
0x1800073e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073f0  lea     rax, WPP_GLOBAL_Control
0x1800073f7  cmp     rcx, rax
0x1800073fa  jz      loc_180007611
0x180007400  test    byte ptr [rcx+1Ch], 2
0x180007404  jz      loc_180007611
0x18000740a  mov     ecx, ebx; err
0x18000740c  call    cs:__imp_ldap_err2stringW
0x180007413  nop     dword ptr [rax+rax+00h]
0x180007418  mov     edx, 0Fh
0x18000741d  jmp     loc_1800075F5
0x180007422  mov     edi, 1
0x180007427  lea     r8, [rsp+58h+invalue]; invalue
0x18000742f  mov     edx, 98h; option
0x180007434  mov     [rsp+58h+invalue], edi
0x18000743b  mov     rcx, rax; ld
0x18000743e  call    cs:__imp_ldap_set_optionW
0x180007445  nop     dword ptr [rax+rax+00h]
0x18000744a  mov     ebx, eax
0x18000744c  test    eax, eax
0x18000744e  jz      short loc_180007487
0x180007450  mov     rcx, cs:WPP_GLOBAL_Control
0x180007457  lea     rax, WPP_GLOBAL_Control
0x18000745e  cmp     rcx, rax
0x180007461  jz      loc_180007611
0x180007467  test    byte ptr [rcx+1Ch], 2
0x18000746b  jz      loc_180007611
0x180007471  mov     ecx, ebx; err
0x180007473  call    cs:__imp_ldap_err2stringW
0x18000747a  nop     dword ptr [rax+rax+00h]
0x18000747f  lea     edx, [rdi+0Fh]
0x180007482  jmp     loc_1800075F5
0x180007487  mov     rcx, [r14]; ld
0x18000748a  lea     r8, [rsp+58h+invalue]; invalue
0x180007492  mov     edx, 96h; option
0x180007497  mov     [rsp+58h+invalue], edi
0x18000749e  call    cs:__imp_ldap_set_optionW
0x1800074a5  nop     dword ptr [rax+rax+00h]
0x1800074aa  mov     ebx, eax
0x1800074ac  test    eax, eax
0x1800074ae  jz      short loc_1800074E9
0x1800074b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074b7  lea     rax, WPP_GLOBAL_Control
0x1800074be  cmp     rcx, rax
0x1800074c1  jz      loc_180007611
0x1800074c7  test    byte ptr [rcx+1Ch], 2
0x1800074cb  jz      loc_180007611
0x1800074d1  mov     ecx, ebx; err
0x1800074d3  call    cs:__imp_ldap_err2stringW
0x1800074da  nop     dword ptr [rax+rax+00h]
0x1800074df  mov     edx, 11h
0x1800074e4  jmp     loc_1800075F5
0x1800074e9  mov     rcx, [r14]; ld
0x1800074ec  lea     r8, [rsp+58h+invalue]; invalue
0x1800074f4  mov     edx, 8; option
0x1800074f9  mov     [rsp+58h+invalue], 0
0x180007504  call    cs:__imp_ldap_set_optionW
0x18000750b  nop     dword ptr [rax+rax+00h]
0x180007510  mov     ebx, eax
0x180007512  test    eax, eax
0x180007514  jz      short loc_18000754F
0x180007516  mov     rcx, cs:WPP_GLOBAL_Control
0x18000751d  lea     rax, WPP_GLOBAL_Control
0x180007524  cmp     rcx, rax
0x180007527  jz      loc_180007611
0x18000752d  test    byte ptr [rcx+1Ch], 2
0x180007531  jz      loc_180007611
0x180007537  mov     ecx, ebx; err
0x180007539  call    cs:__imp_ldap_err2stringW
0x180007540  nop     dword ptr [rax+rax+00h]
0x180007545  mov     edx, 12h
0x18000754a  jmp     loc_1800075F5
0x18000754f  mov     rcx, [r14]; ld
0x180007552  lea     r8, [rsp+58h+arg_8]; invalue
0x180007557  mov     edx, 3Bh ; ';'; option
0x18000755c  call    cs:__imp_ldap_set_optionW
0x180007563  nop     dword ptr [rax+rax+00h]
0x180007568  mov     ebx, eax
0x18000756a  test    eax, eax
0x18000756c  jz      short loc_1800075A9
0x18000756e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007575  lea     rax, WPP_GLOBAL_Control
0x18000757c  cmp     rcx, rax
0x18000757f  jz      loc_180007611
0x180007585  test    byte ptr [rcx+1Ch], 2
0x180007589  jz      loc_180007611
0x18000758f  mov     ecx, ebx; err
0x180007591  call    cs:__imp_ldap_err2stringW
0x180007598  nop     dword ptr [rax+rax+00h]
0x18000759d  mov     r9, [rsp+58h+arg_8]
0x1800075a2  mov     edx, 13h
0x1800075a7  jmp     short loc_1800075F8
0x1800075a9  mov     rcx, [r14]; ld
0x1800075ac  mov     r9d, 486h; method
0x1800075b2  xor     r8d, r8d; cred
0x1800075b5  xor     edx, edx; dn
0x1800075b7  xor     edi, edi
0x1800075b9  call    cs:__imp_ldap_bind_sW
0x1800075c0  nop     dword ptr [rax+rax+00h]
0x1800075c5  mov     ebx, eax
0x1800075c7  test    eax, eax
0x1800075c9  jz      short loc_180007639
0x1800075cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075d2  lea     rax, WPP_GLOBAL_Control
0x1800075d9  cmp     rcx, rax
0x1800075dc  jz      short loc_180007611
0x1800075de  test    byte ptr [rcx+1Ch], 2
0x1800075e2  jz      short loc_180007611
0x1800075e4  mov     ecx, ebx; err
0x1800075e6  call    cs:__imp_ldap_err2stringW
0x1800075ed  nop     dword ptr [rax+rax+00h]
0x1800075f2  lea     edx, [rdi+14h]
0x1800075f5  mov     r9, rsi
0x1800075f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075ff  mov     [rsp+58h+var_30], rax
0x180007604  mov     [rsp+58h+var_38], ebx
0x180007608  mov     rcx, [rcx+10h]
0x18000760c  call    WPP_SF_SlS
0x180007611  mov     ecx, ebx
0x180007613  call    GmsapMapLdapErrorToNtStatus
0x180007618  mov     edi, eax
0x18000761a  test    eax, eax
0x18000761c  jns     short loc_180007639
0x18000761e  mov     rcx, [r14]; ld
0x180007621  test    rcx, rcx
0x180007624  jz      short loc_180007639
0x180007626  call    cs:__imp_ldap_unbind
0x18000762d  nop     dword ptr [rax+rax+00h]
0x180007632  mov     qword ptr [r14], 0
0x180007639  mov     eax, edi
0x18000763b  add     rsp, 38h
0x18000763f  pop     r14
0x180007641  pop     rdi
0x180007642  pop     rsi
0x180007643  pop     rbx
0x180007644  retn
```
