# CleanupIpDatabase

- ea: `0x1800503c8`
- end: `0x180051340`
- name: `CleanupIpDatabase`
- size: `3960`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004ff20`

## callees

- `0x18000282c`
- `0x180003228`
- `0x180003c90`
- `0x1800057e0`
- `0x180006234`
- `0x18000c164`
- `0x18000d028`
- `0x18000e1a0`
- `0x18000e1d0`
- `0x18000e204`
- `0x18000e24c`
- `0x18000e284`
- `0x18000e410`
- `0x18000e540`
- `0x18000e78c`
- `0x18000e7c0`
- `0x18000e814`
- `0x18001c45c`
- `0x180020094`
- `0x180020bec`
- `0x1800250e8`
- `0x180030ed4`
- `0x18003147c`
- `0x1800314cc`
- `0x1800503c8`
- `0x1800516fc`
- `0x18005ea38`
- `0x18008eef8`
- `0x18008ef8c`
- `0x18008f020`
- `0x18008f58c`
- `0x180093144`
- `0x1800932a8`
- `0x18009481c`
- `0x180098a40`
- `0x1800a03f0`
- `0x1800a08f4`
- `0x1800a0b68`
- `0x1800a0bac`
- `0x1800cdac0`
- `0x1800cf010`

## import_xrefs

- `msvcrt!time` at `0x1800504b3`
- `msvcrt!time` at `0x180050871`
- `msvcrt!time` at `0x180051267`
- `msvcrt!time` at `0x1800504b3`
- `msvcrt!time` at `0x180050871`
- `msvcrt!time` at `0x180051267`
- `ESENT!JetSetCurrentIndex` at `0x1800505a1`
- `ESENT!JetSetCurrentIndex` at `0x1800505a1`
- `ESENT!JetMakeKey` at `0x1800505dd`
- `ESENT!JetMakeKey` at `0x1800505dd`
- `ESENT!JetSeek` at `0x180050611`
- `ESENT!JetSeek` at `0x180050611`
- `ESENT!JetPrepareUpdate` at `0x180050b7c`
- `ESENT!JetPrepareUpdate` at `0x180050ea9`
- `ESENT!JetPrepareUpdate` at `0x180050b7c`
- `ESENT!JetPrepareUpdate` at `0x180050ea9`
- `KERNEL32!LocalFree` at `0x180050d84`
- `KERNEL32!LocalFree` at `0x180050d84`
- `KERNEL32!CompareFileTime` at `0x180050aa9`
- `KERNEL32!CompareFileTime` at `0x180050af2`
- `KERNEL32!CompareFileTime` at `0x180050aa9`
- `KERNEL32!CompareFileTime` at `0x180050af2`
- `KERNEL32!EnterCriticalSection` at `0x1800504d4`
- `KERNEL32!EnterCriticalSection` at `0x180050579`
- `KERNEL32!EnterCriticalSection` at `0x1800504d4`
- `KERNEL32!EnterCriticalSection` at `0x180050579`
- `KERNEL32!LeaveCriticalSection` at `0x18005123f`
- `KERNEL32!LeaveCriticalSection` at `0x180051309`
- `KERNEL32!LeaveCriticalSection` at `0x18005123f`
- `KERNEL32!LeaveCriticalSection` at `0x180051309`
- `KERNEL32!HeapFree` at `0x180051080`
- `KERNEL32!HeapFree` at `0x1800510d2`
- `KERNEL32!HeapFree` at `0x1800512e7`
- `KERNEL32!HeapFree` at `0x180051080`
- `KERNEL32!HeapFree` at `0x1800510d2`
- `KERNEL32!HeapFree` at `0x1800512e7`

## string_xrefs

- `0x1800509c5`: `DhcpJetRollBack`
- `0x180050f32`: `DhcpJetCommitTransaction`
- `0x180050b88`: `Cleanup:PrepareUpdate`
- `0x180050eb5`: `Cleanup:PrepareUpdate`

## pseudocode

```c
__int64 __fastcall CleanupIpDatabase(FILETIME *a1, FILETIME *a2, int a3, _DWORD *a4, _DWORD *a5)
{
  int v6; // r15d
  unsigned int v7; // r14d
  int v8; // ebx
  void *v9; // rcx
  __int64 v10; // r8
  int v11; // r14d
  unsigned int v12; // eax
  unsigned int Key; // eax
  unsigned int v14; // eax
  unsigned int Value; // ebx
  unsigned int v16; // eax
  _DWORD *v17; // r14
  int v18; // r15d
  int v19; // eax
  __int64 v20; // rcx
  int IsSet; // eax
  int v22; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  int v29; // r15d
  int v30; // eax
  int String; // eax
  unsigned int v32; // eax
  __int64 v33; // r9
  const char *v34; // r8
  int v35; // eax
  unsigned int v36; // eax
  int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  int v41; // eax
  __int64 v42; // rbx
  __int64 v43; // rax
  u_long v44; // r14d
  int v45; // r12d
  int v46; // r15d
  int v47; // eax
  unsigned int v48; // eax
  int v49; // eax
  unsigned int v50; // eax
  int v51; // eax
  int v52; // ecx
  int v53; // ecx
  unsigned int v54; // eax
  char *v55; // rdx
  int v56; // eax
  int Record; // eax
  _BYTE v59[4]; // [rsp+40h] [rbp-108h] BYREF
  unsigned int v60; // [rsp+44h] [rbp-104h]
  int v61; // [rsp+48h] [rbp-100h]
  u_long hostlong; // [rsp+4Ch] [rbp-FCh] BYREF
  unsigned int pcbActual; // [rsp+50h] [rbp-F8h] BYREF
  char v64[4]; // [rsp+54h] [rbp-F4h] BYREF
  unsigned int v65; // [rsp+58h] [rbp-F0h] BYREF
  int pvData; // [rsp+5Ch] [rbp-ECh] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-E8h] BYREF
  int v68; // [rsp+68h] [rbp-E0h] BYREF
  int v69; // [rsp+6Ch] [rbp-DCh]
  unsigned int v70; // [rsp+70h] [rbp-D8h] BYREF
  unsigned int v71; // [rsp+78h] [rbp-D0h] BYREF
  unsigned int v72; // [rsp+7Ch] [rbp-CCh] BYREF
  unsigned int v73; // [rsp+80h] [rbp-C8h] BYREF
  int v74; // [rsp+84h] [rbp-C4h]
  unsigned int v75; // [rsp+88h] [rbp-C0h] BYREF
  unsigned int Size; // [rsp+8Ch] [rbp-BCh] BYREF
  unsigned int Size_4; // [rsp+90h] [rbp-B8h]
  FILETIME FileTime1; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-A8h] BYREF
  _DWORD *v80; // [rsp+A8h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-98h] BYREF
  _DWORD *v82; // [rsp+B8h] [rbp-90h]
  FILETIME *lpFileTime2; // [rsp+C0h] [rbp-88h]
  FILETIME *v84; // [rsp+C8h] [rbp-80h]
  unsigned __int64 v85; // [rsp+D0h] [rbp-78h]
  FILETIME *v86; // [rsp+D8h] [rbp-70h]
  FILETIME *v87; // [rsp+E0h] [rbp-68h]
  __int64 p_hostlong; // [rsp+E8h] [rbp-60h] BYREF
  int v89; // [rsp+F0h] [rbp-58h]
  int v90; // [rsp+F4h] [rbp-54h]
  int *v91; // [rsp+F8h] [rbp-50h]
  __int64 v92; // [rsp+100h] [rbp-48h]

  v6 = a3;
  v84 = a2;
  lpFileTime2 = a1;
  v86 = a1;
  v87 = a2;
  v82 = a5;
  FileTime1 = 0;
  pcbActual = 0;
  lpMem = 0;
  v65 = 0;
  hostlong = 0;
  pvData = 0;
  v59[0] = 0;
  Size_4 = 0;
  v80 = 0;
  v79 = 0;
  v68 = 0;
  v75 = 0;
  v7 = 0;
  v60 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids);
  *a4 = 0;
  *a5 = 0;
  v74 = 50;
  v85 = time(0) + 180000;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v8 = 1;
  v69 = 1;
  if ( !(unsigned int)DhcpJetPrepareSearch(*(_QWORD *)DhcpGlobalClientTable, 1, 0, 0) )
  {
    pcbActual = 4;
    if ( !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &pvData, &pcbActual) )
    {
      if ( v6 )
      {
        DhcpGlobalScavengeStartAddress = 0;
      }
      else if ( DhcpGlobalScavengeStartAddress )
      {
        pvData = DhcpGlobalScavengeStartAddress++;
      }
      while ( 1 )
      {
        v68 = 0;
        v11 = 0;
        v61 = 0;
        if ( DhcpGlobalServiceStopping )
          goto LABEL_197;
        if ( !v8 )
        {
          EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
          v69 = 1;
        }
        v12 = JetSetCurrentIndex(
                DhcpGlobalJetServerSession,
                DhcpGlobalClientTableHandle,
                *(_QWORD *)DhcpGlobalClientTable);
        if ( (unsigned int)DhcpMapJetError(v12, "Cleanup:SetCurrentIndex") )
          goto LABEL_197;
        Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, &pvData, 4u, 1u);
        if ( (unsigned int)DhcpMapJetError(Key, "Cleanup:MakeKey") )
          goto LABEL_197;
        v14 = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 8u);
        if ( (unsigned int)DhcpMapJetError(v14, "Cleanup:Seek") )
          goto LABEL_197;
        pcbActual = 4;
        Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &hostlong, &pcbActual);
        if ( Value )
          goto LABEL_173;
        if ( !v6 )
          DhcpGlobalScavengeStartAddress = hostlong;
        if ( (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, hostlong) )
        {
          Value = 0;
          goto LABEL_173;
        }
        pcbActual = 8;
        Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &FileTime1, &pcbActual);
        if ( Value )
          goto LABEL_173;
        v16 = (hostlong & 0xF0000000) == 0xE0000000
            ? MemServerGetMAddressInfo(
                (_DWORD)DhcpGlobalThisServer,
                hostlong,
                (unsigned int)&v80,
                (unsigned int)&v79,
                0,
                0)
            : MemServerGetUAddressInfo(
                (_DWORD)DhcpGlobalThisServer,
                hostlong,
                (unsigned int)&v80,
                (unsigned int)&v79,
                0,
                0);
        Value = v16;
        if ( v16 || !v79 )
          goto LABEL_173;
        v17 = v80;
        if ( !v80 )
          goto LABEL_131;
        v18 = v80[1073];
        if ( v18 == 1 )
        {
          v19 = v80[1077];
          if ( v19 != 5 && v19 != 3 && (!*(_DWORD *)&gFailoverEnableCommInt || v19 != 4) )
            goto LABEL_40;
        }
        if ( v18 == 1 )
        {
          if ( v80[1074] == 1 )
            v20 = *(_QWORD *)(v79 + 56);
          else
            v20 = *(_QWORD *)(v79 + 64);
          IsSet = MemBitIsSet(v20, hostlong - *(_DWORD *)v79);
          if ( v17[1077] == 3 && !IsSet )
          {
            Value = 0;
LABEL_40:
            v11 = 0;
            goto LABEL_172;
          }
          v22 = v17[1077];
          if ( v22 == 5 || v22 == 4 )
          {
            v71 = 0;
            v72 = 0;
            v73 = 0;
            pcbActual = 4;
            Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 232), &v71, &pcbActual);
            if ( Value )
              goto LABEL_40;
            pcbActual = 4;
            Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), &v72, &pcbActual);
            if ( Value )
              goto LABEL_40;
            pcbActual = 4;
            Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 248), &v73, &pcbActual);
            if ( Value )
              goto LABEL_40;
            v23 = DhcpCalculateUTCTime(&FileTime1);
            if ( v23 < v71 )
              v23 = v71;
            if ( v23 < v72 )
              v23 = v72;
            if ( v23 < v73 )
              v23 = v73;
            v24 = time(0);
            if ( v23 >= v24 )
              v25 = DhcpCalculateTime(v23 - v24);
            else
              v25 = DhcpCalculatePastTime(v24 - v23);
            FileTime1 = (FILETIME)(v25 + 10000000LL * (unsigned int)v17[1076]);
          }
        }
        Value = 0;
        if ( !DhcpGlobalUseNoDns )
        {
          pcbActual = 1;
          v26 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), v59, &pcbActual);
          Value = v26;
          if ( v26 )
          {
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_85;
            }
            v28 = 17;
          }
          else
          {
            Value = DhcpJetBeginTransaction();
            if ( Value )
              goto LABEL_85;
            if ( v59[0] >= 0 )
            {
              if ( (v59[0] & 0x40) != 0 )
                DhcpDoDynDnsRefresh(hostlong);
            }
            else if ( (unsigned int)DhcpDoDynDnsCheckDelete(hostlong) )
            {
              v29 = 0;
              if ( v17[1073] != 1 )
              {
                v30 = DhcpJetDeleteCurrentRecord();
                goto LABEL_68;
              }
              v30 = DhcpHandleFailoverRequest(v17, hostlong, 1, 0);
              if ( v30 )
                goto LABEL_74;
              v29 = 1;
              ++v60;
LABEL_68:
              if ( v30 )
              {
LABEL_74:
                v32 = DhcpJetRollBack();
                Value = v32;
                v11 = 1;
                if ( v32 )
                {
                  v33 = 733;
                  goto LABEL_76;
                }
              }
              else
              {
                Value = DhcpJetCommitTransaction();
                if ( v17[1073] != 1 || v29 == 1 )
                  ++*v82;
                v11 = 0;
              }
              String = GetString(1083);
              DhcpUpdateAuditLog(16, String, hostlong, 0, 0, 0);
              goto LABEL_172;
            }
            v26 = DhcpJetCommitTransaction();
            Value = v26;
            if ( !v26 )
              goto LABEL_85;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_85;
            }
            v28 = 18;
          }
          WPP_SF_D(v27[2], v28, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v26);
        }
