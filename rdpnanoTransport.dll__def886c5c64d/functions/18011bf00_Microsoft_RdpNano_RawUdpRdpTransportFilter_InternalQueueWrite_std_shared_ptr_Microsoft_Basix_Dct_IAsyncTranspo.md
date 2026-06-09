# Microsoft::RdpNano::RawUdpRdpTransportFilter::InternalQueueWrite(std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer> const &)

- ea: `0x18011bf00`
- end: `0x18011c4a9`
- name: `?InternalQueueWrite@RawUdpRdpTransportFilter@RdpNano@Microsoft@@UEAAXAEBV?$shared_ptr@VOutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z`
- size: `1449`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018d1c`
- `0x180018ea4`
- `0x1800328a0`
- `0x18003da74`
- `0x18003f0f4`
- `0x18004569c`
- `0x1800bb210`
- `0x1800ea630`
- `0x1801177f0`
- `0x180117b2c`
- `0x18011bf00`
- `0x1801acb74`
- `0x1802ec708`
- `0x1802ec800`
- `0x1802ecd54`
- `0x1802ed10c`
- `0x1802ed54c`
- `0x1802ee5e0`
- `0x1802ee648`
- `0x1802ee6dc`
- `0x180311dbc`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18011c33b`: `OnWritableThread`
- `0x18011bfb4`: `InternalQueueWrite - length is smaller than syn byte offset: %d`
- `0x18011c1a0`: `Microsoft::RdpNano::RawUdpRdpTransportFilter::InternalQueueWrite`
- `0x18011c18f`: `InternalQueueWrite - failed to shuffle the syn byte\n    %s(%d): %s()`
- `0x18011c37f`: `RawUdpRdpTransportFilter::InternalQueueWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::RdpNano::RawUdpRdpTransportFilter::InternalQueueWrite(
        __int64 a1,
        Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **a2)
{
  Microsoft::Basix::Containers::FlexOBuffer *v4; // rax
  unsigned __int64 v5; // r12
  _BYTE *v6; // rax
  char v7; // r14
  char v8; // r14
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  __int64 v12; // r8
  Microsoft::Basix::Containers::FlexOBuffer *v13; // rax
  struct Microsoft::Basix::Containers::FlexOBuffer *v14; // rax
  Microsoft::Basix::Containers::FlexOBuffer::Iterator *v15; // rax
  unsigned __int64 v16; // r8
  unsigned __int8 *v17; // rdx
  char v18; // bl
  __int64 v19; // r8
  int v20; // r9d
  volatile signed __int32 *v21; // rbx
  struct Microsoft::Basix::Containers::FlexOBuffer *v22; // rax
  unsigned __int16 v23; // r14
  Microsoft::Basix::Containers::FlexOBuffer *v24; // rax
  char v25; // bl
  int v26; // r9d
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **DelayedTraceRecord; // r14
  int i; // ebx
  char *Buffer; // rax
  int v35; // eax
  __int64 result; // rax
  __int64 v37; // rdx
  int v38; // ett
  size_t v39; // r14
  volatile signed __int32 *v40; // rdi
  __int64 (__fastcall *v41)(size_t, Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **, __int128 *); // rbx
  const char *v42; // [rsp+20h] [rbp-89h]
  _BYTE v43[40]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE *v44; // [rsp+68h] [rbp-41h]
  char v45; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int8 v46[7]; // [rsp+71h] [rbp-38h] BYREF
  size_t BufferCount[2]; // [rsp+78h] [rbp-31h] BYREF
  __int128 v48; // [rsp+88h] [rbp-21h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v50; // [rsp+B0h] [rbp+7h]

  v4 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
  v5 = Microsoft::Basix::Containers::FlexOBuffer::Size(v4);
  v6 = (_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
  v7 = 0;
  if ( *v6 != 35 )
    v7 = *(_BYTE *)((unsigned __int8)*v6 + a1 + 1148);
  v8 = 2 * v7;
  if ( v5 >= *(unsigned int *)(a1 + 1204) )
  {
    v18 = *(_BYTE *)(a1 + 1204);
    v45 = 0;
    BufferCount[0] = 0;
    v46[0] = 0;
    Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    *(_QWORD *)&v49 = v46;
    *((_QWORD *)&v49 + 1) = &v45;
    *(_QWORD *)&v50 = BufferCount;
    BYTE8(v50) = v8 | (32 * v18);
    BYTE9(v50) = v18 - 1;
    v44 = 0;
    if ( (unsigned __int8)std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(&v49) )
    {
      *(_QWORD *)v43 = &std::_Func_impl_no_alloc<_lambda_2190cea8d8c84a7b1f4759b526926e8a_,void,unsigned char *,unsigned __int64>::`vftable';
      *(_OWORD *)&v43[8] = v49;
      *(_OWORD *)&v43[24] = v50;
      v44 = v43;
    }
    Microsoft::Basix::Containers::FlexOBuffer::Process(v19, v43);
    if ( !v45 )
    {
      v48 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v48);
      if ( (_QWORD)v48 && *(_BYTE *)(v48 + 128) )
      {
        memset(v43, 0, 32);
        std::string::_Construct<1,char const *>(
          v43,
          "InternalQueueWrite - failed to shuffle the syn byte\n    %s(%d): %s()",
          (const char *)0x44,
          v20,
          v42);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v48,
          (unsigned int)"RDPNANO",
          (unsigned int)v43,
          (unsigned int)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
          42,
          (__int64)"Microsoft::RdpNano::RawUdpRdpTransportFilter::InternalQueueWrite");
        std::string::_Tidy_deallocate(v43);
      }
      v21 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
      if ( *((_QWORD *)&v48 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
    }
    v22 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    v15 = (Microsoft::Basix::Containers::FlexOBuffer::Iterator *)Microsoft::Basix::Containers::FlexOBuffer::Begin(
                                                                   v22,
                                                                   &v49);
    v16 = 1;
    v17 = v46;
  }
  else
  {
    v48 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v48);
    if ( (_QWORD)v48 && *(_BYTE *)(v48 + 128) )
    {
      _mm_lfence();
      memset(v43, 0, 32);
      std::string::_Construct<1,char const *>(
        v43,
        "InternalQueueWrite - length is smaller than syn byte offset: %d",
        63);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64>(
        &v48,
        "RDPNANO",
        v43,
        v5);
      std::string::_Tidy_deallocate(v43);
    }
    v9 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    v10 = *(unsigned int *)(a1 + 1204);
    v11 = (unsigned int)(v10 + 1);
    v49 = 0;
    *((_BYTE *)&v49 + v10) = v8 | (32 * v5);
    BufferCount[0] = 0;
    Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    v44 = 0;
    if ( (unsigned __int8)std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(&v48) )
    {
      *(_QWORD *)v43 = &std::_Func_impl_no_alloc<_lambda_70d0395ae49a88588088054834031df1_,void,unsigned char *,unsigned __int64>::`vftable';
      *(_QWORD *)&v43[8] = &v49;
      *(_QWORD *)&v43[16] = BufferCount;
      *(_QWORD *)&v43[24] = v11;
      v44 = v43;
    }
    Microsoft::Basix::Containers::FlexOBuffer::Process(v12, v43);
    v13 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    Microsoft::Basix::Containers::FlexOBuffer::Clear(v13);
    v14 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    v15 = (Microsoft::Basix::Containers::FlexOBuffer::Iterator *)Microsoft::Basix::Containers::FlexOBuffer::Begin(
                                                                   v14,
                                                                   &v48);
    v16 = v11;
    v17 = (unsigned __int8 *)&v49;
  }
  Microsoft::Basix::Containers::FlexOBuffer::Iterator::InsertBufferCopy(v15, v17, v16);
  v23 = *(_WORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 2);
  v48 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v48);
  if ( (_QWORD)v48 && *(_BYTE *)(v48 + 128) )
  {
    v24 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    v25 = Microsoft::Basix::Containers::FlexOBuffer::Size(v24);
    memset(v43, 0, 32);
    std::string::_Construct<1,char const *>(v43, "Send seq: %d, size: %d", 22, v26);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned short,unsigned __int64>(
      (unsigned int)&v48,
      (unsigned int)"RDPNANO",
      (unsigned int)v43,
      v23,
      v25);
    std::string::_Tidy_deallocate(v43);
  }
  v27 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
  if ( *((_QWORD *)&v48 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  if ( *(_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) == 104 )
  {
    v31 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v29, v28, v30);
    memset(v43, 0, 32);
    std::string::_Construct<1,char const *>(v43, "OnWritableThread", 16);
    DelayedTraceRecord = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v31, v43, 0);
    std::string::_Tidy_deallocate(v43);
    if ( *DelayedTraceRecord )
    {
      BufferCount[0] = 0;
      for ( i = 0; i < 2; ++i )
      {
        Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(
                   *DelayedTraceRecord,
                   BufferCount);
        v35 = snprintf(Buffer, BufferCount[0], "RawUdpRdpTransportFilter::InternalQueueWrite");
        if ( v35 < BufferCount[0] )
          break;
        BufferCount[0] = v35;
      }
      Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(
        *DelayedTraceRecord,
        4,
        "BASIX_DCT");
    }
  }
  result = Microsoft::Basix::Dct::IAsyncTransport::QueueWrite(*(_QWORD *)(a1 + 1104), a2);
  *(_OWORD *)BufferCount = 0;
  v37 = *(_QWORD *)(a1 + 1352);
  if ( v37 )
  {
    result = *(unsigned int *)(v37 + 8);
    while ( (_DWORD)result )
    {
      v38 = result;
      result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(v37 + 8), result + 1, result);
      if ( v38 == (_DWORD)result )
      {
        v39 = *(_QWORD *)(a1 + 1344);
        BufferCount[0] = v39;
        v40 = *(volatile signed __int32 **)(a1 + 1352);
        BufferCount[1] = (size_t)v40;
        goto LABEL_43;
      }
    }
  }
  v39 = BufferCount[0];
  v40 = (volatile signed __int32 *)BufferCount[1];
LABEL_43:
  if ( v39 )
  {
    v41 = *(__int64 (__fastcall **)(size_t, Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **, __int128 *))(*(_QWORD *)v39 + 8LL);
    v49 = 0;
    __ExceptionPtrCreate(&v49);
    result = v41(v39, a2, &v49);
  }
  if ( v40 )
  {
    result = (unsigned int)_InterlockedDecrement(v40 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      result = (unsigned int)_InterlockedDecrement(v40 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18011bf00  mov     [rsp-8+arg_10], rbx
0x18011bf05  push    rbp
0x18011bf06  push    rsi
0x18011bf07  push    rdi
0x18011bf08  push    r12
0x18011bf0a  push    r13
0x18011bf0c  push    r14
0x18011bf0e  push    r15
0x18011bf10  lea     rbp, [rsp-27h]
0x18011bf15  mov     eax, 0D0h
0x18011bf1a  call    _alloca_probe
0x18011bf1f  sub     rsp, rax
0x18011bf22  mov     rax, cs:__security_cookie
0x18011bf29  xor     rax, rsp
0x18011bf2c  mov     [rbp+57h+var_40], rax
0x18011bf30  mov     r15, rdx
0x18011bf33  mov     rdi, rcx
0x18011bf36  mov     rcx, [rdx]; this
0x18011bf39  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011bf3e  mov     rcx, rax; this
0x18011bf41  call    ?Size@FlexOBuffer@Containers@Basix@Microsoft@@QEBA_KXZ; Microsoft::Basix::Containers::FlexOBuffer::Size(void)
0x18011bf46  mov     r12, rax
0x18011bf49  mov     rcx, [r15]
0x18011bf4c  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011bf51  xor     r13d, r13d
0x18011bf54  mov     r14b, r13b
0x18011bf57  cmp     byte ptr [rax], 23h ; '#'
0x18011bf5a  jz      short loc_18011BF67
0x18011bf5c  movzx   ecx, byte ptr [rax]
0x18011bf5f  mov     r14b, [rcx+rdi+47Ch]
0x18011bf67  add     r14b, r14b
0x18011bf6a  mov     eax, [rdi+4B4h]
0x18011bf70  cmp     r12, rax
0x18011bf73  jnb     loc_18011C0C7
0x18011bf79  xorps   xmm0, xmm0
0x18011bf7c  movups  [rbp+57h+var_78], xmm0
0x18011bf80  lea     rcx, [rbp+57h+var_78]
0x18011bf84  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18011bf89  nop
0x18011bf8a  mov     rax, qword ptr [rbp+57h+var_78]
0x18011bf8e  test    rax, rax
0x18011bf91  jz      short loc_18011BFE7
0x18011bf93  cmp     [rax+80h], r13b
0x18011bf9a  jz      short loc_18011BFE7
0x18011bf9c  lfence
0x18011bf9f  xorps   xmm0, xmm0
0x18011bfa2  movups  [rbp+57h+var_D0], xmm0
0x18011bfa6  xorps   xmm1, xmm1
0x18011bfa9  movdqu  [rbp+57h+var_C0], xmm1
0x18011bfae  mov     r8d, 3Fh ; '?'
0x18011bfb4  lea     rdx, aInternalqueuew_0; "InternalQueueWrite - length is smaller "...
0x18011bfbb  lea     rcx, [rbp+57h+var_D0]
0x18011bfbf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011bfc4  nop
0x18011bfc5  mov     r9, r12
0x18011bfc8  lea     r8, [rbp+57h+var_D0]
0x18011bfcc  lea     rdx, aRdpnano; "RDPNANO"
0x18011bfd3  lea     rcx, [rbp+57h+var_78]
0x18011bfd7  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@_K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,unsigned __int64)
0x18011bfdc  nop
0x18011bfdd  lea     rcx, [rbp+57h+var_D0]
0x18011bfe1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011bfe6  nop
0x18011bfe7  or      esi, 0FFFFFFFFh
0x18011bfea  mov     rbx, qword ptr [rbp+57h+var_78+8]
0x18011bfee  test    rbx, rbx
0x18011bff1  jz      short loc_18011C028
0x18011bff3  mov     eax, esi
0x18011bff5  lock xadd [rbx+8], eax
0x18011bffa  add     eax, esi
0x18011bffc  jnz     short loc_18011C028
0x18011bffe  mov     rax, [rbx]
0x18011c001  mov     rcx, rbx
0x18011c004  mov     rax, [rax]
0x18011c007  call    cs:__guard_dispatch_icall_fptr
0x18011c00d  mov     eax, esi
0x18011c00f  lock xadd [rbx+0Ch], eax
0x18011c014  add     eax, esi
0x18011c016  jnz     short loc_18011C028
0x18011c018  mov     rax, [rbx]
0x18011c01b  mov     rcx, rbx
0x18011c01e  mov     rax, [rax+8]
0x18011c022  call    cs:__guard_dispatch_icall_fptr
0x18011c028  shl     r12b, 5
0x18011c02c  or      r12b, r14b
0x18011c02f  mov     ecx, [rdi+4B4h]
0x18011c035  lea     ebx, [rcx+1]
0x18011c038  xorps   xmm0, xmm0
0x18011c03b  movups  [rbp+57h+var_60], xmm0
0x18011c03f  mov     byte ptr [rbp+rcx+57h+var_60], r12b
0x18011c044  mov     [rbp+57h+BufferCount], r13
0x18011c048  mov     rcx, [r15]; this
0x18011c04b  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011c050  mov     r8, rax
0x18011c053  mov     [rbp+57h+var_98], r13
0x18011c057  lea     rcx, [rbp+57h+var_78]
0x18011c05b  call    ??$_Test_callable@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@@std@@YA_NAEBV_lambda_052e919cc0e5399df76dff3972c0cac1_@@@Z; std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(_lambda_052e919cc0e5399df76dff3972c0cac1_ const &)
0x18011c060  test    al, al
0x18011c062  jz      short loc_18011C08B
0x18011c064  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_70d0395ae49a88588088054834031df1_@@XPEAE_K@std@@6B@; const std::_Func_impl_no_alloc<_lambda_70d0395ae49a88588088054834031df1_,void,uchar *,unsigned __int64>::`vftable'
0x18011c06b  mov     qword ptr [rbp+57h+var_D0], rax
0x18011c06f  lea     rax, [rbp+57h+var_60]
0x18011c073  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18011c077  lea     rax, [rbp+57h+BufferCount]
0x18011c07b  mov     qword ptr [rbp+57h+var_C0], rax
0x18011c07f  mov     qword ptr [rbp+57h+var_C0+8], rbx
0x18011c083  lea     rax, [rbp+57h+var_D0]
0x18011c087  mov     [rbp+57h+var_98], rax
0x18011c08b  lea     rdx, [rbp+57h+var_D0]
0x18011c08f  mov     rcx, r8
0x18011c092  call    ?Process@FlexOBuffer@Containers@Basix@Microsoft@@QEAAXV?$function@$$A6AXPEAE_K@Z@std@@@Z; Microsoft::Basix::Containers::FlexOBuffer::Process(std::function<void (uchar *,unsigned __int64)>)
0x18011c097  mov     rcx, [r15]; this
0x18011c09a  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011c09f  mov     rcx, rax; this
0x18011c0a2  call    ?Clear@FlexOBuffer@Containers@Basix@Microsoft@@QEAAXXZ; Microsoft::Basix::Containers::FlexOBuffer::Clear(void)
0x18011c0a7  mov     rcx, [r15]; this
0x18011c0aa  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011c0af  lea     rdx, [rbp+57h+var_78]
0x18011c0b3  mov     rcx, rax
0x18011c0b6  call    ?Begin@FlexOBuffer@Containers@Basix@Microsoft@@QEBA?AVIterator@1234@XZ; Microsoft::Basix::Containers::FlexOBuffer::Begin(void)
0x18011c0bb  mov     r8, rbx
0x18011c0be  lea     rdx, [rbp+57h+var_60]
0x18011c0c2  jmp     loc_18011C236
0x18011c0c7  mov     bl, [rdi+4B4h]
0x18011c0cd  mov     [rbp+57h+var_90], r13b
0x18011c0d1  mov     [rbp+57h+BufferCount], r13
0x18011c0d5  mov     [rbp+57h+var_8F], r13b
0x18011c0d9  mov     rcx, [r15]; this
0x18011c0dc  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011c0e1  mov     r8, rax
0x18011c0e4  lea     rax, [rbp+57h+var_8F]
0x18011c0e8  mov     qword ptr [rbp+57h+var_60], rax
0x18011c0ec  lea     rax, [rbp+57h+var_90]
0x18011c0f0  mov     qword ptr [rbp+57h+var_60+8], rax
0x18011c0f4  lea     rax, [rbp+57h+BufferCount]
0x18011c0f8  mov     qword ptr [rbp+57h+var_50], rax
0x18011c0fc  mov     cl, bl
0x18011c0fe  shl     cl, 5
0x18011c101  or      cl, r14b
0x18011c104  mov     byte ptr [rbp+57h+var_50+8], cl
0x18011c107  dec     bl
0x18011c109  mov     byte ptr [rbp+57h+var_50+9], bl
0x18011c10c  mov     [rbp+57h+var_98], r13
0x18011c110  lea     rcx, [rbp+57h+var_60]
0x18011c114  call    ??$_Test_callable@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@@std@@YA_NAEBV_lambda_052e919cc0e5399df76dff3972c0cac1_@@@Z; std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(_lambda_052e919cc0e5399df76dff3972c0cac1_ const &)
0x18011c119  test    al, al
0x18011c11b  jz      short loc_18011C140
0x18011c11d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2190cea8d8c84a7b1f4759b526926e8a_@@XPEAE_K@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2190cea8d8c84a7b1f4759b526926e8a_,void,uchar *,unsigned __int64>::`vftable'
0x18011c124  mov     qword ptr [rbp+57h+var_D0], rax
0x18011c128  movups  xmm0, [rbp+57h+var_60]
0x18011c12c  movups  [rbp+57h+var_D0+8], xmm0
0x18011c130  movups  xmm1, [rbp+57h+var_50]
0x18011c134  movups  [rbp+57h+var_C0+8], xmm1
0x18011c138  lea     rax, [rbp+57h+var_D0]
0x18011c13c  mov     [rbp+57h+var_98], rax
0x18011c140  lea     rdx, [rbp+57h+var_D0]
0x18011c144  mov     rcx, r8
0x18011c147  call    ?Process@FlexOBuffer@Containers@Basix@Microsoft@@QEAAXV?$function@$$A6AXPEAE_K@Z@std@@@Z; Microsoft::Basix::Containers::FlexOBuffer::Process(std::function<void (uchar *,unsigned __int64)>)
0x18011c14c  or      esi, 0FFFFFFFFh
0x18011c14f  cmp     [rbp+57h+var_90], r13b
0x18011c153  jnz     loc_18011C218
0x18011c159  xorps   xmm0, xmm0
0x18011c15c  movups  [rbp+57h+var_78], xmm0
0x18011c160  lea     rcx, [rbp+57h+var_78]
0x18011c164  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18011c169  nop
0x18011c16a  mov     rax, qword ptr [rbp+57h+var_78]
0x18011c16e  test    rax, rax
0x18011c171  jz      short loc_18011C1DA
0x18011c173  cmp     [rax+80h], r13b
0x18011c17a  jz      short loc_18011C1DA
0x18011c17c  xorps   xmm0, xmm0
0x18011c17f  movups  [rbp+57h+var_D0], xmm0
0x18011c183  xorps   xmm1, xmm1
0x18011c186  movdqu  [rbp+57h+var_C0], xmm1
0x18011c18b  lea     r8d, [rsi+45h]
0x18011c18f  lea     rdx, aInternalqueuew; "InternalQueueWrite - failed to shuffle "...
0x18011c196  lea     rcx, [rbp+57h+var_D0]
0x18011c19a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011c19f  nop
0x18011c1a0  lea     rax, aMicrosoftRdpna_13; "Microsoft::RdpNano::RawUdpRdpTransportF"...
0x18011c1a7  mov     [rsp+100h+var_D8], rax
0x18011c1ac  mov     dword ptr [rsp+100h+var_E0], 32Ah
0x18011c1b4  lea     r9, aCW1SRdnanolibR_2; "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUd"...
0x18011c1bb  lea     r8, [rbp+57h+var_D0]
0x18011c1bf  lea     rdx, aRdpnano; "RDPNANO"
0x18011c1c6  lea     rcx, [rbp+57h+var_78]
0x18011c1ca  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x18011c1cf  nop
0x18011c1d0  lea     rcx, [rbp+57h+var_D0]
0x18011c1d4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011c1d9  nop
0x18011c1da  mov     rbx, qword ptr [rbp+57h+var_78+8]
0x18011c1de  test    rbx, rbx
0x18011c1e1  jz      short loc_18011C218
0x18011c1e3  mov     eax, esi
0x18011c1e5  lock xadd [rbx+8], eax
0x18011c1ea  add     eax, esi
0x18011c1ec  jnz     short loc_18011C218
0x18011c1ee  mov     rax, [rbx]
0x18011c1f1  mov     rcx, rbx
0x18011c1f4  mov     rax, [rax]
0x18011c1f7  call    cs:__guard_dispatch_icall_fptr
0x18011c1fd  mov     eax, esi
0x18011c1ff  lock xadd [rbx+0Ch], eax
0x18011c204  add     eax, esi
0x18011c206  jnz     short loc_18011C218
0x18011c208  mov     rax, [rbx]
0x18011c20b  mov     rcx, rbx
0x18011c20e  mov     rax, [rax+8]
0x18011c212  call    cs:__guard_dispatch_icall_fptr
0x18011c218  mov     rcx, [r15]; this
0x18011c21b  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011c220  lea     rdx, [rbp+57h+var_60]
0x18011c224  mov     rcx, rax
0x18011c227  call    ?Begin@FlexOBuffer@Containers@Basix@Microsoft@@QEBA?AVIterator@1234@XZ; Microsoft::Basix::Containers::FlexOBuffer::Begin(void)
0x18011c22c  mov     r8d, 1; unsigned __int64
0x18011c232  lea     rdx, [rbp+57h+var_8F]; unsigned __int8 *
0x18011c236  mov     rcx, rax; this
0x18011c239  call    ?InsertBufferCopy@Iterator@FlexOBuffer@Containers@Basix@Microsoft@@QEAAXPEBE_K@Z; Microsoft::Basix::Containers::FlexOBuffer::Iterator::InsertBufferCopy(uchar const *,unsigned __int64)
0x18011c23e  mov     rcx, [r15]
0x18011c241  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c246  movzx   r14d, word ptr [rax+2]
0x18011c24b  xorps   xmm0, xmm0
0x18011c24e  movups  [rbp+57h+var_78], xmm0
0x18011c252  lea     rcx, [rbp+57h+var_78]
0x18011c256  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18011c25b  nop
0x18011c25c  mov     rax, qword ptr [rbp+57h+var_78]
0x18011c260  test    rax, rax
0x18011c263  jz      short loc_18011C2CF
0x18011c265  cmp     [rax+80h], r13b
0x18011c26c  jz      short loc_18011C2CF
0x18011c26e  mov     rcx, [r15]; this
0x18011c271  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18011c276  mov     rcx, rax; this
0x18011c279  call    ?Size@FlexOBuffer@Containers@Basix@Microsoft@@QEBA_KXZ; Microsoft::Basix::Containers::FlexOBuffer::Size(void)
0x18011c27e  mov     rbx, rax
0x18011c281  xorps   xmm0, xmm0
0x18011c284  movups  [rbp+57h+var_D0], xmm0
0x18011c288  xorps   xmm1, xmm1
0x18011c28b  movdqu  [rbp+57h+var_C0], xmm1
0x18011c290  mov     r8d, 16h
0x18011c296  lea     rdx, aSendSeqDSizeD; "Send seq: %d, size: %d"
0x18011c29d  lea     rcx, [rbp+57h+var_D0]
0x18011c2a1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011c2a6  nop
0x18011c2a7  mov     [rsp+100h+var_E0], rbx
0x18011c2ac  movzx   r9d, r14w
0x18011c2b0  lea     r8, [rbp+57h+var_D0]
0x18011c2b4  lea     rdx, aRdpnano; "RDPNANO"
0x18011c2bb  lea     rcx, [rbp+57h+var_78]
0x18011c2bf  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@G_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@G_K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,ushort,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,ushort,unsigned __int64)
0x18011c2c4  nop
0x18011c2c5  lea     rcx, [rbp+57h+var_D0]
0x18011c2c9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011c2ce  nop
0x18011c2cf  mov     rbx, qword ptr [rbp+57h+var_78+8]
0x18011c2d3  test    rbx, rbx
0x18011c2d6  jz      short loc_18011C30D
0x18011c2d8  mov     eax, esi
0x18011c2da  lock xadd [rbx+8], eax
0x18011c2df  add     eax, esi
0x18011c2e1  jnz     short loc_18011C30D
0x18011c2e3  mov     rax, [rbx]
0x18011c2e6  mov     rcx, rbx
0x18011c2e9  mov     rax, [rax]
0x18011c2ec  call    cs:__guard_dispatch_icall_fptr
0x18011c2f2  mov     eax, esi
0x18011c2f4  lock xadd [rbx+0Ch], eax
0x18011c2f9  add     eax, esi
0x18011c2fb  jnz     short loc_18011C30D
0x18011c2fd  mov     rax, [rbx]
0x18011c300  mov     rcx, rbx
0x18011c303  mov     rax, [rax+8]
0x18011c307  call    cs:__guard_dispatch_icall_fptr
0x18011c30d  mov     rcx, [r15]
0x18011c310  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c315  cmp     byte ptr [rax], 68h ; 'h'
0x18011c318  jnz     loc_18011C3BA
0x18011c31e  call    ?s_delayedTraceManager@TraceManager@Instrumentation@Basix@Microsoft@@SAAEAV?$shared_ptr@VDelayedTraceManager@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(void)
0x18011c323  mov     rbx, [rax]
0x18011c326  xorps   xmm0, xmm0
0x18011c329  movups  [rbp+57h+var_D0], xmm0
0x18011c32d  xorps   xmm1, xmm1
0x18011c330  movdqu  [rbp+57h+var_C0], xmm1
0x18011c335  mov     r8d, 10h
0x18011c33b  lea     rdx, aOnwritablethre_0; "OnWritableThread"
0x18011c342  lea     rcx, [rbp+57h+var_D0]
0x18011c346  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011c34b  nop
0x18011c34c  xor     r8d, r8d
0x18011c34f  lea     rdx, [rbp+57h+var_D0]
0x18011c353  mov     rcx, rbx
0x18011c356  call    ?GetDelayedTraceRecord@DelayedTraceManager@Instrumentation@Basix@Microsoft@@QEAAAEAV?$shared_ptr@VDelayedTraceRecord@DelayedTraceManager@Instrumentation@Basix@Microsoft@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@_N@Z; Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(std::string const &,bool)
0x18011c35b  mov     r14, rax
0x18011c35e  lea     rcx, [rbp+57h+var_D0]
0x18011c362  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011c367  cmp     [r14], r13
0x18011c36a  jz      short loc_18011C3BA
  ... truncated ...
```
