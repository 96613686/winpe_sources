# TaskScheduler::AddItemToWorkGroup(SidHandle,TaskSchedulerWorkItem *)

- ea: `0x18002da90`
- end: `0x18002e5b3`
- name: `?AddItemToWorkGroup@TaskScheduler@@AEAAXVSidHandle@@PEAVTaskSchedulerWorkItem@@@Z`
- size: `2851`
- prototype: `void __fastcall(_QWORD *, PSID *, unsigned __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d040`
- `0x180046c6c`

## callees

- `0x180006640`
- `0x18002da90`
- `0x18002e5c0`
- `0x1800634e0`
- `0x1800845ec`
- `0x180088f98`
- `0x18009a9d0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a3de8`
- `0x1800a7558`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc63`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002e29d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002e29d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18002e386`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18002e386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ddea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ddea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2c0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e2ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e3cd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e2ea`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e3cd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e255`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e255`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002e370`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002e370`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18002e1f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18002e1f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3bb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db6c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db7c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db9f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df62`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df72`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df87`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df97`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db6c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db7c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002db9f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df62`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df72`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df87`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002df97`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db1f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db2b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db3b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db47`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db5a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df02`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df0e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df24`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df30`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df4a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db1f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db2b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db3b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db47`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002db5a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df02`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df0e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df24`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df30`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002df4a`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18002dddb`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18002dddb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e032`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e032`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall TaskScheduler::AddItemToWorkGroup(_QWORD *a1, PSID *a2, unsigned __int64 a3)
{
  PSID *v3; // r15
  _QWORD *v4; // rsi
  _QWORD *v5; // r14
  __int64 *v6; // r13
  __int64 *v7; // rbx
  PSID v8; // rsi
  PSID v9; // r14
  PUCHAR SidSubAuthorityCount; // rdi
  PUCHAR v11; // rax
  PUCHAR v12; // rdi
  PUCHAR v13; // rax
  UCHAR i; // r12
  PDWORD SidSubAuthority; // rdi
  PDWORD v16; // rax
  PDWORD v17; // rdi
  PDWORD v18; // rax
  _QWORD *v19; // rdi
  EVENT_LOG *v20; // rcx
  _QWORD *v21; // rax
  unsigned __int64 v22; // rdx
  volatile signed __int32 *v23; // rax
  unsigned __int64 v24; // r13
  SIZE_T v25; // rax
  SIZE_T v26; // rax
  HANDLE SemaphoreW; // rax
  signed int LastError; // eax
  unsigned int v29; // ecx
  PSID v30; // rax
  volatile signed __int32 *v31; // r13
  _BYTE *v32; // rcx
  _BYTE *v33; // r14
  PSID v34; // r13
  PUCHAR v35; // rbx
  PUCHAR v36; // rbx
  UCHAR j; // bl
  PDWORD v38; // rbx
  PDWORD v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rbx
  void *v42; // r14
  unsigned __int64 v43; // r14
  _QWORD *v44; // r8
  _QWORD *k; // rax
  _QWORD *v46; // r10
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // r9
  bool v49; // cf
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // r9
  unsigned __int64 v52; // r9
  unsigned __int64 v53; // rax
  HANDLE *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  HANDLE *v58; // r14
  DWORD *lpThreadId; // r13
  HANDLE Thread; // r9
  DWORD v61; // eax
  DWORD v62; // eax
  EVENT_LOG *v63; // rcx
  unsigned int v64; // edx
  UCHAR v65; // [rsp+30h] [rbp-348h]
  DWORD nSubAuthority; // [rsp+34h] [rbp-344h] BYREF
  PSID pSid; // [rsp+38h] [rbp-340h]
  LPVOID lpParameter; // [rsp+40h] [rbp-338h]
  void *v69; // [rsp+48h] [rbp-330h] BYREF
  void *v70; // [rsp+50h] [rbp-328h]
  unsigned __int64 v71; // [rsp+58h] [rbp-320h]
  _BYTE *v72; // [rsp+60h] [rbp-318h]
  TaskScheduler::TaskSchedulerWorkGroup *v73; // [rsp+68h] [rbp-310h]
  _QWORD *v74; // [rsp+70h] [rbp-308h]
  void **v75; // [rsp+78h] [rbp-300h]
  HANDLE Handles; // [rsp+80h] [rbp-2F8h] BYREF
  unsigned __int64 v77; // [rsp+88h] [rbp-2F0h]
  _BYTE *v78; // [rsp+90h] [rbp-2E8h]
  _QWORD *v79; // [rsp+98h] [rbp-2E0h]
  PSID *v80; // [rsp+A0h] [rbp-2D8h]
  _QWORD *v81; // [rsp+A8h] [rbp-2D0h]
  void *v82; // [rsp+B0h] [rbp-2C8h] BYREF
  volatile signed __int32 *v83; // [rsp+B8h] [rbp-2C0h]
  _QWORD *v84; // [rsp+C0h] [rbp-2B8h]
  _QWORD *v85; // [rsp+C8h] [rbp-2B0h]
  unsigned __int64 v86; // [rsp+D0h] [rbp-2A8h]
  _BYTE v87[24]; // [rsp+D8h] [rbp-2A0h] BYREF
  void **pExceptionObject; // [rsp+F0h] [rbp-288h] BYREF
  __int128 v89; // [rsp+F8h] [rbp-280h]
  int v90; // [rsp+108h] [rbp-270h]
  int v91; // [rsp+10Ch] [rbp-26Ch]
  int v92; // [rsp+110h] [rbp-268h]
  void **v93; // [rsp+150h] [rbp-228h] BYREF
  __int128 v94; // [rsp+158h] [rbp-220h]
  unsigned int v95; // [rsp+168h] [rbp-210h]
  int v96; // [rsp+16Ch] [rbp-20Ch]
  int v97; // [rsp+170h] [rbp-208h]
  void **v98; // [rsp+1B0h] [rbp-1C8h] BYREF
  __int128 v99; // [rsp+1B8h] [rbp-1C0h]
  int v100; // [rsp+1C8h] [rbp-1B0h]
  int v101; // [rsp+1CCh] [rbp-1ACh]
  int v102; // [rsp+1D0h] [rbp-1A8h]
  void **v103; // [rsp+210h] [rbp-168h] BYREF
  __int128 v104; // [rsp+218h] [rbp-160h]
  int v105; // [rsp+228h] [rbp-150h]
  int v106; // [rsp+22Ch] [rbp-14Ch]
  int v107; // [rsp+230h] [rbp-148h]
  void **v108; // [rsp+270h] [rbp-108h] BYREF
  __int128 v109; // [rsp+278h] [rbp-100h]
  int v110; // [rsp+288h] [rbp-F0h]
  int v111; // [rsp+28Ch] [rbp-ECh]
  int v112; // [rsp+290h] [rbp-E8h]
  void **v113; // [rsp+2D0h] [rbp-A8h] BYREF
  _DWORD v114[22]; // [rsp+2D8h] [rbp-A0h] BYREF

  v71 = a3;
  v3 = a2;
  v4 = a1;
  lpParameter = a1;
  v79 = a1;
  v80 = a2;
  v86 = a3;
  v5 = a1 + 13;
  v74 = a1 + 13;
  v6 = (__int64 *)a1[13];
  v7 = (__int64 *)v6[1];
  HIDWORD(v83) = 0;
  if ( !*((_BYTE *)v7 + 25) )
  {
    while ( 1 )
    {
      v8 = (PSID)v7[4];
      v9 = *v3;
      if ( v8 && v9 )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*v3);
        v11 = GetSidSubAuthorityCount(v8);
        a1 = (_QWORD *)*SidSubAuthorityCount;
        if ( *v11 >= (unsigned __int8)a1 )
        {
          v12 = GetSidSubAuthorityCount(v9);
          v13 = GetSidSubAuthorityCount(v8);
          a1 = (_QWORD *)*v12;
          if ( *v13 <= (unsigned __int8)a1 )
          {
            for ( i = 0; i < *GetSidSubAuthorityCount(v8); ++i )
            {
              SidSubAuthority = GetSidSubAuthority(v9, i);
              v16 = GetSidSubAuthority(v8, i);
              a1 = (_QWORD *)*SidSubAuthority;
              if ( *v16 < (unsigned int)a1 )
                goto LABEL_12;
              v17 = GetSidSubAuthority(v9, i);
              v18 = GetSidSubAuthority(v8, i);
              a1 = (_QWORD *)*v17;
              if ( *v18 > (unsigned int)a1 )
                break;
            }
          }
LABEL_13:
          v6 = v7;
          goto LABEL_14;
        }
      }
      else if ( (__int64)v8 >= (__int64)v9 )
      {
        goto LABEL_13;
      }
LABEL_12:
      v7 += 2;
LABEL_14:
      v7 = (__int64 *)*v7;
      if ( *((_BYTE *)v7 + 25) )
      {
        v5 = v74;
        v4 = lpParameter;
        break;
      }
    }
  }
  if ( *((_BYTE *)v6 + 25) || (unsigned __int8)CSidSorter::operator()(a1, v3, v6 + 4) || (__int64 *)*v5 == v6 )
  {
    v85 = v5;
    v73 = 0;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    while ( 2 )
    {
      v21 = HeapAlloc(hBitsHeap, 8u, 0x88u);
      try
      {
        v19 = v21;
        if ( !v21 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 136);
          v89 = 0;
          pExceptionObject = &ComError::`vftable';
          v90 = -2147024882;
          v91 = 0;
          v92 = 1;
          throw (ComError *)&pExceptionObject;
        }
        v81 = v21;
        v22 = *((unsigned int *)v4 + 30);
        v69 = *v3;
        v70 = v3[1];
        _InterlockedIncrement((volatile signed __int32 *)v70);
        v75 = &v69;
        *v21 = v69;
        v23 = (volatile signed __int32 *)v70;
        v19[1] = v70;
        _InterlockedIncrement(v23);
        v19[2] = v19 + 2;
        v19[3] = v19 + 2;
        v19[5] = 0;
        v19[4] = v19 + 2;
        v19[7] = v19 + 7;
        v19[8] = v19 + 7;
        v19[10] = 0;
        v19[9] = v19 + 7;
        v19[12] = 0;
        *((_DWORD *)v19 + 26) = 0;
        *(_QWORD *)((char *)v19 + 108) = (unsigned int)v22;
        if ( (unsigned int)v22 > 0x3FFFFFFF )
        {
          v109 = 0;
          v108 = &ComError::`vftable';
          v110 = -2147023537;
          v111 = 796;
          v112 = 1;
          throw (ComError *)&v108;
        }
        v24 = (unsigned int)v22;
        v25 = 8 * v22;
        if ( !is_mul_ok(v22, 8u) )
          v25 = -1;
        v19[15] = operator new(v25);
        v26 = 4 * v24;
        if ( !is_mul_ok(v24, 4u) )
          v26 = -1;
        v19[16] = operator new(v26);
        memset_0((void *)v19[15], 0, 8 * v24);
        memset_0((void *)v19[16], 0, 4 * v24);
        SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
        v19[12] = SemaphoreW;
        if ( !SemaphoreW )
        {
          LastError = GetLastError();
          v29 = LastError;
          if ( LastError > 0 )
            v29 = (unsigned __int16)LastError | 0x80070000;
          v94 = 0;
          v93 = &ComError::`vftable';
          v95 = v29;
          v96 = 0;
          v97 = 1;
          throw (ComError *)&v93;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v70, 0xFFFFFFFF) == 1 )
        {
          operator delete(v70, 4u);
          operator delete(v69, 0);
          v70 = 0;
          v69 = 0;
        }
        v73 = (TaskScheduler::TaskSchedulerWorkGroup *)v19;
        v30 = *v3;
        pSid = v30;
        v82 = v30;
        v31 = (volatile signed __int32 *)v3[1];
        v75 = (void **)v31;
        v83 = v31;
        _InterlockedIncrement(v31);
        v84 = v19;
        v32 = (_BYTE *)*v5;
        v72 = v32;
        v78 = (_BYTE *)*((_QWORD *)v32 + 1);
        nSubAuthority = 0;
        v81 = 0;
        v33 = v78;
        if ( !v78[25] )
        {
          while ( 1 )
          {
            v78 = v33;
            v34 = (PSID)*((_QWORD *)v33 + 4);
            if ( v34 && v30 )
            {
              v35 = GetSidSubAuthorityCount(v30);
              if ( *GetSidSubAuthorityCount(v34) >= *v35 )
              {
                v36 = GetSidSubAuthorityCount(pSid);
                if ( *GetSidSubAuthorityCount(v34) <= *v36 )
                {
                  for ( j = 0; ; j = v65 + 1 )
                  {
                    v65 = j;
                    if ( j >= *GetSidSubAuthorityCount(v34) )
                      break;
                    nSubAuthority = j;
                    v38 = GetSidSubAuthority(pSid, j);
                    if ( *GetSidSubAuthority(v34, nSubAuthority) < *v38 )
                      goto LABEL_52;
                    v39 = GetSidSubAuthority(pSid, nSubAuthority);
                    if ( *GetSidSubAuthority(v34, nSubAuthority) > *v39 )
                      break;
                  }
                }
                v30 = pSid;
LABEL_55:
                nSubAuthority = 1;
                v32 = v33;
                v72 = v33;
                goto LABEL_56;
              }
LABEL_52:
              v32 = v72;
              v30 = pSid;
            }
            else if ( (__int64)v34 >= (__int64)v30 )
            {
              goto LABEL_55;
            }
            nSubAuthority = 0;
            v33 += 16;
LABEL_56:
            v33 = *(_BYTE **)v33;
            if ( v33[25] )
            {
              v31 = (volatile signed __int32 *)v75;
              break;
            }
          }
        }
        if ( v32[25] || (unsigned __int8)CSidSorter::operator()(v32, &v82, v32 + 32) )
        {
          if ( v74[1] == 0x492492492492492LL )
            std::_Xlength_error("map/set too long");
          v40 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SidHandle const,TaskScheduler::TaskSchedulerWorkGroup *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SidHandle const,TaskScheduler::TaskSchedulerWorkGroup *>,void *>>>(
                  v87,
                  v74,
                  *v74,
                  &v82);
          v41 = *(_QWORD *)(v40 + 8);
          *(_QWORD *)(v40 + 8) = 0;
          std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SidHandle const,unsigned long>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<SidHandle const,unsigned long>,void *>>>(v87);
          Handles = v78;
          v77 = __PAIR64__((unsigned int)v81, nSubAuthority);
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
            v85,
            &Handles,
            v41);
          v31 = v83;
          v42 = v82;
        }
        else
        {
          v42 = pSid;
        }
        if ( _InterlockedExchangeAdd(v31, 0xFFFFFFFF) == 1 )
        {
          operator delete((void *)v31, 4u);
          operator delete(v42, 0);
        }
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v19);
          v20 = WPP_GLOBAL_Control;
        }
      }
      catch ( ComError v113 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v114[4]);
        std::_Tree<std::_Tmap_traits<SidHandle,TaskScheduler::TaskSchedulerWorkGroup *,CSidSorter,std::allocator<std::pair<SidHandle const,TaskScheduler::TaskSchedulerWorkGroup *>>,0>>::erase(
          v79 + 13,
          v80);
        if ( v73 )
          TaskScheduler::TaskSchedulerWorkGroup::`scalar deleting destructor'(v73, v64);
        v73 = 0;
        Sleep(0x1388u);
        v113 = &std::bad_alloc::`vftable';
        o___std_exception_destroy_0(v114);
        v4 = v79;
        lpParameter = v79;
        v3 = v80;
        v71 = v86;
        v5 = v74;
        continue;
      }
      goto LABEL_69;
    }
  }
  v19 = (_QWORD *)v6[6];
  v20 = WPP_GLOBAL_Control;
