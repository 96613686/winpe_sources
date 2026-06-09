# CRunDefragSimple::RunOperation(void)

- ea: `0x18002b840`
- end: `0x18002c677`
- name: `?RunOperation@CRunDefragSimple@@UEAAJXZ`
- size: `3639`
- prototype: `__int64 __fastcall(CRunDefragSimple *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000c794`
- `0x18000c848`
- `0x180013ae8`
- `0x1800140bc`
- `0x1800156a0`
- `0x18002acc4`
- `0x18002b840`
- `0x18002ebe4`
- `0x180031a5c`
- `0x1800381c4`
- `0x180038c3c`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002b929`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002b929`
- `ntdll!NtSetInformationThread` at `0x18002bf16`
- `ntdll!NtSetInformationThread` at `0x18002c03e`
- `ntdll!NtSetInformationThread` at `0x18002bf16`
- `ntdll!NtSetInformationThread` at `0x18002c03e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002be56`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002c1b9`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002be56`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002c1b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c57b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c589`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall CRunDefragSimple::RunOperation(CRunDefragSimple *this)
{
  _BYTE *v2; // r12
  struct IVolume *v3; // rdi
  bool v4; // sf
  __int16 v5; // ax
  struct IRunnableThread *v6; // rcx
  struct IRunnableThread *v7; // rcx
  unsigned int *v8; // r15
  struct IFreeSpaceManager *v9; // rcx
  bool v10; // sf
  struct IVolume *v11; // rdi
  __int64 (__fastcall *v12)(struct IVolume *, __int64, __int64 *); // rsi
  __int64 v13; // rcx
  struct IVolume *v14; // rdi
  __int64 (__fastcall *v15)(struct IVolume *, __int64, __int64 *); // rsi
  __int64 v16; // rcx
  struct IVolume *v17; // rdi
  __int64 (__fastcall *v18)(struct IVolume *, _QWORD, __int64 *); // rsi
  __int64 v19; // rcx
  int v20; // esi
  int v21; // eax
  __int16 v22; // cx
  struct IFreeSpaceManager *v23; // rcx
  unsigned int *v24; // r14
  unsigned int v25; // r13d
  __int64 i; // rdi
  __int64 v27; // rax
  bool v28; // sf
  __int16 v29; // ax
  __int64 v30; // rdx
  _BYTE *v31; // rcx
  unsigned int v32; // eax
  int v33; // eax
  int v34; // edi
  unsigned int v35; // eax
  int v36; // eax
  __int16 v37; // ax
  _QWORD *v38; // rax
  unsigned __int64 v39; // rdi
  unsigned int *j; // rdi
  __int64 v41; // rax
  __int64 v42; // rcx
  unsigned int *v43; // rcx
  unsigned int v44; // ebx
  struct IRunnableThread *v45; // rcx
  struct IFreeSpaceManager *v46; // rcx
  struct IFileOperation *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  struct IVolume *v51; // rcx
  struct IVolume *v53; // [rsp+50h] [rbp-B0h] BYREF
  int DefragListFile; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v55; // [rsp+5Ch] [rbp-A4h]
  __int16 v56; // [rsp+5Eh] [rbp-A2h]
  struct IFileOperation *v57; // [rsp+90h] [rbp-70h] BYREF
  struct IFreeSpaceManager *v58; // [rsp+98h] [rbp-68h] BYREF
  int ThreadInformation; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v60; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v61; // [rsp+A8h] [rbp-58h] BYREF
  struct IRunnableThread *v62; // [rsp+B0h] [rbp-50h] BYREF
  int v63; // [rsp+B8h] [rbp-48h] BYREF
  int v64; // [rsp+BCh] [rbp-44h] BYREF
  int v65; // [rsp+C0h] [rbp-40h] BYREF
  int v66; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v67; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v68; // [rsp+D0h] [rbp-30h] BYREF
  int v69; // [rsp+D8h] [rbp-28h] BYREF
  int v70; // [rsp+DCh] [rbp-24h]
  __int64 v71; // [rsp+E0h] [rbp-20h] BYREF
  int v72; // [rsp+E8h] [rbp-18h] BYREF
  int v73; // [rsp+ECh] [rbp-14h] BYREF
  int v74; // [rsp+F0h] [rbp-10h] BYREF
  int v75; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned __int64 v76; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v77; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v79[2]; // [rsp+110h] [rbp+10h] BYREF
  _SYSTEMTIME v80; // [rsp+120h] [rbp+20h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+130h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DefragListFile, "CRunDefragSimple::RunOperation", 49, 1);
  v53 = 0;
  v61 = 0;
  v68 = 0;
  v67 = 0;
  v75 = 0;
  v60 = 0;
  v57 = 0;
  v58 = 0;
  v76 = 0;
  ThreadInformation = 2;
  v64 = 0;
  v65 = 0;
  v74 = 0;
  v73 = 0;
  v63 = 0;
  v72 = 0;
  v71 = 0;
  v62 = 0;
  v66 = 0;
  SystemTime = 0;
  v69 = 0;
  v2 = 0;
  UnbiasedTime = 0;
  v77 = 0;
  v3 = (struct IVolume *)*((_QWORD *)this + 93);
  if ( v3 )
  {
    v70 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v3 + 8LL))(v3);
    v53 = v3;
    v8 = (unsigned int *)((char *)this + 56);
  }
  else
  {
    DefragListFile = CDefragOperation::_CreateVolumeForFileSystem(this, &v53);
    if ( DefragListFile < 0 )
    {
      v56 = 100;
      goto LABEL_150;
    }
    v55 = 100;
    GetLocalTime(&SystemTime);
    if ( *((_DWORD *)this + 192) )
    {
      DefragListFile = CDefragOperation::_ReadDefragListFile(this, v53, *((unsigned __int16 **)this + 95));
      v4 = DefragListFile < 0;
      v5 = 106;
    }
    else
    {
      DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *))(*(_QWORD *)v53 + 360LL))(v53);
      v4 = DefragListFile < 0;
      v5 = 110;
    }
    if ( v4 )
      goto LABEL_8;
    v55 = v5;
    DefragListFile = CDefragOperation::_SetPhase(this, 1u);
    v5 = 116;
    if ( DefragListFile < 0 )
      goto LABEL_8;
    v55 = 116;
    v6 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    DefragListFile = CRunAnalysis::CreateInstance(0, 0, *((_DWORD *)this + 194), v53, &v62, 0, 0, 0, 0);
    v5 = 119;
    if ( DefragListFile < 0 )
      goto LABEL_8;
    v55 = 119;
    DefragListFile = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v62 + 24LL))(
                       v62,
                       *((_QWORD *)this + 5));
    v5 = 122;
    if ( DefragListFile < 0 )
      goto LABEL_8;
    v55 = 122;
    v7 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = (unsigned int *)((char *)this + 56);
    DefragListFile = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                       *((_QWORD *)this + 6),
                       (char *)this + 56);
    if ( DefragListFile < 0 )
    {
      v56 = 128;
      goto LABEL_150;
    }
    v70 = 1;
    v55 = 128;
  }
  DefragListFile = CDefragOperation::_SetPhase(this, 3u);
  v5 = 136;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 136;
  *(_QWORD *)&v80.wYear = *((_QWORD *)v8 + 9);
  if ( (*(int (__fastcall **)(struct IVolume *))(*(_QWORD *)v53 + 224LL))(v53) < 0 )
  {
    v23 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    DefragListFile = CFreeSpaceManager::CreateInstance(*((unsigned __int16 **)this + 87), *((_QWORD *)this + 18), &v58);
    v10 = DefragListFile < 0;
    v5 = 153;
  }
  else
  {
    v9 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    DefragListFile = CTieredFreeSpaceManager::CreateInstance(
                       *((unsigned __int16 **)this + 87),
                       *((_QWORD *)this + 18),
                       *((_DWORD *)this + 38),
                       &v58);
    v10 = DefragListFile < 0;
    v5 = 149;
  }
  if ( v10 )
    goto LABEL_8;
  v55 = v5;
  v11 = v53;
  v12 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v53 + 104LL);
  v13 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  DefragListFile = v12(v11, 1, &v61);
  v5 = 157;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 157;
  v14 = v53;
  v15 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v53 + 104LL);
  v16 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  DefragListFile = v15(v14, 2, &v67);
  v5 = 158;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 158;
  v17 = v53;
  v18 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64 *))(*(_QWORD *)v53 + 104LL);
  v19 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  DefragListFile = v18(v17, 0, &v68);
  v20 = 0;
  v5 = 159;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 159;
  DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, int *, int *, int *, int *))(*(_QWORD *)v53 + 192LL))(
                     v53,
                     &v74,
                     &v73,
                     &v63,
                     &v72);
  v5 = 162;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 162;
  if ( v63 )
  {
    v79[0] = *((_QWORD *)this + 22);
    v79[1] = *((_QWORD *)this + 21);
    DefragListFile = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, _QWORD *))(*(_QWORD *)v58 + 48LL))(v58, v79);
    v5 = 169;
    if ( DefragListFile >= 0 )
    {
      v55 = 169;
      goto LABEL_39;
    }
LABEL_8:
    v56 = v5;
    goto LABEL_150;
  }
LABEL_39:
  *((_DWORD *)this + 185) = 0;
  DefragListFile = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 64LL))(v61, &v75);
  v5 = 182;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 182;
  DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, int *))(*(_QWORD *)v53 + 368LL))(v53, &v69);
  v5 = 185;
  if ( DefragListFile < 0 )
    goto LABEL_8;
  v55 = 185;
  if ( !v69 )
    *((_DWORD *)this + 194) = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v61 + 48LL))(v61, &v60);
  DefragListFile = v21;
  v22 = 193;
  if ( v21 < 0 )
  {
    v56 = 193;
    goto LABEL_150;
  }
  v24 = 0;
  v25 = 0;
  for ( i = 0; ; i = v79[0] )
  {
    v55 = v22;
    if ( v21 == 1 || !v60 )
      break;
    v27 = *(_QWORD *)v53;
    if ( v57 )
    {
      DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, struct IFileOperation *, _QWORD))(v27 + 56))(
                         v53,
                         v60,
                         v57,
                         0);
      v28 = DefragListFile < 0;
      v29 = 206;
    }
    else
    {
      DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, _QWORD, struct IFileOperation **))(v27 + 56))(
                         v53,
                         v60,
                         0,
                         &v57);
      v28 = DefragListFile < 0;
      v29 = 201;
    }
    if ( v28 )
      goto LABEL_119;
    v55 = v29;
    if ( *((_DWORD *)this + 194) )
    {
      v2 = CoTaskMemAlloc(0x60u);
      v29 = 213;
      if ( !v2 )
      {
        DefragListFile = -2147024882;
LABEL_119:
        v56 = v29;
        goto LABEL_149;
      }
      DefragListFile = 0;
      v55 = 213;
      v30 = 96;
      v31 = v2;
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
      QueryUnbiasedInterruptTime(&UnbiasedTime);
    }
    if ( v63 )
    {
      DefragListFile = ((__int64 (__fastcall *)(struct IFileOperation *, __int64, int *))v57->lpVtbl->SetProperties)(
                         v57,
                         16,
                         &v64);
      v29 = 223;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 223;
      if ( v64 )
      {
        DefragListFile = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 6) + 40LL))(
                           *((_QWORD *)this + 6),
                           &v65);
        v29 = 226;
        if ( DefragListFile < 0 )
          goto LABEL_119;
        v55 = 226;
        if ( !v65 )
        {
          if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5c97b034d65533668c1189a6944eb349_Traceguids);
          }
          ThreadInformation = 2;
          v32 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, &ThreadInformation, 4u);
          DefragListFile = HRESULTFromNTSTATUS(v32);
          v29 = 234;
          if ( DefragListFile < 0 )
            goto LABEL_119;
          v55 = 234;
        }
      }
    }
    ((void (__fastcall *)(struct IFileOperation *, _QWORD, __int64 *))v57->lpVtbl->SetProgressDialog)(
      v57,
      *((_QWORD *)this + 23),
      &v71);
    v79[0] = v71 + i;
    if ( *((_DWORD *)this + 194) )
    {
      DefragListFile = ((__int64 (__fastcall *)(struct IFileOperation *, __int64 *))v57->lpVtbl[1].SetProgressMessage)(
                         v57,
                         &v71);
      v29 = 247;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 247;
      *((_QWORD *)v2 + 2) = v71 * *((unsigned int *)this + 38);
    }
    v33 = CDefragOperation::_Defragment(this, 0, v57, v53, v58, (struct _DF_FILE_STATISTICS *)v2);
    v34 = v33;
    if ( *((_DWORD *)this + 194) )
      *(_DWORD *)v2 = v33;
    if ( v33 != -1996488682 )
    {
      DefragListFile = v33;
      v29 = 261;
      if ( v34 < 0 )
        goto LABEL_119;
      v55 = 261;
    }
    if ( v64 && !v65 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5c97b034d65533668c1189a6944eb349_Traceguids);
      }
      ThreadInformation = 0;
      v35 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, &ThreadInformation, 4u);
      DefragListFile = HRESULTFromNTSTATUS(v35);
      v29 = 275;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 275;
    }
    if ( v34 != 150995204 )
    {
      v36 = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *, struct IFreeSpaceManager *, unsigned int *))v57->lpVtbl->RenameItems)(
              v57,
              v53,
              v58,
              v8);
      DefragListFile = v36;
      if ( v36 < 0 )
      {
        v37 = 285;
LABEL_121:
        v56 = v37;
        goto LABEL_149;
      }
      v55 = 285;
      if ( v36 == 1 )
        v20 = 1;
    }
    DefragListFile = ((__int64 (__fastcall *)(struct IFileOperation *, _QWORD, unsigned __int64 *))v57->lpVtbl->SetOperationFlags)(
                       v57,
                       *((_QWORD *)this + 23),
                       &v76);
    v37 = 295;
    if ( DefragListFile < 0 )
      goto LABEL_121;
    v55 = 295;
    v66 = 0;
    DefragListFile = ((__int64 (__fastcall *)(struct IFileOperation *, __int64, int *))v57->lpVtbl->SetProperties)(
                       v57,
                       128,
                       &v66);
    v37 = 298;
    if ( DefragListFile < 0 )
      goto LABEL_121;
    v55 = 298;
    if ( v66 )
    {
      if ( v76 <= 2 )
        goto LABEL_93;
    }
    else if ( v76 <= 1 )
    {
      goto LABEL_93;
    }
    if ( !v20 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5c97b034d65533668c1189a6944eb349_Traceguids);
      }
      goto LABEL_98;
    }
LABEL_93:
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5c97b034d65533668c1189a6944eb349_Traceguids);
    }
    v38 = CoTaskMemAlloc(0x10u);
    if ( !v38 )
    {
      DefragListFile = -2147024882;
      v37 = 317;
      goto LABEL_121;
    }
    DefragListFile = 0;
    v55 = 317;
    *(_DWORD *)v38 = v60;
    v38[1] = v24;
    *((_DWORD *)v38 + 1) = v20;
    v24 = (unsigned int *)v38;
LABEL_98:
    v20 = 0;
    if ( *((_DWORD *)this + 194) )
    {
      ((void (__fastcall *)(struct IFileOperation *, struct IVolume *, _BYTE *))v57->lpVtbl[1].Unadvise)(
        v57,
        v53,
        v2 + 80);
      QueryUnbiasedInterruptTime(&v77);
      *((_QWORD *)v2 + 1) = v77 - UnbiasedTime;
      *((_QWORD *)v2 + 3) *= *((unsigned int *)this + 38);
      *((_QWORD *)v2 + 5) *= *((unsigned int *)this + 38);
      DefragListFile = ((__int64 (__fastcall *)(struct IFileOperation *, _BYTE *, unsigned int *))v57->lpVtbl[1].SetOperationFlags)(
                         v57,
                         v2,
                         v8);
      v29 = 344;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 344;
      DefragListFile = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 6) + 168LL))(
                         *((_QWORD *)this + 6),
                         v2);
      v29 = 346;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 346;
      v2 = 0;
    }
    DefragListFile = (*(__int64 (__fastcall **)(CRunDefragSimple *))(*(_QWORD *)this + 32LL))(this);
    v29 = 352;
    if ( DefragListFile < 0 )
      goto LABEL_119;
    v55 = 352;
    if ( *(_QWORD *)&v80.wYear )
    {
      v39 = (unsigned __int64)(100LL * v79[0]) / *(_QWORD *)&v80.wYear;
      if ( (unsigned int)v39 > 0x64 )
        LODWORD(v39) = 100;
    }
    else
    {
      LODWORD(v39) = 100;
    }
    if ( (unsigned int)v39 > v25 )
    {
      DefragListFile = CDefragOperation::_SetPercentComplete(this, v39);
      v29 = 370;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 370;
      v25 = v39;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v61 + 56LL))(v61, &v60);
    DefragListFile = v21;
    if ( v21 < 0 )
    {
      v29 = 376;
      goto LABEL_119;
    }
    v22 = 376;
  }
  for ( j = v24; j; j = (unsigned int *)*((_QWORD *)j + 1) )
  {
    DefragListFile = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v61 + 32LL))(v61, *j);
    v29 = 384;
    if ( DefragListFile < 0 )
      goto LABEL_119;
    v55 = 384;
    if ( j[1] )
    {
      v41 = *(_QWORD *)v53;
      if ( v57 )
      {
        DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, struct IFileOperation *, _QWORD))(v41 + 56))(
                           v53,
                           *j,
                           v57,
                           0);
        if ( DefragListFile < 0 )
        {
          v56 = 391;
          goto LABEL_149;
        }
        v55 = 391;
      }
      else
      {
        DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, _QWORD, struct IFileOperation **))(v41 + 56))(
                           v53,
                           *j,
                           0,
                           &v57);
        v29 = 395;
        if ( DefragListFile < 0 )
          goto LABEL_119;
        v55 = 395;
      }
      DefragListFile = ((__int64 (__fastcall *)(struct IFileOperation *, struct IVolume *))v57->lpVtbl->DeleteItem)(
                         v57,
                         v53);
      v29 = 399;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 399;
      DefragListFile = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v68 + 32LL))(v68, *j);
      v29 = 402;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 402;
      DefragListFile = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 32LL))(v67, *j);
      v29 = 403;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 403;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_5c97b034d65533668c1189a6944eb349_Traceguids);
      }
      DefragListFile = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD))(*(_QWORD *)v53 + 152LL))(v53, *j);
      v29 = 406;
      if ( DefragListFile < 0 )
        goto LABEL_119;
      v55 = 406;
    }
  }
  DefragListFile = CalculateAggregateStatistics(v8, v58);
  v29 = 413;
  if ( DefragListFile < 0 )
    goto LABEL_119;
  v55 = 413;
  DefragListFile = CDefragOperation::_SetPercentComplete(this, 0x64u);
  v29 = 415;
  if ( DefragListFile < 0 )
    goto LABEL_119;
  v55 = 415;
  if ( v70 )
  {
    v42 = *((_QWORD *)this + 6);
    v80 = SystemTime;
    (*(void (__fastcall **)(__int64, _SYSTEMTIME *))(*(_QWORD *)v42 + 80LL))(v42, &v80);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 112LL))(*((_QWORD *)this + 6), *v8);
  }
  DefragListFile = 0;
LABEL_149:
  while ( v24 )
  {
    v43 = v24;
    v24 = (unsigned int *)*((_QWORD *)v24 + 1);
    CoTaskMemFree(v43);
  }
LABEL_150:
  CoTaskMemFree(v2);
  v44 = DefragListFile;
  v45 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(struct IFileOperation *))v47->lpVtbl->Release)(v47);
  }
  v48 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v51 + 16LL))(v51);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DefragListFile);
  return v44;
}

```

