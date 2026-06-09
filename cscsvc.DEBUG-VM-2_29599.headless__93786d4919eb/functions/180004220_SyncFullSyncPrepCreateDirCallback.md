# SyncFullSyncPrepCreateDirCallback

- ea: `0x180004220`
- end: `0x180004c34`
- name: `SyncFullSyncPrepCreateDirCallback`
- size: `2580`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64, int, __int64, PHANDLE FileHandle, int, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x180003b6c`
- `0x180004220`
- `0x180004c40`
- `0x180004c70`
- `0x1800060a0`
- `0x1800223c0`
- `0x1800360c0`
- `0x180036394`
- `0x18003e928`
- `0x180044554`
- `0x18006eaa4`
- `0x1800715d8`
- `0x180074984`
- `0x1800772e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004423`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004412`

## string_xrefs

- `0x18000498d`: `SyncOpenUNCPathServerForEnumeration: Handle: 0x%p UNCPath: 0x%p DesiredAccess: 0x%x ShareAccess: 0x%x`
- `0x1800049f7`: `SyncOpenUNCPathServerForEnumeration: Error opening '%wZ' (%x)`
- `0x180004a38`: `SyncOpenUNCPathServerForEnumeration: %x`
- `0x1800047a7`: `SyncFullSyncPrepCreateDirCallback: Ctx: 0x%p RemoteHdl: 0x%p LocalHdl: 0x%p RemoteItem: 0x%p LocalItem: 0x%p`
- `0x180004815`: `SyncFullSyncPrepCreateDirCallback: NewRemote: 0x%p NewLocal: 0x%p NewContext: 0x%p EnterDir: 0x%p`
- `0x180004b72`: `SyncFullSyncPrepCreateDirCallback: Invalid remote buffer! (R: %d NE: %d)`
- `0x180004b40`: `SyncFullSyncPrepCreateDirCallback: 0x%x`
- `0x180004bbf`: `SyncFullSyncPrepCreateDirCallback: 0x%x`
- `0x180004c04`: `SyncFullSyncPrepCreateDirCallback: 0x%x`
- `0x180004af0`: `SyncFullSyncPrepCreateDirCallback: Invalid local buffer! (R: %d NE: %d)`
- `0x1800048ab`: `SyncFullSyncPrepCreateDirCallback: SyncOpenUNCPathLocalForEnumeration (Local) failed with %x`
- `0x180004924`: `SyncFullSyncPrepCreateDirCallback: Received %d on [%ws] for NEXT_ITEM`
- `0x180004a7c`: `SyncFullSyncPrepCreateDirCallback: SyncOpenUNCPathServerForEnumeration (Remote) failed with %x`

## pseudocode