LABEL_69:
  v43 = v71;
  if ( v20 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
    WPP_SF_qq(*((_QWORD *)v20 + 2), 42, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v71, v19);
  v44 = v19 + 2;
  for ( k = (_QWORD *)v19[3]; k != v44; k = (_QWORD *)k[1] )
  {
    v46 = k - 1;
    if ( !k )
      v46 = 0;
    v47 = v46[5];
    v48 = *(_QWORD *)(v43 + 40);
    v49 = v47 < v48;
    if ( v47 == v48 && (v50 = v46[4], v51 = *(_QWORD *)(v43 + 32), v49 = v50 < v51, v50 == v51) )
    {
      if ( (unsigned __int64)v46 >= v43 )
        break;
    }
    else if ( !v49 )
    {
      break;
    }
  }
  *(_QWORD *)(v43 + 16) = k;
  *(_QWORD *)(v43 + 8) = *k;
  *(_QWORD *)(v43 + 24) = k[2];
  *k = v43 + 8;
  *(_QWORD *)(*(_QWORD *)(v43 + 8) + 8LL) = v43 + 8;
  ++v19[5];
  *(_QWORD *)(v43 + 88) = v44;
  *(_DWORD *)(v43 + 80) = 1;
  *(_QWORD *)(v43 + 72) = v19;
  ReleaseSemaphore((HANDLE)v19[12], 1, 0);
  v52 = v19[5] + *((int *)v19 + 28);
  v53 = *((unsigned int *)v19 + 26);
  if ( v52 > v53 && (unsigned int)v53 < *((_DWORD *)v19 + 27) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids,
        v52,
        *((_DWORD *)v19 + 26));
    while ( 1 )
    {
      while ( 1 )
      {
        v54 = (HANDLE *)lpParameter;
        *((_QWORD *)lpParameter + 17) = v19;
        ResetEvent(v54[16]);
        v55 = v19[15];
        if ( !v55 )
        {
          v104 = 0;
          v103 = &ComError::`vftable';
          v105 = -2147023537;
          v106 = 53;
          v107 = 1;
          throw (ComError *)&v103;
        }
        v56 = v19[16];
        if ( !v56 )
        {
          v99 = 0;
          v98 = &ComError::`vftable';
          v100 = -2147023537;
          v101 = 53;
          v102 = 1;
          throw (ComError *)&v98;
        }
        v57 = *((unsigned int *)v19 + 26);
        v58 = (HANDLE *)(v55 + 8 * v57);
        lpThreadId = (DWORD *)(v56 + 4 * v57);
        Thread = CreateThread(0, 0, TaskScheduler::WorkGroupWorkerThunk, lpParameter, 0, lpThreadId);
        *v58 = Thread;
        if ( Thread )
          break;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v61 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v61);
        }
        Sleep(0x1388u);
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids,
          Thread,
          *lpThreadId);
      Handles = *v58;
      v77 = *((_QWORD *)lpParameter + 16);
      v62 = WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
      nSubAuthority = v62;
      if ( v62 )
        break;
      GetExitCodeThread(*v58, &nSubAuthority);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids,
          nSubAuthority);
      CloseHandle(*v58);
      *v58 = 0;
      *lpThreadId = 0;
      Sleep(0x1388u);
    }
    if ( v62 != 1 )
    {
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control )
      {
LABEL_109:
        *((_QWORD *)lpParameter + 17) = 0;
        ++*((_DWORD *)v19 + 26);
        goto LABEL_110;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_106:
        if ( v63 != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)v63 + 28) < 0 )
          WPP_SF_(*((_QWORD *)v63 + 2), 48, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
        goto LABEL_109;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v62);
    }
    v63 = WPP_GLOBAL_Control;
    goto LABEL_106;
  }
