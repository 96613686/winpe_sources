# NetpRemoveServiceAccount(ushort const *,ulong)

- ea: `0x180067760`
- end: `0x180067a92`
- name: `?NetpRemoveServiceAccount@@YAJPEBGK@Z`
- size: `818`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002cd20`

## callees

- `0x1800046b0`
- `0x180007518`
- `0x18000d7a0`
- `0x18000dfd4`
- `0x180065f58`
- `0x18006655c`
- `0x1800669b0`
- `0x180066d98`
- `0x180066fb4`
- `0x1800671d4`
- `0x180067760`
- `0x180067fac`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18006786c`
- `RPCRT4!RpcImpersonateClient` at `0x18006786c`
- `RPCRT4!RpcRevertToSelf` at `0x1800678a6`
- `RPCRT4!RpcRevertToSelf` at `0x1800678a6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006787a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006787a`
- `netutils!NetApiBufferFree` at `0x1800679e9`
- `netutils!NetApiBufferFree` at `0x1800679fe`
- `netutils!NetApiBufferFree` at `0x180067a3b`
- `netutils!NetApiBufferFree` at `0x180067a50`
- `netutils!NetApiBufferFree` at `0x1800679e9`
- `netutils!NetApiBufferFree` at `0x1800679fe`
- `netutils!NetApiBufferFree` at `0x180067a3b`
- `netutils!NetApiBufferFree` at `0x180067a50`
- `WLDAP32!__imp_ldap_unbind` at `0x180067a12`
- `WLDAP32!__imp_ldap_unbind` at `0x180067a26`
- `WLDAP32!__imp_ldap_unbind` at `0x180067a12`
- `WLDAP32!__imp_ldap_unbind` at `0x180067a26`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1800679b2`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1800679b2`

## string_xrefs

- `0x1800678ed`: `computer`
- `0x1800677b1`: `Entering NetpRemoveServiceAccount for account %s, flags 0x%08X\n`
- `0x180067819`: `NetpRemoveServiceAccount: Failed to find usable DC\n`
- `0x180067850`: `NetpRemoveServiceAccount: Failed LDAP bind as SYSTEM\n`
- `0x1800678b6`: `NetpRemoveServiceAccount: Failed LDAP bind as caller\n`
- `0x18006790b`: `NetpRemoveServiceAccount: Failed to find computer account object for %s\n`
- `0x180067960`: `NetpAddServiceAccount: Failed to find service account object for %s\n`
- `0x180067982`: `NetpRemoveServiceAccount: Failed to stop password management\n`
- `0x1800679cb`: `NetpRemoveServiceAccount: Failed to unlink or delete service account\n`
- `0x180067a5f`: `Exiting NetpRemoveServiceAccount for account %s, Status 0x%08X\n`

## pseudocode

