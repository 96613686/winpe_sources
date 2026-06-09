# CompressedStreamDump::CompressedMemStream::ExecuteParallelDumpTasks(void)

- ea: `0x18040a2dc`
- end: `0x18040a963`
- name: `?ExecuteParallelDumpTasks@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `1671`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180409f68`

## callees

- `0x1800aa0e0`
- `0x180213bdc`
- `0x1804092d0`
- `0x180409584`
- `0x1804097b4`
- `0x1804098f0`
- `0x180409af0`
- `0x180409ca8`
- `0x18040a2dc`
- `0x180411458`
- `0x180411750`
- `0x180411be8`
- `0x180412050`
- `0x180412d0c`
- `0x1804da0c8`
- `0x1804da264`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18040a742`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18040a742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18040a672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18040a672`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18040a31e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18040a31e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18040a30e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18040a30e`

## string_xrefs

- `0x18040a8c4`: `ExecuteParallelDumpTasks failed.\n`
- `0x18040a864`: `ParallelDumpTasks speed: Read: %I64u bytes (~%I64u MB), compressed: %I64u bytes (~%I64u MB). Read %I64u MB/sec, Write %I64u MB/sec. Compression rate: %I64u%%. Time taken: %I64u milliseconds.\n`
- `0x18040a78a`: `Data loss occurred! m_streamHeader.BucketStreamOffset + m_streamHeader.BucketStreamSize is %I64u and it is not equal to m_pMainDumpWriter->GetMaxFileOffset() (%I64u) !\n`
- `0x18040a5d5`: `Spawn %u parallel dump tasks to read/compress/write memory.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CompressedStreamDump::CompressedMemStream::ExecuteParallelDumpTasks(
        CompressedStreamDump::CompressedMemStream *this)
{
  CompressedStreamDump *v2; // rbx
  unsigned __int64 v3; // rax
  unsigned int v4; // r8d
  char *v5; // rdi
  CompressedStreamDump *v6; // rbx
  unsigned int v7; // r8d
  char *v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r9
  __int64 v14; // r12
  int v15; // r13d
  char v16; // dl
  __int64 v17; // rdi
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 *v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r9
  _Thrd_t **v25; // rbx
  _Thrd_t **v26; // rdi
  _Thrd_t *v27; // r14
  _Thrd_t v28; // xmm1
  _Thrd_t *v29; // r14
  int *v30; // rdx
  int v31; // r14d
  const char *v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  const char *v38; // r8
  unsigned __int64 ElapsedMilliseconds; // rbx
  __int128 v41; // [rsp+50h] [rbp-69h] BYREF
  __int64 v42; // [rsp+60h] [rbp-59h]
  __int128 v43; // [rsp+68h] [rbp-51h] BYREF
  __int64 v44; // [rsp+78h] [rbp-41h]
  _Thrd_t v45; // [rsp+80h] [rbp-39h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp-29h] BYREF
  LARGE_INTEGER Frequency; // [rsp+98h] [rbp-21h] BYREF
  unsigned __int64 v48; // [rsp+A0h] [rbp-19h]
  __int64 v49; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-9h] BYREF
  _QWORD v51[11]; // [rsp+B8h] [rbp-1h] BYREF
  _Thrd_t *v52; // [rsp+120h] [rbp+67h] BYREF
  void (__fastcall *v53)(CompressedStreamDump::ParallelDumpTask *); // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v54; // [rsp+130h] [rbp+77h] BYREF
  unsigned __int64 v55; // [rsp+138h] [rbp+7Fh]

  v51[1] = -2;
  PerformanceCount.QuadPart = 0;
  Frequency.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v2 = (CompressedStreamDump *)*((_QWORD *)this + 43);
  *((_QWORD *)this + 25) = v2;
  v3 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3);
  *((_QWORD *)this + 28) = v3;
  v2 = (CompressedStreamDump *)(32LL * (_QWORD)v2);
  *((_QWORD *)this + 27) = v2;
  *((_QWORD *)this + 30) = 40 * v3;
  v41 = 0;
  v42 = 0;
  v5 = (char *)v2 + CompressedStreamDump::GetPaddingBytes(v2, *((unsigned int *)this + 10), v4) + *((_QWORD *)this + 26);
  *((_QWORD *)this + 29) = v5;
  v6 = (CompressedStreamDump *)*((_QWORD *)this + 30);
  v8 = &v5[CompressedStreamDump::GetPaddingBytes(v6, *((unsigned int *)this + 10), v7) + (_QWORD)v6];
  *((_QWORD *)this + 31) = v8;
  *(_QWORD *)(*((_QWORD *)this + 9) + 48LL) = v8;
  v9 = *((unsigned int *)this + 3);
  if ( v9 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3) )
    LODWORD(v9) = -858993459 * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3);
  v10 = (unsigned int)v9;
  *((_DWORD *)this + 3) = v9;
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"Parallelism is set to %u.\n",
    (const char *)(unsigned int)v9);
  v52 = (_Thrd_t *)v10;
  if ( v10 > (v42 - (__int64)v41) >> 3 )
    std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Reallocate<0>(&v41, &v52);
  v11 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3);
  v12 = v11 / v10;
  v55 = v11 / v10;
  v13 = v11 % v10;
  v48 = v11 % v10;
  v14 = 0;
  v54 = 0;
  v15 = 0;
  LODWORD(v53) = 0;
  v43 = 0;
  v44 = 0;
  v16 = 0;
  LOBYTE(v52) = 0;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 46) - *((_QWORD *)this + 45)) >> 3) )
  {
    CompressedStreamDump::GenerateThreadNodeMapping((char *)this + 360, (unsigned int)v10, &v43, v13);
    v16 = 1;
    LOBYTE(v52) = 1;
    v12 = v55;
    v13 = v48;
  }
  v17 = 0;
  while ( 1 )
  {
    v18 = ((unsigned int)v17 < v13) + v12;
    v51[0] = v18;
    if ( v16 )
    {
      if ( (__int64)(*((_QWORD *)&v43 + 1) - v43) >> 2 <= (unsigned __int64)(unsigned int)v17 )
        std::vector<_MINIDUMP_MEMORY_DESCRIPTOR64>::_Xrange();
      v19 = *(unsigned int *)(v43 + 4 * v17);
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 46) - *((_QWORD *)this + 45)) >> 3) <= v19 )
        std::vector<_MINIDUMP_MEMORY_DESCRIPTOR64>::_Xrange();
      v20 = *((_QWORD *)this + 45) + 40 * v19;
    }
    else
    {
      v20 = 0;
    }
    v49 = v20;
    v50 = *((_QWORD *)this + 9);
    v21 = (__int64 *)std::make_unique<CompressedStreamDump::ParallelDumpTask,CompressedStreamDump::CompressedMemoryDumpConfig &,std::vector<MemoryBucket> &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,CompressedStreamDump::DumpWriter *,int &,_NUMA_NODE_RELATIONSHIP *,0>(
                       (unsigned int)&v45,
                       (_DWORD)this,
                       (int)this + 312,
                       (unsigned int)&v54,
                       (__int64)v51,
                       (__int64)this + 208,
                       (__int64)&v50,
                       (__int64)&v53,
                       (__int64)&v49);
    v22 = (_QWORD *)*((_QWORD *)&v41 + 1);
    if ( *((_QWORD *)&v41 + 1) == v42 )
    {
      std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Emplace_reallocate<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(
        &v41,
        *((_QWORD *)&v41 + 1),
        v21);
    }
    else
    {
      v23 = *v21;
      *v21 = 0;
      *v22 = v23;
      *((_QWORD *)&v41 + 1) += 8LL;
    }
    std::unique_ptr<CompressedStreamDump::ParallelDumpTask>::~unique_ptr<CompressedStreamDump::ParallelDumpTask>(&v45);
    LODWORD(v53) = ++v15;
    v14 += v18;
    v54 = v14;
    v17 = (unsigned int)(v17 + 1);
    if ( (unsigned int)v17 >= (unsigned int)v10 )
      break;
    v16 = (char)v52;
    v12 = v55;
    v13 = v48;
  }
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"Spawn %u parallel dump tasks to read/compress/write memory.\n",
    (const char *)(unsigned int)v10,
    v24);
  v26 = (_Thrd_t **)*((_QWORD *)&v41 + 1);
  v25 = (_Thrd_t **)v41;
  if ( (_QWORD)v41 != *((_QWORD *)&v41 + 1) )
  {
    do
    {
      v52 = *v25;
      v27 = v52;
      v53 = CompressedStreamDump::ParallelDumpTask::DumpTaskThreadEntry;
      std::thread::_Start<void (CompressedStreamDump::ParallelDumpTask::*)(void),CompressedStreamDump::ParallelDumpTask *>(
        &v45,
        &v53,
        &v52);
      if ( v27[19]._Id )
        terminate();
      v28 = v45;
      v45 = 0;
      v27[19] = v28;
      std::thread::~thread((std::thread *)&v45);
      ++v25;
    }
    while ( v25 != v26 );
    v26 = (_Thrd_t **)*((_QWORD *)&v41 + 1);
    v25 = (_Thrd_t **)v41;
    if ( (_QWORD)v41 != *((_QWORD *)&v41 + 1) )
    {
      do
      {
        v29 = *v25;
        if ( !(*v25)[19]._Id )
          std::_Throw_Cpp_error(1);
        if ( v29[19]._Id == GetCurrentThreadId() )
          std::_Throw_Cpp_error(5);
        v45 = v29[19];
        if ( Thrd_join(&v45, v30) )
          std::_Throw_Cpp_error(2);
        v29[19] = 0;
        ++v25;
      }
      while ( v25 != v26 );
      v26 = (_Thrd_t **)*((_QWORD *)&v41 + 1);
      v25 = (_Thrd_t **)v41;
    }
  }
  v31 = 0;
  v32 = 0;
  if ( v25 != v26 )
  {
    v33 = *((_QWORD *)this + 22);
    v34 = *((_QWORD *)this + 23);
    do
    {
      v31 += *(&(*v25)[9]._Id + 1);
      v33 += *(_QWORD *)&(*v25)[6]._Id;
      *((_QWORD *)this + 22) = v33;
      v34 += (__int64)(*v25)[7]._Hnd;
      *((_QWORD *)this + 23) = v34;
      v32 += (unsigned __int64)(*v25++)[8]._Hnd;
    }
    while ( v25 != v26 );
  }
  v35 = *((_QWORD *)this + 23);
  *((_QWORD *)this + 32) = v35;
  v36 = *((_QWORD *)this + 22);
  if ( v36 )
    v37 = 100 - 100 * v35 / v36;
  else
    v37 = 0;
  *((_QWORD *)this + 24) = v37;
  if ( *((_QWORD *)this + 32) + *((_QWORD *)this + 31) > *(_QWORD *)(*((_QWORD *)this + 9) + 48LL) )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Data loss occurred! m_streamHeader.BucketStreamOffset + m_streamHeader.BucketStreamSize is %I64u and it is no"
           "t equal to m_pMainDumpWriter->GetMaxFileOffset() (%I64u) !\n",
      (const char *)(*((_QWORD *)this + 32) + *((_QWORD *)this + 31)),
      *(_QWORD *)(*((_QWORD *)this + 9) + 48LL));