LABEL_110:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3[1], 0xFFFFFFFF) == 1 )
  {
    operator delete(v3[1], 4u);
    operator delete(*v3, 0);
    v3[1] = 0;
    *v3 = 0;
  }
}

```

## disassembly

```asm
0x18002da90  mov     [rsp+arg_8], rdx
0x18002da95  push    rbx
0x18002da96  push    rsi
0x18002da97  push    rdi
0x18002da98  push    r12
0x18002da9a  push    r13
0x18002da9c  push    r14
0x18002da9e  push    r15
0x18002daa0  sub     rsp, 340h
0x18002daa7  mov     rax, cs:__security_cookie
0x18002daae  xor     rax, rsp
0x18002dab1  mov     [rsp+378h+var_48], rax
0x18002dab9  mov     [rsp+378h+var_320], r8
0x18002dabe  mov     r15, rdx
0x18002dac1  mov     rsi, rcx
0x18002dac4  mov     [rsp+378h+lpParameter], rcx
0x18002dac9  mov     [rsp+378h+var_2E0], rcx
0x18002dad1  mov     [rsp+378h+var_2D8], rdx
0x18002dad9  mov     [rsp+378h+var_2A8], r8
0x18002dae1  lea     r14, [rcx+68h]
0x18002dae5  mov     [rsp+378h+var_308], r14
0x18002daea  mov     r13, [r14]
0x18002daed  mov     rbx, [r13+8]
0x18002daf1  xor     eax, eax
0x18002daf3  mov     [rsp+378h+var_2BC], eax
0x18002dafa  cmp     [rbx+19h], al
0x18002dafd  jnz     loc_18002DBD5
0x18002db03  mov     rsi, [rbx+20h]
0x18002db07  mov     r14, [r15]
0x18002db0a  test    rsi, rsi
0x18002db0d  jz      loc_18002DBB0
0x18002db13  test    r14, r14
0x18002db16  jz      loc_18002DBB0
0x18002db1c  mov     rcx, r14; pSid
0x18002db1f  call    cs:__imp_GetSidSubAuthorityCount
0x18002db25  mov     rdi, rax
0x18002db28  mov     rcx, rsi; pSid
0x18002db2b  call    cs:__imp_GetSidSubAuthorityCount
0x18002db31  movzx   ecx, byte ptr [rdi]
0x18002db34  cmp     [rax], cl
0x18002db36  jb      short loc_18002DBB5
0x18002db38  mov     rcx, r14; pSid
0x18002db3b  call    cs:__imp_GetSidSubAuthorityCount
0x18002db41  mov     rdi, rax
0x18002db44  mov     rcx, rsi; pSid
0x18002db47  call    cs:__imp_GetSidSubAuthorityCount
0x18002db4d  movzx   ecx, byte ptr [rdi]
0x18002db50  cmp     [rax], cl
0x18002db52  ja      short loc_18002DBBB
0x18002db54  xor     r12b, r12b
0x18002db57  mov     rcx, rsi; pSid
0x18002db5a  call    cs:__imp_GetSidSubAuthorityCount
0x18002db60  cmp     r12b, [rax]
0x18002db63  jnb     short loc_18002DBBB
0x18002db65  movzx   edx, r12b; nSubAuthority
0x18002db69  mov     rcx, r14; pSid
0x18002db6c  call    cs:__imp_GetSidSubAuthority
0x18002db72  mov     rdi, rax
0x18002db75  movzx   edx, r12b; nSubAuthority
0x18002db79  mov     rcx, rsi; pSid
0x18002db7c  call    cs:__imp_GetSidSubAuthority
0x18002db82  mov     ecx, [rdi]
0x18002db84  cmp     [rax], ecx
0x18002db86  jb      short loc_18002DBB5
0x18002db88  movzx   edx, r12b; nSubAuthority
0x18002db8c  mov     rcx, r14; pSid
0x18002db8f  call    cs:__imp_GetSidSubAuthority
0x18002db95  mov     rdi, rax
0x18002db98  movzx   edx, r12b; nSubAuthority
0x18002db9c  mov     rcx, rsi; pSid
0x18002db9f  call    cs:__imp_GetSidSubAuthority
0x18002dba5  mov     ecx, [rdi]
0x18002dba7  cmp     [rax], ecx
0x18002dba9  ja      short loc_18002DBBB
0x18002dbab  inc     r12b
0x18002dbae  jmp     short loc_18002DB57
0x18002dbb0  cmp     rsi, r14
0x18002dbb3  jge     short loc_18002DBBB
0x18002dbb5  add     rbx, 10h
0x18002dbb9  jmp     short loc_18002DBBE
0x18002dbbb  mov     r13, rbx
0x18002dbbe  mov     rbx, [rbx]
0x18002dbc1  cmp     byte ptr [rbx+19h], 0
0x18002dbc5  jz      loc_18002DB03
0x18002dbcb  mov     r14, [rsp+378h+var_308]
0x18002dbd0  mov     rsi, [rsp+378h+lpParameter]
0x18002dbd5  cmp     byte ptr [r13+19h], 0
0x18002dbda  jnz     short loc_18002DC12
0x18002dbdc  lea     r8, [r13+20h]
0x18002dbe0  mov     rdx, r15
0x18002dbe3  call    ??RCSidSorter@@QEBA_NAEBVSidHandle@@0@Z; CSidSorter::operator()(SidHandle const &,SidHandle const &)
0x18002dbe8  test    al, al
0x18002dbea  jnz     short loc_18002DC12
0x18002dbec  cmp     [r14], r13
0x18002dbef  jz      short loc_18002DC12
0x18002dbf1  mov     rdi, [r13+30h]
0x18002dbf5  xor     r12d, r12d
0x18002dbf8  lea     rbx, WPP_GLOBAL_Control
0x18002dbff  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002dc06  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc0d  jmp     loc_18002E11A
0x18002dc12  mov     [rsp+378h+var_2B0], r14
0x18002dc1a  xor     r12d, r12d
0x18002dc1d  mov     [rsp+378h+var_310], r12
0x18002dc22  lea     rbx, WPP_GLOBAL_Control
0x18002dc29  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc30  cmp     rcx, rbx
0x18002dc33  jz      short loc_18002DC51
0x18002dc35  test    byte ptr [rcx+1Ch], 80h
0x18002dc39  jz      short loc_18002DC51
0x18002dc3b  mov     edx, 27h ; '''
0x18002dc40  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18002dc47  mov     rcx, [rcx+10h]
0x18002dc4b  call    WPP_SF_
0x18002dc50  nop
0x18002dc51  mov     edx, 8; dwFlags
0x18002dc56  mov     r8d, 88h; dwBytes
0x18002dc5c  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18002dc63  call    cs:__imp_HeapAlloc
0x18002dc69  mov     rdi, rax
0x18002dc6c  test    rax, rax
0x18002dc6f  jnz     short loc_18002DCEA
0x18002dc71  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc78  cmp     rcx, rbx
0x18002dc7b  jz      short loc_18002DC9E
0x18002dc7d  test    byte ptr [rcx+1Ch], 4
0x18002dc81  jz      short loc_18002DC9E
0x18002dc83  mov     edx, 0Ah
0x18002dc88  mov     r9d, 88h
0x18002dc8e  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18002dc95  mov     rcx, [rcx+10h]
0x18002dc99  call    WPP_SF_d
0x18002dc9e  xorps   xmm0, xmm0
0x18002dca1  movups  [rsp+378h+var_280], xmm0
0x18002dca9  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18002dcb0  mov     [rsp+378h+pExceptionObject], rax
0x18002dcb8  mov     [rsp+378h+var_270], 8007000Eh
0x18002dcc3  mov     [rsp+378h+var_26C], r12d
0x18002dccb  mov     [rsp+378h+var_268], 1
0x18002dcd6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002dcdd  lea     rcx, [rsp+378h+pExceptionObject]; pExceptionObject
0x18002dce5  call    _CxxThrowException_0
0x18002dcea  mov     [rsp+378h+var_2D0], rdi
0x18002dcf2  mov     edx, [rsi+78h]
0x18002dcf5  mov     rax, [r15]
0x18002dcf8  mov     [rsp+378h+var_330], rax
0x18002dcfd  mov     rax, [r15+8]
0x18002dd01  mov     [rsp+378h+var_328], rax
0x18002dd06  lock inc dword ptr [rax]
0x18002dd09  lea     rax, [rsp+378h+var_330]
0x18002dd0e  mov     [rsp+378h+var_300], rax
0x18002dd13  mov     rax, [rsp+378h+var_330]
0x18002dd18  mov     [rdi], rax
0x18002dd1b  mov     rax, [rsp+378h+var_328]
0x18002dd20  mov     [rdi+8], rax
0x18002dd24  lock inc dword ptr [rax]
0x18002dd27  lea     rax, [rdi+10h]
0x18002dd2b  mov     [rax], rax
0x18002dd2e  mov     [rdi+18h], rax
0x18002dd32  mov     [rdi+28h], r12
0x18002dd36  mov     [rdi+20h], rax
0x18002dd3a  lea     rcx, [rdi+38h]
0x18002dd3e  mov     [rcx], rcx
0x18002dd41  mov     [rdi+40h], rcx
0x18002dd45  mov     [rdi+50h], r12
0x18002dd49  mov     [rdi+48h], rcx
0x18002dd4d  mov     [rdi+60h], r12
0x18002dd51  mov     [rdi+68h], r12d
0x18002dd55  mov     [rdi+6Ch], edx
0x18002dd58  mov     [rdi+70h], r12d
0x18002dd5c  cmp     edx, 3FFFFFFFh
0x18002dd62  ja      loc_18002E52C
0x18002dd68  mov     r13d, edx
0x18002dd6b  mov     eax, 8
0x18002dd70  mul     rdx
0x18002dd73  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002dd7a  cmovb   rax, rsi
0x18002dd7e  mov     rcx, rax; dwBytes
0x18002dd81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dd86  mov     [rdi+78h], rax
0x18002dd8a  mov     eax, 4
0x18002dd8f  mul     r13
0x18002dd92  cmovb   rax, rsi
0x18002dd96  mov     rcx, rax; dwBytes
0x18002dd99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dd9e  mov     [rdi+80h], rax
0x18002dda5  lea     r8, ds:0[r13*8]; Size
0x18002ddad  xor     edx, edx; Val
0x18002ddaf  mov     rcx, [rdi+78h]; void *
0x18002ddb3  call    memset_0
0x18002ddb8  lea     r8, ds:0[r13*4]; Size
0x18002ddc0  xor     edx, edx; Val
0x18002ddc2  mov     rcx, [rdi+80h]; void *
0x18002ddc9  call    memset_0
0x18002ddce  xor     r9d, r9d; lpName
0x18002ddd1  xor     edx, edx; lInitialCount
0x18002ddd3  xor     ecx, ecx; lpSemaphoreAttributes
0x18002ddd5  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002dddb  call    cs:__imp_CreateSemaphoreW
0x18002dde1  mov     [rdi+60h], rax
0x18002dde5  test    rax, rax
0x18002dde8  jnz     short loc_18002DE48
0x18002ddea  call    cs:__imp_GetLastError
0x18002ddf0  mov     ecx, eax
0x18002ddf2  test    eax, eax
0x18002ddf4  jle     short loc_18002DDFF
0x18002ddf6  movzx   ecx, ax
0x18002ddf9  or      ecx, 80070000h
0x18002ddff  xorps   xmm0, xmm0
0x18002de02  movups  [rsp+378h+var_220], xmm0
0x18002de0a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18002de11  mov     [rsp+378h+var_228], rax
0x18002de19  mov     [rsp+378h+var_210], ecx
0x18002de20  mov     [rsp+378h+var_20C], r12d
0x18002de28  mov     [rsp+378h+var_208], 1
0x18002de33  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002de3a  lea     rcx, [rsp+378h+var_228]; pExceptionObject
0x18002de42  call    _CxxThrowException_0
0x18002de48  mov     rax, [rsp+378h+var_328]
0x18002de4d  mov     ecx, esi
0x18002de4f  lock xadd [rax], ecx
0x18002de53  cmp     ecx, 1
0x18002de56  jnz     short loc_18002DE7D
0x18002de58  mov     edx, 4; unsigned __int64
0x18002de5d  mov     rcx, [rsp+378h+var_328]; void *
0x18002de62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002de67  xor     edx, edx; unsigned __int64
0x18002de69  mov     rcx, [rsp+378h+var_330]; void *
0x18002de6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002de73  mov     [rsp+378h+var_328], r12
0x18002de78  mov     [rsp+378h+var_330], r12
0x18002de7d  mov     [rsp+378h+var_310], rdi
0x18002de82  mov     rax, [r15]
0x18002de85  mov     [rsp+378h+pSid], rax
0x18002de8a  mov     [rsp+378h+var_2C8], rax
0x18002de92  mov     r13, [r15+8]
0x18002de96  mov     [rsp+378h+var_300], r13
0x18002de9b  mov     [rsp+0B8h], r13
0x18002dea3  lock inc dword ptr [r13+0]
0x18002dea8  mov     [rsp+378h+var_2B8], rdi
0x18002deb0  mov     rcx, [r14]
0x18002deb3  mov     [rsp+378h+var_318], rcx
0x18002deb8  mov     rdx, [rcx+8]
0x18002debc  mov     [rsp+378h+var_2E8], rdx
0x18002dec4  mov     [rsp+378h+nSubAuthority], r12d
0x18002dec9  xor     r8d, r8d
0x18002decc  mov     [rsp+378h+var_2D0], r8
0x18002ded4  mov     r14, rdx
0x18002ded7  cmp     [rdx+19h], r8b
0x18002dedb  jnz     loc_18002DFF7
0x18002dee1  mov     [rsp+378h+var_2E8], r14
0x18002dee9  mov     r13, [r14+20h]
0x18002deed  test    r13, r13
0x18002def0  jz      loc_18002DFAC
0x18002def6  test    rax, rax
0x18002def9  jz      loc_18002DFAC
0x18002deff  mov     rcx, rax; pSid
0x18002df02  call    cs:__imp_GetSidSubAuthorityCount
0x18002df08  mov     rbx, rax
0x18002df0b  mov     rcx, r13; pSid
0x18002df0e  call    cs:__imp_GetSidSubAuthorityCount
0x18002df14  movzx   ecx, byte ptr [rbx]
0x18002df17  cmp     [rax], cl
0x18002df19  jb      loc_18002DFB3
0x18002df1f  mov     rcx, [rsp+378h+pSid]; pSid
0x18002df24  call    cs:__imp_GetSidSubAuthorityCount
0x18002df2a  mov     rbx, rax
0x18002df2d  mov     rcx, r13; pSid
0x18002df30  call    cs:__imp_GetSidSubAuthorityCount
0x18002df36  movzx   ecx, byte ptr [rbx]
0x18002df39  cmp     [rax], cl
0x18002df3b  ja      loc_18002DFC8
0x18002df41  xor     bl, bl
0x18002df43  mov     [rsp+378h+var_348], bl
0x18002df47  mov     rcx, r13; pSid
0x18002df4a  call    cs:__imp_GetSidSubAuthorityCount
0x18002df50  cmp     bl, [rax]
0x18002df52  jnb     short loc_18002DFC8
0x18002df54  movzx   eax, bl
0x18002df57  mov     [rsp+378h+nSubAuthority], eax
0x18002df5b  mov     edx, eax; nSubAuthority
0x18002df5d  mov     rcx, [rsp+378h+pSid]; pSid
0x18002df62  call    cs:__imp_GetSidSubAuthority
0x18002df68  mov     rbx, rax
0x18002df6b  mov     edx, [rsp+378h+nSubAuthority]; nSubAuthority
0x18002df6f  mov     rcx, r13; pSid
0x18002df72  call    cs:__imp_GetSidSubAuthority
0x18002df78  mov     ecx, [rbx]
0x18002df7a  cmp     [rax], ecx
0x18002df7c  jb      short loc_18002DFB3
0x18002df7e  mov     edx, [rsp+378h+nSubAuthority]; nSubAuthority
0x18002df82  mov     rcx, [rsp+378h+pSid]; pSid
0x18002df87  call    cs:__imp_GetSidSubAuthority
0x18002df8d  mov     rbx, rax
0x18002df90  mov     edx, [rsp+378h+nSubAuthority]; nSubAuthority
0x18002df94  mov     rcx, r13; pSid
0x18002df97  call    cs:__imp_GetSidSubAuthority
0x18002df9d  mov     ecx, [rbx]
0x18002df9f  cmp     [rax], ecx
0x18002dfa1  ja      short loc_18002DFC8
  ... truncated ...
```
