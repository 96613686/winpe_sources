# NetpGetServiceAccountObject(ldap *,ushort const *,int *,ushort * *,ushort const *,int *)

- ea: `0x180062270`
- end: `0x180062426`
- name: `?NetpGetServiceAccountObject@@YAJPEAUldap@@PEBGPEAHPEAPEAG12@Z`
- size: `438`
- prototype: `__int64 __fastcall(LDAP *ld, const unsigned __int16 *, int *, unsigned __int16 **, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180060fa4`
- `0x180062bb8`
- `0x180062ee0`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18006176c`
- `0x180061e88`
- `0x180062270`
- `0x18006242c`
- `0x1800624fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006230d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006230d`
- `netutils!NetApiBufferFree` at `0x180062407`
- `netutils!NetApiBufferFree` at `0x180062407`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800623f4`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800623f4`

## string_xrefs

- `0x1800622b4`: `msDS-ManagedServiceAccount`
- `0x1800622d3`: `msDS-HostServiceAccountBL`
- `0x180062322`: `Service account exists and is linked to a different owner\n`
- `0x18006236c`: `Well-known path attribute for managed service accounts does not exist in directory.  Using default\n`
- `0x18006238d`: `onecore\ds\netapi\svcdlls\logonsrv\server\svcacct.cxx`
- `0x180062394`: `WellKnownPath == NULL`
- `0x1800623cd`: `Failed to create new service account\n`
- `0x1800623db`: `Created new service account\n`

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
  char *v18; // r9
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rdx
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
      for ( i = 0; v6[i]; i = (unsigned int)(i + 1) )
      {
        if ( !(unsigned int)_o__wcsicmp(a5) )
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
      v19 = (const unsigned __int16 *)Buffer;
      if ( !Buffer )
      {
LABEL_18:
        v20 = a5;
        if ( v19 )
          v20 = v19;
        ServiceAccount = NetpCreateServiceAccount(ld, v20, a2, a4);
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
        v18);
    }
    v19 = (const unsigned __int16 *)Buffer;
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
0x180062270  mov     rax, rsp
0x180062273  mov     [rax+8], rbx
0x180062277  mov     [rax+10h], rbp
0x18006227b  push    rsi
0x18006227c  push    rdi
0x18006227d  push    r12
0x18006227f  push    r14
0x180062281  push    r15
0x180062283  sub     rsp, 40h
0x180062287  xor     edi, edi
0x180062289  mov     r14, r9
0x18006228c  mov     [rax-38h], rdi
0x180062290  mov     rsi, r8
0x180062293  mov     [rax+18h], rdi
0x180062297  mov     r12, rdx
0x18006229a  mov     rbp, rcx
0x18006229d  test    r8, r8
0x1800622a0  jnz     short loc_1800622AC
0x1800622a2  mov     eax, 0C000000Dh
0x1800622a7  jmp     loc_18006240F
0x1800622ac  mov     r15, [rsp+68h+arg_28]
0x1800622b4  lea     r8, aMsdsManagedser; "msDS-ManagedServiceAccount"
0x1800622bb  mov     [rsp+68h+var_48], r15; int *
0x1800622c0  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x1800622c5  mov     ebx, eax
0x1800622c7  test    eax, eax
0x1800622c9  js      short loc_18006233D
0x1800622cb  mov     rdx, [r14]; unsigned __int16 *
0x1800622ce  lea     r9, [rsp+68h+vals]; unsigned __int16 ***
0x1800622d3  lea     r8, aMsdsHostservic_0; "msDS-HostServiceAccountBL"
0x1800622da  mov     [rsi], edi
0x1800622dc  mov     rcx, rbp; ld
0x1800622df  call    ?NetpGetSingleAttribute@@YAJPEAUldap@@PEBG1PEAPEAPEAG@Z; NetpGetSingleAttribute(ldap *,ushort const *,ushort const *,ushort * * *)
0x1800622e4  mov     rdi, [rsp+68h+vals]
0x1800622e9  test    eax, eax
0x1800622eb  js      loc_1800623E7
0x1800622f1  test    rdi, rdi
0x1800622f4  jz      loc_1800623E7
0x1800622fa  xor     ebx, ebx
0x1800622fc  mov     rdx, [rdi+rbx*8]
0x180062300  test    rdx, rdx
0x180062303  jz      short loc_180062322
0x180062305  mov     rcx, [rsp+68h+arg_20]
0x18006230d  call    cs:__imp__o__wcsicmp
0x180062313  test    eax, eax
0x180062315  jz      short loc_18006231B
0x180062317  inc     ebx
0x180062319  jmp     short loc_1800622FC
0x18006231b  xor     ebx, ebx
0x18006231d  jmp     loc_1800623EC
0x180062322  lea     rdx, aServiceAccount; "Service account exists and is linked to"...
0x180062329  mov     ecx, 40h ; '@'; unsigned int
0x18006232e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062333  mov     ebx, 0C000005Ah
0x180062338  jmp     loc_1800623EC
0x18006233d  cmp     eax, 0C0000225h
0x180062342  jnz     loc_1800623FA
0x180062348  cmp     [rsi], edi
0x18006234a  jz      loc_1800623FA
0x180062350  lea     rdx, [rsp+68h+Buffer]; unsigned __int16 **
0x180062358  mov     [r15], edi
0x18006235b  mov     rcx, rbp; ld
0x18006235e  call    ?NetpGetWellKnownPath@@YAJPEAUldap@@PEAPEAG@Z; NetpGetWellKnownPath(ldap *,ushort * *)
0x180062363  mov     esi, 40h ; '@'
0x180062368  test    eax, eax
0x18006236a  jns     short loc_1800623A0
0x18006236c  lea     rdx, aWellKnownPathA; "Well-known path attribute for managed s"...
0x180062373  mov     ecx, esi; unsigned int
0x180062375  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006237a  mov     rax, [rsp+68h+Buffer]
0x180062382  test    rax, rax
0x180062385  jz      short loc_1800623A8
0x180062387  mov     r8d, 58Eh; unsigned int
0x18006238d  lea     rdx, aOnecoreDsNetap_4; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180062394  lea     rcx, aWellknownpathN; "WellKnownPath == NULL"
0x18006239b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800623a0  mov     rax, [rsp+68h+Buffer]
0x1800623a8  mov     rdx, [rsp+68h+arg_20]
0x1800623b0  test    rax, rax
0x1800623b3  mov     r9, r14; unsigned __int16 **
0x1800623b6  mov     r8, r12; unsigned __int16 *
0x1800623b9  cmovnz  rdx, rax; unsigned __int16 *
0x1800623bd  mov     rcx, rbp; ld
0x1800623c0  call    ?NetpCreateServiceAccount@@YAJPEAUldap@@PEBG1PEAPEAG@Z; NetpCreateServiceAccount(ldap *,ushort const *,ushort const *,ushort * *)
0x1800623c5  mov     ebx, eax
0x1800623c7  mov     ecx, esi; unsigned int
0x1800623c9  test    eax, eax
0x1800623cb  jns     short loc_1800623DB
0x1800623cd  lea     rdx, aFailedToCreate; "Failed to create new service account\n"
0x1800623d4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800623d9  jmp     short loc_1800623FA
0x1800623db  lea     rdx, aCreatedNewServ; "Created new service account\n"
0x1800623e2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800623e7  mov     ebx, 90100h
0x1800623ec  test    rdi, rdi
0x1800623ef  jz      short loc_1800623FA
0x1800623f1  mov     rcx, rdi; vals
0x1800623f4  call    cs:__imp_ldap_value_freeW
0x1800623fa  mov     rcx, [rsp+68h+Buffer]; Buffer
0x180062402  test    rcx, rcx
0x180062405  jz      short loc_18006240D
0x180062407  call    cs:__imp_NetApiBufferFree
0x18006240d  mov     eax, ebx
0x18006240f  mov     rbx, [rsp+68h+arg_0]
0x180062414  mov     rbp, [rsp+68h+arg_8]
0x180062419  add     rsp, 40h
0x18006241d  pop     r15
0x18006241f  pop     r14
0x180062421  pop     r12
0x180062423  pop     rdi
0x180062424  pop     rsi
0x180062425  retn
```
