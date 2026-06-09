# I_CAOIDDelete(ushort const *,ldap *)

- ea: `0x18002c028`
- end: `0x18002c223`
- name: `?I_CAOIDDelete@@YAJPEBGPEAUldap@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ldap *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002cb10`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x18000e130`
- `0x18000e52c`
- `0x180011600`
- `0x180012680`
- `0x18002c028`
- `0x18002c830`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c1e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c1e4`
- `WLDAP32!__imp_ldap_unbind` at `0x18002c20c`
- `WLDAP32!__imp_ldap_unbind` at `0x18002c20c`
- `WLDAP32!__imp_ldap_delete_sW` at `0x18002c1c0`
- `WLDAP32!__imp_ldap_delete_sW` at `0x18002c1c0`

## string_xrefs

- `0x18002c19a`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall I_CAOIDDelete(const unsigned __int16 *a1, struct ldap *a2)
{
  struct ldap *v2; // rbp
  unsigned int v4; // ebx
  LDAP *v5; // rdi
  int v6; // eax
  int v7; // eax
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // rsi
  unsigned int v10; // eax
  unsigned __int16 *v11; // r14
  int v12; // edx
  unsigned int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // rax
  ULONG v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // edx
  unsigned __int16 **v22; // [rsp+20h] [rbp-48h]
  LDAP *ld; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v24; // [rsp+80h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+20h] BYREF

  v2 = a2;
  v24 = 0;
  hMem = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    CSPrintErrorLineFile(0x6940336u, -2147024809);
    return v4;
  }
  ld = 0;
  v5 = 0;
  if ( a2 )
  {
LABEL_7:
    v7 = CAGetAuthoritativeDomainDn(v2, 0, &v24);
    v8 = v24;
    v4 = v7;
    if ( v7 )
    {
      CSPrintErrorLineFile(0x69E0336u, v7);
LABEL_26:
      if ( v8 )
        CertFreeString(v8);
      goto LABEL_28;
    }
    v9 = 0;
    v10 = myOIDHashOIDToString(a1, (unsigned __int16 **)&hMem);
    v11 = (unsigned __int16 *)hMem;
    v4 = v10;
    if ( v10 )
    {
      v12 = v10;
      v13 = 111346486;
    }
    else
    {
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( v8[v15] );
      do
        ++v14;
      while ( *((_WORD *)hMem + v14) );
      v16 = v14 + v15 + 47;
      if ( v16 <= 0x10000 )
      {
        v17 = CertAllocStringLen(0, (int)v16 - 1);
        v9 = v17;
        if ( v17 )
        {
          StringCchCopyW(v17, v16, L"CN=");
          StringCchCatW(v9, v16, v11);
          StringCchCatW(v9, v16, L",");
          StringCchCatW(v9, v16, L"CN=OID,CN=Public Key Services,CN=Services,");
          StringCchCatW(v9, v16, v8);
          v18 = ldap_delete_sW(v2, v9);
          v20 = 0;
          if ( v18 != 32 )
            v20 = v18;
          v4 = myHLdapError3(v2, v20, 0, v19, v22);
          goto LABEL_22;
        }
        v4 = -2147024882;
        v13 = 112132918;
        v12 = -2147024882;
      }
      else
      {
        v4 = -2147024362;
        v13 = 111739702;
        v12 = -2147024362;
      }
    }
    CSPrintErrorLineFile(v13, v12);
LABEL_22:
    if ( v11 )
      LocalFree(v11);
    if ( v9 )
      CertFreeString(v9);
    goto LABEL_26;
  }
  v6 = myTimeOutRobustLdapBind(&ld);
  v4 = v6;
  if ( !v6 )
  {
    v5 = ld;
    v2 = ld;
    goto LABEL_7;
  }
  CSPrintErrorLineFile(0x9E0336u, v6);
  CSPrintErrorLineFile(0x6980336u, v4);
  v5 = ld;
LABEL_28:
  if ( v5 )
    ldap_unbind(v5);
  return v4;
}

