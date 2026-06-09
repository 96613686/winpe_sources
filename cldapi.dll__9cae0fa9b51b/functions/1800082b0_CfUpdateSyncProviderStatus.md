# CfUpdateSyncProviderStatus

- ea: `0x1800082b0`
- end: `0x180008bcf`
- name: `CfUpdateSyncProviderStatus`
- size: `2335`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001078`
- `0x180001aa0`
- `0x18000231e`
- `0x1800082b0`
- `0x18000b5d8`
- `0x18000bb10`
- `0x18000c024`
- `0x180012054`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800083fe`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800087c8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000880b`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800083fe`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800087c8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000880b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008386`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800085ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800087fc`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008386`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800085ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800087fc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008416`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008530`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800087d7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008416`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180008530`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800087d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008489`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008561`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800087ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008489`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008561`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800087ed`
- `ntdll!RtlNtStatusToDosError` at `0x1800088eb`
- `ntdll!RtlNtStatusToDosError` at `0x180008975`
- `ntdll!RtlNtStatusToDosError` at `0x180008a00`
- `ntdll!RtlNtStatusToDosError` at `0x180008a8a`
- `ntdll!RtlNtStatusToDosError` at `0x1800088eb`
- `ntdll!RtlNtStatusToDosError` at `0x180008975`
- `ntdll!RtlNtStatusToDosError` at `0x180008a00`
- `ntdll!RtlNtStatusToDosError` at `0x180008a8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008367`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000830f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000830f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000845a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000881e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000845a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000881e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800084bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000883c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800084bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000883c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000846f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000846f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b99`
- `FLTLIB!FilterSendMessage` at `0x180008ae2`
- `FLTLIB!FilterSendMessage` at `0x180008ae2`

## string_xrefs

- `0x180008995`: `SetCldMsgCommand Failed`
- `0x180008867`: `HeapAlloc for CldCmdUpdateProviderStatus Failed`
- `0x1800084f0`: `HeapAlloc for newThreadStatus failed`

## pseudocode

```c
__int64 __fastcall CfUpdateSyncProviderStatus(__int64 a1, int a2)
{
  __int64 v2; // rbx
  unsigned int v3; // r12d
  _DWORD *v4; // rsi
  int v5; // edi
  int v6; // r13d
  const wchar_t *v7; // rcx
  int v8; // r13d
  __int64 v9; // r12
  __int64 v10; // r14
  _QWORD *v11; // rcx
  DWORD v12; // ebx
  _QWORD *v13; // r15
  DWORD *v14; // rdi
  _QWORD *v15; // rdi
  _QWORD *v16; // r13
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  _DWORD *v21; // rax
  _DWORD *v22; // r15
  _QWORD *v23; // rcx
  unsigned int v24; // r12d
  __int64 v25; // r14
  __int64 v26; // rdi
  __int64 v27; // rdx
  const WCHAR *v28; // rax
  __int64 v29; // rcx
  int v30; // ecx
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rdx
  const WCHAR *v35; // rax
  __int64 v36; // rcx
  int v37; // ecx
  const WCHAR *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  HANDLE v41; // rax
  NTSTATUS v42; // r14d
  NTSTATUS v43; // ecx
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned int v46; // ecx
  signed int v47; // eax
  NTSTATUS v48; // ecx
  __int64 v49; // rcx
  __int64 v50; // rax
  signed int v51; // eax
  NTSTATUS v52; // ecx
  __int64 v53; // rcx
  __int64 v54; // rax
  signed int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rax
  signed int v58; // eax
  HRESULT v59; // eax
  __int64 v60; // rbx
  const WCHAR *v61; // rdx
  const WCHAR *v62; // r9
  HANDLE v63; // rax
  unsigned int v65; // [rsp+40h] [rbp-C0h]
  int v67; // [rsp+48h] [rbp-B8h] BYREF
  DWORD CurrentThreadId; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A0h]
  unsigned __int64 UnbiasedTime; // [rsp+68h] [rbp-98h] BYREF
  __int64 v73; // [rsp+70h] [rbp-90h]
  _DWORD *v74; // [rsp+78h] [rbp-88h]
  int v75; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v76; // [rsp+88h] [rbp-78h]
  __int64 v77; // [rsp+90h] [rbp-70h]
  int v78; // [rsp+98h] [rbp-68h]
  unsigned int v79; // [rsp+9Ch] [rbp-64h]
  char v80; // [rsp+A0h] [rbp-60h]
  _BYTE v81[32]; // [rsp+E0h] [rbp-20h] BYREF
  const WCHAR *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v85; // [rsp+110h] [rbp+10h]
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  DWORD *p_CurrentThreadId; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  int *v90; // [rsp+130h] [rbp+30h]
  __int64 v91; // [rsp+138h] [rbp+38h]
  __int64 *v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]

  v2 = a1;
  v73 = a1;
  UnbiasedTime = 0;
  v65 = 0;
  BytesReturned = 0;
  v3 = 0;
  memset_0(&v75, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v71 = CfpReferenceSyncRoot(v2);
  if ( !v71 )
  {
    v6 = a2;
    goto LABEL_66;
  }
  v74 = 0;
  v4 = 0;
  v80 = 1;
  v5 = GlobalPortInit(0);
  if ( v5 <= -1 )
  {
    v6 = a2;
    v7 = L"GlobalPortInit Failed";
    goto LABEL_113;
  }
  v67 = 0;
  v8 = 0;
  v9 = v71 + 168;
  CurrentThreadId = GetCurrentThreadId();
  v70 = v71 + 168;
  RtlAcquireSRWLockShared(v71 + 168);
  v10 = v71 + 152;
  v11 = *(_QWORD **)(v71 + 152);
  if ( *(_QWORD *)v10 == v10 )
    goto LABEL_13;
  v12 = CurrentThreadId;
  do
  {
    v13 = (_QWORD *)*v11;
    v14 = (DWORD *)(v11 - 1);
    if ( *((_DWORD *)v11 - 2) == v12 )
    {
      v67 = 1;
      if ( a2 >= 0 )
        *((_DWORD *)v11 - 1) = a2;
      else
        v14[1] = *((_DWORD *)v11 - 1) & ~a2;
    }
    else if ( (unsigned int)CfpIsThreadTerminated(*v14) )
    {
      v8 = 1;
      goto LABEL_11;
    }
    if ( v14 )
      LODWORD(v4) = v14[1] | (unsigned int)v4;
LABEL_11:
    v11 = v13;
  }
  while ( v13 != (_QWORD *)v10 );
  v2 = v73;
  v9 = v70;
  v65 = (unsigned int)v4;
  v4 = v74;
LABEL_13:
  RtlReleaseSRWLockShared(v9);
  if ( v8 )
  {
    RtlAcquireSRWLockExclusive(v9);
    v15 = *(_QWORD **)v10;
    if ( *(_QWORD *)v10 != v10 )
    {
      do
      {
        v16 = (_QWORD *)*v15;
        if ( (unsigned int)CfpIsThreadTerminated(*((_DWORD *)v15 - 2)) )
        {
          v17 = (_QWORD *)*v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_30;
          v18 = (_QWORD *)v15[1];
          if ( (_QWORD *)*v18 != v15 )
            goto LABEL_30;
          *v18 = v17;
          v17[1] = v18;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v15 - 1);
        }
        v15 = v16;
      }
      while ( v16 != (_QWORD *)v10 );
    }
    RtlReleaseSRWLockExclusive(v9);
  }
  if ( v67 )
  {
    v24 = v65;
    v6 = a2;
  }
  else
  {
    v20 = GetProcessHeap();
    v21 = HeapAlloc(v20, 8u, 0x18u);
    v22 = v21;
    v5 = v21 == 0 ? 8 : 0;
    v6 = a2;
    if ( !v21 )
      v5 |= 0x80070000;
    if ( v5 <= -1 )
    {
      v7 = L"HeapAlloc for newThreadStatus failed";
      goto LABEL_113;
    }
    v21[1] = a2;
    *v21 = CurrentThreadId;
    RtlAcquireSRWLockExclusive(v9);
    v23 = *(_QWORD **)v10;
    if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) != v10 )
