# DoesOIDExist(ldap *,ushort *,ushort const *)

- ea: `0x18002b9a4`
- end: `0x18002bb44`
- name: `?DoesOIDExist@@YAHPEAUldap@@PEAGPEBG@Z`
- size: `416`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002bbb8`
- `0x18002bd08`
- `0x18002c6a4`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x18000e130`
- `0x18002b9a4`
- `0x18002bb4c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bb05`
- `WLDAP32!__imp_ldap_count_entries` at `0x18002badd`
- `WLDAP32!__imp_ldap_count_entries` at `0x18002badd`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002bb15`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002bb15`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002bac9`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002bac9`

## string_xrefs

- `0x18002ba61`: `msPKI-Cert-Template-OID`
- `0x18002ba35`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall DoesOIDExist(LDAP *ld, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rax
  unsigned __int64 v8; // r14
  unsigned __int16 *v9; // rdi
  struct ldapmsg *v10; // rax
  PLDAPMessage res[2]; // [rsp+48h] [rbp-50h] BYREF
  __int128 attrs; // [rsp+58h] [rbp-40h] BYREF
  struct l_timeval timeout; // [rsp+B0h] [rbp+18h] BYREF
  PWSTR filter; // [rsp+B8h] [rbp+20h] BYREF

  v6 = 0;
  timeout = 0;
  attrs = 0;
  res[0] = 0;
  filter = 0;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = v7 + 43;
    if ( (unsigned __int64)(v7 + 43) <= 0x10000 )
    {
      v10 = (struct ldapmsg *)CertAllocStringLen(0, (int)v7 + 42);
      v9 = (unsigned __int16 *)v10;
      res[1] = v10;
      if ( v10 )
      {
        StringCchCopyW((unsigned __int16 *)v10, v8, L"CN=OID,CN=Public Key Services,CN=Services,");
        StringCchCatW(v9, v8, a2);
        timeout = (struct l_timeval)120LL;
        *(_QWORD *)&attrs = L"msPKI-Cert-Template-OID";
        *((_QWORD *)&attrs + 1) = 0;
        if ( !FormatMessageUnicode(&filter, L"(%1!s!=%2!s!)", L"msPKI-Cert-Template-OID", a3)
          && !ldap_search_stW(ld, v9, 1u, filter, (PZPWSTR)&attrs, 0, &timeout, res)
          && ldap_count_entries(ld, res[0]) )
        {
          v6 = 1;
        }
      }
    }
    else
    {
      v9 = 0;
      CSPrintErrorLineFile(0x1C90336u, -2147024362);
    }
    if ( filter )
      LocalFree(filter);
    if ( res[0] )
      ldap_msgfree(res[0]);
    if ( v9 )
      CertFreeString(v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18002b9a4  mov     rax, rsp
0x18002b9a7  mov     [rax+8], rbx
0x18002b9ab  mov     [rax+10h], rsi
0x18002b9af  push    rdi
0x18002b9b0  push    r12
0x18002b9b2  push    r13
0x18002b9b4  push    r14
0x18002b9b6  push    r15
0x18002b9b8  sub     rsp, 70h
0x18002b9bc  mov     r12, r8
0x18002b9bf  mov     r15, rdx
0x18002b9c2  mov     r13, rcx
0x18002b9c5  xor     ebx, ebx
0x18002b9c7  mov     esi, ebx
0x18002b9c9  mov     [rax-58h], ebx
0x18002b9cc  mov     [rax+18h], rbx
0x18002b9d0  xorps   xmm0, xmm0
0x18002b9d3  movups  xmmword ptr [rax-40h], xmm0
0x18002b9d7  mov     [rax-50h], rbx
0x18002b9db  mov     [rax+20h], rbx
0x18002b9df  test    r8, r8
0x18002b9e2  jz      loc_18002BB28
0x18002b9e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b9ec  inc     rax
0x18002b9ef  cmp     [rdx+rax*2], bx
0x18002b9f3  jnz     short loc_18002B9EC
0x18002b9f5  lea     r14, [rax+2Bh]
0x18002b9f9  cmp     r14, 10000h
0x18002ba00  jbe     short loc_18002BA19
0x18002ba02  mov     rdi, rbx
0x18002ba05  mov     edx, 80070216h; int
0x18002ba0a  mov     ecx, 1C90336h; unsigned int
0x18002ba0f  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ba14  jmp     loc_18002BAF8
0x18002ba19  lea     edx, [r14-1]; unsigned int
0x18002ba1d  xor     ecx, ecx; Src
0x18002ba1f  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002ba24  mov     rdi, rax
0x18002ba27  mov     [rsp+98h+var_48], rax
0x18002ba2c  test    rax, rax
0x18002ba2f  jz      loc_18002BAF8
0x18002ba35  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18002ba3c  mov     rdx, r14; unsigned __int64
0x18002ba3f  mov     rcx, rax; unsigned __int16 *
0x18002ba42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ba47  mov     r8, r15; unsigned __int16 *
0x18002ba4a  mov     rdx, r14; unsigned __int64
0x18002ba4d  mov     rcx, rdi; unsigned __int16 *
0x18002ba50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002ba55  mov     qword ptr [rsp+98h+arg_10.tv_sec], 78h ; 'x'
0x18002ba61  lea     r8, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002ba68  mov     [rsp+98h+var_40], r8
0x18002ba6d  mov     [rsp+98h+var_38], rbx
0x18002ba72  mov     r9, r12
0x18002ba75  lea     rdx, a1S2S; "(%1!s!=%2!s!)"
0x18002ba7c  lea     rcx, [rsp+98h+filter]; unsigned __int16 **
0x18002ba84  call    ?FormatMessageUnicode@@YAJPEAPEAGPEAGZZ; FormatMessageUnicode(ushort * *,ushort *,...)
0x18002ba89  test    eax, eax
0x18002ba8b  jnz     short loc_18002BAF8
0x18002ba8d  lea     rax, [rsp+98h+var_50]
0x18002ba92  mov     [rsp+98h+res], rax; res
0x18002ba97  lea     rax, [rsp+98h+arg_10]
0x18002ba9f  mov     [rsp+98h+timeout], rax; timeout
0x18002baa4  mov     [rsp+98h+attrsonly], ebx; attrsonly
0x18002baa8  lea     rax, [rsp+98h+var_40]
0x18002baad  mov     [rsp+98h+attrs], rax; attrs
0x18002bab2  mov     r9, [rsp+98h+filter]; filter
0x18002baba  mov     r14d, 1
0x18002bac0  mov     r8d, r14d; scope
0x18002bac3  mov     rdx, rdi; base
0x18002bac6  mov     rcx, r13; ld
0x18002bac9  call    cs:__imp_ldap_search_stW
0x18002bacf  test    eax, eax
0x18002bad1  jz      short loc_18002BAD5
0x18002bad3  jmp     short loc_18002BAF8
0x18002bad5  mov     rdx, [rsp+98h+var_50]; res
0x18002bada  mov     rcx, r13; ld
0x18002badd  call    cs:__imp_ldap_count_entries
0x18002bae3  test    eax, eax
0x18002bae5  cmovnz  esi, r14d
0x18002bae9  mov     [rsp+98h+var_58], esi
0x18002baed  jmp     short loc_18002BAF8
0x18002baef  mov     esi, [rsp+98h+var_58]
0x18002baf3  mov     rdi, [rsp+98h+var_48]
0x18002baf8  mov     rcx, [rsp+98h+filter]; hMem
0x18002bb00  test    rcx, rcx
0x18002bb03  jz      short loc_18002BB0B
0x18002bb05  call    cs:__imp_LocalFree
0x18002bb0b  mov     rcx, [rsp+98h+var_50]; res
0x18002bb10  test    rcx, rcx
0x18002bb13  jz      short loc_18002BB1B
0x18002bb15  call    cs:__imp_ldap_msgfree
0x18002bb1b  test    rdi, rdi
0x18002bb1e  jz      short loc_18002BB28
0x18002bb20  mov     rcx, rdi; unsigned __int16 *
0x18002bb23  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002bb28  mov     eax, esi
0x18002bb2a  lea     r11, [rsp+98h+var_28]
0x18002bb2f  mov     rbx, [r11+30h]
0x18002bb33  mov     rsi, [r11+38h]
0x18002bb37  mov     rsp, r11
0x18002bb3a  pop     r15
0x18002bb3c  pop     r14
0x18002bb3e  pop     r13
0x18002bb40  pop     r12
0x18002bb42  pop     rdi
0x18002bb43  retn
```
