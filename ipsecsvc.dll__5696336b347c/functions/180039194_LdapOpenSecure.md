# LdapOpenSecure

- ea: `0x180039194`
- end: `0x1800393f7`
- name: `LdapOpenSecure`
- size: `611`
- prototype: `__int64 __fastcall(LPCWSTR DomainName, __int64, LDAP **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003f168`

## callees

- `0x180006f60`
- `0x18000c828`
- `0x18000e510`
- `0x180039194`

## import_xrefs

- `logoncli!DsGetDcNameW` at `0x1800391d8`
- `logoncli!DsGetDcNameW` at `0x1800391d8`
- `netutils!NetApiBufferFree` at `0x1800393bd`
- `netutils!NetApiBufferFree` at `0x1800393bd`
- `WLDAP32!__imp_ldap_unbind` at `0x1800393cf`
- `WLDAP32!__imp_ldap_unbind` at `0x1800393cf`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800392d1`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800392ef`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039305`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039319`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18003932f`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800392d1`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800392ef`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039305`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039319`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18003932f`
- `WLDAP32!__imp_LdapGetLastError` at `0x180039280`
- `WLDAP32!__imp_LdapGetLastError` at `0x180039280`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039288`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003934a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039288`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003934a`
- `WLDAP32!__imp_ldap_connect` at `0x18003933e`
- `WLDAP32!__imp_ldap_connect` at `0x18003933e`
- `WLDAP32!__imp_ldap_initW` at `0x180039272`
- `WLDAP32!__imp_ldap_initW` at `0x180039272`

## pseudocode

```c
__int64 __fastcall LdapOpenSecure(LPCWSTR DomainName, __int64 a2, LDAP **a3)
{
  LDAP *v4; // rdi
  unsigned __int16 *v5; // rsi
  DWORD DcNameW; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int16 *v10; // rax
  ULONG LastError; // eax
  ULONG v12; // eax
  LPVOID Buffer; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR v15; // [rsp+60h] [rbp+20h] BYREF
  __int64 invalue; // [rsp+78h] [rbp+38h] BYREF

  v15 = DomainName;
  v4 = 0;
  v5 = 0;
  invalue = 0;
  Buffer = 0;
  DcNameW = DsGetDcNameW(0, DomainName, 0, 0, 0x40000010u, (PDOMAIN_CONTROLLER_INFOW *)&Buffer);
  if ( DcNameW )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v8 = 15;
LABEL_5:
      v9 = DcNameW;
LABEL_31:
      WPP_SF_d(v7[2], v8, WPP_856782d8d58335846689e2d0985c0121_Traceguids, v9);
    }
  }
  else if ( Buffer && *(_QWORD *)Buffer )
  {
    v10 = IpsecAllocStr((unsigned __int16 *)(*(_QWORD *)Buffer + 4LL));
    v5 = v10;
    if ( v10 )
    {
      v4 = ldap_initW(v10, 0x185u);
      if ( v4 || (LastError = LdapGetLastError(), (DcNameW = LdapMapErrorToWin32(LastError)) == 0) )
      {
        invalue = 3;
        v12 = ldap_set_optionW(v4, 17, &invalue);
        invalue = 1;
        if ( !v12
          && (v12 = ldap_set_optionW(v4, 150, &invalue)) == 0
          && (v12 = ldap_set_optionW(v4, 149, &invalue)) == 0
          && (v12 = ldap_set_optionW(v4, 59, &v15)) == 0
          && (v12 = ldap_set_optionW(v4, 152, &invalue)) == 0
          && (v12 = ldap_connect(v4, 0)) == 0
          || (DcNameW = LdapMapErrorToWin32(v12)) == 0 )
        {
          *a3 = v4;
          goto LABEL_32;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v8 = 19;
          goto LABEL_5;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v8 = 18;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v9 = 14;
      DcNameW = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = 17;
        goto LABEL_31;
      }
    }
  }
  else
  {
    v9 = 14;
    DcNameW = 14;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v8 = 16;
      goto LABEL_31;
    }
  }
LABEL_32:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( DcNameW )
  {
    if ( v4 )
      ldap_unbind(v4);
    if ( v5 )
      IpsecFreeMem(v5);
  }
  return DcNameW;
}

