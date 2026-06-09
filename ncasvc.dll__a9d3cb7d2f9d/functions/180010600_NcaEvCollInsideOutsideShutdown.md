# NcaEvCollInsideOutsideShutdown

- ea: `0x180010600`
- end: `0x1800106ff`
- name: `NcaEvCollInsideOutsideShutdown`
- size: `255`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010430`

## callees

- `0x180004f04`
- `0x180006544`
- `0x18000b3a8`
- `0x180010600`
- `0x1800190a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010657`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010657`

## string_xrefs

- `0x18001063d`: `EvCollInsideOutside`
- `0x1800106be`: `EvCollInsideOutside`

## pseudocode

```c
void NcaEvCollInsideOutsideShutdown()
{
  PVOID v0; // rcx
  __int64 v1; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_771a672108da301c4352a042022c0f91_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v0, (const EVENT_DESCRIPTOR *)ModuleShutdownStart, L"EvCollInsideOutside");
  SetEvent(gNcaMain);
  if ( gNcaEvCollInOut )
  {
    NcaSrcLnkdTriggerUnregisterWait(&stru_180028CF0, gNcaEvCollInOut);
    gNcaEvCollInOut = 0;
  }
  if ( qword_180028FA8 )
  {
    NcaSrcLnkdTriggerUnregisterWait(&stru_180028CF0, qword_180028FA8);
    qword_180028FA8 = 0;
  }
  NcaCriticalSectionDestroy(&stru_180028FB0);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v1, (const EVENT_DESCRIPTOR *)ModuleShutdownEnd, L"EvCollInsideOutside");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_771a672108da301c4352a042022c0f91_Traceguids);
}

```

## disassembly

```asm
0x180010600  push    rbx
0x180010602  sub     rsp, 20h
0x180010606  mov     rcx, cs:WPP_GLOBAL_Control
0x18001060d  lea     rbx, WPP_GLOBAL_Control
0x180010614  cmp     rcx, rbx
0x180010617  jz      short loc_180010634
0x180010619  test    byte ptr [rcx+1Ch], 8
0x18001061d  jz      short loc_180010634
0x18001061f  mov     rcx, [rcx+10h]
0x180010623  lea     r8, WPP_771a672108da301c4352a042022c0f91_Traceguids
0x18001062a  mov     edx, 10h
0x18001062f  call    WPP_SF_
0x180010634  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18001063b  jz      short loc_180010650
0x18001063d  lea     r8, aEvcollinsideou; "EvCollInsideOutside"
0x180010644  lea     rdx, ModuleShutdownStart
0x18001064b  call    McTemplateU0z_EventWriteTransfer
0x180010650  mov     rcx, cs:?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; hEvent
0x180010657  call    cs:__imp_SetEvent
0x18001065e  nop     dword ptr [rax+rax+00h]
0x180010663  mov     rdx, cs:?gNcaEvCollInOut@@3UNCA_EVCOLL_INOUT_COMPONENT_@@A; struct _LIST_ENTRY *
0x18001066a  test    rdx, rdx
0x18001066d  jz      short loc_180010686
0x18001066f  lea     rcx, stru_180028CF0; lpCriticalSection
0x180010676  call    NcaSrcLnkdTriggerUnregisterWait
0x18001067b  mov     cs:?gNcaEvCollInOut@@3UNCA_EVCOLL_INOUT_COMPONENT_@@A, 0; NCA_EVCOLL_INOUT_COMPONENT_ gNcaEvCollInOut
0x180010686  mov     rdx, cs:qword_180028FA8; struct _LIST_ENTRY *
0x18001068d  test    rdx, rdx
0x180010690  jz      short loc_1800106A9
0x180010692  lea     rcx, stru_180028CF0; lpCriticalSection
0x180010699  call    NcaSrcLnkdTriggerUnregisterWait
0x18001069e  mov     cs:qword_180028FA8, 0
0x1800106a9  lea     rcx, stru_180028FB0; lpCriticalSection
0x1800106b0  call    NcaCriticalSectionDestroy
0x1800106b5  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800106bc  jz      short loc_1800106D1
0x1800106be  lea     r8, aEvcollinsideou; "EvCollInsideOutside"
0x1800106c5  lea     rdx, ModuleShutdownEnd
0x1800106cc  call    McTemplateU0z_EventWriteTransfer
0x1800106d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d8  cmp     rcx, rbx
0x1800106db  jz      short loc_1800106F8
0x1800106dd  test    byte ptr [rcx+1Ch], 8
0x1800106e1  jz      short loc_1800106F8
0x1800106e3  mov     rcx, [rcx+10h]
0x1800106e7  lea     r8, WPP_771a672108da301c4352a042022c0f91_Traceguids
0x1800106ee  mov     edx, 11h
0x1800106f3  call    WPP_SF_
0x1800106f8  add     rsp, 20h
0x1800106fc  pop     rbx
0x1800106fd  retn
```
