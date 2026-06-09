# SleepStudyTroubleshooter::ProcessSpmScenarioStartEvent(_EVENT_RECORD *)

- ea: `0x18001872c`
- end: `0x180018a57`
- name: `?ProcessSpmScenarioStartEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `811`
- prototype: `void __fastcall(SleepStudyTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180008740`
- `0x180018674`
- `0x18001872c`
- `0x180027e10`
- `0x180027f10`
- `0x18003362c`
- `0x180036324`
- `0x18004ca90`
- `0x180096010`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800187c3`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001880e`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001885d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800188c3`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800187c3`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001880e`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001885d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800188c3`

## string_xrefs

- `0x180018968`: `LidOpenState`

## pseudocode

```c
void __fastcall SleepStudyTroubleshooter::ProcessSpmScenarioStartEvent(
        SleepStudyTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  struct ScenarioInstanceData *CurrentScenarioInstanceData; // rdi
  bool v5; // zf
  union _LARGE_INTEGER v6; // rbx
  __int64 v7; // rcx
  __int64 Id; // r8
  void (__fastcall *v9)(__int64, PROPERTY_DATA_DESCRIPTOR *, __int64); // rax
  unsigned __int8 v10; // [rsp+40h] [rbp-19h] BYREF
  BYTE v11[3]; // [rsp+41h] [rbp-18h] BYREF
  BYTE v12[4]; // [rsp+44h] [rbp-15h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v14; // [rsp+4Ch] [rbp-Dh] BYREF
  BYTE v15[8]; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int64 v16; // [rsp+58h] [rbp-1h] BYREF
  union _LARGE_INTEGER v17; // [rsp+60h] [rbp+7h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+70h] [rbp+17h] BYREF
  BYTE pBuffer[16]; // [rsp+80h] [rbp+27h] BYREF

  v10 = 3;
  *(_DWORD *)v12 = 0;
  v14 = 0;
  pPropertyData.PropertyName = (ULONGLONG)L"ScenarioGuid";
  *(_DWORD *)v15 = 0;
  v13 = 0;
  v17.QuadPart = 0;
  v11[0] = 0;
  v16 = 0;
  *(_OWORD *)pBuffer = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 0x10u, pBuffer) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return;
  }
  pPropertyData.Reserved = 0;
  pPropertyData.PropertyName = (ULONGLONG)L"ScenarioInstanceId";
  pPropertyData.ArrayIndex = -1;
  if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 1u, v11) )
    goto LABEL_15;
  pPropertyData.Reserved = 0;
  pPropertyData.PropertyName = (ULONGLONG)L"CsEnterReason";
  pPropertyData.ArrayIndex = -1;
  if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v12) )
    goto LABEL_15;
  if ( !*((_QWORD *)this + 4) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0 )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.PropertyName = (ULONGLONG)L"BatteryRemainingCapacityOnEnter";
    pPropertyData.ArrayIndex = -1;
    if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v15)
      || GetEventProperty(a2, L"BatteryFullChargeCapacityOnEnter", &v14)
      || GetEventProperty(a2, L"ScenarioInstanceIdV2", &v16)
      || GetEventProperty(a2, L"BootId", &v13)
      || GetEventProperty(a2, L"CurrentSystemTime", &v17) )
    {
LABEL_15:
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return;
    }
    if ( a2->EventHeader.EventDescriptor.Version && GetEventProperty(a2, L"LidOpenState", &v10) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      CurrentScenarioInstanceData = SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(this);
      *(_OWORD *)CurrentScenarioInstanceData = *(_OWORD *)pBuffer;
      *((_QWORD *)CurrentScenarioInstanceData + 2) = v16;
      *((_DWORD *)CurrentScenarioInstanceData + 20) = *(_DWORD *)v12;
      v5 = (*((_BYTE *)CurrentScenarioInstanceData + 1708) & 4) == 0;
      *((_QWORD *)CurrentScenarioInstanceData + 23) = v16;
      *((_DWORD *)CurrentScenarioInstanceData + 48) = v13;
      v6 = v17;
      if ( !v5 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      *((_DWORD *)CurrentScenarioInstanceData + 427) |= 4u;
      *((union _LARGE_INTEGER *)CurrentScenarioInstanceData + 175) = v6;
      *((_QWORD *)CurrentScenarioInstanceData + 4) = a2->EventHeader.TimeStamp.QuadPart;
      *((_DWORD *)CurrentScenarioInstanceData + 70) = v10;
      *((_DWORD *)CurrentScenarioInstanceData + 53) = v14;
      *((_DWORD *)CurrentScenarioInstanceData + 54) = *(_DWORD *)v15;
      if ( !*((_QWORD *)CurrentScenarioInstanceData + 168) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v7 = *((_QWORD *)CurrentScenarioInstanceData + 168);
      if ( v7 )
      {
        Id = a2->EventHeader.EventDescriptor.Id;
        v9 = *(void (__fastcall **)(__int64, PROPERTY_DATA_DESCRIPTOR *, __int64))(*(_QWORD *)v7 + 8LL);
        pPropertyData = (PROPERTY_DATA_DESCRIPTOR)a2->EventHeader.ProviderId;
        v9(v7, &pPropertyData, Id);
      }
    }
  }
}

