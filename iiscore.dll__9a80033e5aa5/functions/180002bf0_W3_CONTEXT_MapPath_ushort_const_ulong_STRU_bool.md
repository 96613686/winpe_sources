# W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)

- ea: `0x180002bf0`
- end: `0x18000347e`
- name: `?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z`
- size: `2190`
- prototype: `__int64 __fastcall(W3_CONTEXT *this, unsigned __int16 *, unsigned int, struct STRU *, bool *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800021f0`
- `0x180015cf0`
- `0x180021290`
- `0x18002ac90`

## callees

- `0x180001550`
- `0x180002158`
- `0x180002bf0`
- `0x180004b2c`
- `0x18000d1b8`
- `0x1800123c0`
- `0x180019558`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180002e68`
- `msvcrt!_wcsnicmp` at `0x180002e68`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800032b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800032b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800032d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800032d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003473`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003473`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000314e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000314e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000335b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000335b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002fe1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002fe1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003012`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003012`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003051`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003051`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003024`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003024`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002e27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002e31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002e3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002e27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002e31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002e3b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002cab`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800033a9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002cab`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800033a9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002c9d`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002ea2`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002f60`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002fae`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003031`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000338c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000339a`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002c9d`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002ea2`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002f60`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002fae`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003031`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000338c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000339a`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180002e8d`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180002fcc`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180002fee`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180002e8d`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180002fcc`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180002fee`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180002c88`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180002c88`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002eb2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002f02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002f6f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002fa1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003041`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000308f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002eb2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002f02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002f6f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002fa1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003041`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000308f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000306f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000306f`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002f56`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180002f56`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000333e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000333e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002c75`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cda`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cf4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800031ee`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002c75`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cda`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cf4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800031ee`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002dc4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003005`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002dc4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003005`
- `iisutil!WriteRefTraceLog` at `0x1800031a7`
- `iisutil!WriteRefTraceLog` at `0x180003269`
- `iisutil!WriteRefTraceLog` at `0x1800031a7`
- `iisutil!WriteRefTraceLog` at `0x180003269`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002f8d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002f8d`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180002c7f`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180002c7f`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::MapPath(
        W3_CONTEXT *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct STRU *a4,
        bool *a5)
{
  unsigned __int16 *v5; // r12
  size_t v7; // r13
  BUFFER *Buffer; // rax
  unsigned int Size; // eax
  __int64 v10; // rbx
  RTL_SRWLOCK *v11; // rsi
  __int64 v12; // rbx
  int v13; // edi
  unsigned __int16 *v14; // r13
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned int CCH; // r15d
  const unsigned __int16 *v20; // r12
  __int64 (__fastcall *v21)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64 *, _QWORD); // rbx
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // r15
  int v24; // eax
  __int64 (__fastcall *v25)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64 *, _QWORD); // rbx
  unsigned __int16 *v26; // rax
  __int64 v27; // rbx
  DWORD TickCount; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rdi
  bool v34; // al
  const unsigned __int16 *v35; // rax
  __int64 v36; // r15
  int v37; // edi
  const unsigned __int16 *v38; // rax
  W3_URL_INFO *v39; // rax
  W3_URL_INFO *v40; // rax
  unsigned int v41; // r8d
  __int64 v42; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v44; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v45[2]; // [rsp+70h] [rbp-98h]
  unsigned __int16 *v46; // [rsp+78h] [rbp-90h]
  unsigned __int16 *Str; // [rsp+80h] [rbp-88h]
  bool *v48; // [rsp+88h] [rbp-80h]
  STRU *v49; // [rsp+90h] [rbp-78h]
  _BYTE v50[64]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v51[2]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v52[56]; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int16 v53[116]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v54[56]; // [rsp+208h] [rbp+100h] BYREF
  unsigned __int16 v55[68]; // [rsp+240h] [rbp+138h] BYREF
  unsigned __int16 v56[264]; // [rsp+2C8h] [rbp+1C0h] BYREF

  v5 = a2;
  v7 = a3;
  v46 = a2;
  v49 = a4;
  v48 = a5;
  v43 = 0;
  memset_0(v56, 0, 0x208u);
  STRU::STRU((STRU *)v50, v56, 0x104u);
  Buffer = STRU::QueryBuffer((STRU *)v50);
  Size = BUFFER::QuerySize(Buffer);
  v10 = *((_QWORD *)this + 1009);
  LODWORD(v42) = Size;
  v45[0] = STRU::QueryCCH((STRU *)(v10 + 24));
  v44 = 0;
  Str = (unsigned __int16 *)STRU::QueryStr((STRU *)(v10 + 24));
  v11 = 0;
  v51[0] = &W3_URL_INFO_KEY::`vftable';
  STRU::STRU((STRU *)v52, v53, 0x74u);
  STRU::STRU((STRU *)v54, v55, 0x44u);
  v12 = *((_QWORD *)this + 1115);
  if ( v12 )
  {
    v36 = STRU::QueryCCH((STRU *)(v12 + 320)) + 24;
    v37 = STRU::QueryCCH((STRU *)(v12 + 32)) - v36;
    v38 = STRU::QueryStr((STRU *)(v12 + 32));
    if ( (_DWORD)v7 == v37 && !_wcsnicmp(v5, &v38[v36], v7) )
    {
      v11 = (RTL_SRWLOCK *)*((_QWORD *)this + 1115);
      if ( v11 )
        goto LABEL_72;
    }
  }
  v13 = W3_URL_INFO_KEY::Initialize(
          (W3_URL_INFO_KEY *)v51,
          v5,
          v7,
          Str,
          v45[0],
          *(_DWORD *)(*((_QWORD *)this + 1009) + 16LL));
  if ( v13 < 0 )
    goto LABEL_11;
  if ( (*(int (__fastcall **)(W3_SERVER *, _QWORD, _QWORD *, RTL_SRWLOCK **, _QWORD))(*(_QWORD *)g_pW3Server + 80LL))(
         g_pW3Server,
         0,
         v51,
         &v44,
         0) >= 0
    && v44 )
  {
    v11 = v44 - 1;
  }
  if ( v11 )
  {
LABEL_72:
    if ( STRU::IsEmpty((STRU *)&v11[76]) )
    {
      AcquireSRWLockShared(v11 + 120);
      CCH = STRU::QueryCCH((STRU *)&v11[76]);
      v20 = STRU::QueryStr((STRU *)&v11[76]);
      ReleaseSRWLockShared(v11 + 120);
    }
    else
    {
      CCH = STRU::QueryCCH((STRU *)&v11[76]);
      v20 = STRU::QueryStr((STRU *)&v11[76]);
    }
    if ( CCH )
    {
      v14 = v46;
      goto LABEL_7;
    }
    v5 = v46;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)g_pW3Server + 187) + 56LL))(
          *((_QWORD *)g_pW3Server + 187),
          &v43);
  if ( v13 < 0 )
    goto LABEL_11;
  v21 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64 *, _QWORD))(*(_QWORD *)v43 + 40LL);
  v22 = STRU::QueryStr((STRU *)v50);
  v23 = Str;
  v24 = v21(v43, Str, v5, v22, &v42, 0);
  v13 = v24;
  if ( v24 < 0 )
  {
    if ( v24 != -2147024774 )
      goto LABEL_11;
    v13 = STRU::Resize((STRU *)v50, v42);
    if ( v13 < 0 )
      goto LABEL_11;
    v25 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64 *, _QWORD))(*(_QWORD *)v43 + 40LL);
    v26 = STRU::QueryStr((STRU *)v50);
    v13 = v25(v43, v23, v5, v26, &v42, 0);
    if ( v13 < 0 )
      goto LABEL_11;
  }
  STRU::SyncWithBuffer((STRU *)v50);
  if ( STRU::QueryCCH((STRU *)v50) == 2 && STRU::QueryStr((STRU *)v50)[1] == 58 )
  {
    v13 = STRU::Append((STRU *)v50, L"\\", 1u);
    if ( v13 < 0 )
      goto LABEL_11;
  }
  v20 = STRU::QueryStr((STRU *)v50);
  CCH = STRU::QueryCCH((STRU *)v50);
  if ( v11 )
  {
    v14 = v46;
  }
  else
  {
    v39 = (W3_URL_INFO *)operator new(0x540u);
    if ( !v39 || (v40 = W3_URL_INFO::W3_URL_INFO(v39), (v11 = (RTL_SRWLOCK *)v40) == 0) )
    {
      v13 = -2147024888;
      goto LABEL_11;
    }
    v41 = v7;
    v14 = v46;
    v13 = W3_URL_INFO::Initialize(v40, v46, v41, *(_DWORD *)(*((_QWORD *)this + 1009) + 16LL), Str, v45[0], 0);
    if ( v13 < 0 )
      goto LABEL_11;
    v44 = v11 + 1;
    (*(void (__fastcall **)(W3_SERVER *, __int64, _QWORD *, RTL_SRWLOCK **, _QWORD))(*(_QWORD *)g_pW3Server + 80LL))(
      g_pW3Server,
      1,
      v51,
      &v44,
      0);
  }
  if ( STRU::IsEmpty((STRU *)&v11[76]) )
  {
    AcquireSRWLockExclusive(v11 + 120);
    if ( STRU::IsEmpty((STRU *)&v11[76]) )
      STRU::Copy((STRU *)&v11[76], v20, CCH);
    ReleaseSRWLockExclusive(v11 + 120);
  }
