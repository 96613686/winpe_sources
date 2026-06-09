# SyncActionCreateClient

- ea: `0x180002540`
- end: `0x180003044`
- name: `SyncActionCreateClient`
- size: `2820`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18007a750`

## callees

- `0x1800023f0`
- `0x180002540`
- `0x1800032cc`
- `0x1800053e0`
- `0x180014d08`
- `0x18001f534`
- `0x1800223c0`
- `0x180024c90`
- `0x180031d38`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x180039fb4`
- `0x18003c488`
- `0x18003c4e8`
- `0x18003e928`
- `0x1800469c0`
- `0x1800725d8`
- `0x18007291c`
- `0x180072f5c`
- `0x180073660`
- `0x1800738f0`
- `0x18007906c`
- `0x18007b5fc`
- `0x18007c638`
- `0x18007e5d8`

## string_xrefs

- `0x18000261a`: `SyncActionCreateClient: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x IsDir: %c`
- `0x18000268f`: `SyncActionCreateClient: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x`
- `0x180002794`: `SyncActionCreateClient: SyncOpenFileByPathEx failed for '%ws' with %x`
- `0x180002803`: `SyncActionCreateClient: SyncHandleIsDisconnected failed for '%ws' with %x`
- `0x180002a49`: `SyncActionCreateClient: SyncActionHasFileChanged failed with %x`
- `0x180002ab0`: `SyncActionCreateClient: '%ws' has changed remotely since enumeration [%x]`
- `0x180002b57`: `SyncActionCreateClient: Altered pin clear flags to only contain inherit mask, from %x/%x to %x/%x`
- `0x180002bd6`: `SyncActionCreateClient: SyncItemSetPinInformation failed for '%ws' with %x`
- `0x180002c37`: `SyncActionCreateClient: File '%ws' is Pin-Only -- jumping out`
- `0x180002cca`: `SyncActionCreateClient: '%ws' is dirty -- failing create op`
- `0x180002d54`: `SyncActionCreateClient: File '%ws' does not exist in the cache so cannot fill it`
- `0x180002f6a`: `SyncActionCreateClient: SyncHandleIsCached failed for '%ws' with %x`
- `0x180002dbd`: `SyncActionCreateClient: SyncQueryInformationLocal to find if file is suspended failed with %x`
- `0x180002e5b`: `SyncActionCreateClient: SyncActionReadFile failed with %x`
- `0x180002ebc`: `SyncActionCreateClient: SyncQueryInformationLocal failed with %x`
- `0x180002f0f`: `SyncActionCreateClient: File is still sparse even after reading! ItemStatus = %x`
- `0x180002fe5`: `SyncActionCreateClient: Result: 0x%x  Return: %x ( EE = %u )`
- `0x18000298e`: `SyncActionHasFileChanged: SyncItemEnumSingleFile failed with %x`

## pseudocode

