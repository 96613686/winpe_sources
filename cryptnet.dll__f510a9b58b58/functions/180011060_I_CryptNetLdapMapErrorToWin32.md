# I_CryptNetLdapMapErrorToWin32

- ea: `0x180011060`
- end: `0x18001112e`
- name: `I_CryptNetLdapMapErrorToWin32`
- size: `206`
- prototype: `ULONG __fastcall(LDAP *ld, ULONG)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011134`
- `0x180019b00`
- `0x18001d22c`

## callees

- `0x18000bb78`
- `0x180011060`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180011127`
- `WLDAP32!__imp_ldap_get_option` at `0x180011092`
- `WLDAP32!__imp_ldap_get_option` at `0x1800110f2`
- `WLDAP32!__imp_ldap_get_option` at `0x180011092`
- `WLDAP32!__imp_ldap_get_option` at `0x1800110f2`
- `WLDAP32!__imp_ldap_memfreeA` at `0x180011115`
- `WLDAP32!__imp_ldap_memfreeA` at `0x180011115`

## string_xrefs

- `0x1800110fd`: `CRYPTNET.DLL --> LdapError: 0x%x <%s>\n`

## pseudocode

```c
ULONG __fastcall I_CryptNetLdapMapErrorToWin32(LDAP *ld, ULONG a2)
{
  PCHAR v4; // rax
  __int64 v5; // rdx
  char near **v6; // rcx
  __int64 v7; // r8
  char near **v8; // rax
  int outvalue; // [rsp+30h] [rbp+8h] BYREF
  PCHAR Block; // [rsp+40h] [rbp+18h] BYREF

  if ( ld )
  {
    Block = 0;
    outvalue = 0;
    if ( !ldap_get_option(ld, 51, &Block) )
    {
      v4 = Block;
      if ( Block )
      {
        v5 = 128;
        v6 = &g_rgszLdapServerError;
        v7 = 2147483646;
        do
        {
          if ( !v7 )
            break;
          if ( !*v4 )
            break;
          *(_BYTE *)v6 = *v4++;
          v6 = (char near **)((char *)v6 + 1);
          --v7;
          --v5;
        }
        while ( v5 );
        v8 = (char near **)((char *)v6 - 1);
        if ( v5 )
          v8 = v6;
        *(_BYTE *)v8 = 0;
      }
    }
    ldap_get_option(ld, 52, &outvalue);
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> LdapError: 0x%x <%s>\n", a2, Block);
    if ( Block )
      ldap_memfreeA(Block);
  }
  return LdapMapErrorToWin32(a2);
}

```

## disassembly

```asm
0x180011060  mov     rax, rsp
0x180011063  mov     [rax+10h], rbx
0x180011067  push    rdi
0x180011068  sub     rsp, 20h
0x18001106c  mov     edi, edx
0x18001106e  mov     rbx, rcx
0x180011071  test    rcx, rcx
0x180011074  jz      loc_18001111B
0x18001107a  lea     r8, [rax+18h]; outvalue
0x18001107e  mov     qword ptr [rax+18h], 0
0x180011086  mov     edx, 33h ; '3'; option
0x18001108b  mov     dword ptr [rax+8], 0
0x180011092  call    cs:__imp_ldap_get_option
0x180011098  test    eax, eax
0x18001109a  jnz     short loc_1800110E5
0x18001109c  mov     rax, [rsp+28h+Block]
0x1800110a1  test    rax, rax
0x1800110a4  jz      short loc_1800110E5
0x1800110a6  mov     edx, 80h
0x1800110ab  lea     rcx, ?g_rgszLdapServerError@@3PADA; char near * g_rgszLdapServerError
0x1800110b2  mov     r8d, 7FFFFFFEh
0x1800110b8  test    r8, r8
0x1800110bb  jz      short loc_1800110D7
0x1800110bd  mov     r9b, [rax]
0x1800110c0  test    r9b, r9b
0x1800110c3  jz      short loc_1800110D7
0x1800110c5  mov     [rcx], r9b
0x1800110c8  inc     rax
0x1800110cb  inc     rcx
0x1800110ce  dec     r8
0x1800110d1  sub     rdx, 1
0x1800110d5  jnz     short loc_1800110B8
0x1800110d7  test    rdx, rdx
0x1800110da  lea     rax, [rcx-1]
0x1800110de  cmovnz  rax, rcx
0x1800110e2  mov     byte ptr [rax], 0
0x1800110e5  lea     r8, [rsp+28h+outvalue]; outvalue
0x1800110ea  mov     edx, 34h ; '4'; option
0x1800110ef  mov     rcx, rbx; ld
0x1800110f2  call    cs:__imp_ldap_get_option
0x1800110f8  mov     r8, [rsp+28h+Block]
0x1800110fd  lea     rcx, aCryptnetDllLda; "CRYPTNET.DLL --> LdapError: 0x%x <%s>\n"
0x180011104  mov     edx, edi
0x180011106  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18001110b  mov     rcx, [rsp+28h+Block]; Block
0x180011110  test    rcx, rcx
0x180011113  jz      short loc_18001111B
0x180011115  call    cs:__imp_ldap_memfreeA
0x18001111b  mov     ecx, edi
0x18001111d  mov     rbx, [rsp+28h+arg_8]
0x180011122  add     rsp, 20h
0x180011126  pop     rdi
0x180011127  jmp     cs:__imp_LdapMapErrorToWin32
```
