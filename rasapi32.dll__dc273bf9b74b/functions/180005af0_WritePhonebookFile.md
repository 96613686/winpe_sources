# WritePhonebookFile

- ea: `0x180005af0`
- end: `0x18000630c`
- name: `WritePhonebookFile`
- size: `2076`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180005850`
- `0x18003b8d0`
- `0x180077110`
- `0x180079da0`
- `0x18007a750`
- `0x18007c380`
- `0x18007d390`
- `0x180096d00`
- `0x1800975b8`
- `0x1800a7f48`
- `0x1800c8028`
- `0x1800caa9c`

## callees

- `0x180005af0`
- `0x180006314`
- `0x18000642c`
- `0x1800160ec`
- `0x1800292a0`
- `0x180032510`
- `0x18003b31c`
- `0x180040a68`
- `0x18004e580`
- `0x18004e984`
- `0x18004eb5c`
- `0x18007e5f0`
- `0x1800caa9c`
- `0x1800cea94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005e6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005e6d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005de2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060f3`
- `rtutils!TracePrintfExA` at `0x180005c0e`
- `rtutils!TracePrintfExA` at `0x180005c71`
- `rtutils!TracePrintfExA` at `0x180005d44`
- `rtutils!TracePrintfExA` at `0x180005efc`
- `rtutils!TracePrintfExA` at `0x180005f7c`
- `rtutils!TracePrintfExA` at `0x1800060a9`
- `rtutils!TracePrintfExA` at `0x180006117`
- `rtutils!TracePrintfExA` at `0x180006177`
- `rtutils!TracePrintfExA` at `0x180006204`
- `rtutils!TracePrintfExA` at `0x1800062aa`
- `rtutils!TracePrintfExA` at `0x180005c0e`
- `rtutils!TracePrintfExA` at `0x180005c71`
- `rtutils!TracePrintfExA` at `0x180005d44`
- `rtutils!TracePrintfExA` at `0x180005efc`
- `rtutils!TracePrintfExA` at `0x180005f7c`
- `rtutils!TracePrintfExA` at `0x1800060a9`
- `rtutils!TracePrintfExA` at `0x180006117`
- `rtutils!TracePrintfExA` at `0x180006177`
- `rtutils!TracePrintfExA` at `0x180006204`
- `rtutils!TracePrintfExA` at `0x1800062aa`

## string_xrefs

- `0x180005c63`: `RASSQM: In WritePhonebookFile Number of alluser profiles set %d`
- `0x180005d3b`: `WritePhonebookFile`
- `0x18000609b`: `WritePhonebookFile: pRasfileData NULL!`
- `0x180005f73`: `WritePhonebookFile: Invalid entryname to delete`
- `0x1800062a1`: `WritePhonebookFile: No pbk file or no entries in pbk file to write`
- `0x180005ef3`: `WritePhonebookFile: Lockdown profile provisioned, so no changes can be made`
- `0x180005c00`: `WritePhonebookFile: DeleteAllHiddenProfile: failed %d`
- `0x180006109`: `WritePhonebookFile: WaitForSingleObject Failed: Ret:%d`
- `0x180006169`: `WritePhonebookFile: PbkMutex is NULL!`
- `0x180006236`: `ProfileCreate`
- `0x180006228`: `ProfileDelete`
- `0x1800061f6`: `RASSQM: In WritePhonebookFile Number of myuse profiles set %d`

## pseudocode

```c
__int64 __fastcall WritePhonebookFile(__int64 a1, const wchar_t *a2)
{
  unsigned int v4; // edi
  int v5; // edi
  DWORD v6; // eax
  DWORD LastError; // esi
  _QWORD *v8; // rcx
  DWORD v9; // eax
  int v10; // r9d
  __int64 *v11; // rdi
  __int64 v12; // rdi
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rax
  __int64 v18; // r15
  unsigned int *v19; // rdi
  __int64 v20; // rcx
  _BYTE *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  _DWORD *v24; // rcx
  const wchar_t *v25; // r8
  _QWORD *v26; // rcx
  unsigned int v27; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 788, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 789, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  v27 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "WritePhonebookFile");
  v4 = 5;
  if ( (unsigned int)LockDownPolicyExists() )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "WritePhonebookFile: Lockdown profile provisioned, so no changes can be made");
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 790, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 5);
      v21 = WPP_GLOBAL_Control;
    }
    if ( v21 == (_BYTE *)&WPP_GLOBAL_Control || (v21[28] & 0x80) == 0 || v21[25] < 6u )
      return v4;
    v22 = 791;
    goto LABEL_101;
  }
  if ( a1 && *(_QWORD *)(a1 + 16) )
  {
    if ( a2 && !*a2 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "WritePhonebookFile: Invalid entryname to delete");
      v21 = WPP_GLOBAL_Control;
      v4 = 87;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 794, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 87);
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 == (_BYTE *)&WPP_GLOBAL_Control || (v21[28] & 0x80) == 0 || v21[25] < 6u )
        return v4;
      v22 = 795;
