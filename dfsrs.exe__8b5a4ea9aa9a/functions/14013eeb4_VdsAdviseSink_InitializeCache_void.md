# VdsAdviseSink::InitializeCache(void)

- ea: `0x14013eeb4`
- end: `0x14013fcd7`
- name: `?InitializeCache@VdsAdviseSink@@AEAAXXZ`
- size: `3619`
- prototype: `void __fastcall(VdsAdviseSink *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x14013ed28`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000be44`
- `0x14000cb00`
- `0x14000cc64`
- `0x14000cdc0`
- `0x14000dd10`
- `0x14000e34c`
- `0x1400249f4`
- `0x14003cc2c`
- `0x14003d45c`
- `0x140041f54`
- `0x1400f25ac`
- `0x14013eaec`
- `0x14013ecf4`
- `0x14013ee0c`
- `0x14013eeb4`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14013ef56`
- `KERNEL32!GetCurrentThreadId` at `0x14013f96b`
- `KERNEL32!GetCurrentThreadId` at `0x14013fa79`
- `KERNEL32!GetCurrentThreadId` at `0x14013fb87`
- `KERNEL32!GetCurrentThreadId` at `0x14013ef56`
- `KERNEL32!GetCurrentThreadId` at `0x14013f96b`
- `KERNEL32!GetCurrentThreadId` at `0x14013fa79`
- `KERNEL32!GetCurrentThreadId` at `0x14013fb87`
- `ole32!CoTaskMemFree` at `0x14013f90f`
- `ole32!CoTaskMemFree` at `0x14013f95a`
- `ole32!CoTaskMemFree` at `0x14013f90f`
- `ole32!CoTaskMemFree` at `0x14013f95a`

## string_xrefs

