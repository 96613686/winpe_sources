# QueryInformationFromTargetForestViaLDAP(ushort *,_TRUST_SCAN_CONTEXT *)

- ea: `0x180031ff8`
- end: `0x180032193`
- name: `?QueryInformationFromTargetForestViaLDAP@@YAKPEAGPEAU_TRUST_SCAN_CONTEXT@@@Z`
- size: `411`
- prototype: `unsigned int __fastcall(unsigned __int16 *, struct _TRUST_SCAN_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003222c`

## callees

- `0x180007f8c`
- `0x18000fd40`
- `0x18002f474`
- `0x1800309d0`
- `0x180030aa8`
- `0x180030d3c`
- `0x180030ecc`
- `0x180031ff8`
- `0x1800329ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800320f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800320f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003216e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003216e`
- `WLDAP32!__imp_ldap_unbind` at `0x180032179`
- `WLDAP32!__imp_ldap_unbind` at `0x180032179`

## string_xrefs

- `0x1800320ae`: `configurationNamingContext`

## pseudocode

```c
__int64 __fastcall QueryInformationFromTargetForestViaLDAP(
        unsigned __int16 *a1,
        struct _TRUST_SCAN_CONTEXT *a2,
        int a3)
{
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rsi
  unsigned int v7; // eax
  unsigned __int16 *v8; // rdx
  unsigned int PartitionsContainerData; // ebx
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  int v15; // eax
  LDAP *ld; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v18; // [rsp+70h] [rbp+18h] BYREF

  ld = 0;
  v4 = 0;
  v18 = 0;
  v5 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)a1, *((_QWORD *)a2 + 2));
  v7 = LdapOpenConnectionAndBind(a1, *((unsigned __int16 **)a2 + 2), &ld);
  PartitionsContainerData = v7;
  if ( v7 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, v7);
  }
  else
  {
    v10 = LdapQueryRootDseStringAttribute(ld, v8, &v18);
    PartitionsContainerData = v10;
    if ( v10 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
          (unsigned int)L"configurationNamingContext",
          v10);
      v4 = v18;
    }
    else
    {
      v4 = v18;
      v11 = -1;
      do
        ++v11;
      while ( v18[v11] );
      v12 = (unsigned int)(v11 + 16);
      v13 = (unsigned int)v12;
      v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v12);
      v5 = v14;
      if ( v14 )
      {
        v15 = StringCchPrintfW(v14, v13, L"CN=Partitions,%s", v4);
        PartitionsContainerData = v15;
        if ( v15 >= 0 )
        {
          PartitionsContainerData = LdapQueryPartitionsContainerData(ld, a1, v5, a2);
          if ( !PartitionsContainerData )
            PartitionsContainerData = LdapQueryCrossRefObjects(ld, a1, v5, a2);
        }
        else if ( (v15 & 0x1FFF0000) == 0x70000 )
        {
          PartitionsContainerData = (unsigned __int16)v15;
        }
      }
      else
      {
        PartitionsContainerData = 8;
      }
    }
  }
  LocalFree(v5);
  LocalFree(v4);
  ldap_unbind(ld);
  return PartitionsContainerData;
}

```

## disassembly

