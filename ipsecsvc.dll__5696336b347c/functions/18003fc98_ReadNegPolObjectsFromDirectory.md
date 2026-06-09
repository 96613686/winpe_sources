# ReadNegPolObjectsFromDirectory

- ea: `0x18003fc98`
- end: `0x18003ff44`
- name: `ReadNegPolObjectsFromDirectory`
- size: `684`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18003ff4c`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000e510`
- `0x180038f04`
- `0x180038fe4`
- `0x180039400`
- `0x18003ecfc`
- `0x18003fc98`
- `0x180041954`
- `0x180042dd4`
- `0x180042ef8`

## import_xrefs

- `WLDAP32!__imp_ldap_count_entries` at `0x18003fd91`
- `WLDAP32!__imp_ldap_count_entries` at `0x18003fd91`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003ff2b`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003ff2b`

## pseudocode

```c
__int64 __fastcall ReadNegPolObjectsFromDirectory(
        LDAP *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6)
{
  __int64 v6; // r13
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  ULONG v12; // eax
  ULONG v13; // r12d
  _QWORD *v14; // rsi
  __int64 v15; // rdi
  ULONG i; // r14d
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  LDAPMessage *res; // [rsp+30h] [rbp-38h] BYREF
  __int64 v21; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-28h] BYREF
  SIZE_T v23; // [rsp+48h] [rbp-20h] BYREF
  __int64 v24[3]; // [rsp+50h] [rbp-18h] BYREF

  v6 = 0;
  res = 0;
  v21 = 0;
  lpMem = 0;
  v24[0] = 0;
  v23 = 0;
  v9 = GenerateQuery(a3, a4, L"(&(objectclass=ipsecNegotiationPolicy)", &lpMem);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 37;
LABEL_5:
    WPP_SF_d(v10[2], v11, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v9);
LABEL_39:
    LODWORD(v15) = 0;
    v14 = 0;
    goto LABEL_41;
  }
  v9 = LdapSearchHelper((int)a1, a2, 1, (int)lpMem, &NegPolDNAttributes, &res);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 38;
    goto LABEL_5;
  }
  v12 = ldap_count_entries(a1, res);
  v13 = v12;
  if ( !v12 )
  {
    v9 = 8202;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 39;
    goto LABEL_5;
  }
  v9 = NsuSizeTMultiply(v12, 8, &v23);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 40;
    goto LABEL_5;
  }
  v14 = IpsecAllocMem(v23);
  if ( !v14 )
  {
    v9 = 14;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 41;
    goto LABEL_5;
  }
  v15 = 0;
  for ( i = 0; i < v13; ++i )
  {
    if ( i )
    {
      LdapNextEntry(a1, v6, &v21);
    }
    else
    {
      v9 = LdapFirstEntry(a1, res, &v21);
      if ( v9 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 42;
          goto LABEL_37;
        }
        goto LABEL_38;
      }
    }
    v6 = v21;
    if ( !(unsigned int)UnMarshallNegPolObject(a1, v21, v24) )
    {
      v14[v15] = v24[0];
      v15 = (unsigned int)(v15 + 1);
    }
  }
  if ( !(_DWORD)v15 )
  {
    v9 = 13;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v18 = 43;
LABEL_37:
      WPP_SF_d(v17[2], v18, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v9);
    }
LABEL_38:
    FreeIpsecNegPolObjects(v14);
    goto LABEL_39;
  }
  v9 = 0;
LABEL_41:
  *a5 = v14;
  *a6 = v15;
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( res )
    ldap_msgfree(res);
  return v9;
}

```

## disassembly

