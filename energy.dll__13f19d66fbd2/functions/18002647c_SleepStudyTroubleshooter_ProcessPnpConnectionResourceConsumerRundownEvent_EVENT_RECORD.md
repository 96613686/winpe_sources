# SleepStudyTroubleshooter::ProcessPnpConnectionResourceConsumerRundownEvent(_EVENT_RECORD *)

- ea: `0x18002647c`
- end: `0x18002662b`
- name: `?ProcessPnpConnectionResourceConsumerRundownEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `431`
- prototype: `void(SleepStudyTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180008740`
- `0x180008da0`
- `0x18001be60`
- `0x18001f44c`
- `0x18002647c`
- `0x180026634`
- `0x18003bb60`
- `0x18003bf74`
- `0x18003bf8c`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18002653b`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18002653b`

## string_xrefs

- `0x180026550`: `ResourceConsumerInstancePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SleepStudyTroubleshooter::ProcessPnpConnectionResourceConsumerRundownEvent(
        ScenarioInstanceScaffold **this,
        struct _EVENT_RECORD *a2)
{
  char *v4; // rbx
  __int128 *v5; // rdx
  unsigned __int64 v6; // [rsp+40h] [rbp+7h] BYREF
  BYTE pBuffer[8]; // [rsp+48h] [rbp+Fh] BYREF
  __int128 v8; // [rsp+50h] [rbp+17h] BYREF
  __int64 v9; // [rsp+60h] [rbp+27h]
  unsigned __int64 v10; // [rsp+68h] [rbp+2Fh]
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+70h] [rbp+37h] BYREF

  *(_QWORD *)pBuffer = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  std::wstring::_Construct_empty(&v8);
  v6 = 0;
  if ( this[4] )
  {
    if ( GetEventPropertyPtr(a2, L"ResourceConsumerPdo", &v6) )
      goto LABEL_10;
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"ConnectionId";
    if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer) || (unsigned int)GetEventProperty(a2) )
      goto LABEL_10;
    v4 = (char *)operator new(0x28u);
    pPropertyData.PropertyName = (ULONGLONG)v4;
    if ( v4 )
    {
      *(_QWORD *)v4 = v6;
      *(_OWORD *)(v4 + 8) = 0;
      *((_QWORD *)v4 + 3) = 0;
      *((_QWORD *)v4 + 4) = 0;
      v5 = &v8;
      if ( v10 > 7 )
        v5 = (__int128 *)v8;
      std::wstring::_Construct<2,unsigned short const *>(v4 + 8, v5, v9);
    }
    else
    {
      v4 = 0;
    }
    if ( ScenarioInstanceScaffold::AddMappingConnectionIdToConsumer(
           this[4],
           *(union _LARGE_INTEGER *)pBuffer,
           (struct ConnectionResourceDeviceConsumer *)v4) )
    {
LABEL_10:
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  if ( v10 > 7 )
    std::_Deallocate<16>((void *)v8, 2 * v10 + 2);
}

