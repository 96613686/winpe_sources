# ReadNFAObjectsFromDirectory

- ea: `0x18003f824`
- end: `0x18003fc90`
- name: `ReadNFAObjectsFromDirectory`
- size: `1132`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18003ff4c`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000e510`
- `0x180035608`
- `0x180038f04`
- `0x180038fe4`
- `0x180039400`
- `0x18003ecfc`
- `0x18003f824`
- `0x180041114`
- `0x180042ab0`
- `0x180042cf8`
- `0x180042ef8`

## import_xrefs

- `WLDAP32!__imp_ldap_count_entries` at `0x18003f8f7`
- `WLDAP32!__imp_ldap_count_entries` at `0x18003f8f7`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003fc62`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003fc62`

## pseudocode

```c
__int64 __fastcall ReadNFAObjectsFromDirectory(
        LDAP *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int *a7,
        _QWORD *a8,
        unsigned int *a9,
        _QWORD *a10,
        _DWORD *a11)
{
  unsigned int v11; // r12d
  unsigned int v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  ULONG v19; // eax
  __int64 v20; // rsi
  void *v21; // r14
  unsigned int v22; // edi
  unsigned int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  _QWORD *v27; // r13
  _QWORD *v28; // r15
  __int64 v29; // rbx
  __int64 v30; // r14
  ULONG i; // esi
  unsigned int v32; // eax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // rax
  LPVOID v37; // rcx
  SIZE_T v39; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  __int64 v41; // [rsp+40h] [rbp-30h] BYREF
  LDAPMessage *res; // [rsp+48h] [rbp-28h] BYREF
  LPVOID v43; // [rsp+50h] [rbp-20h]
  LPVOID v44; // [rsp+58h] [rbp-18h] BYREF
  __int64 v45; // [rsp+60h] [rbp-10h] BYREF
  __int64 v46; // [rsp+68h] [rbp-8h] BYREF
  ULONG v48; // [rsp+C0h] [rbp+50h]

  v11 = 0;
  res = 0;
  v41 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  lpMem = 0;
  v39 = 0;
  GenerateQuery(a4, a5, L"(&(objectclass=ipsecNFA)", &v44);
  v14 = LdapSearchHelper((int)a1, a2, 1, (int)v44, &NFADNAttributes, &res);
  v15 = v14;
  if ( v14 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_57;
    v17 = 22;
    goto LABEL_5;
  }
  v19 = ldap_count_entries(a1, res);
  v48 = v19;
  if ( !v19 )
  {
    v15 = 8202;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_57;
    v17 = 23;
    v18 = 8202;
    goto LABEL_6;
  }
  v20 = v19;
  v14 = NsuSizeTMultiply(v19, 8, &v39);
  v15 = v14;
  if ( v14 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_57;
    v17 = 24;
LABEL_5:
    v18 = v14;
LABEL_6:
    WPP_SF_d(v16[2], v17, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v18);
LABEL_57:
    *a10 = 0;
    *a8 = 0;
    *a11 = 0;
    *a9 = 0;
    *a6 = 0;
    *a7 = 0;
    goto LABEL_59;
  }
  v43 = IpsecAllocMem(v39);
  v21 = v43;
  if ( !v43 )
  {
    v18 = 14;
    v15 = 14;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_57;
    v17 = 25;
    goto LABEL_6;
  }
  v22 = 0;
  v23 = NsuSizeTMultiply(v20, 8, &v39);
  v15 = v23;
  if ( v23 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_56;
    v25 = 26;
    v26 = v23;
LABEL_23:
    WPP_SF_d(v24[2], v25, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v26);
LABEL_56:
    FreeIpsecNFAObjects(v21);
    goto LABEL_57;
  }
  v27 = IpsecAllocMem(v39);
  if ( !v27 )
  {
    v26 = 14;
    v15 = 14;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_56;
    v25 = 27;
    goto LABEL_23;
  }
  v28 = IpsecAllocMem(v39);
  if ( !v28 )
  {
    v15 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, 14);
LABEL_55:
    FreeNFAReferences(v27, v22);
    goto LABEL_56;
  }
  v29 = v41;
  v30 = 0;
  for ( i = 0; i < v48; ++i )
  {
    if ( i )
    {
      LdapNextEntry(a1, v29, &v41);
    }
    else
    {
      v32 = LdapFirstEntry(a1, res, &v41);
      v15 = v32;
      if ( v32 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v34 = 29;
          v35 = v32;
          goto LABEL_53;
        }
        goto LABEL_54;
      }
    }
    v29 = v41;
    if ( !(unsigned int)UnMarshallNFAObject((_DWORD)a1, v41, (unsigned int)&v45, (unsigned int)&v46, (__int64)&lpMem) )
    {
      *((_QWORD *)v43 + v22) = v45;
      if ( v46 )
      {
        v36 = v11++;
        v27[v36] = v46;
      }
      if ( lpMem )
      {
        if ( (unsigned int)IsStringInArray(v28, lpMem, (unsigned int)v30) )
        {
          IpsecFreeMem(lpMem);
          lpMem = 0;
        }
        else
        {
          v28[v30] = lpMem;
          v30 = (unsigned int)(v30 + 1);
        }
      }
      ++v22;
    }
  }
  if ( !v22 )
  {
    v15 = 13;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v34 = 30;
      v35 = 13;
LABEL_53:
      WPP_SF_d(v33[2], v34, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v35);
    }
LABEL_54:
    FreeNFAReferences(v28, v22);
    v21 = v43;
    goto LABEL_55;
  }
  v37 = v43;
  *a8 = v27;
  *a10 = v28;
  *a6 = v37;
  *a7 = v22;
  *a11 = v30;
  *a9 = v11;
  v15 = 0;
LABEL_59:
  if ( res )
    ldap_msgfree(res);
  if ( v44 )
    IpsecFreeMem(v44);
  return v15;
}

```

