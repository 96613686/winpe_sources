# SmsWapMsgHandler::RegisterForWNF(void)

- ea: `0x180003e90`
- end: `0x18000409b`
- name: `?RegisterForWNF@SmsWapMsgHandler@@QEAAJXZ`
- size: `523`
- prototype: `__int64 __fastcall(SmsWapMsgHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004ab4`

## callees

- `0x1800010f4`
- `0x180001a70`
- `0x180001a94`
- `0x180002554`
- `0x180003608`
- `0x180003e90`
- `0x1800049c0`

## import_xrefs

- `EventAggregation!EaCreateAggregatedEvent` at `0x180003ff0`
- `EventAggregation!EaCreateAggregatedEvent` at `0x180003ff0`

## string_xrefs

- `0x180003f1d`: `DmWapPushService`
- `0x180003f3a`: `RegistrationXml`

## pseudocode

```c
__int64 __fastcall SmsWapMsgHandler::RegisterForWNF(SmsWapMsgHandler *this)
{
  SmsWapMsgHandler *v1; // rbx
  int CurrentSIDFromToken; // eax
  void *v3; // rdi
  int AggregatedEvent; // eax
  __int64 v5; // rcx
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  __int64 *v9; // rdx
  void *Block[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v12[10]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v13[4]; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v14; // [rsp+D0h] [rbp-30h] BYREF
  int v15; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t *v16; // [rsp+E0h] [rbp-20h]
  const wchar_t *v17; // [rsp+F0h] [rbp-10h]
  int v18; // [rsp+F8h] [rbp-8h]
  const wchar_t *v19; // [rsp+100h] [rbp+0h]
  const wchar_t *v20; // [rsp+110h] [rbp+10h]
  int v21; // [rsp+118h] [rbp+18h]
  __int16 v22; // [rsp+120h] [rbp+20h]
  __int64 *v23; // [rsp+128h] [rbp+28h]

  v1 = spSmsWapMsgHandler;
  v14 = 0;
  memset_0(&v15, 0, 0x58u);
  memset(v13, 0, sizeof(v13));
  memset_0(v12, 0, 0x48u);
  Block[0] = 0;
  CurrentSIDFromToken = GetCurrentSIDFromToken(Block);
  v3 = Block[0];
  if ( CurrentSIDFromToken >= 0 )
  {
    v16 = L"DmWapPushService";
    v14 = L"RegistrationName";
    v12[7] = L"DmWapPushService";
    v17 = L"RegistrationXml";
    v15 = 2;
    v19 = L"<SmsMessageFilter Action=\"AcceptImmediately\"><FilterRule><MessageType>Wap</MessageType></FilterRule></SmsMessageFilter>";
    v18 = 2;
    v20 = L"RegistrationWnf";
    v21 = 4;
    v22 = 8;
    v23 = &WNF_ENTR_WAP_MESSAGE_FOR_DMWAPPUSHSVC_READY;
    HIDWORD(v13[1]) = 2001490878;
    LOWORD(v13[2]) = 3;
    v13[3] = &v14;
    v12[0] = v13;
    LODWORD(v13[0]) = -779750954;
    *(_QWORD *)((char *)v13 + 4) = 0x64F6878F44C2A4AFLL;
    v12[8] = Block[0];
    AggregatedEvent = EaCreateAggregatedEvent(v12, 0, &HandleNewWapMessage, 0, 0, 0, v1, 0, (char *)v1 + 152);
    v8 = AggregatedEvent;
    if ( AggregatedEvent < 0 )
    {
      if ( (unsigned int)dword_18001C048 > 2 )
      {
        LODWORD(Block[0]) = AggregatedEvent;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)&dword_1800161C4,
          v6,
          v7,
          (__int64)Block);
      }
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
      {
        v9 = PushRouterDmWapPushServiceEaCreateAggregatedEventFailed;
        goto LABEL_11;
      }
    }
    else
    {
      v5 = (unsigned int)dword_18001C048;
      if ( (unsigned int)dword_18001C048 > 4 )
      {
        LODWORD(Block[0]) = AggregatedEvent;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          dword_18001C048,
          (unsigned int)&byte_18001621F,
          v6,
          v7,
          (__int64)Block);
      }
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      {
        v9 = PushRouterDmWapPushServiceEaCreateAggregatedEventSucceeded;
LABEL_11:
        McTemplateU0d_EventWriteTransfer(v5, v9, v8);
      }
    }
  }
  operator delete(v3);
  return 0;
}

```

## disassembly

