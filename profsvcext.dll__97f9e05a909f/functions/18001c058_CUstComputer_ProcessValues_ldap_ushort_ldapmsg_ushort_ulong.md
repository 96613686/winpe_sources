# CUstComputer::_ProcessValues(ldap *,ushort *,ldapmsg *,ushort * * *,ulong &)

- ea: `0x18001c058`
- end: `0x18001c27e`
- name: `?_ProcessValues@CUstComputer@@KAJPEAUldap@@PEAGPEAUldapmsg@@PEAPEAPEAGAEAK@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, struct ldapmsg *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001be64`

## callees

- `0x18000baec`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001b008`
- `0x18001c058`
- `0x18001d264`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001c115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001c19b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001c115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001c19b`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001c096`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001c096`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001c0c8`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001c0c8`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18001c122`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18001c1ac`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18001c122`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18001c1ac`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18001c07a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18001c07a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18001c265`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18001c265`

## string_xrefs

- `0x18001c191`: `msDS-IsPrimaryComputerFor`

## pseudocode

```c
__int64 __fastcall CUstComputer::_ProcessValues(
        struct ldap *a1,
        unsigned __int16 *a2,
        struct ldapmsg *a3,
        unsigned __int16 ***a4,
        unsigned int *a5)
{
  signed int StringCopy; // ebx
  PWCHAR *valuesW; // rdi
  ULONG LastError; // eax
  ULONG v10; // esi
  signed int v11; // eax
  ULONG v12; // eax
  ULONG v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // kr00_8
  unsigned __int16 **v16; // rax
  __int64 v17; // r9
  __int64 v18; // r15
  __int64 i; // rsi

  StringCopy = 0;
  valuesW = ldap_get_valuesW(a1, a3, a2);
  if ( valuesW )
    goto LABEL_10;
  LastError = LdapGetLastError();
  v10 = LastError;
  if ( !LastError )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ab0185983553356c12180ac14bccd298_Traceguids, LastError);
  }
  v11 = LdapMapErrorToWin32(v10);
  StringCopy = v11;
  if ( v11 > 0 )
    StringCopy = (unsigned __int16)v11 | 0x80070000;
  if ( StringCopy >= 0 )
  {
LABEL_10:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ab0185983553356c12180ac14bccd298_Traceguids, a2);
    }
    if ( lstrcmpiW(a2, L"cn") )
    {
      if ( !lstrcmpiW(a2, L"msDS-IsPrimaryComputerFor") )
      {
        v13 = ldap_count_valuesW(valuesW);
        *a5 = v13;
        if ( !v13 )
          goto LABEL_28;
        v15 = v13;
        v14 = 8LL * v13;
        if ( !is_mul_ok(v15, 8u) )
          v14 = -1;
        v16 = (unsigned __int16 **)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
        *a4 = v16;
        if ( v16
          || (StringCopy = -2147024882, WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control)
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_28:
          v18 = (__int64)*a4;
          for ( i = 0; StringCopy >= 0 && (unsigned int)i < *a5; i = (unsigned int)(i + 1) )
          {
            StringCopy = CUstUtil::CreateStringCopy(valuesW[i], (unsigned __int16 **)(v18 + 8 * i));
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_ab0185983553356c12180ac14bccd298_Traceguids,
                valuesW[i]);
            }
          }
        }
        else
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v17);
        }
      }
    }
    else
    {
      v12 = ldap_count_valuesW(valuesW);
      if ( v12 == 1 )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ab0185983553356c12180ac14bccd298_Traceguids, *valuesW);
        }
      }
      else if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v12);
      }
    }
    if ( valuesW )
      ldap_value_freeW(valuesW);
  }
  return (unsigned int)StringCopy;
}

```

## disassembly