LABEL_85:
        if ( v17[1073] == 1 )
        {
          v35 = v17[1077];
          if ( v35 == 5 || v35 == 4 && *(_DWORD *)&gFailoverEnableCommInt )
          {
            v75 = 4;
            v36 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 312), &v68, &v75);
            Value = v36;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v36);
            }
          }
        }
        if ( CompareFileTime(&FileTime1, lpFileTime2) >= 0 && (v17[1073] != 1 || (v68 & 0x10) == 0) )
          goto LABEL_40;
        v6 = a3;
        if ( a3 || CompareFileTime(&FileTime1, v84) < 0 || v17[1073] == 1 && (v68 & 0x10) != 0 )
        {
          v64[0] = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v42 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v43 = DhcpIpAddressToDottedString(hostlong);
            WPP_SF_s(v42, 20, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v43);
          }
          pcbActual = 1;
          if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), v64, &pcbActual) )
            v64[0] = 1;
          if ( v64[0] == 2 )
          {
            v44 = hostlong;
            hMem = 0;
            Size = 0;
            Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &hMem, &Size);
            if ( !Value )
            {
              Value = DoIcmpRequestForDynBootp(v44, hMem, Size);
              if ( hMem )
                LocalFree(hMem);
            }
            goto LABEL_131;
          }
          if ( v17[1073] != 1 )
          {
            Value = DhcpReleaseAddress(hostlong);
            if ( Value )
            {
              DhcpReleaseBootpAddress(hostlong);
              Value = 0;
            }
            goto LABEL_135;
          }
          pcbActual = 1;
          v48 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), v59, &pcbActual);
          Value = v48;
          if ( v48 )
          {
            DhcpPrintFOErrorEx(v48, "CleanupIpDatabase", "DhcpJetGetValue", 844);
LABEL_131:
            v11 = 0;
            goto LABEL_173;
          }
          v49 = v59[0] & 3;
          if ( v49 == 3 || v49 == 2 )
            goto LABEL_135;
          v32 = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
          if ( v32 )
          {
            v33 = 852;
            v34 = "DhcpDALJetBeginTransaction";
            goto LABEL_77;
          }
          v50 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 2u);
          if ( !(unsigned int)DhcpDALMapJetError(v50, "Cleanup:PrepareUpdate") )
          {
            v59[0] |= 3u;
            if ( !(unsigned int)DhcpDALJetSetValue(
                                  DhcpGlobalJetServerSession,
                                  DhcpGlobalClientTableHandle,
                                  *(_DWORD *)(DhcpGlobalClientTable + 40),
                                  (unsigned int)v59,
                                  1u)
              && !(unsigned int)DhcpJetCommitUpdate() )
            {
              v32 = DhcpJetCommitTransaction();
              Value = v32;
              if ( v32 )
              {
                v33 = 883;
                v34 = "DhcpJetCommitTransaction";
                goto LABEL_77;
              }
LABEL_135:
              v65 = 0;
              lpMem = 0;
              if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &lpMem, &v65) )
                goto LABEL_131;
              if ( (unsigned int)DhcpJetBeginTransaction() )
                goto LABEL_197;
              v45 = DhcpDoDynDnsCheckDelete(hostlong);
              v46 = 0;
              if ( v17[1073] != 1 )
              {
                v47 = DhcpJetDeleteCurrentRecord();
                goto LABEL_154;
              }
              v47 = DhcpHandleFailoverRequest(v17, hostlong, 1, 0);
              if ( v47 )
                goto LABEL_170;
              ++v60;
              v46 = 1;
