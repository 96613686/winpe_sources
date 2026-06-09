# PlaiReadMetadata(ushort *,int,IDataCollectorSet *)

- ea: `0x18005cbcc`
- end: `0x18005d9f7`
- name: `?PlaiReadMetadata@@YAJPEAGHPEAUIDataCollectorSet@@@Z`
- size: `3627`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, struct IDataCollectorSet *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002eab0`
- `0x18012a080`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x18003f304`
- `0x18005cbcc`
- `0x180113c60`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!rand` at `0x18005d00c`
- `msvcrt!rand` at `0x18005d00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d90e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d90e`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18005d92b`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18005d92b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005d02d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005d02d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cc3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cc3e`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18005d904`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18005d904`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18005cf35`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18005cf35`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18005cc4b`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18005cc4b`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18005cffe`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18005d060`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18005cffe`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18005d060`

## string_xrefs

- `0x18005cce4`: `PlaiReadMetadata`
- `0x18005d74d`: `PlaiReadMetadata`
- `0x18005d8ba`: `PlaiReadMetadata`

## pseudocode

```c
__int64 __fastcall PlaiReadMetadata(unsigned __int16 *a1, int a2, struct IDataCollectorSet *a3)
{
  HANDLE CurrentProcess; // rax
  __int64 v7; // rax
  _QWORD *v9; // r15
  _DWORD *v10; // r13
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rax
  SIZE_T *v14; // rcx
  SIZE_T *p_dwBytes; // r9
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  DWORD LastError; // eax
  int v20; // eax
  __int64 v21; // rax
  WCHAR *v22; // rsi
  int v23; // ebx
  DWORD CurrentThreadId; // eax
  HRESULT v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  ULONG v35; // edx
  ULONG v36; // r8d
  __int64 v37; // rdx
  ULONG v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  ULONG v47; // r14d
  __int64 v48; // rax
  int v49; // eax
  int v50; // eax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  DWORD v55; // eax
  int v56; // eax
  int pStgOptions; // [rsp+20h] [rbp-E0h]
  int pStgOptionsa; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+70h] [rbp-90h] BYREF
  SIZE_T dwBytes; // [rsp+78h] [rbp-88h] BYREF
  ULONG cVariants; // [rsp+80h] [rbp-80h] BYREF
  int v62; // [rsp+88h] [rbp-78h] BYREF
  WINBOOL Wow64Process; // [rsp+90h] [rbp-70h] BYREF
  void *ppObjectOpen; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v65; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR *pwcsName; // [rsp+B8h] [rbp-48h] BYREF
  PVOID OldValue; // [rsp+C0h] [rbp-40h] BYREF
  struct tagVARIANT v70; // [rsp+C8h] [rbp-38h] BYREF
  struct tagVARIANT v71; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v72[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v73[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v74[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v75[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v76[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v77[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v78[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v79[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v80[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v81[64]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v82[64]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int16 v83[64]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v84[64]; // [rsp+700h] [rbp+600h] BYREF
  unsigned __int16 v85[64]; // [rsp+780h] [rbp+680h] BYREF
  unsigned __int16 v86[64]; // [rsp+800h] [rbp+700h] BYREF
  unsigned __int16 v87[64]; // [rsp+880h] [rbp+780h] BYREF
  unsigned __int16 v88[64]; // [rsp+900h] [rbp+800h] BYREF

  Wow64Process = 0;
  OldValue = 0;
  v67 = 0;
  ppObjectOpen = 0;
  v65 = 0;
  v66 = 0;
  pwcsName = 0;
  memset(&v70, 0, sizeof(v70));
  PlaiVariantInit(&v70);
  cVariants = 0;
  CurrentProcess = GetCurrentProcess();
  v62 = 0;
  if ( !IsWow64Process(CurrentProcess, &Wow64Process) )
  {
    v59 = -2147418113;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v72, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v72[v7] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v59, 4, byte_180147320, 1, &v62, 4);
    }
    return 2147549183LL;
  }
  v9 = 0;
  v10 = 0;
  v11 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, __int64 **))a3->lpVtbl->get_DataCollectors)(a3, &v65);
  v12 = v11;
  if ( v11 < 0 )
  {
    LODWORD(dwBytes) = v11;
    v59 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v73, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v73[v13] );
      v14 = (SIZE_T *)&v59;
      p_dwBytes = &dwBytes;
      goto LABEL_126;
    }
LABEL_127:
    if ( v12 == -2147287007 )
      v12 = -2147024863;
    goto LABEL_141;
  }
  v12 = (*(__int64 (__fastcall **)(__int64 *, ULONG *))(*v65 + 56))(v65, &cVariants);
  if ( v12 < 0 )
  {
    v59 = v12;
    LODWORD(dwBytes) = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_127;
    }
    PlaiWhoAmI(v74, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v74[v16] );
    goto LABEL_125;
  }
  if ( !g_isTaskSchedulerUseXMLStoreEnabled )
    goto LABEL_24;
  v17 = PlaiCreateCollectorSetPath(a1, a2, &pwcsName);
  v12 = v17;
  if ( v17 < 0 )
  {
    LODWORD(dwBytes) = 0;
    v59 = v17;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_127;
    }
    PlaiWhoAmI(v75, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v75[v18] );
    goto LABEL_125;
  }
  if ( Wow64Process )
  {
    if ( !Wow64DisableWow64FsRedirection(&OldValue) )
    {
      LastError = GetLastError();
      v20 = PlaiHResultFromWin32(LastError);
      v12 = v20;
      if ( v20 < 0 )
      {
        LODWORD(dwBytes) = 0;
        v59 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_127;
        }
        PlaiWhoAmI(v76, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v76[v21] );
        goto LABEL_125;
      }
    }
    v62 = 1;
  }
  v22 = pwcsName;
  if ( StgOpenStorageEx(pwcsName, 0x20u, 3u, 0, 0, 0, &IID_IPropertySetStorage, &ppObjectOpen) < 0 )
  {
    v23 = rand();
    CurrentThreadId = GetCurrentThreadId();
    Sleep((CurrentThreadId ^ v23) % 0x64);
    v25 = StgOpenStorageEx(v22, 0x20u, 3u, 0, 0, 0, &IID_IPropertySetStorage, &ppObjectOpen);
    v12 = v25;
    if ( v25 < 0 )
    {
      LODWORD(dwBytes) = 0;
      v59 = v25;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_127;
      }
      PlaiWhoAmI(v77, 0x4000000000000800uLL);
      v26 = -1;
      do
        ++v26;
      while ( v77[v26] );
      goto LABEL_125;
    }
  }
  if ( (*(int (__fastcall **)(void *, GUID *, __int64, __int64 *))(*(_QWORD *)ppObjectOpen + 32LL))(
         ppObjectOpen,
         &FMTID_PlaDcsInfo,
         16,
         &v67) < 0 )
  {
LABEL_24:
    v12 = 0;
    goto LABEL_141;
  }
  v27 = cVariants + 2LL;
  if ( v27 < cVariants )
  {
    v12 = -2147024362;
    v59 = -2147024362;
    LODWORD(dwBytes) = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_141;
    }
    PlaiWhoAmI(v88, 0x4000000000000800uLL);
    v54 = -1;
    do
      ++v54;
    while ( v88[v54] );
  }
  else
  {
    dwBytes = cVariants + 2LL;
    v28 = ULongLongMult(v27, 0x10u, &dwBytes);
    v12 = v28;
    if ( v28 < 0 )
    {
      LODWORD(dwBytes) = 0;
      v59 = v28;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_127;
      }
      PlaiWhoAmI(v78, 0x4000000000000800uLL);
      v29 = -1;
      do
        ++v29;
      while ( v78[v29] );
      goto LABEL_125;
    }
    v10 = PlaiAlloc(dwBytes, 1, 0, byte_180147320, pStgOptions);
    if ( !v10 )
    {
      v12 = -2147024882;
      v59 = -2147024882;
      LODWORD(dwBytes) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v79, 0x4000000000000800uLL);
      v30 = -1;
      do
        ++v30;
      while ( v79[v30] );
      goto LABEL_140;
    }
    v31 = cVariants + 2LL;
    if ( v31 < cVariants )
    {
      v12 = -2147024362;
      v59 = -2147024362;
      LODWORD(dwBytes) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v87, 0x4000000000000800uLL);
      v53 = -1;
      do
        ++v53;
      while ( v87[v53] );
    }
    else
    {
      dwBytes = cVariants + 2LL;
      v32 = ULongLongMult(v31, 0x18u, &dwBytes);
      v12 = v32;
      if ( v32 < 0 )
      {
        LODWORD(dwBytes) = 0;
        v59 = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_127;
        }
        PlaiWhoAmI(v80, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v80[v33] );
        goto LABEL_125;
      }
      v9 = PlaiAlloc(dwBytes, 1, 0, byte_180147320, pStgOptionsa);
      if ( v9 )
      {
        v35 = cVariants;
        v36 = 0;
        if ( cVariants != -2 )
        {
          do
          {
            v37 = v36;
            v38 = v36 + 2;
            v39 = 2LL * v36++;
            v10[2 * v39 + 2] = v38;
            v40 = 3 * v37;
            v10[2 * v39] = 1;
            *(_OWORD *)&v9[v40] = 0;
            v9[v40 + 2] = 0;
            v35 = cVariants;
          }
          while ( v36 < cVariants + 2 );
        }
        v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, _QWORD *))(*(_QWORD *)v67 + 24LL))(
                v67,
                v35 + 2,
                v10,
                v9);
        v12 = v41;
        if ( v41 >= 0 )
        {
          if ( *(_WORD *)v9 == 19
            && (v43 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a3->lpVtbl->put_SerialNumber)(
                        a3,
                        *((unsigned int *)v9 + 2)),
                v12 = v43,
                v43 < 0) )
          {
            LODWORD(dwBytes) = 0;
            v59 = v43;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_127;
            }
            PlaiWhoAmI(v83, 0x4000000000000800uLL);
            v44 = -1;
            do
              ++v44;
            while ( v83[v44] );
          }
          else
          {
            if ( *((_WORD *)v9 + 12) != 8
              || (v45 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, _QWORD))a3->lpVtbl->put_LatestOutputLocation)(
                          a3,
                          v9[4]),
                  v12 = v45,
                  v45 >= 0) )
            {
              PlaiVariantClear(&v70);
              v47 = 0;
              v70.vt = 19;
              while ( v47 < cVariants )
              {
                if ( LOWORD(v9[3 * v47 + 6]) == 8 )
                {
                  v70.lVal = v47;
                  if ( v66 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                    v66 = 0;
                  }
                  v48 = *v65;
                  v71 = v70;
                  v49 = (*(__int64 (__fastcall **)(__int64 *, struct tagVARIANT *, __int64 *))(v48 + 64))(
                          v65,
                          &v71,
                          &v66);
                  v12 = v49;
                  if ( v49 < 0 )
                  {
                    v59 = v49;
                    LODWORD(dwBytes) = 0;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v86, 0x4000000000000800uLL);
                      v52 = -1;
                      do
                        ++v52;
                      while ( v86[v52] );
                      goto LABEL_125;
                    }
                    goto LABEL_127;
                  }
                  v50 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v66 + 136LL))(v66, v9[3 * v47 + 7]);
                  v12 = v50;
                  if ( v50 < 0 )
                  {
                    LODWORD(dwBytes) = 0;
                    v59 = v50;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v85, 0x4000000000000800uLL);
                      v51 = -1;
                      do
                        ++v51;
                      while ( v85[v51] );
                      goto LABEL_125;
                    }
                    goto LABEL_127;
                  }
                }
                ++v47;
              }
              goto LABEL_127;
            }
            LODWORD(dwBytes) = 0;
            v59 = v45;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_127;
            }
            PlaiWhoAmI(v84, 0x4000000000000800uLL);
            v46 = -1;
            do
              ++v46;
            while ( v84[v46] );
          }
        }
        else
        {
          LODWORD(dwBytes) = 0;
          v59 = v41;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_127;
          }
          PlaiWhoAmI(v82, 0x4000000000000800uLL);
          v42 = -1;
          do
            ++v42;
          while ( v82[v42] );
        }
