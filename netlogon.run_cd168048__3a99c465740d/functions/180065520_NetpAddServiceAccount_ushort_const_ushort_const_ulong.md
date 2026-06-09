# NetpAddServiceAccount(ushort const *,ushort const *,ulong)

- ea: `0x180065520`
- end: `0x180065acc`
- name: `?NetpAddServiceAccount@@YAJPEBG0K@Z`
- size: `1452`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ca10`

## callees

- `0x1800046b0`
- `0x180007518`
- `0x18000d7a0`
- `0x18000dfd4`
- `0x180041c10`
- `0x180056ab0`
- `0x180065520`
- `0x180065f58`
- `0x18006655c`
- `0x1800669b0`
- `0x180066d98`
- `0x180066fb4`
- `0x1800671d4`
- `0x180067a98`
- `0x180067af4`
- `0x180067d30`
- `0x180067fac`
- `0x180068008`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800659b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800659b3`
- `RPCRT4!RpcImpersonateClient` at `0x180065676`
- `RPCRT4!RpcImpersonateClient` at `0x180065676`
- `RPCRT4!RpcRevertToSelf` at `0x1800656b1`
- `RPCRT4!RpcRevertToSelf` at `0x1800656b1`
- `RPCRT4!I_RpcMapWin32Status` at `0x180065684`
- `RPCRT4!I_RpcMapWin32Status` at `0x180065684`
- `ntdll!RtlLeaveCriticalSection` at `0x1800659df`
- `ntdll!RtlLeaveCriticalSection` at `0x1800659df`
- `ntdll!RtlEnterCriticalSection` at `0x1800659a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800659a0`
- `netutils!NetApiBufferFree` at `0x1800659fc`
- `netutils!NetApiBufferFree` at `0x180065a2b`
- `netutils!NetApiBufferFree` at `0x180065a40`
- `netutils!NetApiBufferFree` at `0x180065a7d`
- `netutils!NetApiBufferFree` at `0x180065a92`
- `netutils!NetApiBufferFree` at `0x1800659fc`
- `netutils!NetApiBufferFree` at `0x180065a2b`
- `netutils!NetApiBufferFree` at `0x180065a40`
- `netutils!NetApiBufferFree` at `0x180065a7d`
- `netutils!NetApiBufferFree` at `0x180065a92`
- `WLDAP32!__imp_ldap_unbind` at `0x180065a54`
- `WLDAP32!__imp_ldap_unbind` at `0x180065a68`
- `WLDAP32!__imp_ldap_unbind` at `0x180065a54`
- `WLDAP32!__imp_ldap_unbind` at `0x180065a68`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180065965`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180065965`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180065831`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180065831`

## string_xrefs

- `0x1800656ef`: `computer`
- `0x1800657fb`: `msDS-HostServiceAccount`
- `0x180065583`: `Entering NetpAddServiceAccount for account %s, flags 0x%08X\n`
- `0x18006561d`: `NetpAddServiceAccount: Provided password must accompany RODC add\n`
- `0x180065603`: `NetpAddServiceAccount: Failed to locate usable domain controller\n`
- `0x18006565a`: `NetpAddServiceAccount: Failed to bind to LDAP as SYSTEM\n`
- `0x1800656c1`: `NetpAddServiceAccount: Failed to bind to LDAP as caller\n`
- `0x180065710`: `NetpAddServiceAccount: Failed to find computer account object for %s\n`
- `0x18006575e`: `NetpAddServiceAccount: Failed to find or create service account object for %s\n`
- `0x18006577f`: `NetpAddServiceAccount: Account CREATED\n`
- `0x1800657a0`: `NetpAddServiceAccount: Account password management STOPPED\n`
- `0x1800657df`: `NetpAddServiceAccount: RODC add requires that the account be pre-linked\n`
- `0x18006584f`: `NetpAddServiceAccount: Failed to link service account to computer\n`
- `0x18006585b`: `NetpAddServiceAccount: Account LINKED\n`
- `0x180065880`: `NetpAddServiceAccount: Failed to set password on service account\n`
- `0x1800658a8`: `NetpAddServiceAccount: Failed to write local account secret\n`
- `0x1800658d4`: `NetpAddServiceAccount: Failed to enable service account\n`
- `0x1800658dd`: `NetpAddServiceAccount: Account ENABLED\n`
- `0x1800658fb`: `NetpAddServiceAccount: Failed to start password management for account\n`
- `0x18006591f`: `NetpAddServiceAccount: RODC join could not validate provided credential\n`
- `0x180065aa1`: `Exiting NetpAddServiceAccount for account %s, Status 0x%08X\n`