- `0x14013f8a9`: `Insert in cache. VDS_OBJECT_ID:%? volId:%?`
- `0x14013ef92`: `VdsAdviseSink::InitializeCache`
- `0x14013f9a7`: `VdsAdviseSink::InitializeCache`
- `0x14013fab5`: `VdsAdviseSink::InitializeCache`
- `0x14013fbc3`: `VdsAdviseSink::InitializeCache`
- `0x14013ef1d`: `VdsAdviseSink::InitializeCache`
- `0x14013f2e2`: `VdsAdviseSink::InitializeCache`
- `0x14013f388`: `VdsAdviseSink::InitializeCache`
- `0x14013f4d4`: `VdsAdviseSink::InitializeCache`
- `0x14013f582`: `VdsAdviseSink::InitializeCache`
- `0x14013f779`: `VdsAdviseSink::InitializeCache`
- `0x14013f81c`: `VdsAdviseSink::InitializeCache`
- `0x14013f873`: `VdsAdviseSink::InitializeCache`
- `0x14013f9eb`: `VdsAdviseSink::InitializeCache`
- `0x14013faf9`: `VdsAdviseSink::InitializeCache`
- `0x14013fb7b`: `VdsAdviseSink::InitializeCache`
- `0x14013f844`: `(Ignored) Unable to retrieve volume's GUID. Volume will not be added to the cache. This could be a CD ROM. Error:%?`
- `0x14013f7a6`: `volumeMF3->QueryVolumeGuidPathnames(): hr=%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall VdsAdviseSink::InitializeCache(VdsAdviseSink *this)
{
  VdsAdviseSink *v1; // rbx
  struct FrsStatus *v2; // r15
  unsigned int v3; // r13d
  struct ShutdownObject *v4; // rsi
  __int64 CurrentThreadId; // rcx
  __int64 v6; // rdx
  struct FrsStatus *v7; // rax
  int v8; // eax
  const wchar_t *v9; // rdx
  unsigned int v10; // r12d
  int v11; // eax
  const wchar_t *v12; // rdx
  unsigned int v13; // r14d
  int v14; // eax
  const wchar_t *v15; // rdx
  struct FrsStatus *VolumeIdFromVolumeNotification; // r8
  unsigned int v17; // ebx
  unsigned int i; // edx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  struct FrsStatus *v26; // rbx
  __int64 v27; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v28; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+68h] [rbp-A0h]
  const wchar_t *v30; // [rsp+70h] [rbp-98h]
  unsigned int v31[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-78h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, _QWORD); // [rsp+98h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, _QWORD); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-50h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+C0h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-38h] BYREF
  int v43; // [rsp+D8h] [rbp-30h] BYREF
  int v44; // [rsp+DCh] [rbp-2Ch] BYREF
  int v45; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int16 **v46; // [rsp+E8h] [rbp-20h] BYREF
  struct FrsStatus *v47; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-10h] BYREF
  struct FrsStatus *v49; // [rsp+100h] [rbp-8h] BYREF
  VdsAdviseSink *v50; // [rsp+108h] [rbp+0h]
  const wchar_t *v51; // [rsp+110h] [rbp+8h] BYREF
  int v52; // [rsp+118h] [rbp+10h]
  int v53; // [rsp+11Ch] [rbp+14h]
  const wchar_t *v54; // [rsp+120h] [rbp+18h]
  _BYTE v55[96]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v56[56]; // [rsp+188h] [rbp+80h] BYREF
  LPVOID pv; // [rsp+1C0h] [rbp+B8h]
  _BYTE v58[64]; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v59[16]; // [rsp+218h] [rbp+110h] BYREF
  _BYTE v60[64]; // [rsp+228h] [rbp+120h] BYREF

  v1 = this;
  v50 = this;
  LODWORD(v27) = 0;
  v2 = 0;
  v47 = 0;
  v43 = 0;
  v3 = 1;
  v48 = 0;
  v4 = (VdsAdviseSink *)((char *)this + 32);
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 48LL))((char *)this + 32) )
  {
    LODWORD(v27) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)v1 + 2) + 48LL))(
                     *((_QWORD *)v1 + 2),
                     1,
                     &v48);
    if ( (int)v27 < 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = (unsigned int)v27;
      if ( (v27 & 0x1FFF0000) == 0x70000 )
        v6 = (unsigned __int16)v27;
      v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 CurrentThreadId,
                                 v6,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\vdsnotify.cpp",
                                 "VdsAdviseSink::InitializeCache",
                                 423,
                                 CurrentThreadId,
                                 0);
      v2 = v7;
      v47 = v7;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v51 = L"VdsAdviseSink::InitializeCache";
        v52 = 424;
        v53 = 2;
        v54 = L"VDSN";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(
          &v51,
          L"Failed to QueryProviders(VDS_QUERY_SOFTWARE_PROVIDERS). Error:%?",
          v7);
      }
    }
  }
  while ( 1 )
  {
    if ( v2 )
      goto LABEL_150;
    if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
      goto LABEL_151;
    v39 = 0;
    v38 = 0;
    v37 = 0;
    v36 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
      goto LABEL_18;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD), int *))(*(_QWORD *)v48 + 24LL))(
           v48,
           1,
           &v38,
           &v43);
    LODWORD(v27) = v8;
    if ( v8 == 1 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      goto LABEL_151;
    }
    if ( v8 < 0 )
      break;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v28 = L"VdsAdviseSink::InitializeCache";
      v29 = 0x4000001C7LL;
      v30 = L"VDSN";
      v31[0] = v3++;
      dbgobj::DbgPrint<unsigned short,unsigned int,unsigned int>(&v28, L"Fetched:%?, Provider#:%?", &v43, v31);
    }
LABEL_18:
    if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
    {
      LODWORD(v27) = (**v38)(v38, &IID_IVdsProvider, &v37);
      if ( (_DWORD)v27 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
          goto LABEL_140;
        LODWORD(v29) = 466;
        v9 = L"unknown->QueryInterface(IVdsProvider): hr=%?";
        goto LABEL_24;
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
    {
      LODWORD(v27) = (**v37)(v37, &IID_IVdsSwProvider, &v36);
      if ( (_DWORD)v27 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
          goto LABEL_140;
        LODWORD(v29) = 478;
        v9 = L"provider->QueryInterface(IVdsSwProvider): hr=%?";
        goto LABEL_24;
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
    {
      LODWORD(v27) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 24LL))(v36, &v39);
      if ( (_DWORD)v27 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
          goto LABEL_140;
        LODWORD(v29) = 490;
        v9 = L"swProvider->QueryPacks(): hr=%?";
LABEL_24:
        v28 = L"VdsAdviseSink::InitializeCache";
        HIDWORD(v29) = 2;
        v30 = L"VDSN";
        dbgobj::DbgPrint<unsigned short,unsigned int>(&v28, v9, &v27);
        goto LABEL_140;
      }
    }
    v44 = 0;
    v10 = 1;
    while ( 1 )
    {
      if ( v2 || (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
        goto LABEL_140;
      v42 = 0;
      v41 = 0;
      v40 = 0;
      if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
        break;
LABEL_48:
      if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
      {
        LODWORD(v27) = (**v40)(v40, &IID_IVdsPack, &v41);
        if ( (_DWORD)v27 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            LODWORD(v29) = 534;
            v12 = L"packUnknown->QueryInterface(IVdsPack): hr=%?";
LABEL_54:
            v28 = L"VdsAdviseSink::InitializeCache";
            v30 = L"VDSN";
            HIDWORD(v29) = 4;
            dbgobj::DbgPrint<unsigned short,unsigned int>(&v28, v12, &v27);
            goto LABEL_130;
          }
          goto LABEL_130;
        }
      }
      if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4)
        || (LODWORD(v27) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 40LL))(v41, &v42),
            !(_DWORD)v27) )
      {
        v45 = 0;
        v13 = 1;
        while ( 1 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
            goto LABEL_130;
          v35 = 0;
          v32 = 0;
          v34 = 0;
          v33 = 0;
          memset_0(v56, 0, 0x48u);
          if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
          {
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD), int *))(*(_QWORD *)v42 + 24LL))(
                    v42,
                    1,
                    &v35,
                    &v45);
            LODWORD(v27) = v14;
            if ( v14 == 1 )
              goto LABEL_129;
            if ( v14 < 0 )
            {
              v20 = GetCurrentThreadId();
              v21 = (unsigned int)v27;
              if ( (int)v27 < 0 )
              {
                if ( (v27 & 0x1FFF0000) == 0x70000 )
                  v21 = (unsigned __int16)v27;
              }
              else
              {
                v21 = 0;
              }
              v2 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v20,
                                         v21,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\sync\\vdsnotify.cpp",
                                         "VdsAdviseSink::InitializeCache",
                                         579,
                                         v20,
                                         0);
              v47 = v2;
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v28 = L"VdsAdviseSink::InitializeCache";
                v29 = 0x200000244LL;
                v30 = L"VDSN";
                dbgobj::DbgPrint<unsigned short,FrsStatus>(&v28, L"Failed to enumVolume->Next(). Error:%?", v2);
              }
LABEL_129:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              goto LABEL_130;
            }
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v28 = L"VdsAdviseSink::InitializeCache";
              v29 = 0x400000248LL;
              v30 = L"VDSN";
              v31[0] = v13++;
              dbgobj::DbgPrint<unsigned short,unsigned int,unsigned int>(&v28, L"Fetched:%?, Volume#:%?", &v45, v31);
            }
          }
          if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4)
            || (LODWORD(v27) = (**v35)(v35, &IID_IVdsVolume, &v32), !(_DWORD)v27) )
          {
            if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4)
              || (LODWORD(v27) = (**v32)(v32, &IID_IVdsVolume2, &v34), !(_DWORD)v27) )
            {
              if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4)
                || (LODWORD(v27) = (**v32)(v32, &IID_IVdsVolumeMF3, &v33), !(_DWORD)v27) )
              {
                if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4)
                  || (LODWORD(v27) = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v34 + 24LL))(v34, v56),
                      !(_DWORD)v27) )
                {
                  if ( !(*(unsigned __int8 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v4 + 48LL))(v4) )
                  {
                    v46 = 0;
                    v31[0] = 0;
                    LODWORD(v27) = (*(__int64 (__fastcall **)(__int64, unsigned __int16 ***, unsigned int *))(*(_QWORD *)v33 + 24LL))(
                                     v33,
                                     &v46,
                                     v31);
                    if ( (int)v27 >= 0 )
                    {
                      VolumeId::VolumeId((VolumeId *)v58);
                      VolumeIdTable::VolumeIdTable((VolumeIdTable *)v55);
                      VolumeIdFromVolumeNotification = VolumeIdTable::GetVolumeIdFromVolumeNotification(
                                                         (VolumeIdTable *)v55,
                                                         v46,
                                                         v31[0],
                                                         v4,
                                                         (struct VolumeId *)v58,
                                                         0);
                      v49 = VolumeIdFromVolumeNotification;
                      if ( VolumeIdFromVolumeNotification )
                      {
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                        {
                          v28 = L"VdsAdviseSink::InitializeCache";
                          v29 = 0x300000293LL;
                          v30 = L"VDSN";
                          dbgobj::DbgPrint<unsigned short,FrsStatus>(
                            &v28,
                            L"(Ignored) Unable to retrieve volume's GUID. Volume will not be added to the cache. This coul"
                             "d be a CD ROM. Error:%?",
                            VolumeIdFromVolumeNotification);
                        }
                        CLEAR_ERROR(&v49);
                      }
                      else
                      {
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                        {
                          v28 = L"VdsAdviseSink::InitializeCache";
                          v29 = 0x400000299LL;
                          v30 = L"VDSN";
                          dbgobj::DbgPrint<unsigned short,_GUID,VolumeId>(
                            &v28,
                            L"Insert in cache. VDS_OBJECT_ID:%? volId:%?",
                            v56,
                            v58);
                        }
                        std::pair<_GUID,VolumeId>::pair<_GUID,VolumeId>(v59, v56, v58);
                        std::map<_GUID,VolumeId>::insert<std::pair<_GUID,VolumeId>,0>((char *)v1 + 56, &v51, v59);
                        VolumeId::~VolumeId((VolumeId *)v60);
                      }
                      v17 = 0;
                      for ( i = v31[0]; v17 < i; ++v17 )
                      {
                        v19 = v46[v17];
                        if ( v19 )
                        {
                          CoTaskMemFree(v19);
                          v46[v17] = 0;
                          i = v31[0];
                        }
                      }
                      VolumeIdTable::~VolumeIdTable((VolumeIdTable *)v55);
                      VolumeId::~VolumeId((VolumeId *)v58);
                      v1 = v50;
                    }
                    else if ( g_DebugLog
                           && LODWORD(g_DebugLog[1].LockSemaphore)
                           && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                    {
                      v28 = L"VdsAdviseSink::InitializeCache";
                      v29 = 0x200000285LL;
                      v30 = L"VDSN";
                      dbgobj::DbgPrint<unsigned short,unsigned int>(
                        &v28,
                        L"volumeMF3->QueryVolumeGuidPathnames(): hr=%?",
                        &v27);
                    }
                    scoped_any<unsigned short * *,close_fun<void (*)(void *),&void CoTaskMemFree(void *)>,null_t,0>::~scoped_any<unsigned short * *,close_fun<void (*)(void *),&void CoTaskMemFree(void *)>,null_t,0>(&v46);
                  }
                  CoTaskMemFree(pv);
                }
                else if ( g_DebugLog
                       && LODWORD(g_DebugLog[1].LockSemaphore)
                       && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                {
                  LODWORD(v29) = 631;
                  v15 = L"volume2->GetProperties2(): hr=%?";
                  goto LABEL_77;
                }
              }
              else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
              {
                LODWORD(v29) = 619;
                v15 = L"volume->QueryInterface(IVdsVolumeMF3): hr=%?";
                goto LABEL_77;
              }
            }
            else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              LODWORD(v29) = 607;
              v15 = L"volume->QueryInterface(IVdsVolume2): hr=%?";
              goto LABEL_77;
            }
          }
          else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            LODWORD(v29) = 595;
            v15 = L"volumeUnk->QueryInterface(IVdsVolume): hr=%?";
LABEL_77:
            v28 = L"VdsAdviseSink::InitializeCache";
            v30 = L"VDSN";
            HIDWORD(v29) = 4;
            dbgobj::DbgPrint<unsigned short,unsigned int>(&v28, v15, &v27);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        }
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        LODWORD(v29) = 546;
        v12 = L"pack->QueryVolumes(): hr=%?";
        goto LABEL_54;
      }
LABEL_130:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
    }
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v39 + 24LL))(
            v39,
            1,
            &v40,
            &v44);
    LODWORD(v27) = v11;
    if ( v11 == 1 )
      goto LABEL_139;
    if ( v11 >= 0 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v28 = L"VdsAdviseSink::InitializeCache";
        v29 = 0x40000020BLL;
        v30 = L"VDSN";
        v31[0] = v10++;
        dbgobj::DbgPrint<unsigned short,unsigned int,unsigned int>(&v28, L"Fetched:%?, Pack#:%?", &v44, v31);
      }
      goto LABEL_48;
    }
    v22 = GetCurrentThreadId();
    v23 = (unsigned int)v27;
    if ( (int)v27 < 0 )
    {
      if ( (v27 & 0x1FFF0000) == 0x70000 )
        v23 = (unsigned __int16)v27;
    }
    else
    {
      v23 = 0;
    }
    v2 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v22,
                               v23,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\sync\\vdsnotify.cpp",
                               "VdsAdviseSink::InitializeCache",
                               518,
                               v22,
                               0);
    v47 = v2;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v28 = L"VdsAdviseSink::InitializeCache";
      v29 = 0x200000207LL;
      v30 = L"VDSN";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v28, L"Failed to enumPack->Next(). Error:%?", v2);
    }
LABEL_139:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
LABEL_140:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  }
  v24 = GetCurrentThreadId();
  v25 = (unsigned int)v27;
  if ( (int)v27 < 0 )
  {
    if ( (v27 & 0x1FFF0000) == 0x70000 )
      v25 = (unsigned __int16)v27;
  }
  else
  {
    v25 = 0;
  }
  v26 = (struct FrsStatus *)FrsStatusList::PushNewError(
                              v24,
                              v25,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\sync\\vdsnotify.cpp",
                              "VdsAdviseSink::InitializeCache",
                              450,
                              v24,
                              0);
  v47 = v26;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v28 = L"VdsAdviseSink::InitializeCache";
    v29 = 0x2000001C3LL;
    v30 = L"VDSN";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v28, L"Failed to enumProvider->Next(). Error:%?", v26);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  if ( v26 )
LABEL_150:
    CLEAR_ERROR(&v47);
LABEL_151:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
}

```

