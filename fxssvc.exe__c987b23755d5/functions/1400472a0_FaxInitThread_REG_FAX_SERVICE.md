# FaxInitThread(_REG_FAX_SERVICE *)

- ea: `0x1400472a0`
- end: `0x140047b7f`
- name: `?FaxInitThread@@YAKPEAU_REG_FAX_SERVICE@@@Z`
- size: `2271`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140003a54`
- `0x140003be0`
- `0x140003d5c`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14000b544`
- `0x14000d680`
- `0x14002e978`
- `0x14002ea30`
- `0x1400326fc`
- `0x140043484`
- `0x1400458d0`
- `0x1400472a0`
- `0x14004a360`
- `0x14004a434`
- `0x14004c3cc`
- `0x14004da68`
- `0x14004dc88`
- `0x14004dd74`
- `0x14004df2c`
- `0x14005cbcc`
- `0x14005d870`
- `0x14005f97c`
- `0x140060da4`
- `0x140065df8`
- `0x1400703a8`
- `0x1400708c4`
- `0x14007ca0c`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140047405`
- `ADVAPI32!RegCloseKey` at `0x1400474eb`
- `ADVAPI32!RegCloseKey` at `0x140047405`
- `ADVAPI32!RegCloseKey` at `0x1400474eb`
- `KERNEL32!GetLastError` at `0x14004735f`
- `KERNEL32!GetLastError` at `0x14004745c`
- `KERNEL32!GetLastError` at `0x140047648`
- `KERNEL32!GetLastError` at `0x140047703`
- `KERNEL32!GetLastError` at `0x140047753`
- `KERNEL32!GetLastError` at `0x140047930`
- `KERNEL32!GetLastError` at `0x14004798d`
- `KERNEL32!GetLastError` at `0x1400479dc`
- `KERNEL32!GetLastError` at `0x140047a2e`
- `KERNEL32!GetLastError` at `0x140047a6d`
- `KERNEL32!GetLastError` at `0x140047aac`
- `KERNEL32!GetLastError` at `0x140047aeb`
- `KERNEL32!GetLastError` at `0x14004735f`
- `KERNEL32!GetLastError` at `0x14004745c`
- `KERNEL32!GetLastError` at `0x140047648`
- `KERNEL32!GetLastError` at `0x140047703`
- `KERNEL32!GetLastError` at `0x140047753`
- `KERNEL32!GetLastError` at `0x140047930`
- `KERNEL32!GetLastError` at `0x14004798d`
- `KERNEL32!GetLastError` at `0x1400479dc`
- `KERNEL32!GetLastError` at `0x140047a2e`
- `KERNEL32!GetLastError` at `0x140047a6d`
- `KERNEL32!GetLastError` at `0x140047aac`
- `KERNEL32!GetLastError` at `0x140047aeb`
- `KERNEL32!EnterCriticalSection` at `0x14004786f`
- `KERNEL32!EnterCriticalSection` at `0x14004786f`
- `KERNEL32!LeaveCriticalSection` at `0x1400478bb`
- `KERNEL32!LeaveCriticalSection` at `0x1400478bb`
- `KERNEL32!CreateEventW` at `0x140047a1c`
- `KERNEL32!CreateEventW` at `0x140047a1c`
- `KERNEL32!CreateWaitableTimerW` at `0x1400479ca`
- `KERNEL32!CreateWaitableTimerW` at `0x1400479ca`
- `USER32!SendMessageW` at `0x140047b45`
- `USER32!SendMessageW` at `0x140047b45`
- `USER32!FindWindowW` at `0x140047b2a`
- `USER32!FindWindowW` at `0x140047b2a`

## pseudocode

```c
__int64 __fastcall FaxInitThread(struct _REG_FAX_SERVICE *Parameter)
{
  CMapDeviceId *v2; // rcx
  CFaxAccountList *v3; // rdi
  HKEY v4; // rax
  HKEY v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // ebx
  CMapDeviceId *v8; // rcx
  HKEY v9; // rax
  HKEY v10; // rdi
  DWORD v11; // eax
  unsigned int v12; // ebx
  CMapDeviceId *v13; // rcx
  unsigned int v14; // eax
  DWORD updated; // ebx
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD v19; // eax
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  struct _REG_FAX_SERVICE *v22; // rcx
  DWORD v23; // eax
  unsigned int v24; // edx
  DWORD v25; // eax
  CMapDeviceId *v26; // rcx
  DWORD v27; // eax
  struct _DEVICE_PROVIDER *v28; // rdx
  int v29; // r8d
  bool v30; // zf
  int v31; // eax
  DWORD_PTR *v32; // rbx
  DWORD_PTR *v33; // rcx
  COutboundRoutingGroupsMap *v34; // rcx
  COutboundRoutingGroupsMap *v35; // rcx
  CMapDeviceId *v36; // rcx
  __int64 v37; // rdx
  COutboundRulesMap *v38; // rcx
  COutboundRulesMap *v39; // rcx
  HWND WindowW; // rax
  unsigned __int16 v42[14]; // [rsp+34h] [rbp-2Ch] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = g_pAccountList;
  if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v2 + 2), 56, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  v4 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax", 0, 0x20019u);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v3 + 4) = 1;
    EnumerateRegistryKeys((_DWORD)v4, (unsigned int)L"Accounts", 0, (unsigned int)RegEnumAccountsCB, 0);
    RegCloseKey(v5);
    goto LABEL_20;
  }
  LastError = GetLastError();
  v7 = LastError;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Fax",
      LastError);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    if ( v8 == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_25;
    if ( (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 76, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v7);
LABEL_20:
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( v8 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v8 + 2), 81, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
LABEL_25:
  v9 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Accounts", 0, 0x20019u);
  v10 = v9;
  if ( v9 )
  {
    v14 = CFaxAccount::Load(g_pAccountDefaults, v9, 0);
    v12 = v14;
    if ( v14
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, v14);
    }
    RegCloseKey(v10);
    goto LABEL_36;
  }
  v11 = GetLastError();
  v12 = v11;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Fax\\Accounts",
      v11);