## pseudocode

```c
int __fastcall NetpAddServiceAccount(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  LDAP *v3; // r14
  char v4; // si
  unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // r12
  LDAP *v7; // r15
  BOOL v8; // ecx
  int v9; // esi
  int result; // eax
  unsigned int DcNameEx2; // eax
  int AccountObject; // ebx
  void *v13; // r9
  WCHAR *v14; // r13
  RPC_STATUS v15; // eax
  void *v16; // r9
  int v17; // r12d
  int v18; // edi
  unsigned __int16 *v19; // rdx
  ULONG v20; // eax
  unsigned int v21; // ecx
  unsigned __int16 *v22; // rax
  __int64 v23; // rcx
  LPVOID Buffer; // [rsp+40h] [rbp-59h] BYREF
  PWSTR v25; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-49h] BYREF
  PWSTR dn; // [rsp+58h] [rbp-41h] BYREF
  LPVOID v28; // [rsp+60h] [rbp-39h] BYREF
  LDAP *ld[2]; // [rsp+68h] [rbp-31h] BYREF
  int v30; // [rsp+78h] [rbp-21h] BYREF
  LDAP *v31[2]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v32[12]; // [rsp+90h] [rbp-9h] BYREF
  int v35; // [rsp+110h] [rbp+77h] BYREF
  int v36; // [rsp+118h] [rbp+7Fh] BYREF

  v3 = 0;
  Buffer = 0;
  v4 = a3;
  v28 = 0;
  ld[0] = 0;
  v5 = a2;
  v30 = 0;
  v6 = a1;
  v25 = 0;
  dn = 0;
  v7 = 0;
  v26 = 0;
  v31[0] = 0;
  NlPrintRoutine(0x40u, L"Entering NetpAddServiceAccount for account %s, flags 0x%08X\n", a1, a3);
  v8 = (v4 & 3) == 0;
  v9 = v4 & 2;
  v35 = v8;
  if ( v5 )
  {
    if ( v9 )
      goto LABEL_3;
LABEL_7:
    NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Provided password must accompany RODC add\n");
    return -1073741811;
  }
  if ( v9 )
    goto LABEL_7;
LABEL_3:
  result = NetpProcessAccountName(v6, (unsigned __int16 **)&Buffer);
  if ( result < 0 )
    return result;
  DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, (v9 == 0 ? 0x1000 : 0) | 0x40000000u, (__int64)&v28);
  AccountObject = NetpApiStatusToNtStatus(DcNameEx2);
  if ( AccountObject >= 0 )
  {
    v14 = *(WCHAR **)v28;
    AccountObject = NetpLdapBind(*(PWSTR *)v28, *((const unsigned __int16 **)v28 + 5), ld, v13, 0);
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to bind to LDAP as SYSTEM\n");
LABEL_10:
      v3 = ld[0];
      goto LABEL_58;
    }
    v15 = RpcImpersonateClient(0);
    AccountObject = I_RpcMapWin32Status(v15);
    if ( AccountObject < 0 )
      goto LABEL_10;
    AccountObject = NetpLdapBind(v14, *((const unsigned __int16 **)v28 + 5), v31, v16, 0);
    RpcRevertToSelf();
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to bind to LDAP as caller\n");
      v3 = ld[0];
LABEL_16:
      v7 = v31[0];
      goto LABEL_58;
    }
    v36 = 0;
    v3 = ld[0];
    AccountObject = NetpGetAccountObject(ld[0], NlGlobalUnicodeComputerName, L"computer", &dn, &v36);
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(
        0x40u,
        L"NetpAddServiceAccount: Failed to find computer account object for %s\n",
        NlGlobalUnicodeComputerName);
      goto LABEL_16;
    }
    v7 = v31[0];
    AccountObject = NetpGetServiceAccountObject(v31[0], (const unsigned __int16 *)Buffer, &v35, &v25, dn, &v30);
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to find or create service account object for %s\n", Buffer);
      goto LABEL_58;
    }
    v17 = v35;
    v18 = 0;
    if ( v35 )
    {
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Account CREATED\n");
      v18 = 1;
    }
    if ( (int)NlDeleteServiceAccount((unsigned __int16 *)Buffer) >= 0 )
    {
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Account password management STOPPED\n");
      v18 |= 0x10u;
    }
    if ( AccountObject == 590080 || v17 )
    {
      if ( v9 )
      {
        AccountObject = -1073741734;
        NlPrintRoutine(0x40u, L"NetpAddServiceAccount: RODC add requires that the account be pre-linked\n");
        goto LABEL_46;
      }
      ld[0] = (LDAP *)v32;
      v32[0] = 0;
      v32[1] = L"msDS-HostServiceAccount";
      ld[1] = 0;
      v32[2] = v31;
      v31[0] = (LDAP *)v25;
      v31[1] = 0;
      v20 = ldap_modify_sW(v3, dn, (LDAPModW **)ld);
      AccountObject = NetpMapLdapErrorToNtStatus(v20);
      if ( AccountObject < 0 )
      {
        NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to link service account to computer\n");
        goto LABEL_46;
      }
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Account LINKED\n");
      v18 |= 2u;
    }
    else if ( v9 )
    {
      v19 = a2;
      v26 = a2;
LABEL_35:
      AccountObject = NetpSetAccountSecret((PCWSTR)Buffer, v19, v9 != 0);
      if ( AccountObject >= 0 )
      {
        v18 |= 4u;
        if ( !v9 )
        {
          AccountObject = NetpSetAccountControl(v7, v25, L"4096");
          if ( AccountObject < 0 )
          {
            NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to enable service account\n");
            goto LABEL_46;
          }
          NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Account ENABLED\n");
          v18 |= 8u;
        }
        AccountObject = NlAddServiceAccount((unsigned __int16 *)Buffer);
        if ( AccountObject >= 0 )
        {
          if ( v9 )
          {
            AccountObject = NetpVerifyServiceAccount((const unsigned __int16 *)Buffer, v26);
            if ( AccountObject < 0 )
            {
              NlPrintRoutine(0x40u, L"NetpAddServiceAccount: RODC join could not validate provided credential\n");
              goto LABEL_46;
            }
            RtlEnterCriticalSection(&NlGlobalScavengerCritSect);
            GetSystemTimeAsFileTime(&NlGlobalScavengerTimer);
            dword_1800F8BA8 = 15000;
            NlpDumpPeriod(v21, "NlWksScavenger: Scheduling extra password change pass for new MSA in", 0x3A98u);
            RtlLeaveCriticalSection(&NlGlobalScavengerCritSect);
          }
LABEL_57:
          v6 = a1;
          v5 = a2;
          goto LABEL_58;
        }
        NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to start password management for account\n");
      }
      else
      {
        NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to write local account secret\n");
      }
LABEL_46:
      if ( (v18 & 8) != 0 )
        NetpSetAccountControl(v7, v25, L"4130");
      if ( (v18 & 4) != 0 )
        NetpDeleteAccountSecret((const unsigned __int16 *)Buffer);
      if ( (v18 & 1) != 0 )
      {
        ldap_delete_sW(v7, v25);
      }
      else if ( (v18 & 2) != 0 )
      {
        NetpUnlinkServiceAccount(v3, dn, v25);
      }
      if ( v18 == 16 )
        NlAddServiceAccount((unsigned __int16 *)Buffer);
      goto LABEL_57;
    }
    AccountObject = NetpSetAccountPassword(v14, (const unsigned __int16 *)Buffer, &v26);
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to set password on service account\n");
      goto LABEL_46;
    }
    v19 = v26;
    goto LABEL_35;
  }
  NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to locate usable domain controller\n");
LABEL_58:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  v22 = v26;
  if ( v26 && v26 != v5 )
  {
    v23 = 240;
    do
    {
      *(_BYTE *)v22 = 0;
      v22 = (unsigned __int16 *)((char *)v22 + 1);
      --v23;
    }
    while ( v23 );
    NetApiBufferFree(v26);
  }
  if ( v28 )
    NetApiBufferFree(v28);
  if ( v3 )
    ldap_unbind(v3);
  if ( v7 )
    ldap_unbind(v7);
  if ( dn )
    NetApiBufferFree(dn);
  if ( v25 )
    NetApiBufferFree(v25);
  NlPrintRoutine(
    0x40u,
    L"Exiting NetpAddServiceAccount for account %s, Status 0x%08X\n",
    v6,
    (unsigned int)AccountObject);
  return AccountObject;
}

```

