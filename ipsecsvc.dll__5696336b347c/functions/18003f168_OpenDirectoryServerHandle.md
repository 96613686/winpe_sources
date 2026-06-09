# OpenDirectoryServerHandle

- ea: `0x18003f168`
- end: `0x18003f2c6`
- name: `OpenDirectoryServerHandle`
- size: `350`
- prototype: `__int64 __fastcall(LPCWSTR DomainName)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002bb44`
- `0x18002c1ec`

## callees

- `0x18000e510`
- `0x180039024`
- `0x180039194`
- `0x18003eaa8`
- `0x18003f09c`
- `0x18003f168`
- `0x18004d05e`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003f253`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003f253`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18003f24b`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18003f24b`

## pseudocode

```c
__int64 __fastcall OpenDirectoryServerHandle(WCHAR *DomainName, __int64 a2, LDAP **a3)
{
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  WCHAR *v10; // r8
  ULONG v11; // eax
  WCHAR cred[2]; // [rsp+20h] [rbp-58h] BYREF
  int v14; // [rsp+24h] [rbp-54h]
  int v15; // [rsp+54h] [rbp-24h]
  const wchar_t *v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+60h] [rbp-18h]

  *a3 = 0;
  LOBYTE(v5) = IsValuesOverridenUsingRegkey((__int64)DomainName);
  if ( v5 )
  {
    v7 = LdapOpen(DomainName, v6, a3);
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v9 = 10;
LABEL_18:
        WPP_SF_d(v8[2], v9, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v7);
        goto LABEL_19;
      }
      goto LABEL_19;
    }
    v10 = 0;
LABEL_12:
    v11 = ldap_bind_sW(*a3, 0, v10, 0x486u);
    v7 = LdapMapErrorToWin32(v11);
    if ( v7 == 1323 )
    {
      v7 = 5;
    }
    else if ( !v7 )
    {
      return 0;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = 12;
      goto LABEL_18;
    }
    goto LABEL_19;
  }
  v7 = LdapOpenSecure(DomainName, v6, a3);
  if ( !v7 )
  {
    memset_0(cred, 0, 0x48u);
    wcscpy(cred, L"Ȁ");
    v16 = L"Kerberos";
    v10 = cred;
    v14 = 72;
    v15 = 2;
    v17 = 8;
    goto LABEL_12;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v9 = 11;
    goto LABEL_18;
  }
LABEL_19:
  if ( *a3 )
  {
    CloseDirectoryServerHandle(*a3);
    *a3 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18003f168  mov     [rsp+arg_0], rbx
0x18003f16d  push    rdi
0x18003f16e  sub     rsp, 70h
0x18003f172  mov     rdi, r8
0x18003f175  mov     qword ptr [r8], 0
0x18003f17c  mov     rbx, rcx
0x18003f17f  call    IsValuesOverridenUsingRegkey
0x18003f184  mov     r8, rdi
0x18003f187  mov     rcx, rbx; DomainName
0x18003f18a  test    eax, eax
0x18003f18c  jz      short loc_18003F1C9
0x18003f18e  call    LdapOpen
0x18003f193  mov     ebx, eax
0x18003f195  test    eax, eax
0x18003f197  jz      short loc_18003F1C4
0x18003f199  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1a0  lea     rax, WPP_GLOBAL_Control
0x18003f1a7  cmp     rcx, rax
0x18003f1aa  jz      loc_18003F29E
0x18003f1b0  test    byte ptr [rcx+1Ch], 10h
0x18003f1b4  jz      loc_18003F29E
0x18003f1ba  mov     edx, 0Ah
0x18003f1bf  jmp     loc_18003F28B
0x18003f1c4  xor     r8d, r8d
0x18003f1c7  jmp     short loc_18003F240
0x18003f1c9  call    LdapOpenSecure
0x18003f1ce  mov     ebx, eax
0x18003f1d0  test    eax, eax
0x18003f1d2  jz      short loc_18003F1FF
0x18003f1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1db  lea     rax, WPP_GLOBAL_Control
0x18003f1e2  cmp     rcx, rax
0x18003f1e5  jz      loc_18003F29E
0x18003f1eb  test    byte ptr [rcx+1Ch], 10h
0x18003f1ef  jz      loc_18003F29E
0x18003f1f5  mov     edx, 0Bh
0x18003f1fa  jmp     loc_18003F28B
0x18003f1ff  mov     ebx, 48h ; 'H'
0x18003f204  lea     rcx, [rsp+78h+cred]; void *
0x18003f209  mov     r8d, ebx; Size
0x18003f20c  xor     edx, edx; Val
0x18003f20e  call    memset_0
0x18003f213  lea     rax, aKerberos; "Kerberos"
0x18003f21a  mov     dword ptr [rsp+78h+cred], 200h
0x18003f222  mov     [rsp+78h+var_20], rax
0x18003f227  lea     r8, [rsp+78h+cred]; cred
0x18003f22c  mov     [rsp+78h+var_54], ebx
0x18003f230  mov     [rsp+78h+var_24], 2
0x18003f238  mov     [rsp+78h+var_18], 8
0x18003f240  mov     rcx, [rdi]; ld
0x18003f243  mov     r9d, 486h; method
0x18003f249  xor     edx, edx; dn
0x18003f24b  call    cs:__imp_ldap_bind_sW
0x18003f251  mov     ecx, eax; LdapError
0x18003f253  call    cs:__imp_LdapMapErrorToWin32
0x18003f259  mov     ebx, eax
0x18003f25b  cmp     eax, 52Bh
0x18003f260  jnz     short loc_18003F269
0x18003f262  mov     ebx, 5
0x18003f267  jmp     short loc_18003F26D
0x18003f269  test    ebx, ebx
0x18003f26b  jz      short loc_18003F2B6
0x18003f26d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f274  lea     rax, WPP_GLOBAL_Control
0x18003f27b  cmp     rcx, rax
0x18003f27e  jz      short loc_18003F29E
0x18003f280  test    byte ptr [rcx+1Ch], 10h
0x18003f284  jz      short loc_18003F29E
0x18003f286  mov     edx, 0Ch
0x18003f28b  mov     rcx, [rcx+10h]
0x18003f28f  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003f296  mov     r9d, ebx
0x18003f299  call    WPP_SF_d
0x18003f29e  mov     rcx, [rdi]
0x18003f2a1  test    rcx, rcx
0x18003f2a4  jz      short loc_18003F2B2
0x18003f2a6  call    CloseDirectoryServerHandle
0x18003f2ab  mov     qword ptr [rdi], 0
0x18003f2b2  mov     eax, ebx
0x18003f2b4  jmp     short loc_18003F2B8
0x18003f2b6  xor     eax, eax
0x18003f2b8  mov     rbx, [rsp+78h+arg_0]
0x18003f2c0  add     rsp, 70h
0x18003f2c4  pop     rdi
0x18003f2c5  retn
```
