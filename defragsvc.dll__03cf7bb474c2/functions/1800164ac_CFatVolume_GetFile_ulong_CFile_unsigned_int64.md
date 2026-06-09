# CFatVolume::_GetFile(ulong *,_CFile *,unsigned __int64 *)

- ea: `0x1800164ac`
- end: `0x180016e78`
- name: `?_GetFile@CFatVolume@@AEAAJPEAKPEAU_CFile@@PEA_K@Z`
- size: `2508`
- prototype: `__int64 __fastcall(CFatVolume *__hidden this, unsigned int *, struct _CFile *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014910`
- `0x1800402b0`

## callees

- `0x180006400`
- `0x180008af0`
- `0x18000ad50`
- `0x180010bc0`
- `0x180014acc`
- `0x180014c68`
- `0x180014e48`
- `0x180014f70`
- `0x1800156a0`
- `0x1800157fc`
- `0x1800164ac`
- `0x180017e34`
- `0x18001913c`
- `0x180019228`
- `0x1800192b4`
- `0x18001fed8`
- `0x18001ff18`
- `0x18002af08`
- `0x18002cf74`
- `0x18003905c`
- `0x180067af2`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016b78`
- `msvcrt!_wcsicmp` at `0x180016b90`
- `msvcrt!_wcsicmp` at `0x180016b78`
- `msvcrt!_wcsicmp` at `0x180016b90`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800169a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800169a3`
- `ntdll!NtQueryDirectoryFile` at `0x180016a8e`
- `ntdll!NtQueryDirectoryFile` at `0x180016a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016cec`

## pseudocode

