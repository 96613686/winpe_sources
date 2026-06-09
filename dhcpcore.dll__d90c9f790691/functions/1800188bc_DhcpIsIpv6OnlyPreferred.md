# DhcpIsIpv6OnlyPreferred

- ea: `0x1800188bc`
- end: `0x180018a19`
- name: `DhcpIsIpv6OnlyPreferred`
- size: `349`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800327f0`
- `0x180032f50`
- `0x18003ba84`

## callees

- `0x1800188bc`
- `0x18001cef0`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800189d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800189d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018927`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018927`
- `NSI!NsiGetParameter` at `0x180018982`
- `NSI!NsiGetParameter` at `0x180018982`
- `IPXLATCFG!IPxlatPolicyMgrInitialize` at `0x180018932`
- `IPXLATCFG!IPxlatPolicyMgrInitialize` at `0x180018932`
- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x180018941`
- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x180018941`
- `IPXLATCFG!IPxlatPolicyMgrUninitialize` at `0x1800189c0`
- `IPXLATCFG!IPxlatPolicyMgrUninitialize` at `0x1800189c0`

## pseudocode

```c
__int64 DhcpIsIpv6OnlyPreferred()
{
  unsigned int v0; // ebx
  int v1; // edi
  bool v2; // zf
  unsigned int Parameter; // eax
  _BYTE v5[8]; // [rsp+50h] [rbp-38h] BYREF
  __int128 v6; // [rsp+58h] [rbp-30h] BYREF
  int v7; // [rsp+68h] [rbp-20h]

  v5[0] = 0;
  v0 = 0;
  v7 = 0;
  v1 = 0;
  v6 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 105, WPP_b85ebe6c12863f19dba418452b756303_Traceguids);
  if ( DhcpGlobalIpv6OnlyPreferredEnabled )
  {
    if ( g_fVelocityDhcpIPxlatPolicyMgr )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v1 = 1;
      if ( !(unsigned int)IPxlatPolicyMgrInitialize() && !(unsigned int)IPxlatPolicyMgrReadConfiguration(&v6) )
      {
        v2 = (_DWORD)v6 == 0;
LABEL_12:
        LOBYTE(v0) = !v2;
      }
    }
    else
    {
      Parameter = NsiGetParameter(1, &NPI_MS_IPV4_MODULEID, 6, 0, 0, 1, v5, 1, 208);
      if ( !Parameter )
      {
        v2 = v5[0] == 0;
        goto LABEL_12;
      }
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 106, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, Parameter);
    }
  }
  if ( g_fVelocityDhcpIPxlatPolicyMgr )
  {
    IPxlatPolicyMgrUninitialize();
    if ( v1 )
      ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 107, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x1800188bc  mov     [rsp+arg_0], rbx
0x1800188c1  push    rdi
0x1800188c2  sub     rsp, 80h
0x1800188c9  mov     rax, cs:__security_cookie
0x1800188d0  xor     rax, rsp
0x1800188d3  mov     [rsp+88h+var_18], rax
0x1800188d8  xor     eax, eax
0x1800188da  mov     [rsp+88h+var_38], 0
0x1800188df  xor     ebx, ebx
0x1800188e1  mov     [rsp+88h+var_20], eax
0x1800188e5  xorps   xmm0, xmm0
0x1800188e8  xor     edi, edi
0x1800188ea  movups  [rsp+88h+var_30], xmm0
0x1800188ef  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800188f6  jz      short loc_18001890C
0x1800188f8  lea     edx, [rbx+69h]
0x1800188fb  mov     ecx, 404h
0x180018900  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180018907  call    WPP_SF_
0x18001890c  cmp     cs:DhcpGlobalIpv6OnlyPreferredEnabled, ebx
0x180018912  jz      loc_1800189B7
0x180018918  cmp     cs:g_fVelocityDhcpIPxlatPolicyMgr, ebx
0x18001891e  jz      short loc_180018951
0x180018920  lea     rcx, SRWLock; SRWLock
0x180018927  call    cs:__imp_AcquireSRWLockExclusive
0x18001892d  mov     edi, 1
0x180018932  call    cs:__imp_IPxlatPolicyMgrInitialize
0x180018938  test    eax, eax
0x18001893a  jnz     short loc_1800189B7
0x18001893c  lea     rcx, [rsp+88h+var_30]
0x180018941  call    cs:__imp_IPxlatPolicyMgrReadConfiguration
0x180018947  test    eax, eax
0x180018949  jnz     short loc_1800189B7
0x18001894b  cmp     dword ptr [rsp+88h+var_30], ebx
0x18001894f  jmp     short loc_1800189B4
0x180018951  mov     ecx, 1
0x180018956  mov     [rsp+88h+var_48], 0D0h
0x18001895e  mov     [rsp+88h+var_50], ecx
0x180018962  lea     rax, [rsp+88h+var_38]
0x180018967  mov     [rsp+88h+var_58], rax
0x18001896c  lea     rdx, NPI_MS_IPV4_MODULEID
0x180018973  mov     [rsp+88h+var_60], ecx
0x180018977  xor     r9d, r9d
0x18001897a  lea     r8d, [rcx+5]
0x18001897e  mov     [rsp+88h+var_68], ebx
0x180018982  call    cs:__imp_NsiGetParameter
0x180018988  test    eax, eax
0x18001898a  jz      short loc_1800189B0
0x18001898c  test    byte ptr cs:xmmword_1800616A0, 2
0x180018993  jz      short loc_1800189B7
0x180018995  mov     edx, 6Ah ; 'j'
0x18001899a  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x1800189a1  mov     ecx, 401h
0x1800189a6  mov     r9d, eax
0x1800189a9  call    WPP_SF_D
0x1800189ae  jmp     short loc_1800189B7
0x1800189b0  cmp     [rsp+88h+var_38], bl
0x1800189b4  setnz   bl
0x1800189b7  cmp     cs:g_fVelocityDhcpIPxlatPolicyMgr, 0
0x1800189be  jz      short loc_1800189D7
0x1800189c0  call    cs:__imp_IPxlatPolicyMgrUninitialize
0x1800189c6  test    edi, edi
0x1800189c8  jz      short loc_1800189D7
0x1800189ca  lea     rcx, SRWLock; SRWLock
0x1800189d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800189d7  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800189de  jz      short loc_1800189F9
0x1800189e0  mov     edx, 6Bh ; 'k'
0x1800189e5  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x1800189ec  mov     ecx, 404h
0x1800189f1  mov     r9d, ebx
0x1800189f4  call    WPP_SF_d
0x1800189f9  mov     eax, ebx
0x1800189fb  mov     rcx, [rsp+88h+var_18]
0x180018a00  xor     rcx, rsp; StackCookie
0x180018a03  call    __security_check_cookie
0x180018a08  mov     rbx, [rsp+88h+arg_0]
0x180018a10  add     rsp, 80h
0x180018a17  pop     rdi
0x180018a18  retn
```
