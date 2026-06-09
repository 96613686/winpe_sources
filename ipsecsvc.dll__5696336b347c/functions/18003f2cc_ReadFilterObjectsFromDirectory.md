# ReadFilterObjectsFromDirectory

- ea: `0x18003f2cc`
- end: `0x18003f56e`
- name: `ReadFilterObjectsFromDirectory`
- size: `674`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

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
- `0x18003f2cc`
- `0x180040380`
- `0x180042b70`
- `0x180042ef8`

## import_xrefs

- `WLDAP32!__imp_ldap_count_entries` at `0x18003f3e3`
- `WLDAP32!__imp_ldap_count_entries` at `0x18003f3e3`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003f555`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003f555`

## pseudocode

```c
__int64 __fastcall ReadFilterObjectsFromDirectory(
        LDAP *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6)
{
  __int64 v6; // r13
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  ULONG v15; // eax
  ULONG v16; // r12d
  void *v17; // rsi
  __int64 v18; // rdi
  ULONG i; // r14d
  unsigned int v20; // eax
  LDAPMessage *res; // [rsp+30h] [rbp-38h] BYREF
  __int64 v22; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-28h] BYREF
  SIZE_T v24; // [rsp+48h] [rbp-20h] BYREF
  __int64 v25[3]; // [rsp+50h] [rbp-18h] BYREF

  v6 = 0;
  res = 0;
  v22 = 0;
  lpMem = 0;
  v25[0] = 0;
  v24 = 0;
  if ( !a4 )
  {
    *a5 = 0;
    *a6 = 0;
    return 0;
  }
  v10 = GenerateQuery(a3, a4, L"(&(objectclass=ipsecFilter)", &lpMem);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = 31;
LABEL_7:
      v13 = v10;
LABEL_8:
      WPP_SF_d(v11[2], v12, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v13);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v14 = LdapSearchHelper((int)a1, a2, 1, (int)lpMem, &FilterDNAttributes, &res);
  v10 = v14;
  if ( v14 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v12 = 32;
    goto LABEL_13;
  }
  v15 = ldap_count_entries(a1, res);
  v16 = v15;
  if ( v15 )
  {
    v14 = NsuSizeTMultiply(v15, 8, &v24);
    v10 = v14;
    if ( !v14 )
    {
      v17 = IpsecAllocMem(v24);
      if ( v17 )
      {
        v18 = 0;
        for ( i = 0; ; ++i )
        {
          if ( i >= v16 )
          {
            v10 = 0;
            goto LABEL_40;
          }
          if ( i )
          {
            LdapNextEntry(a1, v6, &v22);
          }
          else
          {
            v20 = LdapFirstEntry(a1, res, &v22);
            v10 = v20;
            if ( v20 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids, v20);
              }
              FreeIpsecFilterObjects(v17);
              goto LABEL_34;
            }
          }
          v6 = v22;
          if ( !(unsigned int)UnMarshallFilterObject(a1, v22, v25) )
          {
            *((_QWORD *)v17 + v18) = v25[0];
            v18 = (unsigned int)(v18 + 1);
          }
        }
      }
      v10 = 14;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_34;
      v12 = 35;
      goto LABEL_7;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v12 = 34;
LABEL_13:
    v13 = v14;
    goto LABEL_8;
  }
  v10 = 8202;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v12 = 33;
    goto LABEL_7;
  }
LABEL_34:
  LODWORD(v18) = 0;
  v17 = 0;
LABEL_40:
  *a5 = v17;
  *a6 = v18;
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( res )
    ldap_msgfree(res);
  return v10;
}

```

## disassembly

