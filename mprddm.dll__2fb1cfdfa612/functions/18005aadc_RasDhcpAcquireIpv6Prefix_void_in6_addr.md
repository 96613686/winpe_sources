# RasDhcpAcquireIpv6Prefix(void *,in6_addr *)

- ea: `0x18005aadc`
- end: `0x18005ac97`
- name: `?RasDhcpAcquireIpv6Prefix@@YAKPEAXPEAUin6_addr@@@Z`
- size: `443`
- prototype: `unsigned int(void *, struct in6_addr *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180052670`
- `0x180052a44`

## callees

- `0x18005aadc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18005ac6a`
- `KERNEL32!LeaveCriticalSection` at `0x18005ac6a`
- `KERNEL32!EnterCriticalSection` at `0x18005ab51`
- `KERNEL32!EnterCriticalSection` at `0x18005ab51`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005abc8`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005abc8`
- `ntdll!RtlUpdateTimer` at `0x18005ac5b`
- `ntdll!RtlUpdateTimer` at `0x18005ac5b`

## pseudocode

```c
__int64 __fastcall RasDhcpAcquireIpv6Prefix(void *a1, struct in6_addr *a2)
{
  struct _Ipv6Prefix_Info *v4; // rbx
  unsigned int v5; // ebx
  CHAR S[128]; // [rsp+20h] [rbp-898h] BYREF
  int v8; // [rsp+A0h] [rbp-818h] BYREF
  _BYTE v9[2044]; // [rsp+A4h] [rbp-814h] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"RasDhcpAcquireIpv6Prefix");
  EnterCriticalSection(&csRasDhcpv6);
  v4 = RasDhcpIpv6FreePool;
  if ( RasDhcpIpv6FreePool )
  {
    RasDhcpIpv6FreePool = *(struct _Ipv6Prefix_Info **)RasDhcpIpv6FreePool;
    *(_QWORD *)v4 = RasDhcpIpv6AllocPool;
    RasDhcpIpv6AllocPool = v4;
    *(_QWORD *)a2->u.Byte = **(_QWORD **)(*((_QWORD *)v4 + 4) + 8LL);
    RtlIpv6AddressToStringA(a2, S);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"Acquired 0x%hs", S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v8);
    }
    *((_DWORD *)v4 + 20) |= 2u;
    *((_QWORD *)v4 + 11) = a1;
    if ( !RasDhcpIpv6FreePool && !RasDhcpNumIpv6ReqPrefix )
    {
      RasDhcpNumIpv6ReqPrefix = dword_1800C98D8;
      RtlUpdateTimer(RasDhcpIpv6TimerQueueHandle, RasDhcpIpv6TimerHandle, 0, 0x7530u);
    }
    v5 = 0;
  }
  else
  {
    v5 = 1168;
    if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        L"Out of addresses");
  }
  LeaveCriticalSection(&csRasDhcpv6);
  return v5;
}

```

## disassembly

