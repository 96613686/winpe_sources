# SleepStudyTroubleshooter::ProcessDeviceVerboseRundownEvent(_EVENT_RECORD *)

- ea: `0x18003a404`
- end: `0x18003a808`
- name: `?ProcessDeviceVerboseRundownEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `1028`
- prototype: `void __fastcall(SleepStudyTroubleshooter *__hidden this, PEVENT_RECORD pEvent)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180008da0`
- `0x18000b6f0`
- `0x18000cd7c`
- `0x1800161c4`
- `0x180018674`
- `0x18001be60`
- `0x18001c8cc`
- `0x18001e218`
- `0x18001f2b4`
- `0x180021080`
- `0x180027e10`
- `0x180027f10`
- `0x18002b5e8`
- `0x180033690`
- `0x18003a404`
- `0x18003bce0`
- `0x18004ca90`
- `0x1800816f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003a78a`
- `ntdll!RtlInitUnicodeString` at `0x18003a78a`
- `ext-ms-win-sleepstudy-um-l1-1-1!SleepstudyHelperCreateGuidFromInstancePath` at `0x18003a799`
- `ext-ms-win-sleepstudy-um-l1-1-1!SleepstudyHelperCreateGuidFromInstancePath` at `0x18003a799`

## string_xrefs

- `0x18003a53c`: `InstancePath`
- `0x18003a55a`: `ServiceName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SleepStudyTroubleshooter::ProcessDeviceVerboseRundownEvent(
        SleepStudyTroubleshooter *this,
        PEVENT_RECORD pEvent)
{
  char *v4; // r14
  __int64 v5; // rbx
  __int64 v6; // rax
  FxDeviceData *v7; // rdi
  FxDeviceData *v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v10; // r9
  __int64 i; // r8
  __int64 v12; // rbx
  __int64 v13; // rax
  const WCHAR *v14; // rdx
  unsigned __int64 v15; // rbx
  unsigned int v16; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v27[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v28[4]; // [rsp+E0h] [rbp-20h] BYREF

  std::wstring::wstring(v28);
  std::wstring::wstring(SourceString);
  v26 = 0;
  DestinationString = 0;
  v16 = 0;
  v20 = 0;
  std::wstring::wstring(v27);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v4 = (char *)this + 24;
  if ( !*((_QWORD *)this + 4) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)v4 + 392LL) & 0x20) == 0 )
      goto LABEL_34;
    SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(this);
  }
  if ( (!pEvent->EventHeader.EventDescriptor.Version
     || !GetEventProperty(pEvent, L"ScenarioInstanceId", &v20)
     && ((*(_BYTE *)(*(_QWORD *)v4 + 392LL) & 0x20) != 0 || *(_QWORD *)(**((_QWORD **)this + 4) + 184LL) == v20))
    && !GetEventProperty(pEvent, L"DeviceNode", &v17)
    && !(unsigned int)GetEventProperty(pEvent)
    && !(unsigned int)GetEventProperty(pEvent)
    && !(unsigned int)GetEventProperty(pEvent)
    && !GetEventProperty(pEvent, L"PlatformStateDependents", &v16)
    && !GetEventProperty(pEvent, L"Pdo", &v19)
    && !GetEventProperty(pEvent, L"ParentDeviceNode", &v21)
    && !GetEventProperty(pEvent, L"Flags", &v18) )
  {
    if ( v16 )
      *(_BYTE *)(**((_QWORD **)this + 4) + 236LL) = 1;
    v5 = *((_QWORD *)this + 4);
    v6 = std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::find(
           v5 + 8,
           v22,
           &v17);
    if ( *(_QWORD *)v6 == *(_QWORD *)(v5 + 8) )
    {
      v8 = (FxDeviceData *)operator new(0x2F8u);
      v22[0] = v8;
      if ( v8 )
        v7 = FxDeviceData::FxDeviceData(v8);
      else
        v7 = 0;
      *(_QWORD *)(*(_QWORD *)std::map<unsigned __int64,FxDeviceData *>::_Try_emplace<unsigned __int64 const &,>(
                               *((_QWORD *)this + 4) + 8LL,
                               v22,
                               &v17)
                + 40LL) = v7;
    }
    else
    {
      v7 = *(FxDeviceData **)(*(_QWORD *)v6 + 40LL);
    }
    if ( !*((_BYTE *)v7 + 756) )
    {
      std::wstring::operator=((char *)v7 + 8, v28);
      std::wstring::operator=((char *)v7 + 664, (char *)v7 + 8);
      std::wstring::operator=((char *)v7 + 600, SourceString);
      *((_QWORD *)v7 + 73) = v19;
      *((_QWORD *)v7 + 72) = v17;
      *((_QWORD *)v7 + 74) = v21;
      std::wstring::operator=((char *)v7 + 632, v27);
      *((_DWORD *)v7 + 180) = v16 != 0;
      *((_DWORD *)v7 + 188) = v18;
      *((_BYTE *)v7 + 756) = 1;
      if ( (*(_BYTE *)(*(_QWORD *)v4 + 392LL) & 8) != 0 )
        FxDeviceData::SetFriendlyName(v7, (char *)v7 + 600);
      v9 = v17;
      *(_QWORD *)(*(_QWORD *)std::map<unsigned __int64,unsigned __int64>::_Try_emplace<unsigned __int64 const &,>(
                               *((_QWORD *)this + 4) + 24LL,
                               v22,
                               &v19)
                + 40LL) = v9;
      v10 = *((_QWORD *)v7 + 88);
      for ( i = *((_QWORD *)v7 + 87); i != v10; i += 8 )
        *(_QWORD *)(*(_QWORD *)i + 576LL) = v19;
      v12 = *((_QWORD *)this + 4);
      v13 = std::wstring::wstring((__int64)v24, (_QWORD *)v7 + 83);
      DevicePowerRequirements::AddFxDeviceRegistrant(v12 + 168, v17, v13);
      v14 = (const WCHAR *)SourceString;
      if ( SourceString[3] > (PCWSTR)7 )
        v14 = SourceString[0];
      RtlInitUnicodeString(&DestinationString, v14);
      if ( (int)SleepstudyHelperCreateGuidFromInstancePath(&DestinationString, &v26) >= 0 )
      {
        v15 = v19;
        *(_QWORD *)(*(_QWORD *)std::map<_GUID const,unsigned __int64,GuidCompare,std::allocator<std::pair<_GUID const,unsigned __int64>>>::_Try_emplace<_GUID const &,>(
                                 (__int64 *)(*((_QWORD *)this + 4) + 320LL),
                                 (__int64)v22,
                                 &v26)
                  + 48LL) = v15;
      }
    }
  }
