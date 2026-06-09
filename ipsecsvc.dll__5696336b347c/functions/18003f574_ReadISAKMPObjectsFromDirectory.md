# ReadISAKMPObjectsFromDirectory

- ea: `0x18003f574`
- end: `0x18003f81d`
- name: `ReadISAKMPObjectsFromDirectory`
- size: `681`
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
- `0x18003f574`
- `0x180040a7c`
- `0x180042c20`
- `0x180042ef8`

## import_xrefs

- `WLDAP32!__imp_ldap_count_entries` at `0x18003f66a`
- `WLDAP32!__imp_ldap_count_entries` at `0x18003f66a`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003f804`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003f804`

## pseudocode

```c
__int64 __fastcall ReadISAKMPObjectsFromDirectory(LDAP *a1, int a2, __int64 a3, __int64 a4, _QWORD *a5, _DWORD *a6)
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
  v9 = GenerateQuery(a3, 1, L"(&(objectclass=ipsecISAKMPPolicy)", &lpMem);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 44;
LABEL_5:
    WPP_SF_d(v10[2], v11, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v9);
LABEL_39:
    LODWORD(v15) = 0;
    v14 = 0;
    goto LABEL_41;
  }
  v9 = LdapSearchHelper((int)a1, a2, 1, (int)lpMem, &ISAKMPDNAttributes, &res);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 45;
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
    v11 = 46;
    goto LABEL_5;
  }
  v9 = NsuSizeTMultiply(v12, 8, &v23);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 47;
    goto LABEL_5;
  }
  v14 = IpsecAllocMem(v23);
  if ( !v14 )
  {
    v9 = 14;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v11 = 48;
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
          v18 = 49;
          goto LABEL_37;
        }
        goto LABEL_38;
      }
    }
    v6 = v21;
    if ( !(unsigned int)UnMarshallISAKMPObject(a1, v21, v24) )
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
      v18 = 50;
LABEL_37:
      WPP_SF_d(v17[2], v18, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v9);
    }
LABEL_38:
    FreeIpsecISAKMPObjects(v14);
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
0x18003f574  push    rbp
0x18003f576  push    rbx
0x18003f577  push    rsi
0x18003f578  push    rdi
0x18003f579  push    r12
0x18003f57b  push    r13
0x18003f57d  push    r14
0x18003f57f  push    r15
0x18003f581  mov     rbp, rsp
0x18003f584  sub     rsp, 68h
0x18003f588  xor     r13d, r13d
0x18003f58b  mov     [rbp+res], 0
0x18003f593  mov     rax, r8
0x18003f596  mov     [rbp+var_30], r13
0x18003f59a  mov     rdi, rdx
0x18003f59d  mov     [rbp+lpMem], r13
0x18003f5a1  mov     r15, rcx
0x18003f5a4  mov     [rbp+var_18], r13
0x18003f5a8  lea     esi, [r13+1]
0x18003f5ac  mov     [rbp+var_20], r13
0x18003f5b0  mov     edx, esi
0x18003f5b2  lea     r9, [rbp+lpMem]
0x18003f5b6  lea     r8, aObjectclassIps_0; "(&(objectclass=ipsecISAKMPPolicy)"
0x18003f5bd  mov     rcx, rax
0x18003f5c0  call    GenerateQuery
0x18003f5c5  mov     ebx, eax
0x18003f5c7  mov     rax, [rbp+lpMem]
0x18003f5cb  mov     [rbp+lpMem], rax
0x18003f5cf  test    ebx, ebx
0x18003f5d1  jz      short loc_18003F60F
0x18003f5d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5da  lea     rax, WPP_GLOBAL_Control
0x18003f5e1  cmp     rcx, rax
0x18003f5e4  jz      loc_18003F7D8
0x18003f5ea  test    byte ptr [rcx+1Ch], 10h
0x18003f5ee  jz      loc_18003F7D8
0x18003f5f4  lea     edx, [rsi+2Bh]
0x18003f5f7  mov     rcx, [rcx+10h]
0x18003f5fb  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003f602  mov     r9d, ebx
0x18003f605  call    WPP_SF_d
0x18003f60a  jmp     loc_18003F7D8
0x18003f60f  lea     rcx, [rbp+res]
0x18003f613  mov     r9, rax; int
0x18003f616  mov     [rsp+68h+var_40], rcx; LDAPMessage **
0x18003f61b  mov     r8d, esi; int
0x18003f61e  lea     rcx, ISAKMPDNAttributes
0x18003f625  mov     rdx, rdi; int
0x18003f628  mov     [rsp+68h+var_48], rcx; PZPWSTR
0x18003f62d  mov     rcx, r15; int
0x18003f630  call    LdapSearchHelper
0x18003f635  mov     ebx, eax
0x18003f637  test    eax, eax
0x18003f639  jz      short loc_18003F663
0x18003f63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f642  lea     rax, WPP_GLOBAL_Control
0x18003f649  cmp     rcx, rax
0x18003f64c  jz      loc_18003F7D8
0x18003f652  test    byte ptr [rcx+1Ch], 10h
0x18003f656  jz      loc_18003F7D8
0x18003f65c  mov     edx, 2Dh ; '-'
0x18003f661  jmp     short loc_18003F5F7
0x18003f663  mov     rdx, [rbp+res]; res
0x18003f667  mov     rcx, r15; ld
0x18003f66a  call    cs:__imp_ldap_count_entries
0x18003f670  mov     r12d, eax
0x18003f673  test    eax, eax
0x18003f675  jnz     short loc_18003F6A7
0x18003f677  mov     ebx, 200Ah
0x18003f67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f683  lea     rax, WPP_GLOBAL_Control
0x18003f68a  cmp     rcx, rax
0x18003f68d  jz      loc_18003F7D8
0x18003f693  test    byte ptr [rcx+1Ch], 10h
0x18003f697  jz      loc_18003F7D8
0x18003f69d  mov     edx, 2Eh ; '.'
0x18003f6a2  jmp     loc_18003F5F7
0x18003f6a7  mov     rcx, r12
0x18003f6aa  lea     r8, [rbp+var_20]
0x18003f6ae  mov     edx, 8
0x18003f6b3  call    NsuSizeTMultiply
0x18003f6b8  mov     ebx, eax
0x18003f6ba  test    eax, eax
0x18003f6bc  jz      short loc_18003F6E9
0x18003f6be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f6c5  lea     rax, WPP_GLOBAL_Control
0x18003f6cc  cmp     rcx, rax
0x18003f6cf  jz      loc_18003F7D8
0x18003f6d5  test    byte ptr [rcx+1Ch], 10h
0x18003f6d9  jz      loc_18003F7D8
0x18003f6df  mov     edx, 2Fh ; '/'
0x18003f6e4  jmp     loc_18003F5F7
0x18003f6e9  mov     rcx, [rbp+var_20]
0x18003f6ed  call    IpsecAllocMem
0x18003f6f2  mov     rsi, rax
0x18003f6f5  test    rax, rax
0x18003f6f8  jnz     short loc_18003F726
0x18003f6fa  lea     ebx, [rax+0Eh]
0x18003f6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f704  lea     rax, WPP_GLOBAL_Control
0x18003f70b  cmp     rcx, rax
0x18003f70e  jz      loc_18003F7D8
0x18003f714  test    byte ptr [rcx+1Ch], 10h
0x18003f718  jz      loc_18003F7D8
0x18003f71e  lea     edx, [rsi+30h]
0x18003f721  jmp     loc_18003F5F7
0x18003f726  xor     edi, edi
0x18003f728  xor     r14d, r14d
0x18003f72b  cmp     r14d, r12d
0x18003f72e  jnb     short loc_18003F798
0x18003f730  lea     r8, [rbp+var_30]
0x18003f734  mov     rcx, r15
0x18003f737  test    r14d, r14d
0x18003f73a  jnz     short loc_18003F76A
0x18003f73c  mov     rdx, [rbp+res]
0x18003f740  call    LdapFirstEntry
0x18003f745  mov     ebx, eax
0x18003f747  test    eax, eax
0x18003f749  jz      short loc_18003F772
0x18003f74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f752  lea     rax, WPP_GLOBAL_Control
0x18003f759  cmp     rcx, rax
0x18003f75c  jz      short loc_18003F7CE
0x18003f75e  test    byte ptr [rcx+1Ch], 10h
0x18003f762  jz      short loc_18003F7CE
0x18003f764  lea     edx, [r14+31h]
0x18003f768  jmp     short loc_18003F7BB
0x18003f76a  mov     rdx, r13
0x18003f76d  call    LdapNextEntry
0x18003f772  mov     r13, [rbp+var_30]
0x18003f776  lea     r8, [rbp+var_18]
0x18003f77a  mov     rdx, r13
0x18003f77d  mov     rcx, r15
0x18003f780  call    UnMarshallISAKMPObject
0x18003f785  test    eax, eax
0x18003f787  jnz     short loc_18003F793
0x18003f789  mov     rax, [rbp+var_18]
0x18003f78d  mov     [rsi+rdi*8], rax
0x18003f791  inc     edi
0x18003f793  inc     r14d
0x18003f796  jmp     short loc_18003F72B
0x18003f798  test    edi, edi
0x18003f79a  jnz     short loc_18003F7DE
0x18003f79c  lea     ebx, [rdi+0Dh]
0x18003f79f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f7a6  lea     rax, WPP_GLOBAL_Control
0x18003f7ad  cmp     rcx, rax
0x18003f7b0  jz      short loc_18003F7CE
0x18003f7b2  test    byte ptr [rcx+1Ch], 10h
0x18003f7b6  jz      short loc_18003F7CE
0x18003f7b8  lea     edx, [rdi+32h]
0x18003f7bb  mov     rcx, [rcx+10h]
0x18003f7bf  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003f7c6  mov     r9d, ebx
0x18003f7c9  call    WPP_SF_d
0x18003f7ce  mov     edx, edi
0x18003f7d0  mov     rcx, rsi; lpMem
0x18003f7d3  call    FreeIpsecISAKMPObjects
0x18003f7d8  xor     edi, edi
0x18003f7da  xor     esi, esi
0x18003f7dc  jmp     short loc_18003F7E0
0x18003f7de  xor     ebx, ebx
0x18003f7e0  mov     rax, [rbp+arg_20]
0x18003f7e4  mov     [rax], rsi
0x18003f7e7  mov     rax, [rbp+arg_28]
0x18003f7eb  mov     [rax], edi
0x18003f7ed  mov     rcx, [rbp+lpMem]; lpMem
0x18003f7f1  test    rcx, rcx
0x18003f7f4  jz      short loc_18003F7FB
0x18003f7f6  call    IpsecFreeMem
0x18003f7fb  mov     rcx, [rbp+res]; res
0x18003f7ff  test    rcx, rcx
0x18003f802  jz      short loc_18003F80A
0x18003f804  call    cs:__imp_ldap_msgfree
0x18003f80a  mov     eax, ebx
0x18003f80c  add     rsp, 68h
0x18003f810  pop     r15
0x18003f812  pop     r14
0x18003f814  pop     r13
0x18003f816  pop     r12
0x18003f818  pop     rdi
0x18003f819  pop     rsi
0x18003f81a  pop     rbx
0x18003f81b  pop     rbp
0x18003f81c  retn
```
