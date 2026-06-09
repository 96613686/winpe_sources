# NetpGetServiceAccountObject(ldap *,ushort const *,int *,ushort * *,ushort const *,int *)

- ea: `0x1800669b0`
- end: `0x180066b79`
- name: `?NetpGetServiceAccountObject@@YAJPEAUldap@@PEBGPEAHPEAPEAG12@Z`
- size: `457`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, const unsigned __int16 *@<rdx>, int *@<r8>, unsigned __int16 **@<r9>, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180065520`
- `0x180067400`
- `0x180067760`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x180065d90`
- `0x18006655c`
- `0x1800669b0`
- `0x180066b80`
- `0x180066c78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180066a4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180066a4d`
- `netutils!NetApiBufferFree` at `0x180066b53`
- `netutils!NetApiBufferFree` at `0x180066b53`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066b3a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066b3a`

## string_xrefs

- `0x1800669f4`: `msDS-ManagedServiceAccount`
- `0x180066a13`: `msDS-HostServiceAccountBL`
- `0x180066a68`: `Service account exists and is linked to a different owner\n`
- `0x180066ab2`: `Well-known path attribute for managed service accounts does not exist in directory.  Using default\n`
- `0x180066ad3`: `onecore\ds\netapi\svcdlls\logonsrv\server\svcacct.cxx`
- `0x180066ada`: `WellKnownPath == NULL`
- `0x180066b13`: `Failed to create new service account\n`
- `0x180066b21`: `Created new service account\n`

## pseudocode

```c
__int64 __fastcall NetpGetServiceAccountObject(
        LDAP *ld,
        const unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4,
        const unsigned __int16 *a5,
        int *a6)
{
  PWCHAR *v6; // rdi
  int *v12; // r15
  int AccountObject; // eax
  int ServiceAccount; // ebx
  const unsigned __int16 *v15; // rdx
  int SingleAttribute; // eax
  __int64 i; // rbx
  PWCHAR v18; // rdx
  char *v19; // r9
  const unsigned __int16 *v20; // rax
  const unsigned __int16 *v21; // rdx
  PWCHAR *vals; // [rsp+30h] [rbp-38h] BYREF
  LPVOID Buffer; // [rsp+80h] [rbp+18h] BYREF

  v6 = 0;
  vals = 0;
  Buffer = 0;
  if ( !a3 )
    return 3221225485LL;
  v12 = a6;
  AccountObject = NetpGetAccountObject(ld, a2, L"msDS-ManagedServiceAccount", a4, a6);
  ServiceAccount = AccountObject;
  if ( AccountObject >= 0 )
  {
    v15 = *a4;
    *a3 = 0;
    SingleAttribute = NetpGetSingleAttribute(ld, v15, L"msDS-HostServiceAccountBL", &vals);
    v6 = vals;
    if ( SingleAttribute >= 0 && vals )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v18 = v6[i];
        if ( !v18 )
          break;
        if ( !(unsigned int)_o__wcsicmp(a5, v18) )
        {
          ServiceAccount = 0;
          goto LABEL_24;
        }
      }
      NlPrintRoutine(0x40u, L"Service account exists and is linked to a different owner\n");
      ServiceAccount = -1073741734;
      goto LABEL_24;
    }
LABEL_23:
    ServiceAccount = 590080;
LABEL_24:
    if ( v6 )
      ldap_value_freeW(v6);
    goto LABEL_26;
  }
  if ( AccountObject == -1073741275 && *a3 )
  {
    *v12 = 0;
    if ( (int)NetpGetWellKnownPath(ld, (unsigned __int16 **)&Buffer) < 0 )
    {
      NlPrintRoutine(
        0x40u,
        L"Well-known path attribute for managed service accounts does not exist in directory.  Using default\n");
      v20 = (const unsigned __int16 *)Buffer;
      if ( !Buffer )
      {
LABEL_18:
        v21 = a5;
        if ( v20 )
          v21 = v20;
        ServiceAccount = NetpCreateServiceAccount(ld, v21, a2, a4);
        if ( ServiceAccount >= 0 )
        {
          NlPrintRoutine(0x40u, L"Created new service account\n");
          goto LABEL_23;
        }
        NlPrintRoutine(0x40u, L"Failed to create new service account\n");
        goto LABEL_26;
      }
      NlAssertFailed(
        "WellKnownPath == NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\svcacct.cxx",
        0x58Eu,
        v19);
    }
    v20 = (const unsigned __int16 *)Buffer;
    goto LABEL_18;
  }
LABEL_26:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  return (unsigned int)ServiceAccount;
}