LABEL_7:
  v15 = *((_QWORD *)this + 10);
  if ( !*(_QWORD *)(v15 + 80)
    || (v16 = *(_QWORD *)(v15 + 112),
        v17 = *(_QWORD *)(v15 + 104),
        *(_DWORD *)(v17 + 4LL * *(unsigned int *)(v16 + 252)) == -1)
    && *(_DWORD *)(v17 + 4LL * *(unsigned int *)(v16 + 248)) == -1 )
  {
    *v48 = 0;
    v13 = STRU::Copy(v49, v20, CCH);
  }
  else
  {
    v27 = (*(__int64 (__fastcall **)(W3_CONTEXT *, __int64))(*(_QWORD *)this + 144LL))(this, 736);
    if ( v27 )
    {
      *(_DWORD *)(v27 + 8) = 0;
      *(_QWORD *)v27 = &NOTIFICATION_CONTEXT::`vftable';
      *(_WORD *)(v27 + 12) = 0;
      *(_DWORD *)(v27 + 16) = -1;
      *(_QWORD *)(v27 + 24) = this;
      *(_DWORD *)(v27 + 32) = 1480807502;
      *(_DWORD *)(v27 + 36) = 1;
      *(_DWORD *)(v27 + 40) = 1;
      TickCount = GetTickCount();
      v29 = *(_QWORD *)(v27 + 24);
      *(_DWORD *)(v27 + 44) = TickCount;
      *(_QWORD *)(v27 + 48) = 0;
      *(_QWORD *)(v27 + 56) = 0;
      *(_QWORD *)(v27 + 64) = 0;
      *(_QWORD *)(v27 + 72) = 0;
      *(_QWORD *)(v27 + 80) = 0;
      *(_QWORD *)(v27 + 88) = 0;
      *(_QWORD *)(v27 + 96) = 0;
      *(_QWORD *)(v27 + 104) = 0;
      *(_QWORD *)(v27 + 112) = 0;
      *(_DWORD *)(v27 + 120) = 0;
      *(_DWORD *)(v27 + 124) = -1;
      *(_QWORD *)(v27 + 128) = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v29 + 76));
      if ( W3_CONTEXT_BASE::sm_pTraceLog )
        WriteRefTraceLog(W3_CONTEXT_BASE::sm_pTraceLog, *(unsigned int *)(v29 + 76), v29);
      *(_DWORD *)(v27 + 144) = 0;
      *(_QWORD *)v27 = &NOTIFICATION_MAP_PATH::`vftable'{for `NOTIFICATION_CONTEXT'};
      *(_QWORD *)(v27 + 152) = v14;
      *(_QWORD *)(v27 + 136) = &NOTIFICATION_MAP_PATH::`vftable'{for `IMapPathProvider'};
      *(_QWORD *)(v27 + 160) = v20;
      STRU::STRU((STRU *)(v27 + 168), (unsigned __int16 *)(v27 + 224), 0x100u);
      v30 = *(_QWORD *)(v15 + 80);
      *(_QWORD *)(v27 + 80) = v30;
      *(_QWORD *)(v27 + 88) = *(_QWORD *)(v15 + 88);
      *(_QWORD *)(v27 + 104) = *(_QWORD *)(v15 + 104);
      *(_DWORD *)(v27 + 120) = *(_DWORD *)(v15 + 120);
      v31 = *(_QWORD *)(v15 + 112);
      *(_QWORD *)(v27 + 112) = v31;
      if ( v30 )
      {
        *(_DWORD *)(v27 + 8) = 0x80000000;
        *(_BYTE *)(v27 + 12) = 0;
        *(_DWORD *)(v27 + 16) = -1;
        *(_DWORD *)(v27 + 124) = *(_DWORD *)(v31 + 248);
      }
      v32 = NOTIFICATION_CONTEXT::SetupSynchronousCall((NOTIFICATION_CONTEXT *)v27);
      if ( v32 < 0 )
      {
        *(_DWORD *)(v27 + 72) = v32;
      }
      else
      {
        v33 = *((_QWORD *)this + 10);
        if ( v33 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v33 + 36));
          if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
            WriteRefTraceLog(NOTIFICATION_CONTEXT::sm_pTraceLog, *(unsigned int *)(v33 + 36), v33);
          _InterlockedIncrement((volatile signed __int32 *)(v33 + 52));
        }
        *(_QWORD *)(v27 + 56) = v33;
        *((_QWORD *)this + 10) = v27;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v27 + 8LL))(
               v27,
               0,
               0,
               0,
               0) == 1 )
          WaitForSingleObject(*(HANDLE *)(v27 + 64), 0xFFFFFFFF);
        if ( TlsGetValue(g_TlsEventIndex) )
          CloseHandle(*(HANDLE *)(v27 + 64));
        else
          TlsSetValue(g_TlsEventIndex, *(LPVOID *)(v27 + 64));
        *(_QWORD *)(v27 + 64) = 0;
      }
      if ( *(_DWORD *)(v27 + 144) )
        *(_BYTE *)(*((_QWORD *)this + 49) + 9097LL) = 1;
      v13 = *(_DWORD *)(v27 + 72);
      if ( v13 >= 0 )
      {
        v34 = v20 != (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v27 + 136) + 16LL))(v27 + 136);
        *v48 = v34;
        v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v27 + 136) + 16LL))(v27 + 136);
        v13 = STRU::Copy(v49, v35);
      }
      W3_CONTEXT_BASE::FinishNotificationLoop(v27);
    }
    else
    {
      v13 = -2147024888;
    }
  }
