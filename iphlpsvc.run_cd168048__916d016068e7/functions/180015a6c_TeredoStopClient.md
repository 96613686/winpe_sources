# TeredoStopClient

- ea: `0x180015a6c`
- end: `0x180015d3b`
- name: `TeredoStopClient`
- size: `719`
- prototype: ``
- caller_count: `16`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005500`
- `0x180007f34`
- `0x180008260`
- `0x1800084d4`
- `0x180008f7c`
- `0x180009200`
- `0x1800135a0`
- `0x180014170`
- `0x18001a990`
- `0x180032180`
- `0x18003f3a8`
- `0x180042ea0`
- `0x180043350`
- `0x18005224c`
- `0x1800523c0`
- `0x180052630`

## callees

- `0x180004c54`
- `0x180008ae4`
- `0x18000d7b0`
- `0x180015a6c`
- `0x180015d44`
- `0x180015d90`
- `0x180015e00`
- `0x18001613c`
- `0x1800161a0`
- `0x1800162d8`
- `0x1800163d4`
- `0x1800190e0`
- `0x18001b1b0`
- `0x1800338e4`
- `0x180041020`
- `0x18004d2f8`
- `0x1800502b4`

## import_xrefs

- `IPHLPAPI!InternalSetTeredoPort` at `0x180015baa`
- `IPHLPAPI!InternalSetTeredoPort` at `0x180015baa`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180015c09`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180015c09`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015c2c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015c2c`
- `WS2_32!__imp_ntohs` at `0x180015d15`
- `WS2_32!__imp_ntohs` at `0x180015d15`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x180015cfa`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x180015cfa`

## string_xrefs