```

## disassembly

```asm
0x180039194  mov     r11, rsp
0x180039197  mov     [r11+10h], rbx
0x18003919b  mov     [r11+18h], rsi
0x18003919f  mov     [r11+8], rcx
0x1800391a3  push    rbp
0x1800391a4  push    rdi
0x1800391a5  push    r14
0x1800391a7  mov     rbp, rsp
0x1800391aa  sub     rsp, 40h
0x1800391ae  lea     rax, [rbp+Buffer]
0x1800391b2  mov     r14, r8
0x1800391b5  mov     rdx, rcx; DomainName
0x1800391b8  mov     [r11-30h], rax
0x1800391bc  xor     edi, edi
0x1800391be  mov     [rsp+40h+Flags], 40000010h; Flags
0x1800391c6  xor     esi, esi
0x1800391c8  mov     [rbp+invalue], rdi
0x1800391cc  xor     r9d, r9d; SiteName
0x1800391cf  mov     [rbp+Buffer], rsi
0x1800391d3  xor     r8d, r8d; DomainGuid
0x1800391d6  xor     ecx, ecx; ComputerName
0x1800391d8  call    cs:__imp_DsGetDcNameW
0x1800391de  mov     ebx, eax
0x1800391e0  test    eax, eax
0x1800391e2  jz      short loc_180039210
0x1800391e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391eb  lea     rax, WPP_GLOBAL_Control
0x1800391f2  cmp     rcx, rax
0x1800391f5  jz      loc_1800393B4
0x1800391fb  test    byte ptr [rcx+1Ch], 10h
0x1800391ff  jz      loc_1800393B4
0x180039205  lea     edx, [rdi+0Fh]
0x180039208  mov     r9d, ebx
0x18003920b  jmp     loc_1800393A4
0x180039210  mov     rcx, [rbp+Buffer]
0x180039214  test    rcx, rcx
0x180039217  jz      loc_18003937E
0x18003921d  mov     rcx, [rcx]
0x180039220  test    rcx, rcx
0x180039223  jz      loc_18003937E
0x180039229  add     rcx, 4; unsigned __int16 *
0x18003922d  call    IpsecAllocStr
0x180039232  mov     rsi, rax
0x180039235  test    rax, rax
0x180039238  jnz     short loc_18003926A
0x18003923a  lea     r9d, [rax+0Eh]
0x18003923e  mov     ebx, r9d
0x180039241  mov     rcx, cs:WPP_GLOBAL_Control
0x180039248  lea     rax, WPP_GLOBAL_Control
0x18003924f  cmp     rcx, rax
0x180039252  jz      loc_1800393B4
0x180039258  test    byte ptr [rcx+1Ch], 10h
0x18003925c  jz      loc_1800393B4
0x180039262  lea     edx, [rsi+11h]
0x180039265  jmp     loc_1800393A4
0x18003926a  mov     edx, 185h; PortNumber
0x18003926f  mov     rcx, rax; HostName
0x180039272  call    cs:__imp_ldap_initW
0x180039278  mov     rdi, rax
0x18003927b  test    rax, rax
0x18003927e  jnz     short loc_1800392BD
0x180039280  call    cs:__imp_LdapGetLastError
0x180039286  mov     ecx, eax; LdapError
0x180039288  call    cs:__imp_LdapMapErrorToWin32
0x18003928e  mov     ebx, eax
0x180039290  test    eax, eax
0x180039292  jz      short loc_1800392BD
0x180039294  mov     rcx, cs:WPP_GLOBAL_Control
0x18003929b  lea     rax, WPP_GLOBAL_Control
0x1800392a2  cmp     rcx, rax
0x1800392a5  jz      loc_1800393B4
0x1800392ab  test    byte ptr [rcx+1Ch], 10h
0x1800392af  jz      loc_1800393B4
0x1800392b5  lea     edx, [rdi+12h]
0x1800392b8  jmp     loc_180039208
0x1800392bd  lea     r8, [rbp+invalue]; invalue
0x1800392c1  mov     [rbp+invalue], 3
0x1800392c9  mov     edx, 11h; option
0x1800392ce  mov     rcx, rdi; ld
0x1800392d1  call    cs:__imp_ldap_set_optionW
0x1800392d7  mov     [rbp+invalue], 1
0x1800392df  test    eax, eax
0x1800392e1  jnz     short loc_180039348
0x1800392e3  lea     r8, [rbp+invalue]; invalue
0x1800392e7  mov     edx, 96h; option
0x1800392ec  mov     rcx, rdi; ld
0x1800392ef  call    cs:__imp_ldap_set_optionW
0x1800392f5  test    eax, eax
0x1800392f7  jnz     short loc_180039348
0x1800392f9  lea     r8, [rbp+invalue]; invalue
0x1800392fd  mov     edx, 95h; option
0x180039302  mov     rcx, rdi; ld
0x180039305  call    cs:__imp_ldap_set_optionW
0x18003930b  test    eax, eax
0x18003930d  jnz     short loc_180039348
0x18003930f  lea     r8, [rbp+arg_0]; invalue
0x180039313  mov     rcx, rdi; ld
0x180039316  lea     edx, [rax+3Bh]; option
0x180039319  call    cs:__imp_ldap_set_optionW
0x18003931f  test    eax, eax
0x180039321  jnz     short loc_180039348
0x180039323  lea     r8, [rbp+invalue]; invalue
0x180039327  mov     edx, 98h; option
0x18003932c  mov     rcx, rdi; ld
0x18003932f  call    cs:__imp_ldap_set_optionW
0x180039335  test    eax, eax
0x180039337  jnz     short loc_180039348
0x180039339  xor     edx, edx; timeout
0x18003933b  mov     rcx, rdi; ld
0x18003933e  call    cs:__imp_ldap_connect
0x180039344  test    eax, eax
0x180039346  jz      short loc_180039379
0x180039348  mov     ecx, eax; LdapError
0x18003934a  call    cs:__imp_LdapMapErrorToWin32
0x180039350  mov     ebx, eax
0x180039352  test    eax, eax
0x180039354  jz      short loc_180039379
0x180039356  mov     rcx, cs:WPP_GLOBAL_Control
0x18003935d  lea     rax, WPP_GLOBAL_Control
0x180039364  cmp     rcx, rax
0x180039367  jz      short loc_1800393B4
0x180039369  test    byte ptr [rcx+1Ch], 10h
0x18003936d  jz      short loc_1800393B4
0x18003936f  mov     edx, 13h
0x180039374  jmp     loc_180039208
0x180039379  mov     [r14], rdi
0x18003937c  jmp     short loc_1800393B4
0x18003937e  mov     r9d, 0Eh
0x180039384  mov     ebx, r9d
0x180039387  mov     rcx, cs:WPP_GLOBAL_Control
0x18003938e  lea     rax, WPP_GLOBAL_Control
0x180039395  cmp     rcx, rax
0x180039398  jz      short loc_1800393B4
0x18003939a  test    byte ptr [rcx+1Ch], 10h
0x18003939e  jz      short loc_1800393B4
0x1800393a0  lea     edx, [r9+2]
0x1800393a4  mov     rcx, [rcx+10h]
0x1800393a8  lea     r8, WPP_856782d8d58335846689e2d0985c0121_Traceguids
0x1800393af  call    WPP_SF_d
0x1800393b4  mov     rcx, [rbp+Buffer]; Buffer
0x1800393b8  test    rcx, rcx
0x1800393bb  jz      short loc_1800393C3
0x1800393bd  call    cs:__imp_NetApiBufferFree
0x1800393c3  test    ebx, ebx
0x1800393c5  jz      short loc_1800393E2
0x1800393c7  test    rdi, rdi
0x1800393ca  jz      short loc_1800393D5
0x1800393cc  mov     rcx, rdi; ld
0x1800393cf  call    cs:__imp_ldap_unbind
0x1800393d5  test    rsi, rsi
0x1800393d8  jz      short loc_1800393E2
0x1800393da  mov     rcx, rsi; lpMem
0x1800393dd  call    IpsecFreeMem
0x1800393e2  mov     rsi, [rsp+40h+arg_10]
0x1800393e7  mov     eax, ebx
0x1800393e9  mov     rbx, [rsp+40h+arg_8]
0x1800393ee  add     rsp, 40h
0x1800393f2  pop     r14
0x1800393f4  pop     rdi
0x1800393f5  pop     rbp
0x1800393f6  retn
```
