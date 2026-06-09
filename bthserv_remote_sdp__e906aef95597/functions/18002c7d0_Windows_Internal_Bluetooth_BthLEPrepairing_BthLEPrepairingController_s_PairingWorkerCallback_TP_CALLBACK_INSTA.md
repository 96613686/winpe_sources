# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::s_PairingWorkerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002c7d0`
- end: `0x18002c827`
- name: `?s_PairingWorkerCallback@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `87`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18002bef4`
- `0x180030930`

## import_xrefs

- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002c7e8`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002c7e8`
- `BthTelemetry!BthProcessEventOccurrenceResultBthaddr` at `0x18002c80e`
- `BthTelemetry!BthProcessEventOccurrenceResultBthaddr` at `0x18002c80e`

## string_xrefs

- `0x18002c7d9`: `BTH_TELEMETRYDATA_PREPAIRING_ATTEMPTED`
- `0x18002c801`: `BTH_TELEMETRYDATA_PREPAIRING_RESULT`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::s_PairingWorkerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WORK Work)
{
  int v4; // eax

  BthProcessEventOccurrenceBthaddr(
    "BTH_TELEMETRYDATA_PREPAIRING_ATTEMPTED",
    *(_QWORD *)(*((_QWORD *)Context + 11) + 48LL));
  v4 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(*((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice **)Context
                                                                                   + 11));
  BthProcessEventOccurrenceResultBthaddr(
    "BTH_TELEMETRYDATA_PREPAIRING_RESULT",
    v4,
    *(_QWORD *)(*((_QWORD *)Context + 11) + 48LL));
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)Context);
}

```

## disassembly

```asm
0x18002c7d0  push    rbx
0x18002c7d2  sub     rsp, 20h
0x18002c7d6  mov     rbx, rdx
0x18002c7d9  lea     rcx, aBthTelemetryda_1; "BTH_TELEMETRYDATA_PREPAIRING_ATTEMPTED"
0x18002c7e0  mov     rdx, [rdx+58h]
0x18002c7e4  mov     rdx, [rdx+30h]
0x18002c7e8  call    cs:__imp_?BthProcessEventOccurrenceBthaddr@@YAXPEBD_K@Z; BthProcessEventOccurrenceBthaddr(char const *,unsigned __int64)
0x18002c7ef  nop     dword ptr [rax+rax+00h]
0x18002c7f4  mov     rcx, [rbx+58h]; this
0x18002c7f8  call    ?Start@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(void)
0x18002c7fd  mov     r8, [rbx+58h]
0x18002c801  lea     rcx, aBthTelemetryda_0; "BTH_TELEMETRYDATA_PREPAIRING_RESULT"
0x18002c808  mov     edx, eax
0x18002c80a  mov     r8, [r8+30h]
0x18002c80e  call    cs:__imp_?BthProcessEventOccurrenceResultBthaddr@@YAXPEBDJ_K@Z; BthProcessEventOccurrenceResultBthaddr(char const *,long,unsigned __int64)
0x18002c815  nop     dword ptr [rax+rax+00h]
0x18002c81a  mov     rcx, rbx; this
0x18002c81d  add     rsp, 20h
0x18002c821  pop     rbx
0x18002c822  jmp     ?ResetPairingState@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState(void)
```
