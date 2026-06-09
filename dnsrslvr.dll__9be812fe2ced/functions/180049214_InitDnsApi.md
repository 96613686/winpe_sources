# InitDnsApi

- ea: `0x180049214`
- end: `0x18004936a`
- name: `InitDnsApi`
- size: `342`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800495c0`

## callees

- `0x180046ec0`
- `0x180049214`

## import_xrefs

- `DNSAPI!Query_Cancel` at `0x1800492ec`
- `DNSAPI!AddRefQueryBlobEx` at `0x1800492f7`
- `DNSAPI!DeRefQueryBlobEx` at `0x180049302`
- `DNSAPI!Dns_CacheServiceInitEx` at `0x18004934f`
- `DNSAPI!Dns_CacheServiceInitEx` at `0x18004934f`

## pseudocode

```c
__int64 InitDnsApi()
{
  __int64 v0; // r8
  _QWORD *v1; // rdx
  __int64 v2; // rcx
  _QWORD v4[2]; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v5[15]; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int128 v6; // [rsp+A8h] [rbp+2Fh]
  __int64 (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+B8h] [rbp+3Fh]

  v7 = 0;
  v5[0] = DnsGetDohWellKnownServer;
  v5[1] = DnsGetDotWellKnownServer;
  v5[2] = DnsGetInterfaceProperties;
  v5[3] = Internal_R_DnsGetMulticastData;
  v5[4] = Internal_R_DnsStartMulticastQuery;
  v5[5] = Internal_R_DnsStopMulticastQuery;
  v5[6] = AddRefServerMapView;
  v5[7] = DeRefServerMapView;
  v5[8] = GetCachedServerProperties;
  v5[9] = ZtGetTrustedServers;
  v5[10] = DnsZtAddNetinfoServers;
  v5[11] = ZtGetConfigPrivate;
  v5[12] = &ZtVerifyServerCert;
  v5[13] = ZtGetClientCertContext;
  v5[14] = ResolverQueryInProc;
  v6 = 0;
  if ( g_fVelocityDisableInternalExports )
  {
    v6 = __PAIR128__((unsigned __int64)AddRefQueryBlobEx, Query_Cancel);
    v7 = DeRefQueryBlobEx;
  }
  if ( g_fVelocityZtdnsProbing || g_fVelocityRpcUpdate )
  {
    v0 = 16;
    v4[0] = v5;
    v1 = v4;
    v4[1] = &g_DnsApiData;
    v2 = 2;
  }
  else
  {
    v0 = 144;
    v1 = v5;
    v2 = 1;
  }
  return Dns_CacheServiceInitEx(v2, v1, v0);
}

```

## disassembly

```asm
0x180049214  push    rbp
0x180049216  lea     rbp, [rsp-57h]
0x18004921b  sub     rsp, 0D0h
0x180049222  mov     rax, cs:__security_cookie
0x180049229  xor     rax, rsp
0x18004922c  mov     [rbp+57h+var_10], rax
0x180049230  xor     eax, eax
0x180049232  xor     ecx, ecx
0x180049234  cmp     cs:g_fVelocityDisableInternalExports, ecx
0x18004923a  xorps   xmm0, xmm0
0x18004923d  mov     [rbp+57h+var_18], rax
0x180049241  lea     rax, DnsGetDohWellKnownServer
0x180049248  mov     [rbp+57h+var_A0], rax
0x18004924c  lea     rax, DnsGetDotWellKnownServer
0x180049253  mov     [rbp+57h+var_98], rax
0x180049257  lea     rax, DnsGetInterfaceProperties
0x18004925e  mov     [rbp+57h+var_90], rax
0x180049262  lea     rax, Internal_R_DnsGetMulticastData
0x180049269  mov     [rbp+57h+var_88], rax
0x18004926d  lea     rax, Internal_R_DnsStartMulticastQuery
0x180049274  mov     [rbp+57h+var_80], rax
0x180049278  lea     rax, Internal_R_DnsStopMulticastQuery
0x18004927f  mov     [rbp+57h+var_78], rax
0x180049283  lea     rax, AddRefServerMapView
0x18004928a  mov     [rbp+57h+var_70], rax
0x18004928e  lea     rax, DeRefServerMapView
0x180049295  mov     [rbp+57h+var_68], rax
0x180049299  lea     rax, GetCachedServerProperties
0x1800492a0  mov     [rbp+57h+var_60], rax
0x1800492a4  lea     rax, ZtGetTrustedServers
0x1800492ab  mov     [rbp+57h+var_58], rax
0x1800492af  lea     rax, DnsZtAddNetinfoServers
0x1800492b6  mov     [rbp+57h+var_50], rax
0x1800492ba  lea     rax, ZtGetConfigPrivate
0x1800492c1  mov     [rbp+57h+var_48], rax
0x1800492c5  lea     rax, ZtVerifyServerCert
0x1800492cc  mov     [rbp+57h+var_40], rax
0x1800492d0  lea     rax, ZtGetClientCertContext
0x1800492d7  mov     [rbp+57h+var_38], rax
0x1800492db  lea     rax, ResolverQueryInProc
0x1800492e2  mov     [rbp+57h+var_30], rax
0x1800492e6  movups  [rbp+57h+var_28], xmm0
0x1800492ea  jz      short loc_18004930D
0x1800492ec  mov     rax, cs:__imp_Query_Cancel
0x1800492f3  mov     qword ptr [rbp+57h+var_28], rax
0x1800492f7  mov     rax, cs:__imp_AddRefQueryBlobEx
0x1800492fe  mov     qword ptr [rbp+57h+var_28+8], rax
0x180049302  mov     rax, cs:__imp_DeRefQueryBlobEx
0x180049309  mov     [rbp+57h+var_18], rax
0x18004930d  cmp     cs:g_fVelocityZtdnsProbing, ecx
0x180049313  jnz     short loc_18004932E
0x180049315  cmp     cs:g_fVelocityRpcUpdate, ecx
0x18004931b  jnz     short loc_18004932E
0x18004931d  mov     r8d, 90h
0x180049323  lea     rdx, [rbp+57h+var_A0]
0x180049327  mov     ecx, 1
0x18004932c  jmp     short loc_18004934F
0x18004932e  lea     rax, [rbp+57h+var_A0]
0x180049332  mov     r8d, 10h
0x180049338  mov     [rbp+57h+var_B0], rax
0x18004933c  lea     rdx, [rbp+57h+var_B0]
0x180049340  lea     rax, g_DnsApiData
0x180049347  mov     [rbp+57h+var_A8], rax
0x18004934b  lea     ecx, [r8-0Eh]
0x18004934f  call    cs:__imp_Dns_CacheServiceInitEx
0x180049355  mov     rcx, [rbp+57h+var_10]
0x180049359  xor     rcx, rsp; StackCookie
0x18004935c  call    __security_check_cookie
0x180049361  add     rsp, 0D0h
0x180049368  pop     rbp
0x180049369  retn
```
