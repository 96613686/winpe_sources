# SleepStudyTroubleshooter::ProcessComponentAccountingEvent(_EVENT_RECORD *)

- ea: `0x18001f820`
- end: `0x18001fb7b`
- name: `?ProcessComponentAccountingEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `859`
- prototype: `void(SleepStudyTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180008da0`
- `0x1800161c4`
- `0x180018674`
- `0x18001f6f4`
- `0x18001f820`
- `0x18001fb84`
- `0x180033690`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f8b1`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f8f7`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f94e`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f994`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f9da`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f8b1`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f8f7`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f94e`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f994`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001f9da`

## string_xrefs

- `0x18001f964`: `Component`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SleepStudyTroubleshooter::ProcessComponentAccountingEvent(
        SleepStudyTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  FxComponentData *v4; // rax
  FxComponentData *v5; // rbx
  __int64 *v6; // rdx
  __int64 *v7; // rax
  __int64 *v8; // rcx
  __int64 v9; // rdi
  _BYTE *v10; // rdx
  _BYTE *v11; // rdx
  FxDeviceData *v12; // rax
  FxDeviceData *v13; // rdi
  BYTE v14[4]; // [rsp+40h] [rbp-19h] BYREF
  BYTE v15[8]; // [rsp+48h] [rbp-11h] BYREF
  FxComponentData *v16; // [rsp+50h] [rbp-9h] BYREF
  BYTE pBuffer[8]; // [rsp+58h] [rbp-1h] BYREF
  BYTE v18[8]; // [rsp+60h] [rbp+7h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+68h] [rbp+Fh] BYREF

  *(_QWORD *)v18 = 0;
  *(_DWORD *)v14 = 0;
  *(_QWORD *)v15 = 0;
  *(_QWORD *)pBuffer = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) == 0 )
      return;
    SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(this);
  }
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ScenarioInstanceId";
  if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer) )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.ArrayIndex = -1;
    pPropertyData.PropertyName = (ULONGLONG)L"ScenarioInstanceIdV2";
    if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer)
      && ((*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0
       || *(_QWORD *)(**((_QWORD **)this + 4) + 16LL) == *(_QWORD *)pBuffer) )
    {
      pPropertyData.Reserved = 0;
      pPropertyData.ArrayIndex = -1;
      pPropertyData.PropertyName = (ULONGLONG)L"DeviceNode";
      if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, v15) )
      {
        pPropertyData.Reserved = 0;
        pPropertyData.ArrayIndex = -1;
        pPropertyData.PropertyName = (ULONGLONG)L"Component";
        if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v14) )
        {
          pPropertyData.Reserved = 0;
          pPropertyData.ArrayIndex = -1;
          pPropertyData.PropertyName = (ULONGLONG)L"ActiveTime";
          if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, v18) )
          {
            v4 = (FxComponentData *)operator new(0x250u);
            v16 = v4;
            if ( v4 )
              v5 = FxComponentData::FxComponentData(v4, *(unsigned int *)v14);
            else
              v5 = 0;
            v16 = v5;
            v6 = *(__int64 **)(*((_QWORD *)this + 4) + 8LL);
            v7 = (__int64 *)v6[1];
            pPropertyData.Reserved = 0;
            v8 = v6;
            while ( !*((_BYTE *)v7 + 25) )
            {
              if ( (unsigned __int64)v7[4] < *(_QWORD *)v15 )
                v7 += 2;
              else
                v8 = v7;
              v7 = (__int64 *)*v7;
            }
            if ( v8 == v6 || *((_BYTE *)v8 + 25) || *(_QWORD *)v15 < (unsigned __int64)v8[4] )
            {
              v12 = (FxDeviceData *)operator new(0x2F8u);
              pPropertyData.PropertyName = (ULONGLONG)v12;
              if ( v12 )
                v13 = FxDeviceData::FxDeviceData(v12);
              else
                v13 = 0;
              *((_QWORD *)v13 + 72) = *(_QWORD *)v15;
              v11 = (_BYTE *)*((_QWORD *)v13 + 88);
              if ( v11 == *((_BYTE **)v13 + 89) )
              {
                std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
                  (void **)v13 + 87,
                  v11,
                  (__int64 *)&v16);
              }
              else
              {
                *(_QWORD *)v11 = v5;
                *((_QWORD *)v13 + 88) += 8LL;
              }
              *(_QWORD *)(*(_QWORD *)std::map<unsigned __int64,FxDeviceData *>::_Try_emplace<unsigned __int64 const &,>(
                                       *((_QWORD *)this + 4) + 8LL,
                                       &pPropertyData,
                                       v15)
                        + 40LL) = v13;
            }
            else
            {
              v9 = v8[5];
              v10 = *(_BYTE **)(v9 + 704);
              if ( v10 == *(_BYTE **)(v9 + 712) )
              {
                std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
                  (void **)(v9 + 696),
                  v10,
                  (__int64 *)&v16);
                v5 = v16;
              }
              else
              {
                *(_QWORD *)v10 = v5;
                *(_QWORD *)(v9 + 704) += 8LL;
              }
              *((_QWORD *)v5 + 72) = *(_QWORD *)(v9 + 584);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001f820  mov     [rsp-8+arg_10], rbx
0x18001f825  mov     [rsp-8+arg_18], rsi
0x18001f82a  push    rbp
0x18001f82b  push    rdi
0x18001f82c  push    r12
0x18001f82e  push    r13
0x18001f830  push    r14
0x18001f832  lea     rbp, [rsp-37h]
0x18001f837  sub     rsp, 90h
0x18001f83e  mov     rax, cs:__security_cookie
0x18001f845  xor     rax, rsp
0x18001f848  mov     [rbp+57h+var_30], rax
0x18001f84c  mov     rdi, rdx
0x18001f84f  mov     rsi, rcx
0x18001f852  xor     r14d, r14d
0x18001f855  mov     qword ptr [rbp+57h+var_50], r14
0x18001f859  mov     dword ptr [rbp+57h+var_70], r14d
0x18001f85d  mov     qword ptr [rbp+57h+var_68], r14
0x18001f861  mov     qword ptr [rbp+57h+var_58], r14
0x18001f865  cmp     [rcx+20h], r14
0x18001f869  jz      loc_18001FB2D
0x18001f86f  mov     [rbp+57h+var_48.Reserved], r14d
0x18001f873  or      r12d, 0FFFFFFFFh
0x18001f877  mov     [rbp+57h+var_48.ArrayIndex], r12d
0x18001f87b  lea     rax, aScenarioinstan_0; "ScenarioInstanceId"
0x18001f882  mov     [rbp+57h+var_48.PropertyName], rax
0x18001f886  lea     rax, [rbp+57h+var_58]
0x18001f88a  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x18001f88f  mov     [rsp+0B0h+BufferSize], 8; BufferSize
0x18001f897  lea     rax, [rbp+57h+var_48]
0x18001f89b  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001f8a0  mov     r13d, 1
0x18001f8a6  mov     r9d, r13d; PropertyDataCount
0x18001f8a9  xor     r8d, r8d; pTdhContext
0x18001f8ac  xor     edx, edx; TdhContextCount
0x18001f8ae  mov     rcx, rdi; pEvent
0x18001f8b1  call    cs:__imp_TdhGetProperty
0x18001f8b7  test    eax, eax
0x18001f8b9  jnz     loc_18001FA8F
0x18001f8bf  mov     [rbp+57h+var_48.Reserved], r14d
0x18001f8c3  mov     [rbp+57h+var_48.ArrayIndex], r12d
0x18001f8c7  lea     rax, aScenarioinstan_2; "ScenarioInstanceIdV2"
0x18001f8ce  mov     [rbp+57h+var_48.PropertyName], rax
0x18001f8d2  lea     rax, [rbp+57h+var_58]
0x18001f8d6  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x18001f8db  mov     [rsp+0B0h+BufferSize], 8; BufferSize
0x18001f8e3  lea     rax, [rbp+57h+var_48]
0x18001f8e7  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001f8ec  mov     r9d, r13d; PropertyDataCount
0x18001f8ef  xor     r8d, r8d; pTdhContext
0x18001f8f2  xor     edx, edx; TdhContextCount
0x18001f8f4  mov     rcx, rdi; pEvent
0x18001f8f7  call    cs:__imp_TdhGetProperty
0x18001f8fd  test    eax, eax
0x18001f8ff  jnz     loc_18001FA8F
0x18001f905  mov     rax, [rsi+18h]
0x18001f909  test    byte ptr [rax+188h], 20h
0x18001f910  jz      loc_18001FAC6
0x18001f916  mov     [rbp+57h+var_48.Reserved], r14d
0x18001f91a  mov     [rbp+57h+var_48.ArrayIndex], r12d
0x18001f91e  lea     rax, aDevicenode; "DeviceNode"
0x18001f925  mov     [rbp+57h+var_48.PropertyName], rax
0x18001f929  lea     rax, [rbp+57h+var_68]
0x18001f92d  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x18001f932  mov     [rsp+0B0h+BufferSize], 8; BufferSize
0x18001f93a  lea     rax, [rbp+57h+var_48]
0x18001f93e  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001f943  mov     r9d, r13d; PropertyDataCount
0x18001f946  xor     r8d, r8d; pTdhContext
0x18001f949  xor     edx, edx; TdhContextCount
0x18001f94b  mov     rcx, rdi; pEvent
0x18001f94e  call    cs:__imp_TdhGetProperty
0x18001f954  test    eax, eax
0x18001f956  jnz     loc_18001FA8F
0x18001f95c  mov     [rbp+57h+var_48.Reserved], r14d
0x18001f960  mov     [rbp+57h+var_48.ArrayIndex], r12d
0x18001f964  lea     rax, aComponent; "Component"
0x18001f96b  mov     [rbp+57h+var_48.PropertyName], rax
0x18001f96f  lea     rax, [rbp+57h+var_70]
0x18001f973  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x18001f978  mov     [rsp+0B0h+BufferSize], 4; BufferSize
0x18001f980  lea     rax, [rbp+57h+var_48]
0x18001f984  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001f989  mov     r9d, r13d; PropertyDataCount
0x18001f98c  xor     r8d, r8d; pTdhContext
0x18001f98f  xor     edx, edx; TdhContextCount
0x18001f991  mov     rcx, rdi; pEvent
0x18001f994  call    cs:__imp_TdhGetProperty
0x18001f99a  test    eax, eax
0x18001f99c  jnz     loc_18001FA8F
0x18001f9a2  mov     [rbp+57h+var_48.Reserved], r14d
0x18001f9a6  mov     [rbp+57h+var_48.ArrayIndex], r12d
0x18001f9aa  lea     rax, aActivetime_0; "ActiveTime"
0x18001f9b1  mov     [rbp+57h+var_48.PropertyName], rax
0x18001f9b5  lea     rax, [rbp+57h+var_50]
0x18001f9b9  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x18001f9be  mov     [rsp+0B0h+BufferSize], 8; BufferSize
0x18001f9c6  lea     rax, [rbp+57h+var_48]
0x18001f9ca  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x18001f9cf  mov     r9d, r13d; PropertyDataCount
0x18001f9d2  xor     r8d, r8d; pTdhContext
0x18001f9d5  xor     edx, edx; TdhContextCount
0x18001f9d7  mov     rcx, rdi; pEvent
0x18001f9da  call    cs:__imp_TdhGetProperty
0x18001f9e0  test    eax, eax
0x18001f9e2  jnz     loc_18001FA8F
0x18001f9e8  mov     ecx, 250h; dwBytes
0x18001f9ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f9f2  mov     [rbp+57h+var_60], rax
0x18001f9f6  test    rax, rax
0x18001f9f9  jz      loc_18001FB48
0x18001f9ff  mov     r8, qword ptr [rbp+57h+var_50]; unsigned __int64
0x18001fa03  mov     edx, dword ptr [rbp+57h+var_70]; unsigned int
0x18001fa06  mov     rcx, rax; this
0x18001fa09  call    ??0FxComponentData@@QEAA@K_K@Z; FxComponentData::FxComponentData(ulong,unsigned __int64)
0x18001fa0e  mov     rbx, rax
0x18001fa11  mov     [rbp+57h+var_60], rbx
0x18001fa15  mov     rax, [rsi+20h]
0x18001fa19  mov     rdx, [rax+8]
0x18001fa1d  mov     rax, [rdx+8]
0x18001fa21  xor     ecx, ecx
0x18001fa23  mov     [rbp+57h+var_48.Reserved], ecx
0x18001fa26  mov     rcx, rdx
0x18001fa29  mov     r8, qword ptr [rbp+57h+var_68]
0x18001fa2d  jmp     short loc_18001FA36
0x18001fa2f  add     rax, 10h
0x18001fa33  mov     rax, [rax]
0x18001fa36  cmp     [rax+19h], r14b
0x18001fa3a  jnz     short loc_18001FA47
0x18001fa3c  cmp     [rax+20h], r8
0x18001fa40  jb      short loc_18001FA2F
0x18001fa42  mov     rcx, rax
0x18001fa45  jmp     short loc_18001FA33
0x18001fa47  cmp     rcx, rdx
0x18001fa4a  jz      loc_18001FB50
0x18001fa50  cmp     [rcx+19h], r14b
0x18001fa54  jnz     loc_18001FB50
0x18001fa5a  cmp     r8, [rcx+20h]
0x18001fa5e  jb      loc_18001FB50
0x18001fa64  mov     rdi, [rcx+28h]
0x18001fa68  lea     rcx, [rdi+2B8h]
0x18001fa6f  mov     rdx, [rcx+8]
0x18001fa73  cmp     rdx, [rcx+10h]
0x18001fa77  jz      short loc_18001FAB7
0x18001fa79  mov     [rdx], rbx
0x18001fa7c  add     qword ptr [rcx+8], 8
0x18001fa81  mov     rax, [rdi+248h]
0x18001fa88  mov     [rbx+240h], rax
0x18001fa8f  mov     rcx, [rbp+57h+var_30]
0x18001fa93  xor     rcx, rsp; StackCookie
0x18001fa96  call    __security_check_cookie
0x18001fa9b  lea     r11, [rsp+0B0h+var_20]
0x18001faa3  mov     rbx, [r11+40h]
0x18001faa7  mov     rsi, [r11+48h]
0x18001faab  mov     rsp, r11
0x18001faae  pop     r14
0x18001fab0  pop     r13
0x18001fab2  pop     r12
0x18001fab4  pop     rdi
0x18001fab5  pop     rbp
0x18001fab6  retn
0x18001fab7  lea     r8, [rbp+57h+var_60]
0x18001fabb  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18001fac0  mov     rbx, [rbp+57h+var_60]
0x18001fac4  jmp     short loc_18001FA81
0x18001fac6  mov     rax, [rsi+20h]
0x18001faca  mov     rcx, [rax]
0x18001facd  mov     rax, qword ptr [rbp+57h+var_58]
0x18001fad1  cmp     [rcx+10h], rax
0x18001fad5  jz      loc_18001F916
0x18001fadb  jmp     short loc_18001FA8F
0x18001fadd  mov     rax, qword ptr [rbp+57h+var_68]
0x18001fae1  mov     [rdi+240h], rax
0x18001fae8  lea     rcx, [rdi+2B8h]
0x18001faef  mov     rdx, [rcx+8]
0x18001faf3  cmp     rdx, [rcx+10h]
0x18001faf7  jz      short loc_18001FB22
0x18001faf9  mov     [rdx], rbx
0x18001fafc  add     qword ptr [rcx+8], 8
0x18001fb01  mov     rcx, [rsi+20h]
0x18001fb05  add     rcx, 8
0x18001fb09  lea     r8, [rbp+57h+var_68]
0x18001fb0d  lea     rdx, [rbp+57h+var_48]
0x18001fb11  call    ??$_Try_emplace@AEB_K$$V@?$map@_KPEAUFxDeviceData@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAUFxDeviceData@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAUFxDeviceData@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,FxDeviceData *>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001fb16  mov     rcx, [rax]
0x18001fb19  mov     [rcx+28h], rdi
0x18001fb1d  jmp     loc_18001FA8F
0x18001fb22  lea     r8, [rbp+57h+var_60]
0x18001fb26  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18001fb2b  jmp     short loc_18001FB01
0x18001fb2d  mov     rax, [rcx+18h]
0x18001fb31  test    byte ptr [rax+188h], 20h
0x18001fb38  jz      loc_18001FA8F
0x18001fb3e  call    ?GetCurrentScenarioInstanceData@SleepStudyTroubleshooter@@AEAAPEAUScenarioInstanceData@@XZ; SleepStudyTroubleshooter::GetCurrentScenarioInstanceData(void)
0x18001fb43  jmp     loc_18001F86F
0x18001fb48  mov     rbx, r14
0x18001fb4b  jmp     loc_18001FA11
0x18001fb50  mov     ecx, 2F8h; dwBytes
0x18001fb55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb5a  mov     [rbp+57h+var_48.PropertyName], rax
0x18001fb5e  test    rax, rax
0x18001fb61  jz      short loc_18001FB73
0x18001fb63  mov     rcx, rax; this
0x18001fb66  call    ??0FxDeviceData@@QEAA@XZ; FxDeviceData::FxDeviceData(void)
0x18001fb6b  mov     rdi, rax
0x18001fb6e  jmp     loc_18001FADD
0x18001fb73  mov     rdi, r14
0x18001fb76  jmp     loc_18001FADD
```
