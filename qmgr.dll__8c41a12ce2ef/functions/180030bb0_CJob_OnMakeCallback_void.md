# CJob::OnMakeCallback(void)

- ea: `0x180030bb0`
- end: `0x180031b5c`
- name: `?OnMakeCallback@CJob@@UEAAXXZ`
- size: `4012`
- prototype: `void __fastcall(CJob *__hidden this)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000b4d0`
- `0x18001e1d0`
- `0x18002c6ac`
- `0x180030bb0`
- `0x180031b64`
- `0x180031d74`
- `0x180031db0`
- `0x180034760`
- `0x180039ef0`
- `0x180060058`
- `0x180063740`
- `0x180063fa0`
- `0x180071990`
- `0x1800765dc`
- `0x1800890ac`
- `0x18009d024`
- `0x18009e89c`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x1800b1fe8`
- `0x1800cc300`
- `0x1800cfb1c`
- `0x1800d13b4`
- `0x1800d19c4`
- `0x1800f1804`
- `0x1800f64f4`
- `0x1800f9948`
- `0x1800f9954`
- `0x18010f010`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x1800318a4`
- `combase!__imp_CoAddRefSharedService` at `0x1800318a4`
- `combase!__imp_CoReleaseSharedService` at `0x180031a61`
- `combase!__imp_CoReleaseSharedService` at `0x180031a61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031707`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030cb1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003130e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030cb1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003130e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003135d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003135d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030c6b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031b1a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030c6b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031b1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003187a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003187a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800312af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800312af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031919`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031919`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180030da7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031301`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180030da7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031301`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800313ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800313ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800313d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800313d9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180030cfc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180030cfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall CJob::OnMakeCallback(CJob *this)
{
  const char *CallbackName; // rax
  __int64 v3; // r10
  CJobManager *v4; // rbx
  HANDLE *Value; // rax
  void *v6; // rcx
  DWORD v7; // eax
  bool v8; // dl
  volatile __int32 *v9; // r13
  int v10; // edx
  void *v11; // r10
  int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  char v16; // di
  __int64 v17; // r14
  __int64 v18; // rsi
  __int64 v19; // r12
  __int64 *OldGroupExternal; // rax
  __int64 *OldJobExternal; // rax
  char v22; // bl
  __int64 v23; // rbx
  char *v24; // rdi
  __int64 v25; // r15
  CJob *v26; // rbx
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int128 v29; // xmm6
  __int64 v30; // rdx
  volatile signed __int32 *v31; // rdi
  volatile signed __int32 *v32; // rbx
  CJobManager *v33; // r13
  CJobManager *v34; // r13
  char *v35; // r13
  int v36; // ecx
  bool v37; // zf
  unsigned __int64 v38; // r13
  __int64 v39; // rcx
  unsigned __int64 v40; // rax
  __int64 FileExternal; // rax
  int v42; // ecx
  int v43; // ecx
  CJob *v44; // rcx
  EVENT_LOG *v45; // r10
  _DWORD *v46; // r13
  int v47; // eax
  bool IsNotificationCallbackPending; // al
  unsigned int v49; // eax
  EVENT_LOG *v50; // rcx
  int i; // r13d
  __int64 v52; // rcx
  unsigned int v53; // eax
  __int16 v54; // di
  DWORD v55; // ebx
  const char *v56; // rax
  __int64 v57; // r10
  int v58; // [rsp+50h] [rbp-318h]
  volatile __int32 *v59; // [rsp+58h] [rbp-310h]
  __int64 v60; // [rsp+60h] [rbp-308h] BYREF
  __int64 v61; // [rsp+68h] [rbp-300h] BYREF
  unsigned __int64 v62; // [rsp+70h] [rbp-2F8h] BYREF
  int v63; // [rsp+78h] [rbp-2F0h]
  unsigned int v64; // [rsp+7Ch] [rbp-2ECh] BYREF
  unsigned int v65; // [rsp+80h] [rbp-2E8h] BYREF
  unsigned int v66; // [rsp+84h] [rbp-2E4h]
  DWORD dwMilliseconds; // [rsp+88h] [rbp-2E0h]
  TaskScheduler *v68[2]; // [rsp+90h] [rbp-2D8h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-2C8h] BYREF
  void *v70; // [rsp+A8h] [rbp-2C0h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-2B8h] BYREF
  __int64 v72; // [rsp+B8h] [rbp-2B0h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-2A8h] BYREF
  __int64 v74; // [rsp+C8h] [rbp-2A0h]
  __int64 v75; // [rsp+D0h] [rbp-298h]
  __int64 v76; // [rsp+D8h] [rbp-290h]
  __int64 v77; // [rsp+E0h] [rbp-288h]
  __int64 v78; // [rsp+E8h] [rbp-280h]
  HANDLE Handles[2]; // [rsp+F0h] [rbp-278h] BYREF
  __int128 v80; // [rsp+100h] [rbp-268h] BYREF
  _QWORD v81[3]; // [rsp+110h] [rbp-258h] BYREF
  DWORD v82; // [rsp+128h] [rbp-240h]
  volatile signed __int32 *v83; // [rsp+130h] [rbp-238h]
  void **v84; // [rsp+140h] [rbp-228h] BYREF
  __int128 v85; // [rsp+148h] [rbp-220h]
  int v86; // [rsp+158h] [rbp-210h]
  int v87; // [rsp+15Ch] [rbp-20Ch]
  int v88; // [rsp+160h] [rbp-208h]
  void **pExceptionObject; // [rsp+1A0h] [rbp-1C8h] BYREF
  __int128 v90; // [rsp+1A8h] [rbp-1C0h]
  int v91; // [rsp+1B8h] [rbp-1B0h]
  int v92; // [rsp+1BCh] [rbp-1ACh]
  int v93; // [rsp+1C0h] [rbp-1A8h]
  void **v94; // [rsp+200h] [rbp-168h] BYREF
  __int128 v95; // [rsp+208h] [rbp-160h]
  int v96; // [rsp+218h] [rbp-150h]
  int v97; // [rsp+21Ch] [rbp-14Ch]
  int v98; // [rsp+220h] [rbp-148h]
  void **v99; // [rsp+260h] [rbp-108h] BYREF
  __int128 v100; // [rsp+268h] [rbp-100h]
  int v101; // [rsp+278h] [rbp-F0h]
  int v102; // [rsp+27Ch] [rbp-ECh]
  int v103; // [rsp+280h] [rbp-E8h]
  volatile signed __int32 *v105; // [rsp+378h] [rbp+10h] BYREF
  CJobManager *v106; // [rsp+380h] [rbp+18h]
  volatile signed __int32 *v107; // [rsp+388h] [rbp+20h] BYREF

  LODWORD(v105) = 0;
  dwMilliseconds = *((_DWORD *)g_GlobalInfo + 52);
  v74 = *((_QWORD *)g_GlobalInfo + 25);
  v81[0] = *((_QWORD *)g_GlobalInfo + 24);
  v81[1] = v74;
  v81[2] = 0x2000;
  v82 = dwMilliseconds;
  if ( (v81[0] & 0x2000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CallbackName = CallbackSleepHelper::GetCallbackName(0x2000u);
      WPP_SF_s(*(_QWORD *)(v3 + 16), 10, &WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, CallbackName);
    }
    Sleep(dwMilliseconds);
  }
  v4 = g_Manager;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  Value = (HANDLE *)TlsGetValue(*((_DWORD *)v4 + 143));
  v6 = (void *)*((_QWORD *)v4 + 70);
  if ( !Value || !Value[6] )
  {
    WaitForSingleObject(v6, 0xFFFFFFFF);
    *((_DWORD *)v4 + 144) = GetCurrentThreadId();
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
LABEL_23:
    v9 = (volatile __int32 *)((char *)this - 192);
    v59 = (volatile __int32 *)((char *)this - 192);
    if ( this != (CJob *)192 )
      RefCountedObject::AddRef((RefCountedObject *)(v9 + 150));
    LOBYTE(v106) = 0;
    if ( (v9[201] & 0x14) != 0x10 )
      goto LABEL_28;
    if ( *((_BYTE *)v9 + 1344) )
    {
      if ( !*((_QWORD *)v9 + 171) )
      {
LABEL_28:
        if ( CJob::IsCallbackEnabled((CJob *)((char *)this - 192), 1u)
          && *((_DWORD *)v9 + 165) == 6
          && *((_DWORD *)v9 + 73) == v10 )
        {
          v12 = v10;
LABEL_48:
          *((_DWORD *)this + 25) = (_DWORD)v11;
          v58 = v12;
          goto LABEL_50;
        }
        if ( CJob::IsCallbackEnabled((CJob *)((char *)this - 192), 2u)
          && *((_DWORD *)v9 + 165) == 4
          && *((_DWORD *)v9 + 73) == 2 )
        {
          v12 = 2;
          goto LABEL_48;
        }
        v12 = (int)v11;
        v58 = (int)v11;
LABEL_50:
        LODWORD(v107) = v12;
        v16 = *((_BYTE *)this + 1152);
        LOBYTE(v105) = v16;
        v17 = (__int64)v11;
        v75 = (__int64)v11;
        v18 = (__int64)v11;
        v76 = (__int64)v11;
        v19 = (__int64)v11;
        v77 = (__int64)v11;
        if ( !v16 )
          goto LABEL_65;
        OldGroupExternal = (__int64 *)CJob::GetOldGroupExternal((__int64)this - 192, (__int64)&v62);
        v17 = 0;
        if ( &v71 != OldGroupExternal )
        {
          v17 = *OldGroupExternal;
          *OldGroupExternal = 0;
        }
        v71 = 0;
        v75 = v17;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
        if ( *((_BYTE *)this + 1184) )
        {
          OldJobExternal = (__int64 *)CJob::GetOldJobExternal((char *)this - 192, &v62);
          v18 = 0;
          v22 = 1;
          if ( &v72 == OldJobExternal )
            goto LABEL_58;
        }
        else
        {
          v61 = 0;
          OldJobExternal = &v61;
          v22 = 2;
        }
        v18 = *OldJobExternal;
        *OldJobExternal = 0;
LABEL_58:
        v72 = 0;
        v76 = v18;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        if ( (v22 & 2) != 0 )
        {
          v22 &= ~2u;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
        }
        if ( (v22 & 1) != 0 )
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
        v23 = *((_QWORD *)this + 147);
        if ( v23 )
        {
          v60 = *((_QWORD *)this + 147);
          Microsoft::WRL::ComPtr<IBackgroundCopyCallback1>::InternalAddRef(&v60);
          v60 = 0;
          v19 = v23;
          v77 = v23;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
        }
        v11 = 0;
        v12 = (int)v107;
LABEL_65:
        v66 = (unsigned int)v11;
        v65 = (unsigned int)v11;
        v64 = (unsigned int)v11;
        v63 = (int)v11;
        if ( v16 && v12 == 2 )
        {
          v66 = *((_DWORD *)this + 171);
          CJobError::GetOldInterfaceErrors((CJob *)((char *)this + 680), &v65, &v64);
          v63 = *((_DWORD *)this + 182);
        }
        v70 = v11;
        v24 = (char *)this + 580;
        v80 = *(_OWORD *)((char *)this + 580);
        CJob::GetJobExternal((__int64)this - 192, &v69);
        v25 = 0;
        v78 = 0;
        v61 = 0;
        LODWORD(v62) = 0;
        LODWORD(v60) = 0;
        if ( v12 == 2 )
        {
          v26 = this;
          v68[0] = (CJob *)((char *)this + 680);
          v27 = (__int64 *)ThrowingMake<CJobErrorExternal,CJobError *>(&v73, v68);
          v25 = *v27;
          *v27 = 0;
          v78 = v25;
          v28 = v73;
          if ( v73 )
          {
            v73 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
        }
        else
        {
          v37 = v12 == 3;
          v26 = this;
          if ( v37 )
          {
            v38 = *((unsigned int *)this + 26);
            v62 = v38;
            v39 = *((_QWORD *)this + 82);
            v40 = (*((_QWORD *)this + 83) - v39) >> 3;
            if ( v38 >= v40 )
            {
              if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  144,
                  &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
                  (unsigned int)v38,
                  v40);
              }
              v85 = 0;
              v84 = &ComError::`vftable';
              v86 = -2147467259;
              v87 = 6313;
              v88 = 1;
              throw (ComError *)&v84;
            }
            FileExternal = CFile::GetFileExternal(*(_QWORD *)(v39 + 8 * v38), v68);
            Microsoft::WRL::ComPtr<IBackgroundCopyFile>::operator=(&v61, FileExternal);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v68);
            LODWORD(v60) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 82) + 8 * v38) + 348LL);
            v9 = v59;
          }
        }
        v29 = *(_OWORD *)((char *)v26 + 596);
        v30 = *((unsigned int *)v26 + 144);
        if ( (!(_DWORD)v30
           || (*(int (__fastcall **)(LPVOID, __int64, char *, void **))(*(_QWORD *)g_GIT + 40LL))(g_GIT, v30, v24, &v70) < 0)
          && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v9);
        }
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v26 + 77) + 8LL));
        v31 = (volatile signed __int32 *)*((_QWORD *)v26 + 77);
        v83 = v31;
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v26 + 78) + 8LL));
        v32 = (volatile signed __int32 *)*((_QWORD *)v26 + 78);
        Handles[0] = (HANDLE)v32;
        v33 = g_Manager;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
        }
        *((_DWORD *)v33 + 144) = 0;
        ReleaseSemaphore(*((HANDLE *)v33 + 70), 1, 0);
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
        }
        v34 = g_Manager;
        v106 = g_Manager;
        WaitForSingleObject(*((HANDLE *)g_Manager + 67), 0xFFFFFFFF);
        v35 = (char *)TlsGetValue(*((_DWORD *)v34 + 143));
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v35);
        if ( v35 )
        {
          TlsSetValue(*((_DWORD *)v106 + 143), 0);
          *((_QWORD *)v35 + 11) = 0;
          if ( *((_QWORD *)v35 + 3) == *((_QWORD *)v35 + 9) + 56LL && *((_QWORD *)v35 + 3) )
          {
            **((_QWORD **)v35 + 2) = *((_QWORD *)v35 + 1);
            *(_QWORD *)(*((_QWORD *)v35 + 1) + 8LL) = *((_QWORD *)v35 + 2);
            --*(_QWORD *)(*((_QWORD *)v35 + 3) + 24LL);
            *((_QWORD *)v35 + 1) = v35 + 8;
            *((_QWORD *)v35 + 2) = v35 + 8;
            *((_QWORD *)v35 + 3) = 0;
          }
          *((_QWORD *)v35 + 9) = 0;
          *((_DWORD *)v35 + 20) = 5;
          SetEvent(*((HANDLE *)v35 + 7));
          *((_QWORD *)v35 + 6) = 0;
          *((_QWORD *)v35 + 7) = 0;
        }
        ReleaseMutex(*((HANDLE *)v106 + 67));
        LOBYTE(v106) = 1;
        if ( (_BYTE)v105 )
        {
          v36 = CJob::OldInterfaceCallback((__int64)v59, v58, v19, v17, v18, v66, v65, v64, v63);
          if ( v36 < 0 )
          {
            v90 = 0;
            pExceptionObject = &ComError::`vftable';
            v91 = v36;
            v92 = 6347;
            v93 = 1;
            throw (ComError *)&pExceptionObject;
          }
        }
        else
        {
          *(_OWORD *)v68 = v29;
          v42 = CJob::InterfaceCallback((CJob *)v59, v58, v70, &v80, v69, v25, v61, v62, v60, (struct _GUID *)v68);
          if ( v42 < 0 )
          {
            if ( (_DWORD)v107 == 3 )
            {
              v100 = 0;
              v99 = &ComError::`vftable';
              v101 = v42;
              v102 = 6374;
              v103 = 1;
              throw (ComError *)&v99;
            }
            _InterlockedIncrement(v32 + 2);
            v105 = v32;
            _InterlockedIncrement(v31 + 2);
            v107 = v31;
            v43 = CJob::CmdLineCallback((__int64)v59, v58, (__int64 *)&v107, (__int64 *)&v105);
            if ( v43 < 0 )
            {
              v95 = 0;
              v94 = &ComError::`vftable';
              v96 = v43;
              v97 = 6370;
              v98 = 1;
              throw (ComError *)&v94;
            }
          }
        }
        v68[0] = (CJobManager *)((char *)g_Manager + 520);
        LODWORD(v107) = 0;
        LODWORD(v68[1]) = 0;
        if ( *((_DWORD *)v68[0] + 14) != GetCurrentThreadId() )
        {
          LODWORD(v107) = 1;
          LODWORD(v68[1]) = 1;
          TaskScheduler::LockWriter(v68[0], 0);
        }
        v44 = (CJob *)v59;
        _InterlockedExchange(v59 + 72, 0);
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v59);
          v45 = WPP_GLOBAL_Control;
          v44 = (CJob *)v59;
        }
        v46 = (_DWORD *)((char *)v44 + 1400);
        v47 = *((_DWORD *)v44 + 165);
        if ( v47 == 5 )
        {
LABEL_120:
          if ( v45 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)v45 + 2), 62, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v44);
            v45 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          if ( v47 != 8 )
          {
            switch ( v47 )
            {
              case 0:
              case 1:
              case 2:
                v44 = (CJob *)v59;
                goto LABEL_120;
              case 3:
              case 4:
              case 6:
              case 7:
                v44 = (CJob *)v59;
                break;
              default:
                goto LABEL_123;
            }
          }
          if ( v45 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)v45 + 2), 63, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v44);
            v44 = (CJob *)v59;
          }
          IsNotificationCallbackPending = CJob::IsNotificationCallbackPending(v44);
          v45 = WPP_GLOBAL_Control;
          if ( !IsNotificationCallbackPending )
          {
            LOBYTE(v105) = 0;
LABEL_124:
            if ( *((_BYTE *)v46 + 40) && v45 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v45 + 7) & 0x100) != 0 )
              WPP_SF_q(*((_QWORD *)v45 + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v46);
            EnterCriticalSection((LPCRITICAL_SECTION)v46);
            if ( *((_BYTE *)v46 + 48) )
            {
              if ( !(_BYTE)v105 )
              {
                v53 = CoReleaseSharedService(*((unsigned int *)g_ComServerModule + 5));
                if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    &WPP_b9cae9cbb65e31ab8ab5087a10ce05fe_Traceguids,
                    v53);
                }
                *((_BYTE *)v46 + 48) = 0;
              }
            }
            else if ( (_BYTE)v105 )
            {
              *((_BYTE *)v46 + 48) = 1;
              v49 = CoAddRefSharedService(*((unsigned int *)g_ComServerModule + 5));
              v50 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_134;
              }
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b9cae9cbb65e31ab8ab5087a10ce05fe_Traceguids, v49);
            }
            v50 = WPP_GLOBAL_Control;
