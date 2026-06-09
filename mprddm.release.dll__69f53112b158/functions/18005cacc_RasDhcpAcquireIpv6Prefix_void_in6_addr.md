# RasDhcpAcquireIpv6Prefix(void *,in6_addr *)

- ea: `0x18005cacc`
- end: `0x18005cca5`
- name: `?RasDhcpAcquireIpv6Prefix@@YAKPEAXPEAUin6_addr@@@Z`
- size: `473`
- prototype: `unsigned int(void *, struct in6_addr *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800540f0`
- `0x180054544`

## callees

- `0x18005cacc`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18005cc6e`
- `KERNEL32!LeaveCriticalSection` at `0x18005cc6e`
- `KERNEL32!EnterCriticalSection` at `0x18005cb4a`
- `KERNEL32!EnterCriticalSection` at `0x18005cb4a`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005cbc2`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005cbc2`
- `ntdll!RtlUpdateTimer` at `0x18005cc58`
- `ntdll!RtlUpdateTimer` at `0x18005cc58`

## pseudocode

```c
__int64 __fastcall RasDhcpAcquireIpv6Prefix(void *a1, struct in6_addr *a2)
{
  unsigned int v4; // edi
  struct _Ipv6Prefix_Info *v5; // rbx
  CHAR S[128]; // [rsp+20h] [rbp-8A8h] BYREF
  int v8; // [rsp+A0h] [rbp-828h] BYREF
  int v9; // [rsp+A4h] [rbp-824h] BYREF

  v8 = 0;
  v4 = 1168;
  memset_0(&v9, 0, 0x7FCu);
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasDhcpAcquireIpv6Prefix");
  EnterCriticalSection(&csRasDhcpv6);
  v5 = RasDhcpIpv6FreePool;
  if ( RasDhcpIpv6FreePool )
  {
    RasDhcpIpv6FreePool = *(struct _Ipv6Prefix_Info **)RasDhcpIpv6FreePool;
    *(_QWORD *)v5 = RasDhcpIpv6AllocPool;
    RasDhcpIpv6AllocPool = v5;
    *(_QWORD *)a2->u.Byte = **(_QWORD **)(*((_QWORD *)v5 + 4) + 8LL);
    RtlIpv6AddressToStringA(a2, S);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"Acquired 0x%hs", S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v8);
    }
    *((_DWORD *)v5 + 20) |= 2u;
    *((_QWORD *)v5 + 11) = a1;
    if ( !RasDhcpIpv6FreePool && !RasDhcpNumIpv6ReqPrefix )
    {
      RasDhcpNumIpv6ReqPrefix = dword_1800D08D8;
      RtlUpdateTimer(RasDhcpIpv6TimerQueueHandle, RasDhcpIpv6TimerHandle, 0, 0x7530u);
    }
    v4 = 0;
  }
  else if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
  {
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"Out of addresses");
  }
  LeaveCriticalSection(&csRasDhcpv6);
  return v4;
}

