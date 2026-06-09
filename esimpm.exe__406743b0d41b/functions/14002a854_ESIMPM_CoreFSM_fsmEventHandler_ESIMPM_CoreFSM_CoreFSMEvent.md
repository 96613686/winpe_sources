# ESIMPM::CoreFSM::fsmEventHandler(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002a854`
- end: `0x14002aa16`
- name: `?fsmEventHandler@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `450`
- prototype: `void __fastcall(unsigned int *, unsigned int)`
- caller_count: `9`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x140024624`
- `0x140024770`
- `0x1400248e0`
- `0x140028160`
- `0x140028774`
- `0x140028e5c`
- `0x140029040`
- `0x1400312d4`
- `0x14003154c`

## callees

- `0x140014f64`
- `0x140020620`
- `0x14002a854`
- `0x14002aa1c`
- `0x14002acf8`
- `0x14002b090`
- `0x14002b32c`
- `0x14002b46c`
- `0x14002b8c0`
- `0x14002b9f8`
- `0x14002bae4`
- `0x14002bbd0`
- `0x14002bc98`
- `0x14002be60`
- `0x14002bf60`
- `0x14002c0a0`
- `0x14002c528`
- `0x14002ca30`
- `0x14002cb80`

## pseudocode

```c
void __fastcall ESIMPM::CoreFSM::fsmEventHandler(unsigned int *a1, unsigned int a2)
{
  wchar_t *v2; // rsi
  __int64 v6; // [rsp+20h] [rbp-18h]

  v2 = (wchar_t *)(a1 + 46);
  ESIMPM::Log::Info(
    "ESIMPM::CoreFSM::fsmEventHandler",
    (const struct _GUID *)(a1 + 46),
    L" entry with state: %u, event: %u",
    *a1,
    a2);
  if ( (int)*a1 > 8 )
  {
    switch ( *a1 )
    {
      case 9u:
        ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileList(a1, a2);
        goto LABEL_35;
      case 0xAu:
        ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF(a1, a2);
        goto LABEL_35;
      case 0xBu:
        ESIMPM::CoreFSM::fsmEventHandler_WaitEFQueryResult(a1, a2);
        goto LABEL_35;
      case 0xCu:
        ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF(a1, a2);
        goto LABEL_35;
      case 0xDu:
        ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan(a1, a2);
        goto LABEL_35;
      case 0xEu:
        ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan(a1, a2);
        goto LABEL_35;
      case 0x10u:
        ESIMPM::CoreFSM::fsmEventHandler_WaitRadioOnForScan(a1, a2);
        goto LABEL_35;
    }
    goto LABEL_27;
  }
  switch ( *a1 )
  {
    case 8u:
      ESIMPM::CoreFSM::fsmEventHandler_NoCellConnectivity(a1, a2);
      goto LABEL_35;
    case 0u:
      ESIMPM::CoreFSM::fsmEventHandler_WaitEligibleModem(a1, a2);
      goto LABEL_35;
    case 1u:
      ESIMPM::CoreFSM::fsmEventHandler_WaitScanResult(a1, a2);
      goto LABEL_35;
    case 2u:
      ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForConn(a1, a2);
      goto LABEL_35;
    case 3u:
      ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn(a1, a2);
      goto LABEL_35;
    case 4u:
      ESIMPM::CoreFSM::fsmEventHandler_WaitRegistered(a1, a2);
      goto LABEL_35;
    case 5u:
      ESIMPM::CoreFSM::fsmEventHandler_WaitConnected(a1, a2);
      goto LABEL_35;
    case 6u:
      ESIMPM::CoreFSM::fsmEventHandler_Connected(a1, a2);
      goto LABEL_35;
  }
  if ( *a1 != 7 )
  {
LABEL_27:
    ESIMPM::Log::Error("ESIMPM::CoreFSM::fsmEventHandler", v2, L" invalid state %u", *a1);
    goto LABEL_35;
  }
  ESIMPM::CoreFSM::fsmEventHandler_ConnectedGoingIntoSleep(a1, a2);
LABEL_35:
  LODWORD(v6) = a2;
  ESIMPM::Log::Info(
    "ESIMPM::CoreFSM::fsmEventHandler",
    (const struct _GUID *)v2,
    L" exit with state: %u, event: %u",
    *a1,
    v6);
}

```

