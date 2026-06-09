# PlaStartDataCollectorSet(ushort const *,ushort const *,void * *,void * *,unsigned __int64 *)

- ea: `0x1801334e8`
- end: `0x18013460e`
- name: `?PlaStartDataCollectorSet@@YAJPEBG0PEAPEAX1PEA_K@Z`
- size: `4390`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void **, void **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800be990`
- `0x180105940`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18000b01c`
- `0x180012ef0`
- `0x180018420`
- `0x18002b3a0`
- `0x18006da34`
- `0x180093874`
- `0x1800d1638`
- `0x1800dccec`
- `0x1800e8b24`
- `0x1800ea8fc`
- `0x1800eb21c`
- `0x18010d840`
- `0x1801334e8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180133c4e`
- `msvcrt!_wcsnicmp` at `0x180133c4e`
- `ntdll!EtwNotificationRegister` at `0x180134391`
- `ntdll!EtwNotificationRegister` at `0x180134391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013375a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801337fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801338a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801339e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801342eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013375a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801337fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801338a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801339e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801342eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133747`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801337ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013388d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133930`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801339d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133a76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133b19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133747`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801337ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013388d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133930`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801339d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133a76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180133b19`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801342d6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801342d6`

## pseudocode

```c
__int64 __fastcall PlaStartDataCollectorSet(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 ***a3,
        void **a4,
        unsigned __int64 *a5)
{
  __int64 v5; // rdi
  unsigned __int16 *v8; // r12
  _QWORD *v9; // rax
  int v10; // r8d
  unsigned __int16 **v11; // rsi
  int v12; // ebx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  _QWORD *v15; // rax
  unsigned __int16 *v16; // rax
  __int64 v17; // rax
  unsigned __int16 *EventW; // rax
  DWORD LastError; // eax
  __int64 v20; // rax
  unsigned __int16 *v21; // rax
  DWORD v22; // eax
  __int64 v23; // rax
  unsigned __int16 *v24; // rax
  DWORD v25; // eax
  __int64 v26; // rax
  unsigned __int16 *v27; // rax
  DWORD v28; // eax
  __int64 v29; // rax
  unsigned __int16 *v30; // rax
  DWORD v31; // eax
  __int64 v32; // rax
  unsigned __int16 *v33; // rax
  DWORD v34; // eax
  __int64 v35; // rax
  unsigned __int16 *v36; // rax
  DWORD v37; // eax
  __int64 v38; // rax
  int started; // eax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  __int64 Class; // rax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  unsigned __int64 v51; // rax
  DWORD v52; // eax
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  int v58; // eax
  __int64 v59; // rax
  unsigned __int16 *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rax
  unsigned __int16 *Thread; // rax
  DWORD v64; // eax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // r8
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  int dwCreationFlags; // [rsp+20h] [rbp-E0h]
  int v77; // [rsp+70h] [rbp-90h] BYREF
  int v78; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v79; // [rsp+80h] [rbp-80h]
  __int16 v80[2]; // [rsp+88h] [rbp-78h] BYREF
  int v81; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int64 v82; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v83; // [rsp+98h] [rbp-68h]
  __int128 v84; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v85; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v86[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v87[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v88[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v89[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v90[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v91[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v92[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v93[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v94[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v95[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v96[64]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v97[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v98[64]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v99[64]; // [rsp+740h] [rbp+640h] BYREF
  unsigned __int16 v100[64]; // [rsp+7C0h] [rbp+6C0h] BYREF
  unsigned __int16 v101[64]; // [rsp+840h] [rbp+740h] BYREF
  unsigned __int16 v102[64]; // [rsp+8C0h] [rbp+7C0h] BYREF
  unsigned __int16 v103[64]; // [rsp+940h] [rbp+840h] BYREF
  unsigned __int16 v104[64]; // [rsp+9C0h] [rbp+8C0h] BYREF
  unsigned __int16 v105[64]; // [rsp+A40h] [rbp+940h] BYREF
  unsigned __int16 v106[64]; // [rsp+AC0h] [rbp+9C0h] BYREF
  unsigned __int16 v107[64]; // [rsp+B40h] [rbp+A40h] BYREF
  unsigned __int16 v108[64]; // [rsp+BC0h] [rbp+AC0h] BYREF
  unsigned __int16 v109[64]; // [rsp+C40h] [rbp+B40h] BYREF

  v83 = a2;
  v5 = -1;
  v79 = a1;
  v82 = 0;
  v77 = 0;
  v80[0] = 0;
  v8 = a1;
  v81 = 0;
  v84 = 0;
  v85 = 0;
  if ( a1 && *a1 && a3 && a4 )
  {
    v9 = PlaiAlloc(0x98u, 1, 1, byte_180147320, dwCreationFlags);
    v11 = (unsigned __int16 **)v9;
    if ( !v9 )
    {
      v12 = -2147024882;
      v77 = 0;
      v78 = -2147024882;
      if ( (_DWORD)xmmword_180169738 )
      {
        a2 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v87, 0x4000000000000800uLL);
          v13 = -1;
          do
            ++v13;
          while ( v87[v13] );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v78, 4, byte_180147320, 1, &v77, 4);
        }
      }
      goto LABEL_171;
    }
    v14 = v79;
    v15 = v9 + 13;
    v15[1] = v15;
    *v15 = v15;
    v16 = PlaiAllocStringEx(v14, (const char *)a2, v10);
    *v11 = v16;
    if ( !v16 )
    {
      v12 = -2147024882;
      v78 = 0;
      v77 = -2147024882;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v88, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v88[v17] );
      goto LABEL_170;
    }
    EventW = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[2] = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v77 = PlaiHResultFromWin32(LastError);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v89, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v89[v20] );
      goto LABEL_170;
    }
    v21 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[4] = v21;
    if ( !v21 )
    {
      v22 = GetLastError();
      v77 = PlaiHResultFromWin32(v22);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v90, 0x4000000000000800uLL);
      v23 = -1;
      do
        ++v23;
      while ( v90[v23] );
      goto LABEL_170;
    }
    v24 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[7] = v24;
    if ( !v24 )
    {
      v25 = GetLastError();
      v77 = PlaiHResultFromWin32(v25);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v91, 0x4000000000000800uLL);
      v26 = -1;
      do
        ++v26;
      while ( v91[v26] );
      goto LABEL_170;
    }
    v27 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[8] = v27;
    if ( !v27 )
    {
      v28 = GetLastError();
      v77 = PlaiHResultFromWin32(v28);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v92, 0x4000000000000800uLL);
      v29 = -1;
      do
        ++v29;
      while ( v92[v29] );
      goto LABEL_170;
    }
    v30 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[5] = v30;
    if ( !v30 )
    {
      v31 = GetLastError();
      v77 = PlaiHResultFromWin32(v31);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v93, 0x4000000000000800uLL);
      v32 = -1;
      do
        ++v32;
      while ( v93[v32] );
      goto LABEL_170;
    }
    v33 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[6] = v33;
    if ( !v33 )
    {
      v34 = GetLastError();
      v77 = PlaiHResultFromWin32(v34);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v94, 0x4000000000000800uLL);
      v35 = -1;
      do
        ++v35;
      while ( v94[v35] );
      goto LABEL_170;
    }
    v36 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    v11[3] = v36;
    if ( !v36 )
    {
      v37 = GetLastError();
      v77 = PlaiHResultFromWin32(v37);
      v12 = v77;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v95, 0x4000000000000800uLL);
      v38 = -1;
      do
        ++v38;
      while ( v95[v38] );
      goto LABEL_170;
    }
    started = PlaiStartService(L"PLA", 0xEA60u);
    v12 = started;
    if ( started < 0 )
    {
      v77 = started;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v96, 0x4000000000000800uLL);
      v40 = -1;
      do
        ++v40;
      while ( v96[v40] );
      goto LABEL_170;
    }
    if ( _wcsnicmp(L"system\\", *v11, 7u) )
    {
      Class = CreateClassObject<SDataCollectorSet>(byte_180147320, 0);
      v11[15] = (unsigned __int16 *)Class;
      if ( !Class )
      {
        v12 = -2147024882;
        v78 = 0;
        v77 = -2147024882;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_171;
        a2 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_171;
        }
        PlaiWhoAmI(v99, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v99[v46] );
        goto LABEL_170;
      }
      v47 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)Class + 472LL))(Class, *v11, 0);
      v12 = v47;
      if ( v47 < 0 )
      {
        v77 = v47;
        v78 = 0;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_171;
        a2 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_171;
        }
        PlaiWhoAmI(v100, 0x4000000000000800uLL);
        v48 = -1;
        do
          ++v48;
        while ( v100[v48] );
        goto LABEL_170;
      }
    }
    else
    {
      v41 = CreateClassObject<SysDataCollectorSet>((char *)byte_180147320, 0);
      v11[15] = (unsigned __int16 *)v41;
      if ( !v41 )
      {
        v12 = -2147024882;
        v78 = 0;
        v77 = -2147024882;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_171;
        a2 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_171;
        }
        PlaiWhoAmI(v97, 0x4000000000000800uLL);
        v42 = -1;
        do
          ++v42;
        while ( v97[v42] );
        goto LABEL_170;
      }
      v43 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v41 + 472LL))(v41, *v11 + 7, 0);
      v12 = v43;
      if ( v43 < 0 )
      {
        v77 = v43;
        v78 = 0;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_171;
        a2 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_171;
        }
        PlaiWhoAmI(v98, 0x4000000000000800uLL);
        v44 = -1;
        do
          ++v44;
        while ( v98[v44] );
        goto LABEL_170;
      }
    }
    *(_QWORD *)&v84 = *v11;
    *((_QWORD *)&v84 + 1) = v11[2];
    *(_QWORD *)&v85 = v11[4];
    *((_QWORD *)&v85 + 1) = v11[7];
    v49 = PlaiRegisterCollectorSet((struct _SET_INSTANCE *)v11, (struct __MIDL_Registration_0002 *)&v84, &v82);
    v12 = v49;
    if ( v49 >= 0 )
    {
      v51 = v82;
      v11[9] = (unsigned __int16 *)v82;
      if ( v51 )
      {
        v54 = PlaiIncrementCollectors((struct _SET_INSTANCE *)v11, 0);
        v12 = v54;
        if ( v54 >= 0 )
        {
          v56 = PlaiCheckPolicyBeforeStart((struct IDataCollectorSet *)v11[15]);
          v12 = v56;
          if ( v56 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int16 *))(*(_QWORD *)v11[15] + 440LL))(v11[15], v80);
            v58 = 0;
            if ( v12 >= 0 )
            {
              v60 = v11[15];
              LOBYTE(v58) = v80[0] == 0xFFFF;
              *((_DWORD *)v11 + 21) = v58;
              v12 = (*(__int64 (__fastcall **)(unsigned __int16 *, int *))(*(_QWORD *)v60 + 208LL))(v60, &v81);
              if ( v12 >= 0 )
              {
                if ( v81 )
                  *((_DWORD *)v11 + 20) = 1;
                v12 = PlaiStartDataCollectors((struct _SET_INSTANCE *)v11, &v77);
                if ( v12 >= 0 )
                {
                  Thread = (unsigned __int16 *)CreateThread(0, 0, PlaiSetControl, v11, 0, 0);
                  v11[1] = Thread;
                  if ( Thread )
                  {
                    if ( v77 )
                      EtwNotificationRegister(&SessionNotificationGuid, 7, PlaiTraceNotificationCallback, v11, a5);
                    *a3 = v11;
                    *a4 = v11[7];
                    goto LABEL_171;
                  }
                  v64 = GetLastError();
                  v77 = PlaiHResultFromWin32(v64);
                  v12 = v77;
                  v78 = 0;
                  if ( !(_DWORD)xmmword_180169738
                    || (a2 = 0x4000000000000800LL, (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0)
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
LABEL_171:
                    v8 = v79;
                    goto LABEL_172;
                  }
                  PlaiWhoAmI(v108, 0x4000000000000800uLL);
                  v65 = -1;
                  do
                    ++v65;
                  while ( v108[v65] );
                }
                else
                {
                  v77 = v12;
                  v78 = 0;
                  if ( !(_DWORD)xmmword_180169738 )
                    goto LABEL_171;
                  a2 = 0x4000000000000800LL;
                  if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_171;
                  }
                  PlaiWhoAmI(v107, 0x4000000000000800uLL);
                  v62 = -1;
                  do
                    ++v62;
                  while ( v107[v62] );
                }
              }
              else
              {
                v77 = v12;
                v78 = 0;
                if ( !(_DWORD)xmmword_180169738 )
                  goto LABEL_171;
                a2 = 0x4000000000000800LL;
                if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_171;
                }
                PlaiWhoAmI(v106, 0x4000000000000800uLL);
                v61 = -1;
                do
                  ++v61;
                while ( v106[v61] );
              }
            }
            else
            {
              v77 = v12;
              v78 = 0;
              if ( !(_DWORD)xmmword_180169738 )
                goto LABEL_171;
              a2 = 0x4000000000000800LL;
              if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_171;
              }
              PlaiWhoAmI(v105, 0x4000000000000800uLL);
              v59 = -1;
              do
                ++v59;
              while ( v105[v59] );
            }
          }
          else
          {
            v77 = v56;
            v78 = 0;
            if ( !(_DWORD)xmmword_180169738 )
              goto LABEL_171;
            a2 = 0x4000000000000800LL;
            if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_171;
            }
            PlaiWhoAmI(v104, 0x4000000000000800uLL);
            v57 = -1;
            do
              ++v57;
            while ( v104[v57] );
          }
        }
        else
        {
          v77 = v54;
          v78 = 0;
          if ( !(_DWORD)xmmword_180169738 )
            goto LABEL_171;
          a2 = 0x4000000000000800LL;
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_171;
          }
          PlaiWhoAmI(v103, 0x4000000000000800uLL);
          v55 = -1;
          do
            ++v55;
          while ( v103[v55] );
        }
      }
      else
      {
        v52 = GetLastError();
        v77 = PlaiHResultFromWin32(v52);
        v12 = v77;
        v78 = 0;
        if ( !(_DWORD)xmmword_180169738 )
          goto LABEL_171;
        a2 = 0x4000000000000800LL;
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_171;
        }
        PlaiWhoAmI(v102, 0x4000000000000800uLL);
        v53 = -1;
        do
          ++v53;
        while ( v102[v53] );
      }
    }
    else
    {
      v77 = v49;
      v78 = 0;
      if ( !(_DWORD)xmmword_180169738 )
        goto LABEL_171;
      a2 = 0x4000000000000800LL;
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_171;
      }
      PlaiWhoAmI(v101, 0x4000000000000800uLL);
      v50 = -1;
      do
        ++v50;
      while ( v101[v50] );
    }