```asm
0x18005aadc  mov     [rsp+arg_0], rbx
0x18005aae1  mov     [rsp+arg_10], rsi
0x18005aae6  push    rdi
0x18005aae7  sub     rsp, 8B0h
0x18005aaee  mov     rax, cs:__security_cookie
0x18005aaf5  xor     rax, rsp
0x18005aaf8  mov     [rsp+8B8h+var_18], rax
0x18005ab00  mov     rsi, rdx
0x18005ab03  mov     rdi, rcx
0x18005ab06  xor     eax, eax
0x18005ab08  lea     rcx, [rsp+8B8h+var_814]; void *
0x18005ab10  xor     edx, edx; Val
0x18005ab12  mov     [rsp+8B8h+var_818], eax
0x18005ab19  mov     r8d, 7FCh; Size
0x18005ab1f  call    memset_0
0x18005ab24  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005ab2b  test    rdx, rdx
0x18005ab2e  jz      short loc_18005AB4A
0x18005ab30  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ab37  lea     r8, aRasdhcpacquire_0; "RasDhcpAcquireIpv6Prefix"
0x18005ab3e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ab45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab4a  lea     rcx, ?csRasDhcpv6@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005ab51  call    cs:__imp_EnterCriticalSection
0x18005ab57  mov     rbx, cs:?RasDhcpIpv6FreePool@@3PEAU_Ipv6Prefix_Info@@EA; _Ipv6Prefix_Info * RasDhcpIpv6FreePool
0x18005ab5e  test    rbx, rbx
0x18005ab61  jnz     short loc_18005AB97
0x18005ab63  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005ab6a  mov     ebx, 490h
0x18005ab6f  test    rdx, rdx
0x18005ab72  jz      loc_18005AC63
0x18005ab78  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ab7f  lea     r8, aOutOfAddresses; "Out of addresses"
0x18005ab86  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ab8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab92  jmp     loc_18005AC63
0x18005ab97  mov     rax, [rbx]
0x18005ab9a  mov     rcx, rsi; Addr
0x18005ab9d  mov     cs:?RasDhcpIpv6FreePool@@3PEAU_Ipv6Prefix_Info@@EA, rax; _Ipv6Prefix_Info * RasDhcpIpv6FreePool
0x18005aba4  mov     rax, cs:?RasDhcpIpv6AllocPool@@3PEAU_Ipv6Prefix_Info@@EA; _Ipv6Prefix_Info * RasDhcpIpv6AllocPool
0x18005abab  mov     [rbx], rax
0x18005abae  mov     cs:?RasDhcpIpv6AllocPool@@3PEAU_Ipv6Prefix_Info@@EA, rbx; _Ipv6Prefix_Info * RasDhcpIpv6AllocPool
0x18005abb5  mov     rax, [rbx+20h]
0x18005abb9  mov     rdx, [rax+8]
0x18005abbd  mov     rax, [rdx]
0x18005abc0  lea     rdx, [rsp+8B8h+S]; S
0x18005abc5  mov     [rsi], rax
0x18005abc8  call    cs:__imp_RtlIpv6AddressToStringA
0x18005abce  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005abd6  jz      short loc_18005AC1D
0x18005abd8  xor     eax, eax
0x18005abda  lea     r8, [rsp+8B8h+S]
0x18005abdf  lea     rdx, aAcquired0xHs; "Acquired 0x%hs"
0x18005abe6  mov     word ptr [rsp+8B8h+var_818], ax
0x18005abee  lea     rcx, [rsp+8B8h+var_818]
0x18005abf6  call    FormatRRASErrorString
0x18005abfb  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005ac02  lea     r8, [rsp+8B8h+var_818]
0x18005ac0a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ac11  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ac18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac1d  or      dword ptr [rbx+50h], 2
0x18005ac21  mov     [rbx+58h], rdi
0x18005ac25  cmp     cs:?RasDhcpIpv6FreePool@@3PEAU_Ipv6Prefix_Info@@EA, 0; _Ipv6Prefix_Info * RasDhcpIpv6FreePool
0x18005ac2d  jnz     short loc_18005AC61
0x18005ac2f  cmp     cs:?RasDhcpNumIpv6ReqPrefix@@3KA, 0; ulong RasDhcpNumIpv6ReqPrefix
0x18005ac36  jnz     short loc_18005AC61
0x18005ac38  mov     eax, cs:dword_1800C98D8
0x18005ac3e  mov     r9d, 7530h; Period
0x18005ac44  mov     rdx, cs:?RasDhcpIpv6TimerHandle@@3PEAXEA; Timer
0x18005ac4b  xor     r8d, r8d; DueTime
0x18005ac4e  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18005ac55  mov     cs:?RasDhcpNumIpv6ReqPrefix@@3KA, eax; ulong RasDhcpNumIpv6ReqPrefix
0x18005ac5b  call    cs:__imp_RtlUpdateTimer
0x18005ac61  xor     ebx, ebx
0x18005ac63  lea     rcx, ?csRasDhcpv6@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005ac6a  call    cs:__imp_LeaveCriticalSection
0x18005ac70  mov     eax, ebx
0x18005ac72  mov     rcx, [rsp+8B8h+var_18]
0x18005ac7a  xor     rcx, rsp; StackCookie
0x18005ac7d  call    __security_check_cookie
0x18005ac82  lea     r11, [rsp+8B8h+var_8]
0x18005ac8a  mov     rbx, [r11+10h]
0x18005ac8e  mov     rsi, [r11+20h]
0x18005ac92  mov     rsp, r11
0x18005ac95  pop     rdi
0x18005ac96  retn
```
