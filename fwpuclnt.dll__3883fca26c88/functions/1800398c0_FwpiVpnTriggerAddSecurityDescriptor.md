# FwpiVpnTriggerAddSecurityDescriptor

- ea: `0x1800398c0`
- end: `0x1800399f0`
- name: `FwpiVpnTriggerAddSecurityDescriptor`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800034e0`
- `0x1800040a0`
- `0x18000438c`
- `0x180004540`
- `0x180007e38`
- `0x180012bd0`
- `0x1800398c0`

## import_xrefs

- `ntdll!RtlValidSecurityDescriptor` at `0x18003991b`
- `ntdll!RtlValidSecurityDescriptor` at `0x18003991b`
- `RPCRT4!NdrClientCall3` at `0x180039995`
- `RPCRT4!NdrClientCall3` at `0x180039995`

## string_xrefs

- `0x180039931`: `FwpiVpnSecurityDescriptorValidate`
- `0x180039945`: `FwpiVpnSecurityDescriptorValidate`
- `0x1800398ff`: `FwpiVpnTriggerAddSecurityDescriptor`
- `0x1800399a8`: `FwppProxyVpnTriggerAddSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall FwpiVpnTriggerAddSecurityDescriptor(_QWORD *a1, void *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  unsigned int Pointer; // eax
  CLIENT_CALL_RETURN v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+38h] [rbp-30h] BYREF
  int v12; // [rsp+40h] [rbp-28h]

  v2 = 0;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  if ( a1 )
  {
    if ( a2 && RtlValidSecurityDescriptor(a2)
      || (v6 = WfpReportSysErrorAsWinError(a1, "FwpiVpnSecurityDescriptorValidate", 2150760501LL), (v5 = v6) == 0) )
    {
      v5 = BfeSecurityDescriptorEncode(a2, (__int64)&v11, &v10);
      if ( !v5 )
      {
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBFu, 0, *a1, a1[1], &v11).Pointer;
        if ( Pointer )
          v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))WfpReportSysErrorAsWinError)(
                 (CLIENT_CALL_RETURN)v8.Simple,
                 "FwppProxyVpnTriggerAddSecurityDescriptor",
                 Pointer);
      }
      v2 = v10;
    }
    else
    {
      WfpReportError(v6, "FwpiVpnSecurityDescriptorValidate");
    }
    if ( v2 )
      WfpMemFree(v2);
  }
  else
  {
    v5 = WfpReportSysErrorAsWinError(0, "FwpiVpnTriggerAddSecurityDescriptor", 2150760476LL);
  }
  return WfpErrorToFwpErr(v5);
}

```

## disassembly

```asm
0x1800398c0  mov     r11, rsp
0x1800398c3  mov     [r11+18h], rbx
0x1800398c7  push    rsi
0x1800398c8  push    rdi
0x1800398c9  push    r14
0x1800398cb  sub     rsp, 50h
0x1800398cf  mov     rax, cs:__security_cookie
0x1800398d6  xor     rax, rsp
0x1800398d9  mov     [rsp+68h+var_20], rax
0x1800398de  xor     eax, eax
0x1800398e0  xor     edi, edi
0x1800398e2  mov     [r11-2Ch], rax
0x1800398e6  mov     rsi, rdx
0x1800398e9  mov     [r11-30h], rax
0x1800398ed  mov     r14, rcx
0x1800398f0  mov     [r11-38h], rdi
0x1800398f4  test    rcx, rcx
0x1800398f7  jnz     short loc_180039913
0x1800398f9  mov     r8d, 8032001Ch
0x1800398ff  lea     rdx, aFwpivpntrigger_16; "FwpiVpnTriggerAddSecurityDescriptor"
0x180039906  call    WfpReportSysErrorAsWinError
0x18003990b  mov     rbx, rax
0x18003990e  jmp     loc_1800399C9
0x180039913  test    rsi, rsi
0x180039916  jz      short loc_18003992B
0x180039918  mov     rcx, rsi; SecurityDescriptor
0x18003991b  call    cs:__imp_RtlValidSecurityDescriptor
0x180039922  nop     dword ptr [rax+rax+00h]
0x180039927  test    al, al
0x180039929  jnz     short loc_180039956
0x18003992b  mov     r8d, 80320035h
0x180039931  lea     rdx, aFwpivpnsecurit; "FwpiVpnSecurityDescriptorValidate"
0x180039938  call    WfpReportSysErrorAsWinError
0x18003993d  mov     rbx, rax
0x180039940  test    rax, rax
0x180039943  jz      short loc_180039956
0x180039945  lea     rdx, aFwpivpnsecurit; "FwpiVpnSecurityDescriptorValidate"
0x18003994c  mov     rcx, rax
0x18003994f  call    WfpReportError
0x180039954  jmp     short loc_1800399BC
0x180039956  lea     r8, [rsp+68h+var_38]
0x18003995b  mov     rcx, rsi; AbsoluteSecurityDescriptor
0x18003995e  lea     rdx, [rsp+68h+var_30]
0x180039963  call    BfeSecurityDescriptorEncode
0x180039968  mov     rbx, rax
0x18003996b  test    rax, rax
0x18003996e  jnz     short loc_1800399B7
0x180039970  mov     r9, [r14]
0x180039973  lea     rax, [rsp+68h+var_30]
0x180039978  mov     [rsp+68h+var_40], rax
0x18003997d  lea     rcx, pProxyInfo; pProxyInfo
0x180039984  mov     rax, [r14+8]
0x180039988  xor     r8d, r8d; pReturnValue
0x18003998b  mov     edx, 0BFh; nProcNum
0x180039990  mov     [rsp+68h+var_48], rax
0x180039995  call    cs:__imp_NdrClientCall3
0x18003999c  nop     dword ptr [rax+rax+00h]
0x1800399a1  test    eax, eax
0x1800399a3  jz      short loc_1800399B7
0x1800399a5  mov     r8d, eax
0x1800399a8  lea     rdx, aFwppproxyvpntr_5; "FwppProxyVpnTriggerAddSecurityDescripto"...
0x1800399af  call    WfpReportSysErrorAsWinError
0x1800399b4  mov     rbx, rax
0x1800399b7  mov     rdi, [rsp+68h+var_38]
0x1800399bc  test    rdi, rdi
0x1800399bf  jz      short loc_1800399C9
0x1800399c1  mov     rcx, rdi
0x1800399c4  call    WfpMemFree
0x1800399c9  mov     rcx, rbx
0x1800399cc  call    WfpErrorToFwpErr
0x1800399d1  mov     rcx, [rsp+68h+var_20]
0x1800399d6  xor     rcx, rsp; StackCookie
0x1800399d9  call    __security_check_cookie
0x1800399de  mov     rbx, [rsp+68h+arg_10]
0x1800399e6  add     rsp, 50h
0x1800399ea  pop     r14
0x1800399ec  pop     rdi
0x1800399ed  pop     rsi
0x1800399ee  retn
```
