# NetpRemoveServiceAccount(ushort const *,ulong)

- ea: `0x180062ee0`
- end: `0x1800631d5`
- name: `?NetpRemoveServiceAccount@@YAJPEBGK@Z`
- size: `757`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b400`

## callees

- `0x180004420`
- `0x180007278`
- `0x18000d100`
- `0x18000d9a8`
- `0x180061920`
- `0x180061e88`
- `0x180062270`
- `0x180062604`
- `0x1800627cc`
- `0x1800629d0`
- `0x180062ee0`
- `0x180063680`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180062fec`
- `RPCRT4!RpcImpersonateClient` at `0x180062fec`
- `RPCRT4!RpcRevertToSelf` at `0x18006301a`
- `RPCRT4!RpcRevertToSelf` at `0x18006301a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180062ff4`
- `RPCRT4!I_RpcMapWin32Status` at `0x180062ff4`
- `netutils!NetApiBufferFree` at `0x180063151`
- `netutils!NetApiBufferFree` at `0x180063160`
- `netutils!NetApiBufferFree` at `0x18006318b`
- `netutils!NetApiBufferFree` at `0x18006319a`
- `netutils!NetApiBufferFree` at `0x180063151`
- `netutils!NetApiBufferFree` at `0x180063160`
- `netutils!NetApiBufferFree` at `0x18006318b`
- `netutils!NetApiBufferFree` at `0x18006319a`
- `WLDAP32!__imp_ldap_unbind` at `0x18006316e`
- `WLDAP32!__imp_ldap_unbind` at `0x18006317c`
- `WLDAP32!__imp_ldap_unbind` at `0x18006316e`
- `WLDAP32!__imp_ldap_unbind` at `0x18006317c`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180063120`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180063120`

## string_xrefs

- `0x18006305b`: `computer`
- `0x180062f31`: `Entering NetpRemoveServiceAccount for account %s, flags 0x%08X\n`
- `0x180062f99`: `NetpRemoveServiceAccount: Failed to find usable DC\n`
- `0x180062fd0`: `NetpRemoveServiceAccount: Failed LDAP bind as SYSTEM\n`
- `0x180063024`: `NetpRemoveServiceAccount: Failed LDAP bind as caller\n`
- `0x180063079`: `NetpRemoveServiceAccount: Failed to find computer account object for %s\n`
- `0x1800630ce`: `NetpAddServiceAccount: Failed to find service account object for %s\n`
- `0x1800630f0`: `NetpRemoveServiceAccount: Failed to stop password management\n`
- `0x180063133`: `NetpRemoveServiceAccount: Failed to unlink or delete service account\n`
- `0x1800631a3`: `Exiting NetpRemoveServiceAccount for account %s, Status 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetpRemoveServiceAccount(const unsigned __int16 *a1, unsigned int a2)
{
  LDAP *v2; // rsi
  LDAP *v3; // rdi
  char v4; // r15
  __int64 result; // rax
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
  result = NetpProcessAccountName(a1, &Buffer);
  if ( (int)result < 0 )
    return result;
  if ( (v4 & 2) != 0 )
    goto LABEL_19;
  DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0, 0, 0, 0x40001000u, (struct _DOMAIN_CONTROLLER_INFOW **)&v20);
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
  return (unsigned int)AccountObject;
}

```

## disassembly

