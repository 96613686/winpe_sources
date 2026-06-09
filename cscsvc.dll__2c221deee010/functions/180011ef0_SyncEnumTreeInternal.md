# SyncEnumTreeInternal

- ea: `0x180011ef0`
- end: `0x180013238`
- name: `SyncEnumTreeInternal`
- size: `4936`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x180011cb0`
- `0x180013970`
- `0x18007c808`

## callees

- `0x180011880`
- `0x180011ef0`
- `0x180013240`
- `0x1800134c0`
- `0x180013970`
- `0x180013e50`
- `0x180014268`
- `0x180014474`
- `0x180014560`
- `0x180014760`
- `0x180028810`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18004fef4`
- `0x18004ff34`
- `0x1800728c4`
- `0x18007cac4`
- `0x18007cb34`
- `0x180089010`

## import_xrefs

- `KERNEL32!VirtualAlloc` at `0x180011fb8`
- `KERNEL32!VirtualAlloc` at `0x180011fb8`
- `KERNEL32!VirtualFree` at `0x1800123eb`
- `KERNEL32!VirtualFree` at `0x180012432`
- `KERNEL32!VirtualFree` at `0x1800123eb`
- `KERNEL32!VirtualFree` at `0x180012432`

## string_xrefs

- `0x180012b10`: `SyncEnumSetFileNamePtr: DirInfo: 0x%p`
- `0x180012c5e`: `SyncEnumSetFileNamePtr: DirInfo: 0x%p`
- `0x180012b53`: `SyncEnumSetFileNamePtr`
- `0x180012ca1`: `SyncEnumSetFileNamePtr`
- `0x180012e29`: `SyncEnumTreeInternal: SyncEnumFindFileInDirectory failed with %x`
- `0x180012ea1`: `SyncEnumTreeInternal: SyncEnumQueueDirectory failed with %x`

## pseudocode