LABEL_154:
              if ( v47 )
              {
LABEL_170:
                v32 = DhcpJetRollBack();
                Value = v32;
                v11 = 1;
                if ( v32 )
                {
                  v33 = 936;
LABEL_76:
                  v34 = "DhcpJetRollBack";
LABEL_77:
                  DhcpPrintFOErrorEx(v32, "CleanupIpDatabase", v34, v33);
LABEL_197:
                  v7 = v60;
                  break;
                }
              }
              else
              {
                Value = DhcpJetCommitTransaction();
                v70 = Value;
                if ( v17[1073] != 1 || v46 == 1 )
                  ++*v82;
                if ( v45 )
                {
                  v51 = GetString(1083);
                  v52 = 16;
                }
                else
                {
                  v51 = GetString(1084);
                  v52 = 17;
                }
                DhcpUpdateAuditLog(v52, v51, hostlong, 0, 0, 0);
                v53 = hostlong & DhcpGetSubnetMaskForAddress(hostlong);
                v54 = v65;
                if ( v65 > 4 && v53 == *(_DWORD *)lpMem )
                {
                  v55 = (char *)lpMem + 4;
                  v54 = v65 - 4;
                  v65 -= 4;
                }
                else
                {
                  v55 = (char *)lpMem;
                }
                if ( qword_1801577F8 )
                  ((void (__fastcall *)(_QWORD, char *, _QWORD, _QWORD, _DWORD))qword_1801577F8)(
                    hostlong,
                    v55,
                    v54,
                    0,
                    0);
                v11 = v61;
                if ( lpMem )
                  HeapFree(gDhcpHeap, 0, lpMem);
                lpMem = 0;
                v65 = 0;
              }