```

## disassembly

```asm
0x18002647c  mov     [rsp-8+arg_10], rbx
0x180026481  mov     [rsp-8+arg_18], rdi
0x180026486  push    rbp
0x180026487  lea     rbp, [rsp-57h]
0x18002648c  sub     rsp, 90h
0x180026493  mov     rax, cs:__security_cookie
0x18002649a  xor     rax, rsp
0x18002649d  mov     [rbp+57h+var_10], rax
0x1800264a1  mov     rbx, rdx
0x1800264a4  mov     rdi, rcx
0x1800264a7  mov     qword ptr [rbp+57h+var_48], 0
0x1800264af  xorps   xmm0, xmm0
0x1800264b2  movups  [rbp+57h+var_40], xmm0
0x1800264b6  mov     [rbp+57h+var_30], 0
0x1800264be  mov     [rbp+57h+var_28], 0
0x1800264c6  lea     rcx, [rbp+57h+var_40]
0x1800264ca  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800264cf  nop
0x1800264d0  mov     [rbp+57h+var_50], 0
0x1800264d8  cmp     qword ptr [rdi+20h], 0
0x1800264dd  jz      loc_1800265CC
0x1800264e3  lea     r8, [rbp+57h+var_50]; unsigned __int64 *
0x1800264e7  lea     rdx, aResourceconsum_0; "ResourceConsumerPdo"
0x1800264ee  mov     rcx, rbx; pEvent
0x1800264f1  call    ?GetEventPropertyPtr@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventPropertyPtr(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x1800264f6  test    eax, eax
0x1800264f8  jnz     loc_1800265FF
0x1800264fe  mov     [rbp+57h+var_20.Reserved], eax
0x180026501  mov     [rbp+57h+var_20.ArrayIndex], 0FFFFFFFFh
0x180026508  lea     rax, aConnectionid; "ConnectionId"
0x18002650f  mov     [rbp+57h+var_20.PropertyName], rax
0x180026513  lea     rax, [rbp+57h+var_48]
0x180026517  mov     [rsp+90h+pBuffer], rax; pBuffer
0x18002651c  mov     [rsp+90h+BufferSize], 8; BufferSize
0x180026524  lea     rax, [rbp+57h+var_20]
0x180026528  mov     [rsp+90h+pPropertyData], rax; pPropertyData
0x18002652d  mov     r9d, 1; PropertyDataCount
0x180026533  xor     r8d, r8d; pTdhContext
0x180026536  xor     edx, edx; TdhContextCount
0x180026538  mov     rcx, rbx; pEvent
0x18002653b  call    cs:__imp_TdhGetProperty
0x180026541  test    eax, eax
0x180026543  jnz     loc_1800265F7
0x180026549  xor     r9d, r9d
0x18002654c  lea     r8, [rbp+57h+var_40]
0x180026550  lea     rdx, aResourceconsum; "ResourceConsumerInstancePath"
0x180026557  mov     rcx, rbx; pEvent
0x18002655a  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18002655f  test    eax, eax
0x180026561  jnz     loc_180026606
0x180026567  lea     ecx, [rax+28h]; dwBytes
0x18002656a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002656f  mov     rbx, rax
0x180026572  mov     [rbp+57h+var_20.PropertyName], rax
0x180026576  test    rax, rax
0x180026579  jz      loc_18002660D
0x18002657f  mov     rax, [rbp+57h+var_50]
0x180026583  mov     [rbx], rax
0x180026586  lea     rcx, [rbx+8]
0x18002658a  xorps   xmm0, xmm0
0x18002658d  movups  xmmword ptr [rcx], xmm0
0x180026590  mov     qword ptr [rcx+10h], 0
0x180026598  mov     qword ptr [rcx+18h], 0
0x1800265a0  lea     rdx, [rbp+57h+var_40]
0x1800265a4  cmp     [rbp+57h+var_28], 7
0x1800265a9  cmova   rdx, qword ptr [rbp+57h+var_40]
0x1800265ae  mov     r8, [rbp+57h+var_30]
0x1800265b2  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800265b7  nop
0x1800265b8  mov     r8, rbx; struct ConnectionResourceDeviceConsumer *
0x1800265bb  mov     rdx, qword ptr [rbp+57h+var_48]; union _LARGE_INTEGER
0x1800265bf  mov     rcx, [rdi+20h]; this
0x1800265c3  call    ?AddMappingConnectionIdToConsumer@ScenarioInstanceScaffold@@QEAAKT_LARGE_INTEGER@@PEAUConnectionResourceDeviceConsumer@@@Z; ScenarioInstanceScaffold::AddMappingConnectionIdToConsumer(_LARGE_INTEGER,ConnectionResourceDeviceConsumer *)
0x1800265c8  test    eax, eax
0x1800265ca  jnz     short loc_180026611
0x1800265cc  mov     rdx, [rbp+57h+var_28]
0x1800265d0  cmp     rdx, 7
0x1800265d4  ja      short loc_180026618
0x1800265d6  mov     rcx, [rbp+57h+var_10]
0x1800265da  xor     rcx, rsp; StackCookie
0x1800265dd  call    __security_check_cookie
0x1800265e2  lea     r11, [rsp+90h+var_s0]
0x1800265ea  mov     rbx, [r11+20h]
0x1800265ee  mov     rdi, [r11+28h]
0x1800265f2  mov     rsp, r11
0x1800265f5  pop     rbp
0x1800265f6  retn
0x1800265f7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800265fc  nop
0x1800265fd  jmp     short loc_1800265CC
0x1800265ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026604  jmp     short loc_1800265CC
0x180026606  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002660b  jmp     short loc_1800265CC
0x18002660d  xor     ebx, ebx
0x18002660f  jmp     short loc_1800265B8
0x180026611  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026616  jmp     short loc_1800265CC
0x180026618  lea     rdx, ds:2[rdx*2]
0x180026620  mov     rcx, qword ptr [rbp+57h+var_40]
0x180026624  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026629  jmp     short loc_1800265D6
```
