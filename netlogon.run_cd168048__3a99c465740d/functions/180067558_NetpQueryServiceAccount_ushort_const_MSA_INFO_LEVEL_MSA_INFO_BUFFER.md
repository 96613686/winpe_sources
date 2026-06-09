# NetpQueryServiceAccount(ushort const *,_MSA_INFO_LEVEL,_MSA_INFO_BUFFER *)

- ea: `0x180067558`
- end: `0x180067759`
- name: `?NetpQueryServiceAccount@@YAJPEBGW4_MSA_INFO_LEVEL@@PEAT_MSA_INFO_BUFFER@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum _MSA_INFO_LEVEL, union _MSA_INFO_BUFFER *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x18002bfd8`
- `0x18002c0b8`

## callees

- `0x1800046b0`
- `0x180007518`
- `0x18000d7a0`
- `0x180066d98`
- `0x1800671d4`
- `0x180067400`
- `0x180067558`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180067646`
- `RPCRT4!RpcImpersonateClient` at `0x180067646`
- `RPCRT4!RpcRevertToSelf` at `0x180067684`
- `RPCRT4!RpcRevertToSelf` at `0x180067684`
- `RPCRT4!I_RpcMapWin32Status` at `0x180067654`
- `RPCRT4!I_RpcMapWin32Status` at `0x180067654`
- `netutils!NetApiBufferFree` at `0x1800676d7`
- `netutils!NetApiBufferFree` at `0x1800676ec`
- `netutils!NetApiBufferFree` at `0x1800676d7`
- `netutils!NetApiBufferFree` at `0x1800676ec`
- `WLDAP32!__imp_ldap_unbind` at `0x180067701`
- `WLDAP32!__imp_ldap_unbind` at `0x180067715`
- `WLDAP32!__imp_ldap_unbind` at `0x180067701`
- `WLDAP32!__imp_ldap_unbind` at `0x180067715`

## string_xrefs

- `0x1800675a8`: `Entering NetpQueryServiceAccount for account %s, Level %u\n`
- `0x180067602`: `NetpQueryServiceAccount: Failed to find usable DC\n`
- `0x18006763b`: `NetpQueryServiceAccount: Failed to LDAP bind as SYSTEM\n`
- `0x180067694`: `NetpQueryServiceAccount: Failed to LDAP bind as caller\n`
- `0x180067724`: `Exiting NetpQueryServiceAccount for account %s, Status 0x%08X\n`

## pseudocode

```c
int __fastcall NetpQueryServiceAccount(const unsigned __int16 *a1, enum _MSA_INFO_LEVEL a2, struct _MSA_INFO_0 **a3)
{
  LDAP *v3; // rdi
  int result; // eax
  unsigned int DcNameEx2; // eax
  int ServiceAccount0; // ebx
  void *v9; // r9
  WCHAR *v10; // r14
  RPC_STATUS v11; // eax
  void *v12; // r9
  LPVOID Buffer; // [rsp+40h] [rbp-10h] BYREF
  LDAP *ld; // [rsp+48h] [rbp-8h] BYREF
  LDAP *v15; // [rsp+90h] [rbp+40h] BYREF
  LPVOID v16; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  Buffer = 0;
  v16 = 0;
  ld = 0;
  v15 = 0;
  if ( !a3 )
    return -1073741811;
  NlPrintRoutine(0x40u, L"Entering NetpQueryServiceAccount for account %s, Level %u\n", a1, 0);
  result = NetpProcessAccountName(a1, (unsigned __int16 **)&Buffer);
  if ( result >= 0 )
  {
    DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0x40000000u, (__int64)&v16);
    ServiceAccount0 = NetpApiStatusToNtStatus(DcNameEx2);
    if ( ServiceAccount0 >= 0 )
    {
      v10 = *(WCHAR **)v16;
      ServiceAccount0 = NetpLdapBind(*(PWSTR *)v16, *((const unsigned __int16 **)v16 + 5), &ld, v9, 1);
      if ( ServiceAccount0 >= 0 )
      {
        v11 = RpcImpersonateClient(0);
        ServiceAccount0 = I_RpcMapWin32Status(v11);
        if ( ServiceAccount0 >= 0 )
        {
          ServiceAccount0 = NetpLdapBind(v10, *((const unsigned __int16 **)v16 + 5), &v15, v12, 1);
          RpcRevertToSelf();
          if ( ServiceAccount0 >= 0 )
          {
            v3 = v15;
            if ( *a3 )
              ServiceAccount0 = NetpQueryServiceAccount0((const unsigned __int16 *)Buffer, v15, ld, *a3);
            else
              ServiceAccount0 = -1073741811;
          }
          else
          {
            NlPrintRoutine(0x40u, L"NetpQueryServiceAccount: Failed to LDAP bind as caller\n");
            v3 = v15;
          }
        }
      }
      else
      {
        NlPrintRoutine(0x40u, L"NetpQueryServiceAccount: Failed to LDAP bind as SYSTEM\n");
      }
    }
    else
    {
      NlPrintRoutine(0x40u, L"NetpQueryServiceAccount: Failed to find usable DC\n");
    }
    if ( Buffer )
      NetApiBufferFree(Buffer);
    if ( v16 )
      NetApiBufferFree(v16);
    if ( ld )
      ldap_unbind(ld);
    if ( v3 )
      ldap_unbind(v3);
    NlPrintRoutine(
      0x40u,
      L"Exiting NetpQueryServiceAccount for account %s, Status 0x%08X\n",
      a1,
      (unsigned int)ServiceAccount0);
    return ServiceAccount0;
  }
  return result;
}