LABEL_101:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v4);
      return v4;
    }
    if ( !CallerHasWritePermission(a1) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 796, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 5);
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 == (_BYTE *)&WPP_GLOBAL_Control || (v21[28] & 0x80) == 0 || v21[25] < 6u )
        return v4;
      v22 = 797;
      goto LABEL_101;
    }
    if ( a2 )
    {
      v15 = EntryNodeFromName(*(_QWORD *)(a1 + 16), a2);
      if ( !v15 )
      {
        LastError = 623;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_31;
        }
        v16 = 798;
        goto LABEL_111;
      }
      *(_DWORD *)(*(_QWORD *)(v15 + 16) + 540LL) = 1;
    }
    v5 = GetRegistryWriteBehavior();
    if ( v5 )
      v6 = ModifyEntryListInRegistry(a1, &v27);
    else
      v6 = ModifyEntryList(a1, &v27);
    LastError = v6;
    if ( !v6 )
    {
      if ( !v5 )
      {
        v17 = *(__int64 **)(a1 + 48);
        if ( v17 )
        {
          v18 = *v17;
          v9 = g_dwTraceId;
          v8 = WPP_GLOBAL_Control;
          while ( 1 )
          {
            if ( !v18 )
            {
              if ( LastError )
                goto LABEL_31;
              goto LABEL_16;
            }
            v19 = *(unsigned int **)(v18 + 16);
            if ( v19 )
            {
              if ( !g_hmutexPb )
              {
                if ( v9 != -1 )
                {
                  TracePrintfExA(v9, 0xCu, "WritePhonebookFile: PbkMutex is NULL!");
                  v8 = WPP_GLOBAL_Control;
                }
                if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x80) != 0 && *((_BYTE *)v8 + 25) >= 2u )
                {
                  WPP_SF_d(v8[2], 801, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
                  v8 = WPP_GLOBAL_Control;
                }
                LastError = 624;
                if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x80) != 0 && *((_BYTE *)v8 + 25) >= 2u )
                {
                  v16 = 802;
                  v23 = 624;
                  goto LABEL_112;
                }
LABEL_31:
                v11 = *(__int64 **)(a1 + 16);
                if ( !v11 || (v12 = *v11) == 0 )
                {
LABEL_33:
                  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x80) != 0 && *((_BYTE *)v8 + 25) >= 6u )
                    WPP_SF_d(v8[2], 808, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
                  return LastError;
                }
                while ( 2 )
                {
                  v24 = *(_DWORD **)(v12 + 16);
                  if ( v24 )
                  {
                    if ( v24[135] )
                    {
                      v25 = L"ProfileDelete";
                      goto LABEL_149;
                    }
                    if ( *v24 == -1 )
                    {
                      v25 = L"ProfileCreate";
                      goto LABEL_149;
                    }
                    if ( v24[133] )
                    {
                      v25 = L"ProfileModify";
LABEL_149:
                      TelemetryEventWritePhonebookEntry(v24, *(_QWORD *)a1, v25, LastError);
                    }
                  }
                  v12 = *(_QWORD *)(v12 + 8);
                  if ( !v12 )
                  {
                    v8 = WPP_GLOBAL_Control;
                    goto LABEL_33;
                  }
                  continue;
                }
              }
              LastError = WaitForSingleObject(g_hmutexPb, 0xFFFFFFFF);
              if ( (LastError & 0xFFFFFF7F) == 0 )
              {
                if ( *v19 > 0x1F3
                  || (v20 = gpRasfiles[*v19]) == 0
                  || (*(_BYTE *)(v20 + 32) & 4) != 0
                  || *(_BYTE *)(v20 + 572)
                  || *(_DWORD *)(v20 + 36) && !(unsigned int)rasWriteFile() )
                {
                  LastError = 624;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      803,
                      &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                      624);
                  }
                }
                ReleaseMutex(g_hmutexPb);
                goto LABEL_70;
              }
              LastError = GetLastError();
              v9 = g_dwTraceId;
              if ( g_dwTraceId != -1 )
              {
                TracePrintfExA(g_dwTraceId, 0xCu, "WritePhonebookFile: WaitForSingleObject Failed: Ret:%d", LastError);
                v9 = g_dwTraceId;
              }
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  804,
                  &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                  LastError);
                goto LABEL_70;
              }
            }
            else
            {
              if ( v9 != -1 )
              {
                TracePrintfExA(v9, 0xCu, "WritePhonebookFile: pRasfileData NULL!");
                v8 = WPP_GLOBAL_Control;
                v9 = g_dwTraceId;
              }
              if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x80) != 0 && *((_BYTE *)v8 + 25) >= 2u )
              {
                WPP_SF_(v8[2], 800, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
LABEL_70:
                v8 = WPP_GLOBAL_Control;
                v9 = g_dwTraceId;
              }
            }
            v18 = *(_QWORD *)(v18 + 8);
          }
        }
      }
      v8 = WPP_GLOBAL_Control;
      v9 = g_dwTraceId;