```asm
0x18001c058  push    rbx
0x18001c05a  push    rbp
0x18001c05b  push    rsi
0x18001c05c  push    rdi
0x18001c05d  push    r12
0x18001c05f  push    r13
0x18001c061  push    r14
0x18001c063  push    r15
0x18001c065  sub     rsp, 28h
0x18001c069  mov     rax, r8
0x18001c06c  mov     rbp, rdx
0x18001c06f  mov     r8, rdx; attr
0x18001c072  mov     r15, r9
0x18001c075  mov     rdx, rax; entry
0x18001c078  xor     ebx, ebx
0x18001c07a  call    cs:__imp_ldap_get_valuesW
0x18001c080  lea     r12, WPP_GLOBAL_Control
0x18001c087  mov     rdi, rax
0x18001c08a  lea     r13, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001c091  test    rax, rax
0x18001c094  jnz     short loc_18001C0E5
0x18001c096  call    cs:__imp_LdapGetLastError
0x18001c09c  mov     esi, eax
0x18001c09e  test    eax, eax
0x18001c0a0  jz      short loc_18001C0E5
0x18001c0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0a9  cmp     rcx, r12
0x18001c0ac  jz      short loc_18001C0C6
0x18001c0ae  test    byte ptr [rcx+1Ch], 1
0x18001c0b2  jz      short loc_18001C0C6
0x18001c0b4  mov     rcx, [rcx+10h]
0x18001c0b8  lea     edx, [rbx+13h]
0x18001c0bb  mov     r9d, eax
0x18001c0be  mov     r8, r13
0x18001c0c1  call    WPP_SF_d
0x18001c0c6  mov     ecx, esi; LdapError
0x18001c0c8  call    cs:__imp_LdapMapErrorToWin32
0x18001c0ce  mov     ebx, eax
0x18001c0d0  test    eax, eax
0x18001c0d2  jle     short loc_18001C0DD
0x18001c0d4  movzx   ebx, ax
0x18001c0d7  or      ebx, 80070000h
0x18001c0dd  test    ebx, ebx
0x18001c0df  js      loc_18001C26B
0x18001c0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0ec  cmp     rcx, r12
0x18001c0ef  jz      short loc_18001C10B
0x18001c0f1  test    byte ptr [rcx+1Ch], 2
0x18001c0f5  jz      short loc_18001C10B
0x18001c0f7  mov     rcx, [rcx+10h]
0x18001c0fb  mov     edx, 14h
0x18001c100  mov     r9, rbp
0x18001c103  mov     r8, r13
0x18001c106  call    WPP_SF_S
0x18001c10b  lea     rdx, aCn; "cn"
0x18001c112  mov     rcx, rbp; lpString1
0x18001c115  call    cs:__imp_lstrcmpiW
0x18001c11b  test    eax, eax
0x18001c11d  jnz     short loc_18001C191
0x18001c11f  mov     rcx, rdi; vals
0x18001c122  call    cs:__imp_ldap_count_valuesW
0x18001c128  cmp     eax, 1
0x18001c12b  jnz     short loc_18001C15E
0x18001c12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c134  cmp     rcx, r12
0x18001c137  jz      loc_18001C25D
0x18001c13d  test    byte ptr [rcx+1Ch], 2
0x18001c141  jz      loc_18001C25D
0x18001c147  mov     r9, [rdi]
0x18001c14a  lea     edx, [rax+14h]
0x18001c14d  mov     rcx, [rcx+10h]
0x18001c151  mov     r8, r13
0x18001c154  call    WPP_SF_S
0x18001c159  jmp     loc_18001C25D
0x18001c15e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c165  cmp     rcx, r12
0x18001c168  jz      loc_18001C25D
0x18001c16e  test    byte ptr [rcx+1Ch], 1
0x18001c172  jz      loc_18001C25D
0x18001c178  mov     rcx, [rcx+10h]
0x18001c17c  mov     edx, 16h
0x18001c181  mov     r9d, eax
0x18001c184  mov     r8, r13
0x18001c187  call    WPP_SF_d
0x18001c18c  jmp     loc_18001C25D
0x18001c191  lea     rdx, aMsdsIsprimaryc; "msDS-IsPrimaryComputerFor"
0x18001c198  mov     rcx, rbp; lpString1
0x18001c19b  call    cs:__imp_lstrcmpiW
0x18001c1a1  test    eax, eax
0x18001c1a3  jnz     loc_18001C25D
0x18001c1a9  mov     rcx, rdi; vals
0x18001c1ac  call    cs:__imp_ldap_count_valuesW
0x18001c1b2  mov     r14, [rsp+68h+arg_20]
0x18001c1ba  mov     [r14], eax
0x18001c1bd  test    eax, eax
0x18001c1bf  jz      short loc_18001C215
0x18001c1c1  mov     ecx, eax
0x18001c1c3  mov     eax, 8
0x18001c1c8  mul     rcx
0x18001c1cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c1d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c1d9  cmovb   rax, rcx
0x18001c1dd  mov     rcx, rax; unsigned __int64
0x18001c1e0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c1e5  mov     [r15], rax
0x18001c1e8  test    rax, rax
0x18001c1eb  jnz     short loc_18001C215
0x18001c1ed  mov     ebx, 8007000Eh
0x18001c1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1f9  cmp     rcx, r12
0x18001c1fc  jz      short loc_18001C215
0x18001c1fe  test    byte ptr [rcx+1Ch], 1
0x18001c202  jz      short loc_18001C215
0x18001c204  mov     rcx, [rcx+10h]
0x18001c208  lea     edx, [rax+17h]
0x18001c20b  mov     r8, r13
0x18001c20e  call    WPP_SF_
0x18001c213  jmp     short loc_18001C25D
0x18001c215  mov     r15, [r15]
0x18001c218  xor     esi, esi
0x18001c21a  jmp     short loc_18001C259
0x18001c21c  cmp     esi, [r14]
0x18001c21f  jnb     short loc_18001C25D
0x18001c221  mov     rcx, [rdi+rsi*8]; unsigned __int16 *
0x18001c225  lea     rdx, [r15+rsi*8]; unsigned __int16 **
0x18001c229  call    ?CreateStringCopy@CUstUtil@@SAJPEAGPEAPEAG@Z; CUstUtil::CreateStringCopy(ushort *,ushort * *)
0x18001c22e  mov     ebx, eax
0x18001c230  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c237  cmp     rcx, r12
0x18001c23a  jz      short loc_18001C257
0x18001c23c  test    byte ptr [rcx+1Ch], 2
0x18001c240  jz      short loc_18001C257
0x18001c242  mov     r9, [rdi+rsi*8]
0x18001c246  mov     edx, 18h
0x18001c24b  mov     rcx, [rcx+10h]
0x18001c24f  mov     r8, r13
0x18001c252  call    WPP_SF_S
0x18001c257  inc     esi
0x18001c259  test    ebx, ebx
0x18001c25b  jns     short loc_18001C21C
0x18001c25d  test    rdi, rdi
0x18001c260  jz      short loc_18001C26B
0x18001c262  mov     rcx, rdi; vals
0x18001c265  call    cs:__imp_ldap_value_freeW
0x18001c26b  mov     eax, ebx
0x18001c26d  add     rsp, 28h
0x18001c271  pop     r15
0x18001c273  pop     r14
0x18001c275  pop     r13
0x18001c277  pop     r12
0x18001c279  pop     rdi
0x18001c27a  pop     rsi
0x18001c27b  pop     rbp
0x18001c27c  pop     rbx
0x18001c27d  retn
```
