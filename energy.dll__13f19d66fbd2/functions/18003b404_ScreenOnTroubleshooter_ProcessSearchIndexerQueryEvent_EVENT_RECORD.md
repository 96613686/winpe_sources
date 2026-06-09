# ScreenOnTroubleshooter::ProcessSearchIndexerQueryEvent(_EVENT_RECORD *)

- ea: `0x18003b404`
- end: `0x18003b589`
- name: `?ProcessSearchIndexerQueryEvent@ScreenOnTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `389`
- prototype: `void __fastcall(ScreenOnTroubleshooter *__hidden this, PEVENT_RECORD pEvent)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180039770`

## callees

- `0x180008740`
- `0x18000b6f0`
- `0x18001be60`
- `0x180026148`
- `0x180027f10`
- `0x18003b404`
- `0x18003bce0`
- `0x18004ca90`
- `0x180065cb4`
- `0x180066ff8`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18003b481`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18003b481`

## string_xrefs

- `0x18003b511`: `ProtocolString`
- `0x18003b4f0`: `ProtocolCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ScreenOnTroubleshooter::ProcessSearchIndexerQueryEvent(
        ScreenOnTroubleshooter *this,
        PEVENT_RECORD pEvent)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  struct ScreenOnTraceData *DataForSessionGuid; // rdi
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+40h] [rbp-9h] BYREF
  BYTE pBuffer[16]; // [rsp+50h] [rbp+7h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+17h] BYREF
  unsigned int v11; // [rsp+64h] [rbp+1Bh] BYREF
  unsigned int v12; // [rsp+68h] [rbp+1Fh] BYREF
  _QWORD v13[4]; // [rsp+70h] [rbp+27h] BYREF

  std::wstring::wstring(v13);
  *(_OWORD *)pBuffer = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ScreenOnSessionGuid";
  if ( TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 0x10u, pBuffer) )
    goto LABEL_9;
  DataForSessionGuid = ScreenOnTroubleshooter::GetDataForSessionGuid(this, (const struct _GUID *)pBuffer);
  if ( DataForSessionGuid )
  {
    if ( GetEventProperty(pEvent, L"TotalNumberOfEvents", &v10)
      || GetEventProperty(pEvent, L"MaxCursorsUsed", &v11)
      || GetEventProperty(pEvent, L"ProtocolCount", &v12)
      || (unsigned int)GetEventProperty(pEvent) )
    {
LABEL_9:
      MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v6);
      goto LABEL_13;
    }
    if ( *((_QWORD *)DataForSessionGuid + 208) == *((_QWORD *)DataForSessionGuid + 209) )
    {
      std::vector<SearchIndexerQueryEventData>::_Emplace_reallocate<SearchIndexerQueryEventData const &>(
        (char *)DataForSessionGuid + 1656,
        *((_QWORD *)DataForSessionGuid + 208),
        &v10);
    }
    else
    {
      SearchIndexerQueryEventData::SearchIndexerQueryEventData(
        *((SearchIndexerQueryEventData **)DataForSessionGuid + 208),
        (const struct SearchIndexerQueryEventData *)&v10);
      *((_QWORD *)DataForSessionGuid + 208) += 48LL;
    }
  }
LABEL_13:
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v13);
}