LABEL_172:
              v6 = a3;
              goto LABEL_173;
            }
          }
          v32 = DhcpJetRollBack();
          Value = v32;
          v11 = 1;
          if ( v32 )
          {
            v33 = 879;
            goto LABEL_76;
          }
        }
        else
        {
          pcbActual = 1;
          Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), v59, &pcbActual);
          if ( Value )
            goto LABEL_131;
          v37 = v59[0] & 3;
          if ( v37 == 3 || v37 == 2 )
            goto LABEL_131;
          if ( (unsigned int)DhcpJetBeginTransaction() )
            goto LABEL_197;
          v38 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, Value + 2);
          if ( !(unsigned int)DhcpMapJetError(v38, "Cleanup:PrepareUpdate") )
          {
            v59[0] |= 3u;
            if ( !(unsigned int)DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), v59, 1u)
              && !(unsigned int)DhcpJetCommitUpdate() )
            {
              Value = DhcpJetCommitTransaction();
              if ( Value )
                goto LABEL_197;
              if ( v17[1073] != 1 )
                goto LABEL_120;
              Value = DhcpJetBeginTransaction();
              if ( !Value )
              {
                v39 = DhcpHandleFailoverRequest(v17, hostlong, 0, 0);
                Value = v39;
                if ( v39 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      21,
                      &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                      v39);
                  }
                  Value = DhcpJetRollBack();
                  v11 = 1;
                  if ( Value )
                    goto LABEL_197;
                }
                else
                {
                  v40 = DhcpJetCommitTransaction();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      22,
                      &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                      v40);
                  }