- `0x180015a7c`: `Teredo stopping client 0x%p (compartment %u, state %u)`

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
0x180015a6c  push    rbx
0x180015a6e  push    rbp
0x180015a6f  push    rsi
0x180015a70  push    rdi
0x180015a71  sub     rsp, 38h
0x180015a75  mov     rsi, [rcx+1EE0h]
0x180015a7c  lea     rdx, aTeredoStopping; "Teredo stopping client 0x%p (compartmen"...
0x180015a83  mov     eax, [rcx+2188h]
0x180015a89  mov     rbx, rcx
0x180015a8c  mov     r8, rcx
0x180015a8f  mov     dword ptr [rsp+58h+var_38], eax
0x180015a93  mov     ecx, 100000h
0x180015a98  mov     r9d, [rsi+10h]
0x180015a9c  call    EventWrite0
0x180015aa1  mov     edx, [rbx+2188h]
0x180015aa7  xor     ebp, ebp
0x180015aa9  mov     ecx, edx
0x180015aab  test    edx, edx
0x180015aad  jz      loc_180015BE4
0x180015ab3  sub     ecx, 1
0x180015ab6  jz      loc_180015BE4
0x180015abc  cmp     ecx, 1
0x180015abf  jz      loc_180015C70
0x180015ac5  cmp     edx, 5
0x180015ac8  jnz     loc_180015C82
0x180015ace  mov     rcx, rbx
0x180015ad1  call    TeredoClientStopTypeSpecificBehavior
0x180015ad6  mov     rcx, rbx
0x180015ad9  call    TeredoTelemetryWriteFailedQualification
0x180015ade  mov     [rbx+21A8h], ebp
0x180015ae4  mov     edi, 1
0x180015ae9  cmp     [rsi+0B34h], ebp
0x180015aef  jnz     loc_180015C3D
0x180015af5  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, dil
0x180015afc  jnz     loc_180015C9B
0x180015b02  mov     rax, [rbx+1EE0h]
0x180015b09  lea     rcx, aClient; "Client"
0x180015b10  mov     r9d, [rbx+21F0h]
0x180015b17  lea     r8, aRelay; "Relay"
0x180015b1e  lea     rdx, aCurrentStatusW; "Current status: %ws Mode, Firewall enab"...
0x180015b25  cmp     [rax+0B30h], edi
0x180015b2b  mov     eax, [rbx+21ECh]
0x180015b31  cmovnz  r8, rcx
0x180015b35  mov     dword ptr [rsp+58h+var_38], eax
0x180015b39  mov     ecx, 100000h
0x180015b3e  call    EventWrite0
0x180015b43  mov     rcx, rbx
0x180015b46  mov     [rbx+2188h], edi
0x180015b4c  mov     [rbx+21E8h], ebp
0x180015b52  mov     [rbx+2AE4h], ebp
0x180015b58  call    TeredoClientFreeQueuedPackets
0x180015b5d  mov     rax, [rbx+2AC8h]
0x180015b64  mov     [rbx+2AF0h], rbp
0x180015b6b  mov     [rbx+2AF8h], rbp
0x180015b72  mov     [rbx+2190h], bp
0x180015b79  test    rax, rax
0x180015b7c  jnz     short loc_180015BEE
0x180015b7e  movups  xmm0, xmmword ptr cs:in6addr_teredoinitiallinklocaladdress.u
0x180015b85  lea     rdi, [rbx+2270h]
0x180015b8c  mov     rcx, rdi
0x180015b8f  movdqu  xmmword ptr [rbx+2218h], xmm0
0x180015b97  call    HashTableCallbackForEachEntry
0x180015b9c  lea     rcx, [rbx+1418h]
0x180015ba3  call    TeredoStopIo
0x180015ba8  xor     ecx, ecx
0x180015baa  call    cs:__imp_InternalSetTeredoPort
0x180015bb1  nop     dword ptr [rax+rax+00h]
0x180015bb6  test    eax, eax
0x180015bb8  jnz     loc_180015CE2
0x180015bbe  call    IsIphlpsvcExtConfigureTeredoClientPortPresent
0x180015bc3  test    al, al
0x180015bc5  jnz     loc_180015CF8
0x180015bcb  mov     rcx, rdi; lpCriticalSection
0x180015bce  call    HashTableUninitialize
0x180015bd3  cmp     [rbx+21FAh], bpl
0x180015bda  jnz     short loc_180015BE4
0x180015bdc  mov     rcx, rbx
0x180015bdf  call    TeredoClientUpdateStateInNsi
0x180015be4  add     rsp, 38h
0x180015be8  pop     rdi
0x180015be9  pop     rsi
0x180015bea  pop     rbp
0x180015beb  pop     rbx
0x180015bec  retn
0x180015bee  mov     [rbx+2AC8h], rbp
0x180015bf5  cmp     [rax+10h], rbp
0x180015bf9  jz      loc_180015CD5
0x180015bff  lea     rcx, [rbx+37F0h]; ListHead
0x180015c06  mov     rdx, rax; ListEntry
0x180015c09  call    cs:__imp_InterlockedPushEntrySList
0x180015c10  nop     dword ptr [rax+rax+00h]
0x180015c15  xor     eax, eax
0x180015c17  lock cmpxchg [rbx+2AE0h], edi
0x180015c1f  jz      loc_180015CBD
0x180015c25  mov     rcx, [rbx+2AD0h]; hEvent
0x180015c2c  call    cs:__imp_SetEvent
0x180015c33  nop     dword ptr [rax+rax+00h]
0x180015c38  jmp     loc_180015B7E
0x180015c3d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, dil
0x180015c44  jz      loc_180015B02
0x180015c4a  mov     r8, [rbx+1EE0h]
0x180015c51  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STOP
0x180015c58  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180015c5f  mov     r8d, [r8+0B34h]
0x180015c66  call    McTemplateU0q_EventWriteTransfer
0x180015c6b  jmp     loc_180015AF5
0x180015c70  mov     edx, 1
0x180015c75  mov     rcx, rbx
0x180015c78  call    TeredoClientChangeStateAndLog
0x180015c7d  jmp     loc_180015BD3
0x180015c82  cmp     [rsi+0B34h], ebp
0x180015c88  jz      loc_180015AD6
0x180015c8e  mov     rcx, rbx
0x180015c91  call    TeredoRecordInterfaceConnectivity
0x180015c96  jmp     loc_180015AD6
0x180015c9b  mov     r8d, [rbx+2188h]
0x180015ca2  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STATE_CHANGE
0x180015ca9  mov     r9d, edi
0x180015cac  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180015cb3  call    McTemplateU0qq_EventWriteTransfer
0x180015cb8  jmp     loc_180015B02
0x180015cbd  mov     rdx, [rbx+2AD0h]
0x180015cc4  mov     rcx, [rbx+2AD8h]
0x180015ccb  call    TpclSetThreadpoolWait
0x180015cd0  jmp     loc_180015C25
0x180015cd5  mov     rcx, rax
0x180015cd8  call    FREE
0x180015cdd  jmp     loc_180015B7E
0x180015ce2  lea     rdx, aUnableToResetT; "Unable to reset Teredo port state in NS"...
0x180015ce9  mov     ecx, 100000h
0x180015cee  call    EventWriteError0
0x180015cf3  jmp     loc_180015BBE
0x180015cf8  xor     ecx, ecx
0x180015cfa  call    cs:__imp_IphlpsvcExtConfigureTeredoClientPort
0x180015d01  nop     dword ptr [rax+rax+00h]
0x180015d06  test    eax, eax
0x180015d08  jz      loc_180015BCB
0x180015d0e  movzx   ecx, word ptr [rbx+1E7Eh]; netshort
0x180015d15  call    cs:__imp_ntohs
0x180015d1c  nop     dword ptr [rax+rax+00h]
0x180015d21  movzx   r8d, ax
0x180015d25  lea     rdx, aUnableToSetTer; "Unable to set Teredo port value (%d) in"...
0x180015d2c  mov     ecx, 100000h
0x180015d31  call    EventWriteError0
0x180015d36  jmp     loc_180015BCB
```
