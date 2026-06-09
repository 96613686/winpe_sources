# CleanupIpDatabase

- ea: `0x180050708`
- end: `0x18005165b`
- name: `CleanupIpDatabase`
- size: `3923`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180050260`

## callees

- `0x180002854`
- `0x18000323c`
- `0x180003c9c`
- `0x1800057f4`
- `0x180006250`
- `0x18000c180`
- `0x18000d97c`
- `0x18000eaf4`
- `0x18000eb24`
- `0x18000eb58`
- `0x18000eb9c`
- `0x18000ebd4`
- `0x18000ed48`
- `0x18000ee78`
- `0x18000f0c4`
- `0x18000f0f8`
- `0x18000f144`
- `0x18001ceb4`
- `0x180020bb4`
- `0x180021734`
- `0x180025b98`
- `0x180031918`
- `0x180031e80`
- `0x180031ed0`
- `0x180050708`
- `0x1800519fc`
- `0x18005ed00`
- `0x18008ed88`
- `0x18008ee18`
- `0x18008eea8`
- `0x18008f3f0`
- `0x180092f64`
- `0x1800930bc`
- `0x1800945a0`
- `0x18009877c`
- `0x18009f738`
- `0x18009fc30`
- `0x18009fea4`
- `0x18009fee0`
- `0x1800cc9e0`
- `0x1800cd010`

## import_xrefs

- `msvcrt!time` at `0x1800507ef`
- `msvcrt!time` at `0x180050b9a`
- `msvcrt!time` at `0x18005157c`
- `msvcrt!time` at `0x1800507ef`
- `msvcrt!time` at `0x180050b9a`
- `msvcrt!time` at `0x18005157c`
- `ESENT!JetSetCurrentIndex` at `0x1800508dd`
- `ESENT!JetSetCurrentIndex` at `0x1800508dd`
- `ESENT!JetMakeKey` at `0x180050919`
- `ESENT!JetMakeKey` at `0x180050919`
- `ESENT!JetSeek` at `0x18005094d`
- `ESENT!JetSeek` at `0x18005094d`
- `ESENT!JetPrepareUpdate` at `0x180050e9e`
- `ESENT!JetPrepareUpdate` at `0x1800511c7`
- `ESENT!JetPrepareUpdate` at `0x180050e9e`
- `ESENT!JetPrepareUpdate` at `0x1800511c7`
- `KERNEL32!LocalFree` at `0x1800510a9`
- `KERNEL32!LocalFree` at `0x1800510a9`
- `KERNEL32!CompareFileTime` at `0x180050dd2`
- `KERNEL32!CompareFileTime` at `0x180050e1b`
- `KERNEL32!CompareFileTime` at `0x180050dd2`
- `KERNEL32!CompareFileTime` at `0x180050e1b`
- `KERNEL32!EnterCriticalSection` at `0x180050810`
- `KERNEL32!EnterCriticalSection` at `0x1800508b5`
- `KERNEL32!EnterCriticalSection` at `0x180050810`
- `KERNEL32!EnterCriticalSection` at `0x1800508b5`
- `KERNEL32!LeaveCriticalSection` at `0x180051557`
- `KERNEL32!LeaveCriticalSection` at `0x180051624`
- `KERNEL32!LeaveCriticalSection` at `0x180051557`
- `KERNEL32!LeaveCriticalSection` at `0x180051624`
- `KERNEL32!HeapFree` at `0x1800513a4`
- `KERNEL32!HeapFree` at `0x1800513f6`
- `KERNEL32!HeapFree` at `0x180051602`
- `KERNEL32!HeapFree` at `0x1800513a4`
- `KERNEL32!HeapFree` at `0x1800513f6`
- `KERNEL32!HeapFree` at `0x180051602`

## string_xrefs

- `0x180050cee`: `DhcpJetRollBack`
- `0x180051250`: `DhcpJetCommitTransaction`
- `0x180050eaa`: `Cleanup:PrepareUpdate`
- `0x1800511d3`: `Cleanup:PrepareUpdate`

## pseudocode

```c
__int64 __fastcall CleanupIpDatabase(FILETIME *a1, FILETIME *a2, int a3, _DWORD *a4, _DWORD *a5)
{
  int v6; // r15d
  unsigned int v7; // r14d
  int v8; // edi
  void *v9; // rcx
  __int64 v10; // r8
  int v11; // r14d
  unsigned int v12; // eax
  unsigned int Key; // eax
  unsigned int v14; // eax
  unsigned int Value; // edi
  unsigned int v16; // eax
  _DWORD *v17; // r14
  int v18; // r15d
  int v19; // edx
  __int64 v20; // rcx
  int IsSet; // eax
  unsigned int v22; // edi
  unsigned int v23; // eax
  __int64 v24; // rax
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  int v28; // r15d
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  int String; // eax
  unsigned int v33; // eax
  __int64 v34; // r9
  const char *v35; // r8
  int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  __int64 v39; // rdx
  unsigned int v40; // eax
  unsigned int v41; // eax
  int v42; // eax
  __int64 v43; // rax
  u_long v44; // r14d
  int v45; // r12d
  int v46; // r15d
  int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // r8
  int v52; // eax
  int v53; // ecx
  int v54; // ecx
  unsigned int v55; // eax
  char *v56; // rdx
  int v57; // eax
  int Record; // eax
  __int64 v60; // [rsp+40h] [rbp-108h] BYREF
  int v61; // [rsp+48h] [rbp-100h]
  __int64 hostlong; // [rsp+4Ch] [rbp-FCh] BYREF
  __int64 v63; // [rsp+54h] [rbp-F4h] BYREF
  int pvData; // [rsp+5Ch] [rbp-ECh] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v66; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v67; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v68; // [rsp+78h] [rbp-D0h] BYREF
  unsigned int v69; // [rsp+80h] [rbp-C8h] BYREF
  unsigned int v70; // [rsp+88h] [rbp-C0h] BYREF
  unsigned int Size; // [rsp+8Ch] [rbp-BCh] BYREF
  unsigned int Size_4; // [rsp+90h] [rbp-B8h]
  FILETIME FileTime1; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-A8h] BYREF
  _DWORD *v75; // [rsp+A8h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-98h] BYREF
  _DWORD *v77; // [rsp+B8h] [rbp-90h]
  FILETIME *lpFileTime2; // [rsp+C0h] [rbp-88h]
  FILETIME *v79; // [rsp+C8h] [rbp-80h]
  unsigned __int64 v80; // [rsp+D0h] [rbp-78h]
  FILETIME *v81; // [rsp+D8h] [rbp-70h]
  FILETIME *v82; // [rsp+E0h] [rbp-68h]
  __int64 p_hostlong; // [rsp+E8h] [rbp-60h] BYREF
  int v84; // [rsp+F0h] [rbp-58h]
  int v85; // [rsp+F4h] [rbp-54h]
  int *v86; // [rsp+F8h] [rbp-50h]
  __int64 v87; // [rsp+100h] [rbp-48h]

  v6 = a3;
  v79 = a2;
  lpFileTime2 = a1;
  v81 = a1;
  v82 = a2;
  v77 = a5;
  FileTime1 = 0;
  lpMem = 0;
  HIDWORD(v63) = 0;
  hostlong = 0;
  pvData = 0;
  LOBYTE(v60) = 0;
  Size_4 = 0;
  v75 = 0;
  v74 = 0;
  LODWORD(v66) = 0;
  v70 = 0;
  v7 = 0;
  HIDWORD(v60) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids);
  *a4 = 0;
  *a5 = 0;
  HIDWORD(v68) = 50;
  v80 = time(0) + 180000;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v8 = 1;
  HIDWORD(v66) = 1;
  if ( !(unsigned int)DhcpJetPrepareSearch(*(_QWORD *)DhcpGlobalClientTable, 1, 0, 0) )
  {
    HIDWORD(hostlong) = 4;
    if ( !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &pvData, (unsigned int *)&hostlong + 1) )
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
        LODWORD(v66) = 0;
        v11 = 0;
        v61 = 0;
        if ( DhcpGlobalServiceStopping )
          goto LABEL_193;
        if ( !v8 )
        {
          EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
          HIDWORD(v66) = 1;
        }
        v12 = JetSetCurrentIndex(
                DhcpGlobalJetServerSession,
                DhcpGlobalClientTableHandle,
                *(_QWORD *)DhcpGlobalClientTable);
        if ( (unsigned int)DhcpMapJetError(v12, "Cleanup:SetCurrentIndex") )
          goto LABEL_193;
        Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, &pvData, 4u, 1u);
        if ( (unsigned int)DhcpMapJetError(Key, "Cleanup:MakeKey") )
          goto LABEL_193;
        v14 = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 8u);
        if ( (unsigned int)DhcpMapJetError(v14, "Cleanup:Seek") )
          goto LABEL_193;
        HIDWORD(hostlong) = 4;
        Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &hostlong, (unsigned int *)&hostlong + 1);
        if ( Value )
          goto LABEL_169;
        if ( !v6 )
          DhcpGlobalScavengeStartAddress = hostlong;
        if ( (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, (unsigned int)hostlong) )
        {
          Value = 0;
          goto LABEL_169;
        }
        HIDWORD(hostlong) = 8;
        Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &FileTime1, (unsigned int *)&hostlong + 1);
        if ( Value )
          goto LABEL_169;
        v16 = (hostlong & 0xF0000000) == 0xE0000000
            ? MemServerGetMAddressInfo(
                (_DWORD)DhcpGlobalThisServer,
                hostlong,
                (unsigned int)&v75,
                (unsigned int)&v74,
                0,
                0)
            : MemServerGetUAddressInfo(
                (_DWORD)DhcpGlobalThisServer,
                hostlong,
                (unsigned int)&v75,
                (unsigned int)&v74,
                0,
                0);
        Value = v16;
        if ( v16 || !v74 )
          goto LABEL_169;
        v17 = v75;
        if ( !v75 )
          goto LABEL_128;
        v18 = v75[1073];
        if ( v18 == 1 )
        {
          v19 = v75[1077];
          if ( ((v19 - 3) & 0xFFFFFFFD) != 0 && (!*(_DWORD *)&gFailoverEnableCommInt || v19 != 4) )
            goto LABEL_39;
        }
        if ( v18 == 1 )
        {
          if ( v75[1074] == 1 )
            v20 = *(_QWORD *)(v74 + 56);
          else
            v20 = *(_QWORD *)(v74 + 64);
          IsSet = MemBitIsSet(v20, (unsigned int)(hostlong - *(_DWORD *)v74));
          if ( v17[1077] == 3 && !IsSet )
          {
            Value = 0;
LABEL_39:
            v11 = 0;
            goto LABEL_168;
          }
          if ( (unsigned int)(v17[1077] - 4) <= 1 )
          {
            v67 = 0;
            LODWORD(v68) = 0;
            HIDWORD(hostlong) = 4;
            Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 232), &v67, (unsigned int *)&hostlong + 1);
            if ( Value )
              goto LABEL_39;
            HIDWORD(hostlong) = 4;
            Value = DhcpJetGetValue(
                      *(_DWORD *)(DhcpGlobalClientTable + 216),
                      (__int64 *)((char *)&v67 + 4),
                      (unsigned int *)&hostlong + 1);
            if ( Value )
              goto LABEL_39;
            HIDWORD(hostlong) = 4;
            Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 248), &v68, (unsigned int *)&hostlong + 1);
            if ( Value )
              goto LABEL_39;
            v22 = DhcpCalculateUTCTime(&FileTime1);
            if ( v22 < (unsigned int)v67 )
              v22 = v67;
            if ( v22 < HIDWORD(v67) )
              v22 = HIDWORD(v67);
            if ( v22 < (unsigned int)v68 )
              v22 = v68;
            v23 = time(0);
            if ( v22 >= v23 )
              v24 = DhcpCalculateTime(v22 - v23);
            else
              v24 = DhcpCalculatePastTime(v23 - v22);
            FileTime1 = (FILETIME)(v24 + 10000000LL * (unsigned int)v17[1076]);
          }
        }
        Value = 0;
        if ( !DhcpGlobalUseNoDns )
        {
          HIDWORD(hostlong) = 1;
          v25 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &v60, (unsigned int *)&hostlong + 1);
          Value = v25;
          if ( v25 )
          {
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_83;
            }
            v27 = 17;
          }
          else
          {
            Value = DhcpJetBeginTransaction();
            if ( Value )
              goto LABEL_83;
            if ( (v60 & 0x80u) == 0LL )
            {
              if ( (v60 & 0x40) != 0 )
                DhcpDoDynDnsRefresh((struct in_addr)hostlong);
            }
            else if ( (unsigned int)DhcpDoDynDnsCheckDelete((struct in_addr)hostlong) )
            {
              v28 = 0;
              if ( v17[1073] != 1 )
              {
                v29 = DhcpJetDeleteCurrentRecord();
                goto LABEL_66;
              }
              v29 = DhcpHandleFailoverRequest(v17, (unsigned int)hostlong, 1, 0);
              if ( v29 )
                goto LABEL_72;
              v28 = 1;
              ++HIDWORD(v60);
LABEL_66:
              if ( v29 )
              {
LABEL_72:
                v33 = DhcpJetRollBack();
                Value = v33;
                v11 = 1;
                if ( v33 )
                {
                  v34 = 733;
                  goto LABEL_74;
                }
              }
              else
              {
                Value = DhcpJetCommitTransaction();
                if ( v17[1073] != 1 || v28 == 1 )
                  ++*v77;
                v11 = 0;
              }
              String = GetString(1083, v30, v31);
              DhcpUpdateAuditLog(16, String, hostlong, 0, 0, 0);
              goto LABEL_168;
            }
            v25 = DhcpJetCommitTransaction();
            Value = v25;
            if ( !v25 )
              goto LABEL_83;
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_83;
            }
            v27 = 18;
          }
          WPP_SF_D(v26[2], v27, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v25);
        }