```c
__int64 __fastcall CFatVolume::_GetFile(CFatVolume *this, unsigned int *a2, struct _CFile *a3, unsigned __int64 *a4)
{
  __int64 v7; // rbx
  LPVOID *v8; // r15
  unsigned int *v9; // rax
  __int64 v10; // rcx
  struct _CFile *v11; // rax
  bool v12; // zf
  __int16 v13; // ax
  unsigned int v14; // r14d
  __int16 v15; // ax
  __int64 v16; // r8
  unsigned int v17; // r9d
  _QWORD *v18; // rcx
  __int64 v19; // r12
  __int64 v20; // r12
  __int64 v21; // rcx
  _BYTE *v22; // rax
  int v23; // edx
  int v24; // r14d
  int HandleToFile; // esi
  CFatVolume *v26; // rcx
  unsigned int v27; // esi
  __int64 v29; // rsi
  int v30; // eax
  _WORD *v31; // rdx
  int v32; // r15d
  unsigned __int16 *v33; // r14
  size_t v34; // rsi
  struct _QUEUED_DIR *v35; // r14
  __int16 v36; // ax
  unsigned __int16 v37; // dx
  unsigned int v38; // edx
  unsigned __int16 *v39; // rax
  LPCWSTR *v40; // rax
  char *FileW; // rsi
  CFatVolume *v42; // rcx
  void *v43; // rcx
  _QWORD *v44; // r14
  NTSTATUS v45; // eax
  __int64 v46; // rcx
  int v47; // esi
  char *v48; // rcx
  unsigned int v49; // r8d
  wchar_t *v50; // rsi
  LPVOID v51; // rax
  unsigned __int16 **v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  unsigned int *v55; // rcx
  unsigned __int64 v56; // rax
  _DWORD *v57; // rdx
  unsigned __int16 **v58; // rdx
  unsigned int v59; // [rsp+68h] [rbp-A0h] BYREF
  int v60; // [rsp+6Ch] [rbp-9Ch]
  int v61; // [rsp+70h] [rbp-98h] BYREF
  __int16 v62; // [rsp+74h] [rbp-94h]
  __int16 v63; // [rsp+76h] [rbp-92h]
  unsigned __int16 *v64; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-58h]
  __int64 v66; // [rsp+B8h] [rbp-50h]
  void *Src; // [rsp+C0h] [rbp-48h]
  unsigned int v68; // [rsp+C8h] [rbp-40h] BYREF
  struct _QUEUED_DIR **v69; // [rsp+D0h] [rbp-38h]
  struct _QUEUED_DIR *v70; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v72; // [rsp+E8h] [rbp-20h]
  LPVOID pv; // [rsp+F0h] [rbp-18h]
  __int64 v74; // [rsp+F8h] [rbp-10h]
  void *v75; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int16 *v76[4]; // [rsp+108h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+20h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v61, "CFatVolume::_GetFile", 867, 1);
  v59 = 0;
  v7 = -1;
  v75 = (void *)-1LL;
  v68 = 0;
  v8 = 0;
  v76[2] = (unsigned __int16 *)&qword_18006F470;
  v76[3] = 0;
  v74 = -1;
  IoStatusBlock = 0;
  String1 = (wchar_t *)&qword_18006F470;
  v72 = 0;
  v64 = (unsigned __int16 *)&qword_18006F470;
  v65 = 0;
  v76[0] = (unsigned __int16 *)&qword_18006F470;
  v76[1] = 0;
  v9 = a2;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
  {
    v10 = 16;
    v11 = a3;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (struct _CFile *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
    v9 = a2;
  }
  if ( a4 )
    *a4 = 0;
  v12 = v9 == 0;
  v13 = 895;
  if ( v12 || (v62 = 895, v13 = 896, !a3) || (v62 = 896, v13 = 897, !a4) )
  {
    v61 = -2147024809;
LABEL_11:
    v63 = v13;
    goto LABEL_36;
  }
  v61 = 0;
  v62 = 897;
  v61 = CBulkAllocator<CFatFile>::Alloc(*((_QWORD *)this + 135), &v59);
  v14 = v59;
  v15 = 899;
  if ( v61 < 0 )
  {
LABEL_33:
    v63 = v15;
    goto LABEL_34;
  }
  v62 = 899;
  v13 = 900;
  if ( !v59 )
  {
    v61 = -2147024882;
    goto LABEL_11;
  }
  v61 = 0;
  v62 = 900;
  v16 = *((_QWORD *)this + 135);
  if ( !*(_DWORD *)(v16 + 28) )
  {
    v61 = -2147467259;
    goto LABEL_41;
  }
  if ( (v59 & 0xF0000000) != *(_DWORD *)(v16 + 28)
    || (v17 = (unsigned __int16)v59 != 0 ? (unsigned __int16)v59 - 1 : 0,
        (v18 = *(_QWORD **)(*(_QWORD *)(v16 + 8) + 8 * (((unsigned __int64)v59 >> 16) & 0xFFF))) == 0)
    || v17 >= *(_DWORD *)(v16 + 20) )
  {
    v61 = -2147024809;
LABEL_41:
    v15 = 902;
    goto LABEL_33;
  }
  v19 = *(_QWORD *)(v16 + 32) * v17;
  v12 = *v18 + v19 == 0;
  v20 = *v18 + v19;
  v62 = 902;
  v15 = 903;
  if ( v12 )
  {
    v61 = -2147024882;
    goto LABEL_33;
  }
  v61 = 0;
  v62 = 903;
  v21 = 24;
  v22 = (_BYTE *)v20;
  do
  {
    *v22++ = 0;
    --v21;
  }
  while ( v21 );
  if ( !*((_QWORD *)this + 132) )
  {
    v51 = CoTaskMemAlloc(0x40000u);
    *((_QWORD *)this + 132) = v51;
    v21 = 912;
    if ( !v51 )
    {
      v61 = -2147024882;
      v63 = 912;
      goto LABEL_34;
    }
    v61 = 0;
    v62 = 912;
    *((_QWORD *)this + 133) = v51;
    *((_DWORD *)this + 268) = 0x40000;
  }
  v23 = 0;
  LODWORD(v66) = 0;
  v24 = 0;
  LODWORD(Src) = 0;
  while ( *((_QWORD *)this + 49) )
  {
    if ( v23 )
      goto LABEL_29;
    v40 = (LPCWSTR *)CFatVolume::PopDir(this);
    v8 = (LPVOID *)v40;
    pv = v40;
    v70 = (struct _QUEUED_DIR *)v40;
    FileW = (char *)*((_QWORD *)this + 131);
    v21 = (__int64)(FileW - 1);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      FileW = (char *)CreateFileW(*v40, 0x89u, 1u, 0, 3u, 0x2000000u, 0);
      v74 = (__int64)FileW;
      if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        CFatVolume::FreeDir(v42, &v70);
        v8 = (LPVOID *)CFatVolume::PopDir(this);
        pv = v8;
      }
      v21 = *((_QWORD *)this + 131);
      if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle((HANDLE)v21);
        *((_QWORD *)this + 131) = -1;
      }
      *((_QWORD *)this + 131) = FileW;
      v74 = -1;
    }
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_70;
    v43 = (void *)*((_QWORD *)this + 132);
    v44 = (_QWORD *)((char *)this + 1064);
    v69 = (struct _QUEUED_DIR **)((char *)this + 1064);
    if ( v43 != *((void **)this + 133) )
    {
      v69 = (struct _QUEUED_DIR **)((char *)this + 1064);
      goto LABEL_81;
    }
    v60 = 1;
    v45 = NtQueryDirectoryFile(
            FileW,
            0,
            0,
            0,
            &IoStatusBlock,
            v43,
            *((_DWORD *)this + 268),
            FileBothDirectoryInformation,
            0,
            &CFatVolume::s_ustrFileMask,
            0);
    v47 = 0;
    if ( (unsigned int)IsNtStatusBufferTooSmall(v45) )
    {
      v55 = (unsigned int *)*((_QWORD *)this + 132);
      v56 = *v55;
      if ( (_DWORD)v56 )
      {
        do
        {
          v57 = v55;
          v55 += v56 >> 2;
          v56 = *v55;
        }
        while ( (_DWORD)v56 );
        if ( v57 )
          *v57 = 0;
      }
      v46 = 0;
LABEL_106:
      v47 = v60;
      goto LABEL_79;
    }
    if ( (_DWORD)v46 != -2147483642 && (_DWORD)v46 != -1073741809 )
      goto LABEL_106;
    *v44 = *((_QWORD *)this + 132);
    v48 = (char *)*((_QWORD *)this + 131);
    if ( (unsigned __int64)(v48 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v48);
      *((_QWORD *)this + 131) = -1;
    }
    if ( v8 )
    {
      CoTaskMemFree(*v8);
      *v8 = 0;
      CoTaskMemFree(v8);
    }
    v8 = (LPVOID *)CFatVolume::PopDir(this);
    pv = v8;
    v46 = 0;
LABEL_79:
    v61 = HRESULTFromNTSTATUS(v46);
    if ( v61 < 0 )
    {
      v63 = 1018;
      v14 = v59;
      goto LABEL_92;
    }
    v62 = 1018;
    if ( !v47 )
    {
LABEL_94:
      v24 = (int)Src;
LABEL_70:
      v23 = v66;
      goto LABEL_59;
    }
LABEL_81:
    if ( *(_DWORD *)*v44 )
      v35 = (struct _QUEUED_DIR *)(*v44 + *(unsigned int *)*v44);
    else
      v35 = (struct _QUEUED_DIR *)*((_QWORD *)this + 132);
    v70 = v35;
    *v69 = v35;
    v49 = *((_DWORD *)v35 + 15) >> 1;
    if ( (_DWORD)v72 )
    {
      LODWORD(v72) = 0;
      *String1 = 0;
    }
    v61 = CBsString::Append((CBsString *)&String1, (const unsigned __int16 *)v35 + 47, v49);
    v36 = 1046;
    if ( v61 < 0 )
      goto LABEL_91;
    v62 = 1046;
    LODWORD(v69) = *((_DWORD *)v35 + 14);
    v68 = (unsigned int)v69;
    v50 = String1;
    if ( !_wcsicmp(String1, L"..") )
      goto LABEL_94;
    if ( !_wcsicmp(v50, L".") )
    {
      v24 = (int)Src;
      goto LABEL_70;
    }
    v31 = *v8;
    Src = *v8;
    if ( (_DWORD)v65 )
    {
      LODWORD(v65) = 0;
      *v64 = 0;
    }
    if ( !v31 )
    {
      v61 = -2147024809;
LABEL_118:
      v36 = 1058;
LABEL_91:
      v63 = v36;
      v14 = v59;
      goto LABEL_92;
    }
    v29 = -1;
    do
      ++v29;
    while ( v31[v29] );
    v66 = v29;
    v30 = 0;
    if ( (_DWORD)v29 && (v30 = CBsString::ExtendBuffer((CBsString *)&v64, (int)v29 + 1), v60 = v30, v30 >= 0) )
    {
      v32 = v65;
      v33 = &v64[(unsigned int)v65];
      v34 = (unsigned int)v29;
      memcpy_0(v33, Src, v34 * 2);
      v33[v34] = 0;
      LODWORD(v65) = v66 + v32;
      v61 = v60;
      v35 = v70;
      v8 = (LPVOID *)pv;
    }
    else
    {
      v61 = v30;
      if ( v30 < 0 )
        goto LABEL_118;
    }
    v62 = 1058;
    v61 = CBsString::Trailing((CBsString *)&v64, (unsigned __int16)v31);
    v36 = 1059;
    if ( v61 < 0 )
      goto LABEL_91;
    v62 = 1059;
    v61 = CBsString::Append((CBsString *)&v64, String1);
    v36 = 1060;
    if ( v61 < 0 )
      goto LABEL_91;
    v62 = 1060;
    if ( ((unsigned __int8)v69 & 0x10) != 0 )
    {
      v61 = CBsString::Trailing((CBsString *)&v64, v37);
      v36 = 1067;
      if ( v61 < 0 )
        goto LABEL_91;
      v62 = 1067;
      v61 = CBsString::Set((CBsString *)v76, v64);
      v36 = 1068;
      if ( v61 < 0 )
        goto LABEL_91;
      v62 = 1068;
      v58 = (unsigned __int16 **)CoTaskMemAlloc(0x10u);
      v36 = 1073;
      if ( !v58 )
      {
        v61 = -2147024882;
        goto LABEL_91;
      }
      v61 = 0;
      v62 = 1073;
      v53 = 16;
      v52 = v58;
      do
      {
        *(_BYTE *)v52 = 0;
        v52 = (unsigned __int16 **)((char *)v52 + 1);
        --v53;
      }
      while ( v53 );
      CBsString::Detach((CBsString *)v76, v58);
      *(_QWORD *)(v54 + 8) = *((_QWORD *)this + 49);
      *((_QWORD *)this + 49) = v54;
      v24 = 1;
    }
    else
    {
      v38 = *((_DWORD *)this + 126);
      if ( v38 )
        *((_QWORD *)this + 50) += (*((unsigned int *)v35 + 12) | (unsigned __int64)((__int64)*((int *)v35 + 13) << 32))
                                / v38;
      v24 = 0;
    }
    LODWORD(Src) = v24;
    v23 = 1;
    LODWORD(v66) = 1;
    v21 = v20 + 16;
    if ( v20 != -16 )
    {
      v39 = 0;
      if ( v64 != &qword_18006F470 )
        v39 = v64;
      *(_QWORD *)v21 = v39;
      v64 = (unsigned __int16 *)&qword_18006F470;
      v65 = 0;
    }
LABEL_59:
    if ( v8 )
      v8[1] = (LPVOID)*((_QWORD *)this + 49);
    *((_QWORD *)this + 49) = v8;
    v8 = 0;
  }
  if ( !v23 )
  {
    v61 = 1;
    v62 = 1107;
    v14 = v59;
    goto LABEL_34;
  }
LABEL_29:
  HandleToFile = CFatVolume::_GetHandleToFile((CFatVolume *)v21, (struct CFatFile *)v20, &v75);
  v7 = (__int64)v75;
  if ( HandleToFile < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_27185f1a9bc437e4d2e47001646cc874_Traceguids,
        *(_QWORD *)(v20 + 16));
    }
    *(_DWORD *)(v20 + 4) |= 0x41u;
    if ( v24 )
      *(_DWORD *)(v20 + 4) |= 4u;
    v14 = v59;
    if ( HandleToFile != -1996488674 )
    {
      v61 = HandleToFile;
      v15 = 1128;
      goto LABEL_33;
    }
  }
  else
  {
    v14 = v59;
    v61 = CFatVolume::_ScanFileFromHandle(this, v75, &v68, (struct CFatFile *)v20, v59);
    v15 = 1134;
    if ( v61 < 0 )
      goto LABEL_33;
    v62 = 1134;
  }
  v61 = CFatVolume::_SetSystemFlags(v26, String1, (struct CFatFile *)v20);
  v15 = 1138;
  if ( v61 < 0 )
    goto LABEL_33;
  v62 = 1138;
  *a4 = *((_QWORD *)this + 50);
  *(_OWORD *)a3 = *(_OWORD *)v20;
  *a2 = v14;
  v14 = 0;
  v59 = 0;
  v61 = 0;
LABEL_92:
  if ( v8 )
  {
    CoTaskMemFree(*v8);
    *v8 = 0;
    CoTaskMemFree(v8);
  }
LABEL_34:
  if ( v14 )
    CBulkAllocator<CFatFile>::Free(*((_QWORD *)this + 135), &v59);
LABEL_36:
  v27 = v61;
  CBsString::_FreeData(v76[0]);
  CBsString::_FreeData(v64);
  CBsString::_FreeData(String1);
  CBsString::_FreeData((unsigned __int16 *)&qword_18006F470);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v61);
  return v27;
}

```