## disassembly

```asm
0x14013eeb4  mov     rax, rsp
0x14013eeb7  mov     [rax+10h], rbx
0x14013eebb  mov     [rax+18h], rsi
0x14013eebf  mov     [rax+20h], rdi
0x14013eec3  push    rbp
0x14013eec4  push    r12
0x14013eec6  push    r13
0x14013eec8  push    r14
0x14013eeca  push    r15
0x14013eecc  lea     rbp, [rax-198h]
0x14013eed3  sub     rsp, 270h
0x14013eeda  mov     rax, cs:__security_cookie
0x14013eee1  xor     rax, rsp
0x14013eee4  mov     [rbp+190h+var_30], rax
0x14013eeeb  mov     rbx, rcx
0x14013eeee  mov     [rbp+190h+var_190], rcx
0x14013eef2  xor     edi, edi
0x14013eef4  mov     dword ptr [rsp+290h+var_240], edi
0x14013eef8  mov     r15d, edi
0x14013eefb  mov     [rbp+190h+var_1A8], rdi
0x14013eeff  mov     [rbp+190h+var_1C0], edi
0x14013ef02  lea     r13d, [rdi+1]
0x14013ef06  mov     [rbp+190h+var_1A0], rdi
0x14013ef0a  lea     rsi, [rcx+20h]
0x14013ef0e  mov     rax, [rsi]
0x14013ef11  mov     rcx, rsi
0x14013ef14  mov     rax, [rax+30h]
0x14013ef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013ef1d  lea     r12, aVdsadvisesinkI; "VdsAdviseSink::InitializeCache"
0x14013ef24  lea     r14, aVdsn; "VDSN"
0x14013ef2b  test    al, al
0x14013ef2d  jnz     loc_14013EFFF
0x14013ef33  mov     rcx, [rbx+10h]
0x14013ef37  mov     rax, [rcx]
0x14013ef3a  lea     r8, [rbp+190h+var_1A0]
0x14013ef3e  mov     edx, r13d
0x14013ef41  mov     rax, [rax+30h]
0x14013ef45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013ef4a  mov     dword ptr [rsp+290h+var_240], eax
0x14013ef4e  test    eax, eax
0x14013ef50  jns     loc_14013EFFF
0x14013ef56  call    cs:__imp_GetCurrentThreadId
0x14013ef5d  nop     dword ptr [rax+rax+00h]
0x14013ef62  mov     ecx, eax
0x14013ef64  mov     edx, dword ptr [rsp+290h+var_240]
0x14013ef68  test    edx, edx
0x14013ef6a  js      short loc_14013EF70
0x14013ef6c  mov     edx, edi
0x14013ef6e  jmp     short loc_14013EF81
0x14013ef70  mov     eax, edx
0x14013ef72  and     eax, 1FFF0000h
0x14013ef77  cmp     eax, 70000h
0x14013ef7c  jnz     short loc_14013EF81
0x14013ef7e  movzx   edx, dx
0x14013ef81  mov     [rsp+290h+var_250], rdi
0x14013ef86  mov     dword ptr [rsp+290h+var_258], ecx
0x14013ef8a  mov     [rsp+290h+var_260], 1A7h
0x14013ef92  lea     rax, aVdsadvisesinkI_0; "VdsAdviseSink::InitializeCache"
0x14013ef99  mov     [rsp+290h+var_268], rax
0x14013ef9e  lea     rax, aBaseFsRemotefs_104; "base\\fs\\remotefs\\frs\\src\\sync\\vds"...
0x14013efa5  mov     [rsp+290h+var_270], rax
0x14013efaa  mov     r9d, 1
0x14013efb0  xor     r8d, r8d
0x14013efb3  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14013efb8  mov     r15, rax
0x14013efbb  mov     [rbp+190h+var_1A8], rax
0x14013efbf  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013efc6  test    rcx, rcx
0x14013efc9  jz      short loc_14013EFFF
0x14013efcb  cmp     [rcx+40h], edi
0x14013efce  jz      short loc_14013EFFF
0x14013efd0  cmp     dword ptr [rcx+38h], 2
0x14013efd4  jl      short loc_14013EFFF
0x14013efd6  mov     [rbp+190h+var_188], r12
0x14013efda  mov     [rbp+190h+var_180], 1A8h
0x14013efe1  mov     [rbp+190h+var_17C], 2
0x14013efe8  mov     [rbp+190h+var_178], r14
0x14013efec  mov     r8, rax
0x14013efef  lea     rdx, aFailedToQueryp; "Failed to QueryProviders(VDS_QUERY_SOFT"...
0x14013eff6  lea     rcx, [rbp+190h+var_188]
0x14013effa  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14013efff  mov     r14d, 4
0x14013f005  test    r15, r15
0x14013f008  jnz     loc_14013FC69
0x14013f00e  mov     rax, [rsi]
0x14013f011  mov     rcx, rsi
0x14013f014  mov     rax, [rax+30h]
0x14013f018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f01d  test    al, al
0x14013f01f  jnz     loc_14013FC73
0x14013f025  mov     [rbp+190h+var_1E0], rdi
0x14013f029  mov     [rbp+190h+var_1E8], rdi
0x14013f02d  mov     [rbp+190h+var_1F0], rdi
0x14013f031  mov     [rbp+190h+var_1F8], rdi
0x14013f035  mov     rax, [rsi]
0x14013f038  mov     rcx, rsi
0x14013f03b  mov     rax, [rax+30h]
0x14013f03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f044  test    al, al
0x14013f046  jnz     loc_14013F0D4
0x14013f04c  mov     rcx, [rbp+190h+var_1A0]
0x14013f050  mov     rax, [rcx]
0x14013f053  lea     r9, [rbp+190h+var_1C0]
0x14013f057  lea     r8, [rbp+190h+var_1E8]
0x14013f05b  lea     edx, [r15+1]
0x14013f05f  mov     rax, [rax+18h]
0x14013f063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f068  mov     dword ptr [rsp+290h+var_240], eax
0x14013f06c  cmp     eax, 1
0x14013f06f  jz      loc_14013FCAD
0x14013f075  test    eax, eax
0x14013f077  js      loc_14013FB87
0x14013f07d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013f084  test    rax, rax
0x14013f087  jz      short loc_14013F0D4
0x14013f089  cmp     [rax+40h], edi
0x14013f08c  jz      short loc_14013F0D4
0x14013f08e  cmp     [rax+38h], r14d
0x14013f092  jl      short loc_14013F0D4
0x14013f094  mov     [rsp+290h+var_238], r12
0x14013f099  mov     dword ptr [rsp+290h+var_230], 1C7h
0x14013f0a1  mov     dword ptr [rsp+290h+var_230+4], r14d
0x14013f0a6  lea     rax, aVdsn; "VDSN"
0x14013f0ad  mov     [rsp+290h+var_228], rax
0x14013f0b2  mov     [rsp+290h+var_220], r13d
0x14013f0b7  inc     r13d
0x14013f0ba  lea     r9, [rsp+290h+var_220]
0x14013f0bf  lea     r8, [rbp+190h+var_1C0]
0x14013f0c3  lea     rdx, aFetchedProvide; "Fetched:%?, Provider#:%?"
0x14013f0ca  lea     rcx, [rsp+290h+var_238]
0x14013f0cf  call    ??$DbgPrint@GII@dbgobj@@QEAA_KPEBGAEBI1@Z; dbgobj::DbgPrint<ushort,uint,uint>(ushort const *,uint const &,uint const &)
0x14013f0d4  mov     rax, [rsi]
0x14013f0d7  mov     rcx, rsi
0x14013f0da  mov     rax, [rax+30h]
0x14013f0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f0e3  test    al, al
0x14013f0e5  jnz     loc_14013F188
0x14013f0eb  mov     rcx, [rbp+190h+var_1E8]
0x14013f0ef  mov     rax, [rcx]
0x14013f0f2  lea     r8, [rbp+190h+var_1F0]
0x14013f0f6  lea     rdx, IID_IVdsProvider
0x14013f0fd  mov     rax, [rax]
0x14013f100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f105  mov     dword ptr [rsp+290h+var_240], eax
0x14013f109  test    eax, eax
0x14013f10b  jz      short loc_14013F188
0x14013f10d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013f114  test    rax, rax
0x14013f117  jz      short loc_14013F15C
0x14013f119  cmp     [rax+40h], edi
0x14013f11c  jz      short loc_14013F15C
0x14013f11e  cmp     dword ptr [rax+38h], 2
0x14013f122  jl      short loc_14013F15C
0x14013f124  mov     dword ptr [rsp+290h+var_230], 1D2h
0x14013f12c  lea     rdx, aUnknownQueryin; "unknown->QueryInterface(IVdsProvider): "...
0x14013f133  lea     rax, aVdsn; "VDSN"
0x14013f13a  mov     [rsp+290h+var_238], r12
0x14013f13f  mov     dword ptr [rsp+290h+var_230+4], 2
0x14013f147  mov     [rsp+290h+var_228], rax
0x14013f14c  lea     r8, [rsp+290h+var_240]
0x14013f151  lea     rcx, [rsp+290h+var_238]
0x14013f156  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14013f15b  nop
0x14013f15c  lea     rcx, [rbp+190h+var_1F8]
0x14013f160  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14013f165  nop
0x14013f166  lea     rcx, [rbp+190h+var_1F0]
0x14013f16a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14013f16f  nop
0x14013f170  lea     rcx, [rbp+190h+var_1E8]
0x14013f174  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14013f179  nop
0x14013f17a  lea     rcx, [rbp+190h+var_1E0]
0x14013f17e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14013f183  jmp     loc_14013F005
0x14013f188  mov     rax, [rsi]
0x14013f18b  mov     rcx, rsi
0x14013f18e  mov     rax, [rax+30h]
0x14013f192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f197  test    al, al
0x14013f199  jnz     short loc_14013F1E8
0x14013f19b  mov     rcx, [rbp+190h+var_1F0]
0x14013f19f  mov     rax, [rcx]
0x14013f1a2  lea     r8, [rbp+190h+var_1F8]
0x14013f1a6  lea     rdx, IID_IVdsSwProvider
0x14013f1ad  mov     rax, [rax]
0x14013f1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f1b5  mov     dword ptr [rsp+290h+var_240], eax
0x14013f1b9  test    eax, eax
0x14013f1bb  jz      short loc_14013F1E8
0x14013f1bd  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013f1c4  test    rax, rax
0x14013f1c7  jz      short loc_14013F15C
0x14013f1c9  cmp     [rax+40h], edi
0x14013f1cc  jz      short loc_14013F15C
0x14013f1ce  cmp     dword ptr [rax+38h], 2
0x14013f1d2  jl      short loc_14013F15C
0x14013f1d4  mov     dword ptr [rsp+290h+var_230], 1DEh
0x14013f1dc  lea     rdx, aProviderQueryi; "provider->QueryInterface(IVdsSwProvider"...
0x14013f1e3  jmp     loc_14013F133
0x14013f1e8  mov     rax, [rsi]
0x14013f1eb  mov     rcx, rsi
0x14013f1ee  mov     rax, [rax+30h]
0x14013f1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f1f7  test    al, al
0x14013f1f9  jnz     short loc_14013F24E
0x14013f1fb  mov     rcx, [rbp+190h+var_1F8]
0x14013f1ff  mov     rax, [rcx]
0x14013f202  lea     rdx, [rbp+190h+var_1E0]
0x14013f206  mov     rax, [rax+18h]
0x14013f20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f20f  mov     dword ptr [rsp+290h+var_240], eax
0x14013f213  test    eax, eax
0x14013f215  jz      short loc_14013F24E
0x14013f217  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013f21e  test    rax, rax
0x14013f221  jz      loc_14013F15C
0x14013f227  cmp     [rax+40h], edi
0x14013f22a  jz      loc_14013F15C
0x14013f230  cmp     dword ptr [rax+38h], 2
0x14013f234  jl      loc_14013F15C
0x14013f23a  mov     dword ptr [rsp+290h+var_230], 1EAh
0x14013f242  lea     rdx, aSwproviderQuer; "swProvider->QueryPacks(): hr=%?"
0x14013f249  jmp     loc_14013F133
0x14013f24e  mov     [rbp+190h+var_1BC], edi
0x14013f251  mov     r12d, 1
0x14013f257  test    r15, r15
0x14013f25a  jnz     loc_14013FB54
0x14013f260  mov     rax, [rsi]
0x14013f263  mov     rcx, rsi
0x14013f266  mov     rax, [rax+30h]
0x14013f26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f26f  test    al, al
0x14013f271  jnz     loc_14013FB54
0x14013f277  mov     [rbp+190h+var_1C8], rdi
0x14013f27b  mov     [rbp+190h+var_1D0], rdi
0x14013f27f  mov     [rbp+190h+var_1D8], rdi
0x14013f283  mov     rax, [rsi]
0x14013f286  mov     rcx, rsi
0x14013f289  mov     rax, [rax+30h]
0x14013f28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f292  test    al, al
0x14013f294  jnz     loc_14013F329
0x14013f29a  mov     rcx, [rbp+190h+var_1E0]
0x14013f29e  mov     rax, [rcx]
0x14013f2a1  lea     r9, [rbp+190h+var_1BC]
0x14013f2a5  lea     r8, [rbp+190h+var_1D8]
0x14013f2a9  lea     edx, [r15+1]
0x14013f2ad  mov     rax, [rax+18h]
0x14013f2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f2b6  mov     dword ptr [rsp+290h+var_240], eax
0x14013f2ba  cmp     eax, 1
0x14013f2bd  jz      loc_14013FB36
0x14013f2c3  test    eax, eax
0x14013f2c5  js      loc_14013FA79
0x14013f2cb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013f2d2  test    rax, rax
0x14013f2d5  jz      short loc_14013F329
0x14013f2d7  cmp     [rax+40h], edi
0x14013f2da  jz      short loc_14013F329
0x14013f2dc  cmp     [rax+38h], r14d
0x14013f2e0  jl      short loc_14013F329
0x14013f2e2  lea     rax, aVdsadvisesinkI; "VdsAdviseSink::InitializeCache"
0x14013f2e9  mov     [rsp+290h+var_238], rax
0x14013f2ee  mov     dword ptr [rsp+290h+var_230], 20Bh
0x14013f2f6  mov     dword ptr [rsp+290h+var_230+4], r14d
0x14013f2fb  lea     rax, aVdsn; "VDSN"
0x14013f302  mov     [rsp+290h+var_228], rax
0x14013f307  mov     [rsp+290h+var_220], r12d
0x14013f30c  inc     r12d
0x14013f30f  lea     r9, [rsp+290h+var_220]
0x14013f314  lea     r8, [rbp+190h+var_1BC]
0x14013f318  lea     rdx, aFetchedPack; "Fetched:%?, Pack#:%?"
0x14013f31f  lea     rcx, [rsp+290h+var_238]
0x14013f324  call    ??$DbgPrint@GII@dbgobj@@QEAA_KPEBGAEBI1@Z; dbgobj::DbgPrint<ushort,uint,uint>(ushort const *,uint const &,uint const &)
0x14013f329  mov     rax, [rsi]
0x14013f32c  mov     rcx, rsi
0x14013f32f  mov     rax, [rax+30h]
0x14013f333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f338  test    al, al
0x14013f33a  jnz     loc_14013F3D7
0x14013f340  mov     rcx, [rbp+190h+var_1D8]
0x14013f344  mov     rax, [rcx]
0x14013f347  lea     r8, [rbp+190h+var_1D0]
0x14013f34b  lea     rdx, IID_IVdsPack
0x14013f352  mov     rax, [rax]
0x14013f355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013f35a  mov     dword ptr [rsp+290h+var_240], eax
0x14013f35e  test    eax, eax
0x14013f360  jz      short loc_14013F3D7
0x14013f362  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013f369  test    rax, rax
0x14013f36c  jz      short loc_14013F3B5
0x14013f36e  cmp     [rax+40h], edi
0x14013f371  jz      short loc_14013F3B5
0x14013f373  cmp     [rax+38h], r14d
0x14013f377  jl      short loc_14013F3B5
0x14013f379  mov     dword ptr [rsp+290h+var_230], 216h
0x14013f381  lea     rdx, aPackunknownQue; "packUnknown->QueryInterface(IVdsPack): "...
0x14013f388  lea     rax, aVdsadvisesinkI; "VdsAdviseSink::InitializeCache"
  ... truncated ...
```