LABEL_11:
  if ( v44 )
  {
    (*((void (__fastcall **)(RTL_SRWLOCK *))v44->Ptr + 2))(v44);
    v44 = 0;
  }
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  STRU::~STRU((STRU *)v54);
  STRU::~STRU((STRU *)v52);
  STRU::~STRU((STRU *)v50);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180002bf0  mov     r11, rsp
0x180002bf3  push    rbp
0x180002bf4  push    rdi
0x180002bf5  push    r15
0x180002bf7  lea     rbp, [r11-428h]
0x180002bfe  sub     rsp, 510h
0x180002c05  mov     rax, cs:__security_cookie
0x180002c0c  xor     rax, rsp
0x180002c0f  mov     [rbp+420h+var_50], rax
0x180002c16  mov     rax, [rbp+420h+arg_20]
0x180002c1d  mov     [r11-20h], rbx
0x180002c21  mov     [r11-28h], rsi
0x180002c25  mov     [r11-30h], r12
0x180002c29  mov     r12, rdx
0x180002c2c  mov     [r11-38h], r13
0x180002c30  mov     [r11-40h], r14
0x180002c34  mov     r14, rcx
0x180002c37  mov     r13d, r8d
0x180002c3a  lea     rcx, [rbp+420h+var_260]; void *
0x180002c41  mov     [rsp+520h+var_4B0], rdx
0x180002c46  mov     r8d, 208h; Size
0x180002c4c  xor     edx, edx; Val
0x180002c4e  mov     [rbp+420h+var_498], r9
0x180002c52  mov     [rbp+420h+var_4A0], rax
0x180002c56  mov     [rsp+520h+var_4C8], 0
0x180002c5f  call    memset_0
0x180002c64  mov     r8d, 104h
0x180002c6a  lea     rdx, [rbp+420h+var_260]
0x180002c71  lea     rcx, [rbp+420h+var_490]
0x180002c75  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002c7b  lea     rcx, [rbp+420h+var_490]
0x180002c7f  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180002c85  mov     rcx, rax
0x180002c88  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180002c8e  mov     rbx, [r14+1F88h]
0x180002c95  mov     dword ptr [rsp+520h+var_4D0], eax
0x180002c99  lea     rcx, [rbx+18h]
0x180002c9d  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180002ca3  lea     rcx, [rbx+18h]
0x180002ca7  mov     [rsp+520h+var_4B8], eax
0x180002cab  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180002cb1  mov     r8d, 74h ; 't'
0x180002cb7  mov     [rsp+520h+var_4C0], 0
0x180002cc0  mov     [rsp+520h+var_4A8], rax
0x180002cc5  lea     rdx, [rbp+420h+var_408]
0x180002cc9  lea     rax, ??_7W3_URL_INFO_KEY@@6B@; const W3_URL_INFO_KEY::`vftable'
0x180002cd0  xor     esi, esi
0x180002cd2  lea     rcx, [rbp+420h+var_440]
0x180002cd6  mov     [rbp+420h+var_450], rax
0x180002cda  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002ce0  mov     r8d, 44h ; 'D'
0x180002ce6  lea     rdx, [rbp+420h+var_2E8]
0x180002ced  lea     rcx, [rbp+420h+var_320]
0x180002cf4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002cfa  mov     rbx, [r14+22D8h]
0x180002d01  test    rbx, rbx
0x180002d04  jnz     loc_180003385
0x180002d0a  mov     rax, [r14+1F88h]
0x180002d11  mov     r8d, r13d; unsigned int
0x180002d14  mov     r9, [rsp+520h+var_4A8]; unsigned __int16 *
0x180002d19  mov     rdx, r12; unsigned __int16 *
0x180002d1c  mov     ecx, [rax+10h]
0x180002d1f  mov     eax, [rsp+520h+var_4B8]
0x180002d23  mov     [rsp+520h+var_4F8], ecx; unsigned int
0x180002d27  lea     rcx, [rbp+420h+var_450]; this
0x180002d2b  mov     dword ptr [rsp+520h+var_500], eax; unsigned int
0x180002d2f  call    ?Initialize@W3_URL_INFO_KEY@@QEAAJPEBGK0KK@Z; W3_URL_INFO_KEY::Initialize(ushort const *,ulong,ushort const *,ulong,ulong)
0x180002d34  mov     edi, eax
0x180002d36  test    eax, eax
0x180002d38  js      loc_180002DCC
0x180002d3e  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180002d45  lea     r9, [rsp+520h+var_4C0]
0x180002d4a  lea     r8, [rbp+420h+var_450]
0x180002d4e  mov     [rsp+520h+var_500], 0
0x180002d57  xor     edx, edx
0x180002d59  mov     rax, [rcx]
0x180002d5c  mov     rax, [rax+50h]
0x180002d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d65  test    eax, eax
0x180002d67  jns     loc_1800033BD
0x180002d6d  test    rsi, rsi
0x180002d70  jz      loc_180002EC9
0x180002d76  jmp     loc_180002E86
0x180002d7b  mov     r13, [rsp+520h+var_4B0]
0x180002d80  mov     rdi, [r14+50h]
0x180002d84  cmp     qword ptr [rdi+50h], 0
0x180002d89  jz      short loc_180002DB3
0x180002d8b  mov     rcx, [rdi+70h]
0x180002d8f  mov     rdx, [rdi+68h]
0x180002d93  mov     eax, [rcx+0FCh]
0x180002d99  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x180002d9d  jnz     loc_1800030F5
0x180002da3  mov     eax, [rcx+0F8h]
0x180002da9  cmp     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x180002dad  jnz     loc_1800030F5
0x180002db3  mov     rcx, [rbp+420h+var_4A0]
0x180002db7  mov     r8d, r15d
0x180002dba  mov     rdx, r12
0x180002dbd  mov     byte ptr [rcx], 0
0x180002dc0  mov     rcx, [rbp+420h+var_498]
0x180002dc4  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002dca  mov     edi, eax
0x180002dcc  xor     r15d, r15d
0x180002dcf  mov     rcx, [rsp+520h+var_4C0]
0x180002dd4  mov     r14, [rsp+520h+var_38]
0x180002ddc  mov     r13, [rsp+520h+var_30]
0x180002de4  mov     r12, [rsp+520h+var_28]
0x180002dec  mov     rsi, [rsp+520h+var_20]
0x180002df4  mov     rbx, [rsp+520h+var_18]
0x180002dfc  test    rcx, rcx
0x180002dff  jnz     loc_1800030DF
0x180002e05  mov     rcx, [rsp+520h+var_4C8]
0x180002e0a  test    rcx, rcx
0x180002e0d  jz      short loc_180002E20
0x180002e0f  mov     rax, [rcx]
0x180002e12  mov     rax, [rax+10h]
0x180002e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1b  mov     [rsp+520h+var_4C8], r15
0x180002e20  lea     rcx, [rbp+420h+var_320]
0x180002e27  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002e2d  lea     rcx, [rbp+420h+var_440]
0x180002e31  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002e37  lea     rcx, [rbp+420h+var_490]
0x180002e3b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002e41  mov     eax, edi
0x180002e43  mov     rcx, [rbp+420h+var_50]
0x180002e4a  xor     rcx, rsp; StackCookie
0x180002e4d  call    __security_check_cookie
0x180002e52  add     rsp, 510h
0x180002e59  pop     r15
0x180002e5b  pop     rdi
0x180002e5c  pop     rbp
0x180002e5d  retn
0x180002e5e  mov     r8, r13; MaxCount
0x180002e61  lea     rdx, [rax+r15*2]; String2
0x180002e65  mov     rcx, r12; String1
0x180002e68  call    cs:__imp__wcsnicmp
0x180002e6e  test    eax, eax
0x180002e70  jnz     loc_180002D0A
0x180002e76  mov     rsi, [r14+22D8h]
0x180002e7d  test    rsi, rsi
0x180002e80  jz      loc_180002D0A
0x180002e86  lea     rcx, [rsi+260h]
0x180002e8d  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180002e93  test    al, al
0x180002e95  jnz     loc_18000301D
0x180002e9b  lea     rcx, [rsi+260h]
0x180002ea2  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180002ea8  lea     rcx, [rsi+260h]
0x180002eaf  mov     r15d, eax
0x180002eb2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002eb8  mov     r12, rax
0x180002ebb  test    r15d, r15d
0x180002ebe  jnz     loc_180002D7B
0x180002ec4  mov     r12, [rsp+520h+var_4B0]
0x180002ec9  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180002ed0  lea     rdx, [rsp+520h+var_4C8]
0x180002ed5  mov     rcx, [rax+5D8h]
0x180002edc  mov     rax, [rcx]
0x180002edf  mov     rax, [rax+38h]
0x180002ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee8  mov     edi, eax
0x180002eea  test    eax, eax
0x180002eec  js      loc_180002DCC
0x180002ef2  mov     rax, [rsp+520h+var_4C8]
0x180002ef7  mov     rcx, [rax]
0x180002efa  mov     rbx, [rcx+28h]
0x180002efe  lea     rcx, [rbp+420h+var_490]
0x180002f02  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002f08  mov     r15, [rsp+520h+var_4A8]
0x180002f0d  lea     rcx, [rsp+520h+var_4D0]
0x180002f12  mov     [rsp+520h+var_4E8], 0
0x180002f1b  mov     r9, rax
0x180002f1e  mov     [rsp+520h+var_4F0], 0; struct INativeSectionException **
0x180002f27  mov     r8, r12
0x180002f2a  mov     qword ptr [rsp+520h+var_4F8], 0
0x180002f33  mov     rdx, r15
0x180002f36  mov     [rsp+520h+var_500], rcx
0x180002f3b  mov     rax, rbx
0x180002f3e  mov     rcx, [rsp+520h+var_4C8]
0x180002f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f48  mov     edi, eax
0x180002f4a  test    eax, eax
0x180002f4c  js      loc_18000305C
0x180002f52  lea     rcx, [rbp+420h+var_490]
0x180002f56  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180002f5c  lea     rcx, [rbp+420h+var_490]
0x180002f60  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180002f66  cmp     eax, 2
0x180002f69  jnz     short loc_180002F9D
0x180002f6b  lea     rcx, [rbp+420h+var_490]
0x180002f6f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002f75  cmp     word ptr [rax+2], 3Ah ; ':'
0x180002f7a  jnz     short loc_180002F9D
0x180002f7c  mov     r8d, 1
0x180002f82  lea     rdx, asc_180039114; "\\"
0x180002f89  lea     rcx, [rbp+420h+var_490]
0x180002f8d  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002f93  mov     edi, eax
0x180002f95  test    eax, eax
0x180002f97  js      loc_180002DCC
0x180002f9d  lea     rcx, [rbp+420h+var_490]
0x180002fa1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002fa7  lea     rcx, [rbp+420h+var_490]
0x180002fab  mov     r12, rax
0x180002fae  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180002fb4  mov     r15d, eax
0x180002fb7  test    rsi, rsi
0x180002fba  jz      loc_1800033D4
0x180002fc0  mov     r13, [rsp+520h+var_4B0]
0x180002fc5  lea     rcx, [rsi+260h]
0x180002fcc  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180002fd2  test    al, al
0x180002fd4  jz      loc_180002D80
0x180002fda  lea     rcx, [rsi+3C0h]; SRWLock
0x180002fe1  call    cs:__imp_AcquireSRWLockExclusive
0x180002fe7  lea     rcx, [rsi+260h]
0x180002fee  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180002ff4  test    al, al
0x180002ff6  jz      short loc_18000300B
0x180002ff8  mov     r8d, r15d
0x180002ffb  lea     rcx, [rsi+260h]
0x180003002  mov     rdx, r12
0x180003005  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000300b  lea     rcx, [rsi+3C0h]; SRWLock
0x180003012  call    cs:__imp_ReleaseSRWLockExclusive
0x180003018  jmp     loc_180002D80
0x18000301d  lea     rcx, [rsi+3C0h]; SRWLock
0x180003024  call    cs:__imp_AcquireSRWLockShared
0x18000302a  lea     rcx, [rsi+260h]
0x180003031  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180003037  lea     rcx, [rsi+260h]
0x18000303e  mov     r15d, eax
0x180003041  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003047  lea     rcx, [rsi+3C0h]; SRWLock
0x18000304e  mov     r12, rax
0x180003051  call    cs:__imp_ReleaseSRWLockShared
0x180003057  jmp     loc_180002EBB
0x18000305c  cmp     eax, 8007007Ah
0x180003061  jnz     loc_180002DCC
0x180003067  mov     edx, dword ptr [rsp+520h+var_4D0]
0x18000306b  lea     rcx, [rbp+420h+var_490]
0x18000306f  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003075  mov     edi, eax
0x180003077  test    eax, eax
0x180003079  js      loc_180002DCC
0x18000307f  mov     rax, [rsp+520h+var_4C8]
0x180003084  mov     rcx, [rax]
0x180003087  mov     rbx, [rcx+28h]
0x18000308b  lea     rcx, [rbp+420h+var_490]
0x18000308f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003095  mov     [rsp+520h+var_4E8], 0
0x18000309e  lea     rcx, [rsp+520h+var_4D0]
0x1800030a3  mov     [rsp+520h+var_4F0], 0
0x1800030ac  mov     r9, rax
0x1800030af  mov     qword ptr [rsp+520h+var_4F8], 0
0x1800030b8  mov     r8, r12
0x1800030bb  mov     [rsp+520h+var_500], rcx
0x1800030c0  mov     rdx, r15
0x1800030c3  mov     rcx, [rsp+520h+var_4C8]
0x1800030c8  mov     rax, rbx
0x1800030cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d0  mov     edi, eax
0x1800030d2  test    eax, eax
0x1800030d4  jns     loc_180002F52
0x1800030da  jmp     loc_180002DCC
0x1800030df  mov     rax, [rcx]
0x1800030e2  mov     rax, [rax+10h]
0x1800030e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030eb  mov     [rsp+520h+var_4C0], r15
0x1800030f0  jmp     loc_180002E05
0x1800030f5  mov     rax, [r14]
0x1800030f8  mov     edx, 2E0h
0x1800030fd  mov     rcx, r14
0x180003100  mov     rax, [rax+90h]
0x180003107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310c  xor     r15d, r15d
0x18000310f  mov     rbx, rax
0x180003112  test    rax, rax
0x180003115  jz      loc_180003348
0x18000311b  lea     rax, ??_7NOTIFICATION_CONTEXT@@6B@; const NOTIFICATION_CONTEXT::`vftable'
0x180003122  mov     [rbx+8], r15d
0x180003126  mov     [rbx], rax
0x180003129  mov     [rbx+0Ch], r15w
0x18000312e  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180003135  mov     [rbx+18h], r14
0x180003139  mov     dword ptr [rbx+20h], 5843544Eh
0x180003140  mov     dword ptr [rbx+24h], 1
0x180003147  mov     dword ptr [rbx+28h], 1
0x18000314e  call    cs:__imp_GetTickCount
0x180003154  mov     rdx, [rbx+18h]
0x180003158  mov     [rbx+2Ch], eax
0x18000315b  mov     [rbx+30h], r15
0x18000315f  mov     [rbx+38h], r15
0x180003163  mov     [rbx+40h], r15
0x180003167  mov     [rbx+48h], r15
0x18000316b  mov     [rbx+50h], r15
0x18000316f  mov     [rbx+58h], r15
0x180003173  mov     [rbx+60h], r15
0x180003177  mov     [rbx+68h], r15
  ... truncated ...
```