LABEL_170:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v77, 4, byte_180147320, 1, &v78, 4);
    goto LABEL_171;
  }
  v12 = -2147024809;
  v11 = 0;
  v78 = 0;
  v77 = -2147024809;
  if ( (_DWORD)xmmword_180169738 )
  {
    a2 = 0x4000000000000800LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v109, 0x4000000000000800uLL);
      v66 = -1;
      do
        ++v66;
      while ( v109[v66] );
      goto LABEL_170;
    }
  }
LABEL_172:
  v77 = v12;
  if ( (int)PlaiWhoAmI(v86, a2) < 0 )
    v86[0] = 0;
  v67 = -1;
  do
    ++v67;
  while ( v86[v67] );
  v68 = (unsigned int)(2 * v67) + 2LL;
  if ( v77 < 0 )
  {
    if ( v83 )
    {
      v72 = -1;
      do
        ++v72;
      while ( *(_WORD *)(v83 + 2 * v72) );
      v73 = (unsigned int)(2 * v72) + 2LL;
    }
    else
    {
      v73 = 0;
    }
    if ( v8 )
    {
      do
        ++v5;
      while ( v8[v5] );
      v74 = (unsigned int)(2 * v5) + 2LL;
    }
    else
    {
      v74 = 0;
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENTLOG_DCS_START_FAILED, 4, v8, v74, v83, v73, v86, v68);
  }
  else
  {
    if ( v83 )
    {
      v69 = -1;
      do
        ++v69;
      while ( *(_WORD *)(v83 + 2 * v69) );
      v70 = (unsigned int)(2 * v69) + 2LL;
    }
    else
    {
      v70 = 0;
    }
    if ( v8 )
    {
      do
        ++v5;
      while ( v8[v5] );
      v71 = (unsigned int)(2 * v5) + 2LL;
    }
    else
    {
      v71 = 0;
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENTLOG_DCS_START, 3, v8, v71, v83, v70, v86, v68);
  }
  if ( v12 < 0 && v11 )
  {
    PlaiCloseCollectorSet((struct _SET_INSTANCE *)v11);
    PlaiFreeDataCollectorSet(v11);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801334e8  push    rbp
0x1801334ea  push    rbx
0x1801334eb  push    rsi
0x1801334ec  push    rdi
0x1801334ed  push    r12
0x1801334ef  push    r13
0x1801334f1  push    r14
0x1801334f3  push    r15
0x1801334f5  lea     rbp, [rsp-0BD8h]
0x1801334fd  sub     rsp, 0CD8h
0x180133504  mov     rax, cs:__security_cookie
0x18013350b  xor     rax, rsp
0x18013350e  mov     [rbp+0C10h+var_50], rax
0x180133515  mov     r13, [rbp+0C10h+arg_20]
0x18013351c  xor     ebx, ebx
0x18013351e  xorps   xmm0, xmm0
0x180133521  mov     [rbp+0C10h+var_C78], rdx
0x180133525  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180133529  mov     [rbp+0C10h+var_C90], rcx
0x18013352d  mov     [rbp+0C10h+var_C80], rbx
0x180133531  mov     r15, r9
0x180133534  mov     [rsp+0D10h+var_CA0], ebx
0x180133538  mov     r14, r8
0x18013353b  mov     [rbp+0C10h+var_C88], bx
0x18013353f  mov     r12, rcx
0x180133542  mov     [rbp+0C10h+var_C84], ebx
0x180133545  movups  [rbp+0C10h+var_C70], xmm0
0x180133549  movups  [rbp+0C10h+var_C60], xmm0
0x18013354d  test    rcx, rcx
0x180133550  jz      loc_1801343A9
0x180133556  cmp     bx, [rcx]
0x180133559  jz      loc_1801343A9
0x18013355f  test    r8, r8
0x180133562  jz      loc_1801343A9
0x180133568  test    r9, r9
0x18013356b  jz      loc_1801343A9
0x180133571  lea     r12d, [rbx+1]
0x180133575  mov     ecx, 98h; dwBytes
0x18013357a  mov     r8d, r12d; int
0x18013357d  lea     r9, byte_180147320; char *
0x180133584  mov     edx, r12d; int
0x180133587  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18013358c  mov     rsi, rax
0x18013358f  test    rax, rax
0x180133592  jnz     loc_180133658
0x180133598  xor     r14d, r14d
0x18013359b  mov     eax, 8007000Eh
0x1801335a0  cmp     dword ptr cs:xmmword_180169738, r14d
0x1801335a7  mov     ebx, eax
0x1801335a9  mov     [rsp+0D10h+var_CA0], r14d
0x1801335ae  mov     [rsp+0D10h+var_C98], eax
0x1801335b2  jz      loc_180134496
0x1801335b8  mov     rdx, 4000000000000800h; unsigned __int64
0x1801335c2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801335c9  jz      loc_180134496
0x1801335cf  mov     rax, cs:qword_180169748
0x1801335d6  and     rax, rdx
0x1801335d9  cmp     cs:qword_180169748, rax
0x1801335e0  jnz     loc_180134496
0x1801335e6  lea     rcx, [rbp+0C10h+var_BD0]; unsigned __int16 *
0x1801335ea  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801335ef  lea     rcx, [rbp+0C10h+var_BD0]
0x1801335f3  mov     rax, rdi
0x1801335f6  inc     rax
0x1801335f9  cmp     [rcx+rax*2], r14w
0x1801335fe  jnz     short loc_1801335F6
0x180133600  lea     ecx, [rax+rax]
0x180133603  add     rcx, 2
0x180133607  lea     rax, [rbp+0C10h+var_BD0]
0x18013360b  mov     [rsp+0D10h+var_CB0], rcx
0x180133610  lea     r9, [rsp+0D10h+var_C98]
0x180133615  mov     [rsp+0D10h+var_CB8], rax
0x18013361a  lea     rcx, byte_180147320
0x180133621  mov     [rsp+0D10h+var_CC0], 19h
0x18013362a  lea     rax, aPlastartdataco; "PlaStartDataCollectorSet"
0x180133631  mov     [rsp+0D10h+var_CC8], rax
0x180133636  lea     rax, [rsp+0D10h+var_CA0]
0x18013363b  mov     [rsp+0D10h+var_CD0], 4
0x180133644  mov     [rsp+0D10h+var_CD8], rax
0x180133649  mov     [rsp+0D10h+var_CE0], r12
0x18013364e  mov     [rsp+0D10h+lpThreadId], rcx
0x180133653  jmp     loc_180134474
0x180133658  mov     rcx, [rbp+0C10h+var_C90]; unsigned __int16 *
0x18013365c  add     rax, 68h ; 'h'
0x180133660  mov     [rax+8], rax
0x180133664  mov     [rax], rax
0x180133667  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18013366c  mov     [rsi], rax
0x18013366f  test    rax, rax
0x180133672  jnz     loc_18013373C
0x180133678  xor     r14d, r14d
0x18013367b  mov     eax, 8007000Eh
0x180133680  cmp     dword ptr cs:xmmword_180169738, r14d
0x180133687  mov     ebx, eax
0x180133689  mov     [rsp+0D10h+var_C98], r14d
0x18013368e  mov     [rsp+0D10h+var_CA0], eax
0x180133692  jz      loc_180134496
0x180133698  mov     rdx, 4000000000000800h; unsigned __int64
0x1801336a2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801336a9  jz      loc_180134496
0x1801336af  mov     rax, cs:qword_180169748
0x1801336b6  and     rax, rdx
0x1801336b9  cmp     cs:qword_180169748, rax
0x1801336c0  jnz     loc_180134496
0x1801336c6  lea     rcx, [rbp+0C10h+var_B50]; unsigned __int16 *
0x1801336cd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801336d2  lea     rcx, [rbp+0C10h+var_B50]
0x1801336d9  mov     rax, rdi
0x1801336dc  inc     rax
0x1801336df  cmp     [rcx+rax*2], r14w
0x1801336e4  jnz     short loc_1801336DC
0x1801336e6  lea     ecx, [rax+rax]
0x1801336e9  lea     rax, [rbp+0C10h+var_B50]
0x1801336f0  add     rcx, 2
0x1801336f4  mov     [rsp+0D10h+var_CB0], rcx
0x1801336f9  lea     rcx, byte_180147320
0x180133700  mov     [rsp+0D10h+var_CB8], rax
0x180133705  lea     rax, aPlastartdataco; "PlaStartDataCollectorSet"
0x18013370c  mov     [rsp+0D10h+var_CC0], 19h
0x180133715  mov     [rsp+0D10h+var_CC8], rax
0x18013371a  lea     rax, [rsp+0D10h+var_C98]
0x18013371f  mov     [rsp+0D10h+var_CD0], 4
0x180133728  mov     [rsp+0D10h+var_CD8], rax
0x18013372d  mov     [rsp+0D10h+var_CE0], r12
0x180133732  mov     [rsp+0D10h+lpThreadId], rcx
0x180133737  jmp     loc_18013446F
0x18013373c  xor     r9d, r9d; lpName
0x18013373f  xor     r8d, r8d; bInitialState
0x180133742  mov     edx, r12d; bManualReset
0x180133745  xor     ecx, ecx; lpEventAttributes
0x180133747  call    cs:__imp_CreateEventW
0x18013374d  mov     [rsi+10h], rax
0x180133751  test    rax, rax
0x180133754  jnz     loc_1801337DF
0x18013375a  call    cs:__imp_GetLastError
0x180133760  mov     ecx, eax; unsigned int
0x180133762  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180133767  xor     r14d, r14d
0x18013376a  mov     [rsp+0D10h+var_CA0], eax
0x18013376e  cmp     dword ptr cs:xmmword_180169738, r14d
0x180133775  mov     ebx, eax
0x180133777  mov     [rsp+0D10h+var_C98], r14d
0x18013377c  jz      loc_180134496
0x180133782  mov     rdx, 4000000000000800h; unsigned __int64
0x18013378c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180133793  jz      loc_180134496
0x180133799  mov     rax, cs:qword_180169748
0x1801337a0  and     rax, rdx
0x1801337a3  cmp     cs:qword_180169748, rax
0x1801337aa  jnz     loc_180134496
0x1801337b0  lea     rcx, [rbp+0C10h+var_AD0]; unsigned __int16 *
0x1801337b7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801337bc  lea     rcx, [rbp+0C10h+var_AD0]
0x1801337c3  mov     rax, rdi
0x1801337c6  inc     rax
0x1801337c9  cmp     [rcx+rax*2], r14w
0x1801337ce  jnz     short loc_1801337C6
0x1801337d0  lea     ecx, [rax+rax]
0x1801337d3  lea     rax, [rbp+0C10h+var_AD0]
0x1801337da  jmp     loc_1801336F0
0x1801337df  xor     r9d, r9d; lpName
0x1801337e2  xor     r8d, r8d; bInitialState
0x1801337e5  mov     edx, r12d; bManualReset
0x1801337e8  xor     ecx, ecx; lpEventAttributes
0x1801337ea  call    cs:__imp_CreateEventW
0x1801337f0  mov     [rsi+20h], rax
0x1801337f4  test    rax, rax
0x1801337f7  jnz     loc_180133882
0x1801337fd  call    cs:__imp_GetLastError
0x180133803  mov     ecx, eax; unsigned int
0x180133805  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18013380a  xor     r14d, r14d
0x18013380d  mov     [rsp+0D10h+var_CA0], eax
0x180133811  cmp     dword ptr cs:xmmword_180169738, r14d
0x180133818  mov     ebx, eax
0x18013381a  mov     [rsp+0D10h+var_C98], r14d
0x18013381f  jz      loc_180134496
0x180133825  mov     rdx, 4000000000000800h; unsigned __int64
0x18013382f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180133836  jz      loc_180134496
0x18013383c  mov     rax, cs:qword_180169748
0x180133843  and     rax, rdx
0x180133846  cmp     cs:qword_180169748, rax
0x18013384d  jnz     loc_180134496
0x180133853  lea     rcx, [rbp+0C10h+var_A50]; unsigned __int16 *
0x18013385a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18013385f  lea     rcx, [rbp+0C10h+var_A50]
0x180133866  mov     rax, rdi
0x180133869  inc     rax
0x18013386c  cmp     [rcx+rax*2], r14w
0x180133871  jnz     short loc_180133869
0x180133873  lea     ecx, [rax+rax]
0x180133876  lea     rax, [rbp+0C10h+var_A50]
0x18013387d  jmp     loc_1801336F0
0x180133882  xor     r9d, r9d; lpName
0x180133885  xor     r8d, r8d; bInitialState
0x180133888  mov     edx, r12d; bManualReset
0x18013388b  xor     ecx, ecx; lpEventAttributes
0x18013388d  call    cs:__imp_CreateEventW
0x180133893  mov     [rsi+38h], rax
0x180133897  test    rax, rax
0x18013389a  jnz     loc_180133925
0x1801338a0  call    cs:__imp_GetLastError
0x1801338a6  mov     ecx, eax; unsigned int
0x1801338a8  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1801338ad  xor     r14d, r14d
0x1801338b0  mov     [rsp+0D10h+var_CA0], eax
0x1801338b4  cmp     dword ptr cs:xmmword_180169738, r14d
0x1801338bb  mov     ebx, eax
0x1801338bd  mov     [rsp+0D10h+var_C98], r14d
0x1801338c2  jz      loc_180134496
0x1801338c8  mov     rdx, 4000000000000800h; unsigned __int64
0x1801338d2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801338d9  jz      loc_180134496
0x1801338df  mov     rax, cs:qword_180169748
0x1801338e6  and     rax, rdx
0x1801338e9  cmp     cs:qword_180169748, rax
0x1801338f0  jnz     loc_180134496
0x1801338f6  lea     rcx, [rbp+0C10h+var_9D0]; unsigned __int16 *
0x1801338fd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180133902  lea     rcx, [rbp+0C10h+var_9D0]
0x180133909  mov     rax, rdi
0x18013390c  inc     rax
0x18013390f  cmp     [rcx+rax*2], r14w
0x180133914  jnz     short loc_18013390C
0x180133916  lea     ecx, [rax+rax]
0x180133919  lea     rax, [rbp+0C10h+var_9D0]
0x180133920  jmp     loc_1801336F0
0x180133925  xor     r9d, r9d; lpName
0x180133928  xor     r8d, r8d; bInitialState
0x18013392b  mov     edx, r12d; bManualReset
0x18013392e  xor     ecx, ecx; lpEventAttributes
0x180133930  call    cs:__imp_CreateEventW
0x180133936  mov     [rsi+40h], rax
0x18013393a  test    rax, rax
0x18013393d  jnz     loc_1801339C8
0x180133943  call    cs:__imp_GetLastError
0x180133949  mov     ecx, eax; unsigned int
0x18013394b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180133950  xor     r14d, r14d
0x180133953  mov     [rsp+0D10h+var_CA0], eax
0x180133957  cmp     dword ptr cs:xmmword_180169738, r14d
0x18013395e  mov     ebx, eax
0x180133960  mov     [rsp+0D10h+var_C98], r14d
0x180133965  jz      loc_180134496
0x18013396b  mov     rdx, 4000000000000800h; unsigned __int64
0x180133975  test    qword ptr cs:xmmword_180169738+8, rdx
0x18013397c  jz      loc_180134496
0x180133982  mov     rax, cs:qword_180169748
0x180133989  and     rax, rdx
0x18013398c  cmp     cs:qword_180169748, rax
0x180133993  jnz     loc_180134496
0x180133999  lea     rcx, [rbp+0C10h+var_950]; unsigned __int16 *
0x1801339a0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801339a5  lea     rcx, [rbp+0C10h+var_950]
0x1801339ac  mov     rax, rdi
0x1801339af  inc     rax
0x1801339b2  cmp     [rcx+rax*2], r14w
0x1801339b7  jnz     short loc_1801339AF
0x1801339b9  lea     ecx, [rax+rax]
0x1801339bc  lea     rax, [rbp+0C10h+var_950]
0x1801339c3  jmp     loc_1801336F0
0x1801339c8  xor     r9d, r9d; lpName
0x1801339cb  xor     r8d, r8d; bInitialState
0x1801339ce  mov     edx, r12d; bManualReset
0x1801339d1  xor     ecx, ecx; lpEventAttributes
0x1801339d3  call    cs:__imp_CreateEventW
0x1801339d9  mov     [rsi+28h], rax
0x1801339dd  test    rax, rax
0x1801339e0  jnz     loc_180133A6B
0x1801339e6  call    cs:__imp_GetLastError
0x1801339ec  mov     ecx, eax; unsigned int
0x1801339ee  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1801339f3  xor     r14d, r14d
0x1801339f6  mov     [rsp+0D10h+var_CA0], eax
0x1801339fa  cmp     dword ptr cs:xmmword_180169738, r14d
0x180133a01  mov     ebx, eax
0x180133a03  mov     [rsp+0D10h+var_C98], r14d
0x180133a08  jz      loc_180134496
0x180133a0e  mov     rdx, 4000000000000800h; unsigned __int64
0x180133a18  test    qword ptr cs:xmmword_180169738+8, rdx
0x180133a1f  jz      loc_180134496
0x180133a25  mov     rax, cs:qword_180169748
0x180133a2c  and     rax, rdx
0x180133a2f  cmp     cs:qword_180169748, rax
0x180133a36  jnz     loc_180134496
0x180133a3c  lea     rcx, [rbp+0C10h+var_8D0]; unsigned __int16 *
0x180133a43  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180133a48  lea     rcx, [rbp+0C10h+var_8D0]
0x180133a4f  mov     rax, rdi
0x180133a52  inc     rax
0x180133a55  cmp     [rcx+rax*2], r14w
0x180133a5a  jnz     short loc_180133A52
0x180133a5c  lea     ecx, [rax+rax]
0x180133a5f  lea     rax, [rbp+0C10h+var_8D0]
0x180133a66  jmp     loc_1801336F0
0x180133a6b  xor     r9d, r9d; lpName
0x180133a6e  xor     r8d, r8d; bInitialState
0x180133a71  mov     edx, r12d; bManualReset
0x180133a74  xor     ecx, ecx; lpEventAttributes
  ... truncated ...
```