```c
__int64 __fastcall SyncEnumTreeInternal(
        void *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        TOKEN_TYPE a7)
{
  unsigned int v11; // edi
  unsigned int v12; // ebx
  CObjectMonitor *v13; // rax
  _DWORD *v14; // rcx
  CObjectMonitor *v15; // rax
  unsigned int v16; // esi
  char v17; // r12
  CObjectMonitor *v18; // rcx
  USHORT *v19; // rdx
  __int64 v20; // r8
  int v21; // eax
  int v22; // r8d
  LPVOID v23; // rcx
  LPVOID v24; // rax
  int v25; // ecx
  int v26; // r8d
  unsigned int v27; // eax
  __int64 v28; // r13
  CObjectMonitor *v29; // rax
  __int64 v31; // r12
  __int64 v32; // rsi
  __int64 v33; // r8
  unsigned int v34; // eax
  unsigned int FileInDirectory; // ebx
  __int64 v36; // r12
  int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r9
  CObjectMonitor *v43; // rax
  LPVOID v44; // rcx
  CObjectMonitor *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  FILE_INFORMATION_CLASS v48[2]; // [rsp+20h] [rbp-C1h]
  char v49[8]; // [rsp+28h] [rbp-B9h]
  _BYTE v50[8]; // [rsp+60h] [rbp-81h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp-79h] BYREF
  LPVOID lpAddress[2]; // [rsp+78h] [rbp-69h]
  __int128 v53; // [rsp+88h] [rbp-59h]
  HANDLE hHandle; // [rsp+98h] [rbp-49h]
  unsigned int v55; // [rsp+A0h] [rbp-41h] BYREF
  LPVOID v56; // [rsp+A8h] [rbp-39h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-31h] BYREF
  LPVOID v58[2]; // [rsp+C0h] [rbp-21h]
  __int128 v59; // [rsp+D0h] [rbp-11h]
  __int64 v60; // [rsp+E0h] [rbp-1h]
  char v61; // [rsp+130h] [rbp+4Fh] BYREF
  __int64 v62; // [rsp+140h] [rbp+5Fh]

  v62 = a3;
  v56 = 0;
  hHandle = 0;
  v60 = 0;
  v61 = 0;
  v11 = 0;
  v12 = 0;
  String1 = 0;
  *(_OWORD *)lpAddress = 0;
  v53 = 0;
  String2 = 0;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTreeInternal: phdl: 0x%p shdl: 0x%p args: 0x%p", a1, a2, a3);
      *(_QWORD *)v49 = a3;
      WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, a1, a2);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 108) & 4) != 0 )
    {
      v31 = a6;
      v32 = a5;
      v48[0] = a7;
      SyncTraceOutputInternal(
        L"SyncEnumTreeInternal: mode: 0x%x callback_arg: 0x%p sync: 0x%p Depth: %d",
        a4,
        a5,
        a6,
        *(_QWORD *)v48);
      WPP_SF_Dqqd(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, v33, a4, v32, v31, a7);
      v13 = WPP_GLOBAL_Control;
    }
  }
  lpAddress[1] = 0;
  v58[1] = 0;
  if ( a1 )
  {
    if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumInitializeDirInfo: DirInfo: 0x%p Handle: 0x%p", &String1, a1);
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1, a1);
    }
    LargeAlloc += 0x10000;
    ++NumLargeAlloc;
    lpAddress[1] = VirtualAlloc(0, 0x10000u, 0x3000u, 4u);
    v14 = lpAddress[1];
    if ( !lpAddress[1] )
    {
      v43 = WPP_GLOBAL_Control;
      v16 = -1073741670;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
        goto LABEL_132;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumInitializeDirInfo: 0x%x", 3221225626LL);
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          13,
          WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids,
          3221225626LL);
        v43 = WPP_GLOBAL_Control;
      }
      if ( v43 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v43 + 108) & 1) == 0 )
        goto LABEL_132;
      SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncEnumInitializeDirInfo failed with %x", 3221225626LL);
      v41 = 34;
      v42 = 3221225626LL;
LABEL_179:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v41, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v42);
      goto LABEL_132;
    }
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumClearDirInfo: DirInfo: 0x%p", &String1);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1);
      v14 = lpAddress[1];
    }
    lpAddress[0] = v14;
    *(_QWORD *)&v53 = 0;
    String1.Buffer = 0;
    *(_DWORD *)&String1.Length = 0;
    *v14 = 0;
    DWORD2(v53) = 3;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumClearDirInfo");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    hHandle = a1;
    if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumInitializeDirInfo: 0x%x", 0);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, 0);
    }
    DWORD2(v53) |= 8u;
  }
  if ( a2 )
  {
    v39 = SyncEnumInitializeDirInfo(&String2, a2);
    v12 = v39;
    if ( v39 )
    {
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_167;
      }
      SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncEnumInitializeDirInfo failed with %x", v39);
      v40 = 35;
    }
    else
    {
      v12 = SyncStrHashNewTable(&v56);
      if ( !v12 )
        goto LABEL_14;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
LABEL_167:
        v16 = 0;
LABEL_132:
        v28 = a5;
LABEL_133:
        *(_DWORD *)(a6 + 16) = v11;
        goto LABEL_89;
      }
      SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncStrHashNewTable failed with %x", v12);
      v40 = 36;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v40, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v12);
    goto LABEL_167;
  }
LABEL_14:
  v16 = 0;
  if ( !a1 )
    goto LABEL_86;
LABEL_15:
  v17 = 0;
  v50[0] = 0;
  (*(void (__fastcall **)(__int64, char *))(v62 + 24))(a5, &v61);
  if ( v61 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTreeInternal: QueryAbortCallback requests abort");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
    }
    v11 = -1073741536;
    v28 = a5;
    v12 = -1073741536;
    v16 = -1073741536;
    *(_DWORD *)(a6 + 16) = -1073741536;
    goto LABEL_89;
  }
  v16 = 0;
  v55 = 0;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumIncrDirPtr: DirInfo: 0x%p", &String1);
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1);
    v18 = WPP_GLOBAL_Control;
  }
  v19 = (USHORT *)lpAddress[0];
  v20 = DWORD2(v53);
  if ( *(_DWORD *)lpAddress[0] )
  {
    DWORD1(v53) += *(_DWORD *)lpAddress[0];
    v19 = (USHORT *)((char *)lpAddress[0] + *(unsigned int *)lpAddress[0]);
LABEL_21:
    lpAddress[0] = v19;
    goto LABEL_22;
  }
  if ( (BYTE8(v53) & 2) != 0 )
  {
    v27 = SyncQueryDirectory(
            hHandle,
            &v55,
            lpAddress[1],
            0x10000u,
            FileBothDirectoryInformation,
            0,
            0,
            BYTE8(v53) & 1,
            (BYTE8(v53) & 8) == 0);
    v16 = v27;
    if ( (BYTE8(v53) & 1) != 0 )
    {
      v20 = DWORD2(v53) & 0xFFFFFFFE;
      DWORD2(v53) &= ~1u;
      if ( v27 && v27 != -2147483642 && v27 != -1073741809 )
        goto LABEL_60;
      v20 = (unsigned int)v20 | 4;
    }
    else
    {
      v20 = DWORD2(v53) & 0xFFFFFFFB;
    }
    DWORD2(v53) = v20;
LABEL_60:
    if ( v27 )
    {
      *(_QWORD *)&v53 = 0;
      if ( v27 == -2147483642 || v27 == -1073741809 )
      {
        v19 = (USHORT *)lpAddress[0];
        v20 = (unsigned int)v20 & 0xFFFFFFFD;
        v18 = WPP_GLOBAL_Control;
        v16 = 0;
        DWORD2(v53) = v20;
      }
      else
      {
        v19 = (USHORT *)lpAddress[0];
        v18 = WPP_GLOBAL_Control;
      }
      goto LABEL_22;
    }
    v19 = (USHORT *)lpAddress[1];
    v18 = WPP_GLOBAL_Control;
    *(_QWORD *)&v53 = v55;
    goto LABEL_21;
  }
LABEL_22:
  if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumSetFileNamePtr: DirInfo: 0x%p", &String1, v20);
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1);
    v20 = DWORD2(v53);
    v19 = (USHORT *)lpAddress[0];
    v18 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)v19 || (v20 & 2) != 0 )
  {
    String1.Buffer = v19 + 47;
    String1.Length = v19[30];
    String1.MaximumLength = v19[30];
  }
  else
  {
    String1.Buffer = 0;
    *(_DWORD *)&String1.Length = 0;
  }
  if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v18 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumSetFileNamePtr", v19, v20);
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
      v20 = DWORD2(v53);
      v19 = (USHORT *)lpAddress[0];
      v18 = WPP_GLOBAL_Control;
    }
    if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumIncrDirPtr: 0x%x", v16, v20);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v16);
      v20 = DWORD2(v53);
      v19 = (USHORT *)lpAddress[0];
      v18 = WPP_GLOBAL_Control;
    }
  }
  if ( !v16 )
  {
    while ( 1 )
    {
      if ( (v20 & 2) == 0 )
        goto LABEL_86;
      v21 = *((_DWORD *)v19 + 15);
      if ( v21 == 2 )
      {
        if ( v19[47] != 46 )
          goto LABEL_37;
      }
      else if ( v21 != 4 || v19[47] != 46 || v19[48] != 46 )
      {
LABEL_37:
        if ( a2 )
        {
          FileInDirectory = SyncEnumFindFileInDirectory(&String1, &String2, v50);
          if ( FileInDirectory )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(
                L"SyncEnumTreeInternal: SyncEnumFindFileInDirectory failed with %x",
                FileInDirectory);
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                38,
                WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids,
                FileInDirectory);
            }
            goto LABEL_148;
          }
          v12 = SyncStrHashInsert(v56, String1.Buffer, String1.Length >> 1);
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncStrHashInsert failed with %x", v12);
              v41 = 39;
              v42 = v12;
              goto LABEL_179;
            }
            goto LABEL_132;
          }
          v19 = (USHORT *)lpAddress[0];
          v17 = v50[0];
        }
        if ( (a4 & 1) != 0 )
        {
          if ( v17 )
            v22 = v59 - DWORD1(v59);
          else
            v22 = 0;
          v23 = 0;
          if ( v17 )
            v23 = v58[0];
          v11 = (*(__int64 (__fastcall **)(__int64, void *, __int64, USHORT *, int, LPVOID, int))v62)(
                  a5,
                  a1,
                  a2,
                  v19,
                  (int)v53 - DWORD1(v53),
                  v23,
                  v22);
          if ( (v11 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(L"SyncEnumTreeInternal: ItemCallback failed with %x", v11);
              v41 = 40;
              v42 = v11;
              goto LABEL_179;
            }
            goto LABEL_132;
          }
          v19 = (USHORT *)lpAddress[0];
        }
        if ( (a4 & 4) == 0 || (v19[28] & 0x10) == 0 )
          goto LABEL_52;
        v24 = v58[0];
        if ( !a2 || v17 && (*((_BYTE *)v58[0] + 56) & 0x10) != 0 )
        {
          if ( v17 )
          {
            v25 = v59 - DWORD1(v59);
          }
          else
          {
            v25 = 0;
            v24 = 0;
          }
          v11 = SyncEnumQueueDirectory(
                  (__int64)a1,
                  a2,
                  (__int64)v19,
                  (int)v53 - DWORD1(v53),
                  (__int64)v24,
                  v25,
                  v62,
                  a4,
                  a5,
                  a6,
                  a7);
          if ( (v11 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncEnumQueueDirectory failed with %x", v11);
              v41 = 41;
              v42 = v11;
              goto LABEL_179;
            }
            goto LABEL_132;
          }
          v19 = (USHORT *)lpAddress[0];
LABEL_52:
          v24 = v58[0];
        }
        if ( (a4 & 2) == 0 )
          goto LABEL_15;
        if ( v17 )
          v26 = v59 - DWORD1(v59);
        else
          v26 = 0;
        v44 = 0;
        if ( v17 )
          v44 = v24;
        v11 = (*(__int64 (__fastcall **)(__int64, void *, __int64, USHORT *, int, LPVOID, int))v62)(
                a5,
                a1,
                a2,
                v19,
                (int)v53 - DWORD1(v53),
                v44,
                v26);
        if ( !v11 )
          goto LABEL_15;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncEnumTreeInternal: ItemCallback failed with %x", v11);
          v41 = 42;
          v42 = v11;
          goto LABEL_179;
        }
        goto LABEL_132;
      }
      v16 = 0;
      v55 = 0;
      if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 108) & 4) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumIncrDirPtr: DirInfo: 0x%p", &String1);
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1);
        v20 = DWORD2(v53);
        v19 = (USHORT *)lpAddress[0];
        v18 = WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)v19 )
        break;
      if ( (v20 & 2) != 0 )
      {
        v34 = SyncQueryDirectory(
                hHandle,
                &v55,
                lpAddress[1],
                0x10000u,
                FileBothDirectoryInformation,
                0,
                0,
                v20 & 1,
                (v20 & 8) == 0);
        v16 = v34;
        if ( (BYTE8(v53) & 1) == 0 )
        {
          v20 = DWORD2(v53) & 0xFFFFFFFB;
          goto LABEL_121;
        }
        v20 = DWORD2(v53) & 0xFFFFFFFE;
        DWORD2(v53) &= ~1u;
        if ( !v34 || v34 == -2147483642 || v34 == -1073741809 )
        {
          v20 = (unsigned int)v20 | 4;
LABEL_121:
          DWORD2(v53) = v20;
        }
        if ( v34 )
        {
          *(_QWORD *)&v53 = 0;
          if ( v34 == -2147483642 || v34 == -1073741809 )
          {
            v19 = (USHORT *)lpAddress[0];
            v20 = (unsigned int)v20 & 0xFFFFFFFD;
            v18 = WPP_GLOBAL_Control;
            v16 = 0;
            DWORD2(v53) = v20;
          }
          else
          {
            v19 = (USHORT *)lpAddress[0];
            v18 = WPP_GLOBAL_Control;
          }
          goto LABEL_72;
        }
        v19 = (USHORT *)lpAddress[1];
        v18 = WPP_GLOBAL_Control;
        *(_QWORD *)&v53 = v55;
LABEL_71:
        lpAddress[0] = v19;
      }
LABEL_72:
      if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 108) & 4) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumSetFileNamePtr: DirInfo: 0x%p", &String1, v20);
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1);
        v20 = DWORD2(v53);
        v19 = (USHORT *)lpAddress[0];
        v18 = WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)v19 || (v20 & 2) != 0 )
      {
        String1.Buffer = v19 + 47;
        String1.Length = v19[30];
        String1.MaximumLength = v19[30];
      }
      else
      {
        String1.Buffer = 0;
        *(_DWORD *)&String1.Length = 0;
      }
      if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v18 + 108) & 8) != 0 )
        {
          SyncTraceOutputInternal(L"SyncEnumSetFileNamePtr", v19, v20);
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
          v20 = DWORD2(v53);
          v19 = (USHORT *)lpAddress[0];
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 108) & 8) != 0 )
        {
          SyncTraceOutputInternal(L"SyncEnumIncrDirPtr: 0x%x", v16, v20);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v16);
          v20 = DWORD2(v53);
          v19 = (USHORT *)lpAddress[0];
          v18 = WPP_GLOBAL_Control;
        }
      }
      if ( v16 )
        goto LABEL_84;
    }
    DWORD1(v53) += *(_DWORD *)v19;
    v19 = (USHORT *)((char *)v19 + *(unsigned int *)v19);
    goto LABEL_71;
  }
LABEL_84:
  if ( v16 == -2147483642 )
    v16 = 0;
LABEL_86:
  if ( !a2 )
  {
LABEL_87:
    v28 = a5;
    if ( v12 == -2147483642 )
      v12 = 0;
    goto LABEL_89;
  }
LABEL_148:
  v50[0] = 0;
  v12 = SyncEnumResetDirInfo(&String2);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_132;
    SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncEnumResetDirInfo failed with %x", v12);
    v41 = 43;
    v42 = v12;
    goto LABEL_179;
  }
  v28 = a5;
  v36 = v62;
LABEL_150:
  if ( v12 )
    goto LABEL_87;
  if ( (BYTE8(v59) & 2) == 0 )
    goto LABEL_89;
  (*(void (__fastcall **)(__int64, char *))(v36 + 24))(v28, &v61);
  if ( v61 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumTreeInternal: QueryAbortCallback requests abort");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
    }
    v11 = -1073741536;
    v12 = -1073741536;
    v16 = -1073741536;
    goto LABEL_133;
  }
  while ( (BYTE8(v59) & 2) != 0 )
  {
    v37 = *((_DWORD *)v58[0] + 15);
    if ( v37 == 2 )
    {
      if ( *((_WORD *)v58[0] + 47) != 46 )
        goto LABEL_169;
    }
    else if ( v37 != 4 || *((_WORD *)v58[0] + 47) != 46 || *((_WORD *)v58[0] + 48) != 46 )
    {
LABEL_169:
      v12 = SyncStrHashLookup(v56, (char *)v58[0] + 94, *((_WORD *)v58[0] + 30) >> 1, v50);
      if ( v12 )
      {
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncStrHashLookup failed with %x", v12);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 46, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v12);
            v45 = WPP_GLOBAL_Control;
          }
          if ( v45 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v45 + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(
              L"SyncEnumTreeInternal: SyncStrHashLookup Params: Table: 0x%p, FNL: %d, Next: %d",
              v56,
              *((unsigned int *)v58[0] + 15),
              *(unsigned int *)v58[0]);
            *(_DWORD *)v49 = *(_DWORD *)v58[0];
            WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 12), v46, v47, v56, *((_DWORD *)v58[0] + 15), *(_QWORD *)v49);
          }
        }
        goto LABEL_87;
      }
      if ( v50[0]
        || (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, LPVOID, int))v36)(
                    v28,
                    0,
                    a2,
                    0,
                    0,
                    v58[0],
                    (int)v59 - DWORD1(v59)),
            (v11 & 0x80000000) == 0) )
      {
        v12 = SyncEnumIncrDirPtr(&String2);
        goto LABEL_150;
      }
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumTreeInternal: ItemCallback failed with %x", v11);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 48, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v11);
      }
      goto LABEL_133;
    }
    v38 = SyncEnumIncrDirPtr(&String2);
    v12 = v38;
    if ( v38 )
    {
      if ( v38 == -2147483642 )
      {
        v12 = 0;
      }
      else if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumTreeInternal: SyncEnumIncrDirPtr failed with %x", v38);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v12);
      }
      break;
    }
  }
LABEL_89:
  (*(void (__fastcall **)(__int64, void *, __int64, _QWORD, unsigned int, char *))(v62 + 16))(
    v28,
    a1,
    a2,
    v16,
    v12,
    *(char **)v49);
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumCleanupDirInfo: DirInfo: 0x%p", &String1);
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String1);
    v29 = WPP_GLOBAL_Control;
  }
  if ( lpAddress[1] )
  {
    ++NumLargeFree;
    VirtualFree(lpAddress[1], 0, 0x8000u);
    v29 = WPP_GLOBAL_Control;
    lpAddress[1] = 0;
  }
  if ( v29 != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v29 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumCleanupDirInfo");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
      v29 = WPP_GLOBAL_Control;
    }
    if ( v29 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumCleanupDirInfo: DirInfo: 0x%p", &String2);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, &String2);
      v29 = WPP_GLOBAL_Control;
    }
  }
  if ( v58[1] )
  {
    ++NumLargeFree;
    VirtualFree(v58[1], 0, 0x8000u);
    v29 = WPP_GLOBAL_Control;
    v58[1] = 0;
  }
  if ( v29 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumCleanupDirInfo");
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids);
    v29 = WPP_GLOBAL_Control;
  }
  if ( v56 )
  {
    SyncStrHashCleanupTable(v56);
    v29 = WPP_GLOBAL_Control;
    v56 = 0;
  }
  if ( v11 == -2147483642 )
    v11 = 0;
  if ( v29 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumTreeInternal: 0x%x", v11);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 49, WPP_c546a7f2495631c27b6466064e48a7b0_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180011ef0  mov     [rsp-8+arg_8], rbx
0x180011ef5  mov     [rsp-8+arg_10], r8
0x180011efa  push    rbp
0x180011efb  push    rsi
0x180011efc  push    rdi
0x180011efd  push    r12
0x180011eff  push    r13
0x180011f01  push    r14
0x180011f03  push    r15
0x180011f05  lea     rbp, [rsp-0Fh]
0x180011f0a  sub     rsp, 0F0h
0x180011f11  xor     r12d, r12d
0x180011f14  xorps   xmm0, xmm0
0x180011f17  xor     eax, eax
0x180011f19  mov     [rbp+3Fh+var_78], r12
0x180011f1d  xorps   xmm1, xmm1
0x180011f20  mov     [rbp+3Fh+hHandle], rax
0x180011f24  mov     [rbp+3Fh+var_40], rax
0x180011f28  mov     r13d, r9d
0x180011f2b  mov     [rbp+3Fh+arg_0], al
0x180011f2e  mov     rsi, r8
0x180011f31  mov     r14, rdx
0x180011f34  mov     r15, rcx
0x180011f37  mov     edi, r12d
0x180011f3a  mov     ebx, r12d
0x180011f3d  movups  xmmword ptr [rbp+3Fh+String1.Length], xmm0
0x180011f41  movups  xmmword ptr [rbp+3Fh+lpAddress], xmm0
0x180011f45  movups  [rbp+3Fh+var_98], xmm0
0x180011f49  movups  xmmword ptr [rbp+3Fh+String2.Length], xmm1
0x180011f4d  movups  xmmword ptr [rbp+3Fh+var_60], xmm1
0x180011f51  movups  [rbp+3Fh+var_50], xmm1
0x180011f55  mov     rax, cs:WPP_GLOBAL_Control
0x180011f5c  lea     rcx, WPP_GLOBAL_Control
0x180011f63  cmp     rax, rcx
0x180011f66  jnz     loc_180012495
0x180011f6c  lea     rsi, WPP_GLOBAL_Control
0x180011f73  mov     [rbp+3Fh+lpAddress+8], r12
0x180011f77  mov     [rbp+3Fh+var_60+8], r12
0x180011f7b  test    r15, r15
0x180011f7e  jz      loc_18001201E
0x180011f84  cmp     rax, rsi
0x180011f87  jz      short loc_180011F93
0x180011f89  test    byte ptr [rax+6Ch], 4
0x180011f8d  jnz     loc_180012962
0x180011f93  add     cs:LargeAlloc, 10000h
0x180011f9e  mov     edx, 10000h; dwSize
0x180011fa3  inc     cs:NumLargeAlloc
0x180011faa  xor     ecx, ecx; lpAddress
0x180011fac  mov     r9d, 4; flProtect
0x180011fb2  mov     r8d, 3000h; flAllocationType
0x180011fb8  call    cs:__imp_VirtualAlloc
0x180011fbe  mov     [rbp+3Fh+lpAddress+8], rax
0x180011fc2  mov     rcx, rax
0x180011fc5  test    rax, rax
0x180011fc8  jz      loc_18001299F
0x180011fce  mov     rax, cs:WPP_GLOBAL_Control
0x180011fd5  cmp     rax, rsi
0x180011fd8  jnz     loc_1800125BE
0x180011fde  mov     [rbp+3Fh+lpAddress], rcx
0x180011fe2  mov     qword ptr [rbp+3Fh+var_98], rbx
0x180011fe6  mov     [rbp+3Fh+String1.Buffer], r12
0x180011fea  mov     dword ptr [rbp+3Fh+String1.Length], ebx
0x180011fed  mov     [rcx], r12d
0x180011ff0  mov     dword ptr [rbp+3Fh+var_98+8], 3
0x180011ff7  mov     rax, cs:WPP_GLOBAL_Control
0x180011ffe  cmp     rax, rsi
0x180012001  jnz     loc_180012601
0x180012007  mov     [rbp+3Fh+hHandle], r15
0x18001200b  cmp     rax, rsi
0x18001200e  jz      short loc_18001201A
0x180012010  test    byte ptr [rax+6Ch], 8
0x180012014  jnz     loc_180012A33
0x18001201a  or      dword ptr [rbp+3Fh+var_98+8], 8
0x18001201e  test    r14, r14
0x180012021  jnz     loc_180012824
0x180012027  mov     esi, r12d
0x18001202a  test    r15, r15
0x18001202d  jz      loc_180012382
0x180012033  test    ebx, ebx
0x180012035  jnz     loc_1800125B6
0x18001203b  mov     rax, [rbp+3Fh+arg_10]
0x18001203f  lea     rdx, [rbp+3Fh+arg_0]
0x180012043  mov     rcx, [rbp+3Fh+arg_20]
0x180012047  xor     r12b, r12b
0x18001204a  mov     [rsp+120h+var_C0], r12b
0x18001204f  mov     rax, [rax+18h]
0x180012053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012058  cmp     [rbp+3Fh+arg_0], r12b
0x18001205c  jnz     loc_1800127F1
0x180012062  xor     r9d, r9d
0x180012065  mov     esi, r9d
0x180012068  mov     [rbp+3Fh+var_80], r9d
0x18001206c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012073  lea     rdx, WPP_GLOBAL_Control
0x18001207a  cmp     rcx, rdx
0x18001207d  jz      short loc_180012089
0x18001207f  test    byte ptr [rcx+6Ch], 4
0x180012083  jnz     loc_180012A97
0x180012089  mov     rdx, [rbp+3Fh+lpAddress]
0x18001208d  mov     r8d, dword ptr [rbp+3Fh+var_98+8]
0x180012091  mov     eax, [rdx]
0x180012093  test    eax, eax
0x180012095  jz      loc_180012232
0x18001209b  add     dword ptr [rbp+3Fh+var_98+4], eax
0x18001209e  mov     eax, [rdx]
0x1800120a0  add     rdx, rax
0x1800120a3  mov     [rbp+3Fh+lpAddress], rdx
0x1800120a7  lea     rax, WPP_GLOBAL_Control
0x1800120ae  cmp     rcx, rax
0x1800120b1  jz      short loc_1800120BD
0x1800120b3  test    byte ptr [rcx+6Ch], 4
0x1800120b7  jnz     loc_180012B0C
0x1800120bd  cmp     dword ptr [rdx], 0
0x1800120c0  jz      loc_18001259C
0x1800120c6  lea     rax, [rdx+5Eh]
0x1800120ca  mov     [rbp+3Fh+String1.Buffer], rax
0x1800120ce  movzx   eax, word ptr [rdx+3Ch]
0x1800120d2  mov     [rbp+3Fh+String1.Length], ax
0x1800120d6  movzx   eax, word ptr [rdx+3Ch]
0x1800120da  mov     [rbp+3Fh+String1.MaximumLength], ax
0x1800120de  lea     rax, WPP_GLOBAL_Control
0x1800120e5  cmp     rcx, rax
0x1800120e8  jz      short loc_180012103
0x1800120ea  test    byte ptr [rcx+6Ch], 8
0x1800120ee  jnz     loc_180012B53
0x1800120f4  cmp     rcx, rax
0x1800120f7  jz      short loc_180012103
0x1800120f9  test    byte ptr [rcx+6Ch], 8
0x1800120fd  jnz     loc_180012B99
0x180012103  test    esi, esi
0x180012105  jnz     loc_180012373
0x18001210b  test    r8b, 2
0x18001210f  jz      loc_1800125B6
0x180012115  mov     eax, [rdx+3Ch]
0x180012118  cmp     eax, 2
0x18001211b  jz      loc_1800122D1
0x180012121  cmp     eax, 4
0x180012124  jz      loc_1800122B9
0x18001212a  test    r14, r14
0x18001212d  jnz     loc_180012709
0x180012133  test    r13b, 1
0x180012137  jz      short loc_18001218A
0x180012139  mov     eax, dword ptr [rbp+3Fh+var_98]
0x18001213c  sub     eax, dword ptr [rbp+3Fh+var_98+4]
0x18001213f  test    r12b, r12b
0x180012142  jnz     loc_180012D2B
0x180012148  xor     r8d, r8d
0x18001214b  xor     ecx, ecx
0x18001214d  mov     dword ptr [rsp+120h+var_F0], r8d
0x180012152  mov     r9, rdx
0x180012155  test    r12b, r12b
0x180012158  mov     r8, r14
0x18001215b  mov     rdx, r15
0x18001215e  cmovnz  rcx, [rbp+3Fh+var_60]
0x180012163  mov     qword ptr [rsp+120h+var_F8], rcx
0x180012168  mov     rcx, [rbp+3Fh+arg_20]
0x18001216c  mov     [rsp+120h+var_100], eax
0x180012170  mov     rax, [rbp+3Fh+arg_10]
0x180012174  mov     rax, [rax]
0x180012177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001217c  mov     edi, eax
0x18001217e  test    eax, eax
0x180012180  js      loc_18001263F
0x180012186  mov     rdx, [rbp+3Fh+lpAddress]
0x18001218a  test    r13b, 4
0x18001218e  jz      short loc_180012206
0x180012190  test    byte ptr [rdx+38h], 10h
0x180012194  jz      short loc_180012206
0x180012196  mov     rax, [rbp+3Fh+var_60]
0x18001219a  test    r14, r14
0x18001219d  jnz     loc_180012D38
0x1800121a3  test    r12b, r12b
0x1800121a6  jnz     loc_1800128DC
0x1800121ac  xor     ecx, ecx
0x1800121ae  xor     eax, eax
0x1800121b0  mov     r8d, [rbp+3Fh+arg_30]
0x1800121b4  mov     r9d, dword ptr [rbp+3Fh+var_98]
0x1800121b8  sub     r9d, dword ptr [rbp+3Fh+var_98+4]
0x1800121bc  mov     [rsp+120h+var_D0], r8d
0x1800121c1  mov     r8, [rbp+3Fh+arg_28]
0x1800121c5  mov     [rsp+120h+var_D8], r8
0x1800121ca  mov     r8, [rbp+3Fh+arg_20]
0x1800121ce  mov     qword ptr [rsp+120h+var_E0], r8
0x1800121d3  mov     r8, [rbp+3Fh+arg_10]
0x1800121d7  mov     dword ptr [rsp+120h+var_E8], r13d
0x1800121dc  mov     [rsp+120h+var_F0], r8
0x1800121e1  mov     r8, rdx
0x1800121e4  mov     dword ptr [rsp+120h+var_F8], ecx
0x1800121e8  mov     rdx, r14
0x1800121eb  mov     rcx, r15
0x1800121ee  mov     qword ptr [rsp+120h+var_100], rax
0x1800121f3  call    SyncEnumQueueDirectory
0x1800121f8  mov     edi, eax
0x1800121fa  test    eax, eax
0x1800121fc  js      loc_180012E7E
0x180012202  mov     rdx, [rbp+3Fh+lpAddress]
0x180012206  mov     rax, [rbp+3Fh+var_60]
0x18001220a  test    r13b, 2
0x18001220e  jz      loc_180012033
0x180012214  mov     r9d, dword ptr [rbp+3Fh+var_98]
0x180012218  sub     r9d, dword ptr [rbp+3Fh+var_98+4]
0x18001221c  test    r12b, r12b
0x18001221f  jz      loc_180012D50
0x180012225  mov     r8d, dword ptr [rbp+3Fh+var_50]
0x180012229  sub     r8d, dword ptr [rbp+3Fh+var_50+4]
0x18001222d  jmp     loc_180012D53
0x180012232  test    r8b, 2
0x180012236  jz      loc_1800120A7
0x18001223c  mov     rcx, [rbp+3Fh+hHandle]; hHandle
0x180012240  lea     rdx, [rbp+3Fh+var_80]
0x180012244  mov     eax, r8d
0x180012247  and     r8b, 1
0x18001224b  shr     eax, 3
0x18001224e  not     al
0x180012250  and     al, 1
0x180012252  mov     [rsp+120h+var_E0], al; char
0x180012256  mov     [rsp+120h+var_E8], r8b; char
0x18001225b  mov     r8, [rbp+3Fh+lpAddress+8]
0x18001225f  mov     [rsp+120h+var_F0], r9; PUNICODE_STRING
0x180012264  mov     r9d, 10000h
0x18001226a  mov     [rsp+120h+var_F8], sil; char
0x18001226f  mov     [rsp+120h+var_100], 3; FILE_INFORMATION_CLASS
0x180012277  call    SyncQueryDirectory
0x18001227c  mov     r8d, dword ptr [rbp+3Fh+var_98+8]
0x180012280  mov     esi, eax
0x180012282  test    r8b, 1
0x180012286  jnz     loc_180012683
0x18001228c  and     r8d, 0FFFFFFFBh
0x180012290  mov     dword ptr [rbp+3Fh+var_98+8], r8d
0x180012294  xor     r9d, r9d
0x180012297  test    eax, eax
0x180012299  jnz     loc_18001269C
0x18001229f  mov     eax, [rbp+3Fh+var_80]
0x1800122a2  mov     rdx, [rbp+3Fh+lpAddress+8]
0x1800122a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122ad  mov     dword ptr [rbp+3Fh+var_98], eax
0x1800122b0  mov     dword ptr [rbp+3Fh+var_98+4], r9d
0x1800122b4  jmp     loc_1800120A3
0x1800122b9  cmp     word ptr [rdx+5Eh], 2Eh ; '.'
0x1800122be  jnz     loc_18001212A
0x1800122c4  cmp     word ptr [rdx+60h], 2Eh ; '.'
0x1800122c9  jnz     loc_18001212A
0x1800122cf  jmp     short loc_1800122DC
0x1800122d1  cmp     word ptr [rdx+5Eh], 2Eh ; '.'
0x1800122d6  jnz     loc_18001212A
0x1800122dc  mov     esi, r9d
0x1800122df  mov     [rbp+3Fh+var_80], r9d
0x1800122e3  lea     rax, WPP_GLOBAL_Control
0x1800122ea  cmp     rcx, rax
0x1800122ed  jz      short loc_1800122F9
0x1800122ef  test    byte ptr [rcx+6Ch], 4
0x1800122f3  jnz     loc_180012BDD
0x1800122f9  mov     eax, [rdx]
0x1800122fb  test    eax, eax
0x1800122fd  jz      loc_180012515
0x180012303  add     dword ptr [rbp+3Fh+var_98+4], eax
0x180012306  mov     eax, [rdx]
0x180012308  add     rdx, rax
0x18001230b  mov     [rbp+3Fh+lpAddress], rdx
0x18001230f  lea     rax, WPP_GLOBAL_Control
0x180012316  cmp     rcx, rax
0x180012319  jz      short loc_180012325
0x18001231b  test    byte ptr [rcx+6Ch], 4
0x18001231f  jnz     loc_180012C5A
0x180012325  cmp     dword ptr [rdx], 0
0x180012328  jz      loc_180012669
0x18001232e  lea     rax, [rdx+5Eh]
0x180012332  mov     [rbp+3Fh+String1.Buffer], rax
0x180012336  movzx   eax, word ptr [rdx+3Ch]
0x18001233a  mov     [rbp+3Fh+String1.Length], ax
0x18001233e  movzx   eax, word ptr [rdx+3Ch]
0x180012342  mov     [rbp+3Fh+String1.MaximumLength], ax
0x180012346  lea     rax, WPP_GLOBAL_Control
0x18001234d  cmp     rcx, rax
0x180012350  jz      short loc_18001236B
0x180012352  test    byte ptr [rcx+6Ch], 8
0x180012356  jnz     loc_180012CA1
0x18001235c  cmp     rcx, rax
0x18001235f  jz      short loc_18001236B
0x180012361  test    byte ptr [rcx+6Ch], 8
0x180012365  jnz     loc_180012CE7
0x18001236b  test    esi, esi
0x18001236d  jz      loc_18001210B
0x180012373  xor     r12d, r12d
0x180012376  cmp     esi, 80000006h
0x18001237c  jz      loc_180012EBA
0x180012382  test    r14, r14
0x180012385  jnz     loc_180012754
0x18001238b  mov     r13, [rbp+3Fh+arg_20]
0x18001238f  cmp     ebx, 80000006h
0x180012395  cmovz   ebx, r12d
0x180012399  mov     rax, [rbp+3Fh+arg_10]
0x18001239d  mov     r9d, esi
0x1800123a0  mov     r8, r14
0x1800123a3  mov     [rsp+120h+var_100], ebx
0x1800123a7  mov     rdx, r15
0x1800123aa  mov     rcx, r13
0x1800123ad  mov     rax, [rax+10h]
0x1800123b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123b6  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