LABEL_30:
      __fastfail(3u);
    *((_QWORD *)v22 + 1) = v23;
    *((_QWORD *)v22 + 2) = v10;
    v23[1] = v22 + 2;
    *(_QWORD *)v10 = v22 + 2;
    RtlReleaseSRWLockExclusive(v9);
    v24 = v22[1] | v65;
  }
  if ( v24 <= 1 )
    v3 = 1;
  else
    v3 = v24 & 0xFFFFFFFE;
  v25 = v71;
  v65 = v3;
  v26 = v71 + 144;
  RtlAcquireSRWLockShared(v71 + 144);
  if ( v3 != *(_DWORD *)(v71 + 140) )
  {
    if ( (unsigned int)dword_18002A1A0 > 5
      && (qword_18002A1B0 & 0x400000000000LL) != 0
      && (qword_18002A1B8 & 0x400000000000LL) == qword_18002A1B8 )
    {
      v27 = *(_QWORD *)(v71 + 16);
      v28 = (const WCHAR *)(v27 + 28);
      if ( v27 == -28 )
      {
        v28 = &SourceString;
        v30 = 2;
      }
      else
      {
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        v30 = 2 * v29 + 2;
      }
      v83 = v30;
      v31 = (const WCHAR *)(v27 + 540);
      v82 = v28;
      v84 = 0;
      if ( v27 == -540 )
      {
        v31 = &SourceString;
        v33 = 2;
      }
      else
      {
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        v33 = 2 * v32 + 2;
      }
      v86 = v33;
      v85 = v31;
      p_CurrentThreadId = &CurrentThreadId;
      v67 = *(_DWORD *)(v71 + 140);
      v87 = 0;
      v90 = &v67;
      v92 = &v70;
      CurrentThreadId = v3;
      v89 = 4;
      v91 = 4;
      v70 = 0x1000000;
      v93 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18002A1A0, &dword_18002388C, 0, 0, 7, v81);
    }
    if ( dword_18002A1A0 )
    {
      v34 = *(_QWORD *)(v25 + 16);
      v35 = (const WCHAR *)(v34 + 28);
      if ( v34 == -28 )
      {
        v35 = &SourceString;
        v37 = 2;
      }
      else
      {
        v36 = -1;
        do
          ++v36;
        while ( v35[v36] );
        v37 = 2 * v36 + 2;
      }
      v83 = v37;
      v38 = (const WCHAR *)(v34 + 540);
      v82 = v35;
      v84 = 0;
      if ( v34 == -540 )
      {
        v38 = &SourceString;
        v40 = 2;
      }
      else
      {
        v39 = -1;
        do
          ++v39;
        while ( v38[v39] );
        v40 = 2 * v39 + 2;
      }
      v86 = v40;
      v85 = v38;
      p_CurrentThreadId = &CurrentThreadId;
      v67 = *(_DWORD *)(v25 + 140);
      v87 = 0;
      v90 = &v67;
      CurrentThreadId = v3;
      v89 = 4;
      v91 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18002A1A0, byte_18002382B, 0, 0, 6, v81);
    }
    RtlReleaseSRWLockShared(v26);
    RtlAcquireSRWLockExclusive(v26);
    *(_DWORD *)(v25 + 140) = v3;
    RtlReleaseSRWLockExclusive(v26);
    RtlAcquireSRWLockShared(v26);
  }
  RtlReleaseSRWLockShared(v26);
