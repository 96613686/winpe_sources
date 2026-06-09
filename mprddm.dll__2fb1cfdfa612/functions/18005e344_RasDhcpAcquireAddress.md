# RasDhcpAcquireAddress

- ea: `0x18005e344`
- end: `0x18005e572`
- name: `RasDhcpAcquireAddress`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800578ec`

## callees

- `0x180007b7c`
- `0x18005e344`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18005e543`
- `KERNEL32!LeaveCriticalSection` at `0x18005e543`
- `KERNEL32!EnterCriticalSection` at `0x18005e3ba`
- `KERNEL32!EnterCriticalSection` at `0x18005e3ba`
- `ntdll!RtlUpdateTimer` at `0x18005e4f8`
- `ntdll!RtlUpdateTimer` at `0x18005e4f8`
- `WS2_32!__imp_htonl` at `0x18005e48a`
- `WS2_32!__imp_htonl` at `0x18005e496`
- `WS2_32!__imp_htonl` at `0x18005e48a`
- `WS2_32!__imp_htonl` at `0x18005e496`

## string_xrefs

- `0x18005e3a0`: `RasDhcpAcquireAddress`

## pseudocode

```c
__int64 __fastcall RasDhcpAcquireAddress(__int64 a1, u_long *a2, u_long *a3, _DWORD *a4)
{
  __int64 v8; // r8
  struct _Addr_Info *v9; // rbx
  unsigned int v10; // edi
  __int64 *v11; // rdx
  bool v12; // zf
  int v13; // eax
  _BYTE v15[16]; // [rsp+30h] [rbp-848h] BYREF
  int v16; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v17[2044]; // [rsp+44h] [rbp-834h] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"RasDhcpAcquireAddress");
  EnterCriticalSection(&RasDhcpCriticalSection);
  v9 = RasDhcpFreePool;
  if ( RasDhcpFreePool )
  {
    v12 = *((_QWORD *)&xmmword_1800C9740 + 1) == 0;
    RasDhcpFreePool = *(struct _Addr_Info **)RasDhcpFreePool;
    *(_QWORD *)v9 = RasDhcpAllocPool;
    RasDhcpAllocPool = v9;
    if ( !v12 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"Acquired 0x%x", *((unsigned int *)v9 + 12));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        &v16);
    }
    *a2 = htonl(*((_DWORD *)v9 + 12));
    *a3 = htonl(*((_DWORD *)v9 + 13));
    *((_DWORD *)v9 + 24) |= 2u;
    *((_QWORD *)v9 + 13) = a1;
    if ( a4 )
      *a4 = RasDhcpUsingEasyNet;
    if ( !RasDhcpFreePool && !RasDhcpNumReqAddrs )
    {
      v13 = dword_1800C98D8;
      if ( RasDhcpNtProductType == NtProductWinNt )
        v13 = 1;
      RasDhcpNumReqAddrs = v13;
      RtlUpdateTimer(RasDhcpTimerQueueHandle, RasDhcpTimerHandle, 0, 0x7530u);
    }
    v10 = 0;
    if ( g_dhcpIpFailureEventRaised != 3 )
    {
      g_dhcpIpFailureEventRaised = 3;
      if ( (Microsoft_Windows_MprddmEnableBits & 2) != 0 )
      {
        v11 = VPN_COULD_GOT_DHCP_ADDRESS;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v10 = 1168;
    if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        L"Out of addresses");
    if ( g_dhcpIpFailureEventRaised != 1 )
    {
      g_dhcpIpFailureEventRaised = 1;
      if ( (Microsoft_Windows_MprddmEnableBits & 2) != 0 )
      {
        v11 = VPN_COULD_NOT_GET_DHCP_ADDRESS;
LABEL_21:
        McGenEventWrite_EventWriteTransfer(MPRDDM_EVENT_SOURCE_Context, v11, v8, 1, v15);
      }
    }
  }
  LeaveCriticalSection(&RasDhcpCriticalSection);
  return v10;
}

```

## disassembly