LABEL_134:
            if ( *((_BYTE *)v46 + 40) && v50 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v50 + 7) & 0x100) != 0 )
              WPP_SF_q(*((_QWORD *)v50 + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v46);
            LeaveCriticalSection((LPCRITICAL_SECTION)v46);
            (*(void (__fastcall **)(volatile __int32 *, _QWORD))(*(_QWORD *)v59 + 480LL))(v59, 0);
            for ( i = (int)v107; i; --i )
              TaskScheduler::UnlockWriter(v68[0]);
            if ( v32 && _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
              operator delete((void *)v32, 0x10u);
            if ( v31 && _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
              operator delete((void *)v31, 0x10u);
            if ( v61 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            v52 = v69;
            if ( v69 )
            {
              v69 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
            if ( v70 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v70 + 16LL))(v70);
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v54 = v74;
            v55 = dwMilliseconds;
            if ( v59 )
              RefCountedObject::Release((RefCountedObject *)(v59 + 150));
            if ( (v54 & 0x2000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v56 = CallbackSleepHelper::GetCallbackName(0x2000u);
                WPP_SF_s(*(_QWORD *)(v57 + 16), 11, &WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, v56);
              }
              Sleep(v55);
            }
            return;
          }
        }
LABEL_123:
        LOBYTE(v105) = 1;
        goto LABEL_124;
      }
    }
    else if ( !*((_DWORD *)v9 + 192)
           && (!memcmp_0((const void *)(v9 + 197), &GUID_NULL, 0x10u) && !**((_QWORD **)v9 + 101)
            || !memcmp_0((const void *)(v9 + 197), &GUID_NULL, 0x10u)) )
    {
      goto LABEL_28;
    }
    v11 = 0;
    v13 = 0;
    v14 = *((_QWORD *)v9 + 106);
    while ( 1 )
    {
      if ( v13 >= (unsigned __int64)((*((_QWORD *)v9 + 107) - v14) >> 3) )
      {
        *((_DWORD *)v9 + 74) = 0x80000000;
        goto LABEL_28;
      }
      v15 = *(_QWORD *)(v14 + 8LL * v13);
      if ( *(_QWORD *)(v15 + 64) == *(_QWORD *)(v15 + 72) && !*(_BYTE *)(v15 + 346) )
        break;
      ++v13;
    }
    *((_DWORD *)v9 + 74) = v13;
    if ( v13 == 0x80000000 )
      goto LABEL_28;
    v12 = 3;
    v58 = 3;
    goto LABEL_50;
  }
  Handles[0] = Value[6];
  Handles[1] = v6;
  v7 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v7 )
  {
    if ( v7 == 1 )
    {
      *((_DWORD *)v4 + 144) = GetCurrentThreadId();
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    }
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  TaskScheduler::CompleteWorkItem((CJobManager *)((char *)g_Manager + 520), v8);
  CallbackSleepHelper::~CallbackSleepHelper((CallbackSleepHelper *)v81);
}