LABEL_83:
        if ( v17[1073] == 1 )
        {
          v36 = v17[1077];
          if ( v36 == 5 || v36 == 4 && *(_DWORD *)&gFailoverEnableCommInt )
          {
            v70 = 4;
            v37 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 312), &v66, &v70);
            Value = v37;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v37);
            }
          }
        }
        if ( CompareFileTime(&FileTime1, lpFileTime2) >= 0 && (v17[1073] != 1 || (v66 & 0x10) == 0) )
          goto LABEL_39;
        v6 = a3;
        if ( a3 || CompareFileTime(&FileTime1, v79) < 0 || v17[1073] == 1 && (v66 & 0x10) != 0 )
        {
          LOBYTE(v63) = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v43 = DhcpIpAddressToDottedString((unsigned int)hostlong);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v43);
          }
          HIDWORD(hostlong) = 1;
          if ( (unsigned int)DhcpJetGetValue(
                               *(_DWORD *)(DhcpGlobalClientTable + 152),
                               &v63,
                               (unsigned int *)&hostlong + 1) )
            LOBYTE(v63) = 1;
          if ( (_BYTE)v63 == 2 )
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
            goto LABEL_128;
          }
          if ( v17[1073] != 1 )
          {
            Value = DhcpReleaseAddress((unsigned int)hostlong);
            if ( Value )
            {
              DhcpReleaseBootpAddress((unsigned int)hostlong);
              Value = 0;
            }
            goto LABEL_132;
          }
          HIDWORD(hostlong) = 1;
          v48 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &v60, (unsigned int *)&hostlong + 1);
          Value = v48;
          if ( v48 )
          {
            DhcpPrintFOErrorEx(v48, "CleanupIpDatabase", "DhcpJetGetValue", 844);
LABEL_128:
            v11 = 0;
            goto LABEL_169;
          }
          if ( (unsigned int)(v60 & 3) - 2 <= 1 )
            goto LABEL_132;
          v33 = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
          if ( v33 )
          {
            v34 = 852;
            v35 = "DhcpDALJetBeginTransaction";
            goto LABEL_75;
          }
          v49 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 2u);
          if ( !(unsigned int)DhcpDALMapJetError(v49, "Cleanup:PrepareUpdate") )
          {
            LOBYTE(v60) = v60 | 3;
            if ( !(unsigned int)DhcpDALJetSetValue(
                                  DhcpGlobalJetServerSession,
                                  DhcpGlobalClientTableHandle,
                                  *(_DWORD *)(DhcpGlobalClientTable + 40),
                                  (unsigned int)&v60,
                                  1u)
              && !(unsigned int)DhcpJetCommitUpdate() )
            {
              v33 = DhcpJetCommitTransaction();
              Value = v33;
              if ( v33 )
              {
                v34 = 883;
                v35 = "DhcpJetCommitTransaction";
                goto LABEL_75;
              }
LABEL_132:
              HIDWORD(v63) = 0;
              lpMem = 0;
              if ( (unsigned int)DhcpJetGetValue(
                                   *(_DWORD *)(DhcpGlobalClientTable + 24),
                                   &lpMem,
                                   (unsigned int *)&v63 + 1) )
                goto LABEL_128;
              if ( (unsigned int)DhcpJetBeginTransaction() )
                goto LABEL_193;
              v45 = DhcpDoDynDnsCheckDelete((struct in_addr)hostlong);
              v46 = 0;
              if ( v17[1073] != 1 )
              {
                v47 = DhcpJetDeleteCurrentRecord();
                goto LABEL_150;
              }
              v47 = DhcpHandleFailoverRequest(v17, (unsigned int)hostlong, 1, 0);
              if ( v47 )
                goto LABEL_166;
              ++HIDWORD(v60);
              v46 = 1;
LABEL_150:
              if ( v47 )
              {
LABEL_166:
                v33 = DhcpJetRollBack();
                Value = v33;
                v11 = 1;
                if ( v33 )
                {
                  v34 = 936;
LABEL_74:
                  v35 = "DhcpJetRollBack";
LABEL_75:
                  DhcpPrintFOErrorEx(v33, "CleanupIpDatabase", v35, v34);
LABEL_193:
                  v7 = HIDWORD(v60);
                  break;
                }
              }
              else
              {
                Value = DhcpJetCommitTransaction();
                v69 = Value;
                if ( v17[1073] != 1 || v46 == 1 )
                  ++*v77;
                if ( v45 )
                {
                  v52 = GetString(1083, v50, v51);
                  v53 = 16;
                }
                else
                {
                  v52 = GetString(1084, v50, v51);
                  v53 = 17;
                }
                DhcpUpdateAuditLog(v53, v52, hostlong, 0, 0, 0);
                v54 = hostlong & DhcpGetSubnetMaskForAddress((unsigned int)hostlong);
                v55 = HIDWORD(v63);
                if ( HIDWORD(v63) > 4 && v54 == *(_DWORD *)lpMem )
                {
                  v56 = (char *)lpMem + 4;
                  v55 = HIDWORD(v63) - 4;
                  HIDWORD(v63) -= 4;
                }
                else
                {
                  v56 = (char *)lpMem;
                }
                if ( qword_180155858 )
                  ((void (__fastcall *)(_QWORD, char *, _QWORD, _QWORD, _DWORD))qword_180155858)(
                    (unsigned int)hostlong,
                    v56,
                    v55,
                    0,
                    0);
                v11 = v61;
                if ( lpMem )
                  HeapFree(gDhcpHeap, 0, lpMem);
                lpMem = 0;
                HIDWORD(v63) = 0;
              }
LABEL_168:
              v6 = a3;
              goto LABEL_169;
            }
          }
          v33 = DhcpJetRollBack();
          Value = v33;
          v11 = 1;
          if ( v33 )
          {
            v34 = 879;
            goto LABEL_74;
          }
        }
        else
        {
          HIDWORD(hostlong) = 1;
          Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &v60, (unsigned int *)&hostlong + 1);
          if ( Value || (unsigned int)(v60 & 3) - 2 <= 1 )
            goto LABEL_128;
          if ( (unsigned int)DhcpJetBeginTransaction() )
            goto LABEL_193;
          v38 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, Value + 2);
          if ( !(unsigned int)DhcpMapJetError(v38, "Cleanup:PrepareUpdate") )
          {
            LOBYTE(v60) = v60 | 3;
            if ( !(unsigned int)DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &v60, 1u)
              && !(unsigned int)DhcpJetCommitUpdate() )
            {
              Value = DhcpJetCommitTransaction();
              if ( Value )
                goto LABEL_193;
              if ( v17[1073] != 1 )
                goto LABEL_117;
              Value = DhcpJetBeginTransaction();
              if ( !Value )
              {
                v40 = DhcpHandleFailoverRequest(v17, (unsigned int)hostlong, 0, 0);
                Value = v40;
                if ( v40 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      21,
                      &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                      v40);
                  }
                  Value = DhcpJetRollBack();
                  v11 = 1;
                  if ( Value )
                    goto LABEL_193;
                }
                else
                {
                  v41 = DhcpJetCommitTransaction();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      22,
                      &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                      v41);
                  }