LABEL_120:
                  v11 = 0;
                }
                v41 = GetString(1085);
                DhcpUpdateAuditLog(18, v41, hostlong, 0, 0, 0);
                goto LABEL_173;
              }
              goto LABEL_131;
            }
          }
          Value = DhcpJetRollBack();
          v11 = 1;
          if ( Value )
            goto LABEL_197;
        }
LABEL_173:
        if ( lpMem )
        {
          HeapFree(gDhcpHeap, 0, lpMem);
          lpMem = 0;
          v65 = 0;
        }
        if ( Value )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, Value);
          }
          Size_4 = Value;
        }
        if ( v11 == 1 )
        {
          p_hostlong = (__int64)&hostlong;
          v89 = 4;
          v90 = 1;
          v56 = DhcpDALJetPrepareSearchEx(
                  DhcpGlobalJetServerSession,
                  DhcpGlobalClientTableHandle,
                  (__int64)&p_hostlong,
                  1,
                  8u);
          if ( v56 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_dD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                hostlong,
                v56);
            }
            goto LABEL_197;
          }
        }
        Record = DhcpJetNextRecord();
        if ( Record == 259 )
        {
          v7 = v60;
          if ( !v6 )
            DhcpGlobalScavengeStartAddress = 0;
          break;
        }
        if ( !Record )
        {
          pcbActual = 4;
          if ( !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &pvData, &pcbActual) )
          {
            if ( !v6 )
              DhcpGlobalScavengeStartAddress = pvData;
            v8 = v69;
            if ( !v69 )
              continue;
            if ( !--v74 )
            {
              LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
              v8 = 0;
              v69 = 0;
              v74 = 50;
            }
            if ( v6 || time(0) < v85 )
              continue;
          }
        }
        goto LABEL_197;
      }
    }
  }
  if ( *(_DWORD *)&isDhcpFailoverTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
  {
    v70 = v7;
    v91 = (int *)&v70;
    v92 = 4;
    McGenEventWrite_EventWriteTransfer(v9, &TotalLeasesDeleted, v10, 2, &p_hostlong);
  }
  if ( lpMem )
  {
    HeapFree(gDhcpHeap, 0, lpMem);
    lpMem = 0;
    v65 = 0;
  }
  if ( v69 )
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return Size_4;
}