## disassembly

```asm
0x14002a854  mov     [rsp+arg_0], rbx
0x14002a859  mov     [rsp+arg_8], rsi
0x14002a85e  push    rdi
0x14002a85f  sub     rsp, 30h
0x14002a863  mov     r9d, [rcx]
0x14002a866  lea     rsi, [rcx+0B8h]
0x14002a86d  mov     edi, edx
0x14002a86f  mov     dword ptr [rsp+38h+var_18], edx
0x14002a873  mov     rbx, rcx
0x14002a876  lea     r8, aEntryWithState; " entry with state: %u, event: %u"
0x14002a87d  mov     rdx, rsi; struct _GUID *
0x14002a880  lea     rcx, aEsimpmCorefsmF_18; "ESIMPM::CoreFSM::fsmEventHandler"
0x14002a887  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002a88c  cmp     dword ptr [rbx], 8
0x14002a88f  jg      loc_14002A953
0x14002a895  jz      loc_14002A944
0x14002a89b  mov     ecx, [rbx]
0x14002a89d  test    ecx, ecx
0x14002a89f  jz      loc_14002A935
0x14002a8a5  sub     ecx, 1
0x14002a8a8  jz      short loc_14002A926
0x14002a8aa  sub     ecx, 1
0x14002a8ad  jz      short loc_14002A917
0x14002a8af  sub     ecx, 1
0x14002a8b2  jz      short loc_14002A908
0x14002a8b4  sub     ecx, 1
0x14002a8b7  jz      short loc_14002A8F9
0x14002a8b9  sub     ecx, 1
0x14002a8bc  jz      short loc_14002A8EA
0x14002a8be  sub     ecx, 1
0x14002a8c1  jz      short loc_14002A8DB
0x14002a8c3  cmp     ecx, 1
0x14002a8c6  jnz     loc_14002A97C
0x14002a8cc  mov     edx, edi
0x14002a8ce  mov     rcx, rbx
0x14002a8d1  call    ?fsmEventHandler_ConnectedGoingIntoSleep@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_ConnectedGoingIntoSleep(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a8d6  jmp     loc_14002A9E9
0x14002a8db  mov     edx, edi
0x14002a8dd  mov     rcx, rbx
0x14002a8e0  call    ?fsmEventHandler_Connected@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_Connected(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a8e5  jmp     loc_14002A9E9
0x14002a8ea  mov     edx, edi
0x14002a8ec  mov     rcx, rbx
0x14002a8ef  call    ?fsmEventHandler_WaitConnected@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitConnected(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a8f4  jmp     loc_14002A9E9
0x14002a8f9  mov     edx, edi
0x14002a8fb  mov     rcx, rbx
0x14002a8fe  call    ?fsmEventHandler_WaitRegistered@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitRegistered(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a903  jmp     loc_14002A9E9
0x14002a908  mov     edx, edi
0x14002a90a  mov     rcx, rbx
0x14002a90d  call    ?fsmEventHandler_WaitSIMReadyForConn@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a912  jmp     loc_14002A9E9
0x14002a917  mov     edx, edi
0x14002a919  mov     rcx, rbx
0x14002a91c  call    ?fsmEventHandler_WaitESIMProfileEnabledForConn@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForConn(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a921  jmp     loc_14002A9E9
0x14002a926  mov     edx, edi
0x14002a928  mov     rcx, rbx
0x14002a92b  call    ?fsmEventHandler_WaitScanResult@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitScanResult(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a930  jmp     loc_14002A9E9
0x14002a935  mov     edx, edi
0x14002a937  mov     rcx, rbx
0x14002a93a  call    ?fsmEventHandler_WaitEligibleModem@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitEligibleModem(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a93f  jmp     loc_14002A9E9
0x14002a944  mov     edx, edi
0x14002a946  mov     rcx, rbx
0x14002a949  call    ?fsmEventHandler_NoCellConnectivity@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_NoCellConnectivity(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a94e  jmp     loc_14002A9E9
0x14002a953  mov     ecx, [rbx]
0x14002a955  sub     ecx, 9
0x14002a958  jz      loc_14002A9DF
0x14002a95e  sub     ecx, 1
0x14002a961  jz      short loc_14002A9D3
0x14002a963  sub     ecx, 1
0x14002a966  jz      short loc_14002A9C7
0x14002a968  sub     ecx, 1
0x14002a96b  jz      short loc_14002A9BB
0x14002a96d  sub     ecx, 1
0x14002a970  jz      short loc_14002A9AF
0x14002a972  sub     ecx, 1
0x14002a975  jz      short loc_14002A9A3
0x14002a977  cmp     ecx, 2
0x14002a97a  jz      short loc_14002A997
0x14002a97c  mov     r9d, [rbx]
0x14002a97f  lea     r8, aInvalidStateU; " invalid state %u"
0x14002a986  mov     rdx, rsi; struct _GUID *
0x14002a989  lea     rcx, aEsimpmCorefsmF_18; "ESIMPM::CoreFSM::fsmEventHandler"
0x14002a990  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002a995  jmp     short loc_14002A9E9
0x14002a997  mov     edx, edi
0x14002a999  mov     rcx, rbx
0x14002a99c  call    ?fsmEventHandler_WaitRadioOnForScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitRadioOnForScan(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9a1  jmp     short loc_14002A9E9
0x14002a9a3  mov     edx, edi
0x14002a9a5  mov     rcx, rbx
0x14002a9a8  call    ?fsmEventHandler_WaitESIMProfileEnabledForScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForScan(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9ad  jmp     short loc_14002A9E9
0x14002a9af  mov     edx, edi
0x14002a9b1  mov     rcx, rbx
0x14002a9b4  call    ?fsmEventHandler_WaitSIMReadyForScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForScan(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9b9  jmp     short loc_14002A9E9
0x14002a9bb  mov     edx, edi
0x14002a9bd  mov     rcx, rbx
0x14002a9c0  call    ?fsmEventHandler_WaitESIMProfileEnabledForEF@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileEnabledForEF(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9c5  jmp     short loc_14002A9E9
0x14002a9c7  mov     edx, edi
0x14002a9c9  mov     rcx, rbx
0x14002a9cc  call    ?fsmEventHandler_WaitEFQueryResult@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitEFQueryResult(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9d1  jmp     short loc_14002A9E9
0x14002a9d3  mov     edx, edi
0x14002a9d5  mov     rcx, rbx
0x14002a9d8  call    ?fsmEventHandler_WaitSIMReadyForEF@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9dd  jmp     short loc_14002A9E9
0x14002a9df  mov     edx, edi
0x14002a9e1  mov     rcx, rbx
0x14002a9e4  call    ?fsmEventHandler_WaitESIMProfileList@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler_WaitESIMProfileList(ESIMPM::CoreFSM::_CoreFSMEvent)
0x14002a9e9  mov     r9d, [rbx]
0x14002a9ec  lea     r8, aExitWithStateU; " exit with state: %u, event: %u"
0x14002a9f3  mov     rdx, rsi; struct _GUID *
0x14002a9f6  mov     dword ptr [rsp+38h+var_18], edi
0x14002a9fa  lea     rcx, aEsimpmCorefsmF_18; "ESIMPM::CoreFSM::fsmEventHandler"
0x14002aa01  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002aa06  mov     rbx, [rsp+38h+arg_0]
0x14002aa0b  mov     rsi, [rsp+38h+arg_8]
0x14002aa10  add     rsp, 30h
0x14002aa14  pop     rdi
0x14002aa15  retn
```
