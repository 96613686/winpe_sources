# TeredoStopClient

- ea: `0x180015a7c`
- end: `0x180015d4b`
- name: `TeredoStopClient`
- size: `719`
- prototype: ``
- caller_count: `16`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005510`
- `0x180007f44`
- `0x180008270`
- `0x1800084e4`
- `0x180008f8c`
- `0x180009210`
- `0x1800135b0`
- `0x180014180`
- `0x18001a9a0`
- `0x180032190`
- `0x18003f368`
- `0x180042e60`
- `0x180043310`
- `0x18005220c`
- `0x180052380`
- `0x1800525f0`

## callees

- `0x180004c64`
- `0x180008af4`
- `0x18000d7c0`
- `0x180015a7c`
- `0x180015d54`
- `0x180015da0`
- `0x180015e10`
- `0x18001614c`
- `0x1800161b0`
- `0x1800162e8`
- `0x1800163e4`
- `0x1800190f0`
- `0x18001b1c0`
- `0x1800338f4`
- `0x180040fe0`
- `0x18004d2b8`
- `0x180050274`

## import_xrefs

- `IPHLPAPI!InternalSetTeredoPort` at `0x180015bba`
- `IPHLPAPI!InternalSetTeredoPort` at `0x180015bba`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180015c19`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180015c19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015c3c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015c3c`
- `WS2_32!__imp_ntohs` at `0x180015d25`
- `WS2_32!__imp_ntohs` at `0x180015d25`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x180015d0a`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x180015d0a`

## string_xrefs

- `0x180015a8c`: `Teredo stopping client 0x%p (compartment %u, state %u)`

## pseudocode

```c
__int64 __fastcall TeredoStopClient(__int64 a1)
{
  __int64 v1; // rsi
  __int64 result; // rax
  unsigned int v4; // edx
  const wchar_t *v5; // r8
  struct _SLIST_ENTRY *v6; // rax
  u_short v7; // ax
  __int64 v8; // [rsp+20h] [rbp-38h]

  v1 = *(_QWORD *)(a1 + 7904);
  result = EventWrite0(
             0x100000,
             L"Teredo stopping client 0x%p (compartment %u, state %u)",
             a1,
             *(unsigned int *)(v1 + 16),
             *(_DWORD *)(a1 + 8584));
  v4 = *(_DWORD *)(a1 + 8584);
  if ( v4 >= 2 )
  {
    if ( v4 == 2 )
    {
      result = TeredoClientChangeStateAndLog(a1, 1);
LABEL_15:
      if ( !*(_BYTE *)(a1 + 8698) )
        return TeredoClientUpdateStateInNsi(a1);
      return result;
    }
    if ( v4 == 5 )
    {
      TeredoClientStopTypeSpecificBehavior(a1);
    }
    else if ( *(_DWORD *)(v1 + 2868) )
    {
      TeredoRecordInterfaceConnectivity(a1);
    }
    TeredoTelemetryWriteFailedQualification(a1);
    *(_DWORD *)(a1 + 8616) = 0;
    if ( *(_DWORD *)(v1 + 2868) )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) == 0 )
      {
LABEL_8:
        v5 = L"Relay";
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 7904) + 2864LL) != 1 )
          v5 = L"Client";
        LODWORD(v8) = *(_DWORD *)(a1 + 8684);
        EventWrite0(
          0x100000,
          L"Current status: %ws Mode, Firewall enabled %d, Listening Apps %u",
          v5,
          *(unsigned int *)(a1 + 8688),
          v8);
        *(_DWORD *)(a1 + 8584) = 1;
        *(_DWORD *)(a1 + 8680) = 0;
        *(_DWORD *)(a1 + 10980) = 0;
        TeredoClientFreeQueuedPackets(a1);
        v6 = *(struct _SLIST_ENTRY **)(a1 + 10952);
        *(_QWORD *)(a1 + 10992) = 0;
        *(_QWORD *)(a1 + 11000) = 0;
        *(_WORD *)(a1 + 8592) = 0;
        if ( v6 )
        {
          *(_QWORD *)(a1 + 10952) = 0;
          if ( v6[1].Next )
          {
            InterlockedPushEntrySList((PSLIST_HEADER)(a1 + 14320), v6);
            if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 10976), 1, 0) )
              TpclSetThreadpoolWait(*(_QWORD *)(a1 + 10968), *(_QWORD *)(a1 + 10960));
            SetEvent(*(HANDLE *)(a1 + 10960));
          }
          else
          {
            FREE(v6);
          }
        }
        *(IN6_ADDR *)(a1 + 8728) = in6addr_teredoinitiallinklocaladdress;
        HashTableCallbackForEachEntry(a1 + 8816);
        TeredoStopIo(a1 + 5144);
        if ( (unsigned int)InternalSetTeredoPort(0) )
          EventWriteError0(0x100000, L"Unable to reset Teredo port state in NSI.");
        if ( (unsigned __int8)IsIphlpsvcExtConfigureTeredoClientPortPresent()
          && (unsigned int)IphlpsvcExtConfigureTeredoClientPort(0) )
        {
          v7 = ntohs(*(_WORD *)(a1 + 7806));
          EventWriteError0(0x100000, L"Unable to set Teredo port value (%d) in Xbox Virtual NIC", v7);
        }
        result = HashTableUninitialize((LPCRITICAL_SECTION)(a1 + 8816));
        goto LABEL_15;
      }
      McTemplateU0q_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STOP,
        *(unsigned int *)(*(_QWORD *)(a1 + 7904) + 2868LL));
    }
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STATE_CHANGE,
        *(unsigned int *)(a1 + 8584),
        1);
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x180015a7c  push    rbx
0x180015a7e  push    rbp
0x180015a7f  push    rsi
0x180015a80  push    rdi
0x180015a81  sub     rsp, 38h
0x180015a85  mov     rsi, [rcx+1EE0h]
0x180015a8c  lea     rdx, aTeredoStopping; "Teredo stopping client 0x%p (compartmen"...
0x180015a93  mov     eax, [rcx+2188h]
0x180015a99  mov     rbx, rcx
0x180015a9c  mov     r8, rcx
0x180015a9f  mov     dword ptr [rsp+58h+var_38], eax
0x180015aa3  mov     ecx, 100000h
0x180015aa8  mov     r9d, [rsi+10h]
0x180015aac  call    EventWrite0
0x180015ab1  mov     edx, [rbx+2188h]
0x180015ab7  xor     ebp, ebp
0x180015ab9  mov     ecx, edx
0x180015abb  test    edx, edx
0x180015abd  jz      loc_180015BF4
0x180015ac3  sub     ecx, 1
0x180015ac6  jz      loc_180015BF4
0x180015acc  cmp     ecx, 1
0x180015acf  jz      loc_180015C80
0x180015ad5  cmp     edx, 5
0x180015ad8  jnz     loc_180015C92
0x180015ade  mov     rcx, rbx
0x180015ae1  call    TeredoClientStopTypeSpecificBehavior
0x180015ae6  mov     rcx, rbx
0x180015ae9  call    TeredoTelemetryWriteFailedQualification
0x180015aee  mov     [rbx+21A8h], ebp
0x180015af4  mov     edi, 1
0x180015af9  cmp     [rsi+0B34h], ebp
0x180015aff  jnz     loc_180015C4D
0x180015b05  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, dil
0x180015b0c  jnz     loc_180015CAB
0x180015b12  mov     rax, [rbx+1EE0h]
0x180015b19  lea     rcx, aClient; "Client"
0x180015b20  mov     r9d, [rbx+21F0h]
0x180015b27  lea     r8, aRelay; "Relay"
0x180015b2e  lea     rdx, aCurrentStatusW; "Current status: %ws Mode, Firewall enab"...
0x180015b35  cmp     [rax+0B30h], edi
0x180015b3b  mov     eax, [rbx+21ECh]
0x180015b41  cmovnz  r8, rcx
0x180015b45  mov     dword ptr [rsp+58h+var_38], eax
0x180015b49  mov     ecx, 100000h
0x180015b4e  call    EventWrite0
0x180015b53  mov     rcx, rbx
0x180015b56  mov     [rbx+2188h], edi
0x180015b5c  mov     [rbx+21E8h], ebp
0x180015b62  mov     [rbx+2AE4h], ebp
0x180015b68  call    TeredoClientFreeQueuedPackets
0x180015b6d  mov     rax, [rbx+2AC8h]
0x180015b74  mov     [rbx+2AF0h], rbp
0x180015b7b  mov     [rbx+2AF8h], rbp
0x180015b82  mov     [rbx+2190h], bp
0x180015b89  test    rax, rax
0x180015b8c  jnz     short loc_180015BFE
0x180015b8e  movups  xmm0, xmmword ptr cs:in6addr_teredoinitiallinklocaladdress.u
0x180015b95  lea     rdi, [rbx+2270h]
0x180015b9c  mov     rcx, rdi
0x180015b9f  movdqu  xmmword ptr [rbx+2218h], xmm0
0x180015ba7  call    HashTableCallbackForEachEntry
0x180015bac  lea     rcx, [rbx+1418h]
0x180015bb3  call    TeredoStopIo
0x180015bb8  xor     ecx, ecx
0x180015bba  call    cs:__imp_InternalSetTeredoPort
0x180015bc1  nop     dword ptr [rax+rax+00h]
0x180015bc6  test    eax, eax
0x180015bc8  jnz     loc_180015CF2
0x180015bce  call    IsIphlpsvcExtConfigureTeredoClientPortPresent
0x180015bd3  test    al, al
0x180015bd5  jnz     loc_180015D08
0x180015bdb  mov     rcx, rdi; lpCriticalSection
0x180015bde  call    HashTableUninitialize
0x180015be3  cmp     [rbx+21FAh], bpl
0x180015bea  jnz     short loc_180015BF4
0x180015bec  mov     rcx, rbx
0x180015bef  call    TeredoClientUpdateStateInNsi
0x180015bf4  add     rsp, 38h
0x180015bf8  pop     rdi
0x180015bf9  pop     rsi
0x180015bfa  pop     rbp
0x180015bfb  pop     rbx
0x180015bfc  retn
0x180015bfe  mov     [rbx+2AC8h], rbp
0x180015c05  cmp     [rax+10h], rbp
0x180015c09  jz      loc_180015CE5
0x180015c0f  lea     rcx, [rbx+37F0h]; ListHead
0x180015c16  mov     rdx, rax; ListEntry
0x180015c19  call    cs:__imp_InterlockedPushEntrySList
0x180015c20  nop     dword ptr [rax+rax+00h]
0x180015c25  xor     eax, eax
0x180015c27  lock cmpxchg [rbx+2AE0h], edi
0x180015c2f  jz      loc_180015CCD
0x180015c35  mov     rcx, [rbx+2AD0h]; hEvent
0x180015c3c  call    cs:__imp_SetEvent
0x180015c43  nop     dword ptr [rax+rax+00h]
0x180015c48  jmp     loc_180015B8E
0x180015c4d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, dil
0x180015c54  jz      loc_180015B12
0x180015c5a  mov     r8, [rbx+1EE0h]
0x180015c61  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STOP
0x180015c68  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180015c6f  mov     r8d, [r8+0B34h]
0x180015c76  call    McTemplateU0q_EventWriteTransfer
0x180015c7b  jmp     loc_180015B05
0x180015c80  mov     edx, 1
0x180015c85  mov     rcx, rbx
0x180015c88  call    TeredoClientChangeStateAndLog
0x180015c8d  jmp     loc_180015BE3
0x180015c92  cmp     [rsi+0B34h], ebp
0x180015c98  jz      loc_180015AE6
0x180015c9e  mov     rcx, rbx
0x180015ca1  call    TeredoRecordInterfaceConnectivity
0x180015ca6  jmp     loc_180015AE6
0x180015cab  mov     r8d, [rbx+2188h]
0x180015cb2  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STATE_CHANGE
0x180015cb9  mov     r9d, edi
0x180015cbc  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180015cc3  call    McTemplateU0qq_EventWriteTransfer
0x180015cc8  jmp     loc_180015B12
0x180015ccd  mov     rdx, [rbx+2AD0h]
0x180015cd4  mov     rcx, [rbx+2AD8h]
0x180015cdb  call    TpclSetThreadpoolWait
0x180015ce0  jmp     loc_180015C35
0x180015ce5  mov     rcx, rax
0x180015ce8  call    FREE
0x180015ced  jmp     loc_180015B8E
0x180015cf2  lea     rdx, aUnableToResetT; "Unable to reset Teredo port state in NS"...
0x180015cf9  mov     ecx, 100000h
0x180015cfe  call    EventWriteError0
0x180015d03  jmp     loc_180015BCE
0x180015d08  xor     ecx, ecx
0x180015d0a  call    cs:__imp_IphlpsvcExtConfigureTeredoClientPort
0x180015d11  nop     dword ptr [rax+rax+00h]
0x180015d16  test    eax, eax
0x180015d18  jz      loc_180015BDB
0x180015d1e  movzx   ecx, word ptr [rbx+1E7Eh]; netshort
0x180015d25  call    cs:__imp_ntohs
0x180015d2c  nop     dword ptr [rax+rax+00h]
0x180015d31  movzx   r8d, ax
0x180015d35  lea     rdx, aUnableToSetTer; "Unable to set Teredo port value (%d) in"...
0x180015d3c  mov     ecx, 100000h
0x180015d41  call    EventWriteError0
0x180015d46  jmp     loc_180015BDB
```