LABEL_36:
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12
    && v13 != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v13 + 28) & 4) != 0
    && *((_BYTE *)v13 + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)v13 + 2), 77, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v12);
  }
  updated = InitializeServerQuota();
  if ( updated )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_48;
    }
    v17 = 78;
LABEL_47:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, updated);
LABEL_48:
    v42[0] = 0;
    StringCchPrintfW(v42, 0xCu, L"%ld", updated);
    v18 = 3221257516LL;
LABEL_49:
    FaxLog(1, 1, 1, v18);
    goto LABEL_158;
  }
  v19 = InitializeServerSecurity();
  updated = v19;
  if ( v19 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 79;
LABEL_55:
      WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v19);
      goto LABEL_158;
    }
    goto LABEL_158;
  }
  if ( !(unsigned int)LoadDeviceProviders(Parameter) )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    }
  }
  if ( !(unsigned int)InitializeJobManager(v22) )
  {
    updated = 31;
    goto LABEL_158;
  }
  if ( (unsigned int)InitializeRouting(Parameter) )
  {
    v23 = TapiInitialize(Parameter);
    updated = v23;
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v23);
      }
      v42[0] = 0;
      StringCchPrintfW(v42, 0xCu, L"%ld", updated);
      v18 = 3221257517LL;
      goto LABEL_49;
    }
    if ( !(unsigned int)InitializeDeviceProvidersConfiguration()
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v25);
    }
    g_dwDeviceCount += CreateVirtualDevices(Parameter, v24);
    if ( !(unsigned int)InitializeDeviceProviders() )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      v27 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v27);
    }
    v26 = WPP_GLOBAL_Control;