```c
__int64 __fastcall SyncFullSyncPrepCreateDirCallback(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        HANDLE *a8,
        PHANDLE FileHandle,
        __int64 a10,
        _BYTE *a11)
{
  unsigned int DirCallback; // r15d
  CObjectMonitor *v15; // rax
  PHANDLE v16; // r12
  HANDLE *v17; // r13
  __int64 v18; // rbx
  int v19; // ecx
  unsigned int v20; // r8d
  unsigned int v21; // esi
  bool v22; // cf
  unsigned int v23; // r8d
  unsigned int v24; // esi
  bool v25; // cf
  __int64 v26; // rax
  int *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int *v30; // rdx
  __int64 v31; // rax
  unsigned int v33; // edi
  __int64 v34; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rbx
  _WORD *v39; // rcx
  _WORD *v40; // rdx
  _WORD *v41; // r9
  __int64 v42; // rax
  __int64 v43; // r10
  _WORD *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // r9
  const wchar_t *v47; // rdx
  _WORD *v48; // r8
  __int64 v49; // rcx
  _WORD *v50; // rcx
  int *v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rcx
  _WORD *v54; // rax
  __int64 v55; // rax
  int *v56; // rcx
  _WORD *v57; // rdx
  __int64 i; // r11
  _WORD *v59; // rcx
  __int64 v60; // rdx
  unsigned int v61; // ebx
  CObjectMonitor *v62; // rcx
  unsigned int Status; // ebx
  CObjectMonitor *v64; // rax
  _BYTE *v65; // rax
  unsigned int v67; // ebx
  CObjectMonitor *v68; // rax
  __int64 v69; // rdx
  CObjectMonitor *v70; // rax
  ULONG v71[2]; // [rsp+20h] [rbp-79h]
  unsigned int v72; // [rsp+60h] [rbp-39h]
  __int64 v73; // [rsp+68h] [rbp-31h] BYREF
  __int64 v74; // [rsp+70h] [rbp-29h]
  __int128 v75; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v76[4]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v77; // [rsp+E0h] [rbp+47h] BYREF
  __int64 v78; // [rsp+E8h] [rbp+4Fh]
  unsigned int *v79; // [rsp+F8h] [rbp+5Fh]

  v79 = a4;
  v78 = a2;
  DirCallback = 0;
  v75 = 0;
  v15 = WPP_GLOBAL_Control;
  v16 = FileHandle;
  v17 = a8;
  v18 = a6;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncFullSyncPrepCreateDirCallback: Ctx: 0x%p RemoteHdl: 0x%p LocalHdl: 0x%p RemoteItem: 0x%p LocalItem: 0x%p",
        a1,
        a2,
        a3,
        a4,
        a6);
      WPP_SF_qqqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        29,
        WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
        a1,
        v78,
        a3,
        a4,
        v18);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v15 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncFullSyncPrepCreateDirCallback: NewRemote: 0x%p NewLocal: 0x%p NewContext: 0x%p EnterDir: 0x%p",
        v17,
        v16,
        a10,
        a11);
      WPP_SF_qqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        30,
        WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
        v17,
        v16,
        a10,
        a11);
    }
  }
  *v17 = 0;
  *v16 = 0;
  if ( !a4 )
    goto LABEL_96;
  if ( !v18 )
    goto LABEL_96;
  v19 = *(_DWORD *)a1[2];
  if ( (v19 & 0x8000000) != 0 || (*(_DWORD *)(*a1 + 8) & 0x1000) != 0 && (v19 & 0x100000) != 0 )
    goto LABEL_96;
  *a11 = 1;
  v20 = *a4;
  v21 = a5;
  if ( v20 )
  {
    if ( a5 < v20 )
      goto LABEL_124;
    v22 = v20 < 0x60;
  }
  else
  {
    v22 = a5 < 0x60;
  }
  if ( v22 )
  {
LABEL_124:
    v70 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
      return 3221225701LL;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncFullSyncPrepCreateDirCallback: Invalid remote buffer! (R: %d NE: %d)", a5);
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, v21, *v79);
      v70 = WPP_GLOBAL_Control;
    }
    if ( v70 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v70 + 108) & 8) == 0 )
      return 3221225701LL;
    SyncTraceOutputInternal(L"SyncFullSyncPrepCreateDirCallback: 0x%x", 3221225701LL);
    v69 = 32;
    goto LABEL_130;
  }
  v23 = *(_DWORD *)v18;
  v24 = a7;
  if ( *(_DWORD *)v18 )
  {
    if ( a7 < v23 )
      goto LABEL_118;
    v25 = v23 < 0xB0;
  }
  else
  {
    v25 = a7 < 0xB0;
  }
  if ( v25 )
  {
LABEL_118:
    v68 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
      return 3221225701LL;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncFullSyncPrepCreateDirCallback: Invalid local buffer! (R: %d NE: %d)", a7);
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        33,
        WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
        v24,
        *(_DWORD *)v18);
      v68 = WPP_GLOBAL_Control;
    }
    if ( v68 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v68 + 108) & 8) == 0 )
      return 3221225701LL;
    SyncTraceOutputInternal(L"SyncFullSyncPrepCreateDirCallback: 0x%x", 3221225701LL);
    v69 = 34;
LABEL_130:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v69, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, 3221225701LL);
    return 3221225701LL;
  }
  LOBYTE(a8) = 0;
  LOBYTE(FileHandle) = 0;
  v73 = 0;
  v74 = v18 + 94;
  WORD1(v73) = *(_WORD *)(v18 + 60);
  LOWORD(v73) = WORD1(v73);
  v26 = *a1;
  LOBYTE(v77) = 0;
  v72 = SyncOpenUNCPathLocalForEnumeration(
          v16,
          7u,
          (__int64)&a8,
          (__int64)&FileHandle,
          0,
          (*(_DWORD *)(*(_QWORD *)(v26 + 16) + 8LL) & 0x800) != 0,
          (__int64)&v77);
  if ( v72 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncFullSyncPrepCreateDirCallback: SyncOpenUNCPathLocalForEnumeration (Local) failed with %x",
        v72);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 35, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, v72);
    }
    LODWORD(FileHandle) = 512;
    *a11 = 0;
  }
  else if ( (_BYTE)FileHandle && !(_BYTE)a8 || (LODWORD(FileHandle) = 0, (_BYTE)v77) )
  {
    SyncCloseFile(*v16);
    *v16 = 0;
LABEL_96:
    *a11 = 0;
    goto LABEL_76;
  }
  v27 = (int *)a1[2];
  if ( (*v27 & 0x20000000) != 0 )
  {
    v28 = 36;
  }
  else
  {
    v28 = 34;
    if ( *v27 < 0 )
      v28 = 9;
  }
  v29 = -1;
  v30 = &v27[v28];
  v31 = -1;
  do
    ++v31;
  while ( *((_WORD *)v30 + v31) );
  while ( *(_WORD *)(a1[3] + 2 * v29++ + 2) != 0 )
    ;
  ++NumAlloc;
  v33 = v31 + v29 + 3;
  v34 = 2 * v33;
  TotalAlloc += v34;
  ProcessHeap = GetProcessHeap();
  v36 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v34);
  v37 = (__int64)v36;
  if ( !v36 )
  {
    DirCallback = -1073741670;
    goto LABEL_84;
  }
  v38 = 2147483646;
  if ( v33 )
  {
    if ( v33 > 0x7FFFFFFFuLL )
    {
      *v36 = 0;
    }
    else
    {
      v39 = (_WORD *)a1[3];
      v40 = v36;
      v41 = v36;
      v42 = 2147483646;
      v43 = v33;
      do
      {
        if ( !v42 )
          break;
        if ( !*v39 )
          break;
        *v41++ = *v39++;
        --v42;
        --v43;
      }
      while ( v43 );
      v44 = v41 - 1;
      if ( v43 )
        v44 = v41;
      *v44 = 0;
      v45 = v33;
      do
      {
        if ( !*v40 )
          break;
        ++v40;
        --v45;
      }
      while ( v45 );
      if ( v45 )
      {
        v46 = v45;
        v47 = L"\\";
        v48 = (_WORD *)(v37 + 2 * (v33 - v45));
        v49 = 2147483646;
        do
        {
          if ( !v49 )
            break;
          if ( !*v47 )
            break;
          *v48++ = *v47++;
          --v49;
          --v46;
        }
        while ( v46 );
        v50 = v48 - 1;
        if ( v46 )
          v50 = v48;
        *v50 = 0;
      }
    }
  }
  v51 = (int *)a1[2];
  if ( (*v51 & 0x20000000) != 0 )
  {
    v52 = 36;
  }
  else
  {
    v52 = 34;
    if ( *v51 < 0 )
      v52 = 9;
  }
  if ( v33 && v33 <= 0x7FFFFFFFuLL )
  {
    v53 = v33;
    v54 = (_WORD *)v37;
    while ( *v54 )
    {
      ++v54;
      if ( !--v53 )
      {
        v55 = 0;
        goto LABEL_55;
      }
    }
    v55 = v33 - v53;
LABEL_55:
    if ( v53 )
    {
      v56 = &v51[v52];
      v57 = (_WORD *)(v37 + 2 * v55);
      for ( i = v33 - v55; i; --i )
      {
        if ( !v38 )
          break;
        if ( !*(_WORD *)v56 )
          break;
        *v57 = *(_WORD *)v56;
        v56 = (int *)((char *)v56 + 2);
        ++v57;
        --v38;
      }
      v59 = v57 - 1;
      if ( i )
        v59 = v57;
      *v59 = 0;
    }
  }
  v60 = *a1;
  *(_QWORD *)&v75 = v37;
  DWORD2(v75) = 1;
  v61 = (*(__int64 (__fastcall **)(__int128 *, _QWORD, __int64))v60)(&v75, *(_QWORD *)(v60 + 24), v52 * 4);
  v62 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    SyncTraceOutputInternal(L"SyncFullSyncPrepCreateDirCallback: Received %d on [%ws] for NEXT_ITEM", v61, (_QWORD)v75);
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      36,
      (unsigned int)WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
      v61,
      v75);
    v62 = WPP_GLOBAL_Control;
  }
  if ( v61 )
  {
    *a11 = 0;
    v67 = v61 - 1;
    if ( !v67 )
      goto LABEL_74;
    if ( v67 == 1 )
      DirCallback = -1073741248;
    else
      DirCallback = -1073741811;
LABEL_84:
    if ( *v16 )
    {
      SyncCloseFile(*v16);
      *v16 = 0;
    }
    if ( *v17 )
    {
      SyncCloseFile(*v17);
      *v17 = 0;
    }
    if ( !v37 )
      goto LABEL_76;
    goto LABEL_74;
  }
  Status = v72;
  if ( v72 )
  {
LABEL_72:
    v65 = a11;
    goto LABEL_73;
  }
  v73 = 0;
  v76[0] = 0;
  v74 = (__int64)v79 + 94;
  WORD1(v73) = *((_WORD *)v79 + 30);
  LOWORD(v73) = WORD1(v73);
  if ( v62 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v62 + 108) & 4) != 0 )
  {
    v71[0] = 7;
    SyncTraceOutputInternal(
      L"SyncOpenUNCPathServerForEnumeration: Handle: 0x%p UNCPath: 0x%p DesiredAccess: 0x%x ShareAccess: 0x%x",
      v17,
      &v73,
      129,
      *(_QWORD *)v71);
    WPP_SF_qqDD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      16,
      WPP_f707efbc203434f979e24425cc714701_Traceguids,
      v17,
      &v73,
      129,
      7);
  }
  Status = CscDriverRemoteCreateFile(v17, v78, &v73, 1048705, v76);
  if ( (Status & 0x80000000) == 0 )
  {
    ++OpenedHandles;
LABEL_69:
    v64 = WPP_GLOBAL_Control;
    goto LABEL_70;
  }
  v64 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
    goto LABEL_71;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncOpenUNCPathServerForEnumeration: Error opening '%wZ' (%x)", &v73, Status);
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      17,
      (unsigned int)WPP_f707efbc203434f979e24425cc714701_Traceguids,
      (unsigned int)&v73,
      Status);
    goto LABEL_69;
  }
LABEL_70:
  if ( v64 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v64 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncOpenUNCPathServerForEnumeration: %x", Status);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_f707efbc203434f979e24425cc714701_Traceguids, Status);
    v64 = WPP_GLOBAL_Control;
  }
LABEL_71:
  if ( !Status )
    goto LABEL_72;
  if ( v64 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v64 + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncFullSyncPrepCreateDirCallback: SyncOpenUNCPathServerForEnumeration (Remote) failed with %x",
      Status);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, Status);
  }
  LODWORD(FileHandle) = (unsigned int)FileHandle | 0x400;
  SyncCloseFile(*v16);
  v65 = a11;
  *v16 = 0;
  *v65 = 0;
LABEL_73:
  DirCallback = SyncEnumDefaultCreateDirCallback(
                  (int)a1,
                  (int)v17,
                  (int)v16,
                  a10,
                  (int)FileHandle,
                  Status,
                  v37,
                  (__int64)v65);
  if ( DirCallback )
    goto LABEL_84;
LABEL_74:
  SyncFree(v37);
LABEL_76:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncFullSyncPrepCreateDirCallback: 0x%x", DirCallback);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, DirCallback);
  }
  return DirCallback;
}

```