```asm
0x18005e344  mov     [rsp+arg_0], rbx
0x18005e349  push    rbp
0x18005e34a  push    rsi
0x18005e34b  push    rdi
0x18005e34c  push    r14
0x18005e34e  push    r15
0x18005e350  sub     rsp, 850h
0x18005e357  mov     rax, cs:__security_cookie
0x18005e35e  xor     rax, rsp
0x18005e361  mov     [rsp+878h+var_38], rax
0x18005e369  mov     r15, r8
0x18005e36c  mov     r14, rdx
0x18005e36f  mov     rbp, rcx
0x18005e372  xor     eax, eax
0x18005e374  xor     edx, edx; Val
0x18005e376  mov     [rsp+878h+var_838], eax
0x18005e37a  mov     r8d, 7FCh; Size
0x18005e380  lea     rcx, [rsp+878h+var_834]; void *
0x18005e385  mov     rsi, r9
0x18005e388  call    memset_0
0x18005e38d  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005e394  test    rdx, rdx
0x18005e397  jz      short loc_18005E3B3
0x18005e399  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e3a0  lea     r8, aRasdhcpacquire; "RasDhcpAcquireAddress"
0x18005e3a7  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3b3  lea     rcx, ?RasDhcpCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e3ba  call    cs:__imp_EnterCriticalSection
0x18005e3c0  mov     rbx, cs:?RasDhcpFreePool@@3PEAU_Addr_Info@@EA; _Addr_Info * RasDhcpFreePool
0x18005e3c7  test    rbx, rbx
0x18005e3ca  jnz     short loc_18005E427
0x18005e3cc  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005e3d3  mov     edi, 490h
0x18005e3d8  test    rdx, rdx
0x18005e3db  jz      short loc_18005E3F7
0x18005e3dd  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e3e4  lea     r8, aOutOfAddresses; "Out of addresses"
0x18005e3eb  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3f7  mov     ebx, 1
0x18005e3fc  cmp     cs:g_dhcpIpFailureEventRaised, ebx
0x18005e402  jz      loc_18005E53C
0x18005e408  test    cs:Microsoft_Windows_MprddmEnableBits, 2
0x18005e40f  mov     cs:g_dhcpIpFailureEventRaised, ebx
0x18005e415  jz      loc_18005E53C
0x18005e41b  lea     rdx, VPN_COULD_NOT_GET_DHCP_ADDRESS
0x18005e422  jmp     loc_18005E523
0x18005e427  cmp     qword ptr cs:xmmword_1800C9740+8, 0
0x18005e42f  mov     rax, [rbx]
0x18005e432  mov     cs:?RasDhcpFreePool@@3PEAU_Addr_Info@@EA, rax; _Addr_Info * RasDhcpFreePool
0x18005e439  mov     rax, cs:?RasDhcpAllocPool@@3PEAU_Addr_Info@@EA; _Addr_Info * RasDhcpAllocPool
0x18005e440  mov     [rbx], rax
0x18005e443  mov     cs:?RasDhcpAllocPool@@3PEAU_Addr_Info@@EA, rbx; _Addr_Info * RasDhcpAllocPool
0x18005e44a  jz      short loc_18005E487
0x18005e44c  xor     eax, eax
0x18005e44e  lea     rdx, aAcquired0xX; "Acquired 0x%x"
0x18005e455  mov     word ptr [rsp+878h+var_838], ax
0x18005e45a  lea     rcx, [rsp+878h+var_838]
0x18005e45f  mov     r8d, [rbx+30h]
0x18005e463  call    FormatRRASErrorString
0x18005e468  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005e46f  lea     r8, [rsp+878h+var_838]
0x18005e474  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e47b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e487  mov     ecx, [rbx+30h]; hostlong
0x18005e48a  call    cs:__imp_htonl
0x18005e490  mov     [r14], eax
0x18005e493  mov     ecx, [rbx+34h]; hostlong
0x18005e496  call    cs:__imp_htonl
0x18005e49c  mov     [r15], eax
0x18005e49f  or      dword ptr [rbx+60h], 2
0x18005e4a3  mov     [rbx+68h], rbp
0x18005e4a7  test    rsi, rsi
0x18005e4aa  jz      short loc_18005E4B4
0x18005e4ac  mov     eax, cs:?RasDhcpUsingEasyNet@@3HA; int RasDhcpUsingEasyNet
0x18005e4b2  mov     [rsi], eax
0x18005e4b4  cmp     cs:?RasDhcpFreePool@@3PEAU_Addr_Info@@EA, 0; _Addr_Info * RasDhcpFreePool
0x18005e4bc  mov     ebx, 1
0x18005e4c1  jnz     short loc_18005E4FE
0x18005e4c3  cmp     cs:?RasDhcpNumReqAddrs@@3KA, 0; ulong RasDhcpNumReqAddrs
0x18005e4ca  jnz     short loc_18005E4FE
0x18005e4cc  cmp     cs:?RasDhcpNtProductType@@3W4_NT_PRODUCT_TYPE@@A, ebx; _NT_PRODUCT_TYPE RasDhcpNtProductType
0x18005e4d2  mov     r9d, 7530h; Period
0x18005e4d8  mov     eax, cs:dword_1800C98D8
0x18005e4de  mov     rdx, cs:?RasDhcpTimerHandle@@3PEAXEA; Timer
0x18005e4e5  cmovz   eax, ebx
0x18005e4e8  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18005e4ef  xor     r8d, r8d; DueTime
0x18005e4f2  mov     cs:?RasDhcpNumReqAddrs@@3KA, eax; ulong RasDhcpNumReqAddrs
0x18005e4f8  call    cs:__imp_RtlUpdateTimer
0x18005e4fe  xor     edi, edi
0x18005e500  cmp     cs:g_dhcpIpFailureEventRaised, 3
0x18005e507  jz      short loc_18005E53C
0x18005e509  test    cs:Microsoft_Windows_MprddmEnableBits, 2
0x18005e510  mov     cs:g_dhcpIpFailureEventRaised, 3
0x18005e51a  jz      short loc_18005E53C
0x18005e51c  lea     rdx, VPN_COULD_GOT_DHCP_ADDRESS
0x18005e523  lea     rax, [rsp+878h+var_848]
0x18005e528  mov     r9d, ebx
0x18005e52b  lea     rcx, MPRDDM_EVENT_SOURCE_Context
0x18005e532  mov     [rsp+878h+var_858], rax
0x18005e537  call    McGenEventWrite_EventWriteTransfer
0x18005e53c  lea     rcx, ?RasDhcpCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005e543  call    cs:__imp_LeaveCriticalSection
0x18005e549  mov     eax, edi
0x18005e54b  mov     rcx, [rsp+878h+var_38]
0x18005e553  xor     rcx, rsp; StackCookie
0x18005e556  call    __security_check_cookie
0x18005e55b  mov     rbx, [rsp+878h+arg_0]
0x18005e563  add     rsp, 850h
0x18005e56a  pop     r15
0x18005e56c  pop     r14
0x18005e56e  pop     rdi
0x18005e56f  pop     rsi
0x18005e570  pop     rbp
0x18005e571  retn
```