```c
int __fastcall NetpRemoveServiceAccount(const unsigned __int16 *a1, unsigned int a2)
{
  LDAP *v2; // rsi
  LDAP *v3; // rdi
  char v4; // r15
  int result; // eax
  unsigned int DcNameEx2; // eax
  int AccountObject; // ebx
  void *v9; // r9
  WCHAR *v10; // rdi
  RPC_STATUS v11; // eax
  void *v12; // r9
  int ServiceAccountObject; // eax
  int v14; // eax
  ULONG v15; // eax
  int v16; // [rsp+40h] [rbp-40h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-38h] BYREF
  LDAP *ld; // [rsp+50h] [rbp-30h] BYREF
  LDAP *v19; // [rsp+58h] [rbp-28h] BYREF
  LPVOID v20; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp-18h] BYREF
  PWSTR dn; // [rsp+70h] [rbp-10h] BYREF
  int v23; // [rsp+C0h] [rbp+40h] BYREF
  int v24; // [rsp+C8h] [rbp+48h] BYREF

  v2 = 0;
  Buffer = 0;
  v3 = 0;
  v20 = 0;
  v4 = a2;
  ld = 0;
  v19 = 0;
  v16 = 0;
  v24 = 0;
  dn = 0;
  v21 = 0;
  NlPrintRoutine(0x40u, L"Entering NetpRemoveServiceAccount for account %s, flags 0x%08X\n", a1, a2);
  result = NetpProcessAccountName(a1, (unsigned __int16 **)&Buffer);
  if ( result < 0 )
    return result;
  if ( (v4 & 2) != 0 )
    goto LABEL_19;
  DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0x40001000u, (__int64)&v20);
  AccountObject = NetpApiStatusToNtStatus(DcNameEx2);
  if ( AccountObject < 0 )
  {
    NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount: Failed to find usable DC\n");
    goto LABEL_28;
  }
  v10 = *(WCHAR **)v20;
  AccountObject = NetpLdapBind(*(PWSTR *)v20, *((const unsigned __int16 **)v20 + 5), &ld, v9, 0);
  if ( AccountObject >= 0 )
  {
    v11 = RpcImpersonateClient(0);
    AccountObject = I_RpcMapWin32Status(v11);
    if ( AccountObject < 0 )
      goto LABEL_8;
    AccountObject = NetpLdapBind(v10, *((const unsigned __int16 **)v20 + 5), &v19, v12, 0);
    RpcRevertToSelf();
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount: Failed LDAP bind as caller\n");
      v3 = ld;
LABEL_12:
      v2 = v19;
      goto LABEL_28;
    }
    v3 = ld;
    v23 = 0;
    AccountObject = NetpGetAccountObject(ld, NlGlobalUnicodeComputerName, L"computer", &v21, &v23);
    if ( AccountObject < 0 )
    {
      NlPrintRoutine(
        0x40u,
        L"NetpRemoveServiceAccount: Failed to find computer account object for %s\n",
        NlGlobalUnicodeComputerName);
      goto LABEL_12;
    }
    v2 = v19;
    ServiceAccountObject = NetpGetServiceAccountObject(v19, (const unsigned __int16 *)Buffer, &v16, &dn, v21, &v24);
    AccountObject = ServiceAccountObject;
    if ( ServiceAccountObject == 590080 )
    {
      AccountObject = -1073741734;
LABEL_18:
      NlPrintRoutine(0x40u, L"NetpAddServiceAccount: Failed to find service account object for %s\n", Buffer);
      goto LABEL_28;
    }
    if ( ServiceAccountObject < 0 )
      goto LABEL_18;
LABEL_19:
    AccountObject = NlDeleteServiceAccount((unsigned __int16 *)Buffer);
    if ( AccountObject >= 0 )
    {
      if ( (v4 & 2) != 0
        || ((v4 & 1) == 0
          ? (v15 = ldap_delete_sW(v2, dn), v14 = NetpMapLdapErrorToNtStatus(v15))
          : (v14 = NetpUnlinkServiceAccount(v3, v21, dn)),
            AccountObject = v14,
            v14 >= 0) )
      {
        NetpDeleteAccountSecret((const unsigned __int16 *)Buffer);
      }
      else
      {
        NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount: Failed to unlink or delete service account\n");
      }
    }
    else
    {
      NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount: Failed to stop password management\n");
    }
    goto LABEL_28;
  }
  NlPrintRoutine(0x40u, L"NetpRemoveServiceAccount: Failed LDAP bind as SYSTEM\n");
LABEL_8:
  v3 = ld;
LABEL_28:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v20 )
    NetApiBufferFree(v20);
  if ( v3 )
    ldap_unbind(v3);
  if ( v2 )
    ldap_unbind(v2);
  if ( v21 )
    NetApiBufferFree(v21);
  if ( dn )
    NetApiBufferFree(dn);
  NlPrintRoutine(
    0x40u,
    L"Exiting NetpRemoveServiceAccount for account %s, Status 0x%08X\n",
    a1,
    (unsigned int)AccountObject);
  return AccountObject;
}

```

## disassembly

