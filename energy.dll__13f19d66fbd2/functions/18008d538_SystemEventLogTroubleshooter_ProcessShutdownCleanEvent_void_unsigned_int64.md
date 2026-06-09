# SystemEventLogTroubleshooter::ProcessShutdownCleanEvent(void *,unsigned __int64)

- ea: `0x18008d538`
- end: `0x18008dab3`
- name: `?ProcessShutdownCleanEvent@SystemEventLogTroubleshooter@@AEAAXPEAX_K@Z`
- size: `1403`
- prototype: `void __fastcall(SystemEventLogTroubleshooter *__hidden this, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002f3ec`

## callees

- `0x180008740`
- `0x180008da0`
- `0x18000b6f0`
- `0x18001c8cc`
- `0x18001e218`
- `0x18001f6f4`
- `0x180036c88`
- `0x180037090`
- `0x18003bce0`
- `0x180044168`
- `0x1800446f8`
- `0x18004ca90`
- `0x180059198`
- `0x1800591b8`
- `0x18008d538`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18008d78c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18008d78c`

## string_xrefs

- `0x18008d849`: `ComputerName`
- `0x18008d9ba`: `Comment`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall SystemEventLogTroubleshooter::ProcessShutdownCleanEvent(SystemEventLogTroubleshooter *this, void *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  void *v7; // rax
  __int64 v8; // rcx
  _BYTE *v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  const wchar_t *v17; // rcx
  unsigned int v18; // eax
  _QWORD *v19; // rdx
  void *v20; // rax
  void *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rbx
  _BYTE *v24; // rdx
  void *v25; // rax
  void *v26; // rdi
  __int64 v27; // rax
  _BYTE *v28; // rdx
  void *v29; // rax
  void *v30; // rdi
  __int64 v31; // rax
  _BYTE *v32; // rdx
  void *v33; // rax
  void *v34; // rdi
  __int64 v35; // rax
  _BYTE *v36; // rdx
  void *v37; // rax
  void *v38; // rdi
  __int64 v39; // rax
  _BYTE *v40; // rdx
  void *v41; // rax
  void *v42; // rdi
  __int64 v43; // rax
  _BYTE *v44; // rdx
  void *v45; // rax
  void *v46; // rdi
  __int64 v47; // rax
  _BYTE *v48; // rdx
  void *v49; // [rsp+30h] [rbp-D0h] BYREF
  void *v50; // [rsp+38h] [rbp-C8h]
  _BYTE v51[32]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v53[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v54[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v55[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v56[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v57[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v58[4]; // [rsp+120h] [rbp+20h] BYREF

  std::wstring::wstring(v58);
  std::wstring::wstring(v57);
  std::wstring::wstring(v54);
  std::wstring::wstring(v53);
  std::wstring::wstring(String);
  std::wstring::wstring(v56);
  std::wstring::wstring(v55);
  if ( (unsigned int)GetEventProperty(a2, L"param1", v54)
    || (unsigned int)GetEventProperty(a2, L"param2", v57)
    || (unsigned int)GetEventProperty(a2, L"param3", v53)
    || (unsigned int)GetEventProperty(a2, L"param4", String)
    || (unsigned int)GetEventProperty(a2, L"param5", v56)
    || (unsigned int)GetEventProperty(a2, L"param6", v58)
    || (unsigned int)GetEventProperty(a2, L"param7", v55) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v6);
  }
  else
  {
    if ( *(_QWORD *)(*((_QWORD *)this + 4) + 8LL) == **((_QWORD **)this + 4) )
    {
      v7 = operator new(0x1E0u);
      v49 = v7;
      if ( v7 )
        v7 = (void *)OsStateInstance::OsStateInstance((__int64)v7, 1, 0, *((_DWORD *)this + 10), 0);
      v49 = v7;
      v8 = *((_QWORD *)this + 4);
      v9 = *(_BYTE **)(v8 + 8);
      if ( v9 == *(_BYTE **)(v8 + 16) )
      {
        std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
          (void **)v8,
          v9,
          (__int64 *)&v49);
      }
      else
      {
        *(_QWORD *)v9 = v7;
        *(_QWORD *)(v8 + 8) += 8LL;
      }
    }
    v10 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8LL) - 8LL);
    if ( !(unsigned int)IsActive((struct OsStateInstance *)v10)
      && !(unsigned int)IsModernStandby((struct OsStateInstance *)v10)
      && !(unsigned int)IsSystemSleep(PowerSystemWorking, (struct OsStateInstance *)v10) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13);
    }
    if ( !(unsigned int)IsActive((struct OsStateInstance *)v10)
      && !(unsigned int)IsModernStandby((struct OsStateInstance *)v10) )
    {
      IsSystemSleep(PowerSystemWorking, (struct OsStateInstance *)v10);
    }
    if ( !*(_BYTE *)(v10 + 183) && *(_BYTE *)(v10 + 20) && *(_QWORD *)(v10 + 96) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v16);
    *(_DWORD *)(v10 + 152) = 6;
    v17 = (const wchar_t *)String;
    if ( String[3] > (wchar_t *)7 )
      v17 = String[0];
    v18 = wcstoul(v17, 0, 0) & 0xFFFFFF;
    if ( v18 == 255 || (v19 = v53, !v18) )
      v19 = v54;
    std::wstring::operator=(v10 + 120, v19);
    v20 = operator new(0x50u);
    v21 = v20;
    v49 = v20;
    if ( v20 )
    {
      v22 = std::wstring::wstring((__int64)v51, v54);
      v20 = (void *)CustomData::CustomData(v21, L"ProcessName", v22);
    }
    v49 = v20;
    v23 = v10 + 208;
    v24 = *(_BYTE **)(v23 + 8);
    if ( v24 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v24,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v24 = v20;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
    v25 = operator new(0x50u);
    v26 = v25;
    v50 = v25;
    if ( v25 )
    {
      v27 = std::wstring::wstring((__int64)v51, v57);
      v25 = (void *)CustomData::CustomData(v26, L"ComputerName", v27);
    }
    v49 = v25;
    v28 = *(_BYTE **)(v23 + 8);
    if ( v28 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v28,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v28 = v25;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
    v29 = operator new(0x50u);
    v30 = v29;
    v50 = v29;
    if ( v29 )
    {
      v31 = std::wstring::wstring((__int64)v51, v53);
      v29 = (void *)CustomData::CustomData(v30, L"ReasonTitle", v31);
    }
    v49 = v29;
    v32 = *(_BYTE **)(v23 + 8);
    if ( v32 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v32,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v32 = v29;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
    v33 = operator new(0x50u);
    v34 = v33;
    v50 = v33;
    if ( v33 )
    {
      v35 = std::wstring::wstring((__int64)v51, String);
      v33 = (void *)CustomData::CustomData(v34, L"ReasonCode", v35);
    }
    v49 = v33;
    v36 = *(_BYTE **)(v23 + 8);
    if ( v36 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v36,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v36 = v33;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
    v37 = operator new(0x50u);
    v38 = v37;
    v50 = v37;
    if ( v37 )
    {
      v39 = std::wstring::wstring((__int64)v51, v56);
      v37 = (void *)CustomData::CustomData(v38, L"ShutdownType", v39);
    }
    v49 = v37;
    v40 = *(_BYTE **)(v23 + 8);
    if ( v40 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v40,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v40 = v37;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
    v41 = operator new(0x50u);
    v42 = v41;
    v50 = v41;
    if ( v41 )
    {
      v43 = std::wstring::wstring((__int64)v51, v58);
      v41 = (void *)CustomData::CustomData(v42, L"Comment", v43);
    }
    v49 = v41;
    v44 = *(_BYTE **)(v23 + 8);
    if ( v44 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v44,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v44 = v41;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
    v45 = operator new(0x50u);
    v46 = v45;
    v50 = v45;
    if ( v45 )
    {
      v47 = std::wstring::wstring((__int64)v51, v55);
      v45 = (void *)CustomData::CustomData(v46, L"UserDomain", v47);
    }
    v49 = v45;
    v48 = *(_BYTE **)(v23 + 8);
    if ( v48 == *(_BYTE **)(v23 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v23,
        v48,
        (__int64 *)&v49);
    }
    else
    {
      *(_QWORD *)v48 = v45;
      *(_QWORD *)(v23 + 8) += 8LL;
    }
  }
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v55);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v56);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(String);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v53);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v54);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v57);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v58);
}

```