LABEL_125:
        p_dwBytes = (SIZE_T *)&v59;
        v14 = &dwBytes;
LABEL_126:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, p_dwBytes, 4, byte_180147320, 1, v14, 4);
        goto LABEL_127;
      }
      v12 = -2147024882;
      v59 = -2147024882;
      LODWORD(dwBytes) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_141;
      }
      PlaiWhoAmI(v81, 0x4000000000000800uLL);
      v34 = -1;
      do
        ++v34;
      while ( v81[v34] );
    }
  }
LABEL_140:
  EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v59, 4, byte_180147320, 1, &dwBytes, 4);
LABEL_141:
  if ( Wow64Process )
  {
    if ( v62 )
    {
      if ( !Wow64RevertWow64FsRedirection(OldValue) )
      {
        v55 = GetLastError();
        v56 = PlaiHResultFromWin32(v55);
        if ( v56 < 0 )
          v12 = v56;
      }
    }
  }
  if ( v9 )
    FreePropVariantArray(cVariants, (PROPVARIANT *)v9);
  PlaiVariantClear(&v70);
  if ( pwcsName )
    PlaiFree(pwcsName, 1);
  if ( v10 )
    PlaiFree(v10, 1);
  if ( v9 )
    PlaiFree(v9, 1);
  if ( ppObjectOpen )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObjectOpen + 16LL))(ppObjectOpen);
    ppObjectOpen = 0;
  }
  if ( v67 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    v67 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64 *))(*v65 + 16))(v65);
    v65 = 0;
  }
  if ( v66 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005cbcc  mov     [rsp-8+arg_18], rbx
0x18005cbd1  push    rbp
0x18005cbd2  push    rsi
0x18005cbd3  push    rdi
0x18005cbd4  push    r12
0x18005cbd6  push    r13
0x18005cbd8  push    r14
0x18005cbda  push    r15
0x18005cbdc  lea     rbp, [rsp-890h]
0x18005cbe4  sub     rsp, 990h
0x18005cbeb  mov     rax, cs:__security_cookie
0x18005cbf2  xor     rax, rsp
0x18005cbf5  mov     [rbp+8C0h+var_40], rax
0x18005cbfc  xor     ebx, ebx
0x18005cbfe  mov     rsi, rcx
0x18005cc01  xorps   xmm0, xmm0
0x18005cc04  mov     [rbp+8C0h+Wow64Process], ebx
0x18005cc07  xor     eax, eax
0x18005cc09  mov     [rbp+8C0h+cVariants], ebx
0x18005cc0c  lea     rcx, [rbp+8C0h+var_8F8]; struct tagVARIANT *
0x18005cc10  mov     [rbp+8C0h+OldValue], rbx
0x18005cc14  mov     [rbp+8C0h+var_910], rbx
0x18005cc18  mov     r14, r8
0x18005cc1b  mov     [rbp+8C0h+var_928], rbx
0x18005cc1f  mov     r12d, edx
0x18005cc22  mov     [rbp+8C0h+var_920], rbx
0x18005cc26  mov     [rbp+8C0h+var_918], rbx
0x18005cc2a  mov     [rbp+8C0h+pwcsName], rbx
0x18005cc2e  movups  xmmword ptr [rbp+8C0h+var_8F8], xmm0
0x18005cc32  mov     qword ptr [rbp+8C0h+var_8F8+10h], rax
0x18005cc36  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x18005cc3b  mov     [rbp+8C0h+cVariants], ebx
0x18005cc3e  call    cs:__imp_GetCurrentProcess
0x18005cc44  mov     rcx, rax; hProcess
0x18005cc47  lea     rdx, [rbp+8C0h+Wow64Process]; Wow64Process
0x18005cc4b  call    cs:__imp_IsWow64Process
0x18005cc51  mov     [rbp+8C0h+var_938], ebx
0x18005cc54  test    eax, eax
0x18005cc56  jnz     loc_18005CD35
0x18005cc5c  cmp     dword ptr cs:xmmword_180169738, ebx
0x18005cc62  mov     r14d, 8000FFFFh
0x18005cc68  mov     [rsp+9C0h+var_950], r14d
0x18005cc6d  jz      loc_18005CD2D
0x18005cc73  mov     rdx, 4000000000000800h; unsigned __int64
0x18005cc7d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005cc84  jz      loc_18005CD2D
0x18005cc8a  mov     rax, cs:qword_180169748
0x18005cc91  and     rax, rdx
0x18005cc94  cmp     cs:qword_180169748, rax
0x18005cc9b  jnz     loc_18005CD2D
0x18005cca1  lea     rcx, [rbp+8C0h+var_8C0]; unsigned __int16 *
0x18005cca5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005ccaa  lea     rcx, [rbp+8C0h+var_8C0]
0x18005ccae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005ccb2  inc     rax
0x18005ccb5  cmp     [rcx+rax*2], bx
0x18005ccb9  jnz     short loc_18005CCB2
0x18005ccbb  lea     ecx, [rax+rax]
0x18005ccbe  add     rcx, 2
0x18005ccc2  lea     rax, [rbp+8C0h+var_8C0]
0x18005ccc6  mov     [rsp+9C0h+var_960], rcx
0x18005cccb  lea     rsi, byte_180147320
0x18005ccd2  mov     [rsp+9C0h+var_968], rax
0x18005ccd7  lea     rcx, [rbp+8C0h+var_938]
0x18005ccdb  mov     [rsp+9C0h+var_970], 11h
0x18005cce4  lea     rax, aPlaireadmetada; "PlaiReadMetadata"
0x18005cceb  mov     [rsp+9C0h+var_978], rax
0x18005ccf0  lea     r9, [rsp+9C0h+var_950]
0x18005ccf5  mov     eax, 4
0x18005ccfa  lea     rdx, PLA_EVENT_ERROR
0x18005cd01  mov     [rsp+9C0h+var_980], rax
0x18005cd06  mov     [rsp+9C0h+ppObjectOpen], rcx
0x18005cd0b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18005cd12  lea     edi, [rax-3]
0x18005cd15  mov     [rsp+9C0h+riid], rdi
0x18005cd1a  lea     r8d, [rax+1]
0x18005cd1e  mov     [rsp+9C0h+pSecurityDescriptor], rsi
0x18005cd23  mov     [rsp+9C0h+pStgOptions], rax
0x18005cd28  call    EventingWriteEvent
0x18005cd2d  mov     eax, r14d
0x18005cd30  jmp     loc_18005D9CD
0x18005cd35  mov     rax, [r14]
0x18005cd38  lea     rdx, [rbp+8C0h+var_920]
0x18005cd3c  mov     rcx, r14
0x18005cd3f  mov     r15, rbx
0x18005cd42  mov     r13, rbx
0x18005cd45  mov     rax, [rax+38h]
0x18005cd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd4e  mov     ebx, eax
0x18005cd50  mov     edi, 1
0x18005cd55  test    eax, eax
0x18005cd57  jns     loc_18005CDEE
0x18005cd5d  xor     r12d, r12d
0x18005cd60  mov     dword ptr [rsp+9C0h+dwBytes], eax
0x18005cd64  cmp     dword ptr cs:xmmword_180169738, r12d
0x18005cd6b  mov     [rsp+9C0h+var_950], r12d
0x18005cd70  jz      loc_18005D787
0x18005cd76  mov     rdx, 4000000000000800h; unsigned __int64
0x18005cd80  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005cd87  jz      loc_18005D787
0x18005cd8d  mov     rax, cs:qword_180169748
0x18005cd94  and     rax, rdx
0x18005cd97  cmp     cs:qword_180169748, rax
0x18005cd9e  jnz     loc_18005D787
0x18005cda4  lea     rcx, [rbp+8C0h+var_840]; unsigned __int16 *
0x18005cdab  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005cdb0  lea     rcx, [rbp+8C0h+var_840]
0x18005cdb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005cdbb  inc     rax
0x18005cdbe  cmp     [rcx+rax*2], r12w
0x18005cdc3  jnz     short loc_18005CDBB
0x18005cdc5  lea     ecx, [rax+rax]
0x18005cdc8  add     rcx, 2
0x18005cdcc  lea     rax, [rbp+8C0h+var_840]
0x18005cdd3  mov     [rsp+9C0h+var_960], rcx
0x18005cdd8  lea     rsi, byte_180147320
0x18005cddf  lea     rcx, [rsp+9C0h+var_950]
0x18005cde4  lea     r9, [rsp+9C0h+dwBytes]
0x18005cde9  jmp     loc_18005D738
0x18005cdee  mov     rcx, [rbp+8C0h+var_920]
0x18005cdf2  lea     rdx, [rbp+8C0h+cVariants]
0x18005cdf6  mov     rax, [rcx]
0x18005cdf9  mov     rax, [rax+38h]
0x18005cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce02  mov     ebx, eax
0x18005ce04  xor     eax, eax
0x18005ce06  test    ebx, ebx
0x18005ce08  jns     short loc_18005CE88
0x18005ce0a  xor     r12d, r12d
0x18005ce0d  mov     [rsp+9C0h+var_950], ebx
0x18005ce11  cmp     dword ptr cs:xmmword_180169738, r12d
0x18005ce18  mov     dword ptr [rsp+9C0h+dwBytes], r12d
0x18005ce1d  jz      loc_18005D787
0x18005ce23  mov     rdx, 4000000000000800h; unsigned __int64
0x18005ce2d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005ce34  jz      loc_18005D787
0x18005ce3a  mov     rax, cs:qword_180169748
0x18005ce41  and     rax, rdx
0x18005ce44  cmp     cs:qword_180169748, rax
0x18005ce4b  jnz     loc_18005D787
0x18005ce51  lea     rcx, [rbp+8C0h+var_7C0]; unsigned __int16 *
0x18005ce58  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005ce5d  lea     rcx, [rbp+8C0h+var_7C0]
0x18005ce64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005ce68  inc     rax
0x18005ce6b  cmp     [rcx+rax*2], r12w
0x18005ce70  jnz     short loc_18005CE68
0x18005ce72  lea     ecx, [rax+rax]
0x18005ce75  lea     rax, [rbp+8C0h+var_7C0]
0x18005ce7c  lea     rsi, byte_180147320
0x18005ce83  jmp     loc_18005D725
0x18005ce88  cmp     cs:?g_isTaskSchedulerUseXMLStoreEnabled@@3_NA, al; bool g_isTaskSchedulerUseXMLStoreEnabled
0x18005ce8e  jnz     short loc_18005CE9B
0x18005ce90  xor     r12d, r12d
0x18005ce93  mov     ebx, r12d
0x18005ce96  jmp     loc_18005D8F4
0x18005ce9b  lea     r8, [rbp+8C0h+pwcsName]; unsigned __int16 **
0x18005ce9f  mov     edx, r12d; int
0x18005cea2  mov     rcx, rsi; unsigned __int16 *
0x18005cea5  call    ?PlaiCreateCollectorSetPath@@YAJPEBGHPEAPEAG@Z; PlaiCreateCollectorSetPath(ushort const *,int,ushort * *)
0x18005ceaa  xor     r12d, r12d
0x18005cead  mov     ebx, eax
0x18005ceaf  test    eax, eax
0x18005ceb1  jns     short loc_18005CF27
0x18005ceb3  cmp     dword ptr cs:xmmword_180169738, r12d
0x18005ceba  mov     dword ptr [rsp+9C0h+dwBytes], r12d
0x18005cebf  mov     [rsp+9C0h+var_950], eax
0x18005cec3  jz      loc_18005D787
0x18005cec9  mov     rdx, 4000000000000800h; unsigned __int64
0x18005ced3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005ceda  jz      loc_18005D787
0x18005cee0  mov     rax, cs:qword_180169748
0x18005cee7  and     rax, rdx
0x18005ceea  cmp     cs:qword_180169748, rax
0x18005cef1  jnz     loc_18005D787
0x18005cef7  lea     rcx, [rbp+8C0h+var_740]; unsigned __int16 *
0x18005cefe  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005cf03  lea     rcx, [rbp+8C0h+var_740]
0x18005cf0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005cf0e  inc     rax
0x18005cf11  cmp     [rcx+rax*2], r12w
0x18005cf16  jnz     short loc_18005CF0E
0x18005cf18  lea     ecx, [rax+rax]
0x18005cf1b  lea     rax, [rbp+8C0h+var_740]
0x18005cf22  jmp     loc_18005CE7C
0x18005cf27  cmp     [rbp+8C0h+Wow64Process], r12d
0x18005cf2b  jz      loc_18005CFCD
0x18005cf31  lea     rcx, [rbp+8C0h+OldValue]; OldValue
0x18005cf35  call    cs:__imp_Wow64DisableWow64FsRedirection
0x18005cf3b  test    eax, eax
0x18005cf3d  jnz     loc_18005CFCA
0x18005cf43  call    cs:__imp_GetLastError
0x18005cf49  mov     ecx, eax; unsigned int
0x18005cf4b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18005cf50  mov     ebx, eax
0x18005cf52  test    eax, eax
0x18005cf54  jns     short loc_18005CFCA
0x18005cf56  cmp     dword ptr cs:xmmword_180169738, r12d
0x18005cf5d  mov     dword ptr [rsp+9C0h+dwBytes], r12d
0x18005cf62  mov     [rsp+9C0h+var_950], eax
0x18005cf66  jz      loc_18005D787
0x18005cf6c  mov     rdx, 4000000000000800h; unsigned __int64
0x18005cf76  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005cf7d  jz      loc_18005D787
0x18005cf83  mov     rax, cs:qword_180169748
0x18005cf8a  and     rax, rdx
0x18005cf8d  cmp     cs:qword_180169748, rax
0x18005cf94  jnz     loc_18005D787
0x18005cf9a  lea     rcx, [rbp+8C0h+var_6C0]; unsigned __int16 *
0x18005cfa1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005cfa6  lea     rcx, [rbp+8C0h+var_6C0]
0x18005cfad  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005cfb1  inc     rax
0x18005cfb4  cmp     [rcx+rax*2], r12w
0x18005cfb9  jnz     short loc_18005CFB1
0x18005cfbb  lea     ecx, [rax+rax]
0x18005cfbe  lea     rax, [rbp+8C0h+var_6C0]
0x18005cfc5  jmp     loc_18005CE7C
0x18005cfca  mov     [rbp+8C0h+var_938], edi
0x18005cfcd  mov     rsi, [rbp+8C0h+pwcsName]
0x18005cfd1  lea     rax, [rbp+8C0h+var_928]
0x18005cfd5  mov     [rsp+9C0h+ppObjectOpen], rax; ppObjectOpen
0x18005cfda  xor     r9d, r9d; grfAttrs
0x18005cfdd  lea     rax, IID_IPropertySetStorage
0x18005cfe4  mov     rcx, rsi; pwcsName
0x18005cfe7  mov     [rsp+9C0h+riid], rax; riid
0x18005cfec  mov     [rsp+9C0h+pSecurityDescriptor], r12; pSecurityDescriptor
0x18005cff1  lea     edx, [r9+20h]; grfMode
0x18005cff5  mov     [rsp+9C0h+pStgOptions], r12; int
0x18005cffa  lea     r8d, [r9+3]; stgfmt
0x18005cffe  call    cs:__imp_StgOpenStorageEx
0x18005d004  test    eax, eax
0x18005d006  jns     loc_18005D0E0
0x18005d00c  call    cs:__imp_rand
0x18005d012  mov     ebx, eax
0x18005d014  call    cs:__imp_GetCurrentThreadId
0x18005d01a  xor     ebx, eax
0x18005d01c  mov     eax, 51EB851Fh
0x18005d021  mul     ebx
0x18005d023  shr     edx, 5
0x18005d026  imul    eax, edx, 64h ; 'd'
0x18005d029  sub     ebx, eax
0x18005d02b  mov     ecx, ebx; dwMilliseconds
0x18005d02d  call    cs:__imp_Sleep
0x18005d033  xor     r9d, r9d; grfAttrs
0x18005d036  lea     rax, [rbp+8C0h+var_928]
0x18005d03a  mov     [rsp+9C0h+ppObjectOpen], rax; ppObjectOpen
0x18005d03f  mov     rcx, rsi; pwcsName
0x18005d042  lea     rax, IID_IPropertySetStorage
0x18005d049  mov     [rsp+9C0h+riid], rax; riid
0x18005d04e  mov     [rsp+9C0h+pSecurityDescriptor], r12; pSecurityDescriptor
0x18005d053  lea     edx, [r9+20h]; grfMode
0x18005d057  lea     r8d, [r9+3]; stgfmt
0x18005d05b  mov     [rsp+9C0h+pStgOptions], r12; pStgOptions
0x18005d060  call    cs:__imp_StgOpenStorageEx
0x18005d066  mov     ebx, eax
0x18005d068  test    eax, eax
0x18005d06a  jns     short loc_18005D0E0
0x18005d06c  cmp     dword ptr cs:xmmword_180169738, r12d
0x18005d073  mov     dword ptr [rsp+9C0h+dwBytes], r12d
0x18005d078  mov     [rsp+9C0h+var_950], eax
0x18005d07c  jz      loc_18005D787
0x18005d082  mov     rdx, 4000000000000800h; unsigned __int64
0x18005d08c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005d093  jz      loc_18005D787
0x18005d099  mov     rax, cs:qword_180169748
0x18005d0a0  and     rax, rdx
0x18005d0a3  cmp     cs:qword_180169748, rax
0x18005d0aa  jnz     loc_18005D787
0x18005d0b0  lea     rcx, [rbp+8C0h+var_640]; unsigned __int16 *
0x18005d0b7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005d0bc  lea     rcx, [rbp+8C0h+var_640]
0x18005d0c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005d0c7  inc     rax
0x18005d0ca  cmp     [rcx+rax*2], r12w
0x18005d0cf  jnz     short loc_18005D0C7
0x18005d0d1  lea     ecx, [rax+rax]
0x18005d0d4  lea     rax, [rbp+8C0h+var_640]
0x18005d0db  jmp     loc_18005CE7C
0x18005d0e0  mov     rcx, [rbp+8C0h+var_928]
0x18005d0e4  lea     r9, [rbp+8C0h+var_910]
0x18005d0e8  mov     ebx, 10h
0x18005d0ed  lea     rdx, ?FMTID_PlaDcsInfo@@3U_GUID@@A; _GUID FMTID_PlaDcsInfo
0x18005d0f4  mov     r8d, ebx
0x18005d0f7  mov     rax, [rcx]
0x18005d0fa  mov     rax, [rax+20h]
0x18005d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d103  test    eax, eax
0x18005d105  js      loc_18005CE93
0x18005d10b  mov     eax, [rbp+8C0h+cVariants]
0x18005d10e  lea     rcx, [rax+2]; unsigned __int64
0x18005d112  cmp     rcx, rax
0x18005d115  jb      loc_18005D815
0x18005d11b  lea     r8, [rsp+9C0h+dwBytes]; unsigned __int64 *
0x18005d120  mov     [rsp+9C0h+dwBytes], rcx
0x18005d125  mov     edx, ebx; unsigned __int64
0x18005d127  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005d12c  mov     ebx, eax
0x18005d12e  test    eax, eax
0x18005d130  jns     short loc_18005D1A6
  ... truncated ...
```
