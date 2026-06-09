# CAOIDGetLdapURL

- ea: `0x18002cb60`
- end: `0x18002ccf8`
- name: `CAOIDGetLdapURL`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005944`
- `0x180008400`
- `0x180008610`
- `0x18000e52c`
- `0x180012680`
- `0x18002bb4c`
- `0x18002cb60`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002cc85`
- `msvcrt!wcsrchr` at `0x18002cc85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ccc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ccc1`
- `WLDAP32!__imp_ldap_unbind` at `0x18002ccdc`
- `WLDAP32!__imp_ldap_unbind` at `0x18002ccdc`

## string_xrefs

- `0x18002cc4c`: `msPKI-Cert-Template-OID`
- `0x18002cc1e`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CAOIDGetLdapURL(int a1, __int64 a2, wchar_t **a3)
{
  LDAP *v3; // rdi
  unsigned __int16 *v4; // rsi
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  int v9; // edx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  wchar_t *v13; // rcx
  unsigned __int16 *v15; // [rsp+60h] [rbp-10h] BYREF
  wchar_t *Str; // [rsp+B0h] [rbp+40h] BYREF
  struct ldap *v17; // [rsp+B8h] [rbp+48h] BYREF

  v3 = 0;
  Str = 0;
  v4 = 0;
  v17 = 0;
  v15 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = 135594806;
LABEL_3:
    v9 = v7;
LABEL_4:
    CSPrintErrorLineFile(v8, v9);
    goto LABEL_16;
  }
  v10 = myTimeOutRobustLdapBind(&v17);
  v7 = v10;
  if ( v10 )
  {
    CSPrintErrorLineFileData2(0, 0x81E0336u, v10, -2147023541);
    v3 = v17;
  }
  else
  {
    v3 = v17;
    v11 = CAGetAuthoritativeDomainDn(v17, 0, &v15);
    v7 = v11;
    if ( v11 )
    {
      CSPrintErrorLineFile(0x8230336u, v11);
      v4 = v15;
    }
    else
    {
      v4 = v15;
      v12 = FormatMessageUnicode(
              &Str,
              L"ldap:///%1!s!%2!s!?%3!s!,%4!s!,%5!s!,%6!s!,%7!s!?one?%8!s!=%9!d!",
              L"CN=OID,CN=Public Key Services,CN=Services,",
              v15,
              L"flags",
              L"msPKI-Cert-Template-OID",
              L"displayName",
              L"msPKI-OID-CPS",
              L"msPKI-OIDLocalizedName",
              L"flags",
              a1);
      v7 = v12;
      if ( v12 )
      {
        v9 = v12;
        v8 = 137560886;
        goto LABEL_4;
      }
      if ( !a1 )
      {
        v13 = wcsrchr(Str, 0x3Fu);
        if ( !v13 )
        {
          v7 = -2147418113;
          v8 = 138281782;
          goto LABEL_3;
        }
        *v13 = 0;
      }
      v7 = 0;
      *a3 = Str;
      Str = 0;
    }
  }
LABEL_16:
  if ( Str )
    LocalFree(Str);
  if ( v4 )
    CertFreeString(v4);
  if ( v3 )
    ldap_unbind(v3);
  return v7;
}

