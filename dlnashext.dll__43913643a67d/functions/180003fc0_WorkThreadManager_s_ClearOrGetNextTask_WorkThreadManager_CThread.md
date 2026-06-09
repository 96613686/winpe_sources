# WorkThreadManager::s_ClearOrGetNextTask(WorkThreadManager::CThread *)

- ea: `0x180003fc0`
- end: `0x1800046d8`
- name: `?s_ClearOrGetNextTask@WorkThreadManager@@CAXPEAVCThread@1@@Z`
- size: `1816`
- prototype: `void __fastcall(struct WorkThreadManager::CThread *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c994`

## callees

- `0x180001710`
- `0x180003fc0`
- `0x1800046e0`
- `0x180004890`
- `0x1800048d0`
- `0x180004fd0`
- `0x18000503c`
- `0x18000a760`
- `0x18000a784`
- `0x18000c5bc`
- `0x18000c620`
- `0x18000c648`
- `0x18000e044`
- `0x18000f08c`
- `0x180012667`
- `0x180012673`
- `0x18001272e`
- `0x18003132c`
- `0x1800316ac`
- `0x18003268c`
- `0x180032958`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004175`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004248`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004295`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800043ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800043fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800044ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000454f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800046be`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004175`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004248`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004295`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800043ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800043fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800044ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000454f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800046be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000445c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180004565`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000445c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180004565`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004451`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004559`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000407a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800045fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000407a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800045fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000441e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000441e`

## pseudocode

