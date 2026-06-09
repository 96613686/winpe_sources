# CJob::BeginAttrSecurityCheck(void)

- ea: `0x18001b460`
- end: `0x18001baba`
- name: `?BeginAttrSecurityCheck@CJob@@MEAAXXZ`
- size: `1626`
- prototype: `void __fastcall(CJob *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180014310`
- `0x18001a6fc`
- `0x18001b460`
- `0x18001c67c`
- `0x18002c360`
- `0x18002c990`
- `0x18002cc00`
- `0x18002e6b8`
- `0x1800383a8`
- `0x180039ef0`
- `0x18007fd20`
- `0x18007ffe4`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a21dc`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800aea00`
- `0x1800d9188`
- `0x1800f4f2c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b4e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b593`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b4e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b992`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001b93d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001b93d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001ba09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001ba09`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b95f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b95f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ba19`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ba19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b82f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b82f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CJob::BeginAttrSecurityCheck(struct _FILETIME *this)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rbx
  _DWORD *v4; // rax
  unsigned int dwHighDateTime; // ecx
  int dwLowDateTime; // r9d
  AppPackageInfo *v7; // r8
  int v8; // eax
  int v9; // edx
  __int64 v10; // r8
  int v11; // esi
  CJobManager *v12; // rcx
  bool v13; // dl
  EVENT_LOG *v14; // rcx
  volatile signed __int32 *v15; // rax
  CJobManager *v16; // rcx
  void *v17; // rcx
  DWORD v18; // eax
  struct _FILETIME v19; // rax
  __int64 v20; // rax
  struct _TP_WAIT *v21; // rcx
  struct _FILETIME v22; // rcx
  unsigned int LastError; // ecx
  void *v24; // rax
  signed __int32 v25; // r14d
  ComError *v26; // rax
  int v27; // r8d
  struct _FILETIME *v28; // rbx
  unsigned int v29; // edx
  CJob::TRANSFER_GLOB *v30; // rcx
  void *v31; // [rsp+40h] [rbp-278h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-270h] BYREF
  struct _FILETIME v33; // [rsp+50h] [rbp-268h] BYREF
  __int64 v34; // [rsp+58h] [rbp-260h]
  __int64 v35; // [rsp+60h] [rbp-258h]
  void *v36; // [rsp+68h] [rbp-250h] BYREF
  struct _GUID v37; // [rsp+70h] [rbp-248h] BYREF
  struct _FILETIME *v38; // [rsp+80h] [rbp-238h]
  void **pExceptionObject; // [rsp+90h] [rbp-228h] BYREF
  __int128 v40; // [rsp+98h] [rbp-220h]
  int v41; // [rsp+A8h] [rbp-210h]
  int v42; // [rsp+ACh] [rbp-20Ch]
  int v43; // [rsp+B0h] [rbp-208h]
  void **v44; // [rsp+F0h] [rbp-1C8h] BYREF
  __int128 v45; // [rsp+F8h] [rbp-1C0h]
  int v46; // [rsp+108h] [rbp-1B0h]
  int v47; // [rsp+10Ch] [rbp-1ACh]
  int v48; // [rsp+110h] [rbp-1A8h]
  void **v49; // [rsp+150h] [rbp-168h] BYREF
  __int128 v50; // [rsp+158h] [rbp-160h]
  unsigned int v51; // [rsp+168h] [rbp-150h]
  int v52; // [rsp+16Ch] [rbp-14Ch]
  int v53; // [rsp+170h] [rbp-148h]
  __int64 v54; // [rsp+1B0h] [rbp-108h] BYREF
  void **v55; // [rsp+210h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+218h] [rbp-A0h] BYREF
  DWORD v57; // [rsp+228h] [rbp-90h]

  v38 = this;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
      this,
      this[105].dwHighDateTime);
  this[81] = 0;
  v2 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
  try
  {
    v3 = v2;
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v40 = 0;
      pExceptionObject = &ComError::`vftable';
      v41 = -2147024882;
      v42 = 0;
      v43 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v36 = (void *)v2;
    *((_DWORD *)v2 + 2) = 1;
    *(_QWORD *)v2 = 0;
    v4 = HeapAlloc(hBitsHeap, 8u, 0x10u);
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v45 = 0;
      v44 = &ComError::`vftable';
      v46 = -2147024882;
      v47 = 0;
      v48 = 1;
      throw (ComError *)&v44;
    }
    v31 = v4;
    v4[2] = 1;
    *(_QWORD *)v31 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&this[191] + 8LL));
    SystemTimeAsFileTime = this[191];
    dwHighDateTime = this[94].dwHighDateTime;
    dwLowDateTime = this[94].dwLowDateTime;
    v7 = (AppPackageInfo *)this[92];
    v33 = this[89];
    v34 = (__int64)this[90];
    _InterlockedIncrement((volatile signed __int32 *)v34);
    v8 = CJobManager::CloneUserToken(
           (__int64)g_Manager,
           (SidHandle *)&v33,
           v7,
           dwLowDateTime,
           dwHighDateTime,
           0,
           (void **)&SystemTimeAsFileTime,
           (TokenHandle *)&v31);
    v11 = v8;
    if ( v8 >= 0 )
    {
      v15 = (volatile signed __int32 *)v31;
      if ( *(_QWORD *)v3 != *(_QWORD *)v31 )
      {
        TokenHandle::Decrement((TokenHandle *)&v36);
        v3 = (volatile signed __int32 *)v31;
        v36 = v31;
        _InterlockedIncrement((volatile signed __int32 *)v31 + 2);
        v15 = (volatile signed __int32 *)v31;
      }
      v16 = (CJobManager *)(unsigned int)_InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF);
      if ( (_DWORD)v16 == 1 )
      {
        v17 = v31;
        if ( (unsigned __int64)(*(_QWORD *)v31 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v31);
          *(_QWORD *)v31 = 0;
          v17 = v31;
        }
        operator delete(v17, 0x10u);
        v31 = 0;
      }
      v18 = this[82].dwHighDateTime;
      if ( v18 != 2 )
      {
        if ( v18 != 1 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_qll(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, v10, this, v18, 1);
          this[82].dwHighDateTime = 1;
          TaskScheduler::CancelWorkItem(
            (CJobManager *)((char *)g_Manager + 520),
            (struct TaskSchedulerWorkItem *)&this[12]);
          CJob::UpdateModificationTime(this, 0);
          CJob::ReevaluateIdleStopConditions((CJob *)this);
        }
        CJob::ScheduleModificationCallback((CJob *)this);
      }
      v37 = *(struct _GUID *)&this[166].dwLowDateTime;
      CJobManager::SignalBackgroundTransferSebEventBestEffort(v16, &v37, (const struct CustomUserContext *)&this[163]);
      v19 = *this;
      SystemTimeAsFileTime = (struct _FILETIME)v3;
      _InterlockedIncrement(v3 + 2);
      v20 = (*(__int64 (__fastcall **)(struct _FILETIME *, struct _FILETIME *))(*(_QWORD *)&v19 + 288LL))(
              this,
              &SystemTimeAsFileTime);
      this[81] = (struct _FILETIME)v20;
      if ( v20 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 32) + 48LL))(*(_QWORD *)(v20 + 32));
        v21 = *(struct _TP_WAIT **)(*(_QWORD *)&this[81] + 48LL);
        if ( v21 )
          CloseThreadpoolWait(v21);
        *(_QWORD *)(*(_QWORD *)&this[81] + 48LL) = CreateThreadpoolWait(
                                                     CJob::StaticOnTransferComplete,
                                                     *(PVOID *)&this[81],
                                                     (PTP_CALLBACK_ENVIRON)((char *)g_Manager + 992));
        v22 = this[81];
        if ( !*(_QWORD *)(*(_QWORD *)&v22 + 48LL) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0x80070000;
          else
            LastError = GetLastError();
          v50 = 0;
          v49 = &ComError::`vftable';
          v51 = LastError;
          v52 = 4557;
          v53 = 1;
          throw (ComError *)&v49;
        }
        v24 = (void *)(***(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)&v22 + 32LL))(*(_QWORD *)(*(_QWORD *)&v22 + 32LL));
        SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)&this[81] + 48LL), v24, 0);
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        this[124] = SystemTimeAsFileTime;
        v25 = _InterlockedIncrement((volatile signed __int32 *)&this[76]);
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_d16db4fdda8e3e911b60915595dfa5af_Traceguids,
            &this[75],
            v25);
        if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
        {
          if ( (unsigned __int64)(*(_QWORD *)v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v3);
            *(_QWORD *)v3 = 0;
          }
          operator delete((void *)v3, 0x10u);
        }
      }
      else
      {
        TokenHandle::Decrement((TokenHandle *)&v36);
      }
    }
    else
    {
      if ( v8 == -2147023651 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
        CJobManager::MoveJobOffline(v12, (struct CJob *)this);
        CJob::RecalcTransientError((CJob *)this, 1, 0, 0);
        CJobManager::ScheduleAnotherGroup(g_Manager);
      }
      else if ( v8 == -2145386390 )
      {
        CJob::OnOwningAppPackageUninstalled((CJob *)this);
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            110,
            &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
            (unsigned int)v8);
          v14 = WPP_GLOBAL_Control;
        }
        v33.dwLowDateTime = 3;
        v35 = 0;
        v34 = 0x200000001LL;
        v33.dwHighDateTime = v11;
        if ( v14 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
          WPP_SF_llDDS(*((_QWORD *)v14 + 2), v9, v10, 3, 1, v11, 2, (__int64)&qword_18011AC70);
        CJob::SetTransientError((CJob *)this, (struct QMErrInfo *)&v33, this[105].dwLowDateTime, 0, 0);
      }
      TaskScheduler::CompleteWorkItem((CJobManager *)((char *)g_Manager + 520), v13);
      TokenHandle::Decrement((TokenHandle *)&v31);
      TokenHandle::Decrement((TokenHandle *)&v36);
    }
  }
  catch ( ComError v55 )
  {
    v26 = ComError::ComError((ComError *)&v54, (const struct ComError *)&v55);
    LogException(v26);
    v28 = v38;
    if ( v38[81] )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v38[81] + 32LL) + 16LL))(*(_QWORD *)(*(_QWORD *)&v38[81] + 32LL));
      v30 = (CJob::TRANSFER_GLOB *)v28[81];
      if ( v30 )
        CJob::TRANSFER_GLOB::`scalar deleting destructor'(v30, v29);
      v28[81] = 0;
    }
    v33.dwLowDateTime = 2;
    v35 = 0;
    v34 = 0x200000001LL;
    v33.dwHighDateTime = v57;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_llDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&qword_18011AC70,
        v27,
        2,
        1,
        v57,
        2,
        (__int64)&qword_18011AC70);
    CJob::SetTransientError((CJob *)v28, (struct QMErrInfo *)&v33, v28[105].dwHighDateTime, 1, 1);
    v55 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(&v56);
  }
}

```