```

## disassembly

```asm
0x1800669b0  mov     rax, rsp
0x1800669b3  mov     [rax+8], rbx
0x1800669b7  mov     [rax+10h], rbp
0x1800669bb  push    rsi
0x1800669bc  push    rdi
0x1800669bd  push    r12
0x1800669bf  push    r14
0x1800669c1  push    r15
0x1800669c3  sub     rsp, 40h
0x1800669c7  xor     edi, edi
0x1800669c9  mov     r14, r9
0x1800669cc  mov     [rax-38h], rdi
0x1800669d0  mov     rsi, r8
0x1800669d3  mov     [rax+18h], rdi
0x1800669d7  mov     r12, rdx
0x1800669da  mov     rbp, rcx
0x1800669dd  test    r8, r8
0x1800669e0  jnz     short loc_1800669EC
0x1800669e2  mov     eax, 0C000000Dh
0x1800669e7  jmp     loc_180066B61
0x1800669ec  mov     r15, [rsp+68h+arg_28]
0x1800669f4  lea     r8, aMsdsManagedser; "msDS-ManagedServiceAccount"
0x1800669fb  mov     [rsp+68h+var_48], r15; int *
0x180066a00  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x180066a05  mov     ebx, eax
0x180066a07  test    eax, eax
0x180066a09  js      short loc_180066A83
0x180066a0b  mov     rdx, [r14]; unsigned __int16 *
0x180066a0e  lea     r9, [rsp+68h+vals]; unsigned __int16 ***
0x180066a13  lea     r8, aMsdsHostservic_0; "msDS-HostServiceAccountBL"
0x180066a1a  mov     [rsi], edi
0x180066a1c  mov     rcx, rbp; ld
0x180066a1f  call    ?NetpGetSingleAttribute@@YAJPEAUldap@@PEBG1PEAPEAPEAG@Z; NetpGetSingleAttribute(ldap *,ushort const *,ushort const *,ushort * * *)
0x180066a24  mov     rdi, [rsp+68h+vals]
0x180066a29  test    eax, eax
0x180066a2b  js      loc_180066B2D
0x180066a31  test    rdi, rdi
0x180066a34  jz      loc_180066B2D
0x180066a3a  xor     ebx, ebx
0x180066a3c  mov     rdx, [rdi+rbx*8]
0x180066a40  test    rdx, rdx
0x180066a43  jz      short loc_180066A68
0x180066a45  mov     rcx, [rsp+68h+arg_20]
0x180066a4d  call    cs:__imp__o__wcsicmp
0x180066a54  nop     dword ptr [rax+rax+00h]
0x180066a59  test    eax, eax
0x180066a5b  jz      short loc_180066A61
0x180066a5d  inc     ebx
0x180066a5f  jmp     short loc_180066A3C
0x180066a61  xor     ebx, ebx
0x180066a63  jmp     loc_180066B32
0x180066a68  lea     rdx, aServiceAccount; "Service account exists and is linked to"...
0x180066a6f  mov     ecx, 40h ; '@'; unsigned int
0x180066a74  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066a79  mov     ebx, 0C000005Ah
0x180066a7e  jmp     loc_180066B32
0x180066a83  cmp     eax, 0C0000225h
0x180066a88  jnz     loc_180066B46
0x180066a8e  cmp     [rsi], edi
0x180066a90  jz      loc_180066B46
0x180066a96  lea     rdx, [rsp+68h+Buffer]; unsigned __int16 **
0x180066a9e  mov     [r15], edi
0x180066aa1  mov     rcx, rbp; ld
0x180066aa4  call    ?NetpGetWellKnownPath@@YAJPEAUldap@@PEAPEAG@Z; NetpGetWellKnownPath(ldap *,ushort * *)
0x180066aa9  mov     esi, 40h ; '@'
0x180066aae  test    eax, eax
0x180066ab0  jns     short loc_180066AE6
0x180066ab2  lea     rdx, aWellKnownPathA; "Well-known path attribute for managed s"...
0x180066ab9  mov     ecx, esi; unsigned int
0x180066abb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066ac0  mov     rax, [rsp+68h+Buffer]
0x180066ac8  test    rax, rax
0x180066acb  jz      short loc_180066AEE
0x180066acd  mov     r8d, 58Eh; unsigned int
0x180066ad3  lea     rdx, aOnecoreDsNetap_4; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180066ada  lea     rcx, aWellknownpathN; "WellKnownPath == NULL"
0x180066ae1  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180066ae6  mov     rax, [rsp+68h+Buffer]
0x180066aee  mov     rdx, [rsp+68h+arg_20]
0x180066af6  test    rax, rax
0x180066af9  mov     r9, r14; unsigned __int16 **
0x180066afc  mov     r8, r12; unsigned __int16 *
0x180066aff  cmovnz  rdx, rax; unsigned __int16 *
0x180066b03  mov     rcx, rbp; ld
0x180066b06  call    ?NetpCreateServiceAccount@@YAJPEAUldap@@PEBG1PEAPEAG@Z; NetpCreateServiceAccount(ldap *,ushort const *,ushort const *,ushort * *)
0x180066b0b  mov     ebx, eax
0x180066b0d  mov     ecx, esi; unsigned int
0x180066b0f  test    eax, eax
0x180066b11  jns     short loc_180066B21
0x180066b13  lea     rdx, aFailedToCreate; "Failed to create new service account\n"
0x180066b1a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066b1f  jmp     short loc_180066B46
0x180066b21  lea     rdx, aCreatedNewServ; "Created new service account\n"
0x180066b28  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066b2d  mov     ebx, 90100h
0x180066b32  test    rdi, rdi
0x180066b35  jz      short loc_180066B46
0x180066b37  mov     rcx, rdi; vals
0x180066b3a  call    cs:__imp_ldap_value_freeW
0x180066b41  nop     dword ptr [rax+rax+00h]
0x180066b46  mov     rcx, [rsp+68h+Buffer]; Buffer
0x180066b4e  test    rcx, rcx
0x180066b51  jz      short loc_180066B5F
0x180066b53  call    cs:__imp_NetApiBufferFree
0x180066b5a  nop     dword ptr [rax+rax+00h]
0x180066b5f  mov     eax, ebx
0x180066b61  mov     rbx, [rsp+68h+arg_0]
0x180066b66  mov     rbp, [rsp+68h+arg_8]
0x180066b6b  add     rsp, 40h
0x180066b6f  pop     r15
0x180066b71  pop     r14
0x180066b73  pop     r12
0x180066b75  pop     rdi
0x180066b76  pop     rsi
0x180066b77  retn
```
