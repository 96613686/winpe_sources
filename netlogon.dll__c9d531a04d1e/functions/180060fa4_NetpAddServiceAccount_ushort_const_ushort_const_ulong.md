# NetpAddServiceAccount(ushort const *,ushort const *,ulong)

- ea: `0x180060fa4`
- end: `0x1800614f5`
- name: `?NetpAddServiceAccount@@YAJPEBG0K@Z`
- size: `1361`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b110`

## callees

- `0x180004420`
- `0x180007278`
- `0x18000d100`
- `0x18000d9a8`
- `0x18003f300`
- `0x180053160`
- `0x180060fa4`
- `0x180061920`
- `0x180061e88`
- `0x180062270`
- `0x180062604`
- `0x1800627cc`
- `0x1800629d0`
- `0x1800631dc`
- `0x180063230`
- `0x180063448`
- `0x180063680`
- `0x1800636d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180061413`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180061413`
- `RPCRT4!RpcImpersonateClient` at `0x1800610fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800610fa`
- `RPCRT4!RpcRevertToSelf` at `0x180061129`
- `RPCRT4!RpcRevertToSelf` at `0x180061129`
- `RPCRT4!I_RpcMapWin32Status` at `0x180061102`
- `RPCRT4!I_RpcMapWin32Status` at `0x180061102`
- `ntdll!RtlLeaveCriticalSection` at `0x180061439`
- `ntdll!RtlLeaveCriticalSection` at `0x180061439`
- `ntdll!RtlEnterCriticalSection` at `0x180061406`
- `ntdll!RtlEnterCriticalSection` at `0x180061406`
- `netutils!NetApiBufferFree` at `0x180061450`
- `netutils!NetApiBufferFree` at `0x180061479`
- `netutils!NetApiBufferFree` at `0x180061488`
- `netutils!NetApiBufferFree` at `0x1800614b3`
- `netutils!NetApiBufferFree` at `0x1800614c2`
- `netutils!NetApiBufferFree` at `0x180061450`
- `netutils!NetApiBufferFree` at `0x180061479`
- `netutils!NetApiBufferFree` at `0x180061488`
- `netutils!NetApiBufferFree` at `0x1800614b3`
- `netutils!NetApiBufferFree` at `0x1800614c2`
- `WLDAP32!__imp_ldap_unbind` at `0x180061496`
- `WLDAP32!__imp_ldap_unbind` at `0x1800614a4`
- `WLDAP32!__imp_ldap_unbind` at `0x180061496`
- `WLDAP32!__imp_ldap_unbind` at `0x1800614a4`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1800613d1`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1800613d1`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800612a3`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1800612a3`

## string_xrefs