LABEL_34:
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v27);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(SourceString);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v28);
}

```

## disassembly

```asm
0x18003a404  mov     [rsp-8+arg_10], rbx
0x18003a409  push    rbp
0x18003a40a  push    rsi
0x18003a40b  push    rdi
0x18003a40c  push    r14
0x18003a40e  push    r15
0x18003a410  lea     rbp, [rsp-10h]
0x18003a415  sub     rsp, 110h
0x18003a41c  mov     rax, cs:__security_cookie
0x18003a423  xor     rax, rsp
0x18003a426  mov     [rbp+30h+var_30], rax
0x18003a42a  mov     rbx, rdx
0x18003a42d  mov     rsi, rcx
0x18003a430  lea     rcx, [rbp+30h+var_50]; void *
0x18003a434  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a439  nop
0x18003a43a  lea     rcx, [rbp+30h+SourceString]; void *
0x18003a43e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a443  nop
0x18003a444  xorps   xmm0, xmm0
0x18003a447  movups  [rbp+30h+var_80], xmm0
0x18003a44b  xorps   xmm1, xmm1
0x18003a44e  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x18003a453  mov     [rsp+130h+var_110], 0
0x18003a45b  mov     [rsp+130h+var_F0], 0
0x18003a464  lea     rcx, [rbp+30h+var_70]; void *
0x18003a468  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a46d  nop
0x18003a46e  mov     [rsp+130h+var_108], 0
0x18003a477  mov     [rsp+130h+var_100], 0
0x18003a47f  mov     [rsp+130h+var_F8], 0
0x18003a488  mov     [rsp+130h+var_E8], 0
0x18003a491  lea     r14, [rsi+18h]
0x18003a495  cmp     qword ptr [rsi+20h], 0
0x18003a49a  jnz     short loc_18003A4B4
0x18003a49c  mov     rax, [r14]
0x18003a49f  test    byte ptr [rax+188h], 20h
0x18003a4a6  jz      loc_18003A7C8
0x18003a4ac  mov     rcx, rsi; this
0x18003a4af  call    ?GetCurrentScenarioInstanceData@SleepStudyTroubleshooter@@AEAAPEAUScenarioInstanceData@@XZ; SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(void)
0x18003a4b4  cmp     byte ptr [rbx+2Ah], 1
0x18003a4b8  jb      short loc_18003A4FB
0x18003a4ba  lea     r8, [rsp+130h+var_F0]; unsigned __int64 *
0x18003a4bf  lea     rdx, aScenarioinstan_0; "ScenarioInstanceId"
0x18003a4c6  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003a4c9  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18003a4ce  test    eax, eax
0x18003a4d0  jnz     loc_18003A7C8
0x18003a4d6  mov     rax, [r14]
0x18003a4d9  test    byte ptr [rax+188h], 20h
0x18003a4e0  jnz     short loc_18003A4FB
0x18003a4e2  mov     rax, [rsi+20h]
0x18003a4e6  mov     rcx, [rax]
0x18003a4e9  mov     rax, [rsp+130h+var_F0]
0x18003a4ee  cmp     [rcx+0B8h], rax
0x18003a4f5  jnz     loc_18003A7C8
0x18003a4fb  lea     r8, [rsp+130h+var_108]; unsigned __int64 *
0x18003a500  lea     rdx, aDevicenode; "DeviceNode"
0x18003a507  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003a50a  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18003a50f  test    eax, eax
0x18003a511  jnz     loc_18003A7C8
0x18003a517  xor     r9d, r9d
0x18003a51a  lea     r8, [rbp+30h+var_50]
0x18003a51e  lea     rdx, aDeviceid; "DeviceId"
0x18003a525  mov     rcx, rbx; pEvent
0x18003a528  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18003a52d  test    eax, eax
0x18003a52f  jnz     loc_18003A7C8
0x18003a535  xor     r9d, r9d
0x18003a538  lea     r8, [rbp+30h+SourceString]
0x18003a53c  lea     rdx, aInstancepath; "InstancePath"
0x18003a543  mov     rcx, rbx; pEvent
0x18003a546  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18003a54b  test    eax, eax
0x18003a54d  jnz     loc_18003A7C8
0x18003a553  xor     r9d, r9d
0x18003a556  lea     r8, [rbp+30h+var_70]
0x18003a55a  lea     rdx, aServicename; "ServiceName"
0x18003a561  mov     rcx, rbx; pEvent
0x18003a564  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18003a569  test    eax, eax
0x18003a56b  jnz     loc_18003A7C8
0x18003a571  lea     r8, [rsp+130h+var_110]; unsigned int *
0x18003a576  lea     rdx, aPlatformstated_1; "PlatformStateDependents"
0x18003a57d  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003a580  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18003a585  test    eax, eax
0x18003a587  jnz     loc_18003A7C8
0x18003a58d  lea     r8, [rsp+130h+var_F8]; unsigned __int64 *
0x18003a592  lea     rdx, aPdo; "Pdo"
0x18003a599  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003a59c  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18003a5a1  test    eax, eax
0x18003a5a3  jnz     loc_18003A7C8
0x18003a5a9  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x18003a5ae  lea     rdx, aParentdeviceno; "ParentDeviceNode"
0x18003a5b5  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003a5b8  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18003a5bd  test    eax, eax
0x18003a5bf  jnz     loc_18003A7C8
0x18003a5c5  lea     r8, [rsp+130h+var_100]; unsigned int *
0x18003a5ca  lea     rdx, aFlags; "Flags"
0x18003a5d1  mov     rcx, rbx; struct _EVENT_RECORD *
0x18003a5d4  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18003a5d9  test    eax, eax
0x18003a5db  jnz     loc_18003A7C8
0x18003a5e1  cmp     [rsp+130h+var_110], eax
0x18003a5e5  jz      short loc_18003A5F5
0x18003a5e7  mov     rax, [rsi+20h]
0x18003a5eb  mov     rcx, [rax]
0x18003a5ee  mov     byte ptr [rcx+0ECh], 1
0x18003a5f5  mov     rbx, [rsi+20h]
0x18003a5f9  lea     r8, [rsp+130h+var_108]
0x18003a5fe  lea     rdx, [rsp+130h+var_E0]
0x18003a603  lea     rcx, [rbx+8]
0x18003a607  call    ?find@?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_K_K@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::find(unsigned __int64 const &)
0x18003a60c  mov     rdi, [rax]
0x18003a60f  cmp     rdi, [rbx+8]
0x18003a613  jz      short loc_18003A61B
0x18003a615  mov     rdi, [rdi+28h]
0x18003a619  jmp     short loc_18003A65C
0x18003a61b  mov     ecx, 2F8h; dwBytes
0x18003a620  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a625  mov     [rsp+130h+var_E0], rax
0x18003a62a  test    rax, rax
0x18003a62d  jz      short loc_18003A63C
0x18003a62f  mov     rcx, rax; this
0x18003a632  call    ??0FxDeviceData@@QEAA@XZ; FxDeviceData::FxDeviceData(void)
0x18003a637  mov     rdi, rax
0x18003a63a  jmp     short loc_18003A63E
0x18003a63c  xor     edi, edi
0x18003a63e  mov     rcx, [rsi+20h]
0x18003a642  add     rcx, 8
0x18003a646  lea     r8, [rsp+130h+var_108]
0x18003a64b  lea     rdx, [rsp+130h+var_E0]
0x18003a650  call    ??$_Try_emplace@AEB_K$$V@?$map@_KPEAUFxDeviceData@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAUFxDeviceData@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAUFxDeviceData@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,FxDeviceData *>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18003a655  mov     rcx, [rax]
0x18003a658  mov     [rcx+28h], rdi
0x18003a65c  cmp     byte ptr [rdi+2F4h], 0
0x18003a663  jnz     loc_18003A7C8
0x18003a669  lea     rdx, [rbp+30h+var_50]
0x18003a66d  lea     rcx, [rdi+8]
0x18003a671  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003a676  lea     r15, [rdi+298h]
0x18003a67d  lea     rdx, [rdi+8]
0x18003a681  mov     rcx, r15
0x18003a684  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003a689  lea     rbx, [rdi+258h]
0x18003a690  lea     rdx, [rbp+30h+SourceString]
0x18003a694  mov     rcx, rbx
0x18003a697  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003a69c  mov     rax, [rsp+130h+var_F8]
0x18003a6a1  mov     [rdi+248h], rax
0x18003a6a8  mov     rax, [rsp+130h+var_108]
0x18003a6ad  mov     [rdi+240h], rax
0x18003a6b4  mov     rax, [rsp+130h+var_E8]
0x18003a6b9  mov     [rdi+250h], rax
0x18003a6c0  lea     rcx, [rdi+278h]
0x18003a6c7  lea     rdx, [rbp+30h+var_70]
0x18003a6cb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003a6d0  xor     eax, eax
0x18003a6d2  cmp     [rsp+130h+var_110], eax
0x18003a6d6  setnz   al
0x18003a6d9  mov     [rdi+2D0h], eax
0x18003a6df  mov     eax, [rsp+130h+var_100]
0x18003a6e3  mov     [rdi+2F0h], eax
0x18003a6e9  mov     byte ptr [rdi+2F4h], 1
0x18003a6f0  mov     rax, [r14]
0x18003a6f3  test    byte ptr [rax+188h], 8
0x18003a6fa  jz      short loc_18003A707
0x18003a6fc  mov     rdx, rbx
0x18003a6ff  mov     rcx, rdi
0x18003a702  call    ?SetFriendlyName@FxDeviceData@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FxDeviceData::SetFriendlyName(std::wstring const &)
0x18003a707  mov     rbx, [rsp+130h+var_108]
0x18003a70c  mov     rcx, [rsi+20h]
0x18003a710  add     rcx, 18h
0x18003a714  lea     r8, [rsp+130h+var_F8]
0x18003a719  lea     rdx, [rsp+130h+var_E0]
0x18003a71e  call    ??$_Try_emplace@AEB_K$$V@?$map@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_K_K@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,unsigned __int64>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18003a723  mov     rcx, [rax]
0x18003a726  mov     [rcx+28h], rbx
0x18003a72a  mov     r9, [rdi+2C0h]
0x18003a731  mov     r8, [rdi+2B8h]
0x18003a738  jmp     short loc_18003A74D
0x18003a73a  mov     rcx, [r8]
0x18003a73d  mov     rax, [rsp+130h+var_F8]
0x18003a742  mov     [rcx+240h], rax
0x18003a749  add     r8, 8
0x18003a74d  cmp     r8, r9
0x18003a750  jnz     short loc_18003A73A
0x18003a752  mov     rbx, [rsi+20h]
0x18003a756  mov     rdx, r15
0x18003a759  lea     rcx, [rsp+130h+var_C0]
0x18003a75e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003a763  mov     r8, rax
0x18003a766  mov     rdx, [rsp+130h+var_108]
0x18003a76b  lea     rcx, [rbx+0A8h]
0x18003a772  call    ?AddFxDeviceRegistrant@DevicePowerRequirements@@QEAAX_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DevicePowerRequirements::AddFxDeviceRegistrant(unsigned __int64,std::wstring)
0x18003a777  lea     rdx, [rbp+30h+SourceString]
0x18003a77b  cmp     [rbp+30h+var_88], 7
0x18003a780  cmova   rdx, [rbp+30h+SourceString]; SourceString
0x18003a785  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18003a78a  call    cs:__imp_RtlInitUnicodeString
0x18003a790  lea     rdx, [rbp+30h+var_80]
0x18003a794  lea     rcx, [rsp+130h+DestinationString]
0x18003a799  call    cs:__imp_SleepstudyHelperCreateGuidFromInstancePath
0x18003a79f  test    eax, eax
0x18003a7a1  js      short loc_18003A7C8
0x18003a7a3  mov     rbx, [rsp+130h+var_F8]
0x18003a7a8  mov     rcx, [rsi+20h]
0x18003a7ac  add     rcx, 140h
0x18003a7b3  lea     r8, [rbp+30h+var_80]
0x18003a7b7  lea     rdx, [rsp+130h+var_E0]
0x18003a7bc  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@$$CBU_GUID@@_KUGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@_K@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@_K@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID const,unsigned __int64,GuidCompare,std::allocator<std::pair<_GUID const,unsigned __int64>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18003a7c1  mov     rcx, [rax]
0x18003a7c4  mov     [rcx+30h], rbx
0x18003a7c8  lea     rcx, [rbp+30h+var_70]; void *
0x18003a7cc  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003a7d1  nop
0x18003a7d2  lea     rcx, [rbp+30h+SourceString]; void *
0x18003a7d6  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003a7db  nop
0x18003a7dc  lea     rcx, [rbp+30h+var_50]; void *
0x18003a7e0  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003a7e5  mov     rcx, [rbp+30h+var_30]
0x18003a7e9  xor     rcx, rsp; StackCookie
0x18003a7ec  call    __security_check_cookie
0x18003a7f1  mov     rbx, [rsp+130h+arg_10]
0x18003a7f9  add     rsp, 110h
0x18003a800  pop     r15
0x18003a802  pop     r14
0x18003a804  pop     rdi
0x18003a805  pop     rsi
0x18003a806  pop     rbp
0x18003a807  retn
```