## disassembly

```asm
0x180065520  mov     [rsp-8+arg_8], rdx
0x180065525  mov     [rsp-8+arg_0], rcx
0x18006552a  push    rbp
0x18006552b  push    rbx
0x18006552c  push    rsi
0x18006552d  push    rdi
0x18006552e  push    r12
0x180065530  push    r13
0x180065532  push    r14
0x180065534  push    r15
0x180065536  lea     rbp, [rsp-1Fh]
0x18006553b  sub     rsp, 0B8h
0x180065542  xor     r14d, r14d
0x180065545  mov     [rbp+57h+Buffer], 0
0x18006554d  mov     esi, r8d
0x180065550  mov     [rbp+57h+var_90], 0
0x180065558  mov     r9d, r8d
0x18006555b  mov     [rbp+57h+ld], r14
0x18006555f  mov     rdi, rdx
0x180065562  mov     [rbp+57h+var_78], r14d
0x180065566  mov     r12, rcx
0x180065569  mov     [rbp+57h+var_A8], r14
0x18006556d  mov     r8, rcx
0x180065570  mov     [rbp+57h+dn], r14
0x180065574  xor     r15d, r15d
0x180065577  mov     [rbp+57h+var_A0], r14
0x18006557b  lea     ecx, [r14+40h]; unsigned int
0x18006557f  mov     [rbp+57h+var_70], r15
0x180065583  lea     rdx, aEnteringNetpad; "Entering NetpAddServiceAccount for acco"...
0x18006558a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006558f  test    sil, 3
0x180065593  lea     ecx, [r14+1]
0x180065597  cmovnz  ecx, r14d
0x18006559b  and     esi, 2
0x18006559e  mov     [rbp+57h+arg_10], ecx
0x1800655a1  test    rdi, rdi
0x1800655a4  jz      short loc_180065619
0x1800655a6  test    esi, esi
0x1800655a8  jz      short loc_18006561D
0x1800655aa  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 **
0x1800655ae  mov     rcx, r12; unsigned __int16 *
0x1800655b1  call    ?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z; NetpProcessAccountName(ushort const *,ushort * *)
0x1800655b6  test    eax, eax
0x1800655b8  js      loc_180065AB7
0x1800655be  mov     eax, esi
0x1800655c0  neg     eax
0x1800655c2  lea     rax, [rbp+57h+var_90]
0x1800655c6  sbb     ecx, ecx
0x1800655c8  mov     [rsp+0F0h+var_B8], rax
0x1800655cd  not     ecx
0x1800655cf  xor     r9d, r9d
0x1800655d2  and     ecx, 1000h
0x1800655d8  xor     r8d, r8d
0x1800655db  bts     ecx, 1Eh
0x1800655df  xor     edx, edx
0x1800655e1  mov     [rsp+0F0h+var_C0], ecx
0x1800655e5  xor     ecx, ecx
0x1800655e7  mov     [rsp+0F0h+var_C8], r14
0x1800655ec  mov     [rsp+0F0h+var_D0], r14
0x1800655f1  call    DsrGetDcNameEx2
0x1800655f6  mov     ecx, eax
0x1800655f8  call    NetpApiStatusToNtStatus
0x1800655fd  mov     ebx, eax
0x1800655ff  test    eax, eax
0x180065601  jns     short loc_180065638
0x180065603  lea     rdx, aNetpaddservice_14; "NetpAddServiceAccount: Failed to locate"...
0x18006560a  mov     ecx, 40h ; '@'; unsigned int
0x18006560f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180065614  jmp     loc_1800659F3
0x180065619  test    esi, esi
0x18006561b  jz      short loc_1800655AA
0x18006561d  lea     rdx, aNetpaddservice_6; "NetpAddServiceAccount: Provided passwor"...
0x180065624  mov     ecx, 40h ; '@'; unsigned int
0x180065629  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006562e  mov     eax, 0C000000Dh
0x180065633  jmp     loc_180065AB7
0x180065638  mov     rdx, [rbp+57h+var_90]
0x18006563c  lea     r8, [rbp+57h+ld]; struct ldap **
0x180065640  mov     dword ptr [rsp+0F0h+var_D0], r14d; int
0x180065645  mov     r13, [rdx]
0x180065648  mov     rdx, [rdx+28h]; unsigned __int16 *
0x18006564c  mov     rcx, r13; HostName
0x18006564f  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180065654  mov     ebx, eax
0x180065656  test    eax, eax
0x180065658  jns     short loc_180065674
0x18006565a  lea     rdx, aNetpaddservice_17; "NetpAddServiceAccount: Failed to bind t"...
0x180065661  mov     ecx, 40h ; '@'; unsigned int
0x180065666  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006566b  mov     r14, [rbp+57h+ld]
0x18006566f  jmp     loc_1800659F3
0x180065674  xor     ecx, ecx; BindingHandle
0x180065676  call    cs:__imp_RpcImpersonateClient
0x18006567d  nop     dword ptr [rax+rax+00h]
0x180065682  mov     ecx, eax; Status
0x180065684  call    cs:__imp_I_RpcMapWin32Status
0x18006568b  nop     dword ptr [rax+rax+00h]
0x180065690  mov     ebx, eax
0x180065692  test    eax, eax
0x180065694  js      short loc_18006566B
0x180065696  mov     rdx, [rbp+57h+var_90]
0x18006569a  lea     r8, [rbp+57h+var_70]; struct ldap **
0x18006569e  mov     rcx, r13; HostName
0x1800656a1  mov     dword ptr [rsp+0F0h+var_D0], r14d; int
0x1800656a6  mov     rdx, [rdx+28h]; unsigned __int16 *
0x1800656aa  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x1800656af  mov     ebx, eax
0x1800656b1  call    cs:__imp_RpcRevertToSelf
0x1800656b8  nop     dword ptr [rax+rax+00h]
0x1800656bd  test    ebx, ebx
0x1800656bf  jns     short loc_1800656D8
0x1800656c1  lea     rdx, aNetpaddservice_0; "NetpAddServiceAccount: Failed to bind t"...
0x1800656c8  mov     ecx, 40h ; '@'; unsigned int
0x1800656cd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800656d2  mov     r14, [rbp+57h+ld]
0x1800656d6  jmp     short loc_180065721
0x1800656d8  mov     rdx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; unsigned __int16 *
0x1800656df  lea     rax, [rbp+57h+arg_18]
0x1800656e3  mov     [rbp+57h+arg_18], r14d
0x1800656e7  lea     r9, [rbp+57h+dn]; unsigned __int16 **
0x1800656eb  mov     r14, [rbp+57h+ld]
0x1800656ef  lea     r8, aComputer; "computer"
0x1800656f6  mov     rcx, r14; ld
0x1800656f9  mov     [rsp+0F0h+var_D0], rax; int *
0x1800656fe  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x180065703  mov     ebx, eax
0x180065705  test    eax, eax
0x180065707  jns     short loc_18006572A
0x180065709  mov     r8, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x180065710  lea     rdx, aNetpaddservice_3; "NetpAddServiceAccount: Failed to find c"...
0x180065717  mov     ecx, 40h ; '@'; unsigned int
0x18006571c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180065721  mov     r15, [rbp+57h+var_70]
0x180065725  jmp     loc_1800659F3
0x18006572a  mov     r15, [rbp+57h+var_70]
0x18006572e  lea     rax, [rbp+57h+var_78]
0x180065732  mov     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x180065736  lea     r9, [rbp+57h+var_A8]; unsigned __int16 **
0x18006573a  mov     [rsp+0F0h+var_C8], rax; int *
0x18006573f  lea     r8, [rbp+57h+arg_10]; int *
0x180065743  mov     rax, [rbp+57h+dn]
0x180065747  mov     rcx, r15; ld
0x18006574a  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18006574f  call    ?NetpGetServiceAccountObject@@YAJPEAUldap@@PEBGPEAHPEAPEAG12@Z; NetpGetServiceAccountObject(ldap *,ushort const *,int *,ushort * *,ushort const *,int *)
0x180065754  mov     ebx, eax
0x180065756  test    eax, eax
0x180065758  jns     short loc_180065774
0x18006575a  mov     r8, [rbp+57h+Buffer]
0x18006575e  lea     rdx, aNetpaddservice_13; "NetpAddServiceAccount: Failed to find o"...
0x180065765  mov     ecx, 40h ; '@'; unsigned int
0x18006576a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006576f  jmp     loc_1800659F3
0x180065774  mov     r12d, [rbp+57h+arg_10]
0x180065778  xor     edi, edi
0x18006577a  test    r12d, r12d
0x18006577d  jz      short loc_180065793
0x18006577f  lea     rdx, aNetpaddservice_9; "NetpAddServiceAccount: Account CREATED"...
0x180065786  lea     ecx, [rdi+40h]; unsigned int
0x180065789  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006578e  mov     edi, 1
0x180065793  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x180065797  call    ?NlDeleteServiceAccount@@YAJPEAG@Z; NlDeleteServiceAccount(ushort *)
0x18006579c  test    eax, eax
0x18006579e  js      short loc_1800657B4
0x1800657a0  lea     rdx, aNetpaddservice_7; "NetpAddServiceAccount: Account password"...
0x1800657a7  mov     ecx, 40h ; '@'; unsigned int
0x1800657ac  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800657b1  or      edi, 10h
0x1800657b4  cmp     ebx, 90100h
0x1800657ba  jz      short loc_1800657D6
0x1800657bc  test    r12d, r12d
0x1800657bf  jnz     short loc_1800657D6
0x1800657c1  test    esi, esi
0x1800657c3  jz      loc_18006586A
0x1800657c9  mov     rdx, [rbp+57h+arg_8]
0x1800657cd  mov     [rbp+57h+var_A0], rdx
0x1800657d1  jmp     loc_180065890
0x1800657d6  test    esi, esi
0x1800657d8  jz      short loc_1800657EB
0x1800657da  mov     ebx, 0C000005Ah
0x1800657df  lea     rdx, aNetpaddservice_1; "NetpAddServiceAccount: RODC add require"...
0x1800657e6  jmp     loc_180065926
0x1800657eb  mov     rdx, [rbp+57h+dn]; dn
0x1800657ef  lea     rax, [rbp+57h+var_60]
0x1800657f3  mov     [rbp+57h+ld], rax
0x1800657f7  lea     r8, [rbp+57h+ld]; mods
0x1800657fb  lea     rax, aMsdsHostservic; "msDS-HostServiceAccount"
0x180065802  mov     [rbp+57h+var_60], 0
0x18006580a  mov     [rbp+57h+var_58], rax
0x18006580e  mov     rcx, r14; ld
0x180065811  lea     rax, [rbp+57h+var_70]
0x180065815  mov     [rbp+57h+var_80], 0
0x18006581d  mov     [rbp+57h+var_50], rax
0x180065821  mov     rax, [rbp+57h+var_A8]
0x180065825  mov     [rbp+57h+var_70], rax
0x180065829  mov     [rbp+57h+var_68], 0
0x180065831  call    cs:__imp_ldap_modify_sW
0x180065838  nop     dword ptr [rax+rax+00h]
0x18006583d  mov     ecx, eax; unsigned int
0x18006583f  call    ?NetpMapLdapErrorToNtStatus@@YAJK@Z; NetpMapLdapErrorToNtStatus(ulong)
0x180065844  mov     ebx, eax
0x180065846  mov     ecx, 40h ; '@'; unsigned int
0x18006584b  test    eax, eax
0x18006584d  jns     short loc_18006585B
0x18006584f  lea     rdx, aNetpaddservice_8; "NetpAddServiceAccount: Failed to link s"...
0x180065856  jmp     loc_18006592B
0x18006585b  lea     rdx, aNetpaddservice_12; "NetpAddServiceAccount: Account LINKED\n"
0x180065862  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180065867  or      edi, 2
0x18006586a  mov     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x18006586e  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x180065872  mov     rcx, r13; servername
0x180065875  call    ?NetpSetAccountPassword@@YAJPEBG0PEAPEAG@Z; NetpSetAccountPassword(ushort const *,ushort const *,ushort * *)
0x18006587a  mov     ebx, eax
0x18006587c  test    eax, eax
0x18006587e  jns     short loc_18006588C
0x180065880  lea     rdx, aNetpaddservice; "NetpAddServiceAccount: Failed to set pa"...
0x180065887  jmp     loc_180065926
0x18006588c  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x180065890  mov     rcx, [rbp+57h+Buffer]; SourceString
0x180065894  xor     r8d, r8d
0x180065897  test    esi, esi
0x180065899  setnz   r8b; int
0x18006589d  call    ?NetpSetAccountSecret@@YAJPEBG0H@Z; NetpSetAccountSecret(ushort const *,ushort const *,int)
0x1800658a2  mov     ebx, eax
0x1800658a4  test    eax, eax
0x1800658a6  jns     short loc_1800658B1
0x1800658a8  lea     rdx, aNetpaddservice_11; "NetpAddServiceAccount: Failed to write "...
0x1800658af  jmp     short loc_180065926
0x1800658b1  or      edi, 4
0x1800658b4  test    esi, esi
0x1800658b6  jnz     short loc_1800658EC
0x1800658b8  mov     rdx, [rbp+57h+var_A8]; unsigned __int16 *
0x1800658bc  lea     r8, a4096; "4096"
0x1800658c3  mov     rcx, r15; struct ldap *
0x1800658c6  call    ?NetpSetAccountControl@@YAJPEAUldap@@PEBG1@Z; NetpSetAccountControl(ldap *,ushort const *,ushort const *)
0x1800658cb  lea     ecx, [rsi+40h]; unsigned int
0x1800658ce  mov     ebx, eax
0x1800658d0  test    eax, eax
0x1800658d2  jns     short loc_1800658DD
0x1800658d4  lea     rdx, aNetpaddservice_16; "NetpAddServiceAccount: Failed to enable"...
0x1800658db  jmp     short loc_18006592B
0x1800658dd  lea     rdx, aNetpaddservice_4; "NetpAddServiceAccount: Account ENABLED"...
0x1800658e4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800658e9  or      edi, 8
0x1800658ec  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800658f0  call    ?NlAddServiceAccount@@YAJPEAG@Z; NlAddServiceAccount(ushort *)
0x1800658f5  mov     ebx, eax
0x1800658f7  test    eax, eax
0x1800658f9  jns     short loc_180065904
0x1800658fb  lea     rdx, aNetpaddservice_15; "NetpAddServiceAccount: Failed to start "...
0x180065902  jmp     short loc_180065926
0x180065904  test    esi, esi
0x180065906  jz      loc_1800659EB
0x18006590c  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x180065910  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x180065914  call    ?NetpVerifyServiceAccount@@YAJPEBG0@Z; NetpVerifyServiceAccount(ushort const *,ushort const *)
0x180065919  mov     ebx, eax
0x18006591b  test    eax, eax
0x18006591d  jns     short loc_180065999
0x18006591f  lea     rdx, aNetpaddservice_10; "NetpAddServiceAccount: RODC join could "...
0x180065926  mov     ecx, 40h ; '@'; unsigned int
0x18006592b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180065930  test    dil, 8
0x180065934  jz      short loc_180065949
0x180065936  mov     rdx, [rbp+57h+var_A8]; unsigned __int16 *
0x18006593a  lea     r8, a4130; "4130"
0x180065941  mov     rcx, r15; struct ldap *
0x180065944  call    ?NetpSetAccountControl@@YAJPEAUldap@@PEBG1@Z; NetpSetAccountControl(ldap *,ushort const *,ushort const *)
0x180065949  test    dil, 4
0x18006594d  jz      short loc_180065958
0x18006594f  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x180065953  call    ?NetpDeleteAccountSecret@@YAJPEBG@Z; NetpDeleteAccountSecret(ushort const *)
0x180065958  test    dil, 1
0x18006595c  jz      short loc_180065973
0x18006595e  mov     rdx, [rbp+57h+var_A8]; dn
0x180065962  mov     rcx, r15; ld
0x180065965  call    cs:__imp_ldap_delete_sW
0x18006596c  nop     dword ptr [rax+rax+00h]
0x180065971  jmp     short loc_180065989
0x180065973  test    dil, 2
0x180065977  jz      short loc_180065989
0x180065979  mov     r8, [rbp+57h+var_A8]; unsigned __int16 *
0x18006597d  mov     rcx, r14; struct ldap *
0x180065980  mov     rdx, [rbp+57h+dn]; unsigned __int16 *
0x180065984  call    ?NetpUnlinkServiceAccount@@YAJPEAUldap@@PEBG1@Z; NetpUnlinkServiceAccount(ldap *,ushort const *,ushort const *)
0x180065989  cmp     edi, 10h
0x18006598c  jnz     short loc_1800659EB
0x18006598e  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x180065992  call    ?NlAddServiceAccount@@YAJPEAG@Z; NlAddServiceAccount(ushort *)
0x180065997  jmp     short loc_1800659EB
0x180065999  lea     rcx, ?NlGlobalScavengerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800659a0  call    cs:__imp_RtlEnterCriticalSection
0x1800659a7  nop     dword ptr [rax+rax+00h]
0x1800659ac  lea     rcx, ?NlGlobalScavengerTimer@@3U_TIMER@@A; lpSystemTimeAsFileTime
0x1800659b3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800659ba  nop     dword ptr [rax+rax+00h]
0x1800659bf  mov     r8d, 3A98h; unsigned int
0x1800659c5  lea     rdx, aNlwksscavenger_0; "NlWksScavenger: Scheduling extra passwo"...
0x1800659cc  mov     cs:dword_1800F8BA8, r8d
  ... truncated ...
```
