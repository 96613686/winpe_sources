# CJob::TriggerSerialization(CJob::SerializationBehavior)

- ea: `0x18002e8c0`
- end: `0x18002eee2`
- name: `?TriggerSerialization@CJob@@QEAAJW4SerializationBehavior@1@@Z`
- size: `1570`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002afd0`
- `0x18002c718`
- `0x18002cc00`
- `0x18002fd88`
- `0x180030174`
- `0x180037b90`
- `0x180041974`
- `0x18008a9a0`
- `0x18008b6b0`
- `0x18008c480`
- `0x18009651c`
- `0x1800b0130`
- `0x1800cd780`
- `0x1800cd8c0`
- `0x1800cd9b0`
- `0x1800d1bb0`
- `0x1800d3394`

## callees

- `0x18000b4d0`
- `0x1800292a0`
- `0x180029304`
- `0x18002931c`
- `0x18002c6e0`
- `0x18002e8c0`
- `0x180034760`
- `0x18006d920`
- `0x180084a4c`
- `0x180089fa4`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3de8`
- `0x1800ab7fc`
- `0x1800b6d34`
- `0x1800e17f0`
- `0x1800e1bcc`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ebb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ebb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e935`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e935`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002e9b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002edbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002e9b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002edbc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ee2a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ee2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eb5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002eb5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CJob::TriggerSerialization(__int64 a1, int a2)
{
  TaskScheduler *v4; // r13
  int v5; // r15d
  int v6; // eax
  int v7; // esi
  int v8; // ecx
  int v9; // r14d
  __int64 result; // rax
  const ComError *v11; // rsi
  int v12; // eax
  __int64 v13; // r14
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r10
  char *v17; // r12
  char *v18; // rax
  size_t v19; // rbx
  void *v20; // rax
  size_t v21; // rax
  BitsESE::ScopedBitsDatabaseSessionTransaction *v22; // rax
  BitsESE::ScopedBitsDatabaseSessionTransaction *v23; // rbx
  int v24; // eax
  BitsESE::ScopedBitsDatabaseSessionTransaction *v25; // rdx
  int v26; // eax
  EVENT_LOG *v27; // rcx
  ULONGLONG v28; // rax
  EVENT_LOG *v29; // rcx
  ULONGLONG v30; // rbx
  const ComError *v31; // rbx
  _QWORD v32[2]; // [rsp+30h] [rbp-298h] BYREF
  int v33; // [rsp+40h] [rbp-288h]
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-280h] BYREF
  __int64 v35; // [rsp+58h] [rbp-270h]
  void *v36; // [rsp+60h] [rbp-268h] BYREF
  void *v37; // [rsp+68h] [rbp-260h]
  __int64 v38; // [rsp+70h] [rbp-258h]
  unsigned int v39[2]; // [rsp+78h] [rbp-250h]
  int v40; // [rsp+80h] [rbp-248h]
  BitsESE::ScopedBitsDatabaseSessionTransaction *v41; // [rsp+88h] [rbp-240h]
  char *v42; // [rsp+90h] [rbp-238h]
  int v43; // [rsp+98h] [rbp-230h]
  const ComError *v44[2]; // [rsp+A0h] [rbp-228h] BYREF
  char v45; // [rsp+B0h] [rbp-218h]
  void **pExceptionObject; // [rsp+C0h] [rbp-208h] BYREF
  __int128 v47; // [rsp+C8h] [rbp-200h]
  int v48; // [rsp+D8h] [rbp-1F0h]
  int v49; // [rsp+DCh] [rbp-1ECh]
  int v50; // [rsp+E0h] [rbp-1E8h]
  void **v51; // [rsp+120h] [rbp-1A8h] BYREF
  __int128 v52; // [rsp+128h] [rbp-1A0h]
  int v53; // [rsp+138h] [rbp-190h]
  int v54; // [rsp+13Ch] [rbp-18Ch]
  int v55; // [rsp+140h] [rbp-188h]
  void **v56; // [rsp+180h] [rbp-148h] BYREF
  __int128 v57; // [rsp+188h] [rbp-140h]
  int v58; // [rsp+198h] [rbp-130h]
  int v59; // [rsp+19Ch] [rbp-12Ch]
  int v60; // [rsp+1A0h] [rbp-128h]
  void **v61; // [rsp+1E0h] [rbp-E8h] BYREF
  __int128 v62; // [rsp+1E8h] [rbp-E0h]
  int v63; // [rsp+1F8h] [rbp-D0h]
  int v64; // [rsp+1FCh] [rbp-CCh]
  int v65; // [rsp+200h] [rbp-C8h]
  void **v66; // [rsp+240h] [rbp-88h] BYREF
  __int128 v67; // [rsp+248h] [rbp-80h]
  int v68; // [rsp+258h] [rbp-70h]
  int v69; // [rsp+25Ch] [rbp-6Ch]
  int v70; // [rsp+260h] [rbp-68h]
  ULONGLONG TickCount64; // [rsp+2E0h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, a1);
  v4 = (CJobManager *)((char *)g_Manager + 520);
  v42 = (char *)g_Manager + 520;
  v5 = 0;
  v43 = 0;
  if ( *((_DWORD *)v4 + 14) == GetCurrentThreadId() )
  {
    v6 = 0;
    v7 = 0;
    v8 = 0;
    v9 = 0;
  }
  else
  {
    v5 = 1;
    v43 = 1;
    TaskScheduler::LockWriter(v4, 0);
    v6 = 1;
    v7 = 1;
    v8 = 1;
    v9 = 1;
  }
  if ( *(_BYTE *)(a1 + 936) )
  {
    if ( v6 )
    {
      do
      {
        TaskScheduler::UnlockWriter(v4);
        --v7;
      }
      while ( v7 );
    }
    return 0;
  }
  if ( a2 == 1 )
  {
    *(_BYTE *)(a1 + 1000) = 1;
    if ( v8 )
    {
      do
      {
        TaskScheduler::UnlockWriter(v4);
        --v9;
      }
      while ( v9 );
    }
    return 0;
  }
  TickCount64 = GetTickCount64();
  v11 = (const ComError *)*((_QWORD *)g_Manager + 83);
  v44[1] = v11;
  v45 = 0;
  try
  {
    v12 = (*(__int64 (**)(void))(*(_QWORD *)v11 + 24LL))();
    if ( v12 < 0 )
    {
      v47 = 0;
      pExceptionObject = &ComError::`vftable';
      v48 = v12;
      v49 = 16;
      v50 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v45 = 1;
    v13 = *((_QWORD *)g_Manager + 83);
    v32[0] = &QmgrDatabaseEntityStateWriter::`vftable';
    v32[1] = v13;
    v33 = 0;
    *(_OWORD *)pvar = 0;
    v35 = 0;
    std::vector<_GUID>::vector<_GUID>(&v36);
    *(_QWORD *)v39 = 0;
    v40 = 0;
    v41 = 0;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = BitsESE::StringifyBitsPersistentEntityType(0);
      WPP_SF_S_guid_(*(_QWORD *)(v15 + 16), 44, v15, v14, v16);
    }
    v17 = (char *)v37;
    if ( (unsigned __int64)((_BYTE *)v37 - (_BYTE *)v36) > 0x4000 )
    {
      v18 = (char *)v36 + 0x4000;
LABEL_27:
      v37 = v18;
      goto LABEL_28;
    }
    if ( (unsigned __int64)((_BYTE *)v37 - (_BYTE *)v36) < 0x4000 )
    {
      if ( (unsigned __int64)(v38 - (_QWORD)v36) >= 0x4000 )
      {
        v19 = 0x4000 - ((_BYTE *)v37 - (_BYTE *)v36);
        memset_0(v37, 0, v19);
        v18 = &v17[v19];
        goto LABEL_27;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v36, 0x4000);
    }
LABEL_28:
    LOWORD(pvar[0]) = 0;
    v20 = CoTaskMemAlloc(0x10u);
    pvar[1] = v20;
    if ( !v20 )
    {
      v67 = 0;
      v66 = &ComError::`vftable';
      v68 = -2147024882;
      v69 = 812;
      v70 = 1;
      throw (ComError *)&v66;
    }
    v21 = CTCoAllocPolicy::_CoTaskMemSize(v20);
    memset_0(pvar[1], 0, v21);
    LOWORD(pvar[0]) = 72;
    *(_OWORD *)pvar[1] = *(_OWORD *)(a1 + 676);
    v22 = (BitsESE::ScopedBitsDatabaseSessionTransaction *)HeapAlloc(hBitsHeap, 8u, 0x10u);
    v23 = v22;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v52 = 0;
      v51 = &ComError::`vftable';
      v53 = -2147024882;
      v54 = 0;
      v55 = 1;
      throw (ComError *)&v51;
    }
    *(_QWORD *)v22 = v13;
    *((_BYTE *)v22 + 8) = 0;
    v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
    if ( v24 < 0 )
    {
      v57 = 0;
      v56 = &ComError::`vftable';
      v58 = v24;
      v59 = 15;
      v60 = 1;
      throw (ComError *)&v56;
    }
    v25 = v41;
    v41 = v23;
    if ( v25 )
      std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()();
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 496LL))(a1, v32);
    if ( v26 < 0 )
    {
      v62 = 0;
      v61 = &ComError::`vftable';
      v63 = v26;
      v64 = 1152;
      v65 = 1;
      throw (ComError *)&v61;
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids);
        v27 = WPP_GLOBAL_Control;
      }
      if ( v27 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)v27 + 2), 47, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids);
    }
    if ( *(_QWORD *)v39 )
    {
      QmgrDatabaseEntityStateWriter::WriteToDatabase((QmgrDatabaseEntityStateWriter *)v32, v36, v39[0]);
      *(_QWORD *)v39 = 0;
    }
    BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction(v41);
    v28 = GetTickCount64();
    v30 = v28 - TickCount64;
    if ( v28 - TickCount64 > 0x3A98 )
      EVENT_LOG::ReportSerialize(v29, v28 - TickCount64);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v30);
    if ( v41 )
      std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()();
    std::vector<unsigned char>::_Tidy(&v36);
    PropVariantClear(pvar);
    v32[0] = &IHttpConnection::`vftable';
    if ( v45 )
      (*(void (__fastcall **)(const ComError *))(*(_QWORD *)v11 + 32LL))(v11);
    for ( ; v5; --v5 )
      TaskScheduler::UnlockWriter(v4);
    result = 0;
  }
  catch ( const ComError *v44 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v31 = v44[0];
    }
    else
    {
      v31 = v44[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        *((unsigned int *)v44[0] + 6),
        *((_DWORD *)v44[0] + 7));
    }
    return *((unsigned int *)v31 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18002e8c0  mov     [rsp+arg_8], rbx
0x18002e8c5  mov     [rsp+arg_18], rsi
0x18002e8ca  push    rdi
0x18002e8cb  push    r12
0x18002e8cd  push    r13
0x18002e8cf  push    r14
0x18002e8d1  push    r15
0x18002e8d3  sub     rsp, 2A0h
0x18002e8da  mov     ebx, edx
0x18002e8dc  mov     rdi, rcx
0x18002e8df  lea     rax, WPP_GLOBAL_Control
0x18002e8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8ed  cmp     rcx, rax
0x18002e8f0  jz      short loc_18002E911
0x18002e8f2  test    byte ptr [rcx+1Ch], 1
0x18002e8f6  jz      short loc_18002E911
0x18002e8f8  mov     edx, 38h ; '8'
0x18002e8fd  mov     r9, rdi
0x18002e900  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002e907  mov     rcx, [rcx+10h]
0x18002e90b  call    WPP_SF_q
0x18002e910  nop
0x18002e911  mov     r13, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002e918  add     r13, 208h
0x18002e91f  mov     [rsp+2C8h+var_238], r13
0x18002e927  xor     r12d, r12d
0x18002e92a  mov     r15d, r12d
0x18002e92d  mov     [rsp+2C8h+var_230], r12d
0x18002e935  call    cs:__imp_GetCurrentThreadId
0x18002e93b  cmp     [r13+38h], eax
0x18002e93f  jnz     short loc_18002E94F
0x18002e941  mov     eax, r12d
0x18002e944  mov     esi, r12d
0x18002e947  mov     ecx, r12d
0x18002e94a  mov     r14d, r12d
0x18002e94d  jmp     short loc_18002E973
0x18002e94f  mov     r15d, 1
0x18002e955  mov     [rsp+2C8h+var_230], r15d
0x18002e95d  xor     edx, edx; void *
0x18002e95f  mov     rcx, r13; this
0x18002e962  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x18002e967  mov     eax, r15d
0x18002e96a  mov     esi, r15d
0x18002e96d  mov     ecx, r15d
0x18002e970  mov     r14d, r15d
0x18002e973  cmp     byte ptr [rdi+3A8h], 0
0x18002e97a  jz      short loc_18002E994
0x18002e97c  test    eax, eax
0x18002e97e  jz      short loc_18002E98D
0x18002e980  mov     rcx, r13; this
0x18002e983  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x18002e988  sub     esi, 1
0x18002e98b  jnz     short loc_18002E980
0x18002e98d  xor     eax, eax
0x18002e98f  jmp     loc_18002EEC4
0x18002e994  cmp     ebx, 1
0x18002e997  jnz     short loc_18002E9B8
0x18002e999  mov     [rdi+3E8h], bl
0x18002e99f  test    ecx, ecx
0x18002e9a1  jz      short loc_18002E9B1
0x18002e9a3  mov     rcx, r13; this
0x18002e9a6  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x18002e9ab  sub     r14d, 1
0x18002e9af  jnz     short loc_18002E9A3
0x18002e9b1  xor     eax, eax
0x18002e9b3  jmp     loc_18002EEC4
0x18002e9b8  call    cs:__imp_GetTickCount64
0x18002e9be  mov     [rsp+2C8h+arg_10], rax
0x18002e9c6  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002e9cd  mov     rsi, [rcx+298h]
0x18002e9d4  mov     [rsp+2C8h+var_220], rsi
0x18002e9dc  mov     [rsp+2C8h+var_218], 0
0x18002e9e4  mov     byte ptr [rsp+2C8h+arg_0], 0
0x18002e9ec  mov     rcx, [rsi]
0x18002e9ef  mov     rax, [rcx+18h]
0x18002e9f3  lea     rdx, [rsp+2C8h+arg_0]
0x18002e9fb  mov     rcx, rsi
0x18002e9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea03  test    eax, eax
0x18002ea05  jns     short loc_18002EA52
0x18002ea07  xorps   xmm0, xmm0
0x18002ea0a  movups  [rsp+2C8h+var_200], xmm0
0x18002ea12  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ea19  mov     [rsp+2C8h+pExceptionObject], rcx
0x18002ea21  mov     [rsp+2C8h+var_1F0], eax
0x18002ea28  mov     [rsp+2C8h+var_1EC], 10h
0x18002ea33  mov     [rsp+2C8h+var_1E8], 1
0x18002ea3e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002ea45  lea     rcx, [rsp+2C8h+pExceptionObject]; pExceptionObject
0x18002ea4d  call    _CxxThrowException_0
0x18002ea52  cmp     byte ptr [rsp+2C8h+arg_0], 0
0x18002ea5a  jnz     short loc_18002EA64
0x18002ea5c  mov     [rsp+2C8h+var_218], 1
0x18002ea64  lea     r10, [rdi+2A4h]
0x18002ea6b  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002ea72  mov     r14, [rax+298h]
0x18002ea79  lea     rax, ??_7QmgrDatabaseEntityStateWriter@@6B@; const QmgrDatabaseEntityStateWriter::`vftable'
0x18002ea80  mov     [rsp+2C8h+var_298], rax
0x18002ea85  mov     [rsp+2C8h+var_290], r14
0x18002ea8a  mov     [rsp+2C8h+var_288], r12d
0x18002ea8f  xorps   xmm0, xmm0
0x18002ea92  xor     eax, eax
0x18002ea94  movups  xmmword ptr [rsp+2C8h+pvar], xmm0
0x18002ea99  mov     [rsp+2C8h+var_270], rax
0x18002ea9e  lea     rcx, [rsp+2C8h+var_268]
0x18002eaa3  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18002eaa8  nop
0x18002eaa9  mov     qword ptr [rsp+2C8h+var_250], r12
0x18002eaae  mov     [rsp+2C8h+var_248], r12d
0x18002eab6  mov     [rsp+2C8h+var_240], r12
0x18002eabe  mov     r8, cs:WPP_GLOBAL_Control
0x18002eac5  lea     rax, WPP_GLOBAL_Control
0x18002eacc  cmp     r8, rax
0x18002eacf  jz      short loc_18002EAF5
0x18002ead1  test    byte ptr [r8+1Ch], 1
0x18002ead6  jz      short loc_18002EAF5
0x18002ead8  xor     ecx, ecx
0x18002eada  call    BitsESE__StringifyBitsPersistentEntityType
0x18002eadf  mov     r9, rax
0x18002eae2  mov     edx, 2Ch ; ','
0x18002eae7  mov     [rsp+2C8h+var_2A8], r10
0x18002eaec  mov     rcx, [r8+10h]
0x18002eaf0  call    WPP_SF_S_guid_
0x18002eaf5  mov     rdx, [rsp+2C8h+var_268]
0x18002eafa  mov     r12, [rsp+2C8h+var_260]
0x18002eaff  mov     rcx, r12
0x18002eb02  sub     rcx, rdx
0x18002eb05  mov     ebx, 4000h
0x18002eb0a  cmp     rcx, rbx
0x18002eb0d  jbe     short loc_18002EB18
0x18002eb0f  lea     rax, [rdx+4000h]
0x18002eb16  jmp     short loc_18002EB4A
0x18002eb18  jnb     short loc_18002EB4F
0x18002eb1a  mov     rax, [rsp+2C8h+var_258]
0x18002eb1f  sub     rax, rdx
0x18002eb22  cmp     rax, rbx
0x18002eb25  jnb     short loc_18002EB36
0x18002eb27  mov     rdx, rbx
0x18002eb2a  lea     rcx, [rsp+2C8h+var_268]
0x18002eb2f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002eb34  jmp     short loc_18002EB4F
0x18002eb36  sub     rbx, rcx
0x18002eb39  mov     r8, rbx; Size
0x18002eb3c  xor     edx, edx; Val
0x18002eb3e  mov     rcx, r12; void *
0x18002eb41  call    memset_0
0x18002eb46  lea     rax, [r12+rbx]
0x18002eb4a  mov     [rsp+2C8h+var_260], rax
0x18002eb4f  xor     eax, eax
0x18002eb51  mov     word ptr [rsp+2C8h+pvar], ax
0x18002eb56  mov     ecx, 10h; cb
0x18002eb5b  call    cs:__imp_CoTaskMemAlloc
0x18002eb61  mov     [rsp+2C8h+pvar+8], rax
0x18002eb66  test    rax, rax
0x18002eb69  jz      loc_18002EE6D
0x18002eb6f  mov     rcx, rax; void *
0x18002eb72  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18002eb77  mov     r8, rax; Size
0x18002eb7a  xor     edx, edx; Val
0x18002eb7c  mov     rcx, [rsp+2C8h+pvar+8]; void *
0x18002eb81  call    memset_0
0x18002eb86  mov     eax, 48h ; 'H'
0x18002eb8b  mov     word ptr [rsp+2C8h+pvar], ax
0x18002eb90  mov     rax, [rsp+2C8h+pvar+8]
0x18002eb95  movups  xmm0, xmmword ptr [rdi+2A4h]
0x18002eb9c  movups  xmmword ptr [rax], xmm0
0x18002eb9f  mov     edx, 8; dwFlags
0x18002eba4  mov     r8d, 10h; dwBytes
0x18002ebaa  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18002ebb1  call    cs:__imp_HeapAlloc
0x18002ebb7  mov     rbx, rax
0x18002ebba  test    rax, rax
0x18002ebbd  jnz     loc_18002EC46
0x18002ebc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebca  lea     rax, WPP_GLOBAL_Control
0x18002ebd1  cmp     rcx, rax
0x18002ebd4  jz      short loc_18002EBF7
0x18002ebd6  test    byte ptr [rcx+1Ch], 4
0x18002ebda  jz      short loc_18002EBF7
0x18002ebdc  mov     edx, 0Ah
0x18002ebe1  mov     r9d, 10h
0x18002ebe7  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18002ebee  mov     rcx, [rcx+10h]
0x18002ebf2  call    WPP_SF_d
0x18002ebf7  xorps   xmm0, xmm0
0x18002ebfa  movups  [rsp+2C8h+var_1A0], xmm0
0x18002ec02  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ec09  mov     [rsp+2C8h+var_1A8], rcx
0x18002ec11  mov     [rsp+2C8h+var_190], 8007000Eh
0x18002ec1c  mov     [rsp+2C8h+var_18C], 0
0x18002ec27  mov     [rsp+2C8h+var_188], 1
0x18002ec32  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002ec39  lea     rcx, [rsp+2C8h+var_1A8]; pExceptionObject
0x18002ec41  call    _CxxThrowException_0
0x18002ec46  mov     [rsp+2C8h+arg_0], rbx
0x18002ec4e  mov     [rax], r14
0x18002ec51  mov     byte ptr [rax+8], 0
0x18002ec55  mov     rax, [r14]
0x18002ec58  mov     rcx, r14
0x18002ec5b  mov     rax, [rax+28h]
0x18002ec5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec64  test    eax, eax
0x18002ec66  jns     short loc_18002ECB4
0x18002ec68  xorps   xmm0, xmm0
0x18002ec6b  movups  [rsp+2C8h+var_140], xmm0
0x18002ec73  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ec7a  mov     [rsp+2C8h+var_148], rcx
0x18002ec82  mov     [rsp+2C8h+var_130], eax
0x18002ec89  mov     [rsp+2C8h+var_12C], 0Fh
0x18002ec94  mov     [rsp+2C8h+var_128], 1
0x18002ec9f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002eca6  lea     rcx, [rsp+2C8h+var_148]; pExceptionObject
0x18002ecae  call    _CxxThrowException_0
0x18002ecb4  mov     rdx, [rsp+2C8h+var_240]
0x18002ecbc  mov     [rsp+2C8h+var_240], rbx
0x18002ecc4  test    rdx, rdx
0x18002ecc7  jz      short loc_18002ECCF
0x18002ecc9  call    ??R?$default_delete@VScopedBitsDatabaseSessionTransaction@BitsESE@@@std@@QEBAXPEAVScopedBitsDatabaseSessionTransaction@BitsESE@@@Z; std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()(BitsESE::ScopedBitsDatabaseSessionTransaction *)
0x18002ecce  nop
0x18002eccf  mov     rax, [rdi]
0x18002ecd2  lea     rdx, [rsp+2C8h+var_298]
0x18002ecd7  mov     rcx, rdi
0x18002ecda  mov     rax, [rax+1F0h]
0x18002ece1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ece6  test    eax, eax
0x18002ece8  jns     short loc_18002ED35
0x18002ecea  xorps   xmm0, xmm0
0x18002eced  movups  [rsp+2C8h+var_E0], xmm0
0x18002ecf5  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ecfc  mov     [rsp+2C8h+var_E8], rcx
0x18002ed04  mov     [rsp+2C8h+var_D0], eax
0x18002ed0b  mov     [rsp+2C8h+var_CC], 480h
0x18002ed16  mov     [rsp+2C8h+var_C8], 1
0x18002ed21  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002ed28  lea     rcx, [rsp+2C8h+var_E8]; pExceptionObject
0x18002ed30  call    _CxxThrowException_0
0x18002ed35  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed3c  lea     rdi, WPP_GLOBAL_Control
0x18002ed43  cmp     rcx, rdi
0x18002ed46  jz      short loc_18002ED8A
0x18002ed48  test    byte ptr [rcx+1Ch], 20h
0x18002ed4c  jz      short loc_18002ED6A
0x18002ed4e  mov     edx, 2Eh ; '.'
0x18002ed53  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x18002ed5a  mov     rcx, [rcx+10h]
0x18002ed5e  call    WPP_SF_
0x18002ed63  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed6a  cmp     rcx, rdi
0x18002ed6d  jz      short loc_18002ED8A
0x18002ed6f  test    byte ptr [rcx+1Ch], 20h
0x18002ed73  jz      short loc_18002ED8A
0x18002ed75  mov     edx, 2Fh ; '/'
0x18002ed7a  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x18002ed81  mov     rcx, [rcx+10h]
0x18002ed85  call    WPP_SF_
0x18002ed8a  cmp     qword ptr [rsp+2C8h+var_250], 0
0x18002ed90  jz      short loc_18002EDAF
0x18002ed92  mov     r8d, [rsp+2C8h+var_250]; unsigned int
0x18002ed97  mov     rdx, [rsp+2C8h+var_268]; void *
0x18002ed9c  lea     rcx, [rsp+2C8h+var_298]; this
0x18002eda1  call    ?WriteToDatabase@QmgrDatabaseEntityStateWriter@@AEAAXPEBXK@Z; QmgrDatabaseEntityStateWriter::WriteToDatabase(void const *,ulong)
0x18002eda6  mov     qword ptr [rsp+2C8h+var_250], 0
0x18002edaf  mov     rcx, [rsp+2C8h+var_240]; this
0x18002edb7  call    ?CommitTransaction@ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAAXXZ; BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction(void)
0x18002edbc  call    cs:__imp_GetTickCount64
0x18002edc2  mov     rbx, rax
0x18002edc5  sub     rbx, [rsp+2C8h+arg_10]
0x18002edcd  cmp     rbx, 3A98h
0x18002edd4  jbe     short loc_18002EDDE
0x18002edd6  mov     rdx, rbx; unsigned __int64
0x18002edd9  call    ?ReportSerialize@EVENT_LOG@@QEAAJ_K@Z; EVENT_LOG::ReportSerialize(unsigned __int64)
0x18002edde  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ede5  cmp     rcx, rdi
0x18002ede8  jz      short loc_18002EE09
0x18002edea  test    byte ptr [rcx+1Ch], 20h
0x18002edee  jz      short loc_18002EE09
0x18002edf0  mov     edx, 39h ; '9'
0x18002edf5  mov     r9, rbx
0x18002edf8  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002edff  mov     rcx, [rcx+10h]
0x18002ee03  call    WPP_SF_q
0x18002ee08  nop
0x18002ee09  mov     rdx, [rsp+2C8h+var_240]
0x18002ee11  test    rdx, rdx
0x18002ee14  jz      short loc_18002EE1B
0x18002ee16  call    ??R?$default_delete@VScopedBitsDatabaseSessionTransaction@BitsESE@@@std@@QEBAXPEAVScopedBitsDatabaseSessionTransaction@BitsESE@@@Z; std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()(BitsESE::ScopedBitsDatabaseSessionTransaction *)
0x18002ee1b  lea     rcx, [rsp+2C8h+var_268]
0x18002ee20  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002ee25  lea     rcx, [rsp+2C8h+pvar]; pvar
0x18002ee2a  call    cs:__imp_PropVariantClear
0x18002ee30  lea     rax, ??_7IHttpConnection@@6B@; const IHttpConnection::`vftable'
0x18002ee37  mov     [rsp+2C8h+var_298], rax
0x18002ee3c  cmp     [rsp+2C8h+var_218], 0
0x18002ee44  jz      short loc_18002EE56
0x18002ee46  mov     rax, [rsi]
0x18002ee49  mov     rcx, rsi
0x18002ee4c  mov     rax, [rax+20h]
0x18002ee50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee55  nop
0x18002ee56  test    r15d, r15d
  ... truncated ...
```