```

## disassembly

```asm
0x18001872c  mov     [rsp-8+arg_10], rbx
0x180018731  mov     [rsp-8+arg_18], rsi
0x180018736  push    rbp
0x180018737  push    rdi
0x180018738  push    r14
0x18001873a  lea     rbp, [rsp-47h]
0x18001873f  sub     rsp, 0A0h
0x180018746  mov     rax, cs:__security_cookie
0x18001874d  xor     rax, rsp
0x180018750  mov     [rbp+57h+var_20], rax
0x180018754  xor     r14d, r14d
0x180018757  mov     [rbp+57h+var_70], 3
0x18001875b  mov     rsi, rdx
0x18001875e  mov     dword ptr [rbp+57h+var_6C], r14d
0x180018762  lea     rax, aScenarioguid; "ScenarioGuid"
0x180018769  mov     [rbp+57h+var_64], r14d
0x18001876d  mov     [rbp+57h+var_40.PropertyName], rax
0x180018771  mov     rbx, rcx
0x180018774  lea     rax, [rbp+57h+var_30]
0x180018778  mov     dword ptr [rbp+57h+var_60], r14d
0x18001877c  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x180018781  lea     edi, [r14+1]
0x180018785  lea     rax, [rbp+57h+var_40]
0x180018789  mov     [rsp+0B0h+BufferSize], 10h; BufferSize
0x180018791  xorps   xmm0, xmm0
0x180018794  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x180018799  mov     r9d, edi; PropertyDataCount
0x18001879c  mov     [rbp+57h+var_68], r14d
0x1800187a0  xor     r8d, r8d; pTdhContext
0x1800187a3  mov     qword ptr [rbp+57h+var_50], r14
0x1800187a7  xor     edx, edx; TdhContextCount
0x1800187a9  mov     [rbp+57h+var_6F], r14b
0x1800187ad  mov     rcx, rsi; pEvent
0x1800187b0  mov     [rbp+57h+var_58], r14
0x1800187b4  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x1800187b8  mov     [rbp+57h+var_40.Reserved], r14d
0x1800187bc  mov     [rbp+57h+var_40.ArrayIndex], 0FFFFFFFFh
0x1800187c3  call    cs:__imp_TdhGetProperty
0x1800187c9  test    eax, eax
0x1800187cb  jz      short loc_1800187D7
0x1800187cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800187d2  jmp     loc_180018A33
0x1800187d7  lea     rax, aScenarioinstan_0; "ScenarioInstanceId"
0x1800187de  mov     [rbp+57h+var_40.Reserved], r14d
0x1800187e2  mov     [rbp+57h+var_40.PropertyName], rax
0x1800187e6  mov     r9d, edi; PropertyDataCount
0x1800187e9  lea     rax, [rbp+57h+var_6F]
0x1800187ed  mov     [rbp+57h+var_40.ArrayIndex], 0FFFFFFFFh
0x1800187f4  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x1800187f9  xor     r8d, r8d; pTdhContext
0x1800187fc  lea     rax, [rbp+57h+var_40]
0x180018800  mov     [rsp+0B0h+BufferSize], edi; BufferSize
0x180018804  xor     edx, edx; TdhContextCount
0x180018806  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001880b  mov     rcx, rsi; pEvent
0x18001880e  call    cs:__imp_TdhGetProperty
0x180018814  test    eax, eax
0x180018816  jz      short loc_180018822
0x180018818  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001881d  jmp     loc_180018A33
0x180018822  lea     rax, aCsenterreason; "CsEnterReason"
0x180018829  mov     [rbp+57h+var_40.Reserved], r14d
0x18001882d  mov     [rbp+57h+var_40.PropertyName], rax
0x180018831  mov     r9d, edi; PropertyDataCount
0x180018834  lea     rax, [rbp+57h+var_6C]
0x180018838  mov     [rbp+57h+var_40.ArrayIndex], 0FFFFFFFFh
0x18001883f  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x180018844  xor     r8d, r8d; pTdhContext
0x180018847  lea     rax, [rbp+57h+var_40]
0x18001884b  mov     [rsp+0B0h+BufferSize], 4; BufferSize
0x180018853  xor     edx, edx; TdhContextCount
0x180018855  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001885a  mov     rcx, rsi; pEvent
0x18001885d  call    cs:__imp_TdhGetProperty
0x180018863  test    eax, eax
0x180018865  jz      short loc_180018871
0x180018867  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001886c  jmp     loc_180018A33
0x180018871  cmp     [rbx+20h], r14
0x180018875  jz      short loc_180018888
0x180018877  mov     rax, [rbx+18h]
0x18001887b  test    byte ptr [rax+188h], 20h
0x180018882  jz      loc_180018A33
0x180018888  lea     rax, aBatteryremaini_2; "BatteryRemainingCapacityOnEnter"
0x18001888f  mov     [rbp+57h+var_40.Reserved], r14d
0x180018893  mov     [rbp+57h+var_40.PropertyName], rax
0x180018897  mov     r9d, edi; PropertyDataCount
0x18001889a  lea     rax, [rbp+57h+var_60]
0x18001889e  mov     [rbp+57h+var_40.ArrayIndex], 0FFFFFFFFh
0x1800188a5  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x1800188aa  xor     r8d, r8d; pTdhContext
0x1800188ad  lea     rax, [rbp+57h+var_40]
0x1800188b1  mov     [rsp+0B0h+BufferSize], 4; BufferSize
0x1800188b9  xor     edx, edx; TdhContextCount
0x1800188bb  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x1800188c0  mov     rcx, rsi; pEvent
0x1800188c3  call    cs:__imp_TdhGetProperty
0x1800188c9  test    eax, eax
0x1800188cb  jz      short loc_1800188D7
0x1800188cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800188d2  jmp     loc_180018A33
0x1800188d7  lea     r8, [rbp+57h+var_64]; unsigned int *
0x1800188db  mov     rcx, rsi; struct _EVENT_RECORD *
0x1800188de  lea     rdx, aBatteryfullcha; "BatteryFullChargeCapacityOnEnter"
0x1800188e5  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800188ea  test    eax, eax
0x1800188ec  jz      short loc_1800188F8
0x1800188ee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800188f3  jmp     loc_180018A33
0x1800188f8  lea     r8, [rbp+57h+var_58]; unsigned __int64 *
0x1800188fc  mov     rcx, rsi; struct _EVENT_RECORD *
0x1800188ff  lea     rdx, aScenarioinstan_2; "ScenarioInstanceIdV2"
0x180018906  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18001890b  test    eax, eax
0x18001890d  jz      short loc_180018919
0x18001890f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018914  jmp     loc_180018A33
0x180018919  lea     r8, [rbp+57h+var_68]; unsigned int *
0x18001891d  mov     rcx, rsi; struct _EVENT_RECORD *
0x180018920  lea     rdx, aBootid; "BootId"
0x180018927  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18001892c  test    eax, eax
0x18001892e  jz      short loc_18001893A
0x180018930  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018935  jmp     loc_180018A33
0x18001893a  lea     r8, [rbp+57h+var_50]; union _LARGE_INTEGER *
0x18001893e  mov     rcx, rsi; struct _EVENT_RECORD *
0x180018941  lea     rdx, aCurrentsystemt; "CurrentSystemTime"
0x180018948  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAT_LARGE_INTEGER@@@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,_LARGE_INTEGER &)
0x18001894d  test    eax, eax
0x18001894f  jz      short loc_18001895B
0x180018951  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018956  jmp     loc_180018A33
0x18001895b  cmp     [rsi+2Ah], dil
0x18001895f  jb      short loc_180018982
0x180018961  lea     r8, [rbp+57h+var_70]; unsigned __int8 *
0x180018965  mov     rcx, rsi; struct _EVENT_RECORD *
0x180018968  lea     rdx, aLidopenstate; "LidOpenState"
0x18001896f  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAE@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,uchar &)
0x180018974  test    eax, eax
0x180018976  jz      short loc_180018982
0x180018978  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001897d  jmp     loc_180018A33
0x180018982  mov     rcx, rbx; this
0x180018985  call    ?GetCurrentScenarioInstanceData@SleepStudyTroubleshooter@@AEAAPEAUScenarioInstanceData@@XZ; SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(void)
0x18001898a  movups  xmm0, xmmword ptr [rbp+57h+var_30]
0x18001898e  mov     rdi, rax
0x180018991  movdqu  xmmword ptr [rax], xmm0
0x180018995  mov     rcx, [rbp+57h+var_58]
0x180018999  mov     [rax+10h], rcx
0x18001899d  mov     ecx, dword ptr [rbp+57h+var_6C]
0x1800189a0  mov     [rax+50h], ecx
0x1800189a3  test    byte ptr [rax+6ACh], 4
0x1800189aa  mov     rcx, [rbp+57h+var_58]
0x1800189ae  mov     [rax+0B8h], rcx
0x1800189b5  mov     ecx, [rbp+57h+var_68]
0x1800189b8  mov     [rax+0C0h], ecx
0x1800189be  mov     rbx, qword ptr [rbp+57h+var_50]
0x1800189c2  jz      short loc_1800189C9
0x1800189c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800189c9  or      dword ptr [rdi+6ACh], 4
0x1800189d0  mov     [rdi+578h], rbx
0x1800189d7  mov     rax, [rsi+10h]
0x1800189db  mov     [rdi+20h], rax
0x1800189df  movzx   eax, [rbp+57h+var_70]
0x1800189e3  mov     [rdi+118h], eax
0x1800189e9  mov     eax, [rbp+57h+var_64]
0x1800189ec  mov     [rdi+0D4h], eax
0x1800189f2  mov     eax, dword ptr [rbp+57h+var_60]
0x1800189f5  mov     [rdi+0D8h], eax
0x1800189fb  cmp     [rdi+540h], r14
0x180018a02  jnz     short loc_180018A09
0x180018a04  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018a09  mov     rcx, [rdi+540h]
0x180018a10  test    rcx, rcx
0x180018a13  jz      short loc_180018A33
0x180018a15  mov     rax, [rcx]
0x180018a18  lea     rdx, [rbp+57h+var_40]
0x180018a1c  movups  xmm0, xmmword ptr [rsi+18h]
0x180018a20  movzx   r8d, word ptr [rsi+28h]
0x180018a25  mov     rax, [rax+8]
0x180018a29  movdqu  xmmword ptr [rbp+57h+var_40.PropertyName], xmm0
0x180018a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a33  mov     rcx, [rbp+57h+var_20]
0x180018a37  xor     rcx, rsp; StackCookie
0x180018a3a  call    __security_check_cookie
0x180018a3f  lea     r11, [rsp+0B0h+var_10]
0x180018a47  mov     rbx, [r11+30h]
0x180018a4b  mov     rsi, [r11+38h]
0x180018a4f  mov     rsp, r11
0x180018a52  pop     r14
0x180018a54  pop     rdi
0x180018a55  pop     rbp
0x180018a56  retn
```