```asm
0x180031ff8  mov     r11, rsp
0x180031ffb  mov     [r11+8], rbx
0x180031fff  push    rsi
0x180032000  push    rdi
0x180032001  push    r12
0x180032003  push    r14
0x180032005  push    r15
0x180032007  sub     rsp, 30h
0x18003200b  xor     r12d, r12d
0x18003200e  mov     r15, rdx
0x180032011  mov     [r11+10h], r12
0x180032015  mov     edi, r12d
0x180032018  mov     [r11+18h], r12
0x18003201c  mov     esi, r12d
0x18003201f  mov     r14, rcx
0x180032022  mov     rcx, cs:WPP_GLOBAL_Control
0x180032029  test    byte ptr [rcx+1Ch], 10h
0x18003202d  jz      short loc_180032043
0x18003202f  mov     rax, [rdx+10h]
0x180032033  mov     r9, r14
0x180032036  mov     rcx, [rcx+10h]
0x18003203a  mov     [r11-38h], rax
0x18003203e  call    WPP_SF_SS
0x180032043  mov     rdx, [r15+10h]; unsigned __int16 *
0x180032047  lea     r8, [rsp+58h+ld]; struct ldap **
0x18003204c  mov     rcx, r14; unsigned __int16 *
0x18003204f  call    ?LdapOpenConnectionAndBind@@YAKPEAG0PEAPEAUldap@@@Z; LdapOpenConnectionAndBind(ushort *,ushort *,ldap * *)
0x180032054  mov     ebx, eax
0x180032056  test    eax, eax
0x180032058  jz      short loc_180032088
0x18003205a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032061  test    byte ptr [rcx+1Ch], 10h
0x180032065  jz      loc_180032162
0x18003206b  mov     rcx, [rcx+10h]
0x18003206f  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x180032076  mov     edx, 18h
0x18003207b  mov     r9d, eax
0x18003207e  call    WPP_SF_d
0x180032083  jmp     loc_180032162
0x180032088  mov     rcx, [rsp+58h+ld]; ld
0x18003208d  lea     r8, [rsp+58h+arg_10]; unsigned __int16 **
0x180032092  call    ?LdapQueryRootDseStringAttribute@@YAKPEAUldap@@PEAGPEAPEAG@Z; LdapQueryRootDseStringAttribute(ldap *,ushort *,ushort * *)
0x180032097  mov     ebx, eax
0x180032099  test    eax, eax
0x18003209b  jz      short loc_1800320D4
0x18003209d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320a4  test    byte ptr [rcx+1Ch], 10h
0x1800320a8  jz      short loc_1800320CA
0x1800320aa  mov     rcx, [rcx+10h]
0x1800320ae  lea     r9, aConfigurationn; "configurationNamingContext"
0x1800320b5  mov     edx, 19h
0x1800320ba  mov     [rsp+58h+var_38], eax
0x1800320be  lea     r8, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x1800320c5  call    WPP_SF_SD
0x1800320ca  mov     rdi, [rsp+58h+arg_10]
0x1800320cf  jmp     loc_180032162
0x1800320d4  mov     rdi, [rsp+58h+arg_10]
0x1800320d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800320dd  inc     rax
0x1800320e0  cmp     [rdi+rax*2], r12w
0x1800320e5  jnz     short loc_1800320DD
0x1800320e7  add     eax, 10h
0x1800320ea  mov     ecx, 40h ; '@'; uFlags
0x1800320ef  mov     ebx, eax
0x1800320f1  lea     rdx, [rax+rax]; uBytes
0x1800320f5  call    cs:__imp_LocalAlloc
0x1800320fb  mov     rsi, rax
0x1800320fe  test    rax, rax
0x180032101  jnz     short loc_180032108
0x180032103  lea     ebx, [rax+8]
0x180032106  jmp     short loc_180032162
0x180032108  mov     r9, rdi
0x18003210b  lea     r8, aCnPartitionsS; "CN=Partitions,%s"
0x180032112  mov     rdx, rbx; unsigned __int64
0x180032115  mov     rcx, rsi; unsigned __int16 *
0x180032118  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003211d  mov     ebx, eax
0x18003211f  test    eax, eax
0x180032121  jns     short loc_180032134
0x180032123  and     eax, 1FFF0000h
0x180032128  cmp     eax, 70000h
0x18003212d  jnz     short loc_180032162
0x18003212f  movzx   ebx, bx
0x180032132  jmp     short loc_180032162
0x180032134  mov     rcx, [rsp+58h+ld]; struct ldap *
0x180032139  mov     r9, r15; struct _TRUST_SCAN_CONTEXT *
0x18003213c  mov     r8, rsi; unsigned __int16 *
0x18003213f  mov     rdx, r14; unsigned __int16 *
0x180032142  call    ?LdapQueryPartitionsContainerData@@YAKPEAUldap@@PEAG1PEAU_TRUST_SCAN_CONTEXT@@@Z; LdapQueryPartitionsContainerData(ldap *,ushort *,ushort *,_TRUST_SCAN_CONTEXT *)
0x180032147  mov     ebx, eax
0x180032149  test    eax, eax
0x18003214b  jnz     short loc_180032162
0x18003214d  mov     rcx, [rsp+58h+ld]; struct ldap *
0x180032152  mov     r9, r15; struct _TRUST_SCAN_CONTEXT *
0x180032155  mov     r8, rsi; unsigned __int16 *
0x180032158  mov     rdx, r14; unsigned __int16 *
0x18003215b  call    ?LdapQueryCrossRefObjects@@YAKPEAUldap@@PEAG1PEAU_TRUST_SCAN_CONTEXT@@@Z; LdapQueryCrossRefObjects(ldap *,ushort *,ushort *,_TRUST_SCAN_CONTEXT *)
0x180032160  mov     ebx, eax
0x180032162  mov     rcx, rsi; hMem
0x180032165  call    cs:__imp_LocalFree
0x18003216b  mov     rcx, rdi; hMem
0x18003216e  call    cs:__imp_LocalFree
0x180032174  mov     rcx, [rsp+58h+ld]; ld
0x180032179  call    cs:__imp_ldap_unbind
0x18003217f  mov     eax, ebx
0x180032181  mov     rbx, [rsp+58h+arg_0]
0x180032186  add     rsp, 30h
0x18003218a  pop     r15
0x18003218c  pop     r14
0x18003218e  pop     r12
0x180032190  pop     rdi
0x180032191  pop     rsi
0x180032192  retn
```
