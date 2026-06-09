# CFile::ValidateDriveInfo(TokenHandle,QMErrInfo &)

- ea: `0x18001c9c4`
- end: `0x18001cf33`
- name: `?ValidateDriveInfo@CFile@@QEAA_NVTokenHandle@@AEAUQMErrInfo@@@Z`
- size: `1391`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001bac0`
- `0x18008c480`

## callees

- `0x180008b70`
- `0x18000db20`
- `0x180014004`
- `0x1800141cc`
- `0x180014310`
- `0x18001c9c4`
- `0x18001d7f0`
- `0x18001e1d0`
- `0x18001e234`
- `0x1800383a8`
- `0x18003dcb0`
- `0x18005e730`
- `0x180070404`
- `0x1800946a4`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800b1fe8`
- `0x1800f4f2c`
- `0x1800f64f4`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001cc67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001cc80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001cc67`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001cc80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ca56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ca56`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001cce3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001cce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb16`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001cd8e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001cd8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ceab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ceab`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001cb0c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001cb0c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001cb8e`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001cb8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall CFile::ValidateDriveInfo(__int64 a1, TokenHandle *a2, __int64 a3)
{
  __int64 *v6; // rbx
  _DWORD *v7; // rax
  signed int LastError; // eax
  UINT DriveTypeW; // eax
  UINT v10; // r14d
  unsigned int v11; // r12d
  __int64 v12; // rax
  int IsVolumeLocked; // eax
  int v14; // eax
  int v15; // r8d
  char result; // al
  unsigned int v17; // r8d
  unsigned __int16 *v18; // r9
  CJobManager *v19; // r12
  DWORD v20; // edi
  const char *CallbackName; // rax
  __int64 v22; // r10
  _QWORD *v23; // rdi
  const unsigned __int16 *v24; // rax
  char *v25; // rcx
  int v26; // edi
  EVENT_LOG *v27; // rcx
  __int64 *v28; // rdx
  __int64 v29; // rbx
  const unsigned __int16 *v30; // rax
  __int64 v31; // [rsp+0h] [rbp-298h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-258h]
  void *v33; // [rsp+48h] [rbp-250h] BYREF
  unsigned __int16 *v34; // [rsp+50h] [rbp-248h] BYREF
  __int64 *v35; // [rsp+58h] [rbp-240h] BYREF
  HANDLE *v36; // [rsp+60h] [rbp-238h] BYREF
  char v37; // [rsp+68h] [rbp-230h]
  volatile signed __int32 *v38; // [rsp+70h] [rbp-228h]
  __int64 v39; // [rsp+78h] [rbp-220h]
  _DWORD *v40; // [rsp+80h] [rbp-218h]
  __int64 v41; // [rsp+88h] [rbp-210h]
  __int64 *v42; // [rsp+90h] [rbp-208h]
  __int64 v43; // [rsp+98h] [rbp-200h]
  __int64 v44; // [rsp+A0h] [rbp-1F8h]
  TokenHandle *v45; // [rsp+A8h] [rbp-1F0h]
  _QWORD v46[3]; // [rsp+B0h] [rbp-1E8h] BYREF
  DWORD v47; // [rsp+C8h] [rbp-1D0h]
  void **pExceptionObject; // [rsp+D0h] [rbp-1C8h] BYREF
  __int128 v49; // [rsp+D8h] [rbp-1C0h]
  int v50; // [rsp+E8h] [rbp-1B0h]
  int v51; // [rsp+ECh] [rbp-1ACh]
  int v52; // [rsp+F0h] [rbp-1A8h]
  void **v53; // [rsp+130h] [rbp-168h] BYREF
  __int128 v54; // [rsp+138h] [rbp-160h]
  signed int v55; // [rsp+148h] [rbp-150h]
  int v56; // [rsp+14Ch] [rbp-14Ch]
  int v57; // [rsp+150h] [rbp-148h]
  void **v58; // [rsp+190h] [rbp-108h] BYREF
  __int128 v59; // [rsp+198h] [rbp-100h]
  int v60; // [rsp+1A8h] [rbp-F0h]
  int v61; // [rsp+1ACh] [rbp-ECh]
  int v62; // [rsp+1B0h] [rbp-E8h]
  void **v63; // [rsp+1F0h] [rbp-A8h] BYREF
  __int64 v64; // [rsp+1F8h] [rbp-A0h] BYREF
  int v65; // [rsp+208h] [rbp-90h]

  v43 = a1;
  v45 = a2;
  v44 = a3;
  _InterlockedAdd(&dword_180145058, 1u);
  v6 = &GenericStringHandle<unsigned short>::s_EmptyString;
  v35 = &GenericStringHandle<unsigned short>::s_EmptyString;
  try
  {
    CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v36);
    v37 = 0;
    v38 = *(volatile signed __int32 **)a2;
    _InterlockedAdd(v38 + 2, 1u);
    v39 = 0;
    v7 = HeapAlloc(hBitsHeap, 8u, 4u);
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
      v49 = 0;
      pExceptionObject = &ComError::`vftable';
      v50 = -2147024882;
      v51 = 0;
      v52 = 1;
      throw (ComError *)&pExceptionObject;
    }
    *v7 = 1;
    v40 = v7;
    v41 = 0;
    _InterlockedAdd(&dword_180145058, 1u);
    v42 = &GenericStringHandle<unsigned short>::s_EmptyString;
    if ( !v37 )
    {
      if ( !ImpersonateLoggedOnUser(*(HANDLE *)v38) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v54 = 0;
        v53 = &ComError::`vftable';
        v55 = LastError;
        v56 = 0;
        v57 = 1;
        throw (ComError *)&v53;
      }
      v37 = 1;
    }
    BITSGetVolumePathName(&v33, *(_QWORD *)(a1 + 16) + 12LL);
    DriveTypeW = GetDriveTypeW((LPCWSTR)v33 + 6);
    v10 = DriveTypeW;
    if ( (DriveTypeW & 0xFFFFFFFA) != 0 || DriveTypeW == 5 )
    {
      v12 = BITSGetVolumeNameForVolumeMountPoint(&v34, (char *)v33 + 12);
      GenericStringHandle<unsigned short>::operator=(&v35, v12);
      GenericStringHandle<unsigned short>::FreeIt(&v34);
      CNestedImpersonation::Revert((CNestedImpersonation *)&v36);
      v6 = v35;
      IsVolumeLocked = CDeviceNotificationController::IsVolumeLocked(
                         (CJobManager *)((char *)g_Manager + 96),
                         (const unsigned __int16 *)v35 + 6);
      if ( IsVolumeLocked < 0 )
      {
        v59 = 0;
        v58 = &ComError::`vftable';
        v60 = IsVolumeLocked;
        v61 = 2041;
        v62 = 1;
        throw (ComError *)&v58;
      }
      v11 = BITSGetVolumeSerialNumber((LPCWSTR)v6 + 6);
    }
    else
    {
      v11 = 0;
    }
    if ( (unsigned int)_o__wcsicmp((char *)v33 + 12, *(_QWORD *)(a1 + 272) + 12LL)
      || (unsigned int)_o__wcsicmp((char *)v6 + 12, *(_QWORD *)(a1 + 280) + 12LL)
      || *(_DWORD *)(a1 + 288) != v10
      || (v14 = *(_DWORD *)(a1 + 292)) != 0 && v14 != v11 )
    {
      if ( v37 )
      {
        SetThreadToken(0, *v36);
        v37 = 0;
      }
      v17 = *(_DWORD *)(a1 + 292);
      v32 = v17;
      v18 = (unsigned __int16 *)(*(_QWORD *)(a1 + 280) + 12LL);
      v34 = v18;
      v19 = g_Manager;
      v20 = *((_DWORD *)g_GlobalInfo + 52);
      v46[0] = *((_QWORD *)g_GlobalInfo + 24);
      v46[1] = *((_QWORD *)g_GlobalInfo + 25);
      v46[2] = 0x80000000LL;
      v47 = v20;
      if ( (v46[0] & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          CallbackName = CallbackSleepHelper::GetCallbackName(0x80000000);
          WPP_SF_s(*(_QWORD *)(v22 + 16), 10, WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, CallbackName);
        }
        Sleep(v20);
        v18 = v34;
        v17 = v32;
      }
      v23 = (_QWORD *)*((_QWORD *)v19 + 87);
      while ( v23 != (_QWORD *)((char *)v19 + 688) )
      {
        CJob::OnDiskChange((CJob *)((unsigned __int64)(v23 - 78) & -(__int64)(v23 != 0)), v18, v17);
        v23 = (_QWORD *)v23[1];
        v18 = v34;
        v17 = v32;
      }
      CJobManager::ScheduleAnotherGroup(v19);
      CallbackSleepHelper::~CallbackSleepHelper((CallbackSleepHelper *)v46);
      *(_DWORD *)(a3 + 12) = 4;
      *(_DWORD *)(a3 + 8) = 1;
      *(_DWORD *)(a3 + 4) = -2145386482;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v24 = &qword_18011AC70;
        if ( *(_QWORD *)(a3 + 16) )
          v24 = *(const unsigned __int16 **)(a3 + 16);
        WPP_SF_llDDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 1, -2145386482, *(_DWORD *)a3, 1, 14, 4, (__int64)v24);
      }
      *(_DWORD *)a3 = 4;
      if ( v33 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33 + 2, 0xFFFFFFFF) == 1 )
          operator delete(v33, 0x10u);
        v33 = 0;
      }
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&v36);
      if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
        operator delete(v6, 0x10u);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)a2 + 8LL)) )
      {
        v25 = **(char ***)a2;
        if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(v25);
          **(_QWORD **)a2 = 0;
        }
        operator delete(*(void **)a2, 0x10u);
        *(_QWORD *)a2 = 0;
      }
      result = 0;
    }
    else
    {
      GenericStringHandle<unsigned short>::FreeIt(&v33);
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&v36);
      GenericStringHandle<unsigned short>::FreeIt(&v35);
      TokenHandle::Decrement(a2);
      result = 1;
    }
  }
  catch ( ComError v63 )
  {
    v28 = &v31;
    v26 = v65;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (int)WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        *(_QWORD *)(v43 + 16) + 12,
        v65);
      v27 = WPP_GLOBAL_Control;
    }
    if ( v26 == -2147024891 )
    {
      if ( v27 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)v27 + 2), 36, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
      v26 = -2145386483;
    }
    v29 = v44;
    *(_DWORD *)(v44 + 12) = 4;
    *(_DWORD *)(v29 + 8) = 1;
    *(_DWORD *)(v29 + 4) = v26;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *(_QWORD *)(v29 + 16) )
        v30 = *(const unsigned __int16 **)(v29 + 16);
      else
        v30 = &qword_18011AC70;
      WPP_SF_llDDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v28, v15, *(_DWORD *)v29, 1, v26, 4, (__int64)v30);
    }
    *(_DWORD *)v29 = 3;
    v63 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(&v64);
    TokenHandle::Decrement(v45);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c9c4  push    rbx