```c
void __fastcall WorkThreadManager::s_ClearOrGetNextTask(struct WorkThreadManager::CThread *a1)
{
  struct WorkThreadManager::TaskData *v1; // rbx
  WorkThreadManager::TaskList *v3; // rcx
  struct WorkThreadManager::TaskData *v4; // rsi
  HMODULE *v5; // r13
  WorkThreadManager::TaskData *v6; // r14
  unsigned __int64 *v7; // r15
  char v8; // al
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rcx
  HMODULE v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 *v14; // rax
  unsigned __int64 v15; // rax
  RTL_SRWLOCK **v16; // r14
  HMODULE v17; // r15
  RTL_SRWLOCK *v18; // rax
  int v19; // esi
  void *v20; // rdx
  WorkThreadManager::TaskData *v21; // rax
  unsigned int v22; // edx
  char v23; // r13
  unsigned __int64 v24; // rcx
  __int64 v25; // r10
  unsigned int v26; // edx
  unsigned int v27; // r8d
  int v28; // r9d
  unsigned __int64 v29; // rax
  DWORD LastError; // ebx
  __int64 v31; // rdx
  __int64 v32; // rcx
  int PriorityForOptions; // ebx
  __int64 v34; // r8
  __int64 v35; // r9
  int CurrentThreadPriority; // r15d
  BOOL v37; // esi
  HANDLE CurrentThread; // rax
  HMODULE v39; // r12
  unsigned int v40; // edx
  HANDLE v41; // rax
  WorkThreadManager::TaskData *v42; // rsi
  __int64 v43; // rax
  unsigned int v44; // edx
  WorkThreadManager::TaskData *v45; // rcx
  WorkThreadManager::TaskData *v46; // rbx
  DWORD TickCount; // eax
  unsigned int v48; // edx
  __int64 v49; // rax
  unsigned __int64 v50; // [rsp+20h] [rbp-E0h]
  _BYTE v51[12]; // [rsp+38h] [rbp-C8h]
  HMODULE hLibModule; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v53; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v54[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+78h] [rbp-88h]
  __int64 v57; // [rsp+80h] [rbp-80h]
  char v58; // [rsp+88h] [rbp-78h]
  __int16 v59; // [rsp+89h] [rbp-77h]
  char v60; // [rsp+8Bh] [rbp-75h]
  __int64 v61; // [rsp+8Ch] [rbp-74h]
  HMODULE v62; // [rsp+98h] [rbp-68h]
  unsigned __int64 v63; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v64[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v65; // [rsp+B8h] [rbp-48h]
  unsigned int v66; // [rsp+BCh] [rbp-44h]
  int v67; // [rsp+C0h] [rbp-40h]
  __int64 v68; // [rsp+C8h] [rbp-38h]
  char v69; // [rsp+D0h] [rbp-30h]
  __int16 v70; // [rsp+D1h] [rbp-2Fh]
  char v71; // [rsp+D3h] [rbp-2Dh]
  __int64 v72; // [rsp+D4h] [rbp-2Ch]
  HMODULE v73; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v74; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v75[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v76; // [rsp+100h] [rbp+0h] BYREF
  __int64 v77; // [rsp+108h] [rbp+8h] BYREF
  int v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  char v80; // [rsp+120h] [rbp+20h]
  __int16 v81; // [rsp+121h] [rbp+21h]
  char v82; // [rsp+123h] [rbp+23h]
  __int64 v83; // [rsp+124h] [rbp+24h]
  HMODULE v84[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v85[10]; // [rsp+140h] [rbp+40h] BYREF
  WorkThreadManager::TaskData *v86; // [rsp+1A0h] [rbp+A0h] BYREF
  WorkThreadManager::TaskData *v87; // [rsp+1A8h] [rbp+A8h] BYREF
  WorkThreadManager::TaskData *v88; // [rsp+1B0h] [rbp+B0h] BYREF
  RTL_SRWLOCK *v89; // [rsp+1B8h] [rbp+B8h] BYREF

  v1 = 0;
  v54[1] = v54;
  v54[0] = v54;
  v53 = 0;
  AcquireSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  v3 = (struct WorkThreadManager::CThread *)((char *)a1 + 24);
  WorkThreadManager::s_anyThreadMadeProgress = 1;
  if ( *(WorkThreadManager::TaskList **)v3 != v3 )
    v1 = WorkThreadManager::TaskList::RawRemoveHead(v3);
  v87 = v1;
  v4 = (struct WorkThreadManager::CThread *)((char *)a1 + 144);
  v5 = (HMODULE *)((char *)a1 + 184);
  v6 = v1;
  v7 = (unsigned __int64 *)((char *)a1 + 192);
  if ( v1 )
  {
    LODWORD(v87) = GetTickCount();
    AcquireSRWLockExclusive_0((PSRWLOCK)a1 + 28);
    v8 = *((_BYTE *)a1 + 171);
    LODWORD(v55) = *(_DWORD *)v4;
    HIDWORD(v55) = *((_DWORD *)a1 + 37);
    v9 = *((_DWORD *)a1 + 38);
    v60 = v8;
    v10 = *(_QWORD *)((char *)a1 + 172);
    v56 = v9;
    v11 = *((_QWORD *)a1 + 20);
    v61 = v10;
    v12 = *v5;
    v57 = v11;
    LOBYTE(v11) = *((_BYTE *)a1 + 168);
    v62 = v12;
    v58 = v11;
    v59 = *(_WORD *)((char *)a1 + 169);
    *v5 = 0;
    v63 = 0;
    if ( &v63 != v7 )
    {
      v63 = *v7;
      *v7 = 0;
    }
    v64[1] = v64;
    v64[0] = v64;
    if ( v4 != v1 )
    {
      *(_DWORD *)v4 = *(_DWORD *)v1;
      v13 = 0;
      *((_DWORD *)a1 + 37) = *((_DWORD *)v1 + 1);
      *((_DWORD *)a1 + 38) = *((_DWORD *)v1 + 2);
      *((_QWORD *)a1 + 20) = *((_QWORD *)v1 + 2);
      v14 = (unsigned __int64 *)((char *)v1 + 48);
      if ( &v76 != (unsigned __int64 *)((char *)v1 + 48) )
      {
        v13 = *v14;
        *v14 = 0;
      }
      v15 = *v7;
      *v7 = v13;
      v76 = v15;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v76);
      v16 = (RTL_SRWLOCK **)((char *)v1 + 40);
      if ( v5 != (HMODULE *)((char *)v1 + 40) )
      {
        v17 = *v5;
        v18 = *v16;
        v89 = *v16;
        if ( v17 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v88);
          FreeLibrary(v17);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v88);
          v18 = v89;
        }
        *v5 = (HMODULE)v18;
        *v16 = 0;
      }
      *((_QWORD *)a1 + 21) = *((_QWORD *)v1 + 3);
      *((_DWORD *)a1 + 44) = *((_DWORD *)v1 + 8);
    }
    v19 = *((_DWORD *)a1 + 20);
    *((_DWORD *)a1 + 54) = (_DWORD)v87;
    *((_BYTE *)a1 + 89) = 0;
    if ( GetCurrentThreadId_0() != v19 && v19 )
      wil::details::SetEvent(*((wil::details **)a1 + 13), v20);
    if ( a1 != (struct WorkThreadManager::CThread *)-224LL )
      ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 28);
    v50 = v55;
    v21 = (WorkThreadManager::TaskData *)v53;
    v53 = v63;
    v63 = 0;
    v87 = v21;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v87);
    hLibModule = v62;
    v62 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v63);
    if ( v62 )
      FreeLibrary(v62);
    v87 = 0;
    v6 = 0;
    WorkThreadManager::TaskData::`scalar deleting destructor'(v1, v22);
    v23 = 0;
  }
  else
  {
    AcquireSRWLockExclusive_0((PSRWLOCK)a1 + 28);
    *((_BYTE *)a1 + 89) = 0;
    v24 = 0;
    v25 = *((_QWORD *)a1 + 20);
    v26 = *(_DWORD *)v4;
    v27 = *((_DWORD *)a1 + 37);
    v28 = *((_DWORD *)a1 + 38);
    v69 = *((_BYTE *)a1 + 168);
    v70 = *(_WORD *)((char *)a1 + 169);
    v71 = *((_BYTE *)a1 + 171);
    v72 = *(_QWORD *)((char *)a1 + 172);
    v73 = *v5;
    v65 = v26;
    v66 = v27;
    v67 = v28;
    v68 = v25;
    *v5 = 0;
    v74 = 0;
    if ( &v74 != v7 )
    {
      v24 = *v7;
      v74 = *v7;
      *v7 = 0;
    }
    v75[1] = v75;
    v75[0] = v75;
    if ( a1 != (struct WorkThreadManager::CThread *)-224LL )
    {
      ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 28);
      v24 = v74;
      v27 = v66;
      v26 = v65;
    }
    v29 = v53;
    v53 = v24;
    v50 = __PAIR64__(v27, v26);
    v74 = 0;
    v86 = (WorkThreadManager::TaskData *)v29;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v86);
    hLibModule = v73;
    v73 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v74);
    if ( v73 )
      FreeLibrary(v73);
    *((_BYTE *)a1 + 41) = 1;
    v23 = 1;
  }
  LastError = GetLastError();
  ReleaseSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  SetLastError(LastError);
  PriorityForOptions = GetPriorityForOptions(HIDWORD(v50));
  if ( PriorityForOptions == 0x10000 )
  {
    CurrentThreadPriority = 0x20000;
  }
  else
  {
    v37 = 0;
    CurrentThreadPriority = GetCurrentThreadPriority(v32, v31, v34, v35, v50);
    if ( PriorityForOptions == 0x7FFFFFFF )
      goto LABEL_33;
  }
  CurrentThread = GetCurrentThread();
  v37 = SetThreadPriority(CurrentThread, PriorityForOptions);
