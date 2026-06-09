# SystemEventLogTroubleshooter::ProcessSystemResumeEvent(void *,unsigned __int64)

- ea: `0x180009d88`
- end: `0x18000ab81`
- name: `?ProcessSystemResumeEvent@SystemEventLogTroubleshooter@@AEAAXPEAX_K@Z`
- size: `3577`
- prototype: `void(SystemEventLogTroubleshooter *__hidden this, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x18002f3ec`

## callees

- `0x180008740`
- `0x180008da0`
- `0x180009d88`
- `0x18000b6f0`
- `0x18000b734`
- `0x18001c8cc`
- `0x18001f17c`
- `0x18001f6f4`
- `0x18001fcac`
- `0x180020454`
- `0x1800253e0`
- `0x18002aa98`
- `0x18002ab50`
- `0x18002ab7c`
- `0x180033a70`
- `0x1800369b0`
- `0x180036c88`
- `0x180037090`
- `0x18003bb60`
- `0x18003bf74`
- `0x1800446f8`
- `0x18004ca90`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000aaa6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000aaa6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009e63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009e92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ec1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ef0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f86`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a01e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a050`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a082`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a0ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a10a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a13e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a18a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009e63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009e92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ec1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ef0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f86`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009fea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a01e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a050`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a082`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a0ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a10a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a13e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a18a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1e0`

## string_xrefs

- `0x180009f64`: `HiberWriteDuration`
- `0x18000a505`: `HiberWriteDuration`
- `0x180009f32`: `HiberReadDuration`
- `0x18000a4b1`: `HiberReadDuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall SystemEventLogTroubleshooter::ProcessSystemResumeEvent(
        SystemEventLogTroubleshooter *this,
        void *a2,
        __int64 a3)
{
  __int128 v4; // xmm0
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // r12
  __int64 v11; // r13
  unsigned int EventProperty; // edi
  void *v13; // rsi
  unsigned int v14; // edi
  void *v15; // rsi
  unsigned int v16; // ebx
  void *v17; // rdi
  SystemEventLogTroubleshooter *v18; // rbx
  void *v19; // rax
  __int64 v20; // rdi
  _BYTE *v21; // rax
  __int64 v22; // rcx
  _BYTE *v23; // rdx
  __int64 v24; // rsi
  void *v25; // rax
  __int64 v26; // rcx
  _BYTE *v27; // rdx
  void *v28; // rax
  _BYTE *v29; // rdx
  void *v30; // rax
  void *v31; // rax
  _BYTE *v32; // rdx
  void *v33; // rax
  void *v34; // rax
  _BYTE *v35; // rdx
  void *v36; // rax
  void *v37; // rax
  _BYTE *v38; // rdx
  void *v39; // rax
  void *v40; // rax
  _BYTE *v41; // rdx
  void *v42; // rax
  void *v43; // rax
  _BYTE *v44; // rdx
  void *v45; // rax
  void *v46; // rax
  _BYTE *v47; // rdx
  void *v48; // rax
  void *v49; // rax
  _BYTE *v50; // rdx
  void *v51; // rax
  void *v52; // rax
  _BYTE *v53; // rdx
  void *v54; // rax
  void *v55; // rax
  _BYTE *v56; // rdx
  void *v57; // rax
  void *v58; // rax
  _BYTE *v59; // rdx
  void *v60; // rax
  void *v61; // rax
  _BYTE *v62; // rdx
  void *v63; // rdi
  __int64 v64; // rax
  void *v65; // rax
  _BYTE *v66; // rdx
  void *v67; // rax
  __int64 v68; // r14
  void *v69; // rax
  _BYTE *v70; // rdx
  void *v71; // rax
  void *v72; // rax
  _BYTE *v73; // rdx
  void *v74; // rdi
  __int64 v75; // rax
  void *v76; // rax
  _BYTE *v77; // rdx
  void *v78; // rdi
  __int64 v79; // rax
  void *v80; // rax
  _BYTE *v81; // rdx
  __int64 v82; // rbx
  __int64 v83; // rax
  __int128 *v84; // rdx
  void *v85; // rax
  SystemEventLogTroubleshooter *v86; // rdi
  __int64 v87; // rax
  __int64 v88; // rcx
  _BYTE *v89; // rdx
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  void *v91; // [rsp+38h] [rbp-C8h]
  __int64 v92; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v93; // [rsp+48h] [rbp-B8h]
  unsigned int v94; // [rsp+4Ch] [rbp-B4h]
  __int64 v95; // [rsp+50h] [rbp-B0h]
  unsigned int v96; // [rsp+58h] [rbp-A8h]
  unsigned int v97; // [rsp+5Ch] [rbp-A4h]
  unsigned int v98; // [rsp+60h] [rbp-A0h]
  unsigned int v99; // [rsp+64h] [rbp-9Ch]
  unsigned int v100; // [rsp+68h] [rbp-98h]
  unsigned int v101; // [rsp+6Ch] [rbp-94h]
  SystemEventLogTroubleshooter *v102; // [rsp+70h] [rbp-90h]
  _BYTE v103[16]; // [rsp+80h] [rbp-80h] BYREF
  char v104[8]; // [rsp+90h] [rbp-70h] BYREF
  char v105[128]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v106[104]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v107; // [rsp+180h] [rbp+80h] BYREF
  __int64 v108; // [rsp+190h] [rbp+90h]
  unsigned __int64 v109; // [rsp+198h] [rbp+98h]
  __int128 v110; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v111; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v112; // [rsp+1B8h] [rbp+B8h]
  __int128 v113; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v114; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v115; // [rsp+1D8h] [rbp+D8h]
  void *v116[3]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int64 v117; // [rsp+1F8h] [rbp+F8h]

  v95 = a3;
  v102 = this;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v103);
  v4 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v107);
  v113 = v4;
  v114 = 0;
  v115 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v113);
  v110 = v4;
  v111 = 0;
  v112 = 0;
  std::wstring::_Construct_empty(&v110);
  Block = 0;
  if ( GetEventProperty(a2, L"Attributes", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v8 = *(unsigned int *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"BiosInitDuration", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v9 = *(unsigned int *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"DriverInitDuration", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v10 = *(unsigned int *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"EffectiveState", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v11 = *(unsigned int *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"HiberPagesWritten", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v96 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"HiberReadDuration", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v97 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"HiberWriteDuration", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v98 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"NoMultiStageResumeReason", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v99 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"SleepDuration", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v100 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"SleepTime", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v91 = *(void **)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"TargetState", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v101 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"WakeDuration", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v94 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  EventProperty = GetEventProperty(a2, L"WakeSourceText", (struct _EVT_VARIANT **)&Block);
  if ( EventProperty )
    goto LABEL_168;
  v13 = Block;
  if ( *(_QWORD *)Block )
    std::wstring::assign(&v107, *(_QWORD *)Block);
  else
    EventProperty = 13;
  free(v13);
  if ( EventProperty )
    goto LABEL_168;
  Block = 0;
  if ( GetEventProperty(a2, L"WakeSourceType", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v93 = *(_DWORD *)Block;
  free(Block);
  Block = 0;
  if ( GetEventProperty(a2, L"WakeTime", (struct _EVT_VARIANT **)&Block) )
    goto LABEL_168;
  v92 = *(_QWORD *)Block;
  free(Block);
  Block = 0;
  v14 = GetEventProperty(a2, L"WakeTimerContext", (struct _EVT_VARIANT **)&Block);
  if ( v14 )
    goto LABEL_168;
  v15 = Block;
  if ( *(_QWORD *)Block )
    std::wstring::assign(&v113, *(_QWORD *)Block);
  else
    v14 = 13;
  free(v15);
  if ( v14 )
    goto LABEL_168;
  Block = 0;
  v16 = GetEventProperty(a2, L"WakeTimerOwner", (struct _EVT_VARIANT **)&Block);
  if ( v16 )
    goto LABEL_168;
  v17 = Block;
  if ( *(_QWORD *)Block )
    std::wstring::assign(&v110, *(_QWORD *)Block);
  else
    v16 = 13;
  free(v17);
  if ( v16 )
  {
LABEL_168:
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v110);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v113);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v107);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v103);
  }
  else
  {
    v18 = v102;
    if ( *(_QWORD *)(*((_QWORD *)v102 + 4) + 8LL) == **((_QWORD **)v102 + 4) )
    {
      v19 = operator new(0x1E0u);
      Block = v19;
      v20 = v95;
      if ( v19 )
        v21 = (_BYTE *)OsStateInstance::OsStateInstance((__int64)v19, 3, v95, *((_DWORD *)v18 + 10), 0);
      else
        v21 = 0;
      Block = v21;
      v21[32] = 0;
      v22 = *((_QWORD *)v18 + 4);
      v23 = *(_BYTE **)(v22 + 8);
      if ( v23 == *(_BYTE **)(v22 + 16) )
      {
        std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
          (void **)v22,
          v23,
          (__int64 *)&Block);
      }
      else
      {
        *(_QWORD *)v23 = v21;
        *(_QWORD *)(v22 + 8) += 8LL;
      }
    }
    else
    {
      v20 = v95;
    }
    v24 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v18 + 4) + 8LL) - 8LL);
    if ( !(unsigned int)IsSystemSleep(PowerSystemWorking, (struct OsStateInstance *)v24) )
    {
      *(_QWORD *)(v24 + 96) = v20;
      v25 = operator new(0x1E0u);
      Block = v25;
      if ( v25 )
        v24 = OsStateInstance::OsStateInstance((__int64)v25, 3, v20, *((_DWORD *)v18 + 10), 0);
      else
        v24 = 0;
      Block = (void *)v24;
      *(_BYTE *)(v24 + 32) = 0;
      v26 = *((_QWORD *)v18 + 4);
      v27 = *(_BYTE **)(v26 + 8);
      if ( v27 == *(_BYTE **)(v26 + 16) )
      {
        std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
          (void **)v26,
          v27,
          (__int64 *)&Block);
        v24 = (__int64)Block;
      }
      else
      {
        *(_QWORD *)v27 = v24;
        *(_QWORD *)(v26 + 8) += 8LL;
      }
    }
    v28 = operator new(0x50u);
    Block = v28;
    if ( v28 )
      v28 = (void *)CustomData::CustomData(v28, L"Attributes", v8, 0);
    Block = v28;
    v29 = *(_BYTE **)(v24 + 216);
    if ( v29 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v29,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v29 = v28;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v30 = operator new(0x50u);
    Block = v30;
    if ( v30 )
      v31 = (void *)CustomData::CustomData(v30, L"BiosInitDuration", v9, 0);
    else
      v31 = 0;
    Block = v31;
    v32 = *(_BYTE **)(v24 + 216);
    if ( v32 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v32,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v32 = v31;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v33 = operator new(0x50u);
    Block = v33;
    if ( v33 )
      v34 = (void *)CustomData::CustomData(v33, L"DriverInitDuration", v10, 0);
    else
      v34 = 0;
    Block = v34;
    v35 = *(_BYTE **)(v24 + 216);
    if ( v35 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v35,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v35 = v34;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v36 = operator new(0x50u);
    Block = v36;
    if ( v36 )
      v37 = (void *)CustomData::CustomData(v36, L"EffectiveState", v11, 0);
    else
      v37 = 0;
    Block = v37;
    v38 = *(_BYTE **)(v24 + 216);
    if ( v38 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v38,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v38 = v37;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v39 = operator new(0x50u);
    Block = v39;
    if ( v39 )
      v40 = (void *)CustomData::CustomData(v39, L"HiberPagesWritten", v96, 0);
    else
      v40 = 0;
    Block = v40;
    v41 = *(_BYTE **)(v24 + 216);
    if ( v41 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v41,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v41 = v40;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v42 = operator new(0x50u);
    Block = v42;
    if ( v42 )
      v43 = (void *)CustomData::CustomData(v42, L"HiberReadDuration", v97, 0);
    else
      v43 = 0;
    Block = v43;
    v44 = *(_BYTE **)(v24 + 216);
    if ( v44 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v44,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v44 = v43;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v45 = operator new(0x50u);
    Block = v45;
    if ( v45 )
      v46 = (void *)CustomData::CustomData(v45, L"HiberWriteDuration", v98, 0);
    else
      v46 = 0;
    Block = v46;
    v47 = *(_BYTE **)(v24 + 216);
    if ( v47 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v47,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v47 = v46;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v48 = operator new(0x50u);
    Block = v48;
    if ( v48 )
      v49 = (void *)CustomData::CustomData(v48, L"NoMultiStageResumeReason", v99, 0);
    else
      v49 = 0;
    Block = v49;
    v50 = *(_BYTE **)(v24 + 216);
    if ( v50 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v50,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v50 = v49;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v51 = operator new(0x50u);
    Block = v51;
    if ( v51 )
      v52 = (void *)CustomData::CustomData(v51, L"SleepDuration", v100, 0);
    else
      v52 = 0;
    Block = v52;
    v53 = *(_BYTE **)(v24 + 216);
    if ( v53 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v53,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v53 = v52;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v54 = operator new(0x50u);
    Block = v54;
    if ( v54 )
      v55 = (void *)CustomData::CustomData(v54, L"SleepTime", v91, 2);
    else
      v55 = 0;
    Block = v55;
    v56 = *(_BYTE **)(v24 + 216);
    if ( v56 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v56,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v56 = v55;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v57 = operator new(0x50u);
    v91 = v57;
    if ( v57 )
      v58 = (void *)CustomData::CustomData(v57, L"TargetState", v101, 0);
    else
      v58 = 0;
    Block = v58;
    v59 = *(_BYTE **)(v24 + 216);
    if ( v59 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v59,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v59 = v58;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v60 = operator new(0x50u);
    v91 = v60;
    if ( v60 )
      v61 = (void *)CustomData::CustomData(v60, L"WakeDuration", v94, 0);
    else
      v61 = 0;
    Block = v61;
    v62 = *(_BYTE **)(v24 + 216);
    if ( v62 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v62,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v62 = v61;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    if ( v108 )
    {
      v63 = operator new(0x50u);
      v91 = v63;
      if ( v63 )
      {
        v64 = std::wstring::wstring((__int64)v116, &v107);
        v65 = (void *)CustomData::CustomData(v63, L"WakeSourceText", v64);
      }
      else
      {
        v65 = 0;
      }
      Block = v65;
      v66 = *(_BYTE **)(v24 + 216);
      if ( v66 == *(_BYTE **)(v24 + 224) )
      {
        std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
          (void **)(v24 + 208),
          v66,
          (__int64 *)&Block);
      }
      else
      {
        *(_QWORD *)v66 = v65;
        *(_QWORD *)(v24 + 216) += 8LL;
      }
    }
    v67 = operator new(0x50u);
    v91 = v67;
    if ( v67 )
    {
      v68 = v93;
      v69 = (void *)CustomData::CustomData(v67, L"WakeSourceType", v93, 0);
    }
    else
    {
      v69 = 0;
      v68 = v93;
    }
    Block = v69;
    v70 = *(_BYTE **)(v24 + 216);
    if ( v70 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v70,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v70 = v69;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    v71 = operator new(0x50u);
    v91 = v71;
    if ( v71 )
      v72 = (void *)CustomData::CustomData(v71, L"WakeTime", v92, 2);
    else
      v72 = 0;
    Block = v72;
    v73 = *(_BYTE **)(v24 + 216);
    if ( v73 == *(_BYTE **)(v24 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v24 + 208),
        v73,
        (__int64 *)&Block);
    }
    else
    {
      *(_QWORD *)v73 = v72;
      *(_QWORD *)(v24 + 216) += 8LL;
    }
    if ( v114 )
    {
      v74 = operator new(0x50u);
      v92 = (__int64)v74;
      if ( v74 )
      {
        v75 = std::wstring::wstring((__int64)v116, &v113);
        v76 = (void *)CustomData::CustomData(v74, L"WakeTimerContext", v75);
      }
      else
      {
        v76 = 0;
      }
      Block = v76;
      v77 = *(_BYTE **)(v24 + 216);
      if ( v77 == *(_BYTE **)(v24 + 224) )
      {
        std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
          (void **)(v24 + 208),
          v77,
          (__int64 *)&Block);
      }
      else
      {
        *(_QWORD *)v77 = v76;
        *(_QWORD *)(v24 + 216) += 8LL;
      }
    }
    if ( v111 )
    {
      v78 = operator new(0x50u);
      v92 = (__int64)v78;
      if ( v78 )
      {
        v79 = std::wstring::wstring((__int64)v116, &v110);
        v80 = (void *)CustomData::CustomData(v78, L"WakeTimerOwner", v79);
      }
      else
      {
        v80 = 0;
      }
      Block = v80;
      v81 = *(_BYTE **)(v24 + 216);
      if ( v81 == *(_BYTE **)(v24 + 224) )
      {
        std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
          (void **)(v24 + 208),
          v81,
          (__int64 *)&Block);
      }
      else
      {
        *(_QWORD *)v81 = v80;
        *(_QWORD *)(v24 + 216) += 8LL;
      }
    }
    if ( (unsigned int)v68 >= 0xA )
      v68 = 9;
    *(_BYTE *)(v24 + 20) = 1;
    v82 = v95;
    *(_QWORD *)(v24 + 96) = v95;
    *(_BYTE *)(v24 + 104) = 1;
    *(_DWORD *)(v24 + 152) = 5;
    v83 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v104, (__int64)(&WakeReasons)[v68]);
    v84 = &v107;
    if ( v109 > 7 )
      v84 = (__int128 *)v107;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v83, v84, v108);
    std::basic_stringbuf<unsigned short>::str(v105, v116);
    std::wstring::operator=(v24 + 120, v116);
    if ( v117 > 7 )
      std::_Deallocate<16>(v116[0], 2 * v117 + 2);
    v85 = operator new(0x1E0u);
    v92 = (__int64)v85;
    v86 = v102;
    if ( v85 )
      v87 = OsStateInstance::OsStateInstance((__int64)v85, 1, v82, *((_DWORD *)v102 + 10), 0);
    else
      v87 = 0;
    v92 = v87;
    *(_DWORD *)(v87 + 36) = 0;
    v88 = *((_QWORD *)v86 + 4);
    v89 = *(_BYTE **)(v88 + 8);
    if ( v89 == *(_BYTE **)(v88 + 16) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)v88,
        v89,
        &v92);
    }
    else
    {
      *(_QWORD *)v89 = v87;
      *(_QWORD *)(v88 + 8) += 8LL;
    }
    if ( v112 > 7 )
      std::_Deallocate<16>((void *)v110, 2 * v112 + 2);
    v111 = 0;
    v112 = 7;
    LOWORD(v110) = 0;
    if ( v115 > 7 )
      std::_Deallocate<16>((void *)v113, 2 * v115 + 2);
    v114 = 0;
    v115 = 7;
    LOWORD(v113) = 0;
    if ( v109 > 7 )
      std::_Deallocate<16>((void *)v107, 2 * v109 + 2);
    v108 = 0;
    v109 = 7;
    LOWORD(v107) = 0;
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v106);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v106);
  }
}

```

## disassembly

```asm
0x180009d88  mov     [rsp-8+arg_18], rbx
0x180009d8d  push    rbp
0x180009d8e  push    rsi
0x180009d8f  push    rdi
0x180009d90  push    r12
0x180009d92  push    r13
0x180009d94  push    r14
0x180009d96  push    r15
0x180009d98  lea     rbp, [rsp-110h]
0x180009da0  sub     rsp, 210h
0x180009da7  mov     rax, cs:__security_cookie
0x180009dae  xor     rax, rsp
0x180009db1  mov     [rbp+140h+var_40], rax
0x180009db8  mov     [rsp+240h+var_1F0], r8
0x180009dbd  mov     rbx, rdx
0x180009dc0  mov     [rsp+240h+var_1D0], rcx
0x180009dc5  xor     esi, esi
0x180009dc7  lea     rcx, [rbp+140h+var_1C0]
0x180009dcb  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180009dd0  nop
0x180009dd1  xorps   xmm0, xmm0
0x180009dd4  movups  [rbp+140h+var_C0], xmm0
0x180009ddb  mov     [rbp+140h+var_B0], rsi
0x180009de2  mov     [rbp+140h+var_A8], rsi
0x180009de9  lea     rcx, [rbp+140h+var_C0]
0x180009df0  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x180009df5  nop
0x180009df6  movups  [rbp+140h+var_80], xmm0
0x180009dfd  mov     [rbp+140h+var_70], rsi
0x180009e04  mov     [rbp+140h+var_68], rsi
0x180009e0b  lea     rcx, [rbp+140h+var_80]
0x180009e12  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x180009e17  nop
0x180009e18  movups  [rbp+140h+var_A0], xmm0
0x180009e1f  mov     [rbp+140h+var_90], rsi
0x180009e26  mov     [rbp+140h+var_88], rsi
0x180009e2d  lea     rcx, [rbp+140h+var_A0]
0x180009e34  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ
0x180009e39  nop
0x180009e3a  mov     [rsp+240h+Block], rsi
0x180009e3f  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009e44  lea     rdx, aAttributes
0x180009e4b  mov     rcx, rbx; void *
0x180009e4e  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009e53  test    eax, eax
0x180009e55  jnz     loc_18000AB21
0x180009e5b  mov     rcx, [rsp+240h+Block]; Block
0x180009e60  mov     r14d, [rcx]
0x180009e63  call    cs:__imp_free
0x180009e69  mov     [rsp+240h+Block], rsi
0x180009e6e  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009e73  lea     rdx, aBiosinitdurati
0x180009e7a  mov     rcx, rbx; void *
0x180009e7d  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009e82  test    eax, eax
0x180009e84  jnz     loc_18000AB1A
0x180009e8a  mov     rcx, [rsp+240h+Block]; Block
0x180009e8f  mov     r15d, [rcx]
0x180009e92  call    cs:__imp_free
0x180009e98  mov     [rsp+240h+Block], rsi
0x180009e9d  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009ea2  lea     rdx, aDriverinitdura
0x180009ea9  mov     rcx, rbx; void *
0x180009eac  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009eb1  test    eax, eax
0x180009eb3  jnz     loc_18000AB13
0x180009eb9  mov     rcx, [rsp+240h+Block]; Block
0x180009ebe  mov     r12d, [rcx]
0x180009ec1  call    cs:__imp_free
0x180009ec7  mov     [rsp+240h+Block], rsi
0x180009ecc  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009ed1  lea     rdx, aEffectivestate
0x180009ed8  mov     rcx, rbx; void *
0x180009edb  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009ee0  test    eax, eax
0x180009ee2  jnz     loc_18000AB0C
0x180009ee8  mov     rcx, [rsp+240h+Block]; Block
0x180009eed  mov     r13d, [rcx]
0x180009ef0  call    cs:__imp_free
0x180009ef6  mov     [rsp+240h+Block], rsi
0x180009efb  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009f00  lea     rdx, aHiberpageswrit
0x180009f07  mov     rcx, rbx; void *
0x180009f0a  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009f0f  test    eax, eax
0x180009f11  jnz     loc_18000AB05
0x180009f17  mov     rcx, [rsp+240h+Block]; Block
0x180009f1c  mov     eax, [rcx]
0x180009f1e  mov     [rsp+240h+var_1E8], eax
0x180009f22  call    cs:__imp_free
0x180009f28  mov     [rsp+240h+Block], rsi
0x180009f2d  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009f32  lea     rdx, aHiberreaddurat
0x180009f39  mov     rcx, rbx; void *
0x180009f3c  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009f41  test    eax, eax
0x180009f43  jnz     loc_18000AAFE
0x180009f49  mov     rcx, [rsp+240h+Block]; Block
0x180009f4e  mov     eax, [rcx]
0x180009f50  mov     [rsp+240h+var_1E4], eax
0x180009f54  call    cs:__imp_free
0x180009f5a  mov     [rsp+240h+Block], rsi
0x180009f5f  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009f64  lea     rdx, aHiberwritedura
0x180009f6b  mov     rcx, rbx; void *
0x180009f6e  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009f73  test    eax, eax
0x180009f75  jnz     loc_18000AAF7
0x180009f7b  mov     rcx, [rsp+240h+Block]; Block
0x180009f80  mov     eax, [rcx]
0x180009f82  mov     [rsp+240h+var_1E0], eax
0x180009f86  call    cs:__imp_free
0x180009f8c  mov     [rsp+240h+Block], rsi
0x180009f91  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009f96  lea     rdx, aNomultistagere
0x180009f9d  mov     rcx, rbx; void *
0x180009fa0  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009fa5  test    eax, eax
0x180009fa7  jnz     loc_18000AAF0
0x180009fad  mov     rcx, [rsp+240h+Block]; Block
0x180009fb2  mov     eax, [rcx]
0x180009fb4  mov     [rsp+240h+var_1DC], eax
0x180009fb8  call    cs:__imp_free
0x180009fbe  mov     [rsp+240h+Block], rsi
0x180009fc3  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009fc8  lea     rdx, aSleepduration
0x180009fcf  mov     rcx, rbx; void *
0x180009fd2  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x180009fd7  test    eax, eax
0x180009fd9  jnz     loc_18000AAE9
0x180009fdf  mov     rcx, [rsp+240h+Block]; Block
0x180009fe4  mov     eax, [rcx]
0x180009fe6  mov     [rsp+240h+var_1D8], eax
0x180009fea  call    cs:__imp_free
0x180009ff0  mov     [rsp+240h+Block], rsi
0x180009ff5  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x180009ffa  lea     rdx, aSleeptime
0x18000a001  mov     rcx, rbx; void *
0x18000a004  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a009  test    eax, eax
0x18000a00b  jnz     loc_18000AAE2
0x18000a011  mov     rcx, [rsp+240h+Block]; Block
0x18000a016  mov     rax, [rcx]
0x18000a019  mov     [rsp+240h+var_208], rax
0x18000a01e  call    cs:__imp_free
0x18000a024  mov     [rsp+240h+Block], rsi
0x18000a029  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a02e  lea     rdx, aTargetstate
0x18000a035  mov     rcx, rbx; void *
0x18000a038  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a03d  test    eax, eax
0x18000a03f  jnz     loc_18000AADB
0x18000a045  mov     rcx, [rsp+240h+Block]; Block
0x18000a04a  mov     eax, [rcx]
0x18000a04c  mov     [rsp+240h+var_1D4], eax
0x18000a050  call    cs:__imp_free
0x18000a056  mov     [rsp+240h+Block], rsi
0x18000a05b  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a060  lea     rdx, aWakeduration
0x18000a067  mov     rcx, rbx; void *
0x18000a06a  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a06f  test    eax, eax
0x18000a071  jnz     loc_18000AAD4
0x18000a077  mov     rcx, [rsp+240h+Block]; Block
0x18000a07c  mov     eax, [rcx]
0x18000a07e  mov     [rsp+240h+var_1F4], eax
0x18000a082  call    cs:__imp_free
0x18000a088  mov     [rsp+240h+Block], rsi
0x18000a08d  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a092  lea     rdx, aWakesourcetext
0x18000a099  mov     rcx, rbx; void *
0x18000a09c  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a0a1  mov     edi, eax
0x18000a0a3  test    eax, eax
0x18000a0a5  jnz     loc_18000AACD
0x18000a0ab  mov     rsi, [rsp+240h+Block]
0x18000a0b0  mov     rdx, [rsi]
0x18000a0b3  test    rdx, rdx
0x18000a0b6  jz      short loc_18000A0C6
0x18000a0b8  lea     rcx, [rbp+140h+var_C0]
0x18000a0bf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z
0x18000a0c4  jmp     short loc_18000A0CB
0x18000a0c6  mov     edi, 0Dh
0x18000a0cb  mov     rcx, rsi; Block
0x18000a0ce  call    cs:__imp_free
0x18000a0d4  xor     esi, esi
0x18000a0d6  test    edi, edi
0x18000a0d8  jnz     loc_18000AACD
0x18000a0de  mov     [rsp+240h+Block], rsi
0x18000a0e3  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a0e8  lea     rdx, aWakesourcetype
0x18000a0ef  mov     rcx, rbx; void *
0x18000a0f2  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a0f7  test    eax, eax
0x18000a0f9  jnz     loc_18000AAC6
0x18000a0ff  mov     rcx, [rsp+240h+Block]; Block
0x18000a104  mov     eax, [rcx]
0x18000a106  mov     [rsp+240h+var_1F8], eax
0x18000a10a  call    cs:__imp_free
0x18000a110  mov     [rsp+240h+Block], rsi
0x18000a115  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a11a  lea     rdx, aWaketime
0x18000a121  mov     rcx, rbx; void *
0x18000a124  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a129  test    eax, eax
0x18000a12b  jnz     loc_18000AABF
0x18000a131  mov     rcx, [rsp+240h+Block]; Block
0x18000a136  mov     rax, [rcx]
0x18000a139  mov     [rsp+240h+var_200], rax
0x18000a13e  call    cs:__imp_free
0x18000a144  mov     [rsp+240h+Block], rsi
0x18000a149  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a14e  lea     rdx, aWaketimerconte
0x18000a155  mov     rcx, rbx; void *
0x18000a158  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a15d  mov     edi, eax
0x18000a15f  test    eax, eax
0x18000a161  jnz     loc_18000AAB8
0x18000a167  mov     rsi, [rsp+240h+Block]
0x18000a16c  mov     rdx, [rsi]
0x18000a16f  test    rdx, rdx
0x18000a172  jz      short loc_18000A182
0x18000a174  lea     rcx, [rbp+140h+var_80]
0x18000a17b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z
0x18000a180  jmp     short loc_18000A187
0x18000a182  mov     edi, 0Dh
0x18000a187  mov     rcx, rsi; Block
0x18000a18a  call    cs:__imp_free
0x18000a190  xor     esi, esi
0x18000a192  test    edi, edi
0x18000a194  jnz     loc_18000AAB8
0x18000a19a  mov     [rsp+240h+Block], rsi
0x18000a19f  lea     r8, [rsp+240h+Block]; struct _EVT_VARIANT **
0x18000a1a4  lea     rdx, aWaketimerowner
0x18000a1ab  mov     rcx, rbx; void *
0x18000a1ae  call    ?GetEventProperty@@YAKPEAXPEBGPEAPEAU_EVT_VARIANT@@@Z
0x18000a1b3  mov     ebx, eax
0x18000a1b5  test    eax, eax
0x18000a1b7  jnz     loc_18000AAB1
0x18000a1bd  mov     rdi, [rsp+240h+Block]
0x18000a1c2  mov     rdx, [rdi]
0x18000a1c5  test    rdx, rdx
0x18000a1c8  jz      short loc_18000A1D8
0x18000a1ca  lea     rcx, [rbp+140h+var_A0]
0x18000a1d1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z
0x18000a1d6  jmp     short loc_18000A1DD
0x18000a1d8  mov     ebx, 0Dh
0x18000a1dd  mov     rcx, rdi; Block
0x18000a1e0  call    cs:__imp_free
0x18000a1e6  test    ebx, ebx
0x18000a1e8  jnz     loc_18000AAB1
0x18000a1ee  mov     rbx, [rsp+240h+var_1D0]
0x18000a1f3  mov     rax, [rbx+20h]
0x18000a1f7  mov     rcx, [rax+8]
0x18000a1fb  cmp     rcx, [rax]
0x18000a1fe  jnz     short loc_18000A264
0x18000a200  mov     ecx, 1E0h; dwBytes
0x18000a205  call    ??2@YAPEAX_K@Z
0x18000a20a  mov     [rsp+240h+Block], rax
0x18000a20f  mov     rdi, [rsp+240h+var_1F0]
0x18000a214  test    rax, rax
0x18000a217  jz      short loc_18000A234
0x18000a219  mov     [rsp+240h+var_220], sil
0x18000a21e  mov     r9d, [rbx+28h]
0x18000a222  mov     r8, rdi
0x18000a225  mov     edx, 3
0x18000a22a  mov     rcx, rax
0x18000a22d  call    ??0OsStateInstance@@QEAA@W4OsStateInstanceType@@_KW4OsStatePowerSourceType@@E@Z
0x18000a232  jmp     short loc_18000A237
0x18000a234  mov     rax, rsi
0x18000a237  mov     [rsp+240h+Block], rax
0x18000a23c  mov     [rax+20h], sil
0x18000a240  mov     rcx, [rbx+20h]
0x18000a244  mov     rdx, [rcx+8]
0x18000a248  cmp     rdx, [rcx+10h]
0x18000a24c  jz      short loc_18000A258
0x18000a24e  mov     [rdx], rax
0x18000a251  add     qword ptr [rcx+8], 8
0x18000a256  jmp     short loc_18000A269
0x18000a258  lea     r8, [rsp+240h+Block]
0x18000a25d  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z
0x18000a262  jmp     short loc_18000A269
0x18000a264  mov     rdi, [rsp+240h+var_1F0]
0x18000a269  mov     rax, [rbx+20h]
0x18000a26d  mov     rcx, [rax+8]
0x18000a271  mov     rsi, [rcx-8]
0x18000a275  mov     rdx, rsi; struct OsStateInstance *
0x18000a278  mov     ecx, 1; enum _SYSTEM_POWER_STATE
0x18000a27d  call    ?IsSystemSleep@@YAHW4_SYSTEM_POWER_STATE@@PEAVOsStateInstance@@@Z
0x18000a282  test    eax, eax
0x18000a284  jnz     short loc_18000A2EE
0x18000a286  mov     [rsi+60h], rdi
0x18000a28a  mov     ecx, 1E0h; dwBytes
0x18000a28f  call    ??2@YAPEAX_K@Z
0x18000a294  mov     [rsp+240h+Block], rax
0x18000a299  test    rax, rax
0x18000a29c  jz      short loc_18000A2BC
0x18000a29e  mov     [rsp+240h+var_220], 0
0x18000a2a3  mov     r9d, [rbx+28h]
0x18000a2a7  mov     r8, rdi
  ... truncated ...
```