```asm
0x18003f2cc  push    rbp
0x18003f2ce  push    rbx
0x18003f2cf  push    rsi
0x18003f2d0  push    rdi
0x18003f2d1  push    r12
0x18003f2d3  push    r13
0x18003f2d5  push    r14
0x18003f2d7  push    r15
0x18003f2d9  mov     rbp, rsp
0x18003f2dc  sub     rsp, 68h
0x18003f2e0  xor     r13d, r13d
0x18003f2e3  mov     [rbp+res], 0
0x18003f2eb  mov     [rbp+var_30], r13
0x18003f2ef  mov     eax, r9d
0x18003f2f2  mov     [rbp+lpMem], r13
0x18003f2f6  mov     r10, r8
0x18003f2f9  mov     [rbp+var_18], r13
0x18003f2fd  mov     rdi, rdx
0x18003f300  mov     [rbp+var_20], r13
0x18003f304  mov     r15, rcx
0x18003f307  test    r9d, r9d
0x18003f30a  jnz     short loc_18003F321
0x18003f30c  mov     rax, [rbp+arg_20]
0x18003f310  mov     [rax], r13
0x18003f313  mov     rax, [rbp+arg_28]
0x18003f317  mov     [rax], r13d
0x18003f31a  xor     eax, eax
0x18003f31c  jmp     loc_18003F55D
0x18003f321  lea     r9, [rbp+lpMem]
0x18003f325  mov     edx, eax
0x18003f327  lea     r8, aObjectclassIps; "(&(objectclass=ipsecFilter)"
0x18003f32e  mov     rcx, r10
0x18003f331  call    GenerateQuery
0x18003f336  mov     ebx, eax
0x18003f338  mov     rax, [rbp+lpMem]
0x18003f33c  mov     [rbp+lpMem], rax
0x18003f340  test    ebx, ebx
0x18003f342  jz      short loc_18003F382
0x18003f344  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f34b  lea     rdx, WPP_GLOBAL_Control
0x18003f352  cmp     rcx, rdx
0x18003f355  jz      loc_18003F4F8
0x18003f35b  test    byte ptr [rcx+1Ch], 10h
0x18003f35f  jz      loc_18003F4F8
0x18003f365  mov     edx, 1Fh
0x18003f36a  mov     r9d, ebx
0x18003f36d  mov     rcx, [rcx+10h]
0x18003f371  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003f378  call    WPP_SF_d
0x18003f37d  jmp     loc_18003F4F8
0x18003f382  lea     rcx, [rbp+res]
0x18003f386  mov     r9, rax; int
0x18003f389  mov     [rsp+68h+var_40], rcx; LDAPMessage **
0x18003f38e  mov     r8d, 1; int
0x18003f394  lea     rcx, FilterDNAttributes
0x18003f39b  mov     rdx, rdi; int
0x18003f39e  mov     [rsp+68h+var_48], rcx; PZPWSTR
0x18003f3a3  mov     rcx, r15; int
0x18003f3a6  call    LdapSearchHelper
0x18003f3ab  mov     ebx, eax
0x18003f3ad  test    eax, eax
0x18003f3af  jz      short loc_18003F3DC
0x18003f3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3b8  lea     rdx, WPP_GLOBAL_Control
0x18003f3bf  cmp     rcx, rdx
0x18003f3c2  jz      loc_18003F4F8
0x18003f3c8  test    byte ptr [rcx+1Ch], 10h
0x18003f3cc  jz      loc_18003F4F8
0x18003f3d2  mov     edx, 20h ; ' '
0x18003f3d7  mov     r9d, eax
0x18003f3da  jmp     short loc_18003F36D
0x18003f3dc  mov     rdx, [rbp+res]; res
0x18003f3e0  mov     rcx, r15; ld
0x18003f3e3  call    cs:__imp_ldap_count_entries
0x18003f3e9  mov     r12d, eax
0x18003f3ec  test    eax, eax
0x18003f3ee  jnz     short loc_18003F41E
0x18003f3f0  mov     ebx, 200Ah
0x18003f3f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3fc  lea     rdx, WPP_GLOBAL_Control
0x18003f403  cmp     rcx, rdx
0x18003f406  jz      loc_18003F4F8
0x18003f40c  test    byte ptr [rcx+1Ch], 10h
0x18003f410  jz      loc_18003F4F8
0x18003f416  lea     edx, [rax+21h]
0x18003f419  jmp     loc_18003F36A
0x18003f41e  mov     rcx, r12
0x18003f421  lea     r8, [rbp+var_20]
0x18003f425  mov     edx, 8
0x18003f42a  call    NsuSizeTMultiply
0x18003f42f  mov     ebx, eax
0x18003f431  test    eax, eax
0x18003f433  jz      short loc_18003F460
0x18003f435  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f43c  lea     rdx, WPP_GLOBAL_Control
0x18003f443  cmp     rcx, rdx
0x18003f446  jz      loc_18003F4F8
0x18003f44c  test    byte ptr [rcx+1Ch], 10h
0x18003f450  jz      loc_18003F4F8
0x18003f456  mov     edx, 22h ; '"'
0x18003f45b  jmp     loc_18003F3D7
0x18003f460  mov     rcx, [rbp+var_20]
0x18003f464  call    IpsecAllocMem
0x18003f469  mov     rsi, rax
0x18003f46c  test    rax, rax
0x18003f46f  jnz     short loc_18003F495
0x18003f471  lea     ebx, [rax+0Eh]
0x18003f474  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f47b  lea     rdx, WPP_GLOBAL_Control
0x18003f482  cmp     rcx, rdx
0x18003f485  jz      short loc_18003F4F8
0x18003f487  test    byte ptr [rcx+1Ch], 10h
0x18003f48b  jz      short loc_18003F4F8
0x18003f48d  lea     edx, [rax+23h]
0x18003f490  jmp     loc_18003F36A
0x18003f495  xor     edi, edi
0x18003f497  xor     r14d, r14d
0x18003f49a  cmp     r14d, r12d
0x18003f49d  jnb     loc_18003F52F
0x18003f4a3  lea     r8, [rbp+var_30]
0x18003f4a7  mov     rcx, r15
0x18003f4aa  test    r14d, r14d
0x18003f4ad  jnz     short loc_18003F4FE
0x18003f4af  mov     rdx, [rbp+res]
0x18003f4b3  call    LdapFirstEntry
0x18003f4b8  mov     ebx, eax
0x18003f4ba  test    eax, eax
0x18003f4bc  jz      short loc_18003F506
0x18003f4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f4c5  lea     rdx, WPP_GLOBAL_Control
0x18003f4cc  cmp     rcx, rdx
0x18003f4cf  jz      short loc_18003F4EE
0x18003f4d1  test    byte ptr [rcx+1Ch], 10h
0x18003f4d5  jz      short loc_18003F4EE
0x18003f4d7  mov     rcx, [rcx+10h]
0x18003f4db  lea     edx, [r14+24h]
0x18003f4df  mov     r9d, eax
0x18003f4e2  lea     r8, WPP_60dba0e50d1c3925ddb354feb94251e3_Traceguids
0x18003f4e9  call    WPP_SF_d
0x18003f4ee  mov     edx, edi
0x18003f4f0  mov     rcx, rsi; lpMem
0x18003f4f3  call    FreeIpsecFilterObjects
0x18003f4f8  xor     edi, edi
0x18003f4fa  xor     esi, esi
0x18003f4fc  jmp     short loc_18003F531
0x18003f4fe  mov     rdx, r13
0x18003f501  call    LdapNextEntry
0x18003f506  mov     r13, [rbp+var_30]
0x18003f50a  lea     r8, [rbp+var_18]
0x18003f50e  mov     rdx, r13
0x18003f511  mov     rcx, r15
0x18003f514  call    UnMarshallFilterObject
0x18003f519  test    eax, eax
0x18003f51b  jnz     short loc_18003F527
0x18003f51d  mov     rax, [rbp+var_18]
0x18003f521  mov     [rsi+rdi*8], rax
0x18003f525  inc     edi
0x18003f527  inc     r14d
0x18003f52a  jmp     loc_18003F49A
0x18003f52f  xor     ebx, ebx
0x18003f531  mov     rax, [rbp+arg_20]
0x18003f535  mov     [rax], rsi
0x18003f538  mov     rax, [rbp+arg_28]
0x18003f53c  mov     [rax], edi
0x18003f53e  mov     rcx, [rbp+lpMem]; lpMem
0x18003f542  test    rcx, rcx
0x18003f545  jz      short loc_18003F54C
0x18003f547  call    IpsecFreeMem
0x18003f54c  mov     rcx, [rbp+res]; res
0x18003f550  test    rcx, rcx
0x18003f553  jz      short loc_18003F55B
0x18003f555  call    cs:__imp_ldap_msgfree
0x18003f55b  mov     eax, ebx
0x18003f55d  add     rsp, 68h
0x18003f561  pop     r15
0x18003f563  pop     r14
0x18003f565  pop     r13
0x18003f567  pop     r12
0x18003f569  pop     rdi
0x18003f56a  pop     rsi
0x18003f56b  pop     rbx
0x18003f56c  pop     rbp
0x18003f56d  retn
```