LABEL_48:
    if ( (_QWORD)v43 )
    {
      std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFFCuLL);
      v43 = 0;
      v44 = 0;
    }
    if ( (_QWORD)v41 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>>(
        v41,
        *((_QWORD *)&v41 + 1));
      std::_Deallocate<16>(v41, (v42 - v41) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    return 0;
  }
  v38 = (const char *)(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3));
  if ( v38 != v32 )
  {
    ++v31;
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Data loss occurred! m_vMemoryBuckets.size() is %zu and it is not equal to processed bucket count (%I64u) !\n",
      v38);
  }
  if ( v31 )
  {
    CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"ExecuteParallelDumpTasks failed.\n", v38);
    goto LABEL_48;
  }
  if ( SimpleTimer::GetElapsedMilliseconds((SimpleTimer *)&PerformanceCount) )
    ElapsedMilliseconds = SimpleTimer::GetElapsedMilliseconds((SimpleTimer *)&PerformanceCount);
  else
    ElapsedMilliseconds = 1;
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"ParallelDumpTasks speed: Read: %I64u bytes (~%I64u MB), compressed: %I64u bytes (~%I64u MB). Read %I64u MB/sec,"
         " Write %I64u MB/sec. Compression rate: %I64u%%. Time taken: %I64u milliseconds.\n",
    *((const char **)this + 22),
    *((_QWORD *)this + 22) >> 20,
    *((_QWORD *)this + 23),
    *((_QWORD *)this + 23) >> 20,
    1000LL * *((_QWORD *)this + 22) / (ElapsedMilliseconds << 20),
    1000LL * *((_QWORD *)this + 23) / (ElapsedMilliseconds << 20),
    *((_QWORD *)this + 24),
    ElapsedMilliseconds);
  if ( (_QWORD)v43 )
  {
    std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFFCuLL);
    v43 = 0;
    v44 = 0;
  }
  if ( (_QWORD)v41 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>>(
      v41,
      *((_QWORD *)&v41 + 1));
    std::_Deallocate<16>(v41, (v42 - v41) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18040a2dc  push    rbp
0x18040a2de  push    rbx
0x18040a2df  push    rsi
0x18040a2e0  push    rdi
0x18040a2e1  push    r12
0x18040a2e3  push    r13
0x18040a2e5  push    r14
0x18040a2e7  push    r15
0x18040a2e9  lea     rbp, [rsp-1Fh]
0x18040a2ee  sub     rsp, 0D8h
0x18040a2f5  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18040a2fd  mov     rsi, rcx
0x18040a300  xor     eax, eax
0x18040a302  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x18040a306  mov     qword ptr [rbp+57h+Frequency], rax
0x18040a30a  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18040a30e  call    cs:__imp_QueryPerformanceCounter
0x18040a315  nop     dword ptr [rax+rax+00h]
0x18040a31a  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x18040a31e  call    cs:__imp_QueryPerformanceFrequency
0x18040a325  nop     dword ptr [rax+rax+00h]
0x18040a32a  mov     rbx, [rsi+158h]
0x18040a331  mov     [rsi+0C8h], rbx
0x18040a338  lea     r14, [rsi+138h]
0x18040a33f  mov     rax, [r14+8]
0x18040a343  sub     rax, [r14]
0x18040a346  sar     rax, 3
0x18040a34a  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18040a354  imul    rax, r15
0x18040a358  mov     [rsi+0E0h], rax
0x18040a35f  shl     rbx, 5
0x18040a363  mov     [rsi+0D8h], rbx
0x18040a36a  lea     rax, [rax+rax*4]
0x18040a36e  shl     rax, 3
0x18040a372  mov     [rsi+0F0h], rax
0x18040a379  xorps   xmm0, xmm0
0x18040a37c  movdqu  [rbp+57h+var_C0], xmm0
0x18040a381  mov     [rbp+57h+var_B0], 0
0x18040a389  mov     edx, [rsi+28h]; unsigned __int64
0x18040a38c  mov     rcx, rbx; this
0x18040a38f  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18040a394  mov     ecx, eax
0x18040a396  add     rcx, rbx
0x18040a399  mov     rdi, [rsi+0D0h]
0x18040a3a0  add     rdi, rcx
0x18040a3a3  mov     [rsi+0E8h], rdi
0x18040a3aa  mov     rbx, [rsi+0F0h]
0x18040a3b1  mov     edx, [rsi+28h]; unsigned __int64
0x18040a3b4  mov     rcx, rbx; this
0x18040a3b7  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18040a3bc  mov     ecx, eax
0x18040a3be  add     rcx, rdi
0x18040a3c1  add     rcx, rbx
0x18040a3c4  mov     [rsi+0F8h], rcx
0x18040a3cb  mov     rax, [rsi+48h]
0x18040a3cf  mov     [rax+30h], rcx
0x18040a3d3  mov     ecx, [rsi+0Ch]
0x18040a3d6  mov     rax, [r14+8]
0x18040a3da  sub     rax, [r14]
0x18040a3dd  sar     rax, 3
0x18040a3e1  imul    rax, r15
0x18040a3e5  cmp     rcx, rax
0x18040a3e8  cmovnb  ecx, eax
0x18040a3eb  mov     ebx, ecx
0x18040a3ed  mov     [rsi+0Ch], ebx
0x18040a3f0  mov     r8d, ecx; char *
0x18040a3f3  lea     rdx, aParallelismIsS; "Parallelism is set to %u.\n"
0x18040a3fa  mov     ecx, 1; this
0x18040a3ff  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040a404  mov     [rbp+57h+arg_0], rbx
0x18040a408  mov     rax, [rbp+57h+var_B0]
0x18040a40c  sub     rax, qword ptr [rbp+57h+var_C0]
0x18040a410  sar     rax, 3
0x18040a414  cmp     rbx, rax
0x18040a417  jbe     short loc_18040A426
0x18040a419  lea     rdx, [rbp+57h+arg_0]
0x18040a41d  lea     rcx, [rbp+57h+var_C0]
0x18040a421  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Reallocate<0>(unsigned __int64 &)
0x18040a426  mov     rcx, [r14+8]
0x18040a42a  sub     rcx, [r14]
0x18040a42d  sar     rcx, 3
0x18040a431  imul    rcx, r15
0x18040a435  xor     edx, edx
0x18040a437  mov     rax, rcx
0x18040a43a  div     rbx
0x18040a43d  mov     r8, rax
0x18040a440  mov     [rbp+57h+arg_18], rax
0x18040a444  xor     edx, edx
0x18040a446  mov     rax, rcx
0x18040a449  div     rbx
0x18040a44c  mov     r9, rdx
0x18040a44f  mov     [rbp+57h+var_70], rdx
0x18040a453  xor     r12d, r12d
0x18040a456  mov     [rbp+57h+arg_10], r12
0x18040a45a  xor     r13d, r13d
0x18040a45d  mov     dword ptr [rbp+57h+arg_8], r13d
0x18040a461  xorps   xmm0, xmm0
0x18040a464  movdqu  [rbp+57h+var_A8], xmm0
0x18040a469  mov     [rbp+57h+var_98], r12
0x18040a46d  xor     dl, dl
0x18040a46f  mov     byte ptr [rbp+57h+arg_0], dl
0x18040a472  lea     r15, [rsi+168h]
0x18040a479  mov     rax, [r15+8]
0x18040a47d  sub     rax, [r15]
0x18040a480  sar     rax, 3
0x18040a484  mov     r10, 0CCCCCCCCCCCCCCCDh
0x18040a48e  imul    rax, r10
0x18040a492  test    rax, rax
0x18040a495  jz      short loc_18040A4BC
0x18040a497  lea     r8, [rbp+57h+var_A8]
0x18040a49b  mov     edx, ebx
0x18040a49d  mov     rcx, r15
0x18040a4a0  call    ?GenerateThreadNodeMapping@CompressedStreamDump@@YAXAEBV?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@IAEAV?$vector@KV?$allocator@K@std@@@3@@Z; CompressedStreamDump::GenerateThreadNodeMapping(std::vector<_NUMA_NODE_RELATIONSHIP> const &,uint,std::vector<ulong> &)
0x18040a4a5  mov     dl, 1
0x18040a4a7  mov     byte ptr [rbp+57h+arg_0], dl
0x18040a4aa  mov     r8, [rbp+57h+arg_18]
0x18040a4ae  mov     r9, [rbp+57h+var_70]
0x18040a4b2  mov     r10, 0CCCCCCCCCCCCCCCDh
0x18040a4bc  xor     edi, edi
0x18040a4be  test    ebx, ebx
0x18040a4c0  jz      loc_18040A5D2
0x18040a4c6  mov     ecx, edi
0x18040a4c8  cmp     rcx, r9
0x18040a4cb  mov     r14, r8
0x18040a4ce  adc     r14, 0
0x18040a4d2  mov     [rbp+57h+var_58], r14
0x18040a4d6  test    dl, dl
0x18040a4d8  jz      short loc_18040A51A
0x18040a4da  mov     rax, qword ptr [rbp+57h+var_A8+8]
0x18040a4de  mov     rdx, qword ptr [rbp+57h+var_A8]
0x18040a4e2  sub     rax, rdx
0x18040a4e5  sar     rax, 2
0x18040a4e9  cmp     rax, rcx
0x18040a4ec  jbe     loc_18040A947
0x18040a4f2  mov     edx, [rdx+rdi*4]
0x18040a4f5  mov     rcx, [r15]
0x18040a4f8  mov     rax, [r15+8]
0x18040a4fc  sub     rax, rcx
0x18040a4ff  sar     rax, 3
0x18040a503  imul    rax, r10
0x18040a507  cmp     rax, rdx
0x18040a50a  jbe     loc_18040A941
0x18040a510  lea     rax, [rdx+rdx*4]
0x18040a514  lea     rcx, [rcx+rax*8]
0x18040a518  jmp     short loc_18040A51C
0x18040a51a  xor     ecx, ecx
0x18040a51c  mov     [rbp+57h+var_68], rcx
0x18040a520  mov     rax, [rsi+48h]
0x18040a524  mov     [rbp+57h+var_60], rax
0x18040a528  lea     rax, [rbp+57h+var_68]
0x18040a52c  mov     [rsp+110h+var_D0], rax
0x18040a531  lea     rax, [rbp+57h+arg_8]
0x18040a535  mov     [rsp+110h+var_D8], rax
0x18040a53a  lea     rax, [rbp+57h+var_60]
0x18040a53e  mov     [rsp+110h+var_E0], rax
0x18040a543  lea     rax, [rsi+0D0h]
0x18040a54a  mov     [rsp+110h+var_E8], rax
0x18040a54f  lea     rax, [rbp+57h+var_58]
0x18040a553  mov     [rsp+110h+var_F0], rax
0x18040a558  lea     r9, [rbp+57h+arg_10]
0x18040a55c  lea     r8, [rsi+138h]
0x18040a563  mov     rdx, rsi
0x18040a566  lea     rcx, [rbp+57h+var_90]
0x18040a56a  call    ??$make_unique@VParallelDumpTask@CompressedStreamDump@@AEAUCompressedMemoryDumpConfig@2@AEAV?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@AEA_KAEA_KAEA_KPEAVDumpWriter@2@AEAHPEAU_NUMA_NODE_RELATIONSHIP@@$0A@@std@@YA?AV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@0@AEAUCompressedMemoryDumpConfig@CompressedStreamDump@@AEAV?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@0@AEA_K22$$QEAPEAVDumpWriter@3@AEAH$$QEAPEAU_NUMA_NODE_RELATIONSHIP@@@Z; std::make_unique<CompressedStreamDump::ParallelDumpTask,CompressedStreamDump::CompressedMemoryDumpConfig &,std::vector<MemoryBucket> &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,CompressedStreamDump::DumpWriter *,int &,_NUMA_NODE_RELATIONSHIP *,0>(CompressedStreamDump::CompressedMemoryDumpConfig &,std::vector<MemoryBucket> &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,CompressedStreamDump::DumpWriter * &&,int &,_NUMA_NODE_RELATIONSHIP * &&)
0x18040a56f  nop
0x18040a570  mov     rdx, qword ptr [rbp+57h+var_C0+8]
0x18040a574  cmp     rdx, [rbp+57h+var_B0]
0x18040a578  jz      short loc_18040A58E
0x18040a57a  mov     rcx, [rax]
0x18040a57d  mov     qword ptr [rax], 0
0x18040a584  mov     [rdx], rcx
0x18040a587  add     qword ptr [rbp+57h+var_C0+8], 8
0x18040a58c  jmp     short loc_18040A59B
0x18040a58e  mov     r8, rax
0x18040a591  lea     rcx, [rbp+57h+var_C0]
0x18040a595  call    ??$_Emplace_reallocate@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Emplace_reallocate<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(std::unique_ptr<CompressedStreamDump::ParallelDumpTask> * const,std::unique_ptr<CompressedStreamDump::ParallelDumpTask> &&)
0x18040a59a  nop
0x18040a59b  lea     rcx, [rbp+57h+var_90]
0x18040a59f  call    ??1?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@QEAA@XZ; std::unique_ptr<CompressedStreamDump::ParallelDumpTask>::~unique_ptr<CompressedStreamDump::ParallelDumpTask>(void)
0x18040a5a4  inc     r13d
0x18040a5a7  mov     dword ptr [rbp+57h+arg_8], r13d
0x18040a5ab  add     r12, r14
0x18040a5ae  mov     [rbp+57h+arg_10], r12
0x18040a5b2  inc     edi
0x18040a5b4  cmp     edi, ebx
0x18040a5b6  jnb     short loc_18040A5D2
0x18040a5b8  mov     dl, byte ptr [rbp+57h+arg_0]
0x18040a5bb  mov     r8, [rbp+57h+arg_18]
0x18040a5bf  mov     r9, [rbp+57h+var_70]
0x18040a5c3  mov     r10, 0CCCCCCCCCCCCCCCDh
0x18040a5cd  jmp     loc_18040A4C6
0x18040a5d2  mov     r8d, ebx; char *
0x18040a5d5  lea     rdx, aSpawnUParallel; "Spawn %u parallel dump tasks to read/co"...
0x18040a5dc  mov     r12d, 1
0x18040a5e2  mov     ecx, r12d; this
0x18040a5e5  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040a5ea  mov     rbx, qword ptr [rbp+57h+var_C0]
0x18040a5ee  mov     rdi, qword ptr [rbp+57h+var_C0+8]
0x18040a5f2  xor     r15d, r15d
0x18040a5f5  cmp     rbx, rdi
0x18040a5f8  jz      loc_18040A6C6
0x18040a5fe  mov     r14, [rbx]
0x18040a601  mov     [rbp+57h+arg_0], r14
0x18040a605  lea     rax, ?DumpTaskThreadEntry@ParallelDumpTask@CompressedStreamDump@@AEAAXXZ; CompressedStreamDump::ParallelDumpTask::DumpTaskThreadEntry(void)
0x18040a60c  mov     [rbp+57h+arg_8], rax
0x18040a610  lea     r8, [rbp+57h+arg_0]
0x18040a614  lea     rdx, [rbp+57h+arg_8]
0x18040a618  lea     rcx, [rbp+57h+var_90]
0x18040a61c  call    ??$_Start@P8ParallelDumpTask@CompressedStreamDump@@EAAXXZPEAV12@@thread@std@@AEAAX$$QEAP8ParallelDumpTask@CompressedStreamDump@@EAAXXZ$$QEAPEAV23@@Z; std::thread::_Start<void (CompressedStreamDump::ParallelDumpTask::*)(void),CompressedStreamDump::ParallelDumpTask *>(void (CompressedStreamDump::ParallelDumpTask::*&&)(void),CompressedStreamDump::ParallelDumpTask * &&)
0x18040a621  cmp     [r14+138h], r15d
0x18040a628  jnz     loc_18040A742
0x18040a62e  xorps   xmm0, xmm0
0x18040a631  movaps  xmm1, xmmword ptr [rbp+57h+var_90._Hnd]
0x18040a635  movdqa  xmmword ptr [rbp+57h+var_90._Hnd], xmm0
0x18040a63a  movdqu  xmmword ptr [r14+130h], xmm1
0x18040a643  lea     rcx, [rbp+57h+var_90]; this
0x18040a647  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18040a64c  add     rbx, 8
0x18040a650  cmp     rbx, rdi
0x18040a653  jnz     short loc_18040A5FE
0x18040a655  mov     rdi, qword ptr [rbp+57h+var_C0+8]
0x18040a659  mov     rbx, qword ptr [rbp+57h+var_C0]
0x18040a65d  cmp     rbx, rdi
0x18040a660  jz      short loc_18040A6C6
0x18040a662  mov     r14, [rbx]
0x18040a665  cmp     [r14+138h], r15d
0x18040a66c  jz      loc_18040A938
0x18040a672  call    cs:__imp_GetCurrentThreadId
0x18040a679  nop     dword ptr [rax+rax+00h]
0x18040a67e  cmp     [r14+138h], eax
0x18040a685  jz      loc_18040A958
0x18040a68b  movups  xmm0, xmmword ptr [r14+130h]
0x18040a693  movdqu  xmmword ptr [rbp+57h+var_90._Hnd], xmm0
0x18040a698  lea     rcx, [rbp+57h+var_90]; _Thrd_t
0x18040a69c  call    _Thrd_join
0x18040a6a1  test    eax, eax
0x18040a6a3  jnz     loc_18040A94D
0x18040a6a9  xorps   xmm0, xmm0
0x18040a6ac  movdqu  xmmword ptr [r14+130h], xmm0
0x18040a6b5  add     rbx, 8
0x18040a6b9  cmp     rbx, rdi
0x18040a6bc  jnz     short loc_18040A662
0x18040a6be  mov     rdi, qword ptr [rbp+57h+var_C0+8]
0x18040a6c2  mov     rbx, qword ptr [rbp+57h+var_C0]
0x18040a6c6  mov     r14d, r15d
0x18040a6c9  mov     r9, r15
0x18040a6cc  cmp     rbx, rdi
0x18040a6cf  jz      short loc_18040A715
0x18040a6d1  mov     rdx, [rsi+0B0h]
0x18040a6d8  mov     r8, [rsi+0B8h]
0x18040a6df  mov     rax, [rbx]
0x18040a6e2  add     r14d, [rax+9Ch]
0x18040a6e9  add     rdx, [rax+68h]
0x18040a6ed  mov     [rsi+0B0h], rdx
0x18040a6f4  mov     rax, [rbx]
0x18040a6f7  add     r8, [rax+70h]
0x18040a6fb  mov     [rsi+0B8h], r8
0x18040a702  mov     rax, [rbx]
0x18040a705  add     r9, [rax+80h]
0x18040a70c  add     rbx, 8
0x18040a710  cmp     rbx, rdi
0x18040a713  jnz     short loc_18040A6DF
0x18040a715  mov     rax, [rsi+0B8h]
0x18040a71c  mov     [rsi+100h], rax
0x18040a723  mov     rcx, [rsi+0B0h]
0x18040a72a  test    rcx, rcx
0x18040a72d  jz      short loc_18040A74F
0x18040a72f  imul    rax, 64h ; 'd'
0x18040a733  xor     edx, edx
0x18040a735  div     rcx
0x18040a738  mov     ecx, 64h ; 'd'
0x18040a73d  sub     rcx, rax
0x18040a740  jmp     short loc_18040A752
0x18040a742  call    cs:__imp_terminate
0x18040a74f  mov     rcx, r15
0x18040a752  mov     [rsi+0C0h], rcx
0x18040a759  mov     rax, [rsi+48h]
0x18040a75d  mov     rcx, [rax+30h]
0x18040a761  mov     rax, [rsi+0F8h]
0x18040a768  add     rax, [rsi+100h]
0x18040a76f  cmp     rax, rcx
0x18040a772  jbe     short loc_18040A7A0
0x18040a774  mov     rax, [rsi+48h]
0x18040a778  mov     r9, [rax+30h]
0x18040a77c  mov     r8, [rsi+0F8h]
0x18040a783  add     r8, [rsi+100h]; char *
0x18040a78a  lea     rdx, aDataLossOccurr_0; "Data loss occurred! m_streamHeader.Buck"...
0x18040a791  mov     ecx, 4; this
0x18040a796  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040a79b  jmp     loc_18040A8D6
0x18040a7a0  lea     rax, [rsi+138h]
0x18040a7a7  mov     r8, [rax+8]
0x18040a7ab  sub     r8, [rax]
0x18040a7ae  sar     r8, 3
0x18040a7b2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18040a7bc  imul    r8, rax; char *
0x18040a7c0  cmp     r8, r9
0x18040a7c3  jz      short loc_18040A7D9
0x18040a7c5  add     r14d, r12d
0x18040a7c8  lea     rdx, aDataLossOccurr; "Data loss occurred! m_vMemoryBuckets.si"...
  ... truncated ...
```