```asm
0x180003e90  mov     [rsp-8+arg_0], rbx
0x180003e95  mov     [rsp-8+arg_8], rdi
0x180003e9a  push    rbp
0x180003e9b  lea     rbp, [rsp-40h]
0x180003ea0  sub     rsp, 140h
0x180003ea7  mov     rax, cs:__security_cookie
0x180003eae  xor     rax, rsp
0x180003eb1  mov     [rbp+40h+var_10], rax
0x180003eb5  mov     rbx, cs:?spSmsWapMsgHandler@@3PEAVSmsWapMsgHandler@@EA; SmsWapMsgHandler * spSmsWapMsgHandler
0x180003ebc  lea     rcx, [rbp+40h+var_68]; void *
0x180003ec0  xor     edx, edx; Val
0x180003ec2  mov     [rbp+40h+var_70], 0
0x180003eca  lea     r8d, [rdx+58h]; Size
0x180003ece  call    memset_0
0x180003ed3  xorps   xmm0, xmm0
0x180003ed6  mov     [rbp+40h+var_90], 0
0x180003edd  xor     edx, edx; Val
0x180003edf  lea     rcx, [rsp+140h+var_E0]; void *
0x180003ee4  movups  [rbp+40h+var_8C], xmm0
0x180003ee8  movups  [rbp+40h+var_8C+0Ch], xmm0
0x180003eec  lea     r8d, [rdx+48h]; Size
0x180003ef0  call    memset_0
0x180003ef5  lea     rcx, [rsp+140h+Block]; void **
0x180003efa  mov     [rsp+140h+Block], 0
0x180003f03  call    ?GetCurrentSIDFromToken@@YAJPEAPEAX@Z; GetCurrentSIDFromToken(void * *)
0x180003f08  mov     rdi, [rsp+140h+Block]
0x180003f0d  test    eax, eax
0x180003f0f  js      loc_180004070
0x180003f15  movsd   xmm0, cs:qword_1800145DC
0x180003f1d  lea     rcx, aDmwappushservi; "DmWapPushService"
0x180003f24  lea     rax, aRegistrationna; "RegistrationName"
0x180003f2b  mov     [rbp+40h+var_60], rcx
0x180003f2f  mov     [rbp+40h+var_70], rax
0x180003f33  lea     r8, ?HandleNewWapMessage@@YAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; HandleNewWapMessage(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)
0x180003f3a  lea     rax, aRegistrationxm; "RegistrationXml"
0x180003f41  mov     [rbp+40h+var_A8], rcx
0x180003f45  mov     [rbp+40h+var_50], rax
0x180003f49  lea     rcx, [rsp+140h+var_E0]
0x180003f4e  lea     rax, aSmsmessagefilt; "<SmsMessageFilter Action=\"AcceptImmedi"...
0x180003f55  mov     [rbp+40h+var_68], 2
0x180003f5c  mov     [rbp+40h+var_40], rax
0x180003f60  xor     r9d, r9d
0x180003f63  lea     rax, aRegistrationwn; "RegistrationWnf"
0x180003f6a  mov     [rbp+40h+var_48], 2
0x180003f71  mov     [rbp+40h+var_30], rax
0x180003f75  xor     edx, edx
0x180003f77  mov     eax, 8
0x180003f7c  mov     [rbp+40h+var_28], 4
0x180003f83  mov     [rbp+40h+var_20], ax
0x180003f87  lea     rax, WNF_ENTR_WAP_MESSAGE_FOR_DMWAPPUSHSVC_READY
0x180003f8e  mov     [rbp+40h+var_18], rax
0x180003f92  mov     eax, cs:dword_1800145E4
0x180003f98  mov     dword ptr [rbp+40h+var_8C+8], eax
0x180003f9b  mov     eax, 3
0x180003fa0  mov     word ptr [rbp+40h+var_8C+0Ch], ax
0x180003fa4  lea     rax, [rbp+40h+var_70]
0x180003fa8  mov     [rbp+40h+var_78], rax
0x180003fac  lea     rax, [rbp+40h+var_90]
0x180003fb0  mov     [rsp+140h+var_E0], rax
0x180003fb5  lea     rax, [rbx+98h]
0x180003fbc  mov     [rsp+140h+var_100], rax
0x180003fc1  mov     [rsp+140h+var_108], 0
0x180003fc9  mov     [rsp+140h+var_110], rbx
0x180003fce  mov     [rsp+140h+var_118], 0
0x180003fd7  mov     [rsp+140h+var_120], 0
0x180003fe0  mov     [rbp+40h+var_90], 0D185F1D6h
0x180003fe7  movsd   qword ptr [rbp+40h+var_8C], xmm0
0x180003fec  mov     [rbp+40h+var_A0], rdi
0x180003ff0  call    cs:__imp_EaCreateAggregatedEvent
0x180003ff6  mov     ebx, eax
0x180003ff8  test    eax, eax
0x180003ffa  js      short loc_180004033
0x180003ffc  mov     ecx, cs:dword_18001C048
0x180004002  cmp     ecx, 4
0x180004005  jbe     short loc_180004021
0x180004007  mov     dword ptr [rsp+140h+Block], eax
0x18000400b  lea     rdx, byte_18001621F
0x180004012  lea     rax, [rsp+140h+Block]
0x180004017  mov     [rsp+140h+var_120], rax
0x18000401c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180004021  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180004028  jz      short loc_180004070
0x18000402a  lea     rdx, PushRouterDmWapPushServiceEaCreateAggregatedEventSucceeded
0x180004031  jmp     short loc_180004068
0x180004033  mov     eax, cs:dword_18001C048
0x180004039  cmp     eax, 2
0x18000403c  jbe     short loc_180004058
0x18000403e  lea     rax, [rsp+140h+Block]
0x180004043  mov     dword ptr [rsp+140h+Block], ebx
0x180004047  lea     rdx, dword_1800161C4
0x18000404e  mov     [rsp+140h+var_120], rax
0x180004053  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180004058  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000405f  jz      short loc_180004070
0x180004061  lea     rdx, PushRouterDmWapPushServiceEaCreateAggregatedEventFailed
0x180004068  mov     r8d, ebx
0x18000406b  call    McTemplateU0d_EventWriteTransfer
0x180004070  mov     rcx, rdi; Block
0x180004073  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004078  xor     eax, eax
0x18000407a  mov     rcx, [rbp+40h+var_10]
0x18000407e  xor     rcx, rsp; StackCookie
0x180004081  call    __security_check_cookie
0x180004086  lea     r11, [rsp+140h+var_s0]
0x18000408e  mov     rbx, [r11+10h]
0x180004092  mov     rdi, [r11+18h]
0x180004096  mov     rsp, r11
0x180004099  pop     rbp
0x18000409a  retn
```