```asm
0x18003fc98  push    rbp
0x18003fc9a  push    rbx
0x18003fc9b  push    rsi
0x18003fc9c  push    rdi
0x18003fc9d  push    r12
0x18003fc9f  push    r13
0x18003fca1  push    r14
0x18003fca3  push    r15
0x18003fca5  mov     rbp, rsp
0x18003fca8  sub     rsp, 68h
0x18003fcac  xor     r13d, r13d
0x18003fcaf  mov     [rbp+res], 0
0x18003fcb7  mov     eax, r9d
0x18003fcba  mov     [rbp+var_30], r13
0x18003fcbe  mov     r10, r8
0x18003fcc1  mov     [rbp+lpMem], r13
0x18003fcc5  mov     rdi, rdx
0x18003fcc8  mov     [rbp+var_18], r13
0x18003fccc  mov     r15, rcx
0x18003fccf  mov     [rbp+var_20], r13
0x18003fcd3  mov     edx, eax
0x18003fcd5  lea     r9, [rbp+lpMem]
0x18003fcd9  mov     rcx, r10
0x18003fcdc  lea     r8, aObjectclassIps_1; "(&(objectclass=ipsecNegotiationPolicy)"
0x18003fce3  call    GenerateQuery
0x18003fce8  mov     ebx, eax
0x18003fcea  mov     rax, [rbp+lpMem]
0x18003fcee  mov     [rbp+lpMem], rax
0x18003fcf2  test    ebx, ebx
0x18003fcf4  jz      short loc_18003FD33
0x18003fcf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fcfd  lea     rax, WPP_GLOBAL_Control
0x18003fd04  cmp     rcx, rax
0x18003fd07  jz      loc_18003FEFF
0x18003fd0d  test    byte ptr [rcx+1Ch], 10h
0x18003fd11  jz      loc_18003FEFF
0x18003fd17  lea     edx, [r13+25h]
0x18003fd1b  mov     rcx, [rcx+10h]
0x18003fd1f  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003fd26  mov     r9d, ebx
0x18003fd29  call    WPP_SF_d
0x18003fd2e  jmp     loc_18003FEFF
0x18003fd33  lea     rcx, [rbp+res]
0x18003fd37  mov     r9, rax; int
0x18003fd3a  mov     [rsp+68h+var_40], rcx; LDAPMessage **
0x18003fd3f  mov     r8d, 1; int
0x18003fd45  lea     rcx, NegPolDNAttributes
0x18003fd4c  mov     rdx, rdi; int
0x18003fd4f  mov     [rsp+68h+var_48], rcx; PZPWSTR
0x18003fd54  mov     rcx, r15; int
0x18003fd57  call    LdapSearchHelper
0x18003fd5c  mov     ebx, eax
0x18003fd5e  test    eax, eax
0x18003fd60  jz      short loc_18003FD8A
0x18003fd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd69  lea     rax, WPP_GLOBAL_Control
0x18003fd70  cmp     rcx, rax
0x18003fd73  jz      loc_18003FEFF
0x18003fd79  test    byte ptr [rcx+1Ch], 10h
0x18003fd7d  jz      loc_18003FEFF
0x18003fd83  mov     edx, 26h ; '&'
0x18003fd88  jmp     short loc_18003FD1B
0x18003fd8a  mov     rdx, [rbp+res]; res
0x18003fd8e  mov     rcx, r15; ld
0x18003fd91  call    cs:__imp_ldap_count_entries
0x18003fd97  mov     r12d, eax
0x18003fd9a  test    eax, eax
0x18003fd9c  jnz     short loc_18003FDCE
0x18003fd9e  mov     ebx, 200Ah
0x18003fda3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fdaa  lea     rax, WPP_GLOBAL_Control
0x18003fdb1  cmp     rcx, rax
0x18003fdb4  jz      loc_18003FEFF
0x18003fdba  test    byte ptr [rcx+1Ch], 10h
0x18003fdbe  jz      loc_18003FEFF
0x18003fdc4  mov     edx, 27h ; '''
0x18003fdc9  jmp     loc_18003FD1B
0x18003fdce  mov     rcx, r12
0x18003fdd1  lea     r8, [rbp+var_20]
0x18003fdd5  mov     edx, 8
0x18003fdda  call    NsuSizeTMultiply
0x18003fddf  mov     ebx, eax
0x18003fde1  test    eax, eax
0x18003fde3  jz      short loc_18003FE10
0x18003fde5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fdec  lea     rax, WPP_GLOBAL_Control
0x18003fdf3  cmp     rcx, rax
0x18003fdf6  jz      loc_18003FEFF
0x18003fdfc  test    byte ptr [rcx+1Ch], 10h
0x18003fe00  jz      loc_18003FEFF
0x18003fe06  mov     edx, 28h ; '('
0x18003fe0b  jmp     loc_18003FD1B
0x18003fe10  mov     rcx, [rbp+var_20]
0x18003fe14  call    IpsecAllocMem
0x18003fe19  mov     rsi, rax
0x18003fe1c  test    rax, rax
0x18003fe1f  jnz     short loc_18003FE4D
0x18003fe21  lea     ebx, [rax+0Eh]
0x18003fe24  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe2b  lea     rax, WPP_GLOBAL_Control
0x18003fe32  cmp     rcx, rax
0x18003fe35  jz      loc_18003FEFF
0x18003fe3b  test    byte ptr [rcx+1Ch], 10h
0x18003fe3f  jz      loc_18003FEFF
0x18003fe45  lea     edx, [rsi+29h]
0x18003fe48  jmp     loc_18003FD1B
0x18003fe4d  xor     edi, edi
0x18003fe4f  xor     r14d, r14d
0x18003fe52  cmp     r14d, r12d
0x18003fe55  jnb     short loc_18003FEBF
0x18003fe57  lea     r8, [rbp+var_30]
0x18003fe5b  mov     rcx, r15
0x18003fe5e  test    r14d, r14d
0x18003fe61  jnz     short loc_18003FE91
0x18003fe63  mov     rdx, [rbp+res]
0x18003fe67  call    LdapFirstEntry
0x18003fe6c  mov     ebx, eax
0x18003fe6e  test    eax, eax
0x18003fe70  jz      short loc_18003FE99
0x18003fe72  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe79  lea     rax, WPP_GLOBAL_Control
0x18003fe80  cmp     rcx, rax
0x18003fe83  jz      short loc_18003FEF5
0x18003fe85  test    byte ptr [rcx+1Ch], 10h
0x18003fe89  jz      short loc_18003FEF5
0x18003fe8b  lea     edx, [r14+2Ah]
0x18003fe8f  jmp     short loc_18003FEE2
0x18003fe91  mov     rdx, r13
0x18003fe94  call    LdapNextEntry
0x18003fe99  mov     r13, [rbp+var_30]
0x18003fe9d  lea     r8, [rbp+var_18]
0x18003fea1  mov     rdx, r13
0x18003fea4  mov     rcx, r15
0x18003fea7  call    UnMarshallNegPolObject
0x18003feac  test    eax, eax
0x18003feae  jnz     short loc_18003FEBA
0x18003feb0  mov     rax, [rbp+var_18]
0x18003feb4  mov     [rsi+rdi*8], rax
0x18003feb8  inc     edi
0x18003feba  inc     r14d
0x18003febd  jmp     short loc_18003FE52
0x18003febf  test    edi, edi
0x18003fec1  jnz     short loc_18003FF05
0x18003fec3  lea     ebx, [rdi+0Dh]
0x18003fec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fecd  lea     rax, WPP_GLOBAL_Control
0x18003fed4  cmp     rcx, rax
0x18003fed7  jz      short loc_18003FEF5
0x18003fed9  test    byte ptr [rcx+1Ch], 10h
0x18003fedd  jz      short loc_18003FEF5
0x18003fedf  lea     edx, [rdi+2Bh]
0x18003fee2  mov     rcx, [rcx+10h]
0x18003fee6  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003feed  mov     r9d, ebx
0x18003fef0  call    WPP_SF_d
0x18003fef5  mov     edx, edi
0x18003fef7  mov     rcx, rsi; lpMem
0x18003fefa  call    FreeIpsecNegPolObjects
0x18003feff  xor     edi, edi
0x18003ff01  xor     esi, esi
0x18003ff03  jmp     short loc_18003FF07
0x18003ff05  xor     ebx, ebx
0x18003ff07  mov     rax, [rbp+arg_20]
0x18003ff0b  mov     [rax], rsi
0x18003ff0e  mov     rax, [rbp+arg_28]
0x18003ff12  mov     [rax], edi
0x18003ff14  mov     rcx, [rbp+lpMem]; lpMem
0x18003ff18  test    rcx, rcx
0x18003ff1b  jz      short loc_18003FF22
0x18003ff1d  call    IpsecFreeMem
0x18003ff22  mov     rcx, [rbp+res]; res
0x18003ff26  test    rcx, rcx
0x18003ff29  jz      short loc_18003FF31
0x18003ff2b  call    cs:__imp_ldap_msgfree
0x18003ff31  mov     eax, ebx
0x18003ff33  add     rsp, 68h
0x18003ff37  pop     r15
0x18003ff39  pop     r14
0x18003ff3b  pop     r13
0x18003ff3d  pop     r12
0x18003ff3f  pop     rdi
0x18003ff40  pop     rsi
0x18003ff41  pop     rbx
0x18003ff42  pop     rbp
0x18003ff43  retn
```