## disassembly

```asm
0x18003f824  mov     [rsp-38h+arg_8], rbx
0x18003f829  mov     [rsp-38h+arg_10], r8
0x18003f82e  mov     [rsp-38h+arg_0], rcx
0x18003f833  push    rbp
0x18003f834  push    rsi
0x18003f835  push    rdi
0x18003f836  push    r12
0x18003f838  push    r13
0x18003f83a  push    r14
0x18003f83c  push    r15
0x18003f83e  mov     rbp, rsp
0x18003f841  sub     rsp, 70h
0x18003f845  xor     r12d, r12d
0x18003f848  lea     r8, aObjectclassIps_2; "(&(objectclass=ipsecNFA)"
0x18003f84f  mov     rax, r9
0x18003f852  mov     [rbp+res], r12
0x18003f856  mov     rbx, rdx
0x18003f859  mov     [rbp+var_30], r12
0x18003f85d  mov     edx, [rbp+arg_20]
0x18003f860  lea     r9, [rbp+var_18]
0x18003f864  mov     rdi, rcx
0x18003f867  mov     [rbp+var_18], r12
0x18003f86b  mov     rcx, rax
0x18003f86e  mov     [rbp+var_10], r12
0x18003f872  mov     [rbp+var_8], r12
0x18003f876  mov     [rbp+lpMem], r12
0x18003f87a  mov     [rbp+var_40], r12
0x18003f87e  call    GenerateQuery
0x18003f883  mov     r9, [rbp+var_18]; int
0x18003f887  lea     rax, [rbp+res]
0x18003f88b  mov     [rsp+70h+var_48], rax; LDAPMessage **
0x18003f890  lea     r8d, [r12+1]; int
0x18003f895  lea     rax, NFADNAttributes
0x18003f89c  mov     rdx, rbx; int
0x18003f89f  mov     rcx, rdi; int
0x18003f8a2  mov     [rsp+70h+var_50], rax; PZPWSTR
0x18003f8a7  call    LdapSearchHelper
0x18003f8ac  mov     ebx, eax
0x18003f8ae  test    eax, eax
0x18003f8b0  jz      short loc_18003F8F0
0x18003f8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8b9  lea     rdx, WPP_GLOBAL_Control
0x18003f8c0  cmp     rcx, rdx
0x18003f8c3  jz      loc_18003FBE8
0x18003f8c9  test    byte ptr [rcx+1Ch], 10h
0x18003f8cd  jz      loc_18003FBE8
0x18003f8d3  lea     edx, [r12+16h]
0x18003f8d8  mov     r9d, eax
0x18003f8db  mov     rcx, [rcx+10h]
0x18003f8df  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003f8e6  call    WPP_SF_d
0x18003f8eb  jmp     loc_18003FBE8
0x18003f8f0  mov     rdx, [rbp+res]; res
0x18003f8f4  mov     rcx, rdi; ld
0x18003f8f7  call    cs:__imp_ldap_count_entries
0x18003f8fd  mov     dword ptr [rbp+arg_10], eax
0x18003f900  test    eax, eax
0x18003f902  jnz     short loc_18003F932
0x18003f904  mov     ebx, 200Ah
0x18003f909  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f910  lea     rdx, WPP_GLOBAL_Control
0x18003f917  cmp     rcx, rdx
0x18003f91a  jz      loc_18003FBE8
0x18003f920  test    byte ptr [rcx+1Ch], 10h
0x18003f924  jz      loc_18003FBE8
0x18003f92a  lea     edx, [rax+17h]
0x18003f92d  mov     r9d, ebx
0x18003f930  jmp     short loc_18003F8DB
0x18003f932  mov     r15d, 8
0x18003f938  mov     ecx, eax
0x18003f93a  mov     edx, r15d
0x18003f93d  mov     esi, eax
0x18003f93f  lea     r8, [rbp+var_40]
0x18003f943  call    NsuSizeTMultiply
0x18003f948  mov     ebx, eax
0x18003f94a  test    eax, eax
0x18003f94c  jz      short loc_18003F978
0x18003f94e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f955  lea     rdx, WPP_GLOBAL_Control
0x18003f95c  cmp     rcx, rdx
0x18003f95f  jz      loc_18003FBE8
0x18003f965  test    byte ptr [rcx+1Ch], 10h
0x18003f969  jz      loc_18003FBE8
0x18003f96f  lea     edx, [r15+10h]
0x18003f973  jmp     loc_18003F8D8
0x18003f978  mov     rcx, [rbp+var_40]
0x18003f97c  call    IpsecAllocMem
0x18003f981  mov     [rbp+var_20], rax
0x18003f985  mov     r14, rax
0x18003f988  test    rax, rax
0x18003f98b  jnz     short loc_18003F9BD
0x18003f98d  lea     r9d, [rax+0Eh]
0x18003f991  mov     ebx, r9d
0x18003f994  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f99b  lea     rdx, WPP_GLOBAL_Control
0x18003f9a2  cmp     rcx, rdx
0x18003f9a5  jz      loc_18003FBE8
0x18003f9ab  test    byte ptr [rcx+1Ch], 10h
0x18003f9af  jz      loc_18003FBE8
0x18003f9b5  lea     edx, [rax+19h]
0x18003f9b8  jmp     loc_18003F8DB
0x18003f9bd  lea     r8, [rbp+var_40]
0x18003f9c1  mov     rdx, r15
0x18003f9c4  mov     rcx, rsi
0x18003f9c7  mov     edi, r12d
0x18003f9ca  call    NsuSizeTMultiply
0x18003f9cf  mov     ebx, eax
0x18003f9d1  test    eax, eax
0x18003f9d3  jz      short loc_18003FA13
0x18003f9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f9dc  lea     rdx, WPP_GLOBAL_Control
0x18003f9e3  cmp     rcx, rdx
0x18003f9e6  jz      loc_18003FBDE
0x18003f9ec  test    byte ptr [rcx+1Ch], 10h
0x18003f9f0  jz      loc_18003FBDE
0x18003f9f6  mov     edx, 1Ah
0x18003f9fb  mov     r9d, eax
0x18003f9fe  mov     rcx, [rcx+10h]
0x18003fa02  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003fa09  call    WPP_SF_d
0x18003fa0e  jmp     loc_18003FBDE
0x18003fa13  mov     rcx, [rbp+var_40]
0x18003fa17  call    IpsecAllocMem
0x18003fa1c  mov     r13, rax
0x18003fa1f  test    rax, rax
0x18003fa22  jnz     short loc_18003FA51
0x18003fa24  lea     r9d, [rax+0Eh]
0x18003fa28  mov     ebx, r9d
0x18003fa2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa32  lea     rdx, WPP_GLOBAL_Control
0x18003fa39  cmp     rcx, rdx
0x18003fa3c  jz      loc_18003FBDE
0x18003fa42  test    byte ptr [rcx+1Ch], 10h
0x18003fa46  jz      loc_18003FBDE
0x18003fa4c  lea     edx, [rax+1Bh]
0x18003fa4f  jmp     short loc_18003F9FE
0x18003fa51  mov     rcx, [rbp+var_40]
0x18003fa55  call    IpsecAllocMem
0x18003fa5a  mov     r15, rax
0x18003fa5d  test    rax, rax
0x18003fa60  jnz     short loc_18003FAA2
0x18003fa62  lea     r9d, [rax+0Eh]
0x18003fa66  mov     ebx, r9d
0x18003fa69  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa70  lea     rdx, WPP_GLOBAL_Control
0x18003fa77  cmp     rcx, rdx
0x18003fa7a  jz      loc_18003FBD4
0x18003fa80  test    byte ptr [rcx+1Ch], 10h
0x18003fa84  jz      loc_18003FBD4
0x18003fa8a  mov     rcx, [rcx+10h]
0x18003fa8e  lea     edx, [rax+1Ch]
0x18003fa91  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003fa98  call    WPP_SF_d
0x18003fa9d  jmp     loc_18003FBD4
0x18003faa2  mov     rbx, [rbp+var_30]
0x18003faa6  xor     r14d, r14d
0x18003faa9  xor     esi, esi
0x18003faab  cmp     esi, dword ptr [rbp+arg_10]
0x18003faae  jnb     loc_18003FB89
0x18003fab4  mov     rcx, [rbp+arg_0]
0x18003fab8  lea     r8, [rbp+var_30]
0x18003fabc  test    esi, esi
0x18003fabe  jnz     short loc_18003FAFB
0x18003fac0  mov     rdx, [rbp+res]
0x18003fac4  call    LdapFirstEntry
0x18003fac9  mov     ebx, eax
0x18003facb  test    eax, eax
0x18003facd  jz      short loc_18003FB03
0x18003facf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fad6  lea     rdx, WPP_GLOBAL_Control
0x18003fadd  cmp     rcx, rdx
0x18003fae0  jz      loc_18003FBC3
0x18003fae6  test    byte ptr [rcx+1Ch], 10h
0x18003faea  jz      loc_18003FBC3
0x18003faf0  lea     edx, [rsi+1Dh]
0x18003faf3  mov     r9d, eax
0x18003faf6  jmp     loc_18003FBB3
0x18003fafb  mov     rdx, rbx
0x18003fafe  call    LdapNextEntry
0x18003fb03  mov     rbx, [rbp+var_30]
0x18003fb07  lea     rax, [rbp+lpMem]
0x18003fb0b  mov     rcx, [rbp+arg_0]
0x18003fb0f  lea     r9, [rbp+var_8]
0x18003fb13  mov     rdx, rbx
0x18003fb16  mov     [rsp+70h+var_50], rax
0x18003fb1b  lea     r8, [rbp+var_10]
0x18003fb1f  call    UnMarshallNFAObject
0x18003fb24  test    eax, eax
0x18003fb26  jnz     short loc_18003FB82
0x18003fb28  mov     rdx, [rbp+var_20]
0x18003fb2c  mov     rax, [rbp+var_10]
0x18003fb30  mov     ecx, edi
0x18003fb32  mov     [rdx+rcx*8], rax
0x18003fb36  mov     rcx, [rbp+var_8]
0x18003fb3a  test    rcx, rcx
0x18003fb3d  jz      short loc_18003FB4A
0x18003fb3f  mov     eax, r12d
0x18003fb42  inc     r12d
0x18003fb45  mov     [r13+rax*8+0], rcx
0x18003fb4a  mov     rdx, [rbp+lpMem]
0x18003fb4e  test    rdx, rdx
0x18003fb51  jz      short loc_18003FB80
0x18003fb53  mov     r8d, r14d
0x18003fb56  mov     rcx, r15
0x18003fb59  call    IsStringInArray
0x18003fb5e  test    eax, eax
0x18003fb60  jnz     short loc_18003FB6F
0x18003fb62  mov     rax, [rbp+lpMem]
0x18003fb66  mov     [r15+r14*8], rax
0x18003fb6a  inc     r14d
0x18003fb6d  jmp     short loc_18003FB80
0x18003fb6f  mov     rcx, [rbp+lpMem]; lpMem
0x18003fb73  call    IpsecFreeMem
0x18003fb78  mov     [rbp+lpMem], 0
0x18003fb80  inc     edi
0x18003fb82  inc     esi
0x18003fb84  jmp     loc_18003FAAB
0x18003fb89  test    edi, edi
0x18003fb8b  jnz     loc_18003FC1D
0x18003fb91  lea     ebx, [rdi+0Dh]
0x18003fb94  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb9b  lea     rdx, WPP_GLOBAL_Control
0x18003fba2  cmp     rcx, rdx
0x18003fba5  jz      short loc_18003FBC3
0x18003fba7  test    byte ptr [rcx+1Ch], 10h
0x18003fbab  jz      short loc_18003FBC3
0x18003fbad  lea     edx, [rdi+1Eh]
0x18003fbb0  mov     r9d, ebx
0x18003fbb3  mov     rcx, [rcx+10h]
0x18003fbb7  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003fbbe  call    WPP_SF_d
0x18003fbc3  mov     edx, edi
0x18003fbc5  mov     rcx, r15; lpMem
0x18003fbc8  call    FreeNFAReferences
0x18003fbcd  mov     r14, [rbp+var_20]
0x18003fbd1  xor     r12d, r12d
0x18003fbd4  mov     edx, edi
0x18003fbd6  mov     rcx, r13; lpMem
0x18003fbd9  call    FreeNFAReferences
0x18003fbde  mov     edx, edi
0x18003fbe0  mov     rcx, r14; lpMem
0x18003fbe3  call    FreeIpsecNFAObjects
0x18003fbe8  mov     rax, [rbp+arg_48]
0x18003fbef  mov     [rax], r12
0x18003fbf2  mov     rax, [rbp+arg_38]
0x18003fbf6  mov     [rax], r12
0x18003fbf9  mov     rax, [rbp+arg_50]
0x18003fc00  mov     [rax], r12d
0x18003fc03  mov     rax, [rbp+arg_40]
0x18003fc0a  mov     [rax], r12d
0x18003fc0d  mov     rax, [rbp+arg_28]
0x18003fc11  mov     [rax], r12
0x18003fc14  mov     rax, [rbp+arg_30]
0x18003fc18  mov     [rax], r12d
0x18003fc1b  jmp     short loc_18003FC59
0x18003fc1d  mov     rax, [rbp+arg_38]
0x18003fc21  mov     rcx, [rbp+var_20]
0x18003fc25  mov     [rax], r13
0x18003fc28  mov     rax, [rbp+arg_48]
0x18003fc2f  mov     [rax], r15
0x18003fc32  mov     rax, [rbp+arg_28]
0x18003fc36  mov     [rax], rcx
0x18003fc39  mov     rax, [rbp+arg_30]
0x18003fc3d  mov     [rax], edi
0x18003fc3f  mov     rax, [rbp+arg_50]
0x18003fc46  mov     [rax], r14d
0x18003fc49  mov     rax, [rbp+arg_40]
0x18003fc50  mov     [rax], r12d
0x18003fc53  xor     r12d, r12d
0x18003fc56  mov     ebx, r12d
0x18003fc59  mov     rcx, [rbp+res]; res
0x18003fc5d  test    rcx, rcx
0x18003fc60  jz      short loc_18003FC68
0x18003fc62  call    cs:__imp_ldap_msgfree
0x18003fc68  mov     rcx, [rbp+var_18]; lpMem
0x18003fc6c  test    rcx, rcx
0x18003fc6f  jz      short loc_18003FC76
0x18003fc71  call    IpsecFreeMem
0x18003fc76  mov     eax, ebx
0x18003fc78  mov     rbx, [rsp+70h+arg_8]
0x18003fc80  add     rsp, 70h
0x18003fc84  pop     r15
0x18003fc86  pop     r14
0x18003fc88  pop     r13
0x18003fc8a  pop     r12
0x18003fc8c  pop     rdi
0x18003fc8d  pop     rsi
0x18003fc8e  pop     rbp
0x18003fc8f  retn
```