LABEL_117:
                  v11 = 0;
                }
                v42 = GetString(1085, v39, v10);
                DhcpUpdateAuditLog(18, v42, hostlong, 0, 0, 0);
                goto LABEL_169;
              }
              goto LABEL_128;
            }
          }
          Value = DhcpJetRollBack();
          v11 = 1;
          if ( Value )
            goto LABEL_193;
        }
LABEL_169:
        if ( lpMem )
        {
          HeapFree(gDhcpHeap, 0, lpMem);
          lpMem = 0;
          HIDWORD(v63) = 0;
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
          v84 = 4;
          v85 = 1;
          v57 = DhcpDALJetPrepareSearchEx(
                  DhcpGlobalJetServerSession,
                  DhcpGlobalClientTableHandle,
                  (__int64)&p_hostlong,
                  1,
                  8u);
          if ( v57 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_dD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids,
                (unsigned int)hostlong,
                v57);
            }
            goto LABEL_193;
          }
        }
        Record = DhcpJetNextRecord();
        if ( Record == 259 )
        {
          v7 = HIDWORD(v60);
          if ( !v6 )
            DhcpGlobalScavengeStartAddress = 0;
          break;
        }
        if ( !Record )
        {
          HIDWORD(hostlong) = 4;
          if ( !(unsigned int)DhcpJetGetValue(
                                *(_DWORD *)(DhcpGlobalClientTable + 8),
                                &pvData,
                                (unsigned int *)&hostlong + 1) )
          {
            if ( !v6 )
              DhcpGlobalScavengeStartAddress = pvData;
            v8 = HIDWORD(v66);
            if ( !HIDWORD(v66) )
              continue;
            if ( !--HIDWORD(v68) )
            {
              LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
              v8 = 0;
              HIDWORD(v66) = 0;
              HIDWORD(v68) = 50;
            }
            if ( v6 || time(0) < v80 )
              continue;
          }
        }
        goto LABEL_193;
      }
    }
  }
  if ( *(_DWORD *)&isDhcpFailoverTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
  {
    v69 = v7;
    v86 = (int *)&v69;
    v87 = 4;
    McGenEventWrite_EventWriteTransfer(v9, &TotalLeasesDeleted, v10, 2, &p_hostlong);
  }
  if ( lpMem )
  {
    HeapFree(gDhcpHeap, 0, lpMem);
    lpMem = 0;
    HIDWORD(v63) = 0;
  }
  if ( HIDWORD(v66) )
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return Size_4;
}