```asm
0x180062ee0  mov     [rsp-28h+arg_0], rbx
0x180062ee5  mov     [rsp-28h+arg_8], rsi
0x180062eea  push    rbp
0x180062eeb  push    rdi
0x180062eec  push    r12
0x180062eee  push    r14
0x180062ef0  push    r15
0x180062ef2  mov     rbp, rsp
0x180062ef5  sub     rsp, 80h
0x180062efc  xor     esi, esi
0x180062efe  mov     [rbp+Buffer], 0
0x180062f06  xor     edi, edi
0x180062f08  mov     [rbp+var_20], 0
0x180062f10  mov     r15d, edx
0x180062f13  mov     [rbp+ld], rdi
0x180062f17  mov     r12, rcx
0x180062f1a  mov     [rbp+var_28], rsi
0x180062f1e  mov     r9d, edx
0x180062f21  mov     [rbp+var_40], esi
0x180062f24  mov     r8, rcx
0x180062f27  mov     [rbp+arg_18], esi
0x180062f2a  lea     ecx, [rdi+40h]; unsigned int
0x180062f2d  mov     [rbp+dn], rsi
0x180062f31  lea     rdx, aEnteringNetpre; "Entering NetpRemoveServiceAccount for a"...
0x180062f38  mov     [rbp+var_18], rsi
0x180062f3c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062f41  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180062f45  mov     rcx, r12; unsigned __int16 *
0x180062f48  call    ?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z; NetpProcessAccountName(ushort const *,ushort * *)
0x180062f4d  test    eax, eax
0x180062f4f  js      loc_1800631B9
0x180062f55  mov     r14d, r15d
0x180062f58  and     r14d, 2
0x180062f5c  jnz     loc_1800630E1
0x180062f62  lea     rax, [rbp+var_20]
0x180062f66  xor     r9d, r9d
0x180062f69  mov     [rsp+80h+var_48], rax
0x180062f6e  xor     r8d, r8d
0x180062f71  mov     [rsp+80h+var_50], 40001000h
0x180062f79  xor     edx, edx
0x180062f7b  mov     [rsp+80h+var_58], rsi
0x180062f80  xor     ecx, ecx
0x180062f82  mov     [rsp+80h+var_60], rsi
0x180062f87  call    DsrGetDcNameEx2
0x180062f8c  mov     ecx, eax
0x180062f8e  call    NetpApiStatusToNtStatus
0x180062f93  mov     ebx, eax
0x180062f95  test    eax, eax
0x180062f97  jns     short loc_180062FAF
0x180062f99  lea     rdx, aNetpremoveserv; "NetpRemoveServiceAccount: Failed to fin"...
0x180062fa0  mov     ecx, 40h ; '@'; unsigned int
0x180062fa5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062faa  jmp     loc_180063148
0x180062faf  mov     rdx, [rbp+var_20]
0x180062fb3  lea     r8, [rbp+ld]; struct ldap **
0x180062fb7  mov     dword ptr [rsp+80h+var_60], esi; int
0x180062fbb  mov     rdi, [rdx]
0x180062fbe  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180062fc2  mov     rcx, rdi; HostName
0x180062fc5  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180062fca  mov     ebx, eax
0x180062fcc  test    eax, eax
0x180062fce  jns     short loc_180062FEA
0x180062fd0  lea     rdx, aNetpremoveserv_3; "NetpRemoveServiceAccount: Failed LDAP b"...
0x180062fd7  mov     ecx, 40h ; '@'; unsigned int
0x180062fdc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062fe1  mov     rdi, [rbp+ld]
0x180062fe5  jmp     loc_180063148
0x180062fea  xor     ecx, ecx; BindingHandle
0x180062fec  call    cs:__imp_RpcImpersonateClient
0x180062ff2  mov     ecx, eax; Status
0x180062ff4  call    cs:__imp_I_RpcMapWin32Status
0x180062ffa  mov     ebx, eax
0x180062ffc  test    eax, eax
0x180062ffe  js      short loc_180062FE1
0x180063000  mov     rdx, [rbp+var_20]
0x180063004  lea     r8, [rbp+var_28]; struct ldap **
0x180063008  mov     rcx, rdi; HostName
0x18006300b  mov     dword ptr [rsp+80h+var_60], esi; int
0x18006300f  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180063013  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180063018  mov     ebx, eax
0x18006301a  call    cs:__imp_RpcRevertToSelf
0x180063020  test    ebx, ebx
0x180063022  jns     short loc_180063042
0x180063024  lea     rdx, aNetpremoveserv_1; "NetpRemoveServiceAccount: Failed LDAP b"...
0x18006302b  mov     ecx, 40h ; '@'; unsigned int
0x180063030  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180063035  mov     rdi, [rbp+ld]
0x180063039  mov     rsi, [rbp+var_28]
0x18006303d  jmp     loc_180063148
0x180063042  mov     rdi, [rbp+ld]
0x180063046  lea     rax, [rbp+arg_10]
0x18006304a  mov     rdx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; unsigned __int16 *
0x180063051  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180063055  mov     rcx, rdi; ld
0x180063058  mov     [rbp+arg_10], esi
0x18006305b  lea     r8, aComputer; "computer"
0x180063062  mov     [rsp+80h+var_60], rax; int *
0x180063067  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x18006306c  mov     ebx, eax
0x18006306e  test    eax, eax
0x180063070  jns     short loc_18006308C
0x180063072  mov     r8, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x180063079  lea     rdx, aNetpremoveserv_2; "NetpRemoveServiceAccount: Failed to fin"...
0x180063080  mov     ecx, 40h ; '@'; unsigned int
0x180063085  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006308a  jmp     short loc_180063039
0x18006308c  mov     rsi, [rbp+var_28]
0x180063090  lea     rax, [rbp+arg_18]
0x180063094  mov     rdx, [rbp+Buffer]; unsigned __int16 *
0x180063098  lea     r9, [rbp+dn]; unsigned __int16 **
0x18006309c  mov     [rsp+80h+var_58], rax; int *
0x1800630a1  lea     r8, [rbp+var_40]; int *
0x1800630a5  mov     rax, [rbp+var_18]
0x1800630a9  mov     rcx, rsi; ld
0x1800630ac  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800630b1  call    ?NetpGetServiceAccountObject@@YAJPEAUldap@@PEBGPEAHPEAPEAG12@Z; NetpGetServiceAccountObject(ldap *,ushort const *,int *,ushort * *,ushort const *,int *)
0x1800630b6  mov     ebx, eax
0x1800630b8  cmp     eax, 90100h
0x1800630bd  jnz     short loc_1800630C6
0x1800630bf  mov     ebx, 0C000005Ah
0x1800630c4  jmp     short loc_1800630CA
0x1800630c6  test    eax, eax
0x1800630c8  jns     short loc_1800630E1
0x1800630ca  mov     r8, [rbp+Buffer]
0x1800630ce  lea     rdx, aNetpaddservice_5; "NetpAddServiceAccount: Failed to find s"...
0x1800630d5  mov     ecx, 40h ; '@'; unsigned int
0x1800630da  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800630df  jmp     short loc_180063148
0x1800630e1  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x1800630e5  call    ?NlDeleteServiceAccount@@YAJPEAG@Z; NlDeleteServiceAccount(ushort *)
0x1800630ea  mov     ebx, eax
0x1800630ec  test    eax, eax
0x1800630ee  jns     short loc_1800630FC
0x1800630f0  lea     rdx, aNetpremoveserv_4; "NetpRemoveServiceAccount: Failed to sto"...
0x1800630f7  jmp     loc_180062FA0
0x1800630fc  test    r14d, r14d
0x1800630ff  jnz     short loc_18006313F
0x180063101  test    r15b, 1
0x180063105  jz      short loc_180063119
0x180063107  mov     r8, [rbp+dn]; unsigned __int16 *
0x18006310b  mov     rcx, rdi; struct ldap *
0x18006310e  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x180063112  call    ?NetpUnlinkServiceAccount@@YAJPEAUldap@@PEBG1@Z; NetpUnlinkServiceAccount(ldap *,ushort const *,ushort const *)
0x180063117  jmp     short loc_18006312D
0x180063119  mov     rdx, [rbp+dn]; dn
0x18006311d  mov     rcx, rsi; ld
0x180063120  call    cs:__imp_ldap_delete_sW
0x180063126  mov     ecx, eax; unsigned int
0x180063128  call    ?NetpMapLdapErrorToNtStatus@@YAJK@Z; NetpMapLdapErrorToNtStatus(ulong)
0x18006312d  mov     ebx, eax
0x18006312f  test    eax, eax
0x180063131  jns     short loc_18006313F
0x180063133  lea     rdx, aNetpremoveserv_5; "NetpRemoveServiceAccount: Failed to unl"...
0x18006313a  jmp     loc_180062FA0
0x18006313f  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x180063143  call    ?NetpDeleteAccountSecret@@YAJPEBG@Z; NetpDeleteAccountSecret(ushort const *)
0x180063148  mov     rcx, [rbp+Buffer]; Buffer
0x18006314c  test    rcx, rcx
0x18006314f  jz      short loc_180063157
0x180063151  call    cs:__imp_NetApiBufferFree
0x180063157  mov     rcx, [rbp+var_20]; Buffer
0x18006315b  test    rcx, rcx
0x18006315e  jz      short loc_180063166
0x180063160  call    cs:__imp_NetApiBufferFree
0x180063166  test    rdi, rdi
0x180063169  jz      short loc_180063174
0x18006316b  mov     rcx, rdi; ld
0x18006316e  call    cs:__imp_ldap_unbind
0x180063174  test    rsi, rsi
0x180063177  jz      short loc_180063182
0x180063179  mov     rcx, rsi; ld
0x18006317c  call    cs:__imp_ldap_unbind
0x180063182  mov     rcx, [rbp+var_18]; Buffer
0x180063186  test    rcx, rcx
0x180063189  jz      short loc_180063191
0x18006318b  call    cs:__imp_NetApiBufferFree
0x180063191  mov     rcx, [rbp+dn]; Buffer
0x180063195  test    rcx, rcx
0x180063198  jz      short loc_1800631A0
0x18006319a  call    cs:__imp_NetApiBufferFree
0x1800631a0  mov     r9d, ebx
0x1800631a3  lea     rdx, aExitingNetprem; "Exiting NetpRemoveServiceAccount for ac"...
0x1800631aa  mov     r8, r12
0x1800631ad  mov     ecx, 40h ; '@'; unsigned int
0x1800631b2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800631b7  mov     eax, ebx
0x1800631b9  lea     r11, [rsp+80h+var_s0]
0x1800631c1  mov     rbx, [r11+30h]
0x1800631c5  mov     rsi, [r11+38h]
0x1800631c9  mov     rsp, r11
0x1800631cc  pop     r15
0x1800631ce  pop     r14
0x1800631d0  pop     r12
0x1800631d2  pop     rdi
0x1800631d3  pop     rbp
0x1800631d4  retn
```