```

## disassembly

```asm
0x180030bb0  mov     r11, rsp
0x180030bb3  mov     [r11+8], rcx
0x180030bb7  push    rbx
0x180030bb8  push    rsi
0x180030bb9  push    rdi
0x180030bba  push    r12
0x180030bbc  push    r13
0x180030bbe  push    r14
0x180030bc0  push    r15
0x180030bc2  sub     rsp, 330h
0x180030bc9  movaps  xmmword ptr [r11-48h], xmm6
0x180030bce  mov     r15, rcx
0x180030bd1  mov     dword ptr [rsp+368h+arg_8], 0
0x180030bdc  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180030be3  mov     ebx, [rax+0D0h]
0x180030be9  mov     [rsp+368h+dwMilliseconds], ebx
0x180030bf0  mov     rcx, [rax+0C8h]
0x180030bf7  mov     [rsp+368h+var_2A0], rcx
0x180030bff  mov     rdx, [rax+0C0h]
0x180030c06  mov     [r11-258h], rdx
0x180030c0d  mov     [r11-250h], rcx
0x180030c14  mov     qword ptr [r11-248h], 2000h
0x180030c1f  mov     [rsp+368h+var_240], ebx
0x180030c26  bt      rdx, 0Dh
0x180030c2b  jnb     short loc_180030C73
0x180030c2d  lea     rsi, WPP_GLOBAL_Control
0x180030c34  mov     r10, cs:WPP_GLOBAL_Control
0x180030c3b  cmp     r10, rsi
0x180030c3e  jz      short loc_180030C69
0x180030c40  test    byte ptr [r10+1Ch], 1
0x180030c45  jz      short loc_180030C69
0x180030c47  mov     ecx, 2000h; unsigned __int64
0x180030c4c  call    ?GetCallbackName@CallbackSleepHelper@@KAPEBD_K@Z; CallbackSleepHelper::GetCallbackName(unsigned __int64)
0x180030c51  mov     r9, rax
0x180030c54  mov     edx, 0Ah
0x180030c59  lea     r8, WPP_263cc8d6529f371e5fb175aafd999872_Traceguids
0x180030c60  mov     rcx, [r10+10h]
0x180030c64  call    WPP_SF_s
0x180030c69  mov     ecx, ebx; dwMilliseconds
0x180030c6b  call    cs:__imp_Sleep
0x180030c71  jmp     short loc_180030C7A
0x180030c73  lea     rsi, WPP_GLOBAL_Control
0x180030c7a  mov     rbx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180030c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c88  cmp     rcx, rsi
0x180030c8b  jz      short loc_180030CAB
0x180030c8d  test    dword ptr [rcx+1Ch], 100h
0x180030c94  jz      short loc_180030CAB
0x180030c96  mov     edx, 1Eh
0x180030c9b  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180030ca2  mov     rcx, [rcx+10h]
0x180030ca6  call    WPP_SF_
0x180030cab  mov     ecx, [rbx+23Ch]; dwTlsIndex
0x180030cb1  call    cs:__imp_TlsGetValue
0x180030cb7  mov     rcx, [rbx+230h]; hHandle
0x180030cbe  test    rax, rax
0x180030cc1  jz      loc_180030DA2
0x180030cc7  mov     rdx, [rax+30h]
0x180030ccb  test    rdx, rdx
0x180030cce  jz      loc_180030DA2
0x180030cd4  mov     [rsp+368h+Handles], rdx
0x180030cdc  mov     [rsp+368h+var_270], rcx
0x180030ce4  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180030cea  xor     r8d, r8d; bWaitAll
0x180030ced  lea     rdx, [rsp+368h+Handles]; lpHandles
0x180030cf5  mov     edi, 2
0x180030cfa  mov     ecx, edi; nCount
0x180030cfc  call    cs:__imp_WaitForMultipleObjects
0x180030d02  test    eax, eax
0x180030d04  jz      short loc_180030D52
0x180030d06  cmp     eax, 1
0x180030d09  jnz     loc_180030DE8
0x180030d0f  call    cs:__imp_GetCurrentThreadId
0x180030d15  mov     [rbx+240h], eax
0x180030d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d22  cmp     rcx, rsi
0x180030d25  jz      loc_180030DE8
0x180030d2b  test    dword ptr [rcx+1Ch], 100h
0x180030d32  jz      loc_180030DE8
0x180030d38  mov     edx, 21h ; '!'
0x180030d3d  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180030d44  mov     rcx, [rcx+10h]
0x180030d48  call    WPP_SF_
0x180030d4d  jmp     loc_180030DE8
0x180030d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d59  cmp     rcx, rsi
0x180030d5c  jz      short loc_180030D7C
0x180030d5e  test    dword ptr [rcx+1Ch], 100h
0x180030d65  jz      short loc_180030D7C
0x180030d67  mov     edx, 20h ; ' '
0x180030d6c  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180030d73  mov     rcx, [rcx+10h]
0x180030d77  call    WPP_SF_
0x180030d7c  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180030d83  add     rcx, 208h; this
0x180030d8a  call    ?CompleteWorkItem@TaskScheduler@@AEAAX_N@Z; TaskScheduler::CompleteWorkItem(bool)
0x180030d8f  nop
0x180030d90  lea     rcx, [rsp+368h+var_258]; this
0x180030d98  call    ??1CallbackSleepHelper@@QEAA@XZ; CallbackSleepHelper::~CallbackSleepHelper(void)
0x180030d9d  jmp     loc_180031B20
0x180030da2  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180030da7  call    cs:__imp_WaitForSingleObject
0x180030dad  call    cs:__imp_GetCurrentThreadId
0x180030db3  mov     [rbx+240h], eax
0x180030db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dc0  cmp     rcx, rsi
0x180030dc3  jz      short loc_180030DE3
0x180030dc5  test    dword ptr [rcx+1Ch], 100h
0x180030dcc  jz      short loc_180030DE3
0x180030dce  mov     edx, 1Fh
0x180030dd3  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180030dda  mov     rcx, [rcx+10h]
0x180030dde  call    WPP_SF_
0x180030de3  mov     edi, 2
0x180030de8  lea     r13, [r15-0C0h]
0x180030def  mov     [rsp+368h+var_310], r13
0x180030df4  test    r13, r13
0x180030df7  jz      short loc_180030E06
0x180030df9  lea     rcx, [r13+258h]; this
0x180030e00  call    ?AddRef@RefCountedObject@@QEAAKXZ; RefCountedObject::AddRef(void)
0x180030e05  nop
0x180030e06  mov     byte ptr [rsp+368h+arg_10], 0
0x180030e0e  mov     eax, [r13+324h]
0x180030e15  and     al, 14h
0x180030e17  cmp     al, 10h
0x180030e19  jnz     short loc_180030E33
0x180030e1b  cmp     byte ptr [r13+540h], 0
0x180030e23  jz      short loc_180030E6D
0x180030e25  cmp     qword ptr [r13+558h], 0
0x180030e2d  jnz     loc_180030EC7
0x180030e33  xor     r10d, r10d
0x180030e36  mov     edx, 1; unsigned int
0x180030e3b  mov     rcx, r13; this
0x180030e3e  call    ?IsCallbackEnabled@CJob@@IEAA_NK@Z; CJob::IsCallbackEnabled(ulong)
0x180030e43  test    al, al
0x180030e45  jz      loc_180030F31
0x180030e4b  cmp     dword ptr [r13+294h], 6
0x180030e53  jnz     loc_180030F31
0x180030e59  cmp     [r13+124h], edx
0x180030e60  jnz     loc_180030F31
0x180030e66  mov     ebx, edx
0x180030e68  jmp     loc_180030F55
0x180030e6d  mov     ebx, [r13+300h]
0x180030e74  test    ebx, ebx
0x180030e76  jnz     short loc_180030EC7
0x180030e78  lea     rcx, [r13+314h]; Buf1
0x180030e7f  mov     r8d, 10h; Size
0x180030e85  lea     rdx, GUID_NULL; Buf2
0x180030e8c  call    memcmp_0
0x180030e91  test    eax, eax
0x180030e93  jnz     short loc_180030EA6
0x180030e95  mov     rax, [r13+328h]
0x180030e9c  cmp     qword ptr [rax], 0
0x180030ea0  jz      short loc_180030E33
0x180030ea2  test    ebx, ebx
0x180030ea4  jnz     short loc_180030EC7
0x180030ea6  lea     rcx, [r13+314h]; Buf1
0x180030ead  mov     r8d, 10h; Size
0x180030eb3  lea     rdx, GUID_NULL; Buf2
0x180030eba  call    memcmp_0
0x180030ebf  test    eax, eax
0x180030ec1  jz      loc_180030E33
0x180030ec7  xor     r10d, r10d
0x180030eca  mov     eax, r10d
0x180030ecd  mov     r9, [r13+350h]
0x180030ed4  mov     r8, [r13+358h]
0x180030edb  sub     r8, r9
0x180030ede  sar     r8, 3
0x180030ee2  mov     edx, eax
0x180030ee4  cmp     rdx, r8
0x180030ee7  jnb     short loc_180030F21
0x180030ee9  mov     rdx, [r9+rdx*8]
0x180030eed  mov     rcx, [rdx+48h]
0x180030ef1  cmp     [rdx+40h], rcx
0x180030ef5  jnz     short loc_180030F1D
0x180030ef7  cmp     [rdx+15Ah], r10b
0x180030efe  jnz     short loc_180030F1D
0x180030f00  mov     [r13+128h], eax
0x180030f07  cmp     eax, 80000000h
0x180030f0c  jz      loc_180030E36
0x180030f12  mov     ebx, 3
0x180030f17  mov     [rsp+368h+var_318], ebx
0x180030f1b  jmp     short loc_180030F67
0x180030f1d  inc     eax
0x180030f1f  jmp     short loc_180030EE2
0x180030f21  mov     dword ptr [r13+128h], 80000000h
0x180030f2c  jmp     loc_180030E36
0x180030f31  mov     edx, edi; unsigned int
0x180030f33  mov     rcx, r13; this
0x180030f36  call    ?IsCallbackEnabled@CJob@@IEAA_NK@Z; CJob::IsCallbackEnabled(ulong)
0x180030f3b  test    al, al
0x180030f3d  jz      short loc_180030F5F
0x180030f3f  cmp     dword ptr [r13+294h], 4
0x180030f47  jnz     short loc_180030F5F
0x180030f49  cmp     dword ptr [r13+124h], 2
0x180030f51  jnz     short loc_180030F5F
0x180030f53  mov     ebx, edi
0x180030f55  mov     [r15+64h], r10d
0x180030f59  mov     [rsp+368h+var_318], ebx
0x180030f5d  jmp     short loc_180030F67
0x180030f5f  mov     ebx, r10d
0x180030f62  mov     [rsp+368h+var_318], r10d
0x180030f67  mov     dword ptr [rsp+368h+arg_18], ebx
0x180030f6e  movzx   edi, byte ptr [r15+480h]
0x180030f76  mov     byte ptr [rsp+368h+arg_8], dil
0x180030f7e  mov     r14, r10
0x180030f81  mov     [rsp+368h+var_298], r10
0x180030f89  mov     rsi, r10
0x180030f8c  mov     [rsp+368h+var_290], r10
0x180030f94  mov     r12, r10
0x180030f97  mov     [rsp+368h+var_288], r10
0x180030f9f  test    dil, dil
0x180030fa2  jz      loc_1800310BF
0x180030fa8  lea     rdx, [rsp+368h+var_2F8]
0x180030fad  mov     rcx, r13
0x180030fb0  call    ?GetOldGroupExternal@CJob@@QEAA?AV?$ComPtr@UIBackgroundCopyGroup@@@WRL@Microsoft@@XZ; CJob::GetOldGroupExternal(void)
0x180030fb5  xor     ebx, ebx
0x180030fb7  mov     r14d, ebx
0x180030fba  lea     rcx, [rsp+368h+var_2B8]
0x180030fc2  cmp     rcx, rax
0x180030fc5  jz      short loc_180030FCD
0x180030fc7  mov     r14, [rax]
0x180030fca  mov     [rax], rbx
0x180030fcd  mov     [rsp+368h+var_2B8], rbx
0x180030fd5  mov     [rsp+368h+var_298], r14
0x180030fdd  lea     rcx, [rsp+368h+var_2B8]
0x180030fe5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030fea  lea     rcx, [rsp+368h+var_2F8]
0x180030fef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030ff4  cmp     [r15+4A0h], bl
0x180030ffb  jz      short loc_180031021
0x180030ffd  lea     rdx, [rsp+368h+var_2F8]
0x180031002  mov     rcx, r13
0x180031005  call    ?GetOldJobExternal@CJob@@QEAA?AV?$ComPtr@UIBackgroundCopyJob1@@@WRL@Microsoft@@XZ; CJob::GetOldJobExternal(void)
0x18003100a  mov     rsi, rbx
0x18003100d  mov     ebx, 1
0x180031012  lea     rcx, [rsp+368h+var_2B0]
0x18003101a  cmp     rcx, rax
0x18003101d  jnz     short loc_180031030
0x18003101f  jmp     short loc_18003103A
0x180031021  mov     [rsp+368h+var_300], rbx
0x180031026  lea     rax, [rsp+368h+var_300]
0x18003102b  mov     ebx, 2
0x180031030  mov     rsi, [rax]
0x180031033  mov     qword ptr [rax], 0
0x18003103a  mov     [rsp+368h+var_2B0], 0
0x180031046  mov     [rsp+368h+var_290], rsi
0x18003104e  lea     rcx, [rsp+368h+var_2B0]
0x180031056  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003105b  test    bl, 2
0x18003105e  jz      short loc_18003106D
0x180031060  and     ebx, 0FFFFFFFDh
0x180031063  lea     rcx, [rsp+368h+var_300]
0x180031068  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003106d  test    bl, 1
0x180031070  jz      short loc_18003107C
0x180031072  lea     rcx, [rsp+368h+var_2F8]
0x180031077  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003107c  mov     rbx, [r15+498h]
0x180031083  test    rbx, rbx
0x180031086  jz      short loc_1800310B5
0x180031088  mov     [rsp+368h+var_308], rbx
0x18003108d  lea     rcx, [rsp+368h+var_308]
0x180031092  call    ?InternalAddRef@?$ComPtr@UIBackgroundCopyCallback1@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IBackgroundCopyCallback1>::InternalAddRef(void)
0x180031097  mov     [rsp+368h+var_308], 0
0x1800310a0  mov     r12, rbx
0x1800310a3  mov     [rsp+368h+var_288], rbx
0x1800310ab  lea     rcx, [rsp+368h+var_308]
0x1800310b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800310b5  xor     r10d, r10d
0x1800310b8  mov     ebx, dword ptr [rsp+368h+arg_18]
0x1800310bf  mov     [rsp+368h+var_2E4], r10d
0x1800310c7  mov     [rsp+368h+var_2E8], r10d
0x1800310cf  mov     [rsp+368h+var_2EC], r10d
0x1800310d4  mov     [rsp+368h+var_2F0], r10d
0x1800310d9  test    dil, dil
0x1800310dc  jz      short loc_180031115
0x1800310de  cmp     ebx, 2
0x1800310e1  jnz     short loc_180031115
0x1800310e3  mov     eax, [r15+2ACh]
0x1800310ea  mov     [rsp+368h+var_2E4], eax
0x1800310f1  lea     rcx, [r15+2A8h]; this
0x1800310f8  lea     r8, [rsp+368h+var_2EC]; unsigned int *
0x1800310fd  lea     rdx, [rsp+368h+var_2E8]; unsigned int *
0x180031105  call    ?GetOldInterfaceErrors@CJobError@@QEBAXPEAK0@Z; CJobError::GetOldInterfaceErrors(ulong *,ulong *)
0x18003110a  mov     eax, [r15+2D8h]
0x180031111  mov     [rsp+368h+var_2F0], eax
0x180031115  mov     [rsp+368h+var_2C0], r10
0x18003111d  lea     rdi, [r15+244h]
0x180031124  movups  xmm0, xmmword ptr [rdi]
0x180031127  movups  [rsp+368h+var_268], xmm0
0x18003112f  lea     rdx, [rsp+368h+var_2C8]
0x180031137  mov     rcx, r13
0x18003113a  call    ?GetJobExternal@CJob@@QEAA?AV?$ComPtr@UIBackgroundCopyJob@@@WRL@Microsoft@@XZ; CJob::GetJobExternal(void)
0x18003113f  nop
0x180031140  xor     r8d, r8d
0x180031143  mov     r15d, r8d
0x180031146  mov     [rsp+368h+var_280], r8
0x18003114e  mov     [rsp+368h+var_300], r8
0x180031153  mov     dword ptr [rsp+368h+var_2F8], r8d
  ... truncated ...
```