## disassembly

```asm
0x180004220  mov     [rsp-8+arg_10], rbx
0x180004225  mov     [rsp-8+arg_18], r9
0x18000422a  mov     [rsp-8+arg_8], rdx
0x18000422f  push    rbp
0x180004230  push    rsi
0x180004231  push    rdi
0x180004232  push    r12
0x180004234  push    r13
0x180004236  push    r14
0x180004238  push    r15
0x18000423a  lea     rbp, [rsp-7]
0x18000423f  sub     rsp, 0A0h
0x180004246  mov     rsi, r9
0x180004249  xorps   xmm0, xmm0
0x18000424c  xor     r9d, r9d
0x18000424f  mov     rdi, r8
0x180004252  mov     r15d, r9d
0x180004255  mov     r14, rcx
0x180004258  movups  [rbp+37h+var_58], xmm0
0x18000425c  mov     rax, cs:WPP_GLOBAL_Control
0x180004263  lea     rcx, WPP_GLOBAL_Control
0x18000426a  mov     r12, [rbp+37h+FileHandle]
0x180004271  mov     r13, [rbp+37h+arg_38]
0x180004275  mov     rbx, [rbp+37h+arg_28]
0x180004279  cmp     rax, rcx
0x18000427c  jnz     loc_18000478E
0x180004282  mov     [r13+0], r9
0x180004286  mov     [r12], r9
0x18000428a  test    rsi, rsi
0x18000428d  jz      loc_180004881
0x180004293  test    rbx, rbx
0x180004296  jz      loc_180004881
0x18000429c  mov     rax, [r14+10h]
0x1800042a0  mov     ecx, [rax]
0x1800042a2  bt      ecx, 1Bh
0x1800042a6  jb      loc_180004881
0x1800042ac  mov     rax, [r14]
0x1800042af  test    dword ptr [rax+8], 1000h
0x1800042b6  jnz     loc_180004877
0x1800042bc  mov     rax, [rbp+37h+arg_50]
0x1800042c3  mov     byte ptr [rax], 1
0x1800042c6  mov     r8d, [rsi]
0x1800042c9  mov     esi, [rbp+37h+arg_20]
0x1800042cc  test    r8d, r8d
0x1800042cf  jz      loc_18000477B
0x1800042d5  cmp     esi, r8d
0x1800042d8  jb      loc_180004B53
0x1800042de  cmp     r8d, 60h ; '`'
0x1800042e2  jb      loc_180004B53
0x1800042e8  mov     r8d, [rbx]
0x1800042eb  mov     esi, [rbp+37h+arg_30]
0x1800042ee  test    r8d, r8d
0x1800042f1  jz      loc_180004783
0x1800042f7  cmp     esi, r8d
0x1800042fa  jb      loc_180004AD1
0x180004300  cmp     r8d, 0B0h
0x180004307  jb      loc_180004AD1
0x18000430d  lea     rax, [rbx+5Eh]
0x180004311  mov     byte ptr [rbp+37h+arg_38], r15b
0x180004315  xorps   xmm0, xmm0
0x180004318  mov     byte ptr [rbp+37h+FileHandle], r15b
0x18000431f  movups  [rbp+37h+var_68], xmm0
0x180004323  mov     qword ptr [rbp+37h+var_68+8], rax
0x180004327  lea     r8, [rbp+37h+var_68]
0x18000432b  movzx   eax, word ptr [rbx+3Ch]
0x18000432f  mov     rdx, rdi
0x180004332  mov     word ptr [rbp+37h+var_68+2], ax
0x180004336  mov     word ptr [rbp+37h+var_68], ax
0x18000433a  mov     rax, [r14]
0x18000433d  mov     byte ptr [rbp+37h+arg_0], r15b
0x180004341  mov     rcx, [rax+10h]
0x180004345  mov     eax, [rcx+8]
0x180004348  lea     rcx, [rbp+37h+arg_0]
0x18000434c  mov     [rsp+0D0h+var_88], rcx; __int64
0x180004351  mov     rcx, r12; FileHandle
0x180004354  shr     eax, 0Bh
0x180004357  and     al, 1
0x180004359  mov     [rsp+0D0h+var_90], al; char
0x18000435d  lea     rax, [rbp+37h+FileHandle]
0x180004364  mov     [rsp+0D0h+var_98], r9; __int64
0x180004369  mov     r9d, 81h
0x18000436f  mov     [rsp+0D0h+var_A0], rax; __int64
0x180004374  lea     rax, [rbp+37h+arg_38]
0x180004378  mov     qword ptr [rsp+0D0h+Status], rax; __int64
0x18000437d  mov     [rsp+0D0h+var_B0], 7; ULONG
0x180004385  call    SyncOpenUNCPathLocalForEnumeration
0x18000438a  mov     [rbp+37h+var_70], eax
0x18000438d  mov     ebx, eax
0x18000438f  test    eax, eax
0x180004391  jnz     loc_180004890
0x180004397  cmp     byte ptr [rbp+37h+FileHandle], r15b
0x18000439e  jnz     loc_1800048EF
0x1800043a4  mov     dword ptr [rbp+37h+FileHandle], r15d
0x1800043ab  cmp     byte ptr [rbp+37h+arg_0], r15b
0x1800043af  jnz     loc_1800048F9
0x1800043b5  mov     rax, [r14+10h]
0x1800043b9  mov     r8d, 24h ; '$'
0x1800043bf  mov     ecx, [rax]
0x1800043c1  bt      ecx, 1Dh
0x1800043c5  jnb     loc_180004493
0x1800043cb  mov     edx, 90h
0x1800043d0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800043d7  add     rdx, rax
0x1800043da  mov     rax, rcx
0x1800043dd  nop     dword ptr [rax]
0x1800043e0  inc     rax
0x1800043e3  cmp     [rdx+rax*2], r15w
0x1800043e8  jnz     short loc_1800043E0
0x1800043ea  mov     rdx, [r14+18h]
0x1800043ee  xchg    ax, ax
0x1800043f0  cmp     [rdx+rcx*2+2], r15w
0x1800043f6  lea     rcx, [rcx+1]
0x1800043fa  jnz     short loc_1800043F0
0x1800043fc  inc     cs:NumAlloc
0x180004403  lea     edi, [rcx+3]
0x180004406  add     edi, eax
0x180004408  lea     ebx, [rdi+rdi]
0x18000440b  add     cs:TotalAlloc, rbx
0x180004412  call    cs:__imp_GetProcessHeap
0x180004418  mov     r8d, ebx; dwBytes
0x18000441b  mov     edx, 8; dwFlags
0x180004420  mov     rcx, rax; hHeap
0x180004423  call    cs:__imp_HeapAlloc
0x180004429  mov     rsi, rax
0x18000442c  test    rax, rax
0x18000442f  jz      loc_18000490B
0x180004435  mov     r11d, edi
0x180004438  mov     ebx, 7FFFFFFEh
0x18000443d  test    edi, edi
0x18000443f  jz      loc_180004526
0x180004445  cmp     r11, 7FFFFFFFh
0x18000444c  ja      short loc_1800044A3
0x18000444e  mov     rcx, [r14+18h]
0x180004452  mov     rdx, rax
0x180004455  mov     r9, rdx
0x180004458  mov     eax, ebx
0x18000445a  mov     r10d, r11d
0x18000445d  test    rax, rax
0x180004460  jz      short loc_180004481
0x180004462  movzx   r8d, word ptr [rcx]
0x180004466  test    r8w, r8w
0x18000446a  jz      short loc_180004481
0x18000446c  mov     [r9], r8w
0x180004470  add     rcx, 2
0x180004474  add     r9, 2
0x180004478  dec     rax
0x18000447b  sub     r10, 1
0x18000447f  jnz     short loc_18000445D
0x180004481  test    r10, r10
0x180004484  lea     rcx, [r9-2]
0x180004488  cmovnz  rcx, r9
0x18000448c  xor     eax, eax
0x18000448e  mov     [rcx], ax
0x180004491  jmp     short loc_1800044B4
0x180004493  test    ecx, ecx
0x180004495  mov     edx, 88h
0x18000449a  cmovs   rdx, r8
0x18000449e  jmp     loc_1800043D0
0x1800044a3  xor     eax, eax
0x1800044a5  mov     [rsi], ax
0x1800044a8  cmp     r11, 7FFFFFFFh
0x1800044af  ja      short loc_180004526
0x1800044b1  mov     rdx, rsi
0x1800044b4  mov     rcx, r11
0x1800044b7  mov     r9, r11
0x1800044ba  nop     word ptr [rax+rax+00h]
0x1800044c0  cmp     [rdx], r15w
0x1800044c4  jz      short loc_1800044D0
0x1800044c6  add     rdx, 2
0x1800044ca  sub     rcx, 1
0x1800044ce  jnz     short loc_1800044C0
0x1800044d0  xor     eax, eax
0x1800044d2  mov     r8, r9
0x1800044d5  sub     r8, rcx
0x1800044d8  test    rcx, rcx
0x1800044db  cmovz   r8, rax
0x1800044df  jz      short loc_180004526
0x1800044e1  sub     r9, r8
0x1800044e4  lea     rdx, Src; "\\"
0x1800044eb  lea     r8, [rsi+r8*2]
0x1800044ef  mov     rcx, rbx
0x1800044f2  jz      short loc_180004516
0x1800044f4  test    rcx, rcx
0x1800044f7  jz      short loc_180004516
0x1800044f9  movzx   eax, word ptr [rdx]
0x1800044fc  test    ax, ax
0x1800044ff  jz      short loc_180004516
0x180004501  mov     [r8], ax
0x180004505  add     rdx, 2
0x180004509  add     r8, 2
0x18000450d  dec     rcx
0x180004510  sub     r9, 1
0x180004514  jnz     short loc_1800044F4
0x180004516  test    r9, r9
0x180004519  lea     rcx, [r8-2]
0x18000451d  cmovnz  rcx, r8
0x180004521  xor     eax, eax
0x180004523  mov     [rcx], ax
0x180004526  mov     rdx, [r14+10h]
0x18000452a  mov     edi, 24h ; '$'
0x18000452f  mov     eax, [rdx]
0x180004531  bt      eax, 1Dh
0x180004535  jnb     loc_180004717
0x18000453b  mov     r8d, 90h
0x180004541  test    r11, r11
0x180004544  jz      short loc_1800045B2
0x180004546  cmp     r11, 7FFFFFFFh
0x18000454d  ja      short loc_1800045B2
0x18000454f  mov     rcx, r11
0x180004552  mov     rax, rsi
0x180004555  cmp     [rax], r15w
0x180004559  jz      short loc_180004569
0x18000455b  add     rax, 2
0x18000455f  sub     rcx, 1
0x180004563  jnz     short loc_180004555
0x180004565  xor     eax, eax
0x180004567  jmp     short loc_18000456F
0x180004569  mov     rax, r11
0x18000456c  sub     rax, rcx
0x18000456f  test    rcx, rcx
0x180004572  jz      short loc_1800045B2
0x180004574  lea     rcx, [r8+rdx]
0x180004578  lea     rdx, [rsi+rax*2]
0x18000457c  sub     r11, rax
0x18000457f  jz      short loc_1800045A2
0x180004581  test    rbx, rbx
0x180004584  jz      short loc_1800045A2
0x180004586  movzx   eax, word ptr [rcx]
0x180004589  test    ax, ax
0x18000458c  jz      short loc_1800045A2
0x18000458e  mov     [rdx], ax
0x180004591  add     rcx, 2
0x180004595  add     rdx, 2
0x180004599  dec     rbx
0x18000459c  sub     r11, 1
0x1800045a0  jnz     short loc_180004581
0x1800045a2  test    r11, r11
0x1800045a5  lea     rcx, [rdx-2]
0x1800045a9  cmovnz  rcx, rdx
0x1800045ad  xor     eax, eax
0x1800045af  mov     [rcx], ax
0x1800045b2  mov     rdx, [r14]
0x1800045b5  lea     rcx, [rbp+37h+var_58]
0x1800045b9  mov     qword ptr [rbp+37h+var_58], rsi
0x1800045bd  mov     dword ptr [rbp+37h+var_58+8], 1
0x1800045c4  mov     rax, [rdx]
0x1800045c7  mov     rdx, [rdx+18h]
0x1800045cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d0  mov     ebx, eax
0x1800045d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045d9  lea     rax, WPP_GLOBAL_Control
0x1800045e0  cmp     rcx, rax
0x1800045e3  jnz     loc_180004916
0x1800045e9  test    ebx, ebx
0x1800045eb  jnz     loc_180004728
0x1800045f1  mov     ebx, [rbp+37h+var_70]
0x1800045f4  test    ebx, ebx
0x1800045f6  jnz     loc_180004698
0x1800045fc  mov     r8, [rbp+37h+arg_18]
0x180004600  xorps   xmm0, xmm0
0x180004603  movups  [rbp+37h+var_68], xmm0
0x180004607  movups  [rbp+37h+var_48], xmm0
0x18000460b  lea     rax, [r8+5Eh]
0x18000460f  mov     qword ptr [rbp+37h+var_68+8], rax
0x180004613  movzx   eax, word ptr [r8+3Ch]
0x180004618  mov     word ptr [rbp+37h+var_68+2], ax
0x18000461c  mov     word ptr [rbp+37h+var_68], ax
0x180004620  lea     r15, WPP_GLOBAL_Control
0x180004627  cmp     rcx, r15
0x18000462a  jnz     loc_18000496E
0x180004630  mov     rdx, [rbp+37h+arg_8]
0x180004634  lea     rax, [rbp+37h+var_48]
0x180004638  mov     dword ptr [rsp+0D0h+var_88], 20h ; ' '
0x180004640  lea     r8, [rbp+37h+var_68]
0x180004644  mov     dword ptr [rsp+0D0h+var_90], 1
0x18000464c  mov     r9d, 100081h
0x180004652  mov     dword ptr [rsp+0D0h+var_98], 7
0x18000465a  mov     rcx, r13
0x18000465d  mov     dword ptr [rsp+0D0h+var_A0], 0
0x180004665  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18000466a  call    CscDriverRemoteCreateFile
0x18000466f  mov     ebx, eax
0x180004671  test    eax, eax
0x180004673  js      loc_1800049D6
0x180004679  inc     cs:OpenedHandles
0x180004680  mov     rax, cs:WPP_GLOBAL_Control
0x180004687  cmp     rax, r15
0x18000468a  jnz     loc_180004A2C
0x180004690  test    ebx, ebx
0x180004692  jnz     loc_180004A6F
0x180004698  mov     rax, [rbp+37h+arg_50]
0x18000469f  mov     r9, [rbp+37h+arg_48]; int
0x1800046a6  mov     r8, r12; int
0x1800046a9  mov     [rsp+0D0h+var_98], rax; __int64
0x1800046ae  mov     rdx, r13; int
0x1800046b1  mov     eax, dword ptr [rbp+37h+FileHandle]
0x1800046b7  mov     rcx, r14; int
0x1800046ba  mov     [rsp+0D0h+var_A0], rsi; __int64
0x1800046bf  mov     [rsp+0D0h+Status], ebx; Status
0x1800046c3  mov     [rsp+0D0h+var_B0], eax; int
  ... truncated ...
```