LABEL_16:
      if ( *(_DWORD *)(a1 + 8) )
        goto LABEL_37;
      if ( a2 )
      {
        if ( !(unsigned int)FIsUserAdminOrNCO(v8) )
        {
LABEL_25:
          v9 = g_dwTraceId;
          v8 = WPP_GLOBAL_Control;
          goto LABEL_26;
        }
        v10 = DeleteAllHiddenProfile(*(wchar_t **)a1, a2);
        v9 = g_dwTraceId;
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "WritePhonebookFile: DeleteAllHiddenProfile: failed %d", v10);
          v9 = g_dwTraceId;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 805, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
          goto LABEL_25;
        }
      }
LABEL_26:
      if ( !*(_DWORD *)(a1 + 8) )
      {
        if ( v9 != -1 )
        {
          TracePrintfExA(v9, 0xCu, "RASSQM: In WritePhonebookFile Number of alluser profiles set %d", v27);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x80) == 0 || *((_BYTE *)v8 + 25) < 5u )
          goto LABEL_31;
        v14 = 806;
LABEL_44:
        WPP_SF_d(v8[2], v14, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v27);
LABEL_45:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
LABEL_37:
      if ( *(_DWORD *)(a1 + 8) != 1 )
        goto LABEL_31;
      if ( v9 != -1 )
      {
        TracePrintfExA(v9, 0xCu, "RASSQM: In WritePhonebookFile Number of myuse profiles set %d", v27);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x80) == 0 || *((_BYTE *)v8 + 25) < 5u )
        goto LABEL_31;
      v14 = 807;
      goto LABEL_44;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    v16 = 799;
LABEL_111:
    v23 = LastError;