```

## disassembly

```asm
0x18003b404  mov     [rsp-8+arg_10], rbx
0x18003b409  mov     [rsp-8+arg_18], rdi
0x18003b40e  push    rbp
0x18003b40f  lea     rbp, [rsp-57h]
0x18003b414  sub     rsp, 0A0h
0x18003b41b  mov     rax, cs:__security_cookie
0x18003b422  xor     rax, rsp
0x18003b425  mov     [rbp+57h+var_10], rax
0x18003b429  mov     rbx, rdx
0x18003b42c  mov     rdi, rcx
0x18003b42f  lea     rcx, [rbp+57h+var_30]; void *
0x18003b433  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003b438  nop
0x18003b439  xorps   xmm0, xmm0
0x18003b43c  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18003b440  mov     [rbp+57h+var_60.Reserved], 0
0x18003b447  mov     [rbp+57h+var_60.ArrayIndex], 0FFFFFFFFh
0x18003b44e  lea     rax, aScreenonsessio_5; "ScreenOnSessionGuid"
0x18003b455  mov     [rbp+57h+var_60.PropertyName], rax
0x18003b459  lea     rax, [rbp+57h+var_50]
0x18003b45d  mov     [rsp+0A0h+pBuffer], rax; pBuffer
0x18003b462  mov     [rsp+0A0h+BufferSize], 10h; BufferSize
0x18003b46a  lea     rax, [rbp+57h+var_60]
0x18003b46e  mov     [rsp+0A0h+pPropertyData], rax; pPropertyData
0x18003b473  mov     r9d, 1; PropertyDataCount
0x18003b479  xor     r8d, r8d; pTdhContext
0x18003b47c  xor     edx, edx; TdhContextCount
0x18003b47e  mov     rcx, rbx; pEvent
0x18003b481  call    cs:__imp_TdhGetProperty
0x18003b487  test    eax, eax
0x18003b489  jz      short loc_18003B495
0x18003b48b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b490  jmp     loc_18003B55F
0x18003b495  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x18003b499  mov     rcx, rdi; this
0x18003b49c  call    ?GetDataForSessionGuid@ScreenOnTroubleshooter@@AEAAPEAUScreenOnTraceData@@AEBU_GUID@@@Z; ScreenOnTroubleshooter::GetDataForSessionGuid(_GUID const &)
0x18003b4a1  mov     rdi, rax
0x18003b4a4  test    rax, rax
0x18003b4a7  jz      loc_18003B55F
0x18003b4ad  lea     r8, [rbp+57h+var_40]; unsigned int *
0x18003b4b1  lea     rdx, aTotalnumberofe; "TotalNumberOfEvents"
0x18003b4b8  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003b4bb  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18003b4c0  test    eax, eax
0x18003b4c2  jz      short loc_18003B4CE
0x18003b4c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b4c9  jmp     loc_18003B55F
0x18003b4ce  lea     r8, [rbp+57h+var_3C]; unsigned int *
0x18003b4d2  lea     rdx, aMaxcursorsused; "MaxCursorsUsed"
0x18003b4d9  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003b4dc  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18003b4e1  test    eax, eax
0x18003b4e3  jz      short loc_18003B4EC
0x18003b4e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b4ea  jmp     short loc_18003B55F
0x18003b4ec  lea     r8, [rbp+57h+var_38]; unsigned int *
0x18003b4f0  lea     rdx, aProtocolcount_0; "ProtocolCount"
0x18003b4f7  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003b4fa  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18003b4ff  test    eax, eax
0x18003b501  jz      short loc_18003B50A
0x18003b503  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b508  jmp     short loc_18003B55F
0x18003b50a  xor     r9d, r9d
0x18003b50d  lea     r8, [rbp+57h+var_30]
0x18003b511  lea     rdx, aProtocolstring_0; "ProtocolString"
0x18003b518  mov     rcx, rbx; pEvent
0x18003b51b  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18003b520  test    eax, eax
0x18003b522  jz      short loc_18003B52B
0x18003b524  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b529  jmp     short loc_18003B55F
0x18003b52b  lea     rbx, [rdi+678h]
0x18003b532  mov     rax, [rbx+8]
0x18003b536  cmp     rax, [rbx+10h]
0x18003b53a  jz      short loc_18003B54F
0x18003b53c  lea     rdx, [rbp+57h+var_40]; struct SearchIndexerQueryEventData *
0x18003b540  mov     rcx, rax; this
0x18003b543  call    ??0SearchIndexerQueryEventData@@QEAA@AEBU0@@Z; SearchIndexerQueryEventData::SearchIndexerQueryEventData(SearchIndexerQueryEventData const &)
0x18003b548  add     qword ptr [rbx+8], 30h ; '0'
0x18003b54d  jmp     short loc_18003B55F
0x18003b54f  lea     r8, [rbp+57h+var_40]
0x18003b553  mov     rdx, rax
0x18003b556  mov     rcx, rbx
0x18003b559  call    ??$_Emplace_reallocate@AEBUSearchIndexerQueryEventData@@@?$vector@USearchIndexerQueryEventData@@V?$allocator@USearchIndexerQueryEventData@@@std@@@std@@AEAAPEAUSearchIndexerQueryEventData@@QEAU2@AEBU2@@Z; std::vector<SearchIndexerQueryEventData>::_Emplace_reallocate<SearchIndexerQueryEventData const &>(SearchIndexerQueryEventData * const,SearchIndexerQueryEventData const &)
0x18003b55e  nop
0x18003b55f  lea     rcx, [rbp+57h+var_30]; void *
0x18003b563  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003b568  mov     rcx, [rbp+57h+var_10]
0x18003b56c  xor     rcx, rsp; StackCookie
0x18003b56f  call    __security_check_cookie
0x18003b574  lea     r11, [rsp+0A0h+var_s0]
0x18003b57c  mov     rbx, [r11+20h]
0x18003b580  mov     rdi, [r11+28h]
0x18003b584  mov     rsp, r11
0x18003b587  pop     rbp
0x18003b588  retn
```