```

## disassembly

```asm
0x18002c028  mov     rax, rsp
0x18002c02b  push    rbx
0x18002c02c  push    rbp
0x18002c02d  push    rsi
0x18002c02e  push    rdi
0x18002c02f  push    r12
0x18002c031  push    r14
0x18002c033  push    r15
0x18002c035  sub     rsp, 30h
0x18002c039  xor     r12d, r12d
0x18002c03c  mov     rbp, rdx
0x18002c03f  mov     [rax+18h], r12
0x18002c043  mov     r14, rcx
0x18002c046  mov     [rax+20h], r12
0x18002c04a  test    rcx, rcx
0x18002c04d  jnz     short loc_18002C065
0x18002c04f  mov     ebx, 80070057h
0x18002c054  mov     ecx, 6940336h; unsigned int
0x18002c059  mov     edx, ebx; int
0x18002c05b  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c060  jmp     loc_18002C212
0x18002c065  mov     [rsp+68h+ld], r12
0x18002c06a  mov     rdi, r12
0x18002c06d  test    rdx, rdx
0x18002c070  jnz     short loc_18002C0AC
0x18002c072  lea     rcx, [rsp+68h+ld]; struct ldap **
0x18002c077  call    ?myTimeOutRobustLdapBind@@YAJPEAPEAUldap@@@Z; myTimeOutRobustLdapBind(ldap * *)
0x18002c07c  mov     ebx, eax
0x18002c07e  test    eax, eax
0x18002c080  jz      short loc_18002C0A4
0x18002c082  mov     edx, eax; int
0x18002c084  mov     ecx, 9E0336h; unsigned int
0x18002c089  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c08e  mov     edx, ebx; int
0x18002c090  mov     ecx, 6980336h; unsigned int
0x18002c095  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c09a  mov     rdi, [rsp+68h+ld]
0x18002c09f  jmp     loc_18002C204
0x18002c0a4  mov     rdi, [rsp+68h+ld]
0x18002c0a9  mov     rbp, rdi
0x18002c0ac  lea     r8, [rsp+68h+arg_10]; unsigned __int16 **
0x18002c0b4  xor     edx, edx; unsigned __int16 **
0x18002c0b6  mov     rcx, rbp; struct ldap *
0x18002c0b9  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x18002c0be  mov     r15, [rsp+68h+arg_10]
0x18002c0c6  mov     ebx, eax
0x18002c0c8  test    eax, eax
0x18002c0ca  jz      short loc_18002C0DD
0x18002c0cc  mov     edx, eax; int
0x18002c0ce  mov     ecx, 69E0336h; unsigned int
0x18002c0d3  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c0d8  jmp     loc_18002C1F7
0x18002c0dd  lea     rdx, [rsp+68h+hMem]; unsigned __int16 **
0x18002c0e5  mov     rcx, r14; unsigned __int16 *
0x18002c0e8  mov     rsi, r12
0x18002c0eb  call    ?myOIDHashOIDToString@@YAJPEBGPEAPEAG@Z; myOIDHashOIDToString(ushort const *,ushort * *)
0x18002c0f0  mov     r14, [rsp+68h+hMem]
0x18002c0f8  mov     ebx, eax
0x18002c0fa  test    eax, eax
0x18002c0fc  jz      short loc_18002C10F
0x18002c0fe  mov     edx, eax; int
0x18002c100  mov     ecx, 6A30336h; unsigned int
0x18002c105  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c10a  jmp     loc_18002C1DC
0x18002c10f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c113  mov     rcx, rax
0x18002c116  inc     rcx
0x18002c119  cmp     [r15+rcx*2], r12w
0x18002c11e  jnz     short loc_18002C116
0x18002c120  inc     rax
0x18002c123  cmp     [r14+rax*2], r12w
0x18002c128  jnz     short loc_18002C120
0x18002c12a  lea     rbx, [rcx+2Fh]
0x18002c12e  add     rbx, rax
0x18002c131  cmp     rbx, 10000h
0x18002c138  jbe     short loc_18002C148
0x18002c13a  mov     ebx, 80070216h
0x18002c13f  mov     ecx, 6A90336h
0x18002c144  mov     edx, ebx
0x18002c146  jmp     short loc_18002C105
0x18002c148  lea     edx, [rbx-1]; unsigned int
0x18002c14b  xor     ecx, ecx; Src
0x18002c14d  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002c152  mov     rsi, rax
0x18002c155  test    rax, rax
0x18002c158  jnz     short loc_18002C168
0x18002c15a  mov     ebx, 8007000Eh
0x18002c15f  mov     ecx, 6AF0336h
0x18002c164  mov     edx, ebx
0x18002c166  jmp     short loc_18002C105
0x18002c168  lea     r8, aCn_2; "CN="
0x18002c16f  mov     rdx, rbx; unsigned __int64
0x18002c172  mov     rcx, rsi; unsigned __int16 *
0x18002c175  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c17a  mov     r8, r14; unsigned __int16 *
0x18002c17d  mov     rdx, rbx; unsigned __int64
0x18002c180  mov     rcx, rsi; unsigned __int16 *
0x18002c183  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c188  lea     r8, asc_180063424; ","
0x18002c18f  mov     rdx, rbx; unsigned __int64
0x18002c192  mov     rcx, rsi; unsigned __int16 *
0x18002c195  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c19a  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18002c1a1  mov     rdx, rbx; unsigned __int64
0x18002c1a4  mov     rcx, rsi; unsigned __int16 *
0x18002c1a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c1ac  mov     r8, r15; unsigned __int16 *
0x18002c1af  mov     rdx, rbx; unsigned __int64
0x18002c1b2  mov     rcx, rsi; unsigned __int16 *
0x18002c1b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c1ba  mov     rdx, rsi; dn
0x18002c1bd  mov     rcx, rbp; ld
0x18002c1c0  call    cs:__imp_ldap_delete_sW
0x18002c1c6  mov     edx, r12d
0x18002c1c9  mov     rcx, rbp; ld
0x18002c1cc  cmp     eax, 20h ; ' '
0x18002c1cf  cmovnz  edx, eax; unsigned int
0x18002c1d2  xor     r8d, r8d; unsigned int
0x18002c1d5  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002c1da  mov     ebx, eax
0x18002c1dc  test    r14, r14
0x18002c1df  jz      short loc_18002C1EA
0x18002c1e1  mov     rcx, r14; hMem
0x18002c1e4  call    cs:__imp_LocalFree
0x18002c1ea  test    rsi, rsi
0x18002c1ed  jz      short loc_18002C1F7
0x18002c1ef  mov     rcx, rsi; unsigned __int16 *
0x18002c1f2  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002c1f7  test    r15, r15
0x18002c1fa  jz      short loc_18002C204
0x18002c1fc  mov     rcx, r15; unsigned __int16 *
0x18002c1ff  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002c204  test    rdi, rdi
0x18002c207  jz      short loc_18002C212
0x18002c209  mov     rcx, rdi; ld
0x18002c20c  call    cs:__imp_ldap_unbind
0x18002c212  mov     eax, ebx
0x18002c214  add     rsp, 30h
0x18002c218  pop     r15
0x18002c21a  pop     r14
0x18002c21c  pop     r12
0x18002c21e  pop     rdi
0x18002c21f  pop     rsi
0x18002c220  pop     rbp
0x18002c221  pop     rbx
0x18002c222  retn
```