## disassembly

```asm
0x1800164ac  mov     rax, rsp
0x1800164af  mov     [rax+8], rbx
0x1800164b3  mov     [rax+20h], r9
0x1800164b7  mov     [rax+18h], r8
0x1800164bb  mov     [rax+10h], rdx
0x1800164bf  push    rbp
0x1800164c0  push    rsi
0x1800164c1  push    rdi
0x1800164c2  push    r12
0x1800164c4  push    r13
0x1800164c6  push    r14
0x1800164c8  push    r15
0x1800164ca  lea     rbp, [rax-68h]
0x1800164ce  sub     rsp, 130h
0x1800164d5  mov     r14, r9
0x1800164d8  mov     r12, r8
0x1800164db  mov     r13, rcx
0x1800164de  mov     r9d, 1; unsigned __int16
0x1800164e4  mov     r8d, 363h; unsigned __int16
0x1800164ea  lea     rdx, aCfatvolumeGetf; "CFatVolume::_GetFile"
0x1800164f1  lea     rcx, [rsp+160h+var_F8]; this
0x1800164f6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800164fb  nop
0x1800164fc  xor     eax, eax
0x1800164fe  mov     [rsp+160h+var_100], eax
0x180016502  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016506  mov     [rbp+60h+var_68], rbx
0x18001650a  mov     [rbp+60h+var_A0], eax
0x18001650d  mov     r15d, eax
0x180016510  lea     rcx, qword_18006F470
0x180016517  mov     [rbp+60h+var_50], rcx
0x18001651b  mov     [rbp+60h+var_48], rax
0x18001651f  mov     rdi, rbx
0x180016522  mov     [rbp+60h+var_70], rbx
0x180016526  xorps   xmm0, xmm0
0x180016529  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x18001652d  mov     [rbp+60h+String1], rcx
0x180016531  xor     esi, esi
0x180016533  mov     [rbp+60h+var_80], rsi
0x180016537  mov     [rbp+60h+var_C0], rcx
0x18001653b  mov     [rbp+60h+var_B8], rsi
0x18001653f  mov     [rbp+60h+var_60], rcx
0x180016543  mov     [rbp+60h+var_58], rsi
0x180016547  mov     rax, [rbp+60h+arg_8]
0x18001654b  test    rax, rax
0x18001654e  jz      short loc_180016552
0x180016550  mov     [rax], esi
0x180016552  test    r12, r12
0x180016555  jz      short loc_18001656F
0x180016557  mov     ecx, 10h
0x18001655c  mov     rax, r12
0x18001655f  mov     [rax], sil
0x180016562  inc     rax
0x180016565  sub     rcx, 1
0x180016569  jnz     short loc_18001655F
0x18001656b  mov     rax, [rbp+60h+arg_8]
0x18001656f  test    r14, r14
0x180016572  jz      short loc_180016577
0x180016574  mov     [r14], rsi
0x180016577  test    rax, rax
0x18001657a  mov     eax, 37Fh
0x18001657f  jnz     short loc_180016593
0x180016581  mov     [rsp+160h+var_F8], 80070057h
0x180016589  mov     [rsp+160h+var_F2], ax
0x18001658e  jmp     loc_180016758
0x180016593  mov     [rsp+160h+var_F4], ax
0x180016598  mov     eax, 380h
0x18001659d  test    r12, r12
0x1800165a0  jz      short loc_180016581
0x1800165a2  mov     [rsp+160h+var_F4], ax
0x1800165a7  mov     eax, 381h
0x1800165ac  test    r14, r14
0x1800165af  jz      short loc_180016581
0x1800165b1  mov     [rsp+160h+var_F8], esi
0x1800165b5  mov     [rsp+160h+var_F4], ax
0x1800165ba  lea     rdx, [rsp+160h+var_100]
0x1800165bf  mov     rcx, [r13+438h]
0x1800165c6  call    ?Alloc@?$CBulkAllocator@VCFatFile@@@@QEAAJPEAK@Z; CBulkAllocator<CFatFile>::Alloc(ulong *)
0x1800165cb  mov     [rsp+160h+var_F8], eax
0x1800165cf  mov     r14d, [rsp+160h+var_100]
0x1800165d4  test    eax, eax
0x1800165d6  mov     eax, 383h
0x1800165db  js      loc_18001674A
0x1800165e1  mov     [rsp+160h+var_F4], ax
0x1800165e6  mov     eax, 384h
0x1800165eb  test    r14d, r14d
0x1800165ee  jz      loc_1800167C2
0x1800165f4  mov     [rsp+160h+var_F8], esi
0x1800165f8  mov     [rsp+160h+var_F4], ax
0x1800165fd  mov     r8, [r13+438h]
0x180016604  cmp     [r8+1Ch], esi
0x180016608  jbe     loc_180016C73
0x18001660e  mov     edx, r14d
0x180016611  mov     eax, r14d
0x180016614  and     eax, 0F0000000h
0x180016619  cmp     eax, [r8+1Ch]
0x18001661d  jnz     loc_1800167E5
0x180016623  test    edx, edx
0x180016625  jz      loc_1800167E5
0x18001662b  movzx   eax, dx
0x18001662e  lea     ecx, [rax-1]
0x180016631  neg     eax
0x180016633  sbb     r9d, r9d
0x180016636  and     r9d, ecx
0x180016639  shr     rdx, 10h
0x18001663d  and     edx, 0FFFh
0x180016643  mov     rax, [r8+8]
0x180016647  mov     rcx, [rax+rdx*8]
0x18001664b  test    rcx, rcx
0x18001664e  jz      loc_1800167E5
0x180016654  cmp     r9d, [r8+14h]
0x180016658  jnb     loc_1800167E5
0x18001665e  mov     r12d, r9d
0x180016661  imul    r12, [r8+20h]
0x180016666  add     r12, [rcx]
0x180016669  mov     eax, 386h
0x18001666e  mov     [rsp+160h+var_F4], ax
0x180016673  mov     eax, 387h
0x180016678  jz      short loc_1800166D9
0x18001667a  mov     [rsp+160h+var_F8], esi
0x18001667e  mov     [rsp+160h+var_F4], ax
0x180016683  mov     ecx, 18h
0x180016688  mov     rax, r12
0x18001668b  mov     [rax], sil
0x18001668e  inc     rax
0x180016691  sub     rcx, 1; this
0x180016695  jnz     short loc_18001668B
0x180016697  cmp     [r13+420h], rsi
0x18001669e  jz      loc_180016C13
0x1800166a4  mov     edx, esi
0x1800166a6  mov     dword ptr [rbp+60h+var_B0], edx
0x1800166a9  mov     r14d, esi
0x1800166ac  mov     dword ptr [rbp+60h+Src], esi
0x1800166af  cmp     [r13+188h], rsi
0x1800166b6  jnz     loc_18001694B
0x1800166bc  test    edx, edx
0x1800166be  jnz     short loc_1800166E3
0x1800166c0  mov     [rsp+160h+var_F8], 1
0x1800166c8  mov     eax, 453h
0x1800166cd  mov     [rsp+160h+var_F4], ax
0x1800166d2  mov     r14d, [rsp+160h+var_100]
0x1800166d7  jmp     short loc_18001674F
0x1800166d9  mov     [rsp+160h+var_F8], 8007000Eh
0x1800166e1  jmp     short loc_18001674A
0x1800166e3  lea     r8, [rbp+60h+var_68]; void **
0x1800166e7  mov     rdx, r12; struct CFatFile *
0x1800166ea  call    ?_GetHandleToFile@CFatVolume@@AEAAJPEAVCFatFile@@PEAPEAX@Z; CFatVolume::_GetHandleToFile(CFatFile *,void * *)
0x1800166ef  mov     esi, eax
0x1800166f1  mov     rbx, [rbp+60h+var_68]
0x1800166f5  test    eax, eax
0x1800166f7  js      loc_180016DBB
0x1800166fd  mov     r14d, [rsp+160h+var_100]
0x180016702  mov     [rsp+160h+dwCreationDisposition], r14d; unsigned int
0x180016707  mov     r9, r12; struct CFatFile *
0x18001670a  lea     r8, [rbp+60h+var_A0]; unsigned int *
0x18001670e  mov     rdx, rbx; void *
0x180016711  mov     rcx, r13; this
0x180016714  call    ?_ScanFileFromHandle@CFatVolume@@AEAAJPEAXPEAKPEAVCFatFile@@K@Z; CFatVolume::_ScanFileFromHandle(void *,ulong *,CFatFile *,ulong)
0x180016719  mov     [rsp+160h+var_F8], eax
0x18001671d  xor     esi, esi
0x18001671f  test    eax, eax
0x180016721  mov     eax, 46Eh
0x180016726  js      short loc_18001674A
0x180016728  mov     [rsp+160h+var_F4], ax
0x18001672d  mov     r8, r12; struct CFatFile *
0x180016730  mov     rdx, [rbp+60h+String1]; unsigned __int16 *
0x180016734  call    ?_SetSystemFlags@CFatVolume@@AEAAJPEBGPEAVCFatFile@@@Z; CFatVolume::_SetSystemFlags(ushort const *,CFatFile *)
0x180016739  mov     [rsp+160h+var_F8], eax
0x18001673d  test    eax, eax
0x18001673f  mov     eax, 472h
0x180016744  jns     loc_180016E24
0x18001674a  mov     [rsp+160h+var_F2], ax
0x18001674f  test    r14d, r14d
0x180016752  jnz     loc_180016E61
0x180016758  mov     esi, [rsp+160h+var_F8]
0x18001675c  mov     rcx, [rbp+60h+var_60]; unsigned __int16 *
0x180016760  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180016765  nop
0x180016766  mov     rcx, [rbp+60h+var_C0]; unsigned __int16 *
0x18001676a  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x18001676f  nop
0x180016770  mov     rcx, [rbp+60h+String1]; unsigned __int16 *
0x180016774  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180016779  nop
0x18001677a  lea     rax, [rdi-1]
0x18001677e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016782  jbe     short loc_1800167CF
0x180016784  lea     rcx, qword_18006F470; unsigned __int16 *
0x18001678b  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180016790  nop
0x180016791  lea     rcx, [rbx-1]
0x180016795  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180016799  jbe     short loc_1800167DA
0x18001679b  lea     rcx, [rsp+160h+var_F8]; this
0x1800167a0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800167a5  mov     eax, esi
0x1800167a7  mov     rbx, [rsp+160h+arg_0]
0x1800167af  add     rsp, 130h
0x1800167b6  pop     r15
0x1800167b8  pop     r14
0x1800167ba  pop     r13
0x1800167bc  pop     r12
0x1800167be  pop     rdi
0x1800167bf  pop     rsi
0x1800167c0  pop     rbp
0x1800167c1  retn
0x1800167c2  mov     [rsp+160h+var_F8], 8007000Eh
0x1800167ca  jmp     loc_180016589
0x1800167cf  mov     rcx, rdi; hObject
0x1800167d2  call    cs:__imp_CloseHandle
0x1800167d8  jmp     short loc_180016784
0x1800167da  mov     rcx, rbx; hObject
0x1800167dd  call    cs:__imp_CloseHandle
0x1800167e3  jmp     short loc_18001679B
0x1800167e5  mov     [rsp+160h+var_F8], 80070057h
0x1800167ed  mov     eax, 386h
0x1800167f2  jmp     loc_18001674A
0x1800167f7  test    rdx, rdx
0x1800167fa  jz      loc_180016DA9
0x180016800  mov     rsi, rbx
0x180016803  xor     ecx, ecx
0x180016805  inc     rsi
0x180016808  cmp     [rdx+rsi*2], cx
0x18001680c  jnz     short loc_180016805
0x18001680e  mov     [rbp+60h+var_B0], rsi
0x180016812  mov     eax, ecx
0x180016814  test    esi, esi
0x180016816  jz      short loc_180016870
0x180016818  lea     edx, [rsi+1]; unsigned int
0x18001681b  lea     rcx, [rbp+60h+var_C0]; this
0x18001681f  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180016824  mov     dword ptr [rsp+160h+var_FC], eax
0x180016828  test    eax, eax
0x18001682a  js      short loc_180016870
0x18001682c  mov     r15d, dword ptr [rbp+60h+var_B8]
0x180016830  mov     rcx, [rbp+60h+var_C0]
0x180016834  lea     r14, [rcx+r15*2]
0x180016838  mov     ecx, esi
0x18001683a  lea     rsi, [rcx+rcx]
0x18001683e  mov     r8, rsi; Size
0x180016841  mov     rdx, [rbp+60h+Src]; Src
0x180016845  mov     rcx, r14; void *
0x180016848  call    memcpy_0
0x18001684d  xor     ecx, ecx
0x18001684f  mov     [rsi+r14], cx
0x180016854  add     r15d, dword ptr [rbp+60h+var_B0]
0x180016858  mov     dword ptr [rbp+60h+var_B8], r15d
0x18001685c  mov     eax, dword ptr [rsp+160h+var_FC]
0x180016860  mov     [rsp+160h+var_F8], eax
0x180016864  mov     r14, [rbp+60h+var_90]
0x180016868  mov     r15, [rbp+60h+pv]
0x18001686c  xor     esi, esi
0x18001686e  jmp     short loc_18001687E
0x180016870  mov     [rsp+160h+var_F8], eax
0x180016874  xor     esi, esi
0x180016876  test    eax, eax
0x180016878  js      loc_180016DB1
0x18001687e  mov     eax, 422h
0x180016883  mov     [rsp+160h+var_F4], ax
0x180016888  lea     rcx, [rbp+60h+var_C0]; this
0x18001688c  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180016891  mov     [rsp+160h+var_F8], eax
0x180016895  test    eax, eax
0x180016897  mov     eax, 423h
0x18001689c  js      loc_180016BCB
0x1800168a2  mov     [rsp+160h+var_F4], ax
0x1800168a7  mov     rdx, [rbp+60h+String1]; unsigned __int16 *
0x1800168ab  lea     rcx, [rbp+60h+var_C0]; this
0x1800168af  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1800168b4  mov     [rsp+160h+var_F8], eax
0x1800168b8  test    eax, eax
0x1800168ba  mov     eax, 424h
0x1800168bf  js      loc_180016BCB
0x1800168c5  mov     [rsp+160h+var_F4], ax
0x1800168ca  test    byte ptr [rbp+60h+var_98], 10h
0x1800168ce  jnz     loc_180016D00
0x1800168d4  mov     edx, [r13+1F8h]
0x1800168db  test    edx, edx
0x1800168dd  jz      short loc_1800168FC
0x1800168df  movsxd  rax, dword ptr [r14+34h]
0x1800168e3  shl     rax, 20h
0x1800168e7  mov     ecx, [r14+30h]
0x1800168eb  or      rax, rcx
0x1800168ee  mov     ecx, edx
0x1800168f0  xor     edx, edx
0x1800168f2  div     rcx
0x1800168f5  add     [r13+190h], rax
0x1800168fc  mov     r14d, esi
0x1800168ff  mov     dword ptr [rbp+60h+Src], r14d
0x180016903  mov     edx, 1
0x180016908  mov     dword ptr [rbp+60h+var_B0], edx
0x18001690b  lea     rcx, [r12+10h]
0x180016910  test    rcx, rcx
0x180016913  jz      short loc_180016933
0x180016915  mov     rax, rsi
0x180016918  lea     r8, qword_18006F470
0x18001691f  cmp     [rbp+60h+var_C0], r8
0x180016923  cmovnz  rax, [rbp+60h+var_C0]
0x180016928  mov     [rcx], rax
0x18001692b  mov     [rbp+60h+var_C0], r8
  ... truncated ...
```