```asm
0x180067760  mov     [rsp-28h+arg_0], rbx
0x180067765  mov     [rsp-28h+arg_8], rsi
0x18006776a  push    rbp
0x18006776b  push    rdi
0x18006776c  push    r12
0x18006776e  push    r14
0x180067770  push    r15
0x180067772  mov     rbp, rsp
0x180067775  sub     rsp, 80h
0x18006777c  xor     esi, esi
0x18006777e  mov     [rbp+Buffer], 0
0x180067786  xor     edi, edi
0x180067788  mov     [rbp+var_20], 0
0x180067790  mov     r15d, edx
0x180067793  mov     [rbp+ld], rdi
0x180067797  mov     r12, rcx
0x18006779a  mov     [rbp+var_28], rsi
0x18006779e  mov     r9d, edx
0x1800677a1  mov     [rbp+var_40], esi
0x1800677a4  mov     r8, rcx
0x1800677a7  mov     [rbp+arg_18], esi
0x1800677aa  lea     ecx, [rdi+40h]; unsigned int
0x1800677ad  mov     [rbp+dn], rsi
0x1800677b1  lea     rdx, aEnteringNetpre; "Entering NetpRemoveServiceAccount for a"...
0x1800677b8  mov     [rbp+var_18], rsi
0x1800677bc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800677c1  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x1800677c5  mov     rcx, r12; unsigned __int16 *
0x1800677c8  call    ?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z; NetpProcessAccountName(ushort const *,ushort * *)
0x1800677cd  test    eax, eax
0x1800677cf  js      loc_180067A75
0x1800677d5  mov     r14d, r15d
0x1800677d8  and     r14d, 2
0x1800677dc  jnz     loc_180067973
0x1800677e2  lea     rax, [rbp+var_20]
0x1800677e6  xor     r9d, r9d
0x1800677e9  mov     [rsp+80h+var_48], rax
0x1800677ee  xor     r8d, r8d
0x1800677f1  mov     [rsp+80h+var_50], 40001000h
0x1800677f9  xor     edx, edx
0x1800677fb  mov     [rsp+80h+var_58], rsi
0x180067800  xor     ecx, ecx
0x180067802  mov     [rsp+80h+var_60], rsi
0x180067807  call    DsrGetDcNameEx2
0x18006780c  mov     ecx, eax
0x18006780e  call    NetpApiStatusToNtStatus
0x180067813  mov     ebx, eax
0x180067815  test    eax, eax
0x180067817  jns     short loc_18006782F
0x180067819  lea     rdx, aNetpremoveserv; "NetpRemoveServiceAccount: Failed to fin"...
0x180067820  mov     ecx, 40h ; '@'; unsigned int
0x180067825  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006782a  jmp     loc_1800679E0
0x18006782f  mov     rdx, [rbp+var_20]
0x180067833  lea     r8, [rbp+ld]; struct ldap **
0x180067837  mov     dword ptr [rsp+80h+var_60], esi; int
0x18006783b  mov     rdi, [rdx]
0x18006783e  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180067842  mov     rcx, rdi; HostName
0x180067845  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x18006784a  mov     ebx, eax
0x18006784c  test    eax, eax
0x18006784e  jns     short loc_18006786A
0x180067850  lea     rdx, aNetpremoveserv_3; "NetpRemoveServiceAccount: Failed LDAP b"...
0x180067857  mov     ecx, 40h ; '@'; unsigned int
0x18006785c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067861  mov     rdi, [rbp+ld]
0x180067865  jmp     loc_1800679E0
0x18006786a  xor     ecx, ecx; BindingHandle
0x18006786c  call    cs:__imp_RpcImpersonateClient
0x180067873  nop     dword ptr [rax+rax+00h]
0x180067878  mov     ecx, eax; Status
0x18006787a  call    cs:__imp_I_RpcMapWin32Status
0x180067881  nop     dword ptr [rax+rax+00h]
0x180067886  mov     ebx, eax
0x180067888  test    eax, eax
0x18006788a  js      short loc_180067861
0x18006788c  mov     rdx, [rbp+var_20]
0x180067890  lea     r8, [rbp+var_28]; struct ldap **
0x180067894  mov     rcx, rdi; HostName
0x180067897  mov     dword ptr [rsp+80h+var_60], esi; int
0x18006789b  mov     rdx, [rdx+28h]; unsigned __int16 *
0x18006789f  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x1800678a4  mov     ebx, eax
0x1800678a6  call    cs:__imp_RpcRevertToSelf
0x1800678ad  nop     dword ptr [rax+rax+00h]
0x1800678b2  test    ebx, ebx
0x1800678b4  jns     short loc_1800678D4
0x1800678b6  lea     rdx, aNetpremoveserv_1; "NetpRemoveServiceAccount: Failed LDAP b"...
0x1800678bd  mov     ecx, 40h ; '@'; unsigned int
0x1800678c2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800678c7  mov     rdi, [rbp+ld]
0x1800678cb  mov     rsi, [rbp+var_28]
0x1800678cf  jmp     loc_1800679E0
0x1800678d4  mov     rdi, [rbp+ld]
0x1800678d8  lea     rax, [rbp+arg_10]
0x1800678dc  mov     rdx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; unsigned __int16 *
0x1800678e3  lea     r9, [rbp+var_18]; unsigned __int16 **
0x1800678e7  mov     rcx, rdi; ld
0x1800678ea  mov     [rbp+arg_10], esi
0x1800678ed  lea     r8, aComputer; "computer"
0x1800678f4  mov     [rsp+80h+var_60], rax; int *
0x1800678f9  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x1800678fe  mov     ebx, eax
0x180067900  test    eax, eax
0x180067902  jns     short loc_18006791E
0x180067904  mov     r8, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18006790b  lea     rdx, aNetpremoveserv_2; "NetpRemoveServiceAccount: Failed to fin"...
0x180067912  mov     ecx, 40h ; '@'; unsigned int
0x180067917  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006791c  jmp     short loc_1800678CB
0x18006791e  mov     rsi, [rbp+var_28]
0x180067922  lea     rax, [rbp+arg_18]
0x180067926  mov     rdx, [rbp+Buffer]; unsigned __int16 *
0x18006792a  lea     r9, [rbp+dn]; unsigned __int16 **
0x18006792e  mov     [rsp+80h+var_58], rax; int *
0x180067933  lea     r8, [rbp+var_40]; int *
0x180067937  mov     rax, [rbp+var_18]
0x18006793b  mov     rcx, rsi; ld
0x18006793e  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180067943  call    ?NetpGetServiceAccountObject@@YAJPEAUldap@@PEBGPEAHPEAPEAG12@Z; NetpGetServiceAccountObject(ldap *,ushort const *,int *,ushort * *,ushort const *,int *)
0x180067948  mov     ebx, eax
0x18006794a  cmp     eax, 90100h
0x18006794f  jnz     short loc_180067958
0x180067951  mov     ebx, 0C000005Ah
0x180067956  jmp     short loc_18006795C
0x180067958  test    eax, eax
0x18006795a  jns     short loc_180067973
0x18006795c  mov     r8, [rbp+Buffer]
0x180067960  lea     rdx, aNetpaddservice_5; "NetpAddServiceAccount: Failed to find s"...
0x180067967  mov     ecx, 40h ; '@'; unsigned int
0x18006796c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067971  jmp     short loc_1800679E0
0x180067973  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x180067977  call    ?NlDeleteServiceAccount@@YAJPEAG@Z; NlDeleteServiceAccount(ushort *)
0x18006797c  mov     ebx, eax
0x18006797e  test    eax, eax
0x180067980  jns     short loc_18006798E
0x180067982  lea     rdx, aNetpremoveserv_4; "NetpRemoveServiceAccount: Failed to sto"...
0x180067989  jmp     loc_180067820
0x18006798e  test    r14d, r14d
0x180067991  jnz     short loc_1800679D7
0x180067993  test    r15b, 1
0x180067997  jz      short loc_1800679AB
0x180067999  mov     r8, [rbp+dn]; unsigned __int16 *
0x18006799d  mov     rcx, rdi; struct ldap *
0x1800679a0  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800679a4  call    ?NetpUnlinkServiceAccount@@YAJPEAUldap@@PEBG1@Z; NetpUnlinkServiceAccount(ldap *,ushort const *,ushort const *)
0x1800679a9  jmp     short loc_1800679C5
0x1800679ab  mov     rdx, [rbp+dn]; dn
0x1800679af  mov     rcx, rsi; ld
0x1800679b2  call    cs:__imp_ldap_delete_sW
0x1800679b9  nop     dword ptr [rax+rax+00h]
0x1800679be  mov     ecx, eax; unsigned int
0x1800679c0  call    ?NetpMapLdapErrorToNtStatus@@YAJK@Z; NetpMapLdapErrorToNtStatus(ulong)
0x1800679c5  mov     ebx, eax
0x1800679c7  test    eax, eax
0x1800679c9  jns     short loc_1800679D7
0x1800679cb  lea     rdx, aNetpremoveserv_5; "NetpRemoveServiceAccount: Failed to unl"...
0x1800679d2  jmp     loc_180067820
0x1800679d7  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x1800679db  call    ?NetpDeleteAccountSecret@@YAJPEBG@Z; NetpDeleteAccountSecret(ushort const *)
0x1800679e0  mov     rcx, [rbp+Buffer]; Buffer
0x1800679e4  test    rcx, rcx
0x1800679e7  jz      short loc_1800679F5
0x1800679e9  call    cs:__imp_NetApiBufferFree
0x1800679f0  nop     dword ptr [rax+rax+00h]
0x1800679f5  mov     rcx, [rbp+var_20]; Buffer
0x1800679f9  test    rcx, rcx
0x1800679fc  jz      short loc_180067A0A
0x1800679fe  call    cs:__imp_NetApiBufferFree
0x180067a05  nop     dword ptr [rax+rax+00h]
0x180067a0a  test    rdi, rdi
0x180067a0d  jz      short loc_180067A1E
0x180067a0f  mov     rcx, rdi; ld
0x180067a12  call    cs:__imp_ldap_unbind
0x180067a19  nop     dword ptr [rax+rax+00h]
0x180067a1e  test    rsi, rsi
0x180067a21  jz      short loc_180067A32
0x180067a23  mov     rcx, rsi; ld
0x180067a26  call    cs:__imp_ldap_unbind
0x180067a2d  nop     dword ptr [rax+rax+00h]
0x180067a32  mov     rcx, [rbp+var_18]; Buffer
0x180067a36  test    rcx, rcx
0x180067a39  jz      short loc_180067A47
0x180067a3b  call    cs:__imp_NetApiBufferFree
0x180067a42  nop     dword ptr [rax+rax+00h]
0x180067a47  mov     rcx, [rbp+dn]; Buffer
0x180067a4b  test    rcx, rcx
0x180067a4e  jz      short loc_180067A5C
0x180067a50  call    cs:__imp_NetApiBufferFree
0x180067a57  nop     dword ptr [rax+rax+00h]
0x180067a5c  mov     r9d, ebx
0x180067a5f  lea     rdx, aExitingNetprem; "Exiting NetpRemoveServiceAccount for ac"...
0x180067a66  mov     r8, r12
0x180067a69  mov     ecx, 40h ; '@'; unsigned int
0x180067a6e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067a73  mov     eax, ebx
0x180067a75  lea     r11, [rsp+80h+var_s0]
0x180067a7d  mov     rbx, [r11+30h]
0x180067a81  mov     rsi, [r11+38h]
0x180067a85  mov     rsp, r11
0x180067a88  pop     r15
0x180067a8a  pop     r14
0x180067a8c  pop     r12
0x180067a8e  pop     rdi
0x180067a8f  pop     rbp
0x180067a90  retn
```
