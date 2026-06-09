# NetpQueryServiceAccount(ushort const *,_MSA_INFO_LEVEL,_MSA_INFO_BUFFER *)

- ea: `0x180062d04`
- end: `0x180062eda`
- name: `?NetpQueryServiceAccount@@YAJPEBGW4_MSA_INFO_LEVEL@@PEAT_MSA_INFO_BUFFER@@@Z`
- size: `470`
- prototype: `int __fastcall(const unsigned __int16 *, enum _MSA_INFO_LEVEL, struct _MSA_INFO_0 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x18002a768`
- `0x18002a838`

## callees

- `0x180004420`
- `0x180007278`
- `0x18000d100`
- `0x180062604`
- `0x1800629d0`
- `0x180062bb8`
- `0x180062d04`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180062df2`
- `RPCRT4!RpcImpersonateClient` at `0x180062df2`
- `RPCRT4!RpcRevertToSelf` at `0x180062e24`
- `RPCRT4!RpcRevertToSelf` at `0x180062e24`
- `RPCRT4!I_RpcMapWin32Status` at `0x180062dfa`
- `RPCRT4!I_RpcMapWin32Status` at `0x180062dfa`
- `netutils!NetApiBufferFree` at `0x180062e71`
- `netutils!NetApiBufferFree` at `0x180062e80`
- `netutils!NetApiBufferFree` at `0x180062e71`
- `netutils!NetApiBufferFree` at `0x180062e80`
- `WLDAP32!__imp_ldap_unbind` at `0x180062e8f`
- `WLDAP32!__imp_ldap_unbind` at `0x180062e9d`
- `WLDAP32!__imp_ldap_unbind` at `0x180062e8f`
- `WLDAP32!__imp_ldap_unbind` at `0x180062e9d`

## string_xrefs

- `0x180062d54`: `Entering NetpQueryServiceAccount for account %s, Level %u\n`
- `0x180062dae`: `NetpQueryServiceAccount: Failed to find usable DC\n`
- `0x180062de7`: `NetpQueryServiceAccount: Failed to LDAP bind as SYSTEM\n`
- `0x180062e2e`: `NetpQueryServiceAccount: Failed to LDAP bind as caller\n`
- `0x180062ea6`: `Exiting NetpQueryServiceAccount for account %s, Status 0x%08X\n`

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
    DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0, 0, 0, 0x40000000u, (struct _DOMAIN_CONTROLLER_INFOW **)&v16);
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
0x180062d04  mov     [rsp-28h+arg_0], rbx
0x180062d09  mov     [rsp-28h+arg_8], rsi
0x180062d0e  push    rbp
0x180062d0f  push    rdi
0x180062d10  push    r13
0x180062d12  push    r14
0x180062d14  push    r15
0x180062d16  mov     rbp, rsp
0x180062d19  sub     rsp, 50h
0x180062d1d  xor     edi, edi
0x180062d1f  mov     [rbp+Buffer], 0
0x180062d27  mov     [rbp+arg_18], 0
0x180062d2f  mov     rsi, r8
0x180062d32  mov     [rbp+ld], 0
0x180062d3a  mov     r15, rcx
0x180062d3d  mov     [rbp+arg_10], rdi
0x180062d41  test    r8, r8
0x180062d44  jz      loc_180062EBC
0x180062d4a  mov     r8, rcx
0x180062d4d  lea     r13d, [rdi+40h]
0x180062d51  mov     ecx, r13d; unsigned int
0x180062d54  lea     rdx, aEnteringNetpqu; "Entering NetpQueryServiceAccount for ac"...
0x180062d5b  xor     r9d, r9d
0x180062d5e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062d63  lea     rdx, [rbp+Buffer]; unsigned __int16 **
0x180062d67  mov     rcx, r15; unsigned __int16 *
0x180062d6a  call    ?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z; NetpProcessAccountName(ushort const *,ushort * *)
0x180062d6f  test    eax, eax
0x180062d71  js      loc_180062EC1
0x180062d77  lea     rax, [rbp+arg_18]
0x180062d7b  xor     r9d, r9d
0x180062d7e  mov     [rsp+50h+var_18], rax
0x180062d83  xor     r8d, r8d
0x180062d86  mov     [rsp+50h+var_20], 40000000h
0x180062d8e  xor     edx, edx
0x180062d90  mov     [rsp+50h+var_28], rdi
0x180062d95  xor     ecx, ecx
0x180062d97  mov     qword ptr [rsp+50h+var_30], rdi
0x180062d9c  call    DsrGetDcNameEx2
0x180062da1  mov     ecx, eax
0x180062da3  call    NetpApiStatusToNtStatus
0x180062da8  mov     ebx, eax
0x180062daa  test    eax, eax
0x180062dac  jns     short loc_180062DC2
0x180062dae  lea     rdx, aNetpqueryservi_2; "NetpQueryServiceAccount: Failed to find"...
0x180062db5  mov     ecx, r13d; unsigned int
0x180062db8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062dbd  jmp     loc_180062E68
0x180062dc2  mov     rdx, [rbp+arg_18]
0x180062dc6  lea     r8, [rbp+ld]; struct ldap **
0x180062dca  mov     [rsp+50h+var_30], 1; int
0x180062dd2  mov     r14, [rdx]
0x180062dd5  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180062dd9  mov     rcx, r14; HostName
0x180062ddc  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180062de1  mov     ebx, eax
0x180062de3  test    eax, eax
0x180062de5  jns     short loc_180062DF0
0x180062de7  lea     rdx, aNetpqueryservi_0; "NetpQueryServiceAccount: Failed to LDAP"...
0x180062dee  jmp     short loc_180062DB5
0x180062df0  xor     ecx, ecx; BindingHandle
0x180062df2  call    cs:__imp_RpcImpersonateClient
0x180062df8  mov     ecx, eax; Status
0x180062dfa  call    cs:__imp_I_RpcMapWin32Status
0x180062e00  mov     ebx, eax
0x180062e02  test    eax, eax
0x180062e04  js      short loc_180062E68
0x180062e06  mov     rdx, [rbp+arg_18]
0x180062e0a  lea     r8, [rbp+arg_10]; struct ldap **
0x180062e0e  mov     rcx, r14; HostName
0x180062e11  mov     [rsp+50h+var_30], 1; int
0x180062e19  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180062e1d  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180062e22  mov     ebx, eax
0x180062e24  call    cs:__imp_RpcRevertToSelf
0x180062e2a  test    ebx, ebx
0x180062e2c  jns     short loc_180062E43
0x180062e2e  lea     rdx, aNetpqueryservi_5; "NetpQueryServiceAccount: Failed to LDAP"...
0x180062e35  mov     ecx, r13d; unsigned int
0x180062e38  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062e3d  mov     rdi, [rbp+arg_10]
0x180062e41  jmp     short loc_180062E68
0x180062e43  mov     r9, [rsi]; struct _MSA_INFO_0 *
0x180062e46  mov     rdi, [rbp+arg_10]
0x180062e4a  test    r9, r9
0x180062e4d  jnz     short loc_180062E56
0x180062e4f  mov     ebx, 0C000000Dh
0x180062e54  jmp     short loc_180062E68
0x180062e56  mov     r8, [rbp+ld]; LDAP *
0x180062e5a  mov     rdx, rdi; ld
0x180062e5d  mov     rcx, [rbp+Buffer]; unsigned __int16 *
0x180062e61  call    ?NetpQueryServiceAccount0@@YAJPEBGPEAUldap@@1PEAU_MSA_INFO_0@@@Z; NetpQueryServiceAccount0(ushort const *,ldap *,ldap *,_MSA_INFO_0 *)
0x180062e66  mov     ebx, eax
0x180062e68  mov     rcx, [rbp+Buffer]; Buffer
0x180062e6c  test    rcx, rcx
0x180062e6f  jz      short loc_180062E77
0x180062e71  call    cs:__imp_NetApiBufferFree
0x180062e77  mov     rcx, [rbp+arg_18]; Buffer
0x180062e7b  test    rcx, rcx
0x180062e7e  jz      short loc_180062E86
0x180062e80  call    cs:__imp_NetApiBufferFree
0x180062e86  mov     rcx, [rbp+ld]; ld
0x180062e8a  test    rcx, rcx
0x180062e8d  jz      short loc_180062E95
0x180062e8f  call    cs:__imp_ldap_unbind
0x180062e95  test    rdi, rdi
0x180062e98  jz      short loc_180062EA3
0x180062e9a  mov     rcx, rdi; ld
0x180062e9d  call    cs:__imp_ldap_unbind
0x180062ea3  mov     r9d, ebx
0x180062ea6  lea     rdx, aExitingNetpque_2; "Exiting NetpQueryServiceAccount for acc"...
0x180062ead  mov     r8, r15
0x180062eb0  mov     ecx, r13d; unsigned int
0x180062eb3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062eb8  mov     eax, ebx
0x180062eba  jmp     short loc_180062EC1
0x180062ebc  mov     eax, 0C000000Dh
0x180062ec1  lea     r11, [rsp+50h+var_s0]
0x180062ec6  mov     rbx, [r11+30h]
0x180062eca  mov     rsi, [r11+38h]
0x180062ece  mov     rsp, r11
0x180062ed1  pop     r15
0x180062ed3  pop     r14
0x180062ed5  pop     r13
0x180062ed7  pop     rdi
0x180062ed8  pop     rbp
0x180062ed9  retn
```