LABEL_66:
  v41 = GetProcessHeap();
  v4 = HeapAlloc(v41, 8u, 0xDCu);
  v5 = v4 == 0 ? 8 : 0;
  if ( !v4 )
    v5 |= 0x80070000;
  if ( v5 > -1 )
  {
    *(_QWORD *)v4 = 1886219331;
    v4[2] = 200;
    v4[3] = 1507328;
    memset_0(v4 + 4, 0, 0xB8u);
    v42 = -1073741811;
    if ( *((_WORD *)v4 + 7) )
    {
      v44 = (unsigned int)v4[2];
      if ( ((v44 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xDC )
      {
        v46 = (v44 + 3) & 0xFFFFFFFC;
        v45 = v46;
        v4[2] = v46;
        v4[5] = v46;
        v43 = 0;
        v4[4] = 65543;
        *((_BYTE *)v4 + v45) = 1;
        ++v4[2];
      }
      else
      {
        v43 = -1073741789;
      }
    }
    else
    {
      v43 = -1073741811;
    }
    v47 = RtlNtStatusToDosError(v43);
    v5 = v47;
    if ( v47 > 0 )
      v5 = (unsigned __int16)v47 | 0x80070000;
    if ( v5 > -1 )
    {
      if ( *((_WORD *)v4 + 7) > 1u )
      {
        v49 = (unsigned int)v4[2];
        if ( ((v49 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xDC )
        {
          v50 = ((_DWORD)v49 + 3) & 0xFFFFFFFC;
          v4[2] = v50;
          if ( *((_WORD *)v4 + 12) )
            *((_WORD *)v4 + 6) |= 1u;
          v4[6] = 131080;
          v48 = 0;
          v4[7] = v50;
          *(_WORD *)((char *)v4 + v50) = 6;
          v4[2] += 2;
        }
        else
        {
          v48 = -1073741789;
        }
      }
      else
      {
        v48 = -1073741811;
      }
      v51 = RtlNtStatusToDosError(v48);
      v5 = v51;
      if ( v51 > 0 )
        v5 = (unsigned __int16)v51 | 0x80070000;
      if ( v5 > -1 )
      {
        if ( *((_WORD *)v4 + 7) > 4u )
        {
          v53 = (unsigned int)v4[2];
          if ( ((v53 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xDC )
          {
            v54 = ((_DWORD)v53 + 3) & 0xFFFFFFFC;
            v4[2] = v54;
            if ( *((_WORD *)v4 + 24) )
              *((_WORD *)v4 + 6) |= 1u;
            v4[12] = 524294;
            v52 = 0;
            v4[13] = v54;
            *(_QWORD *)((char *)v4 + v54) = v2;
            v4[2] += 8;
          }
          else
          {
            v52 = -1073741789;
          }
        }
        else
        {
          v52 = -1073741811;
        }
        v55 = RtlNtStatusToDosError(v52);
        v5 = v55;
        if ( v55 > 0 )
          v5 = (unsigned __int16)v55 | 0x80070000;
        if ( v5 > -1 )
        {
          if ( *((_WORD *)v4 + 7) > 0xDu )
          {
            v56 = (unsigned int)v4[2];
            if ( ((v56 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xDC )
            {
              v57 = ((_DWORD)v56 + 3) & 0xFFFFFFFC;
              v4[2] = v57;
              if ( *((_WORD *)v4 + 60) )
                *((_WORD *)v4 + 6) |= 1u;
              v4[30] = 262154;
              v42 = 0;
              v4[31] = v57;
              *(_DWORD *)((char *)v4 + v57) = v3;
              v4[2] += 4;
            }
            else
            {
              v42 = -1073741789;
            }
          }
          v58 = RtlNtStatusToDosError(v42);
          v5 = v58;
          if ( v58 > 0 )
            v5 = (unsigned __int16)v58 | 0x80070000;
          if ( v5 > -1 )
          {
            v4[1] = 0;
            *((_WORD *)v4 + 6) &= ~2u;
            v59 = FilterSendMessage(hPort, v4, 0xDCu, 0, 0, &BytesReturned);
            v7 = L"FilterSendMessage Failed";
            v5 = v59;
            if ( v59 > -1 )
              v7 = 0;
          }
          else
          {
            v7 = L"SetCldDsMsgProviderStatus Failed";
          }
        }
        else
        {
          v7 = L"SetCldDsMsgSyncRootKey Failed";
        }
      }
      else
      {
        v7 = L"SetCldMsgCommand Failed";
      }
    }
    else
    {
      v7 = L"SetVersion Failed";
    }
  }
  else
  {
    v7 = L"HeapAlloc for CldCmdUpdateProviderStatus Failed";
  }
LABEL_113:
  v77 = v2;
  v60 = v71;
  v76 = v7;
  v78 = v6;
  v79 = v65;
  if ( v71 )
  {
    v61 = (const WCHAR *)((*(_QWORD *)(v71 + 16) + 540LL) & -(__int64)(*(_QWORD *)(v71 + 16) != 0));
    v62 = (const WCHAR *)((*(_QWORD *)(v71 + 16) + 28LL) & -(__int64)(*(_QWORD *)(v71 + 16) != 0));
  }
  else
  {
    v62 = 0;
    v61 = 0;
  }
  TlmLogApiReliability(0xDu, 0, 0, v62, v61, UnbiasedTime, &v75, v5);
  if ( v60 )
    CfpReleaseSyncRoot(v60);
  if ( v4 )
  {
    v63 = GetProcessHeap();
    HeapFree(v63, 0, v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800082b0  mov     [rsp-8+arg_10], rbx
0x1800082b5  push    rbp
0x1800082b6  push    rsi
0x1800082b7  push    rdi
0x1800082b8  push    r12
0x1800082ba  push    r13
0x1800082bc  push    r14
0x1800082be  push    r15
0x1800082c0  lea     rbp, [rsp-60h]
0x1800082c5  sub     rsp, 160h
0x1800082cc  mov     rax, cs:__security_cookie
0x1800082d3  xor     rax, rsp
0x1800082d6  mov     [rbp+90h+var_40], rax
0x1800082da  xor     r15d, r15d
0x1800082dd  mov     [rsp+190h+var_14C], edx
0x1800082e1  mov     rbx, rcx
0x1800082e4  mov     [rsp+190h+var_120], rcx
0x1800082e9  xor     edx, edx; Val
0x1800082eb  mov     [rsp+190h+UnbiasedTime], r15
0x1800082f0  lea     rcx, [rbp+90h+var_110]; void *
0x1800082f4  mov     [rsp+190h+var_150], r15d
0x1800082f9  lea     r8d, [r15+58h]; Size
0x1800082fd  mov     [rsp+190h+BytesReturned], r15d
0x180008302  mov     r12d, r15d
0x180008305  call    memset_0
0x18000830a  lea     rcx, [rsp+190h+UnbiasedTime]; UnbiasedTime
0x18000830f  call    cs:__imp_QueryUnbiasedInterruptTime
0x180008316  nop     dword ptr [rax+rax+00h]
0x18000831b  mov     rcx, rbx
0x18000831e  call    CfpReferenceSyncRoot
0x180008323  mov     [rsp+190h+var_130], rax
0x180008328  mov     r14, rax
0x18000832b  test    rax, rax
0x18000832e  jz      loc_180008819
0x180008334  xor     ecx, ecx
0x180008336  mov     [rsp+190h+var_118], r15
0x18000833b  mov     esi, r15d
0x18000833e  mov     [rbp+90h+var_F0], 1
0x180008342  call    GlobalPortInit
0x180008347  mov     edi, eax
0x180008349  cmp     eax, 0FFFFFFFFh
0x18000834c  jg      short loc_18000835F
0x18000834e  mov     r13d, [rsp+190h+var_14C]
0x180008353  lea     rcx, aGlobalportinit; "GlobalPortInit Failed"
0x18000835a  jmp     loc_180008AFE
0x18000835f  mov     [rsp+190h+var_148], r15d
0x180008364  mov     r13d, r15d
0x180008367  call    cs:__imp_GetCurrentThreadId
0x18000836e  nop     dword ptr [rax+rax+00h]
0x180008373  lea     r12, [r14+0A8h]
0x18000837a  mov     [rsp+190h+var_144], eax
0x18000837e  mov     rcx, r12
0x180008381  mov     [rsp+190h+var_138], r12
0x180008386  call    cs:__imp_RtlAcquireSRWLockShared
0x18000838d  nop     dword ptr [rax+rax+00h]
0x180008392  add     r14, 98h
0x180008399  mov     rcx, [r14]
0x18000839c  cmp     rcx, r14
0x18000839f  jz      short loc_1800083FB
0x1800083a1  mov     ebx, [rsp+190h+var_144]
0x1800083a5  mov     r12d, [rsp+190h+var_14C]
0x1800083aa  mov     r15, [rcx]
0x1800083ad  lea     rdi, [rcx-8]
0x1800083b1  cmp     [rdi], ebx
0x1800083b3  jnz     loc_180008508
0x1800083b9  mov     [rsp+190h+var_148], 1
0x1800083c1  test    r12d, r12d
0x1800083c4  jns     loc_1800084FF
0x1800083ca  mov     eax, r12d
0x1800083cd  not     eax
0x1800083cf  and     eax, [rcx-4]
0x1800083d2  mov     [rdi+4], eax
0x1800083d5  test    rdi, rdi
0x1800083d8  jz      short loc_1800083DD
0x1800083da  or      esi, [rdi+4]
0x1800083dd  mov     rcx, r15
0x1800083e0  cmp     r15, r14
0x1800083e3  jnz     short loc_1800083AA
0x1800083e5  mov     rbx, [rsp+190h+var_120]
0x1800083ea  xor     r15d, r15d
0x1800083ed  mov     r12, [rsp+190h+var_138]
0x1800083f2  mov     [rsp+190h+var_150], esi
0x1800083f6  mov     rsi, [rsp+190h+var_118]
0x1800083fb  mov     rcx, r12
0x1800083fe  call    cs:__imp_RtlReleaseSRWLockShared
0x180008405  nop     dword ptr [rax+rax+00h]
0x18000840a  test    r13d, r13d
0x18000840d  jz      loc_180008495
0x180008413  mov     rcx, r12
0x180008416  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000841d  nop     dword ptr [rax+rax+00h]
0x180008422  mov     rdi, [r14]
0x180008425  cmp     rdi, r14
0x180008428  jz      short loc_180008486
0x18000842a  mov     ecx, [rdi-8]; dwThreadId
0x18000842d  mov     r13, [rdi]
0x180008430  call    CfpIsThreadTerminated
0x180008435  test    eax, eax
0x180008437  jz      short loc_18000847B
0x180008439  mov     rcx, [rdi]
0x18000843c  cmp     [rcx+8], rdi
0x180008440  jnz     loc_180008545
0x180008446  mov     rax, [rdi+8]
0x18000844a  cmp     [rax], rdi
0x18000844d  jnz     loc_180008545
0x180008453  mov     [rax], rcx
0x180008456  mov     [rcx+8], rax
0x18000845a  call    cs:__imp_GetProcessHeap
0x180008461  nop     dword ptr [rax+rax+00h]
0x180008466  lea     r8, [rdi-8]; lpMem
0x18000846a  xor     edx, edx; dwFlags
0x18000846c  mov     rcx, rax; hHeap
0x18000846f  call    cs:__imp_HeapFree
0x180008476  nop     dword ptr [rax+rax+00h]
0x18000847b  mov     rdi, r13
0x18000847e  cmp     r13, r14
0x180008481  jnz     short loc_18000842A
0x180008483  xor     r15d, r15d
0x180008486  mov     rcx, r12
0x180008489  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008490  nop     dword ptr [rax+rax+00h]
0x180008495  cmp     [rsp+190h+var_148], r15d
0x18000849a  jnz     loc_18000857B
0x1800084a0  call    cs:__imp_GetProcessHeap
0x1800084a7  nop     dword ptr [rax+rax+00h]
0x1800084ac  mov     r8d, 18h; dwBytes
0x1800084b2  mov     rcx, rax; hHeap
0x1800084b5  lea     r13d, [r8-10h]
0x1800084b9  mov     edx, r13d; dwFlags
0x1800084bc  call    cs:__imp_HeapAlloc
0x1800084c3  nop     dword ptr [rax+rax+00h]
0x1800084c8  mov     rcx, rax
0x1800084cb  mov     r15, rax
0x1800084ce  neg     rcx
0x1800084d1  sbb     edi, edi
0x1800084d3  not     edi
0x1800084d5  and     edi, r13d
0x1800084d8  mov     r13d, [rsp+190h+var_14C]
0x1800084dd  mov     ecx, edi
0x1800084df  or      ecx, 80070000h
0x1800084e5  test    rax, rax
0x1800084e8  cmovz   edi, ecx
0x1800084eb  cmp     edi, 0FFFFFFFFh
0x1800084ee  jg      short loc_180008522
0x1800084f0  lea     rcx, aHeapallocForNe; "HeapAlloc for newThreadStatus failed"
0x1800084f7  xor     r15d, r15d
0x1800084fa  jmp     loc_180008AFE
0x1800084ff  mov     [rcx-4], r12d
0x180008503  jmp     loc_1800083D5
0x180008508  mov     ecx, [rdi]; dwThreadId
0x18000850a  call    CfpIsThreadTerminated
0x18000850f  test    eax, eax
0x180008511  jz      loc_1800083D5
0x180008517  mov     r13d, 1
0x18000851d  jmp     loc_1800083DD
0x180008522  mov     [rax+4], r13d
0x180008526  mov     rcx, r12
0x180008529  mov     eax, [rsp+190h+var_144]
0x18000852d  mov     [r15], eax
0x180008530  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008537  nop     dword ptr [rax+rax+00h]
0x18000853c  mov     rcx, [r14]
0x18000853f  cmp     [rcx+8], r14
0x180008543  jz      short loc_18000854C
0x180008545  mov     ecx, 3
0x18000854a  int     29h; Win8: RtlFailFast(ecx)
0x18000854c  lea     rax, [r15+8]
0x180008550  mov     [rax], rcx
0x180008553  mov     [rax+8], r14
0x180008557  mov     [rcx+8], rax
0x18000855b  mov     rcx, r12
0x18000855e  mov     [r14], rax
0x180008561  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008568  nop     dword ptr [rax+rax+00h]
0x18000856d  mov     r12d, [rsp+190h+var_150]
0x180008572  or      r12d, [r15+4]
0x180008576  xor     r15d, r15d
0x180008579  jmp     short loc_180008585
0x18000857b  mov     r12d, [rsp+190h+var_150]
0x180008580  mov     r13d, [rsp+190h+var_14C]
0x180008585  mov     eax, 1
0x18000858a  cmp     r12d, eax
0x18000858d  jbe     short loc_180008595
0x18000858f  and     r12d, 0FFFFFFFEh
0x180008593  jmp     short loc_180008598
0x180008595  mov     r12d, eax
0x180008598  mov     r14, [rsp+190h+var_130]
0x18000859d  mov     [rsp+190h+var_150], r12d
0x1800085a2  lea     rdi, [r14+90h]
0x1800085a9  mov     rcx, rdi
0x1800085ac  call    cs:__imp_RtlAcquireSRWLockShared
0x1800085b3  nop     dword ptr [rax+rax+00h]
0x1800085b8  cmp     r12d, [r14+8Ch]
0x1800085bf  jz      loc_180008808
0x1800085c5  mov     eax, cs:dword_18002A1A0
0x1800085cb  lea     rsi, SourceString
0x1800085d2  cmp     eax, 5
0x1800085d5  jbe     loc_1800086EE
0x1800085db  mov     rcx, cs:qword_18002A1B8
0x1800085e2  mov     rdx, 400000000000h
0x1800085ec  mov     rax, cs:qword_18002A1B0
0x1800085f3  test    rdx, rax
0x1800085f6  jz      loc_1800086EE
0x1800085fc  mov     rax, rcx
0x1800085ff  and     rax, rdx
0x180008602  cmp     rax, rcx
0x180008605  jnz     loc_1800086EE
0x18000860b  mov     rdx, [r14+10h]
0x18000860f  lea     rax, [rdx+1Ch]
0x180008613  test    rax, rax
0x180008616  jz      short loc_18000862F
0x180008618  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000861c  inc     rcx
0x18000861f  cmp     [rax+rcx*2], r15w
0x180008624  jnz     short loc_18000861C
0x180008626  lea     ecx, ds:2[rcx*2]
0x18000862d  jmp     short loc_180008637
0x18000862f  mov     rax, rsi
0x180008632  mov     ecx, 2
0x180008637  mov     [rbp+90h+var_88], ecx
0x18000863a  lea     rcx, [rdx+21Ch]
0x180008641  mov     [rbp+90h+var_90], rax
0x180008645  mov     [rbp+90h+var_84], r15d
0x180008649  test    rcx, rcx
0x18000864c  jz      short loc_180008665
0x18000864e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008652  inc     rax
0x180008655  cmp     [rcx+rax*2], r15w
0x18000865a  jnz     short loc_180008652
0x18000865c  lea     eax, ds:2[rax*2]
0x180008663  jmp     short loc_18000866D
0x180008665  mov     rcx, rsi
0x180008668  mov     eax, 2
0x18000866d  mov     [rbp+90h+var_78], eax
0x180008670  lea     rdx, dword_18002388C
0x180008677  lea     rax, [rsp+190h+var_144]
0x18000867c  mov     [rbp+90h+var_80], rcx
0x180008680  mov     [rbp+90h+var_70], rax
0x180008684  lea     rcx, dword_18002A1A0
0x18000868b  mov     eax, [r14+8Ch]
0x180008692  xor     r9d, r9d
0x180008695  mov     [rsp+190h+var_148], eax
0x180008699  xor     r8d, r8d
0x18000869c  lea     rax, [rsp+190h+var_148]
0x1800086a1  mov     [rbp+90h+var_74], r15d
0x1800086a5  mov     [rbp+90h+var_60], rax
0x1800086a9  lea     rax, [rsp+190h+var_138]
0x1800086ae  mov     [rbp+90h+var_50], rax
0x1800086b2  lea     rax, [rbp+90h+var_B0]
0x1800086b6  mov     [rsp+190h+lpBytesReturned], rax
0x1800086bb  mov     [rsp+190h+dwOutBufferSize], 7
0x1800086c3  mov     [rsp+190h+var_144], r12d
0x1800086c8  mov     [rbp+90h+var_68], 4
0x1800086d0  mov     [rbp+90h+var_58], 4
0x1800086d8  mov     [rsp+190h+var_138], 1000000h
0x1800086e1  mov     [rbp+90h+var_48], 8
0x1800086e9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800086ee  mov     eax, cs:dword_18002A1A0
0x1800086f4  test    eax, eax
0x1800086f6  jz      loc_1800087C5
0x1800086fc  mov     rdx, [r14+10h]
0x180008700  lea     rax, [rdx+1Ch]
0x180008704  test    rax, rax
0x180008707  jz      short loc_180008720
0x180008709  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000870d  inc     rcx
0x180008710  cmp     [rax+rcx*2], r15w
0x180008715  jnz     short loc_18000870D
0x180008717  lea     ecx, ds:2[rcx*2]
0x18000871e  jmp     short loc_180008728
0x180008720  mov     rax, rsi
0x180008723  mov     ecx, 2
0x180008728  mov     [rbp+90h+var_88], ecx
0x18000872b  lea     rcx, [rdx+21Ch]
0x180008732  mov     [rbp+90h+var_90], rax
0x180008736  mov     [rbp+90h+var_84], r15d
0x18000873a  test    rcx, rcx
0x18000873d  jz      short loc_180008756
0x18000873f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008743  inc     rax
0x180008746  cmp     [rcx+rax*2], r15w
0x18000874b  jnz     short loc_180008743
0x18000874d  lea     eax, ds:2[rax*2]
0x180008754  jmp     short loc_18000875E
0x180008756  mov     rcx, rsi
0x180008759  mov     eax, 2
0x18000875e  mov     [rbp+90h+var_78], eax
0x180008761  lea     rdx, byte_18002382B
0x180008768  lea     rax, [rsp+190h+var_144]
0x18000876d  mov     [rbp+90h+var_80], rcx
0x180008771  mov     [rbp+90h+var_70], rax
0x180008775  lea     rcx, dword_18002A1A0
0x18000877c  mov     eax, [r14+8Ch]
0x180008783  xor     r9d, r9d
0x180008786  mov     [rsp+190h+var_148], eax
0x18000878a  xor     r8d, r8d
0x18000878d  lea     rax, [rsp+190h+var_148]
0x180008792  mov     [rbp+90h+var_74], r15d
0x180008796  mov     [rbp+90h+var_60], rax
0x18000879a  lea     rax, [rbp+90h+var_B0]
  ... truncated ...
```