```

## disassembly

```asm
0x18005cacc  mov     r11, rsp
0x18005cacf  mov     [r11+8], rbx
0x18005cad3  mov     [r11+18h], rbp
0x18005cad7  push    rsi
0x18005cad8  push    rdi
0x18005cad9  push    r14
0x18005cadb  sub     rsp, 8B0h
0x18005cae2  mov     rax, cs:__security_cookie
0x18005cae9  xor     rax, rsp
0x18005caec  mov     [rsp+8C8h+var_28], rax
0x18005caf4  mov     rsi, rdx
0x18005caf7  mov     rbp, rcx
0x18005cafa  xor     r14d, r14d
0x18005cafd  lea     rcx, [r11-824h]; void *
0x18005cb04  xor     edx, edx; Val
0x18005cb06  mov     [r11-828h], r14d
0x18005cb0d  mov     r8d, 7FCh; Size
0x18005cb13  mov     edi, 490h
0x18005cb18  call    memset_0
0x18005cb1d  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005cb24  test    rdx, rdx
0x18005cb27  jz      short loc_18005CB43
0x18005cb29  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005cb30  lea     r8, aRasdhcpacquire_0; "RasDhcpAcquireIpv6Prefix"
0x18005cb37  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005cb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb43  lea     rcx, ?csRasDhcpv6@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005cb4a  call    cs:__imp_EnterCriticalSection
0x18005cb51  nop     dword ptr [rax+rax+00h]
0x18005cb56  mov     rbx, cs:?RasDhcpIpv6FreePool@@3PEAU_Ipv6Prefix_Info@@EA; _Ipv6Prefix_Info * RasDhcpIpv6FreePool
0x18005cb5d  test    rbx, rbx
0x18005cb60  jnz     short loc_18005CB91
0x18005cb62  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005cb69  test    rdx, rdx
0x18005cb6c  jz      loc_18005CC67
0x18005cb72  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005cb79  lea     r8, aOutOfAddresses; "Out of addresses"
0x18005cb80  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005cb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb8c  jmp     loc_18005CC67
0x18005cb91  mov     rax, [rbx]
0x18005cb94  mov     rcx, rsi; Addr
0x18005cb97  mov     cs:?RasDhcpIpv6FreePool@@3PEAU_Ipv6Prefix_Info@@EA, rax; _Ipv6Prefix_Info * RasDhcpIpv6FreePool
0x18005cb9e  mov     rax, cs:?RasDhcpIpv6AllocPool@@3PEAU_Ipv6Prefix_Info@@EA; _Ipv6Prefix_Info * RasDhcpIpv6AllocPool
0x18005cba5  mov     [rbx], rax
0x18005cba8  mov     cs:?RasDhcpIpv6AllocPool@@3PEAU_Ipv6Prefix_Info@@EA, rbx; _Ipv6Prefix_Info * RasDhcpIpv6AllocPool
0x18005cbaf  mov     rax, [rbx+20h]
0x18005cbb3  mov     rdx, [rax+8]
0x18005cbb7  mov     rax, [rdx]
0x18005cbba  lea     rdx, [rsp+8C8h+S]; S
0x18005cbbf  mov     [rsi], rax
0x18005cbc2  call    cs:__imp_RtlIpv6AddressToStringA
0x18005cbc9  nop     dword ptr [rax+rax+00h]
0x18005cbce  cmp     qword ptr cs:xmmword_1800D0740, r14
0x18005cbd5  jz      short loc_18005CC1B
0x18005cbd7  lea     r8, [rsp+8C8h+S]
0x18005cbdc  mov     word ptr [rsp+8C8h+var_828], r14w
0x18005cbe5  lea     rdx, aAcquired0xHs; "Acquired 0x%hs"
0x18005cbec  lea     rcx, [rsp+8C8h+var_828]
0x18005cbf4  call    FormatRRASErrorString
0x18005cbf9  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005cc00  lea     r8, [rsp+8C8h+var_828]
0x18005cc08  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005cc0f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005cc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc1b  or      dword ptr [rbx+50h], 2
0x18005cc1f  mov     [rbx+58h], rbp
0x18005cc23  cmp     cs:?RasDhcpIpv6FreePool@@3PEAU_Ipv6Prefix_Info@@EA, r14; _Ipv6Prefix_Info * RasDhcpIpv6FreePool
0x18005cc2a  jnz     short loc_18005CC64
0x18005cc2c  cmp     cs:?RasDhcpNumIpv6ReqPrefix@@3KA, r14d; ulong RasDhcpNumIpv6ReqPrefix
0x18005cc33  jnz     short loc_18005CC64
0x18005cc35  mov     eax, cs:dword_1800D08D8
0x18005cc3b  mov     r9d, 7530h; Period
0x18005cc41  mov     rdx, cs:?RasDhcpIpv6TimerHandle@@3PEAXEA; Timer
0x18005cc48  xor     r8d, r8d; DueTime
0x18005cc4b  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18005cc52  mov     cs:?RasDhcpNumIpv6ReqPrefix@@3KA, eax; ulong RasDhcpNumIpv6ReqPrefix
0x18005cc58  call    cs:__imp_RtlUpdateTimer
0x18005cc5f  nop     dword ptr [rax+rax+00h]
0x18005cc64  mov     edi, r14d
0x18005cc67  lea     rcx, ?csRasDhcpv6@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005cc6e  call    cs:__imp_LeaveCriticalSection
0x18005cc75  nop     dword ptr [rax+rax+00h]
0x18005cc7a  mov     eax, edi
0x18005cc7c  mov     rcx, [rsp+8C8h+var_28]
0x18005cc84  xor     rcx, rsp; StackCookie
0x18005cc87  call    __security_check_cookie
0x18005cc8c  lea     r11, [rsp+8C8h+var_18]
0x18005cc94  mov     rbx, [r11+20h]
0x18005cc98  mov     rbp, [r11+30h]
0x18005cc9c  mov     rsp, r11
0x18005cc9f  pop     r14
0x18005cca1  pop     rdi
0x18005cca2  pop     rsi
0x18005cca3  retn
```