```

## disassembly

```asm
0x18002cb60  mov     [rsp-28h+arg_0], rbx
0x18002cb65  push    rbp
0x18002cb66  push    rsi
0x18002cb67  push    rdi
0x18002cb68  push    r14
0x18002cb6a  push    r15
0x18002cb6c  mov     rbp, rsp
0x18002cb6f  sub     rsp, 70h
0x18002cb73  xor     edi, edi
0x18002cb75  mov     [rbp+Str], 0
0x18002cb7d  xor     esi, esi
0x18002cb7f  mov     [rbp+arg_18], rdi
0x18002cb83  mov     [rbp+var_10], rsi
0x18002cb87  mov     r14, r8
0x18002cb8a  mov     r15d, ecx
0x18002cb8d  test    r8, r8
0x18002cb90  jnz     short loc_18002CBA8
0x18002cb92  mov     ebx, 80070057h
0x18002cb97  mov     ecx, 8150336h; unsigned int
0x18002cb9c  mov     edx, ebx; int
0x18002cb9e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002cba3  jmp     loc_18002CCB8
0x18002cba8  lea     rcx, [rbp+arg_18]; struct ldap **
0x18002cbac  call    ?myTimeOutRobustLdapBind@@YAJPEAPEAUldap@@@Z; myTimeOutRobustLdapBind(ldap * *)
0x18002cbb1  mov     ebx, eax
0x18002cbb3  test    eax, eax
0x18002cbb5  jz      short loc_18002CBD5
0x18002cbb7  mov     r9d, 8007054Bh; int
0x18002cbbd  mov     r8d, eax; int
0x18002cbc0  mov     edx, 81E0336h; unsigned int
0x18002cbc5  xor     ecx, ecx; unsigned __int16 *
0x18002cbc7  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002cbcc  mov     rdi, [rbp+arg_18]
0x18002cbd0  jmp     loc_18002CCB8
0x18002cbd5  mov     rdi, [rbp+arg_18]
0x18002cbd9  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18002cbdd  mov     rcx, rdi; struct ldap *
0x18002cbe0  xor     edx, edx; unsigned __int16 **
0x18002cbe2  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x18002cbe7  mov     ebx, eax
0x18002cbe9  test    eax, eax
0x18002cbeb  jz      short loc_18002CC02
0x18002cbed  mov     edx, eax; int
0x18002cbef  mov     ecx, 8230336h; unsigned int
0x18002cbf4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002cbf9  mov     rsi, [rbp+var_10]
0x18002cbfd  jmp     loc_18002CCB8
0x18002cc02  mov     rsi, [rbp+var_10]
0x18002cc06  lea     rcx, attr; "flags"
0x18002cc0d  mov     [rsp+70h+var_20], r15d
0x18002cc12  lea     rax, aMspkiOidlocali; "msPKI-OIDLocalizedName"
0x18002cc19  mov     [rsp+70h+var_28], rcx
0x18002cc1e  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18002cc25  mov     [rsp+70h+var_30], rax
0x18002cc2a  lea     rdx, aLdap1S2S3S4S5S; "ldap:///%1!s!%2!s!?%3!s!,%4!s!,%5!s!,%6"...
0x18002cc31  lea     rax, aMspkiOidCps; "msPKI-OID-CPS"
0x18002cc38  mov     r9, rsi
0x18002cc3b  mov     [rsp+70h+var_38], rax
0x18002cc40  lea     rax, aDisplayname_0; "displayName"
0x18002cc47  mov     [rsp+70h+var_40], rax
0x18002cc4c  lea     rax, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002cc53  mov     [rsp+70h+var_48], rax
0x18002cc58  mov     [rsp+70h+var_50], rcx
0x18002cc5d  lea     rcx, [rbp+Str]; unsigned __int16 **
0x18002cc61  call    ?FormatMessageUnicode@@YAJPEAPEAGPEAGZZ; FormatMessageUnicode(ushort * *,ushort *,...)
0x18002cc66  mov     ebx, eax
0x18002cc68  test    eax, eax
0x18002cc6a  jz      short loc_18002CC78
0x18002cc6c  mov     edx, eax
0x18002cc6e  mov     ecx, 8330336h
0x18002cc73  jmp     loc_18002CB9E
0x18002cc78  test    r15d, r15d
0x18002cc7b  jnz     short loc_18002CCA7
0x18002cc7d  mov     rcx, [rbp+Str]; Str
0x18002cc81  lea     edx, [r15+3Fh]; Ch
0x18002cc85  call    cs:__imp_wcsrchr
0x18002cc8b  mov     rcx, rax
0x18002cc8e  test    rax, rax
0x18002cc91  jnz     short loc_18002CCA2
0x18002cc93  mov     ebx, 8000FFFFh
0x18002cc98  mov     ecx, 83E0336h
0x18002cc9d  jmp     loc_18002CB9C
0x18002cca2  xor     eax, eax
0x18002cca4  mov     [rcx], ax
0x18002cca7  mov     rax, [rbp+Str]
0x18002ccab  xor     ebx, ebx
0x18002ccad  mov     [r14], rax
0x18002ccb0  mov     [rbp+Str], 0
0x18002ccb8  mov     rcx, [rbp+Str]; hMem
0x18002ccbc  test    rcx, rcx
0x18002ccbf  jz      short loc_18002CCC7
0x18002ccc1  call    cs:__imp_LocalFree
0x18002ccc7  test    rsi, rsi
0x18002ccca  jz      short loc_18002CCD4
0x18002cccc  mov     rcx, rsi; unsigned __int16 *
0x18002cccf  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002ccd4  test    rdi, rdi
0x18002ccd7  jz      short loc_18002CCE2
0x18002ccd9  mov     rcx, rdi; ld
0x18002ccdc  call    cs:__imp_ldap_unbind
0x18002cce2  mov     eax, ebx
0x18002cce4  mov     rbx, [rsp+70h+arg_0]
0x18002ccec  add     rsp, 70h
0x18002ccf0  pop     r15
0x18002ccf2  pop     r14
0x18002ccf4  pop     rdi
0x18002ccf5  pop     rsi
0x18002ccf6  pop     rbp
0x18002ccf7  retn
```
