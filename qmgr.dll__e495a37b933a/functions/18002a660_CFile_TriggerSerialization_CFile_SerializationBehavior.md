# CFile::TriggerSerialization(CFile::SerializationBehavior)

- ea: `0x18002a660`
- end: `0x18002ac6d`
- name: `?TriggerSerialization@CFile@@QEAAJW4SerializationBehavior@1@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002887c`
- `0x180029d80`
- `0x18002a0f0`
- `0x18002afd0`
- `0x1800324b8`
- `0x180039290`
- `0x18003a124`
- `0x18005fbe0`
- `0x18008c480`
- `0x180097bf0`
- `0x1800999bc`
- `0x1800a1c68`
- `0x1800b0130`
- `0x1800c7210`
- `0x1800c735c`
- `0x1800c9cc0`
- `0x1800c9e38`
- `0x1800ca73c`

## callees

- `0x18000b4d0`
- `0x1800292a0`
- `0x180029304`
- `0x18002931c`
- `0x180029390`
- `0x18002a660`
- `0x18002c6e0`
- `0x180034760`
- `0x18006d920`
- `0x1800736e0`
- `0x180084a4c`
- `0x180089fa4`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3de8`
- `0x1800ab7fc`
- `0x1800b6d34`
- `0x1800e1bcc`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a946`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a946`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a6d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a6d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a74e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ab47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a74e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ab47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002abb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002abb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a8f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a8f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CFile::TriggerSerialization(__int64 a1, int a2)
{
  TaskScheduler *v4; // r13
  int v5; // r15d
  int v6; // ecx
  int v7; // edi
  __int64 result; // rax
  const ComError *v9; // rdi
  int v10; // eax
  __int64 v11; // r14
  __int64 v12; // r8
  char *v13; // r12
  char *v14; // rax
  size_t v15; // rbx
  void *v16; // rax
  size_t v17; // rax
  BitsESE::ScopedBitsDatabaseSessionTransaction *v18; // rax
  BitsESE::ScopedBitsDatabaseSessionTransaction *v19; // rbx
  int v20; // eax
  BitsESE::ScopedBitsDatabaseSessionTransaction *v21; // rdx
  int v22; // eax
  EVENT_LOG *v23; // rcx
  ULONGLONG v24; // rax
  EVENT_LOG *v25; // rcx
  ULONGLONG v26; // rbx
  const ComError *v27; // rbx
  _QWORD v28[2]; // [rsp+30h] [rbp-298h] BYREF
  int v29; // [rsp+40h] [rbp-288h]
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-280h] BYREF
  __int64 v31; // [rsp+58h] [rbp-270h]
  void *v32; // [rsp+60h] [rbp-268h] BYREF
  void *v33; // [rsp+68h] [rbp-260h]
  __int64 v34; // [rsp+70h] [rbp-258h]
  unsigned int v35[2]; // [rsp+78h] [rbp-250h]
  int v36; // [rsp+80h] [rbp-248h]
  BitsESE::ScopedBitsDatabaseSessionTransaction *v37; // [rsp+88h] [rbp-240h]
  char *v38; // [rsp+90h] [rbp-238h] BYREF
  int v39; // [rsp+98h] [rbp-230h]
  const ComError *v40[2]; // [rsp+A0h] [rbp-228h] BYREF
  char v41; // [rsp+B0h] [rbp-218h]
  void **pExceptionObject; // [rsp+C0h] [rbp-208h] BYREF
  __int128 v43; // [rsp+C8h] [rbp-200h]
  int v44; // [rsp+D8h] [rbp-1F0h]
  int v45; // [rsp+DCh] [rbp-1ECh]
  int v46; // [rsp+E0h] [rbp-1E8h]
  void **v47; // [rsp+120h] [rbp-1A8h] BYREF
  __int128 v48; // [rsp+128h] [rbp-1A0h]
  int v49; // [rsp+138h] [rbp-190h]
  int v50; // [rsp+13Ch] [rbp-18Ch]
  int v51; // [rsp+140h] [rbp-188h]
  void **v52; // [rsp+180h] [rbp-148h] BYREF
  __int128 v53; // [rsp+188h] [rbp-140h]
  int v54; // [rsp+198h] [rbp-130h]
  int v55; // [rsp+19Ch] [rbp-12Ch]
  int v56; // [rsp+1A0h] [rbp-128h]
  void **v57; // [rsp+1E0h] [rbp-E8h] BYREF
  __int128 v58; // [rsp+1E8h] [rbp-E0h]
  int v59; // [rsp+1F8h] [rbp-D0h]
  int v60; // [rsp+1FCh] [rbp-CCh]
  int v61; // [rsp+200h] [rbp-C8h]
  void **v62; // [rsp+240h] [rbp-88h] BYREF
  __int128 v63; // [rsp+248h] [rbp-80h]
  int v64; // [rsp+258h] [rbp-70h]
  int v65; // [rsp+25Ch] [rbp-6Ch]
  int v66; // [rsp+260h] [rbp-68h]
  ULONGLONG TickCount64; // [rsp+2E0h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, a1);
  v4 = (CJobManager *)((char *)g_Manager + 520);
  v38 = (char *)g_Manager + 520;
  v5 = 0;
  v39 = 0;
  if ( *((_DWORD *)v4 + 14) == GetCurrentThreadId() )
  {
    v6 = 0;
    v7 = 0;
  }
  else
  {
    v5 = 1;
    v39 = 1;
    TaskScheduler::LockWriter(v4, 0);
    v6 = 1;
    v7 = 1;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 264) + 936LL) )
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
    *(_BYTE *)(a1 + 408) = 1;
    HoldWriterLock::~HoldWriterLock((HoldWriterLock *)&v38);
    return 0;
  }
  TickCount64 = GetTickCount64();
  v9 = (const ComError *)*((_QWORD *)g_Manager + 83);
  v40[1] = v9;
  v41 = 0;
  try
  {
    v10 = (*(__int64 (**)(void))(*(_QWORD *)v9 + 24LL))();
    if ( v10 < 0 )
    {
      v43 = 0;
      pExceptionObject = &ComError::`vftable';
      v44 = v10;
      v45 = 16;
      v46 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v41 = 1;
    v11 = *((_QWORD *)g_Manager + 83);
    v28[0] = &QmgrDatabaseEntityStateWriter::`vftable';
    v28[1] = v11;
    v29 = 1;
    *(_OWORD *)pvar = 0;
    v31 = 0;
    std::vector<_GUID>::vector<_GUID>(&v32);
    *(_QWORD *)v35 = 0;
    v36 = 0;
    v37 = 0;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v12, (unsigned int)L"File", v12);
    v13 = (char *)v33;
    if ( (unsigned __int64)((_BYTE *)v33 - (_BYTE *)v32) > 0x4000 )
    {
      v14 = (char *)v32 + 0x4000;
LABEL_25:
      v33 = v14;
      goto LABEL_26;
    }
    if ( (unsigned __int64)((_BYTE *)v33 - (_BYTE *)v32) < 0x4000 )
    {
      if ( (unsigned __int64)(v34 - (_QWORD)v32) >= 0x4000 )
      {
        v15 = 0x4000 - ((_BYTE *)v33 - (_BYTE *)v32);
        memset_0(v33, 0, v15);
        v14 = &v13[v15];
        goto LABEL_25;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v32, 0x4000);
    }
LABEL_26:
    LOWORD(pvar[0]) = 0;
    v16 = CoTaskMemAlloc(0x10u);
    pvar[1] = v16;
    if ( !v16 )
    {
      v63 = 0;
      v62 = &ComError::`vftable';
      v64 = -2147024882;
      v65 = 812;
      v66 = 1;
      throw (ComError *)&v62;
    }
    v17 = CTCoAllocPolicy::_CoTaskMemSize(v16);
    memset_0(pvar[1], 0, v17);
    LOWORD(pvar[0]) = 72;
    *(_OWORD *)pvar[1] = *(_OWORD *)(a1 + 384);
    v18 = (BitsESE::ScopedBitsDatabaseSessionTransaction *)HeapAlloc(hBitsHeap, 8u, 0x10u);
    v19 = v18;
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v48 = 0;
      v47 = &ComError::`vftable';
      v49 = -2147024882;
      v50 = 0;
      v51 = 1;
      throw (ComError *)&v47;
    }
    *(_QWORD *)v18 = v11;
    *((_BYTE *)v18 + 8) = 0;
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
    if ( v20 < 0 )
    {
      v53 = 0;
      v52 = &ComError::`vftable';
      v54 = v20;
      v55 = 15;
      v56 = 1;
      throw (ComError *)&v52;
    }
    v21 = v37;
    v37 = v19;
    if ( v21 )
      std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()();
    v22 = CFile::Serialize((CFile *)a1, (struct IQmgrPersistenceWriter *)v28);
    if ( v22 < 0 )
    {
      v58 = 0;
      v57 = &ComError::`vftable';
      v59 = v22;
      v60 = 3425;
      v61 = 1;
      throw (ComError *)&v57;
    }
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids);
        v23 = WPP_GLOBAL_Control;
      }
      if ( v23 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)v23 + 2), 47, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids);
    }
    if ( *(_QWORD *)v35 )
    {
      QmgrDatabaseEntityStateWriter::WriteToDatabase((QmgrDatabaseEntityStateWriter *)v28, v32, v35[0]);
      *(_QWORD *)v35 = 0;
    }
    BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction(v37);
    v24 = GetTickCount64();
    v26 = v24 - TickCount64;
    if ( v24 - TickCount64 > 0x3A98 )
      EVENT_LOG::ReportSerialize(v25, v24 - TickCount64);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, v26);
    if ( v37 )
      std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()();
    std::vector<unsigned char>::_Tidy(&v32);
    PropVariantClear(pvar);
    v28[0] = &IHttpConnection::`vftable';
    if ( v41 )
      (*(void (__fastcall **)(const ComError *))(*(_QWORD *)v9 + 32LL))(v9);
    for ( ; v5; --v5 )
      TaskScheduler::UnlockWriter(v4);
    result = 0;
  }
  catch ( const ComError *v40 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v27 = v40[0];
    }
    else
    {
      v27 = v40[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        *((unsigned int *)v40[0] + 6),
        *((_DWORD *)v40[0] + 7));
    }
    return *((unsigned int *)v27 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18002a660  mov     [rsp+arg_8], rbx
0x18002a665  mov     [rsp+arg_18], rsi
0x18002a66a  push    rdi
0x18002a66b  push    r12
0x18002a66d  push    r13
0x18002a66f  push    r14
0x18002a671  push    r15
0x18002a673  sub     rsp, 2A0h
0x18002a67a  mov     ebx, edx
0x18002a67c  mov     rsi, rcx
0x18002a67f  lea     rax, WPP_GLOBAL_Control
0x18002a686  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a68d  cmp     rcx, rax
0x18002a690  jz      short loc_18002A6B1
0x18002a692  test    byte ptr [rcx+1Ch], 1
0x18002a696  jz      short loc_18002A6B1
0x18002a698  mov     edx, 46h ; 'F'
0x18002a69d  mov     r9, rsi
0x18002a6a0  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a6a7  mov     rcx, [rcx+10h]
0x18002a6ab  call    WPP_SF_q
0x18002a6b0  nop
0x18002a6b1  mov     r13, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002a6b8  add     r13, 208h
0x18002a6bf  mov     [rsp+2C8h+var_238], r13
0x18002a6c7  xor     r12d, r12d
0x18002a6ca  mov     r15d, r12d
0x18002a6cd  mov     [rsp+2C8h+var_230], r12d
0x18002a6d5  call    cs:__imp_GetCurrentThreadId
0x18002a6db  cmp     [r13+38h], eax
0x18002a6df  jnz     short loc_18002A6E9
0x18002a6e1  mov     ecx, r12d
0x18002a6e4  mov     edi, r12d
0x18002a6e7  jmp     short loc_18002A707
0x18002a6e9  mov     r15d, 1
0x18002a6ef  mov     [rsp+2C8h+var_230], r15d
0x18002a6f7  xor     edx, edx; void *
0x18002a6f9  mov     rcx, r13; this
0x18002a6fc  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x18002a701  mov     ecx, r15d
0x18002a704  mov     edi, r15d
0x18002a707  mov     rax, [rsi+108h]
0x18002a70e  cmp     byte ptr [rax+3A8h], 0
0x18002a715  jz      short loc_18002A72F
0x18002a717  test    ecx, ecx
0x18002a719  jz      short loc_18002A728
0x18002a71b  mov     rcx, r13; this
0x18002a71e  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x18002a723  sub     edi, 1
0x18002a726  jnz     short loc_18002A71B
0x18002a728  xor     eax, eax
0x18002a72a  jmp     loc_18002AC4F
0x18002a72f  cmp     ebx, 1
0x18002a732  jnz     short loc_18002A74E
0x18002a734  mov     [rsi+198h], bl
0x18002a73a  lea     rcx, [rsp+2C8h+var_238]; this
0x18002a742  call    ??1HoldWriterLock@@QEAA@XZ; HoldWriterLock::~HoldWriterLock(void)
0x18002a747  xor     eax, eax
0x18002a749  jmp     loc_18002AC4F
0x18002a74e  call    cs:__imp_GetTickCount64
0x18002a754  mov     [rsp+2C8h+arg_10], rax
0x18002a75c  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002a763  mov     rdi, [rcx+298h]
0x18002a76a  mov     [rsp+2C8h+var_220], rdi
0x18002a772  mov     [rsp+2C8h+var_218], 0
0x18002a77a  mov     byte ptr [rsp+2C8h+arg_0], 0
0x18002a782  mov     rcx, [rdi]
0x18002a785  mov     rax, [rcx+18h]
0x18002a789  lea     rdx, [rsp+2C8h+arg_0]
0x18002a791  mov     rcx, rdi
0x18002a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a799  test    eax, eax
0x18002a79b  jns     short loc_18002A7E8
0x18002a79d  xorps   xmm0, xmm0
0x18002a7a0  movups  [rsp+2C8h+var_200], xmm0
0x18002a7a8  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002a7af  mov     [rsp+2C8h+pExceptionObject], rcx
0x18002a7b7  mov     [rsp+2C8h+var_1F0], eax
0x18002a7be  mov     [rsp+2C8h+var_1EC], 10h
0x18002a7c9  mov     [rsp+2C8h+var_1E8], 1
0x18002a7d4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002a7db  lea     rcx, [rsp+2C8h+pExceptionObject]; pExceptionObject
0x18002a7e3  call    _CxxThrowException_0
0x18002a7e8  cmp     byte ptr [rsp+2C8h+arg_0], 0
0x18002a7f0  jnz     short loc_18002A7FA
0x18002a7f2  mov     [rsp+2C8h+var_218], 1
0x18002a7fa  lea     r8, [rsi+180h]
0x18002a801  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002a808  mov     r14, [rax+298h]
0x18002a80f  lea     rax, ??_7QmgrDatabaseEntityStateWriter@@6B@; const QmgrDatabaseEntityStateWriter::`vftable'
0x18002a816  mov     [rsp+2C8h+var_298], rax
0x18002a81b  mov     [rsp+2C8h+var_290], r14
0x18002a820  mov     [rsp+2C8h+var_288], 1
0x18002a828  xorps   xmm0, xmm0
0x18002a82b  xor     eax, eax
0x18002a82d  movups  xmmword ptr [rsp+2C8h+pvar], xmm0
0x18002a832  mov     [rsp+2C8h+var_270], rax
0x18002a837  lea     rcx, [rsp+2C8h+var_268]
0x18002a83c  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18002a841  nop
0x18002a842  mov     qword ptr [rsp+2C8h+var_250], r12
0x18002a847  mov     [rsp+2C8h+var_248], r12d
0x18002a84f  mov     [rsp+2C8h+var_240], r12
0x18002a857  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a85e  lea     rax, WPP_GLOBAL_Control
0x18002a865  cmp     rcx, rax
0x18002a868  jz      short loc_18002A88A
0x18002a86a  test    byte ptr [rcx+1Ch], 1
0x18002a86e  jz      short loc_18002A88A
0x18002a870  mov     edx, 2Ch ; ','
0x18002a875  mov     [rsp+2C8h+var_2A8], r8
0x18002a87a  lea     r9, aFile_0; "File"
0x18002a881  mov     rcx, [rcx+10h]
0x18002a885  call    WPP_SF_S_guid_
0x18002a88a  mov     rdx, [rsp+2C8h+var_268]
0x18002a88f  mov     r12, [rsp+2C8h+var_260]
0x18002a894  mov     rcx, r12
0x18002a897  sub     rcx, rdx
0x18002a89a  mov     ebx, 4000h
0x18002a89f  cmp     rcx, rbx
0x18002a8a2  jbe     short loc_18002A8AD
0x18002a8a4  lea     rax, [rdx+4000h]
0x18002a8ab  jmp     short loc_18002A8DF
0x18002a8ad  jnb     short loc_18002A8E4
0x18002a8af  mov     rax, [rsp+2C8h+var_258]
0x18002a8b4  sub     rax, rdx
0x18002a8b7  cmp     rax, rbx
0x18002a8ba  jnb     short loc_18002A8CB
0x18002a8bc  mov     rdx, rbx
0x18002a8bf  lea     rcx, [rsp+2C8h+var_268]
0x18002a8c4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002a8c9  jmp     short loc_18002A8E4
0x18002a8cb  sub     rbx, rcx
0x18002a8ce  mov     r8, rbx; Size
0x18002a8d1  xor     edx, edx; Val
0x18002a8d3  mov     rcx, r12; void *
0x18002a8d6  call    memset_0
0x18002a8db  lea     rax, [rbx+r12]
0x18002a8df  mov     [rsp+2C8h+var_260], rax
0x18002a8e4  xor     eax, eax
0x18002a8e6  mov     word ptr [rsp+2C8h+pvar], ax
0x18002a8eb  mov     ecx, 10h; cb
0x18002a8f0  call    cs:__imp_CoTaskMemAlloc
0x18002a8f6  mov     [rsp+2C8h+pvar+8], rax
0x18002a8fb  test    rax, rax
0x18002a8fe  jz      loc_18002ABF8
0x18002a904  mov     rcx, rax; void *
0x18002a907  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18002a90c  mov     r8, rax; Size
0x18002a90f  xor     edx, edx; Val
0x18002a911  mov     rcx, [rsp+2C8h+pvar+8]; void *
0x18002a916  call    memset_0
0x18002a91b  mov     eax, 48h ; 'H'
0x18002a920  mov     word ptr [rsp+2C8h+pvar], ax
0x18002a925  mov     rax, [rsp+2C8h+pvar+8]
0x18002a92a  movups  xmm0, xmmword ptr [rsi+180h]
0x18002a931  movups  xmmword ptr [rax], xmm0
0x18002a934  mov     edx, 8; dwFlags
0x18002a939  mov     r8d, 10h; dwBytes
0x18002a93f  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18002a946  call    cs:__imp_HeapAlloc
0x18002a94c  mov     rbx, rax
0x18002a94f  test    rax, rax
0x18002a952  jnz     loc_18002A9DB
0x18002a958  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a95f  lea     rax, WPP_GLOBAL_Control
0x18002a966  cmp     rcx, rax
0x18002a969  jz      short loc_18002A98C
0x18002a96b  test    byte ptr [rcx+1Ch], 4
0x18002a96f  jz      short loc_18002A98C
0x18002a971  mov     edx, 0Ah
0x18002a976  mov     r9d, 10h
0x18002a97c  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18002a983  mov     rcx, [rcx+10h]
0x18002a987  call    WPP_SF_d
0x18002a98c  xorps   xmm0, xmm0
0x18002a98f  movups  [rsp+2C8h+var_1A0], xmm0
0x18002a997  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002a99e  mov     [rsp+2C8h+var_1A8], rcx
0x18002a9a6  mov     [rsp+2C8h+var_190], 8007000Eh
0x18002a9b1  mov     [rsp+2C8h+var_18C], 0
0x18002a9bc  mov     [rsp+2C8h+var_188], 1
0x18002a9c7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002a9ce  lea     rcx, [rsp+2C8h+var_1A8]; pExceptionObject
0x18002a9d6  call    _CxxThrowException_0
0x18002a9db  mov     [rsp+2C8h+arg_0], rbx
0x18002a9e3  mov     [rax], r14
0x18002a9e6  mov     byte ptr [rax+8], 0
0x18002a9ea  mov     rax, [r14]
0x18002a9ed  mov     rcx, r14
0x18002a9f0  mov     rax, [rax+28h]
0x18002a9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9f9  test    eax, eax
0x18002a9fb  jns     short loc_18002AA49
0x18002a9fd  xorps   xmm0, xmm0
0x18002aa00  movups  [rsp+2C8h+var_140], xmm0
0x18002aa08  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002aa0f  mov     [rsp+2C8h+var_148], rcx
0x18002aa17  mov     [rsp+2C8h+var_130], eax
0x18002aa1e  mov     [rsp+2C8h+var_12C], 0Fh
0x18002aa29  mov     [rsp+2C8h+var_128], 1
0x18002aa34  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002aa3b  lea     rcx, [rsp+2C8h+var_148]; pExceptionObject
0x18002aa43  call    _CxxThrowException_0
0x18002aa49  mov     rdx, [rsp+2C8h+var_240]
0x18002aa51  mov     [rsp+2C8h+var_240], rbx
0x18002aa59  test    rdx, rdx
0x18002aa5c  jz      short loc_18002AA64
0x18002aa5e  call    ??R?$default_delete@VScopedBitsDatabaseSessionTransaction@BitsESE@@@std@@QEBAXPEAVScopedBitsDatabaseSessionTransaction@BitsESE@@@Z; std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()(BitsESE::ScopedBitsDatabaseSessionTransaction *)
0x18002aa63  nop
0x18002aa64  lea     rdx, [rsp+2C8h+var_298]; struct IQmgrPersistenceWriter *
0x18002aa69  mov     rcx, rsi; this
0x18002aa6c  call    ?Serialize@CFile@@AEAAJAEAVIQmgrPersistenceWriter@@@Z; CFile::Serialize(IQmgrPersistenceWriter &)
0x18002aa71  test    eax, eax
0x18002aa73  jns     short loc_18002AAC0
0x18002aa75  xorps   xmm0, xmm0
0x18002aa78  movups  [rsp+2C8h+var_E0], xmm0
0x18002aa80  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002aa87  mov     [rsp+2C8h+var_E8], rcx
0x18002aa8f  mov     [rsp+2C8h+var_D0], eax
0x18002aa96  mov     [rsp+2C8h+var_CC], 0D61h
0x18002aaa1  mov     [rsp+2C8h+var_C8], 1
0x18002aaac  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18002aab3  lea     rcx, [rsp+2C8h+var_E8]; pExceptionObject
0x18002aabb  call    _CxxThrowException_0
0x18002aac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aac7  lea     rsi, WPP_GLOBAL_Control
0x18002aace  cmp     rcx, rsi
0x18002aad1  jz      short loc_18002AB15
0x18002aad3  test    byte ptr [rcx+1Ch], 20h
0x18002aad7  jz      short loc_18002AAF5
0x18002aad9  mov     edx, 2Eh ; '.'
0x18002aade  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x18002aae5  mov     rcx, [rcx+10h]
0x18002aae9  call    WPP_SF_
0x18002aaee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaf5  cmp     rcx, rsi
0x18002aaf8  jz      short loc_18002AB15
0x18002aafa  test    byte ptr [rcx+1Ch], 20h
0x18002aafe  jz      short loc_18002AB15
0x18002ab00  mov     edx, 2Fh ; '/'
0x18002ab05  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x18002ab0c  mov     rcx, [rcx+10h]
0x18002ab10  call    WPP_SF_
0x18002ab15  cmp     qword ptr [rsp+2C8h+var_250], 0
0x18002ab1b  jz      short loc_18002AB3A
0x18002ab1d  mov     r8d, [rsp+2C8h+var_250]; unsigned int
0x18002ab22  mov     rdx, [rsp+2C8h+var_268]; void *
0x18002ab27  lea     rcx, [rsp+2C8h+var_298]; this
0x18002ab2c  call    ?WriteToDatabase@QmgrDatabaseEntityStateWriter@@AEAAXPEBXK@Z; QmgrDatabaseEntityStateWriter::WriteToDatabase(void const *,ulong)
0x18002ab31  mov     qword ptr [rsp+2C8h+var_250], 0
0x18002ab3a  mov     rcx, [rsp+2C8h+var_240]; this
0x18002ab42  call    ?CommitTransaction@ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAAXXZ; BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction(void)
0x18002ab47  call    cs:__imp_GetTickCount64
0x18002ab4d  mov     rbx, rax
0x18002ab50  sub     rbx, [rsp+2C8h+arg_10]
0x18002ab58  cmp     rbx, 3A98h
0x18002ab5f  jbe     short loc_18002AB69
0x18002ab61  mov     rdx, rbx; unsigned __int64
0x18002ab64  call    ?ReportSerialize@EVENT_LOG@@QEAAJ_K@Z; EVENT_LOG::ReportSerialize(unsigned __int64)
0x18002ab69  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab70  cmp     rcx, rsi
0x18002ab73  jz      short loc_18002AB94
0x18002ab75  test    byte ptr [rcx+1Ch], 20h
0x18002ab79  jz      short loc_18002AB94
0x18002ab7b  mov     edx, 47h ; 'G'
0x18002ab80  mov     r9, rbx
0x18002ab83  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002ab8a  mov     rcx, [rcx+10h]
0x18002ab8e  call    WPP_SF_q
0x18002ab93  nop
0x18002ab94  mov     rdx, [rsp+2C8h+var_240]
0x18002ab9c  test    rdx, rdx
0x18002ab9f  jz      short loc_18002ABA6
0x18002aba1  call    ??R?$default_delete@VScopedBitsDatabaseSessionTransaction@BitsESE@@@std@@QEBAXPEAVScopedBitsDatabaseSessionTransaction@BitsESE@@@Z; std::default_delete<BitsESE::ScopedBitsDatabaseSessionTransaction>::operator()(BitsESE::ScopedBitsDatabaseSessionTransaction *)
0x18002aba6  lea     rcx, [rsp+2C8h+var_268]
0x18002abab  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002abb0  lea     rcx, [rsp+2C8h+pvar]; pvar
0x18002abb5  call    cs:__imp_PropVariantClear
0x18002abbb  lea     rax, ??_7IHttpConnection@@6B@; const IHttpConnection::`vftable'
0x18002abc2  mov     [rsp+2C8h+var_298], rax
0x18002abc7  cmp     [rsp+2C8h+var_218], 0
0x18002abcf  jz      short loc_18002ABE1
0x18002abd1  mov     rax, [rdi]
0x18002abd4  mov     rcx, rdi
0x18002abd7  mov     rax, [rax+20h]
0x18002abdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abe0  nop
0x18002abe1  test    r15d, r15d
0x18002abe4  jz      short loc_18002ABF4
0x18002abe6  mov     rcx, r13; this
0x18002abe9  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x18002abee  sub     r15d, 1
0x18002abf2  jnz     short loc_18002ABE6
0x18002abf4  xor     eax, eax
0x18002abf6  jmp     short loc_18002AC4F
0x18002abf8  xorps   xmm0, xmm0
0x18002abfb  movups  [rsp+2C8h+var_80], xmm0
0x18002ac03  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18002ac0a  mov     [rsp+2C8h+var_88], rcx
  ... truncated ...
```