LABEL_33:
  v77 = 1;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84[0] = 0;
  v79 = 0;
  v85[1] = v85;
  v85[0] = v85;
  v86 = (WorkThreadManager::TaskData *)v53;
  v78 = 0;
  v80 = 0;
  v84[1] = 0;
  v53 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v86);
  v39 = v84[0];
  if ( hLibModule )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v86);
    FreeLibrary(hLibModule);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v86);
  }
  v51[0] = v80;
  *(_WORD *)&v51[1] = v81;
  v51[3] = v82;
  *(_QWORD *)&v51[4] = v83;
  v84[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v84[1]);
  if ( v84[0] )
    FreeLibrary(v84[0]);
  if ( v37 )
  {
    v41 = GetCurrentThread();
    SetThreadPriority(v41, CurrentThreadPriority);
  }
  if ( v23 )
  {
    v86 = 0;
    v42 = 0;
    AcquireSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
    v89 = &WorkThreadManager::s_rwLock;
    *((_BYTE *)a1 + 41) = 0;
    v43 = WorkThreadManager::TaskList::PopFront(&WorkThreadManager::s_taskFloodingList, &v88);
    wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
      &v87,
      v43);
    v45 = v88;
    v88 = 0;
    if ( v45 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v45, v44);
    v46 = v87;
    if ( v87
      && *((_DWORD *)v87 + 2) == *((_DWORD *)a1 + 38)
      && (unsigned __int8)WorkThreadManager::CThread::Eligible(a1, *(unsigned int *)v87, *((unsigned int *)v87 + 1)) )
    {
      TickCount = GetTickCount();
      WorkThreadManager::CThread::SetThreadTask(a1, &v77, v46, TickCount, 1, 0, 0, *(_QWORD *)v51, *(_DWORD *)&v51[8]);
      WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v77);
      v6 = 0;
      if ( v46 )
        WorkThreadManager::TaskData::`scalar deleting destructor'(v46, v48);
    }
    else
    {
      wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
        &v86,
        &v87);
      v6 = v87;
      v42 = v86;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v89,
      0);
    if ( v42 )
    {
      v49 = wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(
              &v87,
              &v86);
      WorkThreadManager::s_AttachAndRecoverTask(v49);
      v42 = v86;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v89);
    if ( v42 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v42, v40);
  }
  if ( v6 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v6, v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v53);
  if ( v39 )
    FreeLibrary(v39);
}

```