## disassembly

```asm
0x18008d538  mov     [rsp-8+arg_10], rbx
0x18008d53d  push    rbp
0x18008d53e  push    rdi
0x18008d53f  push    r14
0x18008d541  lea     rbp, [rsp-50h]
0x18008d546  sub     rsp, 150h
0x18008d54d  mov     rax, cs:__security_cookie
0x18008d554  xor     rax, rsp
0x18008d557  mov     [rbp+60h+var_20], rax
0x18008d55b  mov     rbx, rdx
0x18008d55e  mov     rdi, rcx
0x18008d561  lea     rcx, [rbp+60h+var_40]; void *
0x18008d565  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d56a  nop
0x18008d56b  lea     rcx, [rbp+60h+var_60]; void *
0x18008d56f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d574  nop
0x18008d575  lea     rcx, [rbp+60h+var_C0]; void *
0x18008d579  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d57e  nop
0x18008d57f  lea     rcx, [rbp+60h+var_E0]; void *
0x18008d583  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d588  nop
0x18008d589  lea     rcx, [rsp+160h+String]; void *
0x18008d58e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d593  nop
0x18008d594  lea     rcx, [rbp+60h+var_80]; void *
0x18008d598  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d59d  nop
0x18008d59e  lea     rcx, [rbp+60h+var_A0]; void *
0x18008d5a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d5a7  nop
0x18008d5a8  lea     r8, [rbp+60h+var_C0]
0x18008d5ac  lea     rdx, aParam1; "param1"
0x18008d5b3  mov     rcx, rbx
0x18008d5b6  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d5bb  test    eax, eax
0x18008d5bd  jz      short loc_18008D5C9
0x18008d5bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d5c4  jmp     loc_18008DA4D
0x18008d5c9  lea     r8, [rbp+60h+var_60]
0x18008d5cd  lea     rdx, aParam2; "param2"
0x18008d5d4  mov     rcx, rbx
0x18008d5d7  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d5dc  test    eax, eax
0x18008d5de  jz      short loc_18008D5EA
0x18008d5e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d5e5  jmp     loc_18008DA4D
0x18008d5ea  lea     r8, [rbp+60h+var_E0]
0x18008d5ee  lea     rdx, aParam3; "param3"
0x18008d5f5  mov     rcx, rbx
0x18008d5f8  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d5fd  test    eax, eax
0x18008d5ff  jz      short loc_18008D60B
0x18008d601  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d606  jmp     loc_18008DA4D
0x18008d60b  lea     r8, [rsp+160h+String]
0x18008d610  lea     rdx, aParam4; "param4"
0x18008d617  mov     rcx, rbx
0x18008d61a  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d61f  test    eax, eax
0x18008d621  jz      short loc_18008D62D
0x18008d623  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d628  jmp     loc_18008DA4D
0x18008d62d  lea     r8, [rbp+60h+var_80]
0x18008d631  lea     rdx, aParam5; "param5"
0x18008d638  mov     rcx, rbx
0x18008d63b  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d640  test    eax, eax
0x18008d642  jz      short loc_18008D64E
0x18008d644  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d649  jmp     loc_18008DA4D
0x18008d64e  lea     r8, [rbp+60h+var_40]
0x18008d652  lea     rdx, aParam6; "param6"
0x18008d659  mov     rcx, rbx
0x18008d65c  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d661  test    eax, eax
0x18008d663  jz      short loc_18008D66F
0x18008d665  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d66a  jmp     loc_18008DA4D
0x18008d66f  lea     r8, [rbp+60h+var_A0]
0x18008d673  lea     rdx, aParam7; "param7"
0x18008d67a  mov     rcx, rbx
0x18008d67d  call    ?GetEventProperty@@YAKPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetEventProperty(void *,ushort const *,std::wstring &)
0x18008d682  test    eax, eax
0x18008d684  jz      short loc_18008D690
0x18008d686  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d68b  jmp     loc_18008DA4D
0x18008d690  mov     rax, [rdi+20h]
0x18008d694  mov     rcx, [rax+8]
0x18008d698  mov     r14d, 1
0x18008d69e  cmp     rcx, [rax]
0x18008d6a1  jnz     short loc_18008D6F6
0x18008d6a3  mov     ecx, 1E0h; dwBytes
0x18008d6a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d6ad  mov     [rsp+160h+var_130], rax
0x18008d6b2  test    rax, rax
0x18008d6b5  jz      short loc_18008D6CF
0x18008d6b7  mov     [rsp+160h+var_140], 0
0x18008d6bc  mov     r9d, [rdi+28h]
0x18008d6c0  xor     r8d, r8d
0x18008d6c3  mov     edx, r14d
0x18008d6c6  mov     rcx, rax
0x18008d6c9  call    ??0OsStateInstance@@QEAA@W4OsStateInstanceType@@_KW4OsStatePowerSourceType@@E@Z; OsStateInstance::OsStateInstance(OsStateInstanceType,unsigned __int64,OsStatePowerSourceType,uchar)
0x18008d6ce  nop
0x18008d6cf  mov     [rsp+160h+var_130], rax
0x18008d6d4  mov     rcx, [rdi+20h]
0x18008d6d8  mov     rdx, [rcx+8]
0x18008d6dc  cmp     rdx, [rcx+10h]
0x18008d6e0  jz      short loc_18008D6EC
0x18008d6e2  mov     [rdx], rax
0x18008d6e5  add     qword ptr [rcx+8], 8
0x18008d6ea  jmp     short loc_18008D6F6
0x18008d6ec  lea     r8, [rsp+160h+var_130]
0x18008d6f1  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18008d6f6  mov     rax, [rdi+20h]
0x18008d6fa  mov     rcx, [rax+8]
0x18008d6fe  mov     rbx, [rcx-8]
0x18008d702  mov     rcx, rbx; struct OsStateInstance *
0x18008d705  call    ?IsActive@@YAHPEAVOsStateInstance@@@Z; IsActive(OsStateInstance *)
0x18008d70a  test    eax, eax
0x18008d70c  jnz     short loc_18008D72E
0x18008d70e  mov     rcx, rbx; struct OsStateInstance *
0x18008d711  call    ?IsModernStandby@@YAHPEAVOsStateInstance@@@Z; IsModernStandby(OsStateInstance *)
0x18008d716  test    eax, eax
0x18008d718  jnz     short loc_18008D72E
0x18008d71a  mov     rdx, rbx; struct OsStateInstance *
0x18008d71d  mov     ecx, r14d; enum _SYSTEM_POWER_STATE
0x18008d720  call    ?IsSystemSleep@@YAHW4_SYSTEM_POWER_STATE@@PEAVOsStateInstance@@@Z; IsSystemSleep(_SYSTEM_POWER_STATE,OsStateInstance *)
0x18008d725  test    eax, eax
0x18008d727  jnz     short loc_18008D72E
0x18008d729  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d72e  mov     rcx, rbx; struct OsStateInstance *
0x18008d731  call    ?IsActive@@YAHPEAVOsStateInstance@@@Z; IsActive(OsStateInstance *)
0x18008d736  test    eax, eax
0x18008d738  jnz     short loc_18008D751
0x18008d73a  mov     rcx, rbx; struct OsStateInstance *
0x18008d73d  call    ?IsModernStandby@@YAHPEAVOsStateInstance@@@Z; IsModernStandby(OsStateInstance *)
0x18008d742  test    eax, eax
0x18008d744  jnz     short loc_18008D751
0x18008d746  mov     rdx, rbx; struct OsStateInstance *
0x18008d749  mov     ecx, r14d; enum _SYSTEM_POWER_STATE
0x18008d74c  call    ?IsSystemSleep@@YAHW4_SYSTEM_POWER_STATE@@PEAVOsStateInstance@@@Z; IsSystemSleep(_SYSTEM_POWER_STATE,OsStateInstance *)
0x18008d751  cmp     byte ptr [rbx+0B7h], 0
0x18008d758  jnz     short loc_18008D76C
0x18008d75a  cmp     byte ptr [rbx+14h], 0
0x18008d75e  jz      short loc_18008D76C
0x18008d760  cmp     qword ptr [rbx+60h], 0
0x18008d765  jz      short loc_18008D76C
0x18008d767  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d76c  mov     dword ptr [rbx+98h], 6
0x18008d776  lea     rcx, [rsp+160h+String]
0x18008d77b  cmp     [rsp+160h+var_E8], 7
0x18008d781  cmova   rcx, [rsp+160h+String]; String
0x18008d787  xor     r8d, r8d; Radix
0x18008d78a  xor     edx, edx; EndPtr
0x18008d78c  call    cs:__imp_wcstoul
0x18008d792  and     eax, 0FFFFFFh
0x18008d797  cmp     eax, 0FFh
0x18008d79c  jz      short loc_18008D7A6
0x18008d79e  test    eax, eax
0x18008d7a0  lea     rdx, [rbp+60h+var_E0]
0x18008d7a4  jnz     short loc_18008D7AA
0x18008d7a6  lea     rdx, [rbp+60h+var_C0]
0x18008d7aa  mov     eax, 78h ; 'x'
0x18008d7af  mov     rcx, rbx
0x18008d7b2  add     rcx, rax
0x18008d7b5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008d7ba  mov     r14d, 50h ; 'P'
0x18008d7c0  mov     ecx, r14d; dwBytes
0x18008d7c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d7c8  mov     rdi, rax
0x18008d7cb  mov     [rsp+160h+var_130], rax
0x18008d7d0  test    rax, rax
0x18008d7d3  jz      short loc_18008D7F6
0x18008d7d5  lea     rdx, [rbp+60h+var_C0]
0x18008d7d9  lea     rcx, [rsp+160h+var_120]
0x18008d7de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d7e3  mov     r8, rax
0x18008d7e6  lea     rdx, aProcessname; "ProcessName"
0x18008d7ed  mov     rcx, rdi
0x18008d7f0  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18008d7f5  nop
0x18008d7f6  mov     [rsp+160h+var_130], rax
0x18008d7fb  add     rbx, 0D0h
0x18008d802  mov     rdx, [rbx+8]
0x18008d806  cmp     rdx, [rbx+10h]
0x18008d80a  jz      short loc_18008D816
0x18008d80c  mov     [rdx], rax
0x18008d80f  add     qword ptr [rbx+8], 8
0x18008d814  jmp     short loc_18008D823
0x18008d816  lea     r8, [rsp+160h+var_130]
0x18008d81b  mov     rcx, rbx
0x18008d81e  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18008d823  mov     rcx, r14; dwBytes
0x18008d826  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d82b  mov     rdi, rax
0x18008d82e  mov     [rsp+160h+var_128], rax
0x18008d833  test    rax, rax
0x18008d836  jz      short loc_18008D859
0x18008d838  lea     rdx, [rbp+60h+var_60]
0x18008d83c  lea     rcx, [rsp+160h+var_120]
0x18008d841  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d846  mov     r8, rax
0x18008d849  lea     rdx, aComputername_0; "ComputerName"
0x18008d850  mov     rcx, rdi
0x18008d853  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18008d858  nop
0x18008d859  mov     [rsp+160h+var_130], rax
0x18008d85e  mov     rdx, [rbx+8]
0x18008d862  cmp     rdx, [rbx+10h]
0x18008d866  jz      short loc_18008D872
0x18008d868  mov     [rdx], rax
0x18008d86b  add     qword ptr [rbx+8], 8
0x18008d870  jmp     short loc_18008D87F
0x18008d872  lea     r8, [rsp+160h+var_130]
0x18008d877  mov     rcx, rbx
0x18008d87a  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18008d87f  mov     rcx, r14; dwBytes
0x18008d882  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d887  mov     rdi, rax
0x18008d88a  mov     [rsp+160h+var_128], rax
0x18008d88f  test    rax, rax
0x18008d892  jz      short loc_18008D8B5
0x18008d894  lea     rdx, [rbp+60h+var_E0]
0x18008d898  lea     rcx, [rsp+160h+var_120]
0x18008d89d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d8a2  mov     r8, rax
0x18008d8a5  lea     rdx, aReasontitle; "ReasonTitle"
0x18008d8ac  mov     rcx, rdi
0x18008d8af  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18008d8b4  nop
0x18008d8b5  mov     [rsp+160h+var_130], rax
0x18008d8ba  mov     rdx, [rbx+8]
0x18008d8be  cmp     rdx, [rbx+10h]
0x18008d8c2  jz      short loc_18008D8CE
0x18008d8c4  mov     [rdx], rax
0x18008d8c7  add     qword ptr [rbx+8], 8
0x18008d8cc  jmp     short loc_18008D8DB
0x18008d8ce  lea     r8, [rsp+160h+var_130]
0x18008d8d3  mov     rcx, rbx
0x18008d8d6  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18008d8db  mov     rcx, r14; dwBytes
0x18008d8de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d8e3  mov     rdi, rax
0x18008d8e6  mov     [rsp+160h+var_128], rax
0x18008d8eb  test    rax, rax
0x18008d8ee  jz      short loc_18008D912
0x18008d8f0  lea     rdx, [rsp+160h+String]
0x18008d8f5  lea     rcx, [rsp+160h+var_120]
0x18008d8fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d8ff  mov     r8, rax
0x18008d902  lea     rdx, aReasoncode; "ReasonCode"
0x18008d909  mov     rcx, rdi
0x18008d90c  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18008d911  nop
0x18008d912  mov     [rsp+160h+var_130], rax
0x18008d917  mov     rdx, [rbx+8]
0x18008d91b  cmp     rdx, [rbx+10h]
0x18008d91f  jz      short loc_18008D92B
0x18008d921  mov     [rdx], rax
0x18008d924  add     qword ptr [rbx+8], 8
0x18008d929  jmp     short loc_18008D938
0x18008d92b  lea     r8, [rsp+160h+var_130]
0x18008d930  mov     rcx, rbx
0x18008d933  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18008d938  mov     rcx, r14; dwBytes
0x18008d93b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d940  mov     rdi, rax
0x18008d943  mov     [rsp+160h+var_128], rax
0x18008d948  test    rax, rax
0x18008d94b  jz      short loc_18008D96E
0x18008d94d  lea     rdx, [rbp+60h+var_80]
0x18008d951  lea     rcx, [rsp+160h+var_120]
0x18008d956  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d95b  mov     r8, rax
0x18008d95e  lea     rdx, aShutdowntype; "ShutdownType"
0x18008d965  mov     rcx, rdi
0x18008d968  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18008d96d  nop
0x18008d96e  mov     [rsp+160h+var_130], rax
0x18008d973  mov     rdx, [rbx+8]
0x18008d977  cmp     rdx, [rbx+10h]
0x18008d97b  jz      short loc_18008D987
0x18008d97d  mov     [rdx], rax
0x18008d980  add     qword ptr [rbx+8], 8
0x18008d985  jmp     short loc_18008D994
0x18008d987  lea     r8, [rsp+160h+var_130]
0x18008d98c  mov     rcx, rbx
0x18008d98f  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18008d994  mov     rcx, r14; dwBytes
0x18008d997  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d99c  mov     rdi, rax
0x18008d99f  mov     [rsp+160h+var_128], rax
0x18008d9a4  test    rax, rax
0x18008d9a7  jz      short loc_18008D9CA
0x18008d9a9  lea     rdx, [rbp+60h+var_40]
0x18008d9ad  lea     rcx, [rsp+160h+var_120]
0x18008d9b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d9b7  mov     r8, rax
  ... truncated ...
```