LABEL_85:
    v28 = g_DeviceProvidersListHead;
    v29 = 0;
    if ( g_DeviceProvidersListHead == (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead )
      goto LABEL_92;
    do
    {
      v30 = *((_DWORD *)v28 + 4) == 0;
      v31 = v29 + 1;
      v28 = *(struct _DEVICE_PROVIDER **)v28;
      if ( !v30 )
        v31 = v29;
      v29 = v31;
    }
    while ( v28 != (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead );
    if ( !v31 )
    {
LABEL_92:
      if ( v26 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 4) != 0 && *((_BYTE *)v26 + 25) >= 2u )
        WPP_SF_(*((_QWORD *)v26 + 2), 85, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
      FaxLog(1, 2, 0, 2147515687LL);
      v26 = WPP_GLOBAL_Control;
    }
    if ( !g_dwDeviceCount )
    {
      if ( v26 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 4) != 0 && *((_BYTE *)v26 + 25) >= 3u )
        WPP_SF_(*((_QWORD *)v26 + 2), 86, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
      FaxLog(1, 2, 0, 2147515674LL);
    }
    UpdateManualAnswerDevice();
    updated = UpdateDevicesFlags();
    if ( updated )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v17 = 87;
      goto LABEL_47;
    }
    EnterCriticalSection(&g_CsLine);
    v32 = (DWORD_PTR *)g_TapiLinesListHead;
    if ( g_TapiLinesListHead && (DWORD_PTR *)g_TapiLinesListHead != &g_TapiLinesListHead )
    {
      do
      {
        v33 = v32;
        v32 = (DWORD_PTR *)*v32;
        UpdateVirtualDeviceSendAndReceiveStatus(
          (struct _LINE_INFO *)v33,
          *((_DWORD *)v33 + 19) & 2,
          *((_DWORD *)v33 + 19) & 1);
      }
      while ( v32 != &g_TapiLinesListHead );
    }
    LeaveCriticalSection(&g_CsLine);
    UpdateReceiveEnabledDevicesCount();
    updated = COutboundRoutingGroupsMap::Load(v34);
    if ( updated )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_115;
      }
      v37 = 88;
    }
    else if ( (unsigned int)COutboundRoutingGroupsMap::UpdateAllDevicesGroup(v35) )
    {
      updated = COutboundRulesMap::Load(v38);
      if ( updated )
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_115;
        }
        v37 = 90;
      }
      else
      {
        if ( (unsigned int)COutboundRulesMap::CreateDefaultRule(v39) )
        {
          g_hQueueTimer = CreateWaitableTimerW(0, 0, 0);
          if ( !g_hQueueTimer )
          {
            updated = GetLastError();
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            v17 = 92;
            goto LABEL_47;
          }
          g_hJobQueueEvent = CreateEventW(0, 0, 0, 0);
          if ( !g_hJobQueueEvent )
          {
            updated = GetLastError();
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            v17 = 93;
            goto LABEL_47;
          }
          if ( !(unsigned int)CreateStatusThreads() )
          {
            updated = GetLastError();
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            v17 = 94;
            goto LABEL_47;
          }
          if ( !(unsigned int)CreateTapiThread() )
          {
            updated = GetLastError();
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            v17 = 95;
            goto LABEL_47;
          }
          if ( !(unsigned int)CreateJobQueueThread() )
          {
            updated = GetLastError();
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_48;
            }
            v17 = 96;
            goto LABEL_47;
          }
          WindowW = FindWindowW(L"SystemTray_Main", 0);
          if ( WindowW )
            SendMessageW(WindowW, 0x64u, 0, 1);
          goto LABEL_158;
        }
        updated = GetLastError();
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_115:
          v42[0] = 0;
          StringCchPrintfW(v42, 0xCu, L"%ld", updated);
          v18 = 3221257537LL;
          goto LABEL_49;
        }
        v37 = 91;
      }
    }
    else
    {
      updated = GetLastError();
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_115;
      }
      v37 = 89;
    }
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, updated);
    goto LABEL_115;
  }
  v19 = GetLastError();
  updated = v19;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 81;
    goto LABEL_55;
  }
LABEL_158:
  if ( Parameter )
    FreeFaxRegistry(Parameter);
  return updated;
}