LABEL_112:
    WPP_SF_d(v8[2], v16, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v23);
    goto LABEL_45;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "WritePhonebookFile: No pbk file or no entries in pbk file to write");
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 792, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
      v26 = WPP_GLOBAL_Control;
    }
    if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 0x80) != 0 && *((_BYTE *)v26 + 25) >= 6u )
      WPP_SF_d(v26[2], 793, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180005af0  push    rbx
0x180005af2  push    rbp
0x180005af3  push    rsi
0x180005af4  push    rdi
0x180005af5  push    r12
0x180005af7  push    r13
0x180005af9  push    r14
0x180005afb  push    r15
0x180005afd  sub     rsp, 28h
0x180005b01  xor     r12d, r12d
0x180005b04  lea     r15, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180005b0b  mov     rbp, rdx
0x180005b0e  mov     r14, rcx
0x180005b11  mov     r13b, 80h
0x180005b14  test    rdx, rdx
0x180005b17  jnz     loc_180005EA4
0x180005b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b24  lea     rbx, WPP_GLOBAL_Control
0x180005b2b  cmp     rcx, rbx
0x180005b2e  jnz     loc_180005D11
0x180005b34  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005b3a  mov     esi, 0Ch
0x180005b3f  mov     [rsp+68h+arg_8], r12d
0x180005b44  cmp     ecx, 0FFFFFFFFh
0x180005b47  jnz     loc_180005D3B
0x180005b4d  call    LockDownPolicyExists
0x180005b52  mov     edi, 5
0x180005b57  test    eax, eax
0x180005b59  jnz     loc_180005EE8
0x180005b5f  test    r14, r14
0x180005b62  jz      loc_180006296
0x180005b68  cmp     [r14+10h], r12
0x180005b6c  jz      loc_180006296
0x180005b72  test    rbp, rbp
0x180005b75  jnz     loc_180005F5D
0x180005b7b  mov     rcx, r14
0x180005b7e  call    CallerHasWritePermission
0x180005b83  test    eax, eax
0x180005b85  jz      loc_180005FED
0x180005b8b  test    rbp, rbp
0x180005b8e  jnz     loc_180005D4F
0x180005b94  call    GetRegistryWriteBehavior
0x180005b99  lea     rdx, [rsp+68h+arg_8]
0x180005b9e  mov     edi, eax
0x180005ba0  mov     rcx, r14
0x180005ba3  test    eax, eax
0x180005ba5  jnz     loc_180005CC4
0x180005bab  call    ModifyEntryList
0x180005bb0  mov     esi, eax
0x180005bb2  test    eax, eax
0x180005bb4  jnz     loc_180006070
0x180005bba  test    edi, edi
0x180005bbc  jz      loc_180005D97
0x180005bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bc9  mov     eax, cs:g_dwTraceId
0x180005bcf  cmp     [r14+8], r12d
0x180005bd3  jnz     loc_180005CCE
0x180005bd9  test    rbp, rbp
0x180005bdc  jz      short loc_180005C53
0x180005bde  call    FIsUserAdminOrNCO
0x180005be3  test    eax, eax
0x180005be5  jz      short loc_180005C46
0x180005be7  mov     rcx, [r14]; Str
0x180005bea  mov     rdx, rbp
0x180005bed  call    DeleteAllHiddenProfile
0x180005bf2  mov     r9d, eax
0x180005bf5  mov     eax, cs:g_dwTraceId
0x180005bfb  cmp     eax, 0FFFFFFFFh
0x180005bfe  jz      short loc_180005C1A
0x180005c00  lea     r8, aWritephonebook_0; "WritePhonebookFile: DeleteAllHiddenProf"...
0x180005c07  mov     edx, 0Ch; dwFlags
0x180005c0c  mov     ecx, eax; dwTraceID
0x180005c0e  call    cs:__imp_TracePrintfExA
0x180005c14  mov     eax, cs:g_dwTraceId
0x180005c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c21  cmp     rcx, rbx
0x180005c24  jz      short loc_180005C53
0x180005c26  test    [rcx+1Ch], r13b
0x180005c2a  jz      short loc_180005C53
0x180005c2c  cmp     byte ptr [rcx+19h], 2
0x180005c30  jb      short loc_180005C53
0x180005c32  mov     rcx, [rcx+10h]
0x180005c36  mov     edx, 325h
0x180005c3b  xor     r9d, r9d
0x180005c3e  mov     r8, r15
0x180005c41  call    WPP_SF_d
0x180005c46  mov     eax, cs:g_dwTraceId
0x180005c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c53  cmp     [r14+8], r12d
0x180005c57  jnz     short loc_180005CCE
0x180005c59  cmp     eax, 0FFFFFFFFh
0x180005c5c  jz      short loc_180005C7E
0x180005c5e  mov     r9d, [rsp+68h+arg_8]
0x180005c63  lea     r8, aRassqmInWritep_0; "RASSQM: In WritePhonebookFile Number of"...
0x180005c6a  mov     edx, 0Ch; dwFlags
0x180005c6f  mov     ecx, eax; dwTraceID
0x180005c71  call    cs:__imp_TracePrintfExA
0x180005c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c7e  cmp     rcx, rbx
0x180005c81  jz      short loc_180005C8D
0x180005c83  test    [rcx+1Ch], r13b
0x180005c87  jnz     loc_1800061DD
0x180005c8d  mov     rdi, [r14+10h]
0x180005c91  test    rdi, rdi
0x180005c94  jz      short loc_180005CA2
0x180005c96  mov     rdi, [rdi]
0x180005c99  test    rdi, rdi
0x180005c9c  jnz     loc_180006216
0x180005ca2  cmp     rcx, rbx
0x180005ca5  jz      short loc_180005CB1
0x180005ca7  test    [rcx+1Ch], r13b
0x180005cab  jnz     loc_18000626F
0x180005cb1  mov     eax, esi
0x180005cb3  add     rsp, 28h
0x180005cb7  pop     r15
0x180005cb9  pop     r14
0x180005cbb  pop     r13
0x180005cbd  pop     r12
0x180005cbf  pop     rdi
0x180005cc0  pop     rsi
0x180005cc1  pop     rbp
0x180005cc2  pop     rbx
0x180005cc3  retn
0x180005cc4  call    ModifyEntryListInRegistry
0x180005cc9  jmp     loc_180005BB0
0x180005cce  cmp     dword ptr [r14+8], 1
0x180005cd3  jnz     short loc_180005C8D
0x180005cd5  cmp     eax, 0FFFFFFFFh
0x180005cd8  jnz     loc_1800061F1
0x180005cde  cmp     rcx, rbx
0x180005ce1  jz      short loc_180005C8D
0x180005ce3  test    [rcx+1Ch], r13b
0x180005ce7  jz      short loc_180005C8D
0x180005ce9  cmp     byte ptr [rcx+19h], 5
0x180005ced  jb      short loc_180005C8D
0x180005cef  mov     edx, 327h
0x180005cf4  mov     r9d, [rsp+68h+arg_8]
0x180005cf9  mov     r8, r15
0x180005cfc  mov     rcx, [rcx+10h]
0x180005d00  call    WPP_SF_d
0x180005d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d0c  jmp     loc_180005C8D
0x180005d11  test    [rcx+1Ch], r13b
0x180005d15  jz      loc_180005B34
0x180005d1b  cmp     byte ptr [rcx+19h], 6
0x180005d1f  jb      loc_180005B34
0x180005d25  mov     rcx, [rcx+10h]
0x180005d29  mov     edx, 315h
0x180005d2e  mov     r8, r15
0x180005d31  call    WPP_SF_
0x180005d36  jmp     loc_180005B34
0x180005d3b  lea     r8, aWritephonebook_7; "WritePhonebookFile"
0x180005d42  mov     edx, esi; dwFlags
0x180005d44  call    cs:__imp_TracePrintfExA
0x180005d4a  jmp     loc_180005B4D
0x180005d4f  mov     rcx, [r14+10h]
0x180005d53  mov     rdx, rbp
0x180005d56  call    EntryNodeFromName
0x180005d5b  test    rax, rax
0x180005d5e  jnz     loc_18000605D
0x180005d64  mov     esi, 26Fh
0x180005d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d70  cmp     rcx, rbx
0x180005d73  jz      loc_180005C8D
0x180005d79  test    [rcx+1Ch], r13b
0x180005d7d  jz      loc_180005C8D
0x180005d83  cmp     byte ptr [rcx+19h], 2
0x180005d87  jb      loc_180005C8D
0x180005d8d  mov     edx, 31Eh
0x180005d92  jmp     loc_180006038
0x180005d97  mov     rax, [r14+30h]
0x180005d9b  test    rax, rax
0x180005d9e  jz      loc_180005BC2
0x180005da4  mov     r15, [rax]
0x180005da7  mov     eax, cs:g_dwTraceId
0x180005dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180005db4  mov     edx, esi
0x180005db6  test    r15, r15
0x180005db9  jz      loc_180005E49
0x180005dbf  mov     rdi, [r15+10h]
0x180005dc3  test    rdi, rdi
0x180005dc6  jz      loc_180006096
0x180005dcc  mov     r8, cs:g_hmutexPb
0x180005dd3  test    r8, r8
0x180005dd6  jz      loc_180006164
0x180005ddc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005ddf  mov     rcx, r8; hHandle
0x180005de2  call    cs:__imp_WaitForSingleObject
0x180005de8  mov     esi, eax
0x180005dea  test    eax, 0FFFFFF7Fh
0x180005def  jnz     loc_1800060F3
0x180005df5  cmp     dword ptr [rdi], 1F3h
0x180005dfb  ja      short loc_180005E10
0x180005dfd  movsxd  rax, dword ptr [rdi]
0x180005e00  lea     rcx, gpRasfiles
0x180005e07  mov     rcx, [rcx+rax*8]
0x180005e0b  test    rcx, rcx
0x180005e0e  jnz     short loc_180005E89
0x180005e10  mov     eax, 270h
0x180005e15  mov     esi, eax
0x180005e17  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e1e  cmp     rcx, rbx
0x180005e21  jz      short loc_180005E66
0x180005e23  test    [rcx+1Ch], r13b
0x180005e27  jz      short loc_180005E66
0x180005e29  cmp     byte ptr [rcx+19h], 2
0x180005e2d  jb      short loc_180005E66
0x180005e2f  mov     rcx, [rcx+10h]
0x180005e33  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180005e3a  mov     edx, 323h
0x180005e3f  mov     r9d, eax
0x180005e42  call    WPP_SF_d
0x180005e47  jmp     short loc_180005E66
0x180005e49  test    edx, edx
0x180005e4b  jnz     loc_180005C8D
0x180005e51  lea     r15, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180005e58  jmp     loc_180005BCF
0x180005e5d  call    rasWriteFile
0x180005e62  test    eax, eax
0x180005e64  jz      short loc_180005E10
0x180005e66  mov     rcx, cs:g_hmutexPb; hMutex
0x180005e6d  call    cs:__imp_ReleaseMutex
0x180005e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e7a  mov     eax, cs:g_dwTraceId
0x180005e80  mov     r15, [r15+8]
0x180005e84  jmp     loc_180005DB4
0x180005e89  test    byte ptr [rcx+20h], 4
0x180005e8d  jnz     short loc_180005E10
0x180005e8f  cmp     [rcx+23Ch], r12b
0x180005e96  jnz     loc_180005E10
0x180005e9c  cmp     [rcx+24h], r12d
0x180005ea0  jz      short loc_180005E66
0x180005ea2  jmp     short loc_180005E5D
0x180005ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eab  lea     rbx, WPP_GLOBAL_Control
0x180005eb2  cmp     rcx, rbx
0x180005eb5  jz      loc_180005B34
0x180005ebb  test    [rcx+1Ch], r13b
0x180005ebf  jz      loc_180005B34
0x180005ec5  cmp     byte ptr [rcx+19h], 6
0x180005ec9  jb      loc_180005B34
0x180005ecf  mov     rcx, [rcx+10h]
0x180005ed3  mov     edx, 314h
0x180005ed8  mov     r9, rbp
0x180005edb  mov     r8, r15
0x180005ede  call    WPP_SF_S
0x180005ee3  jmp     loc_180005B34
0x180005ee8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005eee  cmp     ecx, 0FFFFFFFFh
0x180005ef1  jz      short loc_180005F02
0x180005ef3  lea     r8, aWritephonebook_3; "WritePhonebookFile: Lockdown profile pr"...
0x180005efa  mov     edx, esi; dwFlags
0x180005efc  call    cs:__imp_TracePrintfExA
0x180005f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f09  cmp     rcx, rbx
0x180005f0c  jz      loc_180005FE6
0x180005f12  test    [rcx+1Ch], r13b
0x180005f16  jz      short loc_180005F39
0x180005f18  cmp     byte ptr [rcx+19h], 2
0x180005f1c  jb      short loc_180005F39
0x180005f1e  mov     rcx, [rcx+10h]
0x180005f22  mov     edx, 316h
0x180005f27  mov     r9d, edi
0x180005f2a  mov     r8, r15
0x180005f2d  call    WPP_SF_d
0x180005f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f39  cmp     rcx, rbx
0x180005f3c  jz      loc_180005FE6
0x180005f42  test    [rcx+1Ch], r13b
0x180005f46  jz      loc_180005FE6
0x180005f4c  cmp     byte ptr [rcx+19h], 6
0x180005f50  jb      loc_180005FE6
0x180005f56  mov     edx, 317h
0x180005f5b  jmp     short loc_180005FD7
0x180005f5d  cmp     [rbp+0], r12w
0x180005f62  jnz     loc_180005B7B
0x180005f68  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005f6e  cmp     ecx, 0FFFFFFFFh
0x180005f71  jz      short loc_180005F82
0x180005f73  lea     r8, aWritephonebook_2; "WritePhonebookFile: Invalid entryname t"...
0x180005f7a  mov     edx, esi; dwFlags
0x180005f7c  call    cs:__imp_TracePrintfExA
0x180005f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f89  mov     edi, 57h ; 'W'
0x180005f8e  cmp     rcx, rbx
0x180005f91  jz      short loc_180005FE6
0x180005f93  test    [rcx+1Ch], r13b
0x180005f97  jz      short loc_180005FBA
0x180005f99  cmp     byte ptr [rcx+19h], 2
0x180005f9d  jb      short loc_180005FBA
0x180005f9f  mov     rcx, [rcx+10h]
0x180005fa3  mov     edx, 31Ah
0x180005fa8  mov     r9d, edi
0x180005fab  mov     r8, r15
0x180005fae  call    WPP_SF_d
0x180005fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fba  cmp     rcx, rbx
0x180005fbd  jz      short loc_180005FE6
0x180005fbf  test    [rcx+1Ch], r13b
0x180005fc3  jz      short loc_180005FE6
  ... truncated ...
```