```

## disassembly

```asm
0x180067558  mov     [rsp-28h+arg_0], rbx
0x18006755d  mov     [rsp-28h+arg_8], rsi
0x180067562  push    rbp
0x180067563  push    rdi
0x180067564  push    r13
0x180067566  push    r14
0x180067568  push    r15
0x18006756a  mov     rbp, rsp
0x18006756d  sub     rsp, 50h
0x180067571  xor     edi, edi
0x180067573  mov     [rbp+Buffer], 0
0x18006757b  mov     [rbp+arg_18], 0
0x180067583  mov     rsi, r8
0x180067586  mov     [rbp+ld], 0
0x18006758e  mov     r15, rcx
0x180067591  mov     [rbp+arg_10], rdi
0x180067595  test    r8, r8
0x180067598  jz      loc_18006773A
0x18006759e  mov     r8, rcx
0x1800675a1  lea     r13d, [rdi+40h]
0x1800675a5  mov     ecx, r13d; unsigned int
0x1800675a8  lea     rdx, aEnteringNetpqu; "Entering NetpQueryServiceAccount for ac"...
0x1800675af  xor     r9d, r9d
0x1800675b2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800675b7  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x1800675bb  mov     rcx, r15; unsigned __int16 *
0x1800675be  call    ?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z; NetpProcessAccountName(ushort const *,ushort * *)
0x1800675c3  test    eax, eax
0x1800675c5  js      loc_18006773F
0x1800675cb  lea     rax, [rbp+arg_18]
0x1800675cf  xor     r9d, r9d
0x1800675d2  mov     [rsp+50h+var_18], rax
0x1800675d7  xor     r8d, r8d
0x1800675da  mov     [rsp+50h+var_20], 40000000h
0x1800675e2  xor     edx, edx
0x1800675e4  mov     [rsp+50h+var_28], rdi
0x1800675e9  xor     ecx, ecx
0x1800675eb  mov     qword ptr [rsp+50h+var_30], rdi
0x1800675f0  call    DsrGetDcNameEx2
0x1800675f5  mov     ecx, eax
0x1800675f7  call    NetpApiStatusToNtStatus
0x1800675fc  mov     ebx, eax
0x1800675fe  test    eax, eax
0x180067600  jns     short loc_180067616
0x180067602  lea     rdx, aNetpqueryservi_2; "NetpQueryServiceAccount: Failed to find"...
0x180067609  mov     ecx, r13d; unsigned int
0x18006760c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067611  jmp     loc_1800676CE
0x180067616  mov     rdx, [rbp+arg_18]
0x18006761a  lea     r8, [rbp+ld]; struct ldap **
0x18006761e  mov     [rsp+50h+var_30], 1; int
0x180067626  mov     r14, [rdx]
0x180067629  mov     rdx, [rdx+28h]; unsigned __int16 *
0x18006762d  mov     rcx, r14; HostName
0x180067630  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180067635  mov     ebx, eax
0x180067637  test    eax, eax
0x180067639  jns     short loc_180067644
0x18006763b  lea     rdx, aNetpqueryservi_0; "NetpQueryServiceAccount: Failed to LDAP"...
0x180067642  jmp     short loc_180067609
0x180067644  xor     ecx, ecx; BindingHandle
0x180067646  call    cs:__imp_RpcImpersonateClient
0x18006764d  nop     dword ptr [rax+rax+00h]
0x180067652  mov     ecx, eax; Status
0x180067654  call    cs:__imp_I_RpcMapWin32Status
0x18006765b  nop     dword ptr [rax+rax+00h]
0x180067660  mov     ebx, eax
0x180067662  test    eax, eax
0x180067664  js      short loc_1800676CE
0x180067666  mov     rdx, [rbp+arg_18]
0x18006766a  lea     r8, [rbp+arg_10]; struct ldap **
0x18006766e  mov     rcx, r14; HostName
0x180067671  mov     [rsp+50h+var_30], 1; int
0x180067679  mov     rdx, [rdx+28h]; unsigned __int16 *
0x18006767d  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180067682  mov     ebx, eax
0x180067684  call    cs:__imp_RpcRevertToSelf
0x18006768b  nop     dword ptr [rax+rax+00h]
0x180067690  test    ebx, ebx
0x180067692  jns     short loc_1800676A9
0x180067694  lea     rdx, aNetpqueryservi_5; "NetpQueryServiceAccount: Failed to LDAP"...
0x18006769b  mov     ecx, r13d; unsigned int
0x18006769e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800676a3  mov     rdi, [rbp+arg_10]
0x1800676a7  jmp     short loc_1800676CE
0x1800676a9  mov     r9, [rsi]; struct _MSA_INFO_0 *
0x1800676ac  mov     rdi, [rbp+arg_10]
0x1800676b0  test    r9, r9
0x1800676b3  jnz     short loc_1800676BC
0x1800676b5  mov     ebx, 0C000000Dh
0x1800676ba  jmp     short loc_1800676CE
0x1800676bc  mov     r8, [rbp+ld]; LDAP *
0x1800676c0  mov     rdx, rdi; ld
0x1800676c3  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x1800676c7  call    ?NetpQueryServiceAccount0@@YAJPEBGPEAUldap@@1PEAU_MSA_INFO_0@@@Z; NetpQueryServiceAccount0(ushort const *,ldap *,ldap *,_MSA_INFO_0 *)
0x1800676cc  mov     ebx, eax
0x1800676ce  mov     rcx, [rbp+Buffer]; Buffer
0x1800676d2  test    rcx, rcx
0x1800676d5  jz      short loc_1800676E3
0x1800676d7  call    cs:__imp_NetApiBufferFree
0x1800676de  nop     dword ptr [rax+rax+00h]
0x1800676e3  mov     rcx, [rbp+arg_18]; Buffer
0x1800676e7  test    rcx, rcx
0x1800676ea  jz      short loc_1800676F8
0x1800676ec  call    cs:__imp_NetApiBufferFree
0x1800676f3  nop     dword ptr [rax+rax+00h]
0x1800676f8  mov     rcx, [rbp+ld]; ld
0x1800676fc  test    rcx, rcx
0x1800676ff  jz      short loc_18006770D
0x180067701  call    cs:__imp_ldap_unbind
0x180067708  nop     dword ptr [rax+rax+00h]
0x18006770d  test    rdi, rdi
0x180067710  jz      short loc_180067721
0x180067712  mov     rcx, rdi; ld
0x180067715  call    cs:__imp_ldap_unbind
0x18006771c  nop     dword ptr [rax+rax+00h]
0x180067721  mov     r9d, ebx
0x180067724  lea     rdx, aExitingNetpque_2; "Exiting NetpQueryServiceAccount for acc"...
0x18006772b  mov     r8, r15
0x18006772e  mov     ecx, r13d; unsigned int
0x180067731  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067736  mov     eax, ebx
0x180067738  jmp     short loc_18006773F
0x18006773a  mov     eax, 0C000000Dh
0x18006773f  lea     r11, [rsp+50h+var_s0]
0x180067744  mov     rbx, [r11+30h]
0x180067748  mov     rsi, [r11+38h]
0x18006774c  mov     rsp, r11
0x18006774f  pop     r15
0x180067751  pop     r14
0x180067753  pop     r13
0x180067755  pop     rdi
0x180067756  pop     rbp
0x180067757  retn
```