```

## disassembly

```asm
0x1400472a0  mov     [rsp-28h+arg_8], rbx
0x1400472a5  mov     [rsp-28h+arg_10], rsi
0x1400472aa  push    rbp
0x1400472ab  push    rdi
0x1400472ac  push    r12
0x1400472ae  push    r13
0x1400472b0  push    r15
0x1400472b2  mov     rbp, rsp
0x1400472b5  sub     rsp, 60h
0x1400472b9  mov     rax, cs:__security_cookie
0x1400472c0  xor     rax, rsp
0x1400472c3  mov     [rbp+var_10], rax
0x1400472c7  mov     rsi, rcx
0x1400472ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400472d1  lea     r13, WPP_GLOBAL_Control
0x1400472d8  mov     r15b, 4
0x1400472db  cmp     rcx, r13
0x1400472de  jz      short loc_140047308
0x1400472e0  test    [rcx+1Ch], r15b
0x1400472e4  jz      short loc_140047308
0x1400472e6  cmp     byte ptr [rcx+19h], 5
0x1400472ea  jb      short loc_140047308
0x1400472ec  mov     rcx, [rcx+10h]
0x1400472f0  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x1400472f7  mov     edx, 4Bh ; 'K'
0x1400472fc  call    WPP_SF_
0x140047301  mov     rcx, cs:WPP_GLOBAL_Control
0x140047308  mov     rdi, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x14004730f  cmp     rcx, r13
0x140047312  jz      short loc_140047335
0x140047314  test    [rcx+1Ch], r15b
0x140047318  jz      short loc_140047335
0x14004731a  cmp     byte ptr [rcx+19h], 5
0x14004731e  jb      short loc_140047335
0x140047320  mov     rcx, [rcx+10h]
0x140047324  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004732b  mov     edx, 38h ; '8'
0x140047330  call    WPP_SF_
0x140047335  mov     r9d, 20019h
0x14004733b  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x140047342  xor     r8d, r8d
0x140047345  mov     rcx, 0FFFFFFFF80000002h
0x14004734c  call    OpenRegistryKey
0x140047351  mov     rbx, rax
0x140047354  mov     r12d, 2
0x14004735a  test    rax, rax
0x14004735d  jnz     short loc_1400473D9
0x14004735f  call    cs:__imp_GetLastError
0x140047365  mov     ebx, eax
0x140047367  mov     rcx, cs:WPP_GLOBAL_Control
0x14004736e  cmp     rcx, r13
0x140047371  jz      short loc_1400473A6
0x140047373  test    [rcx+1Ch], r15b
0x140047377  jz      short loc_1400473A6
0x140047379  cmp     [rcx+19h], r12b
0x14004737d  jb      short loc_1400473A6
0x14004737f  mov     rcx, [rcx+10h]
0x140047383  lea     edx, [r12+37h]
0x140047388  lea     r9, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14004738f  mov     dword ptr [rsp+60h+var_40], eax
0x140047393  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004739a  call    WPP_SF_Sd
0x14004739f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473a6  test    ebx, ebx
0x1400473a8  jz      short loc_140047412
0x1400473aa  cmp     rcx, r13
0x1400473ad  jz      loc_140047438
0x1400473b3  test    [rcx+1Ch], r15b
0x1400473b7  jz      short loc_140047412
0x1400473b9  cmp     [rcx+19h], r12b
0x1400473bd  jb      short loc_140047412
0x1400473bf  mov     rcx, [rcx+10h]
0x1400473c3  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x1400473ca  mov     edx, 4Ch ; 'L'
0x1400473cf  mov     r9d, ebx
0x1400473d2  call    WPP_SF_d
0x1400473d7  jmp     short loc_14004740B
0x1400473d9  lea     r9, RegEnumAccountsCB
0x1400473e0  mov     dword ptr [rdi+10h], 1
0x1400473e7  xor     r8d, r8d
0x1400473ea  mov     [rsp+60h+var_40], 0
0x1400473f3  lea     rdx, aAccounts; "Accounts"
0x1400473fa  mov     rcx, rbx
0x1400473fd  call    EnumerateRegistryKeys
0x140047402  mov     rcx, rbx; hKey
0x140047405  call    cs:__imp_RegCloseKey
0x14004740b  mov     rcx, cs:WPP_GLOBAL_Control
0x140047412  cmp     rcx, r13
0x140047415  jz      short loc_140047438
0x140047417  test    [rcx+1Ch], r15b
0x14004741b  jz      short loc_140047438
0x14004741d  cmp     byte ptr [rcx+19h], 5
0x140047421  jb      short loc_140047438
0x140047423  mov     rcx, [rcx+10h]
0x140047427  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14004742e  mov     edx, 51h ; 'Q'
0x140047433  call    WPP_SF_
0x140047438  mov     r9d, 20019h
0x14004743e  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Fax\\Accounts"
0x140047445  xor     r8d, r8d
0x140047448  mov     rcx, 0FFFFFFFF80000002h
0x14004744f  call    OpenRegistryKey
0x140047454  mov     rdi, rax
0x140047457  test    rax, rax
0x14004745a  jnz     short loc_1400474A0
0x14004745c  call    cs:__imp_GetLastError
0x140047462  mov     ebx, eax
0x140047464  mov     rcx, cs:WPP_GLOBAL_Control
0x14004746b  cmp     rcx, r13
0x14004746e  jz      loc_1400474F8
0x140047474  test    [rcx+1Ch], r15b
0x140047478  jz      short loc_1400474F8
0x14004747a  cmp     [rcx+19h], r12b
0x14004747e  jb      short loc_1400474F8
0x140047480  mov     rcx, [rcx+10h]
0x140047484  lea     edx, [rdi+52h]
0x140047487  lea     r9, aSoftwareMicros_10; "Software\\Microsoft\\Fax\\Accounts"
0x14004748e  mov     dword ptr [rsp+60h+var_40], eax
0x140047492  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x140047499  call    WPP_SF_Sd
0x14004749e  jmp     short loc_1400474F1
0x1400474a0  mov     rcx, cs:?g_pAccountDefaults@@3PEAVCFaxAccount@@EA; this
0x1400474a7  xor     r8d, r8d; void *
0x1400474aa  mov     rdx, rdi; HKEY
0x1400474ad  call    ?Load@CFaxAccount@@QEAAKPEAUHKEY__@@PEAX@Z; CFaxAccount::Load(HKEY__ *,void *)
0x1400474b2  mov     ebx, eax
0x1400474b4  test    eax, eax
0x1400474b6  jz      short loc_1400474E8
0x1400474b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400474bf  cmp     rcx, r13
0x1400474c2  jz      short loc_1400474E8
0x1400474c4  test    [rcx+1Ch], r15b
0x1400474c8  jz      short loc_1400474E8
0x1400474ca  cmp     [rcx+19h], r12b
0x1400474ce  jb      short loc_1400474E8
0x1400474d0  mov     rcx, [rcx+10h]
0x1400474d4  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x1400474db  mov     edx, 53h ; 'S'
0x1400474e0  mov     r9d, eax
0x1400474e3  call    WPP_SF_d
0x1400474e8  mov     rcx, rdi; hKey
0x1400474eb  call    cs:__imp_RegCloseKey
0x1400474f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400474f8  test    ebx, ebx
0x1400474fa  jz      short loc_14004752A
0x1400474fc  cmp     rcx, r13
0x1400474ff  jz      short loc_14004752A
0x140047501  test    [rcx+1Ch], r15b
0x140047505  jz      short loc_14004752A
0x140047507  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004750e  cmp     [rcx+19h], r12b
0x140047512  jb      short loc_140047531
0x140047514  mov     rcx, [rcx+10h]
0x140047518  mov     edx, 4Dh ; 'M'
0x14004751d  mov     r9d, ebx
0x140047520  mov     r8, rdi
0x140047523  call    WPP_SF_d
0x140047528  jmp     short loc_140047531
0x14004752a  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140047531  call    ?InitializeServerQuota@@YAKXZ; InitializeServerQuota(void)
0x140047536  mov     ebx, eax
0x140047538  test    eax, eax
0x14004753a  jz      short loc_1400475B0
0x14004753c  mov     rcx, cs:WPP_GLOBAL_Control
0x140047543  cmp     rcx, r13
0x140047546  jz      short loc_140047568
0x140047548  test    [rcx+1Ch], r15b
0x14004754c  jz      short loc_140047568
0x14004754e  cmp     [rcx+19h], r12b
0x140047552  jb      short loc_140047568
0x140047554  mov     edx, 4Eh ; 'N'
0x140047559  mov     rcx, [rcx+10h]
0x14004755d  mov     r9d, ebx
0x140047560  mov     r8, rdi
0x140047563  call    WPP_SF_d
0x140047568  xor     eax, eax
0x14004756a  mov     [rbp+var_30], ebx
0x14004756d  mov     r9d, ebx
0x140047570  mov     [rbp+var_2C], ax
0x140047574  lea     r8, aLd; "%ld"
0x14004757b  lea     rcx, [rbp+var_2C]; unsigned __int16 *
0x14004757f  lea     edx, [rax+0Ch]; unsigned __int64
0x140047582  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140047587  mov     r9d, 0C0007D2Ch
0x14004758d  xor     ecx, ecx
0x14004758f  lea     rdx, [rbp+var_2C]
0x140047593  test    eax, eax
0x140047595  cmovs   rdx, rcx
0x140047599  mov     [rsp+60h+var_40], rdx
0x14004759e  lea     edx, [rcx+1]
0x1400475a1  mov     ecx, edx
0x1400475a3  mov     r8d, edx
0x1400475a6  call    FaxLog
0x1400475ab  jmp     loc_140047B4B
0x1400475b0  call    ?InitializeServerSecurity@@YAKXZ; InitializeServerSecurity(void)
0x1400475b5  mov     ebx, eax
0x1400475b7  test    eax, eax
0x1400475b9  jz      short loc_1400475F8
0x1400475bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400475c2  cmp     rcx, r13
0x1400475c5  jz      loc_140047B4B
0x1400475cb  test    [rcx+1Ch], r15b
0x1400475cf  jz      loc_140047B4B
0x1400475d5  cmp     [rcx+19h], r12b
0x1400475d9  jb      loc_140047B4B
0x1400475df  mov     edx, 4Fh ; 'O'
0x1400475e4  mov     rcx, [rcx+10h]
0x1400475e8  mov     r9d, eax
0x1400475eb  mov     r8, rdi
0x1400475ee  call    WPP_SF_d
0x1400475f3  jmp     loc_140047B4B
0x1400475f8  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x1400475fb  call    ?LoadDeviceProviders@@YAHPEAU_REG_FAX_SERVICE@@@Z; LoadDeviceProviders(_REG_FAX_SERVICE *)
0x140047600  test    eax, eax
0x140047602  jnz     short loc_14004762B
0x140047604  mov     rcx, cs:WPP_GLOBAL_Control
0x14004760b  cmp     rcx, r13
0x14004760e  jz      short loc_14004762B
0x140047610  test    [rcx+1Ch], r15b
0x140047614  jz      short loc_14004762B
0x140047616  cmp     [rcx+19h], r12b
0x14004761a  jb      short loc_14004762B
0x14004761c  mov     rcx, [rcx+10h]
0x140047620  lea     edx, [rax+50h]
0x140047623  mov     r8, rdi
0x140047626  call    WPP_SF_
0x14004762b  call    ?InitializeJobManager@@YAHPEAU_REG_FAX_SERVICE@@@Z; InitializeJobManager(_REG_FAX_SERVICE *)
0x140047630  test    eax, eax
0x140047632  jnz     short loc_14004763C
0x140047634  lea     ebx, [rax+1Fh]
0x140047637  jmp     loc_140047B4B
0x14004763c  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x14004763f  call    ?InitializeRouting@@YAHPEAU_REG_FAX_SERVICE@@@Z; InitializeRouting(_REG_FAX_SERVICE *)
0x140047644  test    eax, eax
0x140047646  jnz     short loc_14004767E
0x140047648  call    cs:__imp_GetLastError
0x14004764e  mov     ebx, eax
0x140047650  mov     rcx, cs:WPP_GLOBAL_Control
0x140047657  cmp     rcx, r13
0x14004765a  jz      loc_140047B4B
0x140047660  test    [rcx+1Ch], r15b
0x140047664  jz      loc_140047B4B
0x14004766a  cmp     [rcx+19h], r12b
0x14004766e  jb      loc_140047B4B
0x140047674  mov     edx, 51h ; 'Q'
0x140047679  jmp     loc_1400475E4
0x14004767e  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x140047681  call    ?TapiInitialize@@YAKPEAU_REG_FAX_SERVICE@@@Z; TapiInitialize(_REG_FAX_SERVICE *)
0x140047686  mov     ebx, eax
0x140047688  test    eax, eax
0x14004768a  jz      short loc_1400476E2
0x14004768c  mov     rcx, cs:WPP_GLOBAL_Control
0x140047693  cmp     rcx, r13
0x140047696  jz      short loc_1400476B8
0x140047698  test    [rcx+1Ch], r15b
0x14004769c  jz      short loc_1400476B8
0x14004769e  cmp     [rcx+19h], r12b
0x1400476a2  jb      short loc_1400476B8
0x1400476a4  mov     rcx, [rcx+10h]
0x1400476a8  mov     edx, 52h ; 'R'
0x1400476ad  mov     r9d, eax
0x1400476b0  mov     r8, rdi
0x1400476b3  call    WPP_SF_d
0x1400476b8  xor     eax, eax
0x1400476ba  mov     [rbp+var_30], ebx
0x1400476bd  mov     r9d, ebx
0x1400476c0  mov     [rbp+var_2C], ax
0x1400476c4  lea     r8, aLd; "%ld"
0x1400476cb  lea     rcx, [rbp+var_2C]; unsigned __int16 *
0x1400476cf  lea     edx, [rax+0Ch]; unsigned __int64
0x1400476d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400476d7  mov     r9d, 0C0007D2Dh
0x1400476dd  jmp     loc_14004758D
0x1400476e2  call    ?InitializeDeviceProvidersConfiguration@@YAHXZ; InitializeDeviceProvidersConfiguration(void)
0x1400476e7  test    eax, eax
0x1400476e9  jnz     short loc_140047724
0x1400476eb  mov     rax, cs:WPP_GLOBAL_Control
0x1400476f2  cmp     rax, r13
0x1400476f5  jz      short loc_140047724
0x1400476f7  test    [rax+1Ch], r15b
0x1400476fb  jz      short loc_140047724
0x1400476fd  cmp     [rax+19h], r12b
0x140047701  jb      short loc_140047724
0x140047703  call    cs:__imp_GetLastError
0x140047709  mov     rcx, cs:WPP_GLOBAL_Control
0x140047710  mov     edx, 53h ; 'S'
0x140047715  mov     r9d, eax
0x140047718  mov     r8, rdi
0x14004771b  mov     rcx, [rcx+10h]
0x14004771f  call    WPP_SF_d
0x140047724  mov     rcx, rsi; struct _REG_FAX_SERVICE *
0x140047727  call    ?CreateVirtualDevices@@YAKPEAU_REG_FAX_SERVICE@@K@Z; CreateVirtualDevices(_REG_FAX_SERVICE *,ulong)
0x14004772c  add     cs:?g_dwDeviceCount@@3KA, eax; ulong g_dwDeviceCount
0x140047732  call    ?InitializeDeviceProviders@@YAHXZ; InitializeDeviceProviders(void)
0x140047737  test    eax, eax
0x140047739  jnz     short loc_140047774
0x14004773b  mov     rcx, cs:WPP_GLOBAL_Control
0x140047742  cmp     rcx, r13
0x140047745  jz      short loc_14004777B
0x140047747  test    [rcx+1Ch], r15b
  ... truncated ...
```