0x18001c9c6  push    rsi
0x18001c9c7  push    rdi
0x18001c9c8  push    r12
0x18001c9ca  push    r13
0x18001c9cc  push    r14
0x18001c9ce  push    r15
0x18001c9d0  sub     rsp, 260h
0x18001c9d7  mov     rax, cs:__security_cookie
0x18001c9de  xor     rax, rsp
0x18001c9e1  mov     [rsp+298h+var_48], rax
0x18001c9e9  mov     r15, r8
0x18001c9ec  mov     rsi, rdx
0x18001c9ef  mov     rdi, rcx
0x18001c9f2  mov     [rsp+298h+var_200], rcx
0x18001c9fa  mov     [rsp+298h+var_1F0], rdx
0x18001ca02  mov     [rsp+298h+var_1F8], r8
0x18001ca0a  xor     r13d, r13d
0x18001ca0d  lea     r12d, [r13+1]
0x18001ca11  lock add cs:dword_180145058, r12d
0x18001ca19  lea     rbx, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18001ca20  mov     [rsp+298h+var_240], rbx
0x18001ca25  lea     rcx, [rsp+298h+var_238]; this
0x18001ca2a  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18001ca2f  nop
0x18001ca30  mov     [rsp+298h+var_230], r13b
0x18001ca35  mov     rax, [rsi]
0x18001ca38  mov     [rsp+298h+var_228], rax
0x18001ca3d  lock add [rax+8], r12d
0x18001ca42  mov     [rsp+298h+var_220], r13
0x18001ca47  lea     edx, [r13+8]; dwFlags
0x18001ca4b  lea     r8d, [r13+4]; dwBytes
0x18001ca4f  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18001ca56  call    cs:__imp_HeapAlloc
0x18001ca5c  test    rax, rax
0x18001ca5f  jnz     short loc_18001CADA
0x18001ca61  lea     r14, WPP_GLOBAL_Control
0x18001ca68  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca6f  cmp     rcx, r14
0x18001ca72  jz      short loc_18001CA91
0x18001ca74  test    byte ptr [rcx+1Ch], 4
0x18001ca78  jz      short loc_18001CA91
0x18001ca7a  lea     edx, [rax+0Ah]
0x18001ca7d  lea     r9d, [r13+4]
0x18001ca81  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18001ca88  mov     rcx, [rcx+10h]
0x18001ca8c  call    WPP_SF_d
0x18001ca91  xorps   xmm0, xmm0
0x18001ca94  movups  [rsp+298h+var_1C0], xmm0
0x18001ca9c  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001caa3  mov     [rsp+298h+pExceptionObject], rcx
0x18001caab  mov     [rsp+298h+var_1B0], 8007000Eh
0x18001cab6  mov     [rsp+298h+var_1AC], r13d
0x18001cabe  mov     [rsp+298h+var_1A8], r12d
0x18001cac6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001cacd  lea     rcx, [rsp+298h+pExceptionObject]; pExceptionObject
0x18001cad5  call    _CxxThrowException_0
0x18001cada  mov     [rax], r12d
0x18001cadd  mov     [rsp+298h+var_218], rax
0x18001cae5  mov     [rsp+298h+var_210], r13
0x18001caed  lock add cs:dword_180145058, r12d
0x18001caf5  mov     [rsp+298h+var_208], rbx
0x18001cafd  cmp     [rsp+298h+var_230], r13b
0x18001cb02  jnz     short loc_18001CB72
0x18001cb04  mov     rcx, [rsp+298h+var_228]
0x18001cb09  mov     rcx, [rcx]; hToken
0x18001cb0c  call    cs:__imp_ImpersonateLoggedOnUser
0x18001cb12  test    eax, eax
0x18001cb14  jnz     short loc_18001CB6D
0x18001cb16  call    cs:__imp_GetLastError
0x18001cb1c  test    eax, eax
0x18001cb1e  jle     short loc_18001CB28
0x18001cb20  movzx   eax, ax
0x18001cb23  or      eax, 80070000h
0x18001cb28  xorps   xmm0, xmm0
0x18001cb2b  movups  [rsp+298h+var_160], xmm0
0x18001cb33  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001cb3a  mov     [rsp+298h+var_168], rcx
0x18001cb42  mov     [rsp+298h+var_150], eax
0x18001cb49  mov     [rsp+298h+var_14C], r13d
0x18001cb51  mov     [rsp+298h+var_148], r12d
0x18001cb59  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001cb60  lea     rcx, [rsp+298h+var_168]; pExceptionObject
0x18001cb68  call    _CxxThrowException_0
0x18001cb6d  mov     [rsp+298h+var_230], r12b
0x18001cb72  mov     rdx, [rdi+10h]
0x18001cb76  add     rdx, 0Ch
0x18001cb7a  lea     rcx, [rsp+298h+var_250]
0x18001cb7f  call    ?BITSGetVolumePathName@@YA?AV?$GenericStringHandle@G@@PEBG@Z; BITSGetVolumePathName(ushort const *)
0x18001cb84  nop
0x18001cb85  mov     rcx, [rsp+298h+var_250]
0x18001cb8a  add     rcx, 0Ch; lpRootPathName
0x18001cb8e  call    cs:__imp_GetDriveTypeW
0x18001cb94  mov     r14d, eax
0x18001cb97  test    eax, 0FFFFFFFAh
0x18001cb9c  jnz     short loc_18001CBAB
0x18001cb9e  cmp     eax, 5
0x18001cba1  jz      short loc_18001CBAB
0x18001cba3  mov     r12d, r13d
0x18001cba6  jmp     loc_18001CC53
0x18001cbab  mov     rdx, [rsp+298h+var_250]
0x18001cbb0  add     rdx, 0Ch
0x18001cbb4  lea     rcx, [rsp+298h+var_248]
0x18001cbb9  call    ?BITSGetVolumeNameForVolumeMountPoint@@YA?AV?$GenericStringHandle@G@@PEBG@Z; BITSGetVolumeNameForVolumeMountPoint(ushort const *)
0x18001cbbe  mov     rdx, rax
0x18001cbc1  lea     rcx, [rsp+298h+var_240]
0x18001cbc6  call    ??4?$GenericStringHandle@G@@QEAAAEAV0@AEBV0@@Z; GenericStringHandle<ushort>::operator=(GenericStringHandle<ushort> const &)
0x18001cbcb  lea     rcx, [rsp+298h+var_248]
0x18001cbd0  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18001cbd5  lea     rcx, [rsp+298h+var_238]; this
0x18001cbda  call    ?Revert@CNestedImpersonation@@QEAAXXZ; CNestedImpersonation::Revert(void)
0x18001cbdf  mov     rbx, [rsp+298h+var_240]
0x18001cbe4  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001cbeb  add     rcx, 60h ; '`'; this
0x18001cbef  lea     rdx, [rbx+0Ch]; unsigned __int16 *
0x18001cbf3  call    ?IsVolumeLocked@CDeviceNotificationController@@QEAAJPEBG@Z; CDeviceNotificationController::IsVolumeLocked(ushort const *)
0x18001cbf8  test    eax, eax
0x18001cbfa  jns     short loc_18001CC47
0x18001cbfc  xorps   xmm0, xmm0
0x18001cbff  movups  [rsp+298h+var_100], xmm0
0x18001cc07  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001cc0e  mov     [rsp+298h+var_108], rcx
0x18001cc16  mov     [rsp+298h+var_F0], eax
0x18001cc1d  mov     [rsp+298h+var_EC], 7F9h
0x18001cc28  mov     [rsp+298h+var_E8], 1
0x18001cc33  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001cc3a  lea     rcx, [rsp+298h+var_108]; pExceptionObject
0x18001cc42  call    _CxxThrowException_0
0x18001cc47  lea     rcx, [rbx+0Ch]; lpRootPathName
0x18001cc4b  call    ?BITSGetVolumeSerialNumber@@YAKPEBG@Z; BITSGetVolumeSerialNumber(ushort const *)
0x18001cc50  mov     r12d, eax
0x18001cc53  mov     rdx, [rdi+110h]
0x18001cc5a  add     rdx, 0Ch
0x18001cc5e  mov     rcx, [rsp+298h+var_250]
0x18001cc63  add     rcx, 0Ch
0x18001cc67  call    cs:__imp__o__wcsicmp
0x18001cc6d  test    eax, eax
0x18001cc6f  jnz     short loc_18001CCD2
0x18001cc71  mov     rdx, [rdi+118h]
0x18001cc78  add     rdx, 0Ch
0x18001cc7c  lea     rcx, [rbx+0Ch]
0x18001cc80  call    cs:__imp__o__wcsicmp
0x18001cc86  test    eax, eax
0x18001cc88  jnz     short loc_18001CCD2
0x18001cc8a  cmp     [rdi+120h], r14d
0x18001cc91  jnz     short loc_18001CCD2
0x18001cc93  mov     eax, [rdi+124h]
0x18001cc99  test    eax, eax
0x18001cc9b  jz      short loc_18001CCA2
0x18001cc9d  cmp     eax, r12d
0x18001cca0  jnz     short loc_18001CCD2
0x18001cca2  lea     rcx, [rsp+298h+var_250]
0x18001cca7  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18001ccac  nop
0x18001ccad  lea     rcx, [rsp+298h+var_238]; this
0x18001ccb2  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x18001ccb7  nop
0x18001ccb8  lea     rcx, [rsp+298h+var_240]
0x18001ccbd  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18001ccc2  nop
0x18001ccc3  mov     rcx, rsi; this
0x18001ccc6  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001cccb  mov     al, 1
0x18001cccd  jmp     loc_18001CF10
0x18001ccd2  cmp     [rsp+298h+var_230], r13b
0x18001ccd7  jz      short loc_18001CCEE
0x18001ccd9  mov     rdx, [rsp+298h+var_238]
0x18001ccde  mov     rdx, [rdx]; Token
0x18001cce1  xor     ecx, ecx; Thread
0x18001cce3  call    cs:__imp_SetThreadToken
0x18001cce9  mov     [rsp+298h+var_230], r13b
0x18001ccee  mov     r8d, [rdi+124h]; unsigned int
0x18001ccf5  mov     [rsp+298h+var_258], r8d
0x18001ccfa  mov     r9, [rdi+118h]
0x18001cd01  add     r9, 0Ch
0x18001cd05  mov     [rsp+298h+var_248], r9
0x18001cd0a  mov     r12, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001cd11  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18001cd18  mov     edi, [rax+0D0h]
0x18001cd1e  mov     rdx, [rax+0C0h]
0x18001cd25  mov     [rsp+298h+var_1E8], rdx
0x18001cd2d  mov     rax, [rax+0C8h]
0x18001cd34  mov     [rsp+298h+var_1E0], rax
0x18001cd3c  mov     ecx, 80000000h; unsigned __int64
0x18001cd41  mov     [rsp+298h+var_1D8], rcx
0x18001cd49  mov     [rsp+298h+var_1D0], edi
0x18001cd50  test    rcx, rdx
0x18001cd53  jz      short loc_18001CDA0
0x18001cd55  lea     r14, WPP_GLOBAL_Control
0x18001cd5c  mov     r10, cs:WPP_GLOBAL_Control
0x18001cd63  cmp     r10, r14
0x18001cd66  jz      short loc_18001CD8C
0x18001cd68  test    byte ptr [r10+1Ch], 1
0x18001cd6d  jz      short loc_18001CD8C
0x18001cd6f  call    ?GetCallbackName@CallbackSleepHelper@@KAPEBD_K@Z; CallbackSleepHelper::GetCallbackName(unsigned __int64)
0x18001cd74  mov     r9, rax
0x18001cd77  mov     edx, 0Ah
0x18001cd7c  lea     r8, WPP_263cc8d6529f371e5fb175aafd999872_Traceguids
0x18001cd83  mov     rcx, [r10+10h]
0x18001cd87  call    WPP_SF_s
0x18001cd8c  mov     ecx, edi; dwMilliseconds
0x18001cd8e  call    cs:__imp_Sleep
0x18001cd94  mov     r9, [rsp+298h+var_248]
0x18001cd99  mov     r8d, [rsp+298h+var_258]
0x18001cd9e  jmp     short loc_18001CDA7
0x18001cda0  lea     r14, WPP_GLOBAL_Control
0x18001cda7  lea     r13, [r12+2B0h]
0x18001cdaf  mov     rdi, [r13+8]
0x18001cdb3  cmp     rdi, r13
0x18001cdb6  jnz     loc_18001CED3
0x18001cdbc  mov     rcx, r12; this
0x18001cdbf  call    ?ScheduleAnotherGroup@CJobManager@@QEAAXXZ; CJobManager::ScheduleAnotherGroup(void)
0x18001cdc4  nop
0x18001cdc5  lea     rcx, [rsp+298h+var_1E8]; this
0x18001cdcd  call    ??1CallbackSleepHelper@@QEAA@XZ; CallbackSleepHelper::~CallbackSleepHelper(void)
0x18001cdd2  mov     dword ptr [r15+0Ch], 4
0x18001cdda  mov     edx, 1
0x18001cddf  mov     [r15+8], edx
0x18001cde3  mov     r8d, 8020000Eh
0x18001cde9  mov     [r15+4], r8d
0x18001cded  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdf4  cmp     rcx, r14
0x18001cdf7  jz      short loc_18001CE31
0x18001cdf9  test    [rcx+1Ch], dl
0x18001cdfc  jz      short loc_18001CE31
0x18001cdfe  lea     rax, qword_18011AC70
0x18001ce05  cmp     qword ptr [r15+10h], 0
0x18001ce0a  cmovnz  rax, [r15+10h]
0x18001ce0f  mov     [rsp+298h+var_260], rax
0x18001ce14  mov     [rsp+298h+var_268], 4
0x18001ce1c  mov     [rsp+298h+var_270], r8d
0x18001ce21  mov     [rsp+298h+var_278], edx
0x18001ce25  mov     r9d, [r15]
0x18001ce28  mov     rcx, [rcx+10h]
0x18001ce2c  call    WPP_SF_llDDS
0x18001ce31  mov     dword ptr [r15], 4
0x18001ce38  mov     rax, [rsp+298h+var_250]
0x18001ce3d  or      edi, 0FFFFFFFFh
0x18001ce40  test    rax, rax
0x18001ce43  jz      short loc_18001CE66
0x18001ce45  mov     ecx, edi
0x18001ce47  lock xadd [rax+8], ecx
0x18001ce4c  add     ecx, edi
0x18001ce4e  jnz     short loc_18001CE5D
0x18001ce50  lea     edx, [rdi+11h]; unsigned __int64
0x18001ce53  mov     rcx, [rsp+298h+var_250]; void *
0x18001ce58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ce5d  mov     [rsp+298h+var_250], 0
0x18001ce66  lea     rcx, [rsp+298h+var_238]; this
0x18001ce6b  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x18001ce70  nop
0x18001ce71  test    rbx, rbx
0x18001ce74  jz      short loc_18001CE8D
0x18001ce76  mov     eax, edi
0x18001ce78  lock xadd [rbx+8], eax
0x18001ce7d  add     eax, edi
0x18001ce7f  jnz     short loc_18001CE8D
0x18001ce81  lea     edx, [rax+10h]; unsigned __int64
0x18001ce84  mov     rcx, rbx; void *
0x18001ce87  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ce8c  nop
0x18001ce8d  mov     rcx, [rsi]
0x18001ce90  mov     eax, edi
0x18001ce92  lock xadd [rcx+8], eax
0x18001ce97  add     eax, edi
0x18001ce99  jnz     short loc_18001CECF
0x18001ce9b  mov     rax, [rsi]
0x18001ce9e  mov     rcx, [rax]; hObject
0x18001cea1  lea     rax, [rcx-1]
0x18001cea5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001cea9  ja      short loc_18001CEBB
0x18001ceab  call    cs:__imp_CloseHandle
0x18001ceb1  mov     rax, [rsi]
0x18001ceb4  mov     qword ptr [rax], 0
0x18001cebb  mov     edx, 10h; unsigned __int64
0x18001cec0  mov     rcx, [rsi]; void *
0x18001cec3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cec8  mov     qword ptr [rsi], 0
0x18001cecf  xor     al, al
0x18001ced1  jmp     short loc_18001CF10
0x18001ced3  mov     rax, rdi
0x18001ced6  lea     rdx, [rdi-270h]
0x18001cedd  neg     rax
0x18001cee0  sbb     rcx, rcx
0x18001cee3  and     rcx, rdx; this
0x18001cee6  mov     rdx, r9; unsigned __int16 *
0x18001cee9  call    ?OnDiskChange@CJob@@QEAAXPEBGK@Z; CJob::OnDiskChange(ushort const *,ulong)
0x18001ceee  mov     rdi, [rdi+8]
0x18001cef2  mov     r9, [rsp+298h+var_248]
0x18001cef7  mov     r8d, [rsp+298h+var_258]
0x18001cefc  jmp     loc_18001CDB3
0x18001cf01  mov     rcx, [rsp+298h+var_1F0]; this
0x18001cf09  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001cf0e  xor     al, al
0x18001cf10  mov     rcx, [rsp+298h+var_48]
0x18001cf18  xor     rcx, rsp; StackCookie
0x18001cf1b  call    __security_check_cookie
0x18001cf20  add     rsp, 260h
0x18001cf27  pop     r15
0x18001cf29  pop     r14
  ... truncated ...
```
