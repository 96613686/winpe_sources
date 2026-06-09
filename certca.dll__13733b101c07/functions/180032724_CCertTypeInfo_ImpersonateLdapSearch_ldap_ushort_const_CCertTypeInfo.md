# CCertTypeInfo::_ImpersonateLdapSearch(ldap *,ushort const *,CCertTypeInfo * *)

- ea: `0x180032724`
- end: `0x1800327bd`
- name: `?_ImpersonateLdapSearch@CCertTypeInfo@@KAJPEAUldap@@PEBGPEAPEAV1@@Z`
- size: `153`
- prototype: `__int64 __fastcall(LDAP *ld, const unsigned __int16 *, struct CCertTypeInfo **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a630`
- `0x18000a920`

## callees

- `0x180008400`
- `0x18000b3f0`
- `0x180012450`
- `0x1800185b4`
- `0x18002fa14`
- `0x180032724`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032795`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180032795`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_ImpersonateLdapSearch(
        LDAP *ld,
        const unsigned __int16 *a2,
        struct CCertTypeInfo **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // ecx
  int TemplateList; // eax
  unsigned int v10; // edx
  CCertTypeInfo *v11; // rcx
  struct CCertTypeInfo *v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v6 = myImpersonateAccountOrSid(
         (const unsigned __int16 *)ld,
         (enum WELL_KNOWN_SID_TYPE)a2,
         (const unsigned __int16 *)a3);
  v7 = v6;
  if ( v6 )
  {
    v8 = 170853160;
LABEL_10:
    CSPrintErrorLineFile(v8, v6);
    return v7;
  }
  TemplateList = CCertTypeInfo::_LdapSearchAndMakeTemplateList(ld, 0x20u, a2, &v13);
  v7 = TemplateList;
  if ( TemplateList )
  {
    CSPrintErrorLineFile(0xA370328u, TemplateList);
    v11 = v13;
  }
  else
  {
    v11 = 0;
    *a3 = v13;
    v7 = 0;
  }
  if ( v11 )
    CCertTypeInfo::`scalar deleting destructor'(v11, v10);
  if ( !RevertToSelf() )
  {
    v6 = myHLastError();
    v7 = v6;
    v8 = 172426024;
    goto LABEL_10;
  }
  return v7;
}

```

## disassembly

```asm
0x180032724  push    rbx
0x180032726  push    rbp
0x180032727  push    rsi
0x180032728  push    rdi
0x180032729  sub     rsp, 28h
0x18003272d  mov     rdi, r8
0x180032730  mov     [rsp+48h+arg_18], 0
0x180032739  mov     rsi, rdx
0x18003273c  mov     rbp, rcx
0x18003273f  call    ?myImpersonateAccountOrSid@@YAJPEBGW4WELL_KNOWN_SID_TYPE@@0@Z; myImpersonateAccountOrSid(ushort const *,WELL_KNOWN_SID_TYPE,ushort const *)
0x180032744  mov     ebx, eax
0x180032746  test    eax, eax
0x180032748  jz      short loc_180032751
0x18003274a  mov     ecx, 0A2F0328h
0x18003274f  jmp     short loc_1800327AB
0x180032751  lea     r9, [rsp+48h+arg_18]; struct CCertTypeInfo **
0x180032756  mov     r8, rsi; unsigned __int16 *
0x180032759  mov     edx, 20h ; ' '; unsigned int
0x18003275e  mov     rcx, rbp; ld
0x180032761  call    ?_LdapSearchAndMakeTemplateList@CCertTypeInfo@@KAJPEAUldap@@KPEBGPEAPEAV1@@Z; CCertTypeInfo::_LdapSearchAndMakeTemplateList(ldap *,ulong,ushort const *,CCertTypeInfo * *)
0x180032766  mov     ebx, eax
0x180032768  test    eax, eax
0x18003276a  jz      short loc_18003277F
0x18003276c  mov     edx, eax; int
0x18003276e  mov     ecx, 0A370328h; unsigned int
0x180032773  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032778  mov     rcx, [rsp+48h+arg_18]
0x18003277d  jmp     short loc_18003278B
0x18003277f  mov     rax, [rsp+48h+arg_18]
0x180032784  xor     ecx, ecx; this
0x180032786  mov     [rdi], rax
0x180032789  xor     ebx, ebx
0x18003278b  test    rcx, rcx
0x18003278e  jz      short loc_180032795
0x180032790  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x180032795  call    cs:__imp_RevertToSelf
0x18003279b  test    eax, eax
0x18003279d  jnz     short loc_1800327B2
0x18003279f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800327a4  mov     ebx, eax
0x1800327a6  mov     ecx, 0A470328h; unsigned int
0x1800327ab  mov     edx, eax; int
0x1800327ad  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800327b2  mov     eax, ebx
0x1800327b4  add     rsp, 28h
0x1800327b8  pop     rdi
0x1800327b9  pop     rsi
0x1800327ba  pop     rbp
0x1800327bb  pop     rbx
0x1800327bc  retn
```