```c
__int64 __fastcall SyncActionCreateClient(__int64 a1)
{
  int v2; // edx
  char v3; // r13
  __int64 v4; // r9
  int v5; // ebx
  unsigned int v6; // r12d
  int v7; // r12d
  CObjectMonitor *v8; // rax
  int v9; // edx
  int v10; // r8d
  bool v11; // zf
  unsigned int IntermediateDirectories; // edi
  unsigned int v13; // ebx
  _BYTE *v14; // rax
  char v15; // bl
  __int64 v16; // rdi
  char v17; // cl
  __int64 v18; // rsi
  int v19; // r13d
  unsigned int *v20; // r15
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  _DWORD *v24; // rax
  int *v25; // rcx
  int v26; // ebx
  unsigned __int8 *v27; // rcx
  int v28; // r13d
  char v29; // dl
  char v30; // si
  _DWORD *v31; // rax
  __int64 v32; // rcx
  ULONG v34[2]; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  ULONG v36[2]; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+28h] [rbp-D8h]
  int v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+30h] [rbp-D0h]
  _BYTE FileHandle[15]; // [rsp+51h] [rbp-AFh] BYREF
  int v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+64h] [rbp-9Ch]
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int128 v46; // [rsp+80h] [rbp-80h]
  __int128 v47; // [rsp+90h] [rbp-70h]
  __int128 v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+B0h] [rbp-50h]
  _DWORD v50[20]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v51[4]; // [rsp+110h] [rbp+10h] BYREF
  int v52; // [rsp+114h] [rbp+14h]

  *(_QWORD *)&FileHandle[7] = 0;
  v49 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  memset_0(v50, 0, sizeof(v50));
  v2 = *(_DWORD *)(a1 + 32);
  v3 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  FileHandle[2] = 0;
  v41 = 0;
  v5 = v2 & 1;
  FileHandle[0] = 0;
  v42 = v2 & 0x40000000;
  if ( (v2 & 0x10000000) != 0 )
    v6 = *(_DWORD *)(v4 + 128);
  else
    v6 = *(_DWORD *)(v4 + 96);
  v7 = (v6 >> 4) & 1;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCreateClient: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x IsDir: %c",
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8));
      WPP_SF_qSqqDc(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        v9,
        v10,
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 16),
        *(_QWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        (_BYTE)v7 != 0 ? 89 : 78);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 108) & 4) != 0 )
    {
      v34[0] = *(_DWORD *)(a1 + 104);
      SyncTraceOutputInternal(
        L"SyncActionCreateClient: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x",
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_QWORD *)v34);
      WPP_SF_qqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        48,
        WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_DWORD *)(a1 + 104));
    }
  }
  if ( !(_BYTE)v7 || *(int *)(a1 + 32) >= 0 || (v11 = (*(_DWORD *)(a1 + 32) & 0x1000000) == 0, FileHandle[1] = 1, !v11) )
    FileHandle[1] = 0;
  while ( 1 )
  {
    IntermediateDirectories = SyncOpenUNCPathForPinAndFill(
                                (PHANDLE)&FileHandle[7],
                                2 * v5 + 5,
                                v37,
                                (__int64)FileHandle,
                                1,
                                v5,
                                1);
    if ( IntermediateDirectories != -1073741766 )
      break;
    if ( v3 )
      goto LABEL_20;
    IntermediateDirectories = SyncActionCreateClientpCreateIntermediateDirectories(a1);
    if ( (IntermediateDirectories & 0x80000000) != 0 )
    {
      v13 = 1155;
LABEL_122:
      v30 = 0;
      goto LABEL_123;
    }
    v3 = 1;
  }
  if ( IntermediateDirectories )
  {
LABEL_20:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCreateClient: SyncOpenFileByPathEx failed for '%ws' with %x",
        *(_QWORD *)(a1 + 8),
        IntermediateDirectories);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        49,
        (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 8),
        IntermediateDirectories);
    }
    v13 = 1166;
    goto LABEL_122;
  }
  IntermediateDirectories = SyncHandleIsDisconnected(*(_QWORD *)&FileHandle[7], FileHandle);
  if ( IntermediateDirectories )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCreateClient: SyncHandleIsDisconnected failed for '%ws' with %x",
        *(_QWORD *)(a1 + 8),
        IntermediateDirectories);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        50,
        (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 8),
        IntermediateDirectories);
    }
    v13 = 1176;
    goto LABEL_122;
  }
  v14 = *(_BYTE **)(a1 + 24);
  v15 = FileHandle[0];
  v16 = *(_QWORD *)&FileHandle[7];
  if ( !v14 )
  {
    if ( FileHandle[0] )
      goto LABEL_39;
    goto LABEL_40;
  }
  if ( !FileHandle[0] )
  {
    if ( v14[1] || (v17 = 0, v14[3]) )
      v17 = 1;
    if ( (*v14 || v14[2]) && !v17 )
    {
      v15 = 1;
      goto LABEL_39;
    }
LABEL_40:
    v18 = *(_QWORD *)&FileHandle[7];
    v43 = 0;
    v16 = 0;
    goto LABEL_41;
  }
LABEL_39:
  v43 = *(_QWORD *)&FileHandle[7];
  v18 = 0;
LABEL_41:
  v19 = *(_DWORD *)(a1 + 32);
  v20 = (unsigned int *)(a1 + 104);
  v44 = *(_QWORD *)(a1 + 16);
  v45 = *(_QWORD *)a1;
  v52 = 0;
  memset_0(v51, 0, 0x7Cu);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    LODWORD(v39) = v19;
    SyncTraceOutputInternal(
      L"SyncActionHasFileChanged: Context: 0x%p hRemote: 0x%p hLocal: 0x%p Item: 0x%p Result: 0x%p Flags: 0x%x",
      v45,
      v18,
      v16,
      v44,
      a1 + 104,
      v39);
    WPP_SF_qqqqqD(*((_QWORD *)WPP_GLOBAL_Control + 12), v22, v23, v45, v18, v16, v44, a1 + 104, v19);
  }
  LOBYTE(v37) = v15;
  LOBYTE(v21) = v15 == 0;
  LOBYTE(v35) = v15;
  IntermediateDirectories = SyncItemEnumSingleFile(v18, v16, v43, v21, v35, v37, v51);
  if ( IntermediateDirectories )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
      goto LABEL_53;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionHasFileChanged: SyncItemEnumSingleFile failed with %x",
        IntermediateDirectories);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        23,
        WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
        IntermediateDirectories);
    }
  }
  else
  {
    SyncActionCompareItemState(v45, (unsigned int)v51, v44, a1 + 104, v19);
    if ( (v19 & 8) != 0 )
      *v20 &= 0xFFFFFE0F;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionHasFileChanged: Result = 0x%x, status = 0x%08x ", *v20, IntermediateDirectories);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      24,
      WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
      *v20,
      IntermediateDirectories);
  }
LABEL_53:
  if ( IntermediateDirectories )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCreateClient: SyncActionHasFileChanged failed with %x",
        IntermediateDirectories);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        51,
        WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        IntermediateDirectories);
    }
    v13 = 1220;
    goto LABEL_122;
  }
  if ( (*v20 & 0x100) != 0 )
  {
    v24 = *(_DWORD **)(a1 + 16);
    if ( (*v24 & 0x209F) != 0 || (*v24 & 0x200000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncActionCreateClient: '%ws' has changed remotely since enumeration [%x]",
          *(_QWORD *)(a1 + 8),
          *v20);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          52,
          (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(_QWORD *)(a1 + 8),
          *v20);
      }
      IntermediateDirectories = -1073741823;
      v13 = 1242;
      goto LABEL_122;
    }
  }
  v25 = *(int **)(a1 + 24);
  *v20 = 0;
  if ( v25 )
  {
    v26 = *v25;
    if ( FileHandle[1] )
    {
      *(_BYTE *)v25 = v26 & 0xA;
      *(_BYTE *)(*(_QWORD *)(a1 + 24) + 2LL) = BYTE2(v26) & 0x2A;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v27 = *(unsigned __int8 **)(a1 + 24);
        v36[0] = v27[2];
        SyncTraceOutputInternal(
          L"SyncActionCreateClient: Altered pin clear flags to only contain inherit mask, from %x/%x to %x/%x",
          (unsigned __int8)v26,
          BYTE2(v26),
          *v27,
          *(_QWORD *)v36);
        v38 = **(unsigned __int8 **)(a1 + 24);
        WPP_SF_DDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          53,
          WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          (unsigned __int8)v26,
          BYTE2(v26));
      }
    }
    IntermediateDirectories = SyncItemSetPinInformation(*(HANDLE *)&FileHandle[7]);
    **(_DWORD **)(a1 + 24) = v26;
    if ( IntermediateDirectories )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncActionCreateClient: SyncItemSetPinInformation failed for '%ws' with %x",
          *(_QWORD *)(a1 + 8),
          IntermediateDirectories);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          54,
          (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(_QWORD *)(a1 + 8),
          IntermediateDirectories);
      }
      v13 = 1289;
      goto LABEL_122;
    }
  }
  v28 = v42;
  if ( v42 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      SyncTraceOutputInternal(L"SyncActionCreateClient: File '%ws' is Pin-Only -- jumping out", *(_QWORD *)(a1 + 8));
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        55,
        WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 8));
    }
  }
  else
  {
    if ( FileHandle[0] )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncActionCreateClient: '%ws' is dirty -- failing create op", *(_QWORD *)(a1 + 8));
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          56,
          WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(_QWORD *)(a1 + 8));
      }
      *v20 = 1;
      IntermediateDirectories = -1073741823;
      v13 = 1310;
      goto LABEL_122;
    }
    IntermediateDirectories = SyncHandleIsCached(*(_QWORD *)&FileHandle[7], &FileHandle[2], &v41);
    if ( IntermediateDirectories )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncActionCreateClient: SyncHandleIsCached failed for '%ws' with %x",
          *(_QWORD *)(a1 + 8),
          IntermediateDirectories);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          58,
          (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(_QWORD *)(a1 + 8),
          IntermediateDirectories);
      }
      v13 = 1348;
      goto LABEL_122;
    }
    if ( !FileHandle[2] )
    {
      IntermediateDirectories = v41;
      if ( v41 >= 0 )
        IntermediateDirectories = -1073741584;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncActionCreateClient: File '%ws' does not exist in the cache so cannot fill it",
          *(_QWORD *)(a1 + 8));
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          57,
          WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(_QWORD *)(a1 + 8));
      }
      v13 = 1341;
      goto LABEL_122;
    }
    if ( !(_BYTE)v7 )
    {
      IntermediateDirectories = SyncQueryInformationLocal(*(HANDLE *)&FileHandle[7]);
      if ( IntermediateDirectories )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncActionCreateClient: SyncQueryInformationLocal to find if file is suspended failed with %x",
            IntermediateDirectories);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            59,
            WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
            IntermediateDirectories);
        }
        v13 = 1367;
        goto LABEL_122;
      }
      if ( (v50[0] & 0x20000) != 0 )
      {
        v30 = 1;
        SyncCloseFile(*(HANDLE *)&FileHandle[7]);
        v31 = *(_DWORD **)(a1 + 16);
        *(_QWORD *)&FileHandle[7] = 0;
        *v31 |= 0x200000u;
        IntermediateDirectories = SyncActionSuspendedServerToClient(a1);
        v13 = 1389;
        goto LABEL_123;
      }
      IntermediateDirectories = SyncActionReadFile(a1, *(void **)&FileHandle[7]);
      if ( IntermediateDirectories )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCreateClient: SyncActionReadFile failed with %x", IntermediateDirectories);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            60,
            WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
            IntermediateDirectories);
        }
        v13 = 1399;
        goto LABEL_122;
      }
      IntermediateDirectories = SyncQueryInformationLocal(*(HANDLE *)&FileHandle[7]);
      if ( IntermediateDirectories )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncActionCreateClient: SyncQueryInformationLocal failed with %x",
            IntermediateDirectories);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            61,
            WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
            IntermediateDirectories);
        }
        v13 = 1411;
        goto LABEL_122;
      }
      if ( (v50[0] & 0x20) != 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCreateClient: File is still sparse even after reading! ItemStatus = %x");
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids, v50[0]);
        }
        *v20 |= 0x800u;
        IntermediateDirectories = -1073741757;
        v13 = 1421;
        goto LABEL_122;
      }
    }
  }
  LOBYTE(v38) = 1;
  LOBYTE(v36[0]) = 1;
  v13 = 0;
  SyncItemEnumSingleFile(0, *(_QWORD *)&FileHandle[7], *(_QWORD *)&FileHandle[7], 0, v36[0], v38, a1 + 112);
  if ( v28 )
  {
    v30 = 0;
  }
  else
  {
    SyncItemAddClientEnumInfo(*(_QWORD *)(a1 + 16) + 72LL, 0, a1 + 112);
    v30 = v29;
  }
LABEL_123:
  v32 = *(_QWORD *)&FileHandle[7];
  if ( *(_QWORD *)&FileHandle[7] )
    SyncCloseFile(*(HANDLE *)&FileHandle[7]);
  if ( !v30 && !IntermediateDirectories )
    SyncBackpatchUNCPath(v32, *(_QWORD *)(a1 + 8));
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncActionCreateClient: Result: 0x%x  Return: %x ( EE = %u )",
      *(unsigned int *)(a1 + 104),
      IntermediateDirectories,
      v13);
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      63,
      WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
      *(unsigned int *)(a1 + 104),
      IntermediateDirectories,
      v13);
  }
  return IntermediateDirectories;
}

```