## disassembly

```asm
0x18001b460  push    rbx
0x18001b462  push    rsi
0x18001b463  push    rdi
0x18001b464  push    r12
0x18001b466  push    r14
0x18001b468  push    r15
0x18001b46a  sub     rsp, 288h
0x18001b471  mov     rax, cs:__security_cookie
0x18001b478  xor     rax, rsp
0x18001b47b  mov     [rsp+2B8h+var_48], rax
0x18001b483  mov     rdi, rcx
0x18001b486  mov     [rsp+2B8h+var_238], rcx
0x18001b48e  lea     r12, WPP_GLOBAL_Control
0x18001b495  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b49c  cmp     rcx, r12
0x18001b49f  jz      short loc_18001B4C9
0x18001b4a1  test    byte ptr [rcx+1Ch], 1
0x18001b4a5  jz      short loc_18001B4C9
0x18001b4a7  mov     edx, 77h ; 'w'
0x18001b4ac  mov     eax, [rdi+34Ch]
0x18001b4b2  mov     dword ptr [rsp+2B8h+var_298], eax
0x18001b4b6  mov     r9, rdi
0x18001b4b9  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001b4c0  mov     rcx, [rcx+10h]
0x18001b4c4  call    WPP_SF_qD
0x18001b4c9  xor     r15d, r15d
0x18001b4cc  mov     [rdi+288h], r15
0x18001b4d3  mov     edx, 8; dwFlags
0x18001b4d8  mov     r8d, 10h; dwBytes
0x18001b4de  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18001b4e5  call    cs:__imp_HeapAlloc
0x18001b4eb  mov     rbx, rax
0x18001b4ee  test    rax, rax
0x18001b4f1  jnz     short loc_18001B56F
0x18001b4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4fa  cmp     rcx, r12
0x18001b4fd  jz      short loc_18001B520
0x18001b4ff  test    byte ptr [rcx+1Ch], 4
0x18001b503  jz      short loc_18001B520
0x18001b505  mov     edx, 0Ah
0x18001b50a  mov     r9d, 10h
0x18001b510  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18001b517  mov     rcx, [rcx+10h]
0x18001b51b  call    WPP_SF_d
0x18001b520  xorps   xmm0, xmm0
0x18001b523  movups  [rsp+2B8h+var_220], xmm0
0x18001b52b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001b532  mov     [rsp+2B8h+pExceptionObject], rax
0x18001b53a  mov     [rsp+2B8h+var_210], 8007000Eh
0x18001b545  mov     [rsp+2B8h+var_20C], r15d
0x18001b54d  mov     r14d, 1
0x18001b553  mov     [rsp+2B8h+var_208], r14d
0x18001b55b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001b562  lea     rcx, [rsp+2B8h+pExceptionObject]; pExceptionObject
0x18001b56a  call    _CxxThrowException_0
0x18001b56f  mov     [rsp+2B8h+var_250], rbx
0x18001b574  mov     r14d, 1
0x18001b57a  mov     [rax+8], r14d
0x18001b57e  mov     [rax], r15
0x18001b581  mov     edx, 8; dwFlags
0x18001b586  mov     r8d, 10h; dwBytes
0x18001b58c  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18001b593  call    cs:__imp_HeapAlloc
0x18001b599  test    rax, rax
0x18001b59c  jnz     short loc_18001B614
0x18001b59e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5a5  cmp     rcx, r12
0x18001b5a8  jz      short loc_18001B5CB
0x18001b5aa  test    byte ptr [rcx+1Ch], 4
0x18001b5ae  jz      short loc_18001B5CB
0x18001b5b0  mov     edx, 0Ah
0x18001b5b5  mov     r9d, 10h
0x18001b5bb  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18001b5c2  mov     rcx, [rcx+10h]
0x18001b5c6  call    WPP_SF_d
0x18001b5cb  xorps   xmm0, xmm0
0x18001b5ce  movups  [rsp+2B8h+var_1C0], xmm0
0x18001b5d6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001b5dd  mov     [rsp+2B8h+var_1C8], rax
0x18001b5e5  mov     [rsp+2B8h+var_1B0], 8007000Eh
0x18001b5f0  mov     [rsp+2B8h+var_1AC], r15d
0x18001b5f8  mov     [rsp+2B8h+var_1A8], r14d
0x18001b600  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001b607  lea     rcx, [rsp+2B8h+var_1C8]; pExceptionObject
0x18001b60f  call    _CxxThrowException_0
0x18001b614  mov     [rsp+2B8h+var_278], rax
0x18001b619  mov     [rax+8], r14d
0x18001b61d  mov     rax, [rsp+2B8h+var_278]
0x18001b622  mov     [rax], r15
0x18001b625  mov     rax, [rdi+5F8h]
0x18001b62c  lock inc dword ptr [rax+8]
0x18001b630  mov     rax, [rdi+5F8h]
0x18001b637  mov     qword ptr [rsp+2B8h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001b63c  mov     ecx, [rdi+2F4h]
0x18001b642  mov     r9d, [rdi+2F0h]
0x18001b649  mov     r8, [rdi+2E0h]
0x18001b650  mov     rax, [rdi+2C8h]
0x18001b657  mov     [rsp+2B8h+var_268], rax
0x18001b65c  mov     rax, [rdi+2D0h]
0x18001b663  mov     [rsp+2B8h+var_260], rax
0x18001b668  lock inc dword ptr [rax]
0x18001b66b  lea     rax, [rsp+2B8h+var_278]
0x18001b670  mov     [rsp+2B8h+var_280], rax
0x18001b675  lea     rax, [rsp+2B8h+SystemTimeAsFileTime]
0x18001b67a  mov     [rsp+2B8h+var_288], rax
0x18001b67f  mov     [rsp+2B8h+var_290], r15
0x18001b684  mov     dword ptr [rsp+2B8h+var_298], ecx
0x18001b688  lea     rdx, [rsp+2B8h+var_268]
0x18001b68d  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001b694  call    ?CloneUserToken@CJobManager@@QEAAJVSidHandle@@PEAUAppPackageInfo@@HKPEA_KV?$GenericStringHandle@G@@PEAVTokenHandle@@@Z; CJobManager::CloneUserToken(SidHandle,AppPackageInfo *,int,ulong,unsigned __int64 *,GenericStringHandle<ushort>,TokenHandle *)
0x18001b699  mov     esi, eax
0x18001b69b  test    eax, eax
0x18001b69d  jns     loc_18001B7DF
0x18001b6a3  cmp     eax, 800704DDh
0x18001b6a8  jnz     short loc_18001B6FA
0x18001b6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6b1  cmp     rcx, r12
0x18001b6b4  jz      short loc_18001B6D1
0x18001b6b6  test    byte ptr [rcx+1Ch], 1
0x18001b6ba  jz      short loc_18001B6D1
0x18001b6bc  mov     edx, 6Dh ; 'm'
0x18001b6c1  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001b6c8  mov     rcx, [rcx+10h]
0x18001b6cc  call    WPP_SF_
0x18001b6d1  mov     rdx, rdi; struct CJob *
0x18001b6d4  call    ?MoveJobOffline@CJobManager@@QEAAXPEAVCJob@@@Z; CJobManager::MoveJobOffline(CJob *)
0x18001b6d9  xor     r9d, r9d; bool
0x18001b6dc  xor     r8d, r8d; bool
0x18001b6df  mov     dl, 1; bool
0x18001b6e1  mov     rcx, rdi; this
0x18001b6e4  call    ?RecalcTransientError@CJob@@IEAA_N_N00@Z; CJob::RecalcTransientError(bool,bool,bool)
0x18001b6e9  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; this
0x18001b6f0  call    ?ScheduleAnotherGroup@CJobManager@@QEAAXXZ; CJobManager::ScheduleAnotherGroup(void)
0x18001b6f5  jmp     loc_18001B7B1
0x18001b6fa  cmp     esi, 8020006Ah
0x18001b700  jnz     short loc_18001B70F
0x18001b702  mov     rcx, rdi; this
0x18001b705  call    ?OnOwningAppPackageUninstalled@CJob@@QEAAXXZ; CJob::OnOwningAppPackageUninstalled(void)
0x18001b70a  jmp     loc_18001B7B1
0x18001b70f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b716  cmp     rcx, r12
0x18001b719  jz      short loc_18001B740
0x18001b71b  test    byte ptr [rcx+1Ch], 4
0x18001b71f  jz      short loc_18001B740
0x18001b721  mov     edx, 6Eh ; 'n'
0x18001b726  mov     r9d, esi
0x18001b729  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18001b730  mov     rcx, [rcx+10h]
0x18001b734  call    WPP_SF_d
0x18001b739  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b740  mov     dword ptr [rsp+2B8h+var_268], 3
0x18001b748  mov     [rsp+2B8h+var_258], r15
0x18001b74d  mov     dword ptr [rsp+2B8h+var_260+4], 2
0x18001b755  mov     dword ptr [rsp+2B8h+var_260], r14d
0x18001b75a  mov     dword ptr [rsp+2B8h+var_268+4], esi
0x18001b75e  cmp     rcx, r12
0x18001b761  jz      short loc_18001B795
0x18001b763  test    byte ptr [rcx+1Ch], 1
0x18001b767  jz      short loc_18001B795
0x18001b769  lea     rax, qword_18011AC70
0x18001b770  mov     [rsp+2B8h+var_280], rax
0x18001b775  mov     dword ptr [rsp+2B8h+var_288], 2
0x18001b77d  mov     dword ptr [rsp+2B8h+var_290], esi
0x18001b781  mov     dword ptr [rsp+2B8h+var_298], r14d
0x18001b786  mov     r9d, 3
0x18001b78c  mov     rcx, [rcx+10h]
0x18001b790  call    WPP_SF_llDDS
0x18001b795  mov     [rsp+2B8h+var_298], 0; bool
0x18001b79a  xor     r9d, r9d; bool
0x18001b79d  mov     r8d, [rdi+348h]; int
0x18001b7a4  lea     rdx, [rsp+2B8h+var_268]; struct QMErrInfo *
0x18001b7a9  mov     rcx, rdi; this
0x18001b7ac  call    ?SetTransientError@CJob@@IEAAXAEAUQMErrInfo@@J_N1@Z; CJob::SetTransientError(QMErrInfo &,long,bool,bool)
0x18001b7b1  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001b7b8  add     rcx, 208h; this
0x18001b7bf  call    ?CompleteWorkItem@TaskScheduler@@AEAAX_N@Z; TaskScheduler::CompleteWorkItem(bool)
0x18001b7c4  nop
0x18001b7c5  lea     rcx, [rsp+2B8h+var_278]; this
0x18001b7ca  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001b7cf  nop
0x18001b7d0  lea     rcx, [rsp+2B8h+var_250]; this
0x18001b7d5  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001b7da  jmp     loc_18001BA98
0x18001b7df  mov     rax, [rsp+2B8h+var_278]
0x18001b7e4  mov     rcx, [rax]
0x18001b7e7  cmp     [rbx], rcx
0x18001b7ea  jz      short loc_18001B809
0x18001b7ec  lea     rcx, [rsp+2B8h+var_250]; this
0x18001b7f1  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001b7f6  mov     rbx, [rsp+2B8h+var_278]
0x18001b7fb  mov     [rsp+2B8h+var_250], rbx
0x18001b800  lock inc dword ptr [rbx+8]
0x18001b804  mov     rax, [rsp+2B8h+var_278]
0x18001b809  mov     esi, 0FFFFFFFFh
0x18001b80e  mov     ecx, esi
0x18001b810  lock xadd [rax+8], ecx
0x18001b815  cmp     ecx, 1
0x18001b818  jnz     short loc_18001B851
0x18001b81a  mov     rcx, [rsp+2B8h+var_278]
0x18001b81f  mov     rdx, [rcx]
0x18001b822  lea     rax, [rdx-1]
0x18001b826  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b82a  ja      short loc_18001B842
0x18001b82c  mov     rcx, rdx; hObject
0x18001b82f  call    cs:__imp_CloseHandle
0x18001b835  mov     rax, [rsp+2B8h+var_278]
0x18001b83a  mov     [rax], r15
0x18001b83d  mov     rcx, [rsp+2B8h+var_278]; void *
0x18001b842  mov     edx, 10h; unsigned __int64
0x18001b847  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b84c  mov     [rsp+2B8h+var_278], r15
0x18001b851  mov     eax, [rdi+294h]
0x18001b857  cmp     eax, 2
0x18001b85a  jz      short loc_18001B8C5
0x18001b85c  cmp     eax, 1
0x18001b85f  jz      short loc_18001B8BD
0x18001b861  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b868  cmp     rcx, r12
0x18001b86b  jz      short loc_18001B88D
0x18001b86d  test    byte ptr [rcx+1Ch], 1
0x18001b871  jz      short loc_18001B88D
0x18001b873  mov     edx, 5Ah ; 'Z'
0x18001b878  mov     dword ptr [rsp+2B8h+var_290], r14d
0x18001b87d  mov     dword ptr [rsp+2B8h+var_298], eax
0x18001b881  mov     r9, rdi
0x18001b884  mov     rcx, [rcx+10h]
0x18001b888  call    WPP_SF_qll
0x18001b88d  mov     [rdi+294h], r14d
0x18001b894  lea     rdx, [rdi+60h]; struct TaskSchedulerWorkItem *
0x18001b898  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001b89f  add     rcx, 208h; this
0x18001b8a6  call    ?CancelWorkItem@TaskScheduler@@QEAA_NPEAVTaskSchedulerWorkItem@@@Z; TaskScheduler::CancelWorkItem(TaskSchedulerWorkItem *)
0x18001b8ab  xor     edx, edx
0x18001b8ad  mov     rcx, rdi
0x18001b8b0  call    ?UpdateModificationTime@CJob@@QEAAXW4UpdateBehavior@1@@Z; CJob::UpdateModificationTime(CJob::UpdateBehavior)
0x18001b8b5  mov     rcx, rdi; this
0x18001b8b8  call    ?ReevaluateIdleStopConditions@CJob@@AEAAXXZ; CJob::ReevaluateIdleStopConditions(void)
0x18001b8bd  mov     rcx, rdi; this
0x18001b8c0  call    ?ScheduleModificationCallback@CJob@@IEAAXXZ; CJob::ScheduleModificationCallback(void)
0x18001b8c5  movups  xmm0, xmmword ptr [rdi+530h]
0x18001b8cc  movaps  xmmword ptr [rsp+2B8h+var_248.Data1], xmm0
0x18001b8d1  lea     r8, [rdi+518h]; struct CustomUserContext *
0x18001b8d8  lea     rdx, [rsp+2B8h+var_248]; struct _GUID
0x18001b8dd  call    ?SignalBackgroundTransferSebEventBestEffort@CJobManager@@QEAAXU_GUID@@AEBVCustomUserContext@@@Z; CJobManager::SignalBackgroundTransferSebEventBestEffort(_GUID,CustomUserContext const &)
0x18001b8e2  mov     rax, [rdi]
0x18001b8e5  mov     qword ptr [rsp+2B8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18001b8ea  lock inc dword ptr [rbx+8]
0x18001b8ee  lea     rdx, [rsp+2B8h+SystemTimeAsFileTime]
0x18001b8f3  mov     rcx, rdi
0x18001b8f6  mov     rax, [rax+120h]
0x18001b8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b902  mov     [rdi+288h], rax
0x18001b909  test    rax, rax
0x18001b90c  jnz     short loc_18001B91D
0x18001b90e  lea     rcx, [rsp+2B8h+var_250]; this
0x18001b913  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001b918  jmp     loc_18001BA98
0x18001b91d  mov     rcx, [rax+20h]
0x18001b921  mov     rax, [rcx]
0x18001b924  mov     rax, [rax+30h]
0x18001b928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b92d  mov     rax, [rdi+288h]
0x18001b934  mov     rcx, [rax+30h]; pwa
0x18001b938  test    rcx, rcx
0x18001b93b  jz      short loc_18001B943
0x18001b93d  call    cs:__imp_CloseThreadpoolWait
0x18001b943  mov     r8, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001b94a  add     r8, 3E0h; pcbe
0x18001b951  mov     rdx, [rdi+288h]; pv
0x18001b958  lea     rcx, ?StaticOnTransferComplete@CJob@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001b95f  call    cs:__imp_CreateThreadpoolWait
0x18001b965  mov     rcx, [rdi+288h]
0x18001b96c  mov     [rcx+30h], rax
0x18001b970  mov     rcx, [rdi+288h]
0x18001b977  cmp     qword ptr [rcx+30h], 0
0x18001b97c  jnz     short loc_18001B9E9
0x18001b97e  call    cs:__imp_GetLastError
0x18001b984  test    eax, eax
0x18001b986  jg      short loc_18001B992
0x18001b988  call    cs:__imp_GetLastError
0x18001b98e  mov     ecx, eax
0x18001b990  jmp     short loc_18001B9A1
0x18001b992  call    cs:__imp_GetLastError
0x18001b998  movzx   ecx, ax
0x18001b99b  or      ecx, 80070000h
0x18001b9a1  xorps   xmm0, xmm0
0x18001b9a4  movups  [rsp+2B8h+var_160], xmm0
0x18001b9ac  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001b9b3  mov     [rsp+2B8h+var_168], rax
0x18001b9bb  mov     [rsp+2B8h+var_150], ecx
0x18001b9c2  mov     [rsp+2B8h+var_14C], 11CDh
0x18001b9cd  mov     [rsp+2B8h+var_148], r14d
0x18001b9d5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001b9dc  lea     rcx, [rsp+2B8h+var_168]; pExceptionObject
0x18001b9e4  call    _CxxThrowException_0
0x18001b9e9  mov     rcx, [rcx+20h]
0x18001b9ed  mov     rax, [rcx]
0x18001b9f0  mov     rax, [rax]
0x18001b9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9f8  mov     rcx, [rdi+288h]
  ... truncated ...
```