- `0x180061161`: `computer`
- `0x18006126d`: `msDS-HostServiceAccount`
- `0x180061007`: `Entering NetpAddServiceAccount for account %s, flags 0x%08X\n`
- `0x1800610a1`: `NetpAddServiceAccount: Provided password must accompany RODC add\n`
- `0x180061087`: `NetpAddServiceAccount: Failed to locate usable domain controller\n`
- `0x1800610de`: `NetpAddServiceAccount: Failed to bind to LDAP as SYSTEM\n`
- `0x180061133`: `NetpAddServiceAccount: Failed to bind to LDAP as caller\n`
- `0x180061182`: `NetpAddServiceAccount: Failed to find computer account object for %s\n`
- `0x1800611d0`: `NetpAddServiceAccount: Failed to find or create service account object for %s\n`
- `0x1800611f1`: `NetpAddServiceAccount: Account CREATED\n`
- `0x180061212`: `NetpAddServiceAccount: Account password management STOPPED\n`
- `0x180061251`: `NetpAddServiceAccount: RODC add requires that the account be pre-linked\n`
- `0x1800612bb`: `NetpAddServiceAccount: Failed to link service account to computer\n`
- `0x1800612c7`: `NetpAddServiceAccount: Account LINKED\n`
- `0x1800612ec`: `NetpAddServiceAccount: Failed to set password on service account\n`
- `0x180061314`: `NetpAddServiceAccount: Failed to write local account secret\n`
- `0x180061340`: `NetpAddServiceAccount: Failed to enable service account\n`
- `0x180061349`: `NetpAddServiceAccount: Account ENABLED\n`
- `0x180061367`: `NetpAddServiceAccount: Failed to start password management for account\n`
- `0x18006138b`: `NetpAddServiceAccount: RODC join could not validate provided credential\n`
- `0x1800614cb`: `Exiting NetpAddServiceAccount for account %s, Status 0x%08X\n`

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
  DcNameEx2 = DsrGetDcNameEx2(
                0,
                0,
                0,
                0,
                0,
                0,
                (v9 == 0 ? 0x1000 : 0) | 0x40000000u,
                (struct _DOMAIN_CONTROLLER_INFOW **)&v28);
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
            dword_1800F1BC8 = 15000;
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
0x180060fa4  mov     [rsp-8+arg_8], rdx
0x180060fa9  mov     [rsp-8+arg_0], rcx
0x180060fae  push    rbp
0x180060faf  push    rbx
0x180060fb0  push    rsi
0x180060fb1  push    rdi
0x180060fb2  push    r12
0x180060fb4  push    r13
0x180060fb6  push    r14
0x180060fb8  push    r15
0x180060fba  lea     rbp, [rsp-1Fh]
0x180060fbf  sub     rsp, 0B8h
0x180060fc6  xor     r14d, r14d
0x180060fc9  mov     [rbp+57h+Buffer], 0
0x180060fd1  mov     esi, r8d
0x180060fd4  mov     [rbp+57h+var_90], 0
0x180060fdc  mov     r9d, r8d
0x180060fdf  mov     [rbp+57h+ld], r14
0x180060fe3  mov     rdi, rdx
0x180060fe6  mov     [rbp+57h+var_78], r14d
0x180060fea  mov     r12, rcx
0x180060fed  mov     [rbp+57h+var_A8], r14
0x180060ff1  mov     r8, rcx
0x180060ff4  mov     [rbp+57h+dn], r14
0x180060ff8  xor     r15d, r15d
0x180060ffb  mov     [rbp+57h+var_A0], r14
0x180060fff  lea     ecx, [r14+40h]; unsigned int
0x180061003  mov     [rbp+57h+var_70], r15
0x180061007  lea     rdx, aEnteringNetpad; "Entering NetpAddServiceAccount for acco"...
0x18006100e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061013  test    sil, 3
0x180061017  lea     ecx, [r14+1]
0x18006101b  cmovnz  ecx, r14d
0x18006101f  and     esi, 2
0x180061022  mov     [rbp+57h+arg_10], ecx
0x180061025  test    rdi, rdi
0x180061028  jz      short loc_18006109D
0x18006102a  test    esi, esi
0x18006102c  jz      short loc_1800610A1
0x18006102e  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 **
0x180061032  mov     rcx, r12; unsigned __int16 *
0x180061035  call    ?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z; NetpProcessAccountName(ushort const *,ushort * *)
0x18006103a  test    eax, eax
0x18006103c  js      loc_1800614E1
0x180061042  mov     eax, esi
0x180061044  neg     eax
0x180061046  lea     rax, [rbp+57h+var_90]
0x18006104a  sbb     ecx, ecx
0x18006104c  mov     [rsp+0F0h+var_B8], rax
0x180061051  not     ecx
0x180061053  xor     r9d, r9d
0x180061056  and     ecx, 1000h
0x18006105c  xor     r8d, r8d
0x18006105f  bts     ecx, 1Eh
0x180061063  xor     edx, edx
0x180061065  mov     [rsp+0F0h+var_C0], ecx
0x180061069  xor     ecx, ecx
0x18006106b  mov     [rsp+0F0h+var_C8], r14
0x180061070  mov     [rsp+0F0h+var_D0], r14
0x180061075  call    DsrGetDcNameEx2
0x18006107a  mov     ecx, eax
0x18006107c  call    NetpApiStatusToNtStatus
0x180061081  mov     ebx, eax
0x180061083  test    eax, eax
0x180061085  jns     short loc_1800610BC
0x180061087  lea     rdx, aNetpaddservice_14; "NetpAddServiceAccount: Failed to locate"...
0x18006108e  mov     ecx, 40h ; '@'; unsigned int
0x180061093  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061098  jmp     loc_180061447
0x18006109d  test    esi, esi
0x18006109f  jz      short loc_18006102E
0x1800610a1  lea     rdx, aNetpaddservice_6; "NetpAddServiceAccount: Provided passwor"...
0x1800610a8  mov     ecx, 40h ; '@'; unsigned int
0x1800610ad  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800610b2  mov     eax, 0C000000Dh
0x1800610b7  jmp     loc_1800614E1
0x1800610bc  mov     rdx, [rbp+57h+var_90]
0x1800610c0  lea     r8, [rbp+57h+ld]; struct ldap **
0x1800610c4  mov     dword ptr [rsp+0F0h+var_D0], r14d; int
0x1800610c9  mov     r13, [rdx]
0x1800610cc  mov     rdx, [rdx+28h]; unsigned __int16 *
0x1800610d0  mov     rcx, r13; HostName
0x1800610d3  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x1800610d8  mov     ebx, eax
0x1800610da  test    eax, eax
0x1800610dc  jns     short loc_1800610F8
0x1800610de  lea     rdx, aNetpaddservice_17; "NetpAddServiceAccount: Failed to bind t"...
0x1800610e5  mov     ecx, 40h ; '@'; unsigned int
0x1800610ea  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800610ef  mov     r14, [rbp+57h+ld]
0x1800610f3  jmp     loc_180061447
0x1800610f8  xor     ecx, ecx; BindingHandle
0x1800610fa  call    cs:__imp_RpcImpersonateClient
0x180061100  mov     ecx, eax; Status
0x180061102  call    cs:__imp_I_RpcMapWin32Status
0x180061108  mov     ebx, eax
0x18006110a  test    eax, eax
0x18006110c  js      short loc_1800610EF
0x18006110e  mov     rdx, [rbp+57h+var_90]
0x180061112  lea     r8, [rbp+57h+var_70]; struct ldap **
0x180061116  mov     rcx, r13; HostName
0x180061119  mov     dword ptr [rsp+0F0h+var_D0], r14d; int
0x18006111e  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180061122  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180061127  mov     ebx, eax
0x180061129  call    cs:__imp_RpcRevertToSelf
0x18006112f  test    ebx, ebx
0x180061131  jns     short loc_18006114A
0x180061133  lea     rdx, aNetpaddservice_0; "NetpAddServiceAccount: Failed to bind t"...
0x18006113a  mov     ecx, 40h ; '@'; unsigned int
0x18006113f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061144  mov     r14, [rbp+57h+ld]
0x180061148  jmp     short loc_180061193
0x18006114a  mov     rdx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; unsigned __int16 *
0x180061151  lea     rax, [rbp+57h+arg_18]
0x180061155  mov     [rbp+57h+arg_18], r14d
0x180061159  lea     r9, [rbp+57h+dn]; unsigned __int16 **
0x18006115d  mov     r14, [rbp+57h+ld]
0x180061161  lea     r8, aComputer; "computer"
0x180061168  mov     rcx, r14; ld
0x18006116b  mov     [rsp+0F0h+var_D0], rax; int *
0x180061170  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x180061175  mov     ebx, eax
0x180061177  test    eax, eax
0x180061179  jns     short loc_18006119C
0x18006117b  mov     r8, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x180061182  lea     rdx, aNetpaddservice_3; "NetpAddServiceAccount: Failed to find c"...
0x180061189  mov     ecx, 40h ; '@'; unsigned int
0x18006118e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061193  mov     r15, [rbp+57h+var_70]
0x180061197  jmp     loc_180061447
0x18006119c  mov     r15, [rbp+57h+var_70]
0x1800611a0  lea     rax, [rbp+57h+var_78]
0x1800611a4  mov     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800611a8  lea     r9, [rbp+57h+var_A8]; unsigned __int16 **
0x1800611ac  mov     [rsp+0F0h+var_C8], rax; int *
0x1800611b1  lea     r8, [rbp+57h+arg_10]; int *
0x1800611b5  mov     rax, [rbp+57h+dn]
0x1800611b9  mov     rcx, r15; ld
0x1800611bc  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x1800611c1  call    ?NetpGetServiceAccountObject@@YAJPEAUldap@@PEBGPEAHPEAPEAG12@Z; NetpGetServiceAccountObject(ldap *,ushort const *,int *,ushort * *,ushort const *,int *)
0x1800611c6  mov     ebx, eax
0x1800611c8  test    eax, eax
0x1800611ca  jns     short loc_1800611E6
0x1800611cc  mov     r8, [rbp+57h+Buffer]
0x1800611d0  lea     rdx, aNetpaddservice_13; "NetpAddServiceAccount: Failed to find o"...
0x1800611d7  mov     ecx, 40h ; '@'; unsigned int
0x1800611dc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800611e1  jmp     loc_180061447
0x1800611e6  mov     r12d, [rbp+57h+arg_10]
0x1800611ea  xor     edi, edi
0x1800611ec  test    r12d, r12d
0x1800611ef  jz      short loc_180061205
0x1800611f1  lea     rdx, aNetpaddservice_9; "NetpAddServiceAccount: Account CREATED"...
0x1800611f8  lea     ecx, [rdi+40h]; unsigned int
0x1800611fb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061200  mov     edi, 1
0x180061205  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x180061209  call    ?NlDeleteServiceAccount@@YAJPEAG@Z; NlDeleteServiceAccount(ushort *)
0x18006120e  test    eax, eax
0x180061210  js      short loc_180061226
0x180061212  lea     rdx, aNetpaddservice_7; "NetpAddServiceAccount: Account password"...
0x180061219  mov     ecx, 40h ; '@'; unsigned int
0x18006121e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061223  or      edi, 10h
0x180061226  cmp     ebx, 90100h
0x18006122c  jz      short loc_180061248
0x18006122e  test    r12d, r12d
0x180061231  jnz     short loc_180061248
0x180061233  test    esi, esi
0x180061235  jz      loc_1800612D6
0x18006123b  mov     rdx, [rbp+57h+arg_8]
0x18006123f  mov     [rbp+57h+var_A0], rdx
0x180061243  jmp     loc_1800612FC
0x180061248  test    esi, esi
0x18006124a  jz      short loc_18006125D
0x18006124c  mov     ebx, 0C000005Ah
0x180061251  lea     rdx, aNetpaddservice_1; "NetpAddServiceAccount: RODC add require"...
0x180061258  jmp     loc_180061392
0x18006125d  mov     rdx, [rbp+57h+dn]; dn
0x180061261  lea     rax, [rbp+57h+var_60]
0x180061265  mov     [rbp+57h+ld], rax
0x180061269  lea     r8, [rbp+57h+ld]; mods
0x18006126d  lea     rax, aMsdsHostservic; "msDS-HostServiceAccount"
0x180061274  mov     [rbp+57h+var_60], 0
0x18006127c  mov     [rbp+57h+var_58], rax
0x180061280  mov     rcx, r14; ld
0x180061283  lea     rax, [rbp+57h+var_70]
0x180061287  mov     [rbp+57h+var_80], 0
0x18006128f  mov     [rbp+57h+var_50], rax
0x180061293  mov     rax, [rbp+57h+var_A8]
0x180061297  mov     [rbp+57h+var_70], rax
0x18006129b  mov     [rbp+57h+var_68], 0
0x1800612a3  call    cs:__imp_ldap_modify_sW
0x1800612a9  mov     ecx, eax; unsigned int
0x1800612ab  call    ?NetpMapLdapErrorToNtStatus@@YAJK@Z; NetpMapLdapErrorToNtStatus(ulong)
0x1800612b0  mov     ebx, eax
0x1800612b2  mov     ecx, 40h ; '@'; unsigned int
0x1800612b7  test    eax, eax
0x1800612b9  jns     short loc_1800612C7
0x1800612bb  lea     rdx, aNetpaddservice_8; "NetpAddServiceAccount: Failed to link s"...
0x1800612c2  jmp     loc_180061397
0x1800612c7  lea     rdx, aNetpaddservice_12; "NetpAddServiceAccount: Account LINKED\n"
0x1800612ce  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800612d3  or      edi, 2
0x1800612d6  mov     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800612da  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x1800612de  mov     rcx, r13; servername
0x1800612e1  call    ?NetpSetAccountPassword@@YAJPEBG0PEAPEAG@Z; NetpSetAccountPassword(ushort const *,ushort const *,ushort * *)
0x1800612e6  mov     ebx, eax
0x1800612e8  test    eax, eax
0x1800612ea  jns     short loc_1800612F8
0x1800612ec  lea     rdx, aNetpaddservice; "NetpAddServiceAccount: Failed to set pa"...
0x1800612f3  jmp     loc_180061392
0x1800612f8  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x1800612fc  mov     rcx, [rbp+57h+Buffer]; SourceString
0x180061300  xor     r8d, r8d
0x180061303  test    esi, esi
0x180061305  setnz   r8b; int
0x180061309  call    ?NetpSetAccountSecret@@YAJPEBG0H@Z; NetpSetAccountSecret(ushort const *,ushort const *,int)
0x18006130e  mov     ebx, eax
0x180061310  test    eax, eax
0x180061312  jns     short loc_18006131D
0x180061314  lea     rdx, aNetpaddservice_11; "NetpAddServiceAccount: Failed to write "...
0x18006131b  jmp     short loc_180061392
0x18006131d  or      edi, 4
0x180061320  test    esi, esi
0x180061322  jnz     short loc_180061358
0x180061324  mov     rdx, [rbp+57h+var_A8]; unsigned __int16 *
0x180061328  lea     r8, a4096; "4096"
0x18006132f  mov     rcx, r15; struct ldap *
0x180061332  call    ?NetpSetAccountControl@@YAJPEAUldap@@PEBG1@Z; NetpSetAccountControl(ldap *,ushort const *,ushort const *)
0x180061337  lea     ecx, [rsi+40h]; unsigned int
0x18006133a  mov     ebx, eax
0x18006133c  test    eax, eax
0x18006133e  jns     short loc_180061349
0x180061340  lea     rdx, aNetpaddservice_16; "NetpAddServiceAccount: Failed to enable"...
0x180061347  jmp     short loc_180061397
0x180061349  lea     rdx, aNetpaddservice_4; "NetpAddServiceAccount: Account ENABLED"...
0x180061350  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061355  or      edi, 8
0x180061358  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x18006135c  call    ?NlAddServiceAccount@@YAJPEAG@Z; NlAddServiceAccount(ushort *)
0x180061361  mov     ebx, eax
0x180061363  test    eax, eax
0x180061365  jns     short loc_180061370
0x180061367  lea     rdx, aNetpaddservice_15; "NetpAddServiceAccount: Failed to start "...
0x18006136e  jmp     short loc_180061392
0x180061370  test    esi, esi
0x180061372  jz      loc_18006143F
0x180061378  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18006137c  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x180061380  call    ?NetpVerifyServiceAccount@@YAJPEBG0@Z; NetpVerifyServiceAccount(ushort const *,ushort const *)
0x180061385  mov     ebx, eax
0x180061387  test    eax, eax
0x180061389  jns     short loc_1800613FF
0x18006138b  lea     rdx, aNetpaddservice_10; "NetpAddServiceAccount: RODC join could "...
0x180061392  mov     ecx, 40h ; '@'; unsigned int
0x180061397  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006139c  test    dil, 8
0x1800613a0  jz      short loc_1800613B5
0x1800613a2  mov     rdx, [rbp+57h+var_A8]; unsigned __int16 *
0x1800613a6  lea     r8, a4130; "4130"
0x1800613ad  mov     rcx, r15; struct ldap *
0x1800613b0  call    ?NetpSetAccountControl@@YAJPEAUldap@@PEBG1@Z; NetpSetAccountControl(ldap *,ushort const *,ushort const *)
0x1800613b5  test    dil, 4
0x1800613b9  jz      short loc_1800613C4
0x1800613bb  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800613bf  call    ?NetpDeleteAccountSecret@@YAJPEBG@Z; NetpDeleteAccountSecret(ushort const *)
0x1800613c4  test    dil, 1
0x1800613c8  jz      short loc_1800613D9
0x1800613ca  mov     rdx, [rbp+57h+var_A8]; dn
0x1800613ce  mov     rcx, r15; ld
0x1800613d1  call    cs:__imp_ldap_delete_sW
0x1800613d7  jmp     short loc_1800613EF
0x1800613d9  test    dil, 2
0x1800613dd  jz      short loc_1800613EF
0x1800613df  mov     r8, [rbp+57h+var_A8]; unsigned __int16 *
0x1800613e3  mov     rcx, r14; struct ldap *
0x1800613e6  mov     rdx, [rbp+57h+dn]; unsigned __int16 *
0x1800613ea  call    ?NetpUnlinkServiceAccount@@YAJPEAUldap@@PEBG1@Z; NetpUnlinkServiceAccount(ldap *,ushort const *,ushort const *)
0x1800613ef  cmp     edi, 10h
0x1800613f2  jnz     short loc_18006143F
0x1800613f4  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800613f8  call    ?NlAddServiceAccount@@YAJPEAG@Z; NlAddServiceAccount(ushort *)
0x1800613fd  jmp     short loc_18006143F
0x1800613ff  lea     rcx, ?NlGlobalScavengerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180061406  call    cs:__imp_RtlEnterCriticalSection
0x18006140c  lea     rcx, ?NlGlobalScavengerTimer@@3U_TIMER@@A; lpSystemTimeAsFileTime
0x180061413  call    cs:__imp_GetSystemTimeAsFileTime
0x180061419  mov     r8d, 3A98h; unsigned int
0x18006141f  lea     rdx, aNlwksscavenger_0; "NlWksScavenger: Scheduling extra passwo"...
0x180061426  mov     cs:dword_1800F1BC8, r8d
0x18006142d  call    ?NlpDumpPeriod@@YAXKPEADK@Z; NlpDumpPeriod(ulong,char *,ulong)
0x180061432  lea     rcx, ?NlGlobalScavengerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180061439  call    cs:__imp_RtlLeaveCriticalSection
0x18006143f  mov     r12, [rbp+57h+arg_0]
0x180061443  mov     rdi, [rbp+57h+arg_8]
0x180061447  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18006144b  test    rcx, rcx
  ... truncated ...
```