## disassembly

```asm
0x180002540  push    rbp
0x180002542  push    rbx
0x180002543  push    rsi
0x180002544  push    rdi
0x180002545  push    r12
0x180002547  push    r13
0x180002549  push    r14
0x18000254b  push    r15
0x18000254d  lea     rbp, [rsp-0A8h]
0x180002555  sub     rsp, 1A8h
0x18000255c  mov     rax, cs:__security_cookie
0x180002563  xor     rax, rsp
0x180002566  mov     [rbp+0E0h+var_50], rax
0x18000256d  xorps   xmm0, xmm0
0x180002570  xor     edi, edi
0x180002572  mov     r14, rcx
0x180002575  mov     qword ptr [rsp+1E0h+FileHandle+7], rdi
0x18000257a  xor     eax, eax
0x18000257c  lea     rcx, [rbp+0E0h+var_120]; void *
0x180002580  xor     edx, edx; Val
0x180002582  mov     [rbp+0E0h+var_130], rax
0x180002586  lea     r8d, [rdi+50h]; Size
0x18000258a  movups  [rbp+0E0h+var_160], xmm0
0x18000258e  movups  [rbp+0E0h+var_150], xmm0
0x180002592  movups  [rbp+0E0h+var_140], xmm0
0x180002596  call    memset_0
0x18000259b  mov     edx, [r14+20h]
0x18000259f  mov     r13b, dil
0x1800025a2  mov     r9, [r14+10h]
0x1800025a6  mov     eax, edx
0x1800025a8  and     eax, 40000000h
0x1800025ad  mov     [rsp+1E0h+FileHandle+2], dil
0x1800025b2  mov     ebx, edx
0x1800025b4  mov     [rsp+1E0h+var_180], edi
0x1800025b8  and     ebx, 1
0x1800025bb  mov     [rsp+1E0h+FileHandle], dil
0x1800025c0  mov     [rsp+1E0h+var_17C], eax
0x1800025c4  mov     [rsp+1E0h+var_190], dil
0x1800025c9  bt      edx, 1Ch
0x1800025cd  jnb     short loc_1800025D8
0x1800025cf  mov     r12d, [r9+80h]
0x1800025d6  jmp     short loc_1800025DC
0x1800025d8  mov     r12d, [r9+60h]
0x1800025dc  shr     r12d, 4
0x1800025e0  and     r12d, 1
0x1800025e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800025eb  lea     rsi, WPP_GLOBAL_Control
0x1800025f2  cmp     rax, rsi
0x1800025f5  jz      loc_1800026E5
0x1800025fb  test    byte ptr [rax+6Ch], 4
0x1800025ff  jz      short loc_180002680
0x180002601  mov     r8, [r14+8]
0x180002605  mov     al, r12b
0x180002608  neg     al
0x18000260a  mov     rax, [r14+18h]
0x18000260e  sbb     ecx, ecx
0x180002610  and     ecx, 0Bh
0x180002613  add     ecx, 4Eh ; 'N'
0x180002616  mov     dword ptr [rsp+1E0h+var_1B0], ecx
0x18000261a  lea     rcx, aSyncactioncrea_26; "SyncActionCreateClient: Context: 0x%p F"...
0x180002621  mov     [rsp+1E0h+var_1B8], edx
0x180002625  mov     rdx, [r14]
0x180002628  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x18000262d  call    SyncTraceOutputInternal
0x180002632  mov     r9, [r14]
0x180002635  mov     al, r12b
0x180002638  neg     al
0x18000263a  mov     eax, [r14+20h]
0x18000263e  sbb     cl, cl
0x180002640  and     cl, 0Bh
0x180002643  add     cl, 4Eh ; 'N'
0x180002646  mov     byte ptr [rsp+1E0h+var_1A0], cl
0x18000264a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002651  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x180002655  mov     rax, [r14+18h]
0x180002659  mov     [rsp+1E0h+var_1B0], rax
0x18000265e  mov     rax, [r14+10h]
0x180002662  mov     rcx, [rcx+60h]
0x180002666  mov     qword ptr [rsp+1E0h+var_1B8], rax
0x18000266b  mov     rax, [r14+8]
0x18000266f  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x180002674  call    WPP_SF_qSqqDc
0x180002679  mov     rax, cs:WPP_GLOBAL_Control
0x180002680  cmp     rax, rsi
0x180002683  jz      short loc_1800026E5
0x180002685  test    byte ptr [rax+6Ch], 4
0x180002689  jz      short loc_1800026E5
0x18000268b  mov     eax, [r14+68h]
0x18000268f  lea     rcx, aSyncactioncrea_23; "SyncActionCreateClient: TICA 0x%p TICO:"...
0x180002696  mov     r9, [r14+60h]
0x18000269a  mov     r8, [r14+48h]
0x18000269e  mov     rdx, [r14+40h]
0x1800026a2  mov     [rsp+1E0h+var_1C0], eax
0x1800026a6  call    SyncTraceOutputInternal
0x1800026ab  mov     eax, [r14+68h]
0x1800026af  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x1800026b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026bd  mov     edx, 30h ; '0'
0x1800026c2  mov     r9, [r14+40h]
0x1800026c6  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1800026ca  mov     rax, [r14+60h]
0x1800026ce  mov     rcx, [rcx+60h]
0x1800026d2  mov     qword ptr [rsp+1E0h+var_1B8], rax; int
0x1800026d7  mov     rax, [r14+48h]
0x1800026db  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x1800026e0  call    WPP_SF_qqqD
0x1800026e5  test    r12b, r12b
0x1800026e8  jz      short loc_1800026FF
0x1800026ea  cmp     [r14+20h], edi
0x1800026ee  jge     short loc_1800026FF
0x1800026f0  test    dword ptr [r14+20h], 1000000h
0x1800026f8  mov     [rsp+1E0h+FileHandle+1], 1
0x1800026fd  jz      short loc_180002704
0x1800026ff  mov     [rsp+1E0h+FileHandle+1], dil
0x180002704  movzx   esi, r12b
0x180002708  lea     r15d, ds:5[rbx*2]
0x180002710  xor     esi, 1
0x180002713  mov     r8, [r14+8]
0x180002717  lea     rax, [rsp+1E0h+FileHandle]
0x18000271c  mov     [rsp+1E0h+var_198], 1; char
0x180002721  lea     r9d, [rsi+80h]
0x180002728  mov     [rsp+1E0h+var_1A0], ebx; int
0x18000272c  lea     rcx, [rsp+1E0h+FileHandle+7]; FileHandle
0x180002731  mov     [rsp+1E0h+var_1A8], 1; char
0x180002736  mov     [rsp+1E0h+var_1B0], rax; __int64
0x18000273b  mov     [rsp+1E0h+var_1C0], r15d; ULONG
0x180002740  call    SyncOpenUNCPathForPinAndFill
0x180002745  mov     edi, eax
0x180002747  cmp     eax, 0C000003Ah
0x18000274c  jnz     short loc_180002770
0x18000274e  test    r13b, r13b
0x180002751  jnz     short loc_180002777
0x180002753  mov     rcx, r14
0x180002756  call    SyncActionCreateClientpCreateIntermediateDirectories
0x18000275b  mov     edi, eax
0x18000275d  test    eax, eax
0x18000275f  js      short loc_180002766
0x180002761  mov     r13b, 1
0x180002764  jmp     short loc_180002713
0x180002766  mov     ebx, 483h
0x18000276b  jmp     loc_180002FA2
0x180002770  xor     r15d, r15d
0x180002773  test    edi, edi
0x180002775  jz      short loc_1800027D1
0x180002777  mov     rax, cs:WPP_GLOBAL_Control
0x18000277e  lea     r15, WPP_GLOBAL_Control
0x180002785  cmp     rax, r15
0x180002788  jz      short loc_1800027C7
0x18000278a  test    byte ptr [rax+6Ch], 1
0x18000278e  jz      short loc_1800027C7
0x180002790  mov     rdx, [r14+8]
0x180002794  lea     rcx, aSyncactioncrea_10; "SyncActionCreateClient: SyncOpenFileByP"...
0x18000279b  mov     r8d, edi
0x18000279e  call    SyncTraceOutputInternal
0x1800027a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027aa  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x1800027b1  mov     r9, [r14+8]
0x1800027b5  mov     edx, 31h ; '1'
0x1800027ba  mov     [rsp+1E0h+var_1C0], edi
0x1800027be  mov     rcx, [rcx+60h]
0x1800027c2  call    WPP_SF_Sd
0x1800027c7  mov     ebx, 48Eh
0x1800027cc  jmp     loc_180002FA9
0x1800027d1  mov     rcx, qword ptr [rsp+1E0h+FileHandle+7]
0x1800027d6  lea     rdx, [rsp+1E0h+FileHandle]
0x1800027db  call    SyncHandleIsDisconnected
0x1800027e0  mov     edi, eax
0x1800027e2  test    eax, eax
0x1800027e4  jz      short loc_180002840
0x1800027e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800027ed  lea     r15, WPP_GLOBAL_Control
0x1800027f4  cmp     rax, r15
0x1800027f7  jz      short loc_180002836
0x1800027f9  test    byte ptr [rax+6Ch], 1
0x1800027fd  jz      short loc_180002836
0x1800027ff  mov     rdx, [r14+8]
0x180002803  lea     rcx, aSyncactioncrea_32; "SyncActionCreateClient: SyncHandleIsDis"...
0x18000280a  mov     r8d, edi
0x18000280d  call    SyncTraceOutputInternal
0x180002812  mov     rcx, cs:WPP_GLOBAL_Control
0x180002819  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x180002820  mov     r9, [r14+8]
0x180002824  mov     edx, 32h ; '2'
0x180002829  mov     [rsp+1E0h+var_1C0], edi
0x18000282d  mov     rcx, [rcx+60h]
0x180002831  call    WPP_SF_Sd
0x180002836  mov     ebx, 498h
0x18000283b  jmp     loc_180002FA9
0x180002840  mov     rax, [r14+18h]
0x180002844  mov     bl, [rsp+1E0h+FileHandle]
0x180002848  mov     rdi, qword ptr [rsp+1E0h+FileHandle+7]
0x18000284d  test    rax, rax
0x180002850  jz      short loc_18000287A
0x180002852  test    bl, bl
0x180002854  jnz     short loc_18000287E
0x180002856  cmp     [rax+1], r15b
0x18000285a  jnz     short loc_180002865
0x18000285c  mov     cl, r15b
0x18000285f  cmp     [rax+3], r15b
0x180002863  jz      short loc_180002867
0x180002865  mov     cl, 1
0x180002867  cmp     [rax], r15b
0x18000286a  jnz     short loc_180002872
0x18000286c  cmp     [rax+2], r15b
0x180002870  jz      short loc_180002885
0x180002872  test    cl, cl
0x180002874  jnz     short loc_180002885
0x180002876  mov     bl, 1
0x180002878  jmp     short loc_18000287E
0x18000287a  test    bl, bl
0x18000287c  jz      short loc_180002893
0x18000287e  mov     [rsp+1E0h+var_178], rdi
0x180002883  jmp     short loc_18000288E
0x180002885  test    bl, bl
0x180002887  jz      short loc_180002893
0x180002889  mov     [rsp+1E0h+var_178], r15
0x18000288e  mov     rsi, r15
0x180002891  jmp     short loc_18000289E
0x180002893  mov     rsi, rdi
0x180002896  mov     [rsp+1E0h+var_178], r15
0x18000289b  mov     rdi, r15
0x18000289e  mov     rax, [r14+10h]
0x1800028a2  lea     rcx, [rbp+0E0h+var_D0]; void *
0x1800028a6  mov     r13d, [r14+20h]
0x1800028aa  lea     r15, [r14+68h]
0x1800028ae  mov     [rsp+1E0h+var_170], rax
0x1800028b3  xor     edx, edx; Val
0x1800028b5  mov     rax, [r14]
0x1800028b8  mov     [rsp+1E0h+var_168], rax
0x1800028bd  xor     eax, eax
0x1800028bf  mov     [rbp+0E0h+var_CC], eax
0x1800028c2  lea     r8d, [rax+7Ch]; Size
0x1800028c6  call    memset_0
0x1800028cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800028d2  lea     rcx, WPP_GLOBAL_Control
0x1800028d9  cmp     rax, rcx
0x1800028dc  jz      short loc_180002942
0x1800028de  test    byte ptr [rax+6Ch], 4
0x1800028e2  jz      short loc_180002942
0x1800028e4  mov     rax, [rsp+1E0h+var_170]
0x1800028e9  lea     rcx, aSyncactionhasf_2; "SyncActionHasFileChanged: Context: 0x%p"...
0x1800028f0  mov     rdx, [rsp+1E0h+var_168]
0x1800028f5  mov     r9, rdi
0x1800028f8  mov     dword ptr [rsp+1E0h+var_1B0], r13d
0x1800028fd  mov     r8, rsi
0x180002900  mov     qword ptr [rsp+1E0h+var_1B8], r15
0x180002905  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x18000290a  call    SyncTraceOutputInternal
0x18000290f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002916  mov     rax, [rsp+1E0h+var_170]
0x18000291b  mov     r9, [rsp+1E0h+var_168]
0x180002920  mov     [rsp+1E0h+var_1A0], r13d
0x180002925  mov     rcx, [rcx+60h]
0x180002929  mov     qword ptr [rsp+1E0h+var_1A8], r15
0x18000292e  mov     [rsp+1E0h+var_1B0], rax
0x180002933  mov     qword ptr [rsp+1E0h+var_1B8], rdi
0x180002938  mov     qword ptr [rsp+1E0h+var_1C0], rsi
0x18000293d  call    WPP_SF_qqqqqD
0x180002942  mov     r8, [rsp+1E0h+var_178]
0x180002947  lea     rax, [rbp+0E0h+var_D0]
0x18000294b  mov     [rsp+1E0h+var_1B0], rax
0x180002950  test    bl, bl
0x180002952  mov     byte ptr [rsp+1E0h+var_1B8], bl
0x180002956  mov     rdx, rdi
0x180002959  setz    r9b
0x18000295d  mov     byte ptr [rsp+1E0h+var_1C0], bl
0x180002961  mov     rcx, rsi
0x180002964  call    SyncItemEnumSingleFile
0x180002969  mov     edi, eax
0x18000296b  test    eax, eax
0x18000296d  jz      short loc_1800029BB
0x18000296f  mov     rax, cs:WPP_GLOBAL_Control
0x180002976  lea     rsi, WPP_GLOBAL_Control
0x18000297d  cmp     rax, rsi
0x180002980  jz      loc_180002A31
0x180002986  test    byte ptr [rax+6Ch], 1
0x18000298a  jz      short loc_1800029EA
0x18000298c  mov     edx, edi
0x18000298e  lea     rcx, aSyncactionhasf; "SyncActionHasFileChanged: SyncItemEnumS"...
0x180002995  call    SyncTraceOutputInternal
0x18000299a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029a1  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x1800029a8  mov     edx, 17h
0x1800029ad  mov     r9d, edi
0x1800029b0  mov     rcx, [rcx+60h]
0x1800029b4  call    WPP_SF_d
0x1800029b9  jmp     short loc_1800029EA
0x1800029bb  mov     r8, [rsp+1E0h+var_170]
0x1800029c0  lea     rdx, [rbp+0E0h+var_D0]
0x1800029c4  mov     rcx, [rsp+1E0h+var_168]
0x1800029c9  mov     r9, r15
0x1800029cc  mov     [rsp+1E0h+var_1C0], r13d
0x1800029d1  call    SyncActionCompareItemState
0x1800029d6  lea     rsi, WPP_GLOBAL_Control
0x1800029dd  test    r13b, 8
0x1800029e1  jz      short loc_1800029EA
0x1800029e3  and     dword ptr [r15], 0FFFFFE0Fh
0x1800029ea  mov     rax, cs:WPP_GLOBAL_Control
0x1800029f1  cmp     rax, rsi
0x1800029f4  jz      short loc_180002A31
  ... truncated ...
```