```

## disassembly

```asm
0x180050708  mov     r11, rsp
0x18005070b  mov     [r11+18h], r8d
0x18005070f  push    rbx
0x180050710  push    rsi
0x180050711  push    rdi
0x180050712  push    r12
0x180050714  push    r13
0x180050716  push    r14
0x180050718  push    r15
0x18005071a  sub     rsp, 110h
0x180050721  mov     rax, cs:__security_cookie
0x180050728  xor     rax, rsp
0x18005072b  mov     [rsp+148h+var_40], rax
0x180050733  mov     rdi, r9
0x180050736  mov     r15d, r8d
0x180050739  mov     [rsp+148h+var_80], rdx
0x180050741  mov     [rsp+148h+lpFileTime2], rcx
0x180050749  mov     [rsp+148h+var_70], rcx
0x180050751  mov     [rsp+148h+var_68], rdx
0x180050759  mov     rsi, [rsp+148h+arg_20]
0x180050761  mov     [rsp+148h+var_90], rsi
0x180050769  xor     ebx, ebx
0x18005076b  mov     [r11-0B0h], rbx
0x180050772  mov     [rsp+148h+pcbActual], ebx
0x180050776  mov     [rsp+148h+lpMem], rbx
0x18005077b  mov     [rsp+148h+var_F0], ebx
0x18005077f  mov     [rsp+148h+hostlong], ebx
0x180050783  mov     [rsp+148h+pvData], ebx
0x180050787  mov     [rsp+148h+var_108], bl
0x18005078b  mov     dword ptr [rsp+148h+Size+4], ebx
0x180050792  mov     [r11-0A0h], rbx
0x180050799  mov     [r11-0A8h], rbx
0x1800507a0  mov     [rsp+148h+var_E0], ebx
0x1800507a4  mov     [rsp+148h+var_C0], ebx
0x1800507ab  mov     r14d, ebx
0x1800507ae  mov     [rsp+148h+var_104], ebx
0x1800507b2  lea     r12, WPP_GLOBAL_Control
0x1800507b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800507c0  cmp     rcx, r12
0x1800507c3  jz      short loc_1800507E1
0x1800507c5  test    dword ptr [rcx+1Ch], 8000h
0x1800507cc  jz      short loc_1800507E1
0x1800507ce  lea     edx, [rbx+10h]
0x1800507d1  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x1800507d8  mov     rcx, [rcx+10h]
0x1800507dc  call    WPP_SF_
0x1800507e1  mov     [rdi], ebx
0x1800507e3  mov     [rsi], ebx
0x1800507e5  mov     [rsp+148h+var_CC], 32h ; '2'
0x1800507ed  xor     ecx, ecx; Time
0x1800507ef  call    cs:__imp_time
0x1800507f6  nop     dword ptr [rax+rax+00h]
0x1800507fb  add     rax, 2BF20h
0x180050801  mov     [rsp+148h+var_78], rax
0x180050809  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180050810  call    cs:__imp_EnterCriticalSection
0x180050817  nop     dword ptr [rax+rax+00h]
0x18005081c  mov     esi, 1
0x180050821  mov     edi, esi
0x180050823  mov     [rsp+148h+var_DC], esi
0x180050827  xor     r9d, r9d
0x18005082a  xor     r8d, r8d
0x18005082d  mov     edx, esi
0x18005082f  mov     rcx, cs:DhcpGlobalClientTable
0x180050836  mov     rcx, [rcx]
0x180050839  call    DhcpJetPrepareSearch
0x18005083e  test    eax, eax
0x180050840  jnz     loc_18005159B
0x180050846  lea     r13d, [rsi+3]
0x18005084a  mov     [rsp+148h+pcbActual], r13d
0x18005084f  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050854  lea     rdx, [rsp+148h+pvData]; pvData
0x180050859  mov     rcx, cs:DhcpGlobalClientTable
0x180050860  mov     ecx, [rcx+8]; columnid
0x180050863  call    DhcpJetGetValue
0x180050868  test    eax, eax
0x18005086a  jnz     loc_18005159B
0x180050870  test    r15d, r15d
0x180050873  jz      short loc_18005087D
0x180050875  mov     cs:DhcpGlobalScavengeStartAddress, ebx
0x18005087b  jmp     short loc_180050893
0x18005087d  mov     eax, cs:DhcpGlobalScavengeStartAddress
0x180050883  test    eax, eax
0x180050885  jz      short loc_180050893
0x180050887  mov     [rsp+148h+pvData], eax
0x18005088b  add     eax, esi
0x18005088d  mov     cs:DhcpGlobalScavengeStartAddress, eax
0x180050893  mov     [rsp+148h+var_E0], ebx
0x180050897  mov     r14d, ebx
0x18005089a  mov     [rsp+148h+var_100], ebx
0x18005089e  cmp     cs:DhcpGlobalServiceStopping, ebx
0x1800508a4  jnz     loc_180051596
0x1800508aa  test    edi, edi
0x1800508ac  jnz     short loc_1800508C5
0x1800508ae  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800508b5  call    cs:__imp_EnterCriticalSection
0x1800508bc  nop     dword ptr [rax+rax+00h]
0x1800508c1  mov     [rsp+148h+var_DC], esi
0x1800508c5  mov     r8, cs:DhcpGlobalClientTable
0x1800508cc  mov     r8, [r8]
0x1800508cf  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800508d6  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800508dd  call    cs:__imp_JetSetCurrentIndex
0x1800508e4  nop     dword ptr [rax+rax+00h]
0x1800508e9  lea     rdx, aCleanupSetcurr; "Cleanup:SetCurrentIndex"
0x1800508f0  mov     ecx, eax
0x1800508f2  call    DhcpMapJetError
0x1800508f7  test    eax, eax
0x1800508f9  jnz     loc_180051596
0x1800508ff  mov     [rsp+148h+grbit], esi; grbit
0x180050903  mov     r9d, r13d; cbData
0x180050906  lea     r8, [rsp+148h+pvData]; pvData
0x18005090b  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180050912  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180050919  call    cs:__imp_JetMakeKey
0x180050920  nop     dword ptr [rax+rax+00h]
0x180050925  lea     rdx, aCleanupMakekey; "Cleanup:MakeKey"
0x18005092c  mov     ecx, eax
0x18005092e  call    DhcpMapJetError
0x180050933  test    eax, eax
0x180050935  jnz     loc_180051596
0x18005093b  lea     r8d, [rax+8]; grbit
0x18005093f  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180050946  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18005094d  call    cs:__imp_JetSeek
0x180050954  nop     dword ptr [rax+rax+00h]
0x180050959  lea     rdx, aCleanupSeek; "Cleanup:Seek"
0x180050960  mov     ecx, eax
0x180050962  call    DhcpMapJetError
0x180050967  test    eax, eax
0x180050969  jnz     loc_180051596
0x18005096f  mov     [rsp+148h+pcbActual], r13d
0x180050974  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050979  lea     rdx, [rsp+148h+hostlong]; pvData
0x18005097e  mov     rcx, cs:DhcpGlobalClientTable
0x180050985  mov     ecx, [rcx+8]; columnid
0x180050988  call    DhcpJetGetValue
0x18005098d  mov     edi, eax
0x18005098f  test    eax, eax
0x180050991  jnz     loc_1800513E3
0x180050997  test    r15d, r15d
0x18005099a  jnz     short loc_1800509A6
0x18005099c  mov     eax, [rsp+148h+hostlong]
0x1800509a0  mov     cs:DhcpGlobalScavengeStartAddress, eax
0x1800509a6  mov     edx, [rsp+148h+hostlong]
0x1800509aa  mov     rcx, cs:DhcpGlobalThisServer
0x1800509b1  call    MemServerIsReservedAddress
0x1800509b6  test    eax, eax
0x1800509b8  jz      short loc_1800509C1
0x1800509ba  mov     edi, ebx
0x1800509bc  jmp     loc_1800513E3
0x1800509c1  mov     [rsp+148h+pcbActual], 8
0x1800509c9  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x1800509ce  lea     rdx, [rsp+148h+FileTime1]; pvData
0x1800509d6  mov     rcx, cs:DhcpGlobalClientTable
0x1800509dd  mov     ecx, [rcx+58h]; columnid
0x1800509e0  call    DhcpJetGetValue
0x1800509e5  mov     edi, eax
0x1800509e7  test    eax, eax
0x1800509e9  jnz     loc_1800513E3
0x1800509ef  mov     rcx, cs:DhcpGlobalThisServer
0x1800509f6  mov     edx, [rsp+148h+hostlong]
0x1800509fa  mov     eax, edx
0x1800509fc  and     eax, 0F0000000h
0x180050a01  mov     qword ptr [rsp+148h+var_120], rbx
0x180050a06  lea     r9, [rsp+148h+var_A8]
0x180050a0e  lea     r8, [rsp+148h+var_A0]
0x180050a16  mov     qword ptr [rsp+148h+grbit], rbx
0x180050a1b  cmp     eax, 0E0000000h
0x180050a20  jnz     short loc_180050A29
0x180050a22  call    MemServerGetMAddressInfo
0x180050a27  jmp     short loc_180050A2E
0x180050a29  call    MemServerGetUAddressInfo
0x180050a2e  mov     edi, eax
0x180050a30  test    eax, eax
0x180050a32  jnz     loc_1800513E3
0x180050a38  mov     rcx, [rsp+148h+var_A8]
0x180050a40  test    rcx, rcx
0x180050a43  jz      loc_1800513E3
0x180050a49  mov     r14, [rsp+148h+var_A0]
0x180050a51  test    r14, r14
0x180050a54  jz      loc_1800510B5
0x180050a5a  mov     r15d, [r14+10C4h]
0x180050a61  cmp     r15d, esi
0x180050a64  jnz     short loc_180050A84
0x180050a66  mov     edx, [r14+10D4h]
0x180050a6d  lea     eax, [rdx-3]
0x180050a70  test    eax, 0FFFFFFFDh
0x180050a75  jz      short loc_180050A84
0x180050a77  cmp     cs:gFailoverEnableCommInt, ebx
0x180050a7d  jz      short loc_180050AC6
0x180050a7f  cmp     edx, r13d
0x180050a82  jnz     short loc_180050AC6
0x180050a84  mov     eax, ebx
0x180050a86  cmp     r15d, esi
0x180050a89  jnz     loc_180050BD7
0x180050a8f  mov     edx, [rsp+148h+hostlong]
0x180050a93  sub     edx, [rcx]
0x180050a95  cmp     [r14+10C8h], esi
0x180050a9c  jnz     short loc_180050AA4
0x180050a9e  mov     rcx, [rcx+38h]
0x180050aa2  jmp     short loc_180050AA8
0x180050aa4  mov     rcx, [rcx+40h]
0x180050aa8  call    MemBitIsSet
0x180050aad  cmp     r15d, esi
0x180050ab0  jnz     loc_180050BD7
0x180050ab6  cmp     dword ptr [r14+10D4h], 3
0x180050abe  jnz     short loc_180050ACE
0x180050ac0  test    eax, eax
0x180050ac2  jnz     short loc_180050ACE
0x180050ac4  mov     edi, ebx
0x180050ac6  mov     r14d, ebx
0x180050ac9  jmp     loc_1800513DB
0x180050ace  cmp     r15d, esi
0x180050ad1  jnz     loc_180050BD7
0x180050ad7  mov     eax, [r14+10D4h]
0x180050ade  sub     eax, r13d
0x180050ae1  cmp     eax, esi
0x180050ae3  ja      loc_180050BD7
0x180050ae9  mov     [rsp+148h+var_D8], ebx
0x180050aed  mov     [rsp+148h+var_D4], ebx
0x180050af1  mov     [rsp+148h+var_D0], ebx
0x180050af5  mov     [rsp+148h+pcbActual], r13d
0x180050afa  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050aff  lea     rdx, [rsp+148h+var_D8]; pvData
0x180050b04  mov     rcx, cs:DhcpGlobalClientTable
0x180050b0b  mov     ecx, [rcx+0E8h]; columnid
0x180050b11  call    DhcpJetGetValue
0x180050b16  mov     edi, eax
0x180050b18  test    eax, eax
0x180050b1a  jnz     short loc_180050AC6
0x180050b1c  mov     [rsp+148h+pcbActual], r13d
0x180050b21  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050b26  lea     rdx, [rsp+148h+var_D4]; pvData
0x180050b2b  mov     rcx, cs:DhcpGlobalClientTable
0x180050b32  mov     ecx, [rcx+0D8h]; columnid
0x180050b38  call    DhcpJetGetValue
0x180050b3d  mov     edi, eax
0x180050b3f  test    eax, eax
0x180050b41  jnz     short loc_180050AC6
0x180050b43  mov     [rsp+148h+pcbActual], r13d
0x180050b48  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050b4d  lea     rdx, [rsp+148h+var_D0]; pvData
0x180050b52  mov     rcx, cs:DhcpGlobalClientTable
0x180050b59  mov     ecx, [rcx+0F8h]; columnid
0x180050b5f  call    DhcpJetGetValue
0x180050b64  mov     edi, eax
0x180050b66  test    eax, eax
0x180050b68  jnz     loc_180050AC6
0x180050b6e  lea     rcx, [rsp+148h+FileTime1]
0x180050b76  call    DhcpCalculateUTCTime
0x180050b7b  mov     edi, eax
0x180050b7d  cmp     eax, [rsp+148h+var_D8]
0x180050b81  cmovb   edi, [rsp+148h+var_D8]
0x180050b86  cmp     edi, [rsp+148h+var_D4]
0x180050b8a  cmovb   edi, [rsp+148h+var_D4]
0x180050b8f  cmp     edi, [rsp+148h+var_D0]
0x180050b93  cmovb   edi, [rsp+148h+var_D0]
0x180050b98  xor     ecx, ecx; Time
0x180050b9a  call    cs:__imp_time
0x180050ba1  nop     dword ptr [rax+rax+00h]
0x180050ba6  cmp     edi, eax
0x180050ba8  jnb     short loc_180050BB5
0x180050baa  sub     eax, edi
0x180050bac  mov     ecx, eax
0x180050bae  call    DhcpCalculatePastTime
0x180050bb3  jmp     short loc_180050BBE
0x180050bb5  sub     edi, eax
0x180050bb7  mov     ecx, edi
0x180050bb9  call    DhcpCalculateTime
0x180050bbe  mov     ecx, [r14+10D0h]
0x180050bc5  imul    rdx, rcx, 989680h
0x180050bcc  add     rdx, rax
0x180050bcf  mov     qword ptr [rsp+148h+FileTime1.dwLowDateTime], rdx
0x180050bd7  mov     edi, ebx
0x180050bd9  cmp     cs:DhcpGlobalUseNoDns, ebx
0x180050bdf  jnz     loc_180050D4A
0x180050be5  mov     [rsp+148h+pcbActual], esi
0x180050be9  lea     r8, [rsp+148h+pcbActual]; pcbActual
0x180050bee  lea     rdx, [rsp+148h+var_108]; pvData
0x180050bf3  mov     rcx, cs:DhcpGlobalClientTable
0x180050bfa  mov     ecx, [rcx+28h]; columnid
0x180050bfd  call    DhcpJetGetValue
0x180050c02  mov     edi, eax
0x180050c04  test    eax, eax
0x180050c06  jz      short loc_180050C2C
0x180050c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c0f  cmp     rcx, r12
0x180050c12  jz      loc_180050D4A
0x180050c18  test    byte ptr [rcx+1Ch], 10h
0x180050c1c  jz      loc_180050D4A
0x180050c22  mov     edx, 11h
0x180050c27  jmp     loc_180050D37
0x180050c2c  call    DhcpJetBeginTransaction
0x180050c31  mov     edi, eax
0x180050c33  test    eax, eax
0x180050c35  jnz     loc_180050D4A
0x180050c3b  mov     al, [rsp+148h+var_108]
0x180050c3f  test    al, al
0x180050c41  jns     loc_180050D08
  ... truncated ...
```