```

## disassembly

```asm
0x1800503c8  mov     r11, rsp
0x1800503cb  mov     [r11+18h], r8d
0x1800503cf  push    rbx
0x1800503d0  push    rsi
0x1800503d1  push    rdi
0x1800503d2  push    r12
0x1800503d4  push    r13
0x1800503d6  push    r14
0x1800503d8  push    r15
0x1800503da  sub     rsp, 110h
0x1800503e1  mov     rax, cs:__security_cookie
0x1800503e8  xor     rax, rsp
0x1800503eb  mov     [rsp+148h+var_40], rax
0x1800503f3  mov     rbx, r9
0x1800503f6  mov     r15d, r8d
0x1800503f9  mov     [rsp+148h+var_80], rdx
0x180050401  mov     [rsp+148h+lpFileTime2], rcx
0x180050409  mov     [rsp+148h+var_70], rcx
0x180050411  mov     [rsp+148h+var_68], rdx
0x180050419  mov     rsi, [rsp+148h+arg_20]
0x180050421  mov     [rsp+148h+var_90], rsi
0x180050429  xor     edi, edi
0x18005042b  mov     [r11-0B0h], rdi
0x180050432  mov     [rsp+148h+pcbActual], edi
0x180050436  mov     [rsp+148h+lpMem], rdi
0x18005043b  mov     [rsp+148h+var_F0], edi
0x18005043f  mov     [rsp+148h+hostlong], edi
0x180050443  mov     [rsp+148h+pvData], edi
0x180050447  mov     [rsp+148h+var_108], dil
0x18005044c  mov     dword ptr [rsp+148h+Size+4], edi
0x180050453  mov     [r11-0A0h], rdi
0x18005045a  mov     [r11-0A8h], rdi
0x180050461  mov     [rsp+148h+var_E0], edi
0x180050465  mov     [rsp+148h+var_C0], edi
0x18005046c  mov     r14d, edi
0x18005046f  mov     [rsp+148h+var_104], edi
0x180050473  lea     r12, WPP_GLOBAL_Control
0x18005047a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050481  cmp     rcx, r12
0x180050484  jz      short loc_1800504A2
0x180050486  test    dword ptr [rcx+1Ch], 8000h
0x18005048d  jz      short loc_1800504A2
0x18005048f  lea     edx, [rdi+10h]
0x180050492  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180050499  mov     rcx, [rcx+10h]
0x18005049d  call    WPP_SF_
0x1800504a2  mov     [rbx], edi
0x1800504a4  mov     [rsi], edi
0x1800504a6  mov     [rsp+148h+var_C4], 32h ; '2'
0x1800504b1  xor     ecx, ecx; Time
0x1800504b3  call    cs:__imp_time
0x1800504ba  nop     dword ptr [rax+rax+00h]
0x1800504bf  add     rax, 2BF20h
0x1800504c5  mov     [rsp+148h+var_78], rax
0x1800504cd  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800504d4  call    cs:__imp_EnterCriticalSection
0x1800504db  nop     dword ptr [rax+rax+00h]
0x1800504e0  mov     esi, 1
0x1800504e5  mov     ebx, esi
0x1800504e7  mov     [rsp+148h+var_DC], ebx
0x1800504eb  xor     r9d, r9d
0x1800504ee  xor     r8d, r8d
0x1800504f1  mov     edx, esi
0x1800504f3  mov     rcx, cs:DhcpGlobalClientTable
0x1800504fa  mov     rcx, [rcx]
0x1800504fd  call    DhcpJetPrepareSearch
0x180050502  test    eax, eax
0x180050504  jnz     loc_180051286
0x18005050a  lea     r13d, [rsi+3]
0x18005050e  mov     [rsp+148h+pcbActual], r13d
0x180050513  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050518  lea     rdx, [rsp+148h+pvData]; pvData
0x18005051d  mov     rcx, cs:DhcpGlobalClientTable
0x180050524  mov     ecx, [rcx+8]; columnid
0x180050527  call    DhcpJetGetValue
0x18005052c  test    eax, eax
0x18005052e  jnz     loc_180051286
0x180050534  test    r15d, r15d
0x180050537  jz      short loc_180050541
0x180050539  mov     cs:DhcpGlobalScavengeStartAddress, edi
0x18005053f  jmp     short loc_180050557
0x180050541  mov     eax, cs:DhcpGlobalScavengeStartAddress
0x180050547  test    eax, eax
0x180050549  jz      short loc_180050557
0x18005054b  mov     [rsp+148h+pvData], eax
0x18005054f  add     eax, esi
0x180050551  mov     cs:DhcpGlobalScavengeStartAddress, eax
0x180050557  mov     [rsp+148h+var_E0], edi
0x18005055b  mov     r14d, edi
0x18005055e  mov     [rsp+148h+var_100], edi
0x180050562  cmp     cs:DhcpGlobalServiceStopping, edi
0x180050568  jnz     loc_180051281
0x18005056e  test    ebx, ebx
0x180050570  jnz     short loc_180050589
0x180050572  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180050579  call    cs:__imp_EnterCriticalSection
0x180050580  nop     dword ptr [rax+rax+00h]
0x180050585  mov     [rsp+148h+var_DC], esi
0x180050589  mov     r8, cs:DhcpGlobalClientTable
0x180050590  mov     r8, [r8]
0x180050593  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18005059a  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800505a1  call    cs:__imp_JetSetCurrentIndex
0x1800505a8  nop     dword ptr [rax+rax+00h]
0x1800505ad  lea     rdx, aCleanupSetcurr; "Cleanup:SetCurrentIndex"
0x1800505b4  mov     ecx, eax
0x1800505b6  call    DhcpMapJetError
0x1800505bb  test    eax, eax
0x1800505bd  jnz     loc_180051281
0x1800505c3  mov     [rsp+148h+grbit], esi; grbit
0x1800505c7  mov     r9d, r13d; cbData
0x1800505ca  lea     r8, [rsp+148h+pvData]; pvData
0x1800505cf  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800505d6  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800505dd  call    cs:__imp_JetMakeKey
0x1800505e4  nop     dword ptr [rax+rax+00h]
0x1800505e9  lea     rdx, aCleanupMakekey; "Cleanup:MakeKey"
0x1800505f0  mov     ecx, eax
0x1800505f2  call    DhcpMapJetError
0x1800505f7  test    eax, eax
0x1800505f9  jnz     loc_180051281
0x1800505ff  lea     r8d, [rax+8]; grbit
0x180050603  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18005060a  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180050611  call    cs:__imp_JetSeek
0x180050618  nop     dword ptr [rax+rax+00h]
0x18005061d  lea     rdx, aCleanupSeek; "Cleanup:Seek"
0x180050624  mov     ecx, eax
0x180050626  call    DhcpMapJetError
0x18005062b  test    eax, eax
0x18005062d  jnz     loc_180051281
0x180050633  mov     [rsp+148h+pcbActual], r13d
0x180050638  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x18005063d  lea     rdx, [rsp+148h+hostlong]; pvData
0x180050642  mov     rcx, cs:DhcpGlobalClientTable
0x180050649  mov     ecx, [rcx+8]; columnid
0x18005064c  call    DhcpJetGetValue
0x180050651  mov     ebx, eax
0x180050653  test    eax, eax
0x180050655  jnz     loc_1800510BF
0x18005065b  test    r15d, r15d
0x18005065e  jnz     short loc_18005066A
0x180050660  mov     eax, [rsp+148h+hostlong]
0x180050664  mov     cs:DhcpGlobalScavengeStartAddress, eax
0x18005066a  mov     edx, [rsp+148h+hostlong]
0x18005066e  mov     rcx, cs:DhcpGlobalThisServer
0x180050675  call    MemServerIsReservedAddress
0x18005067a  test    eax, eax
0x18005067c  jz      short loc_180050685
0x18005067e  mov     ebx, edi
0x180050680  jmp     loc_1800510BF
0x180050685  mov     [rsp+148h+pcbActual], 8
0x18005068d  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050692  lea     rdx, [rsp+148h+FileTime1]; pvData
0x18005069a  mov     rcx, cs:DhcpGlobalClientTable
0x1800506a1  mov     ecx, [rcx+58h]; columnid
0x1800506a4  call    DhcpJetGetValue
0x1800506a9  mov     ebx, eax
0x1800506ab  test    eax, eax
0x1800506ad  jnz     loc_1800510BF
0x1800506b3  mov     edx, [rsp+148h+hostlong]
0x1800506b7  mov     rcx, cs:DhcpGlobalThisServer
0x1800506be  mov     eax, edx
0x1800506c0  and     eax, 0F0000000h
0x1800506c5  mov     qword ptr [rsp+148h+var_120], rdi
0x1800506ca  lea     r9, [rsp+148h+var_A8]
0x1800506d2  lea     r8, [rsp+148h+var_A0]
0x1800506da  mov     qword ptr [rsp+148h+grbit], rdi
0x1800506df  cmp     eax, 0E0000000h
0x1800506e4  jnz     short loc_1800506ED
0x1800506e6  call    MemServerGetMAddressInfo
0x1800506eb  jmp     short loc_1800506F2
0x1800506ed  call    MemServerGetUAddressInfo
0x1800506f2  mov     ebx, eax
0x1800506f4  test    eax, eax
0x1800506f6  jnz     loc_1800510BF
0x1800506fc  mov     rcx, [rsp+148h+var_A8]
0x180050704  test    rcx, rcx
0x180050707  jz      loc_1800510BF
0x18005070d  mov     r14, [rsp+148h+var_A0]
0x180050715  test    r14, r14
0x180050718  jz      loc_180050D90
0x18005071e  mov     r15d, [r14+10C4h]
0x180050725  cmp     r15d, esi
0x180050728  jnz     short loc_180050748
0x18005072a  mov     eax, [r14+10D4h]
0x180050731  cmp     eax, 5
0x180050734  jz      short loc_180050748
0x180050736  cmp     eax, 3
0x180050739  jz      short loc_180050748
0x18005073b  cmp     cs:gFailoverEnableCommInt, edi
0x180050741  jz      short loc_18005078A
0x180050743  cmp     eax, r13d
0x180050746  jnz     short loc_18005078A
0x180050748  mov     eax, edi
0x18005074a  cmp     r15d, esi
0x18005074d  jnz     loc_1800508AE
0x180050753  mov     edx, [rsp+148h+hostlong]
0x180050757  sub     edx, [rcx]
0x180050759  cmp     [r14+10C8h], esi
0x180050760  jnz     short loc_180050768
0x180050762  mov     rcx, [rcx+38h]
0x180050766  jmp     short loc_18005076C
0x180050768  mov     rcx, [rcx+40h]
0x18005076c  call    MemBitIsSet
0x180050771  cmp     r15d, esi
0x180050774  jnz     loc_1800508AE
0x18005077a  cmp     dword ptr [r14+10D4h], 3
0x180050782  jnz     short loc_180050792
0x180050784  test    eax, eax
0x180050786  jnz     short loc_180050792
0x180050788  mov     ebx, edi
0x18005078a  mov     r14d, edi
0x18005078d  jmp     loc_1800510B7
0x180050792  cmp     r15d, esi
0x180050795  jnz     loc_1800508AE
0x18005079b  mov     eax, [r14+10D4h]
0x1800507a2  cmp     eax, 5
0x1800507a5  jz      short loc_1800507B0
0x1800507a7  cmp     eax, r13d
0x1800507aa  jnz     loc_1800508AE
0x1800507b0  mov     [rsp+148h+var_D0], edi
0x1800507b4  mov     [rsp+148h+var_CC], edi
0x1800507b8  mov     [rsp+148h+var_C8], edi
0x1800507bf  mov     [rsp+148h+pcbActual], r13d
0x1800507c4  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x1800507c9  lea     rdx, [rsp+148h+var_D0]; pvData
0x1800507ce  mov     rcx, cs:DhcpGlobalClientTable
0x1800507d5  mov     ecx, [rcx+0E8h]; columnid
0x1800507db  call    DhcpJetGetValue
0x1800507e0  mov     ebx, eax
0x1800507e2  test    eax, eax
0x1800507e4  jnz     short loc_18005078A
0x1800507e6  mov     [rsp+148h+pcbActual], r13d
0x1800507eb  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x1800507f0  lea     rdx, [rsp+148h+var_CC]; pvData
0x1800507f5  mov     rcx, cs:DhcpGlobalClientTable
0x1800507fc  mov     ecx, [rcx+0D8h]; columnid
0x180050802  call    DhcpJetGetValue
0x180050807  mov     ebx, eax
0x180050809  test    eax, eax
0x18005080b  jnz     loc_18005078A
0x180050811  mov     [rsp+148h+pcbActual], r13d
0x180050816  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x18005081b  lea     rdx, [rsp+148h+var_C8]; pvData
0x180050823  mov     rcx, cs:DhcpGlobalClientTable
0x18005082a  mov     ecx, [rcx+0F8h]; columnid
0x180050830  call    DhcpJetGetValue
0x180050835  mov     ebx, eax
0x180050837  test    eax, eax
0x180050839  jnz     loc_18005078A
0x18005083f  lea     rcx, [rsp+148h+FileTime1]
0x180050847  call    DhcpCalculateUTCTime
0x18005084c  mov     ebx, eax
0x18005084e  cmp     eax, [rsp+148h+var_D0]
0x180050852  cmovb   ebx, [rsp+148h+var_D0]
0x180050857  cmp     ebx, [rsp+148h+var_CC]
0x18005085b  cmovb   ebx, [rsp+148h+var_CC]
0x180050860  cmp     ebx, [rsp+148h+var_C8]
0x180050867  cmovb   ebx, [rsp+148h+var_C8]
0x18005086f  xor     ecx, ecx; Time
0x180050871  call    cs:__imp_time
0x180050878  nop     dword ptr [rax+rax+00h]
0x18005087d  cmp     ebx, eax
0x18005087f  jnb     short loc_18005088C
0x180050881  sub     eax, ebx
0x180050883  mov     ecx, eax
0x180050885  call    DhcpCalculatePastTime
0x18005088a  jmp     short loc_180050895
0x18005088c  sub     ebx, eax
0x18005088e  mov     ecx, ebx
0x180050890  call    DhcpCalculateTime
0x180050895  mov     ecx, [r14+10D0h]
0x18005089c  imul    rdx, rcx, 989680h
0x1800508a3  add     rdx, rax
0x1800508a6  mov     qword ptr [rsp+148h+FileTime1.dwLowDateTime], rdx
0x1800508ae  mov     ebx, edi
0x1800508b0  cmp     cs:DhcpGlobalUseNoDns, edi
0x1800508b6  jnz     loc_180050A21
0x1800508bc  mov     [rsp+148h+pcbActual], esi
0x1800508c0  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x1800508c5  lea     rdx, [rsp+148h+var_108]; pvData
0x1800508ca  mov     rcx, cs:DhcpGlobalClientTable
0x1800508d1  mov     ecx, [rcx+28h]; columnid
0x1800508d4  call    DhcpJetGetValue
0x1800508d9  mov     ebx, eax
0x1800508db  test    eax, eax
0x1800508dd  jz      short loc_180050903
0x1800508df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508e6  cmp     rcx, r12
0x1800508e9  jz      loc_180050A21
0x1800508ef  test    byte ptr [rcx+1Ch], 10h
0x1800508f3  jz      loc_180050A21
0x1800508f9  mov     edx, 11h
0x1800508fe  jmp     loc_180050A0E
0x180050903  call    DhcpJetBeginTransaction
0x180050908  mov     ebx, eax
0x18005090a  test    eax, eax
0x18005090c  jnz     loc_180050A21
0x180050912  mov     al, [rsp+148h+var_108]
  ... truncated ...
```