## disassembly

```asm
0x18002b840  push    rbp
0x18002b842  push    rbx
0x18002b843  push    rsi
0x18002b844  push    rdi
0x18002b845  push    r12
0x18002b847  push    r13
0x18002b849  push    r14
0x18002b84b  push    r15
0x18002b84d  lea     rbp, [rsp-58h]
0x18002b852  sub     rsp, 158h
0x18002b859  mov     rax, cs:__security_cookie
0x18002b860  xor     rax, rsp
0x18002b863  mov     [rbp+90h+var_50], rax
0x18002b867  mov     rbx, rcx
0x18002b86a  mov     r14d, 1
0x18002b870  mov     r9d, r14d; unsigned __int16
0x18002b873  lea     r8d, [r14+30h]; unsigned __int16
0x18002b877  lea     rdx, aCrundefragsimp; "CRunDefragSimple::RunOperation"
0x18002b87e  lea     rcx, [rsp+190h+var_138]; this
0x18002b883  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002b888  nop
0x18002b889  xor     esi, esi
0x18002b88b  mov     [rsp+190h+var_140], rsi
0x18002b890  mov     [rbp+90h+var_E8], rsi
0x18002b894  mov     [rbp+90h+var_C0], rsi
0x18002b898  mov     [rbp+90h+var_C8], rsi
0x18002b89c  mov     [rbp+90h+var_9C], esi
0x18002b89f  mov     [rbp+90h+var_EC], esi
0x18002b8a2  mov     [rbp+90h+var_100], rsi
0x18002b8a6  mov     [rbp+90h+var_F8], rsi
0x18002b8aa  mov     [rbp+90h+var_98], rsi
0x18002b8ae  mov     [rbp+90h+ThreadInformation], 2
0x18002b8b5  mov     [rbp+90h+var_D4], esi
0x18002b8b8  mov     [rbp+90h+var_D0], esi
0x18002b8bb  mov     [rbp+90h+var_A0], esi
0x18002b8be  mov     [rbp+90h+var_A4], esi
0x18002b8c1  mov     [rbp+90h+var_D8], esi
0x18002b8c4  mov     [rbp+90h+var_A8], esi
0x18002b8c7  mov     [rbp+90h+var_B0], rsi
0x18002b8cb  mov     [rbp+90h+var_E0], rsi
0x18002b8cf  mov     [rbp+90h+var_CC], esi
0x18002b8d2  xorps   xmm0, xmm0
0x18002b8d5  movups  xmmword ptr [rbp+90h+SystemTime.wYear], xmm0
0x18002b8d9  mov     [rbp+90h+var_B8], esi
0x18002b8dc  mov     r12d, esi
0x18002b8df  mov     [rbp+90h+UnbiasedTime], rsi
0x18002b8e3  mov     [rbp+90h+var_90], rsi
0x18002b8e7  mov     rdi, [rbx+2E8h]
0x18002b8ee  lea     r15d, [r14+63h]
0x18002b8f2  lea     r13d, [r14+7Fh]
0x18002b8f6  test    rdi, rdi
0x18002b8f9  jnz     loc_18002BA81
0x18002b8ff  lea     rdx, [rsp+190h+var_140]; struct IVolume **
0x18002b904  mov     rcx, rbx; this
0x18002b907  call    ?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z; CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)
0x18002b90c  mov     [rsp+190h+var_138], eax
0x18002b910  test    eax, eax
0x18002b912  jns     short loc_18002B91F
0x18002b914  mov     [rsp+190h+var_132], r15w
0x18002b91a  jmp     loc_18002C586
0x18002b91f  mov     [rsp+190h+var_134], r15w
0x18002b925  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x18002b929  call    cs:__imp_GetLocalTime
0x18002b92f  cmp     [rbx+300h], esi
0x18002b935  jnz     short loc_18002B958
0x18002b937  mov     rcx, [rsp+190h+var_140]
0x18002b93c  mov     rax, [rcx]
0x18002b93f  mov     rax, [rax+168h]
0x18002b946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b94b  mov     [rsp+190h+var_138], eax
0x18002b94f  test    eax, eax
0x18002b951  mov     eax, 6Eh ; 'n'
0x18002b956  jmp     short loc_18002B977
0x18002b958  mov     r8, [rbx+2F8h]; unsigned __int16 *
0x18002b95f  mov     rdx, [rsp+190h+var_140]; struct IVolume *
0x18002b964  mov     rcx, rbx; this
0x18002b967  call    ?_ReadDefragListFile@CDefragOperation@@IEAAJPEAUIVolume@@PEAG@Z; CDefragOperation::_ReadDefragListFile(IVolume *,ushort *)
0x18002b96c  mov     [rsp+190h+var_138], eax
0x18002b970  test    eax, eax
0x18002b972  mov     eax, 6Ah ; 'j'
0x18002b977  jns     short loc_18002B983
0x18002b979  mov     [rsp+190h+var_132], ax
0x18002b97e  jmp     loc_18002C586
0x18002b983  mov     [rsp+190h+var_134], ax
0x18002b988  mov     edx, r14d
0x18002b98b  mov     rcx, rbx
0x18002b98e  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18002b993  mov     [rsp+190h+var_138], eax
0x18002b997  test    eax, eax
0x18002b999  mov     eax, 74h ; 't'
0x18002b99e  js      short loc_18002B979
0x18002b9a0  mov     [rsp+190h+var_134], ax
0x18002b9a5  mov     rcx, [rbp+90h+var_E0]
0x18002b9a9  test    rcx, rcx
0x18002b9ac  jz      short loc_18002B9BF
0x18002b9ae  mov     [rbp+90h+var_E0], rsi
0x18002b9b2  mov     rax, [rcx]
0x18002b9b5  mov     rax, [rax+10h]
0x18002b9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9be  nop
0x18002b9bf  mov     [rsp+190h+var_150], rsi; unsigned __int16 *
0x18002b9c4  mov     [rsp+190h+var_158], rsi; unsigned __int64 *
0x18002b9c9  mov     [rsp+190h+var_160], rsi; unsigned __int64 *
0x18002b9ce  mov     [rsp+190h+var_168], rsi; struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *
0x18002b9d3  lea     rax, [rbp+90h+var_E0]
0x18002b9d7  mov     [rsp+190h+var_170], rax; struct IRunnableThread **
0x18002b9dc  mov     r9, [rsp+190h+var_140]; struct IVolume *
0x18002b9e1  mov     r8d, [rbx+308h]; int
0x18002b9e8  xor     edx, edx; int
0x18002b9ea  xor     ecx, ecx; int
0x18002b9ec  call    ?CreateInstance@CRunAnalysis@@SAJHHHPEAUIVolume@@PEAPEAUIRunnableThread@@PEAU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@PEA_K3PEAG@Z; CRunAnalysis::CreateInstance(int,int,int,IVolume *,IRunnableThread * *,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *,unsigned __int64 *,unsigned __int64 *,ushort *)
0x18002b9f1  mov     [rsp+190h+var_138], eax
0x18002b9f5  test    eax, eax
0x18002b9f7  mov     eax, 77h ; 'w'
0x18002b9fc  js      loc_18002B979
0x18002ba02  mov     [rsp+190h+var_134], ax
0x18002ba07  mov     rcx, [rbp+90h+var_E0]
0x18002ba0b  mov     rax, [rcx]
0x18002ba0e  mov     rdx, [rbx+28h]
0x18002ba12  mov     rax, [rax+18h]
0x18002ba16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba1b  mov     [rsp+190h+var_138], eax
0x18002ba1f  test    eax, eax
0x18002ba21  mov     eax, 7Ah ; 'z'
0x18002ba26  js      loc_18002B979
0x18002ba2c  mov     [rsp+190h+var_134], ax
0x18002ba31  mov     rcx, [rbp+90h+var_E0]
0x18002ba35  test    rcx, rcx
0x18002ba38  jz      short loc_18002BA4B
0x18002ba3a  mov     [rbp+90h+var_E0], rsi
0x18002ba3e  mov     rax, [rcx]
0x18002ba41  mov     rax, [rax+10h]
0x18002ba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba4a  nop
0x18002ba4b  mov     rcx, [rbx+30h]
0x18002ba4f  lea     r15, [rbx+38h]
0x18002ba53  mov     rax, [rcx]
0x18002ba56  mov     rdx, r15
0x18002ba59  mov     rax, [rax+18h]
0x18002ba5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba62  mov     [rsp+190h+var_138], eax
0x18002ba66  test    eax, eax
0x18002ba68  jns     short loc_18002BA75
0x18002ba6a  mov     [rsp+190h+var_132], r13w
0x18002ba70  jmp     loc_18002C586
0x18002ba75  mov     [rbp+90h+var_B4], r14d
0x18002ba79  mov     [rsp+190h+var_134], r13w
0x18002ba7f  jmp     short loc_18002BAB9
0x18002ba81  mov     [rbp+90h+var_B4], esi
0x18002ba84  mov     rax, [rdi]
0x18002ba87  mov     rcx, rdi
0x18002ba8a  mov     rax, [rax+8]
0x18002ba8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba93  nop
0x18002ba94  mov     rcx, [rsp+190h+var_140]
0x18002ba99  test    rcx, rcx
0x18002ba9c  jz      short loc_18002BAB0
0x18002ba9e  mov     [rsp+190h+var_140], rsi
0x18002baa3  mov     rax, [rcx]
0x18002baa6  mov     rax, [rax+10h]
0x18002baaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baaf  nop
0x18002bab0  mov     [rsp+190h+var_140], rdi
0x18002bab5  lea     r15, [rbx+38h]
0x18002bab9  mov     edx, 3
0x18002babe  mov     rcx, rbx
0x18002bac1  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18002bac6  mov     [rsp+190h+var_138], eax
0x18002baca  test    eax, eax
0x18002bacc  mov     eax, 88h
0x18002bad1  js      loc_18002B979
0x18002bad7  mov     [rsp+190h+var_134], ax
0x18002badc  mov     rax, [r15+48h]
0x18002bae0  mov     qword ptr [rbp+90h+var_70], rax
0x18002bae4  mov     rcx, [rsp+190h+var_140]
0x18002bae9  mov     rax, [rcx]
0x18002baec  mov     rax, [rax+0E0h]
0x18002baf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baf8  test    eax, eax
0x18002bafa  js      loc_18002BD63
0x18002bb00  mov     rcx, [rbp+90h+var_F8]
0x18002bb04  test    rcx, rcx
0x18002bb07  jz      short loc_18002BB1A
0x18002bb09  mov     [rbp+90h+var_F8], rsi
0x18002bb0d  mov     rax, [rcx]
0x18002bb10  mov     rax, [rax+10h]
0x18002bb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb19  nop
0x18002bb1a  lea     r9, [rbp+90h+var_F8]; struct IFreeSpaceManager **
0x18002bb1e  mov     r8d, [rbx+98h]; unsigned int
0x18002bb25  mov     rdx, [rbx+90h]; unsigned __int64
0x18002bb2c  mov     rcx, [rbx+2B8h]; unsigned __int16 *
0x18002bb33  call    ?CreateInstance@CTieredFreeSpaceManager@@SAJPEAG_KKPEAPEAUIFreeSpaceManager@@@Z; CTieredFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,ulong,IFreeSpaceManager * *)
0x18002bb38  mov     [rsp+190h+var_138], eax
0x18002bb3c  test    eax, eax
0x18002bb3e  mov     eax, 95h
0x18002bb43  js      loc_18002B979
0x18002bb49  mov     [rsp+190h+var_134], ax
0x18002bb4e  mov     rdi, [rsp+190h+var_140]
0x18002bb53  mov     rax, [rdi]
0x18002bb56  mov     rsi, [rax+68h]
0x18002bb5a  mov     rcx, [rbp+90h+var_E8]
0x18002bb5e  test    rcx, rcx
0x18002bb61  jz      short loc_18002BB78
0x18002bb63  mov     [rbp+90h+var_E8], 0
0x18002bb6b  mov     rax, [rcx]
0x18002bb6e  mov     rax, [rax+10h]
0x18002bb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb77  nop
0x18002bb78  lea     r8, [rbp+90h+var_E8]
0x18002bb7c  mov     edx, r14d
0x18002bb7f  mov     rcx, rdi
0x18002bb82  mov     rax, rsi
0x18002bb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb8a  mov     [rsp+190h+var_138], eax
0x18002bb8e  xor     esi, esi
0x18002bb90  test    eax, eax
0x18002bb92  mov     eax, 9Dh
0x18002bb97  js      loc_18002B979
0x18002bb9d  mov     [rsp+190h+var_134], ax
0x18002bba2  mov     rdi, [rsp+190h+var_140]
0x18002bba7  mov     rax, [rdi]
0x18002bbaa  mov     rsi, [rax+68h]
0x18002bbae  mov     rcx, [rbp+90h+var_C8]
0x18002bbb2  test    rcx, rcx
0x18002bbb5  jz      short loc_18002BBCC
0x18002bbb7  mov     [rbp+90h+var_C8], 0
0x18002bbbf  mov     rax, [rcx]
0x18002bbc2  mov     rax, [rax+10h]
0x18002bbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbcb  nop
0x18002bbcc  lea     r8, [rbp+90h+var_C8]
0x18002bbd0  mov     edx, 2
0x18002bbd5  mov     rcx, rdi
0x18002bbd8  mov     rax, rsi
0x18002bbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbe0  mov     [rsp+190h+var_138], eax
0x18002bbe4  xor     esi, esi
0x18002bbe6  test    eax, eax
0x18002bbe8  mov     eax, 9Eh
0x18002bbed  js      loc_18002B979
0x18002bbf3  mov     [rsp+190h+var_134], ax
0x18002bbf8  mov     rdi, [rsp+190h+var_140]
0x18002bbfd  mov     rax, [rdi]
0x18002bc00  mov     rsi, [rax+68h]
0x18002bc04  mov     rcx, [rbp+90h+var_C0]
0x18002bc08  test    rcx, rcx
0x18002bc0b  jz      short loc_18002BC22
0x18002bc0d  mov     [rbp+90h+var_C0], 0
0x18002bc15  mov     rax, [rcx]
0x18002bc18  mov     rax, [rax+10h]
0x18002bc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc21  nop
0x18002bc22  lea     r8, [rbp+90h+var_C0]
0x18002bc26  xor     edx, edx
0x18002bc28  mov     rcx, rdi
0x18002bc2b  mov     rax, rsi
0x18002bc2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc33  mov     [rsp+190h+var_138], eax
0x18002bc37  xor     esi, esi
0x18002bc39  test    eax, eax
0x18002bc3b  mov     eax, 9Fh
0x18002bc40  js      loc_18002B979
0x18002bc46  mov     [rsp+190h+var_134], ax
0x18002bc4b  mov     rcx, [rsp+190h+var_140]
0x18002bc50  mov     rax, [rcx]
0x18002bc53  lea     rdx, [rbp+90h+var_A8]
0x18002bc57  mov     [rsp+190h+var_170], rdx
0x18002bc5c  lea     r9, [rbp+90h+var_D8]
0x18002bc60  lea     r8, [rbp+90h+var_A4]
0x18002bc64  lea     rdx, [rbp+90h+var_A0]
0x18002bc68  mov     rax, [rax+0C0h]
0x18002bc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc74  mov     [rsp+190h+var_138], eax
0x18002bc78  test    eax, eax
0x18002bc7a  mov     eax, 0A2h
0x18002bc7f  js      loc_18002B979
0x18002bc85  mov     [rsp+190h+var_134], ax
0x18002bc8a  cmp     [rbp+90h+var_D8], esi
0x18002bc8d  jz      short loc_18002BCCF
0x18002bc8f  mov     rcx, [rbp+90h+var_F8]
0x18002bc93  mov     rax, [rbx+0B0h]
0x18002bc9a  mov     [rbp+90h+var_80], rax
0x18002bc9e  mov     rax, [rbx+0A8h]
0x18002bca5  mov     [rbp+90h+var_78], rax
0x18002bca9  mov     rax, [rcx]
0x18002bcac  lea     rdx, [rbp+90h+var_80]
0x18002bcb0  mov     rax, [rax+30h]
0x18002bcb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb9  mov     [rsp+190h+var_138], eax
0x18002bcbd  test    eax, eax
0x18002bcbf  mov     eax, 0A9h
0x18002bcc4  js      loc_18002B979
0x18002bcca  mov     [rsp+190h+var_134], ax
0x18002bccf  mov     [rbx+2E4h], esi
0x18002bcd5  mov     rcx, [rbp+90h+var_E8]
0x18002bcd9  mov     rax, [rcx]
0x18002bcdc  lea     rdx, [rbp+90h+var_9C]
0x18002bce0  mov     rax, [rax+40h]
0x18002bce4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
