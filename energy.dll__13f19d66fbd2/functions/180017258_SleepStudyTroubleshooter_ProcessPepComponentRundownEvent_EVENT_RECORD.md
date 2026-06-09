# SleepStudyTroubleshooter::ProcessPepComponentRundownEvent(_EVENT_RECORD *)

- ea: `0x180017258`
- end: `0x180017489`
- name: `?ProcessPepComponentRundownEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `561`
- prototype: `void(SleepStudyTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180017258`
- `0x180017490`
- `0x180018674`
- `0x18001f44c`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001730c`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180017353`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800173bd`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180017462`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001730c`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180017353`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800173bd`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180017462`

## string_xrefs

- `0x1800172d6`: `ComponentIndex`

## pseudocode

```c
void __fastcall SleepStudyTroubleshooter::ProcessPepComponentRundownEvent(
        SleepStudyTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  bool v2; // zf
  ULONG v5; // eax
  unsigned int v6; // r14d
  ULONG i; // edi
  BYTE v8[4]; // [rsp+40h] [rbp-9h] BYREF
  BYTE v9[4]; // [rsp+44h] [rbp-5h] BYREF
  BYTE v10[4]; // [rsp+48h] [rbp-1h] BYREF
  BYTE pBuffer[4]; // [rsp+4Ch] [rbp+3h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp+7h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+58h] [rbp+Fh] BYREF
  PROPERTY_DATA_DESCRIPTOR v14; // [rsp+68h] [rbp+1Fh] BYREF
  const wchar_t *v15; // [rsp+78h] [rbp+2Fh]
  int v16; // [rsp+80h] [rbp+37h]

  v2 = *((_QWORD *)this + 4) == 0;
  *(_DWORD *)pBuffer = 0;
  v12 = 0;
  *(_DWORD *)v9 = 0;
  *(_DWORD *)v8 = 0;
  *(_DWORD *)v10 = 0;
  if ( v2 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) == 0 )
      return;
    SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(this);
  }
  if ( !GetEventPropertyPtr(a2, L"DeviceId", &v12) )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"ComponentIndex";
    if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, pBuffer) )
    {
      pPropertyData.Reserved = 0;
      pPropertyData.ArrayIndex = -1;
      pPropertyData.PropertyName = (ULONGLONG)L"PlatformStateDependencyCount";
      if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v9) )
      {
        v5 = *(_DWORD *)v9;
        if ( *(_DWORD *)v9 )
        {
          v6 = 0;
          for ( i = 0; i < v5; ++i )
          {
            v14.ArrayIndex = i;
            v14.PropertyName = (ULONGLONG)L"PlatformStateDependency";
            v16 = -1;
            v15 = L"PlatformState";
            if ( TdhGetProperty(a2, 0, 0, 2u, &v14, 4u, v8) )
              return;
            if ( *(_DWORD *)v8 >= v6 )
            {
              v6 = *(_DWORD *)v8;
              v15 = L"PowerState";
              if ( TdhGetProperty(a2, 0, 0, 2u, &v14, 4u, v10) )
                return;
            }
            v5 = *(_DWORD *)v9;
          }
          *(_DWORD *)(**((_QWORD **)this + 4) + 232LL) = 1;
          DevicePowerRequirements::AddComponentRequirement(
            (DevicePowerRequirements *)(*((_QWORD *)this + 4) + 168LL),
            v12,
            *(unsigned int *)pBuffer,
            v6,
            *(unsigned int *)v10);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180017258  mov     [rsp-8+arg_10], rbx
0x18001725d  mov     [rsp-8+arg_18], rsi
0x180017262  push    rbp
0x180017263  push    rdi
0x180017264  push    r14
0x180017266  lea     rbp, [rsp-47h]
0x18001726b  sub     rsp, 90h
0x180017272  mov     rax, cs:__security_cookie
0x180017279  xor     rax, rsp
0x18001727c  mov     [rbp+57h+var_18], rax
0x180017280  cmp     qword ptr [rcx+20h], 0
0x180017285  mov     rsi, rdx
0x180017288  mov     rbx, rcx
0x18001728b  mov     dword ptr [rbp+57h+var_54], 0
0x180017292  mov     [rbp+57h+var_50], 0
0x18001729a  mov     dword ptr [rbp+57h+var_5C], 0
0x1800172a1  mov     dword ptr [rbp+57h+var_60], 0
0x1800172a8  mov     dword ptr [rbp+57h+var_58], 0
0x1800172af  jz      loc_180017472
0x1800172b5  lea     r8, [rbp+57h+var_50]; unsigned __int64 *
0x1800172b9  mov     rcx, rsi; pEvent
0x1800172bc  lea     rdx, aDeviceid; "DeviceId"
0x1800172c3  call    ?GetEventPropertyPtr@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventPropertyPtr(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x1800172c8  test    eax, eax
0x1800172ca  jnz     loc_180017407
0x1800172d0  mov     [rbp+57h+var_48.Reserved], eax
0x1800172d3  or      edi, 0FFFFFFFFh
0x1800172d6  lea     rax, aComponentindex; "ComponentIndex"
0x1800172dd  mov     [rbp+57h+var_48.ArrayIndex], edi
0x1800172e0  mov     [rbp+57h+var_48.PropertyName], rax
0x1800172e4  mov     r9d, 1; PropertyDataCount
0x1800172ea  lea     rax, [rbp+57h+var_54]
0x1800172ee  xor     r8d, r8d; pTdhContext
0x1800172f1  mov     [rsp+0A0h+pBuffer], rax; pBuffer
0x1800172f6  xor     edx, edx; TdhContextCount
0x1800172f8  lea     rax, [rbp+57h+var_48]
0x1800172fc  mov     [rsp+0A0h+BufferSize], 4; BufferSize
0x180017304  mov     rcx, rsi; pEvent
0x180017307  mov     [rsp+0A0h+pPropertyData], rax; pPropertyData
0x18001730c  call    cs:__imp_TdhGetProperty
0x180017312  test    eax, eax
0x180017314  jnz     loc_180017407
0x18001731a  mov     [rbp+57h+var_48.Reserved], eax
0x18001731d  mov     r9d, 1; PropertyDataCount
0x180017323  lea     rax, aPlatformstated; "PlatformStateDependencyCount"
0x18001732a  mov     [rbp+57h+var_48.ArrayIndex], edi
0x18001732d  mov     [rbp+57h+var_48.PropertyName], rax
0x180017331  xor     r8d, r8d; pTdhContext
0x180017334  lea     rax, [rbp+57h+var_5C]
0x180017338  xor     edx, edx; TdhContextCount
0x18001733a  mov     [rsp+0A0h+pBuffer], rax; pBuffer
0x18001733f  mov     rcx, rsi; pEvent
0x180017342  lea     rax, [rbp+57h+var_48]
0x180017346  mov     [rsp+0A0h+BufferSize], 4; BufferSize
0x18001734e  mov     [rsp+0A0h+pPropertyData], rax; pPropertyData
0x180017353  call    cs:__imp_TdhGetProperty
0x180017359  test    eax, eax
0x18001735b  jnz     loc_180017407
0x180017361  mov     eax, dword ptr [rbp+57h+var_5C]
0x180017364  test    eax, eax
0x180017366  jz      loc_180017407
0x18001736c  xor     r14d, r14d
0x18001736f  xor     edi, edi
0x180017371  cmp     edi, eax
0x180017373  jnb     short loc_1800173D4
0x180017375  lea     rax, aPlatformstated_0; "PlatformStateDependency"
0x18001737c  mov     [rbp+57h+var_38.ArrayIndex], edi
0x18001737f  mov     [rbp+57h+var_38.PropertyName], rax
0x180017383  mov     r9d, 2; PropertyDataCount
0x180017389  lea     rax, aPlatformstate; "PlatformState"
0x180017390  mov     [rbp+57h+var_20], 0FFFFFFFFh
0x180017397  mov     [rbp+57h+var_28], rax
0x18001739b  xor     r8d, r8d; pTdhContext
0x18001739e  lea     rax, [rbp+57h+var_60]
0x1800173a2  xor     edx, edx; TdhContextCount
0x1800173a4  mov     [rsp+0A0h+pBuffer], rax; pBuffer
0x1800173a9  mov     rcx, rsi; pEvent
0x1800173ac  lea     rax, [rbp+57h+var_38]
0x1800173b0  mov     [rsp+0A0h+BufferSize], 4; BufferSize
0x1800173b8  mov     [rsp+0A0h+pPropertyData], rax; pPropertyData
0x1800173bd  call    cs:__imp_TdhGetProperty
0x1800173c3  test    eax, eax
0x1800173c5  jnz     short loc_180017407
0x1800173c7  cmp     dword ptr [rbp+57h+var_60], r14d
0x1800173cb  jnb     short loc_18001742B
0x1800173cd  mov     eax, dword ptr [rbp+57h+var_5C]
0x1800173d0  inc     edi
0x1800173d2  jmp     short loc_180017371
0x1800173d4  mov     rax, [rbx+20h]
0x1800173d8  mov     r9d, r14d; unsigned int
0x1800173db  mov     rcx, [rax]
0x1800173de  mov     dword ptr [rcx+0E8h], 1
0x1800173e8  mov     rcx, [rbx+20h]
0x1800173ec  mov     eax, dword ptr [rbp+57h+var_58]
0x1800173ef  add     rcx, 0A8h; this
0x1800173f6  mov     r8d, dword ptr [rbp+57h+var_54]; unsigned int
0x1800173fa  mov     rdx, [rbp+57h+var_50]; unsigned __int64
0x1800173fe  mov     dword ptr [rsp+0A0h+pPropertyData], eax; unsigned int
0x180017402  call    ?AddComponentRequirement@DevicePowerRequirements@@QEAAX_KKKK@Z; DevicePowerRequirements::AddComponentRequirement(unsigned __int64,ulong,ulong,ulong)
0x180017407  mov     rcx, [rbp+57h+var_18]
0x18001740b  xor     rcx, rsp; StackCookie
0x18001740e  call    __security_check_cookie
0x180017413  lea     r11, [rsp+0A0h+var_10]
0x18001741b  mov     rbx, [r11+30h]
0x18001741f  mov     rsi, [r11+38h]
0x180017423  mov     rsp, r11
0x180017426  pop     r14
0x180017428  pop     rdi
0x180017429  pop     rbp
0x18001742a  retn
0x18001742b  mov     r14d, dword ptr [rbp+57h+var_60]
0x18001742f  lea     rax, aPowerstate; "PowerState"
0x180017436  mov     [rbp+57h+var_28], rax
0x18001743a  mov     r9d, 2; PropertyDataCount
0x180017440  lea     rax, [rbp+57h+var_58]
0x180017444  xor     r8d, r8d; pTdhContext
0x180017447  mov     [rsp+0A0h+pBuffer], rax; pBuffer
0x18001744c  xor     edx, edx; TdhContextCount
0x18001744e  lea     rax, [rbp+57h+var_38]
0x180017452  mov     [rsp+0A0h+BufferSize], 4; BufferSize
0x18001745a  mov     rcx, rsi; pEvent
0x18001745d  mov     [rsp+0A0h+pPropertyData], rax; pPropertyData
0x180017462  call    cs:__imp_TdhGetProperty
0x180017468  test    eax, eax
0x18001746a  jz      loc_1800173CD
0x180017470  jmp     short loc_180017407
0x180017472  mov     rax, [rcx+18h]
0x180017476  test    byte ptr [rax+188h], 20h
0x18001747d  jz      short loc_180017407
0x18001747f  call    ?GetCurrentScenarioInstanceData@SleepStudyTroubleshooter@@AEAAPEAUScenarioInstanceData@@XZ; SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(void)
0x180017484  jmp     loc_1800172B5
```