## disassembly

```asm
0x180003fc0  push    rbp
0x180003fc2  push    rbx
0x180003fc3  push    rsi
0x180003fc4  push    rdi
0x180003fc5  push    r12
0x180003fc7  push    r13
0x180003fc9  push    r14
0x180003fcb  push    r15
0x180003fcd  lea     rbp, [rsp-58h]
0x180003fd2  sub     rsp, 158h
0x180003fd9  xor     eax, eax
0x180003fdb  mov     [rsp+190h+var_170], 1
0x180003fe4  xor     ebx, ebx
0x180003fe6  mov     [rsp+190h+var_157], ax
0x180003feb  mov     [rsp+190h+var_155], al
0x180003fef  xorps   xmm0, xmm0
0x180003ff2  mov     [rsp+190h+var_154], rax
0x180003ff7  mov     rdi, rcx
0x180003ffa  movups  xmmword ptr [rsp+190h+var_138], xmm0
0x180003fff  lea     rax, [rsp+190h+var_138]
0x180004004  mov     [rsp+190h+var_168], ebx
0x180004008  mov     [rsp+190h+var_138+8], rax
0x18000400d  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x180004014  lea     rax, [rsp+190h+var_138]
0x180004019  mov     [rsp+190h+var_160], rbx
0x18000401e  mov     [rsp+190h+var_138], rax
0x180004023  mov     [rsp+190h+var_158], bl
0x180004027  mov     [rsp+190h+hLibModule], rbx
0x18000402c  mov     [rsp+190h+var_140], rbx
0x180004031  call    AcquireSRWLockExclusive_0
0x180004036  lea     rcx, [rdi+18h]; this
0x18000403a  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, 1; bool WorkThreadManager::s_anyThreadMadeProgress
0x180004041  cmp     [rcx], rcx
0x180004044  jz      short loc_18000404E
0x180004046  call    ?RawRemoveHead@TaskList@WorkThreadManager@@AEAAPEAUTaskData@2@XZ; WorkThreadManager::TaskList::RawRemoveHead(void)
0x18000404b  mov     rbx, rax
0x18000404e  mov     [rbp+90h+arg_8], rbx
0x180004055  lea     rsi, [rdi+90h]
0x18000405c  lea     r13, [rsi+28h]
0x180004060  mov     r14, rbx
0x180004063  lea     r15, [rsi+30h]
0x180004067  lea     r12, [rdi+0E0h]
0x18000406e  test    rbx, rbx
0x180004071  jz      loc_1800042B5
0x180004077  xor     r14d, r14d
0x18000407a  call    cs:__imp_GetTickCount
0x180004080  mov     rcx, r12; SRWLock
0x180004083  mov     dword ptr [rbp+90h+arg_8], eax
0x180004089  call    AcquireSRWLockExclusive_0
0x18000408e  mov     ecx, [rsi]
0x180004090  mov     al, [rsi+1Bh]
0x180004093  mov     dword ptr [rsp+190h+var_120], ecx
0x180004097  mov     ecx, [rsi+4]
0x18000409a  mov     dword ptr [rsp+190h+var_120+4], ecx
0x18000409e  mov     ecx, [rsi+8]
0x1800040a1  mov     [rbp+90h+var_105], al
0x1800040a4  mov     rax, [rsi+1Ch]
0x1800040a8  mov     [rsp+190h+var_118], ecx
0x1800040ac  mov     rcx, [rsi+10h]
0x1800040b0  mov     [rbp+90h+var_104], rax
0x1800040b4  mov     rax, [r13+0]
0x1800040b8  mov     [rbp+90h+var_110], rcx
0x1800040bc  mov     cl, [rsi+18h]
0x1800040bf  mov     [rbp+90h+var_F8], rax
0x1800040c3  lea     rax, [rbp+90h+var_F0]
0x1800040c7  mov     [rbp+90h+var_108], cl
0x1800040ca  movzx   ecx, word ptr [rsi+19h]
0x1800040ce  mov     [rbp+90h+var_107], cx
0x1800040d2  mov     [r13+0], r14
0x1800040d6  mov     [rbp+90h+var_F0], r14
0x1800040da  cmp     rax, r15
0x1800040dd  jz      short loc_1800040E9
0x1800040df  mov     rax, [r15]
0x1800040e2  mov     [rbp+90h+var_F0], rax
0x1800040e6  mov     [r15], r14
0x1800040e9  lea     rax, [rbp+90h+var_E8]
0x1800040ed  xorps   xmm0, xmm0
0x1800040f0  movups  [rbp+90h+var_E8], xmm0
0x1800040f4  mov     qword ptr [rbp+90h+var_E8+8], rax
0x1800040f8  lea     rax, [rbp+90h+var_E8]
0x1800040fc  mov     qword ptr [rbp+90h+var_E8], rax
0x180004100  cmp     rsi, rbx
0x180004103  jz      loc_1800041AC
0x180004109  mov     eax, [rbx]
0x18000410b  lea     rdx, [rbp+90h+var_90]
0x18000410f  mov     [rsi], eax
0x180004111  mov     rcx, r14
0x180004114  mov     eax, [rbx+4]
0x180004117  mov     [rsi+4], eax
0x18000411a  mov     eax, [rbx+8]
0x18000411d  mov     [rsi+8], eax
0x180004120  mov     rax, [rbx+10h]
0x180004124  mov     [rsi+10h], rax
0x180004128  lea     rax, [rbx+30h]
0x18000412c  cmp     rdx, rax
0x18000412f  jz      short loc_180004137
0x180004131  mov     rcx, [rax]
0x180004134  mov     [rax], r14
0x180004137  mov     rax, [r15]
0x18000413a  mov     [r15], rcx
0x18000413d  lea     rcx, [rbp+90h+var_90]
0x180004141  mov     [rbp+90h+var_90], rax
0x180004145  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000414a  lea     r14, [rbx+28h]
0x18000414e  cmp     r13, r14
0x180004151  jz      short loc_180004199
0x180004153  mov     r15, [r13+0]
0x180004157  mov     rax, [r14]
0x18000415a  mov     [rbp+90h+arg_18], rax
0x180004161  test    r15, r15
0x180004164  jz      short loc_18000418E
0x180004166  lea     rcx, [rbp+90h+arg_10]; this
0x18000416d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004172  mov     rcx, r15; hLibModule
0x180004175  call    cs:__imp_FreeLibrary
0x18000417b  lea     rcx, [rbp+90h+arg_10]; this
0x180004182  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180004187  mov     rax, [rbp+90h+arg_18]
0x18000418e  mov     [r13+0], rax
0x180004192  mov     qword ptr [r14], 0
0x180004199  movsd   xmm0, qword ptr [rbx+18h]
0x18000419e  xor     r14d, r14d
0x1800041a1  movsd   qword ptr [rsi+18h], xmm0
0x1800041a6  mov     eax, [rbx+20h]
0x1800041a9  mov     [rsi+20h], eax
0x1800041ac  mov     eax, dword ptr [rbp+90h+arg_8]
0x1800041b2  mov     esi, [rdi+50h]
0x1800041b5  mov     [rdi+0D8h], eax
0x1800041bb  mov     [rdi+59h], r14b
0x1800041bf  call    GetCurrentThreadId_0
0x1800041c4  cmp     eax, esi
0x1800041c6  jz      short loc_1800041D5
0x1800041c8  test    esi, esi
0x1800041ca  jz      short loc_1800041D5
0x1800041cc  mov     rcx, [rdi+68h]; this
0x1800041d0  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800041d5  test    r12, r12
0x1800041d8  jz      short loc_1800041E2
0x1800041da  mov     rcx, r12; SRWLock
0x1800041dd  call    ReleaseSRWLockExclusive_0
0x1800041e2  mov     eax, dword ptr [rsp+190h+var_120]
0x1800041e6  xor     r12d, r12d
0x1800041e9  mov     rcx, [rbp+90h+var_F0]
0x1800041ed  mov     dword ptr [rsp+190h+var_170], eax
0x1800041f1  mov     eax, dword ptr [rsp+190h+var_120+4]
0x1800041f5  mov     dword ptr [rsp+190h+var_170+4], eax
0x1800041f9  mov     eax, [rsp+190h+var_118]
0x1800041fd  mov     [rsp+190h+var_168], eax
0x180004201  mov     rax, [rbp+90h+var_110]
0x180004205  mov     [rsp+190h+var_160], rax
0x18000420a  mov     rax, [rsp+190h+var_140]
0x18000420f  mov     [rsp+190h+var_140], rcx
0x180004214  lea     rcx, [rbp+90h+arg_8]
0x18000421b  mov     [rbp+90h+var_F0], r12
0x18000421f  mov     [rbp+90h+arg_8], rax
0x180004226  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000422b  mov     rsi, [rsp+190h+hLibModule]
0x180004230  mov     r14, [rbp+90h+var_F8]
0x180004234  test    rsi, rsi
0x180004237  jz      short loc_18000425A
0x180004239  lea     rcx, [rbp+90h+arg_8]; this
0x180004240  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004245  mov     rcx, rsi; hLibModule
0x180004248  call    cs:__imp_FreeLibrary
0x18000424e  lea     rcx, [rbp+90h+arg_8]; this
0x180004255  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000425a  mov     al, [rbp+90h+var_108]
0x18000425d  lea     rcx, [rbp+90h+var_F0]
0x180004261  mov     [rsp+190h+var_158], al
0x180004265  movzx   eax, [rbp+90h+var_107]
0x180004269  mov     [rsp+190h+var_157], ax
0x18000426e  mov     al, [rbp+90h+var_105]
0x180004271  mov     [rsp+190h+var_155], al
0x180004275  mov     rax, [rbp+90h+var_104]
0x180004279  mov     [rsp+190h+var_154], rax
0x18000427e  mov     [rsp+190h+hLibModule], r14
0x180004283  mov     [rbp+90h+var_F8], r12
0x180004287  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000428c  mov     rcx, [rbp+90h+var_F8]; hLibModule
0x180004290  test    rcx, rcx
0x180004293  jz      short loc_18000429B
0x180004295  call    cs:__imp_FreeLibrary
0x18000429b  mov     rcx, rbx; this
0x18000429e  mov     [rbp+90h+arg_8], r12
0x1800042a5  mov     r14, r12
0x1800042a8  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x1800042ad  mov     r13b, r12b
0x1800042b0  jmp     loc_180004408
0x1800042b5  mov     rcx, r12; SRWLock
0x1800042b8  call    AcquireSRWLockExclusive_0
0x1800042bd  xor     r11d, r11d
0x1800042c0  mov     [rdi+59h], r11b
0x1800042c4  mov     ecx, r11d
0x1800042c7  mov     al, [rsi+18h]
0x1800042ca  mov     r10, [rsi+10h]
0x1800042ce  mov     edx, [rsi]
0x1800042d0  mov     r8d, [rsi+4]
0x1800042d4  mov     r9d, [rsi+8]
0x1800042d8  mov     [rbp+90h+var_C0], al
0x1800042db  movzx   eax, word ptr [rsi+19h]
0x1800042df  mov     [rbp+90h+var_BF], ax
0x1800042e3  mov     al, [rsi+1Bh]
0x1800042e6  mov     [rbp+90h+var_BD], al
0x1800042e9  mov     rax, [rsi+1Ch]
0x1800042ed  mov     [rbp+90h+var_BC], rax
0x1800042f1  mov     rax, [r13+0]
0x1800042f5  mov     [rbp+90h+var_B0], rax
0x1800042f9  lea     rax, [rbp+90h+var_A8]
0x1800042fd  mov     [rbp+90h+var_D8], edx
0x180004300  mov     [rbp+90h+var_D4], r8d
0x180004304  mov     [rbp+90h+var_D0], r9d
0x180004308  mov     [rbp+90h+var_C8], r10
0x18000430c  mov     [r13+0], r11
0x180004310  mov     [rbp+90h+var_A8], rcx
0x180004314  cmp     rax, r15
0x180004317  jz      short loc_180004323
0x180004319  mov     rcx, [r15]
0x18000431c  mov     [rbp+90h+var_A8], rcx
0x180004320  mov     [r15], r11
0x180004323  lea     rax, [rbp+90h+var_A0]
0x180004327  xorps   xmm0, xmm0
0x18000432a  movups  [rbp+90h+var_A0], xmm0
0x18000432e  mov     qword ptr [rbp+90h+var_A0+8], rax
0x180004332  lea     rax, [rbp+90h+var_A0]
0x180004336  mov     qword ptr [rbp+90h+var_A0], rax
0x18000433a  test    r12, r12
0x18000433d  jz      short loc_18000435A
0x18000433f  mov     rcx, r12; SRWLock
0x180004342  call    ReleaseSRWLockExclusive_0
0x180004347  mov     rcx, [rbp+90h+var_A8]
0x18000434b  mov     r10, [rbp+90h+var_C8]
0x18000434f  mov     r9d, [rbp+90h+var_D0]
0x180004353  mov     r8d, [rbp+90h+var_D4]
0x180004357  mov     edx, [rbp+90h+var_D8]
0x18000435a  mov     rax, [rsp+190h+var_140]
0x18000435f  xor     r12d, r12d
0x180004362  mov     [rsp+190h+var_140], rcx
0x180004367  lea     rcx, [rbp+90h+arg_0]
0x18000436e  mov     dword ptr [rsp+190h+var_170], edx
0x180004372  mov     dword ptr [rsp+190h+var_170+4], r8d
0x180004377  mov     [rsp+190h+var_168], r9d
0x18000437c  mov     [rsp+190h+var_160], r10
0x180004381  mov     [rbp+90h+var_A8], r12
0x180004385  mov     [rbp+90h+arg_0], rax
0x18000438c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180004391  mov     rbx, [rsp+190h+hLibModule]
0x180004396  mov     rsi, [rbp+90h+var_B0]
0x18000439a  test    rbx, rbx
0x18000439d  jz      short loc_1800043C0
0x18000439f  lea     rcx, [rbp+90h+arg_0]; this
0x1800043a6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800043ab  mov     rcx, rbx; hLibModule
0x1800043ae  call    cs:__imp_FreeLibrary
0x1800043b4  lea     rcx, [rbp+90h+arg_0]; this
0x1800043bb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800043c0  mov     al, [rbp+90h+var_C0]
0x1800043c3  lea     rcx, [rbp+90h+var_A8]
0x1800043c7  mov     [rsp+190h+var_158], al
0x1800043cb  movzx   eax, [rbp+90h+var_BF]
0x1800043cf  mov     [rsp+190h+var_157], ax
0x1800043d4  mov     al, [rbp+90h+var_BD]
0x1800043d7  mov     [rsp+190h+var_155], al
0x1800043db  mov     rax, [rbp+90h+var_BC]
0x1800043df  mov     [rsp+190h+var_154], rax
0x1800043e4  mov     [rsp+190h+hLibModule], rsi
0x1800043e9  mov     [rbp+90h+var_B0], r12
0x1800043ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800043f2  mov     rcx, [rbp+90h+var_B0]; hLibModule
0x1800043f6  test    rcx, rcx
0x1800043f9  jz      short loc_180004401
0x1800043fb  call    cs:__imp_FreeLibrary
0x180004401  mov     byte ptr [rdi+29h], 1
0x180004405  mov     r13b, 1
0x180004408  call    cs:__imp_GetLastError
0x18000440e  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x180004415  mov     ebx, eax
0x180004417  call    ReleaseSRWLockExclusive_0
0x18000441c  mov     ecx, ebx; dwErrCode
0x18000441e  call    cs:__imp_SetLastError
0x180004424  mov     ecx, dword ptr [rsp+190h+var_170+4]
0x180004428  call    ?GetPriorityForOptions@@YAHW4TaskOptions@Internal@Windows@@@Z; GetPriorityForOptions(Windows::Internal::TaskOptions)
0x18000442d  mov     ebx, eax
0x18000442f  cmp     eax, 10000h
0x180004434  jnz     short loc_18000443E
0x180004436  mov     r15d, 20000h
0x18000443c  jmp     short loc_180004451
0x18000443e  mov     esi, r12d
0x180004441  call    GetCurrentThreadPriority
0x180004446  mov     r15d, eax
0x180004449  cmp     ebx, 7FFFFFFFh
0x18000444f  jz      short loc_180004464
0x180004451  call    cs:__imp_GetCurrentThread
0x180004457  mov     rcx, rax; hThread
0x18000445a  mov     edx, ebx; nPriority
0x18000445c  call    cs:__imp_SetThreadPriority
0x180004462  mov     esi, eax
0x180004464  xor     eax, eax
0x180004466  mov     [rbp+90h+var_88], 1
0x18000446e  mov     [rbp+90h+var_6F], ax
0x180004472  xorps   xmm1, xmm1
  ... truncated ...
```
