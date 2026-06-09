# RasDhcpAcquireAddress

- ea: `0x18006076c`
- end: `0x1800609b3`
- name: `RasDhcpAcquireAddress`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800597d4`

## callees

- `0x180007c0c`
- `0x18006076c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180060982`
- `KERNEL32!LeaveCriticalSection` at `0x180060982`
- `KERNEL32!EnterCriticalSection` at `0x1800607e8`
- `KERNEL32!EnterCriticalSection` at `0x1800607e8`
- `ntdll!RtlUpdateTimer` at `0x180060930`
- `ntdll!RtlUpdateTimer` at `0x180060930`
- `WS2_32!__imp_htonl` at `0x1800608b7`
- `WS2_32!__imp_htonl` at `0x1800608c9`
- `WS2_32!__imp_htonl` at `0x1800608b7`
- `WS2_32!__imp_htonl` at `0x1800608c9`

## string_xrefs

- `0x1800607ce`: `RasDhcpAcquireAddress`

## pseudocode

```c
__int64 __fastcall RasDhcpAcquireAddress(__int64 a1, u_long *a2, u_long *a3, _DWORD *a4)
{
  unsigned int v8; // edi
  __int64 v9; // r8
  struct _Addr_Info *v10; // rbx
  __int64 *v11; // rdx
  bool v12; // zf
  int v13; // eax
  _BYTE v15[16]; // [rsp+30h] [rbp-858h] BYREF
  int v16; // [rsp+40h] [rbp-848h] BYREF
  _BYTE v17[2044]; // [rsp+44h] [rbp-844h] BYREF

  v16 = 0;
  v8 = 1168;
  memset_0(v17, 0, sizeof(v17));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasDhcpAcquireAddress");
  EnterCriticalSection(&RasDhcpCriticalSection);
  v10 = RasDhcpFreePool;
  if ( RasDhcpFreePool )
  {
    v12 = *((_QWORD *)&xmmword_1800D0740 + 1) == 0;
    RasDhcpFreePool = *(struct _Addr_Info **)RasDhcpFreePool;
    *(_QWORD *)v10 = RasDhcpAllocPool;
    RasDhcpAllocPool = v10;
    if ( !v12 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"Acquired 0x%x", *((unsigned int *)v10 + 12));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        &v16);
    }
    *a2 = htonl(*((_DWORD *)v10 + 12));
    *a3 = htonl(*((_DWORD *)v10 + 13));
    *((_DWORD *)v10 + 24) |= 2u;
    *((_QWORD *)v10 + 13) = a1;
    if ( a4 )
      *a4 = RasDhcpUsingEasyNet;
    if ( !RasDhcpFreePool && !RasDhcpNumReqAddrs )
    {
      v13 = dword_1800D08D8;
      if ( RasDhcpNtProductType == NtProductWinNt )
        v13 = 1;
      RasDhcpNumReqAddrs = v13;
      RtlUpdateTimer(RasDhcpTimerQueueHandle, RasDhcpTimerHandle, 0, 0x7530u);
    }
    v8 = 0;
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
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        L"Out of addresses");
    if ( g_dhcpIpFailureEventRaised != 1 )
    {
      g_dhcpIpFailureEventRaised = 1;
      if ( (Microsoft_Windows_MprddmEnableBits & 2) != 0 )
      {
        v11 = VPN_COULD_NOT_GET_DHCP_ADDRESS;
LABEL_21:
        McGenEventWrite_EventWriteTransfer(MPRDDM_EVENT_SOURCE_Context, v11, v9, 1, v15);
      }
    }
  }
  LeaveCriticalSection(&RasDhcpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x18006076c  push    rbx
0x18006076e  push    rbp
0x18006076f  push    rsi
0x180060770  push    rdi
0x180060771  push    r12
0x180060773  push    r14
0x180060775  push    r15
0x180060777  sub     rsp, 850h
0x18006077e  mov     rax, cs:__security_cookie
0x180060785  xor     rax, rsp
0x180060788  mov     [rsp+888h+var_48], rax
0x180060790  mov     r15, r8
0x180060793  mov     r14, rdx
0x180060796  mov     rbp, rcx
0x180060799  xor     r12d, r12d
0x18006079c  xor     edx, edx; Val
0x18006079e  mov     [rsp+888h+var_848], r12d
0x1800607a3  mov     r8d, 7FCh; Size
0x1800607a9  lea     rcx, [rsp+888h+var_844]; void *
0x1800607ae  mov     rsi, r9
0x1800607b1  mov     edi, 490h
0x1800607b6  call    memset_0
0x1800607bb  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x1800607c2  test    rdx, rdx
0x1800607c5  jz      short loc_1800607E1
0x1800607c7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800607ce  lea     r8, aRasdhcpacquire; "RasDhcpAcquireAddress"
0x1800607d5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800607dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607e1  lea     rcx, ?RasDhcpCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800607e8  call    cs:__imp_EnterCriticalSection
0x1800607ef  nop     dword ptr [rax+rax+00h]
0x1800607f4  mov     rbx, cs:?RasDhcpFreePool@@3PEAU_Addr_Info@@EA; _Addr_Info * RasDhcpFreePool
0x1800607fb  test    rbx, rbx
0x1800607fe  jnz     short loc_180060856
0x180060800  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x180060807  test    rdx, rdx
0x18006080a  jz      short loc_180060826
0x18006080c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180060813  lea     r8, aOutOfAddresses; "Out of addresses"
0x18006081a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180060821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060826  mov     ebx, 1
0x18006082b  cmp     cs:g_dhcpIpFailureEventRaised, ebx
0x180060831  jz      loc_18006097B
0x180060837  test    cs:Microsoft_Windows_MprddmEnableBits, 2
0x18006083e  mov     cs:g_dhcpIpFailureEventRaised, ebx
0x180060844  jz      loc_18006097B
0x18006084a  lea     rdx, VPN_COULD_NOT_GET_DHCP_ADDRESS
0x180060851  jmp     loc_180060962
0x180060856  cmp     qword ptr cs:xmmword_1800D0740+8, r12
0x18006085d  mov     rax, [rbx]
0x180060860  mov     cs:?RasDhcpFreePool@@3PEAU_Addr_Info@@EA, rax; _Addr_Info * RasDhcpFreePool
0x180060867  mov     rax, cs:?RasDhcpAllocPool@@3PEAU_Addr_Info@@EA; _Addr_Info * RasDhcpAllocPool
0x18006086e  mov     [rbx], rax
0x180060871  mov     cs:?RasDhcpAllocPool@@3PEAU_Addr_Info@@EA, rbx; _Addr_Info * RasDhcpAllocPool
0x180060878  jz      short loc_1800608B4
0x18006087a  mov     word ptr [rsp+888h+var_848], r12w
0x180060880  lea     rdx, aAcquired0xX; "Acquired 0x%x"
0x180060887  mov     r8d, [rbx+30h]
0x18006088b  lea     rcx, [rsp+888h+var_848]
0x180060890  call    FormatRRASErrorString
0x180060895  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18006089c  lea     r8, [rsp+888h+var_848]
0x1800608a1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800608a8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800608af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800608b4  mov     ecx, [rbx+30h]; hostlong
0x1800608b7  call    cs:__imp_htonl
0x1800608be  nop     dword ptr [rax+rax+00h]
0x1800608c3  mov     [r14], eax
0x1800608c6  mov     ecx, [rbx+34h]; hostlong
0x1800608c9  call    cs:__imp_htonl
0x1800608d0  nop     dword ptr [rax+rax+00h]
0x1800608d5  mov     [r15], eax
0x1800608d8  or      dword ptr [rbx+60h], 2
0x1800608dc  mov     [rbx+68h], rbp
0x1800608e0  test    rsi, rsi
0x1800608e3  jz      short loc_1800608ED
0x1800608e5  mov     eax, cs:?RasDhcpUsingEasyNet@@3HA; int RasDhcpUsingEasyNet
0x1800608eb  mov     [rsi], eax
0x1800608ed  cmp     cs:?RasDhcpFreePool@@3PEAU_Addr_Info@@EA, r12; _Addr_Info * RasDhcpFreePool
0x1800608f4  mov     ebx, 1
0x1800608f9  jnz     short loc_18006093C
0x1800608fb  cmp     cs:?RasDhcpNumReqAddrs@@3KA, r12d; ulong RasDhcpNumReqAddrs
0x180060902  jnz     short loc_18006093C
0x180060904  cmp     cs:?RasDhcpNtProductType@@3W4_NT_PRODUCT_TYPE@@A, ebx; _NT_PRODUCT_TYPE RasDhcpNtProductType
0x18006090a  mov     r9d, 7530h; Period
0x180060910  mov     eax, cs:dword_1800D08D8
0x180060916  mov     rdx, cs:?RasDhcpTimerHandle@@3PEAXEA; Timer
0x18006091d  cmovz   eax, ebx
0x180060920  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180060927  xor     r8d, r8d; DueTime
0x18006092a  mov     cs:?RasDhcpNumReqAddrs@@3KA, eax; ulong RasDhcpNumReqAddrs
0x180060930  call    cs:__imp_RtlUpdateTimer
0x180060937  nop     dword ptr [rax+rax+00h]
0x18006093c  mov     edi, r12d
0x18006093f  cmp     cs:g_dhcpIpFailureEventRaised, 3
0x180060946  jz      short loc_18006097B
0x180060948  test    cs:Microsoft_Windows_MprddmEnableBits, 2
0x18006094f  mov     cs:g_dhcpIpFailureEventRaised, 3
0x180060959  jz      short loc_18006097B
0x18006095b  lea     rdx, VPN_COULD_GOT_DHCP_ADDRESS
0x180060962  lea     rax, [rsp+888h+var_858]
0x180060967  mov     r9d, ebx
0x18006096a  lea     rcx, MPRDDM_EVENT_SOURCE_Context
0x180060971  mov     [rsp+888h+var_868], rax
0x180060976  call    McGenEventWrite_EventWriteTransfer
0x18006097b  lea     rcx, ?RasDhcpCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180060982  call    cs:__imp_LeaveCriticalSection
0x180060989  nop     dword ptr [rax+rax+00h]
0x18006098e  mov     eax, edi
0x180060990  mov     rcx, [rsp+888h+var_48]
0x180060998  xor     rcx, rsp; StackCookie
0x18006099b  call    __security_check_cookie
0x1800609a0  add     rsp, 850h
0x1800609a7  pop     r15
0x1800609a9  pop     r14
0x1800609ab  pop     r12
0x1800609ad  pop     rdi
0x1800609ae  pop     rsi
0x1800609af  pop     rbp
0x1800609b0  pop     rbx
0x1800609b1  retn
```
