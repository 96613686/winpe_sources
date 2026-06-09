# CompressedStreamDump::CompressedMemStream::ExecuteParallelDumpTasks(void)

- ea: `0x18001e114`
- end: `0x18001e7fc`
- name: `?ExecuteParallelDumpTasks@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `1768`
- prototype: `char __fastcall(CompressedStreamDump::CompressedMemStream *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ddd8`

## callees

- `0x180001ae0`
- `0x180001b1c`
- `0x1800020c6`
- `0x1800021c4`
- `0x18001d478`
- `0x18001d818`
- `0x18001d8f8`
- `0x18001d9ac`
- `0x18001e114`
- `0x18001f04c`
- `0x18001f10c`
- `0x18001f14c`
- `0x18002811c`
- `0x18002845c`
- `0x1800289b8`
- `0x180029408`
- `0x18002a0c0`
- `0x18002ab98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e587`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e599`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e599`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001e151`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001e151`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e147`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e147`

## string_xrefs

- `0x18001e776`: `ExecuteParallelDumpTasks failed.\n`
- `0x18001e492`: `Spawn %u parallel dump tasks to read/compress/write memory.\n`
- `0x18001e676`: `Data loss occurred! m_streamHeader.BucketStreamOffset + m_streamHeader.BucketStreamSize is %I64u and it is not equal to m_pMainDumpWriter->GetMaxFileOffset() (%I64u) !\n`
- `0x18001e74d`: `ParallelDumpTasks speed: Read: %I64u bytes (~%I64u MB), compressed: %I64u bytes (~%I64u MB). Read %I64u MB/sec, Write %I64u MB/sec. Compression rate: %I64u%%. Time taken: %I64u milliseconds.\n`

## pseudocode

```c
char __fastcall CompressedStreamDump::CompressedMemStream::ExecuteParallelDumpTasks(
        CompressedStreamDump::CompressedMemStream *this)
{
  unsigned int v2; // r14d
  CompressedStreamDump *v3; // rcx
  unsigned __int64 v4; // rax
  unsigned int v5; // r8d
  unsigned int v6; // r8d
  __int64 v7; // rdx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rsi
  __int64 *v10; // rcx
  __int64 v11; // rbx
  unsigned __int64 v12; // rax
  _QWORD *v13; // rdx
  void *v14; // rax
  __int64 v15; // rbx
  __int64 *v16; // r9
  _QWORD *v17; // r8
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r10
  unsigned __int64 v21; // r9
  __int64 v22; // r13
  char v23; // dl
  _BOOL8 v24; // r8
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r12
  __int64 v28; // rbx
  int v29; // r12d
  __int64 v30; // rax
  __int64 v31; // r9
  CompressedStreamDump::ParallelDumpTask *v32; // rbx
  __int64 *v33; // rbx
  __int64 *v34; // rsi
  __int64 v35; // r14
  _QWORD *v36; // rax
  __int64 v37; // rax
  int v38; // edx
  int v39; // ecx
  __int64 v40; // r14
  void *v41; // r15
  int v42; // r14d
  const char *v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // rcx
  const char *v48; // r8
  unsigned __int64 ElapsedMilliseconds; // rbx
  __int64 v51; // [rsp+20h] [rbp-89h]
  __int64 v52; // [rsp+40h] [rbp-69h]
  __int128 v53; // [rsp+50h] [rbp-59h] BYREF
  __int64 v54; // [rsp+60h] [rbp-49h]
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-41h] BYREF
  LARGE_INTEGER Frequency; // [rsp+70h] [rbp-39h] BYREF
  __int128 v57; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v58; // [rsp+90h] [rbp-19h]
  __int128 v59; // [rsp+98h] [rbp-11h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-1h]
  __int64 v61; // [rsp+B0h] [rbp+7h]
  char v62; // [rsp+110h] [rbp+67h]
  CompressedStreamDump::ParallelDumpTask *v63; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v64; // [rsp+120h] [rbp+77h]
  unsigned __int64 v65; // [rsp+128h] [rbp+7Fh]

  v61 = -2;
  v2 = 0;
  PerformanceCount.QuadPart = 0;
  Frequency.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v3 = (CompressedStreamDump *)*((_QWORD *)this + 43);
  *((_QWORD *)this + 25) = v3;
  v4 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3);
  *((_QWORD *)this + 28) = v4;
  v3 = (CompressedStreamDump *)(32LL * (_QWORD)v3);
  *((_QWORD *)this + 27) = v3;
  *((_QWORD *)this + 30) = 40 * v4;
  v53 = 0;
  v54 = 0;
  *((_QWORD *)this + 29) = *((_QWORD *)this + 27)
                         + *((_QWORD *)this + 26)
                         + CompressedStreamDump::GetPaddingBytes(v3, *((unsigned int *)this + 10), v5);
  v7 = CompressedStreamDump::GetPaddingBytes(*((CompressedStreamDump **)this + 30), *((unsigned int *)this + 10), v6)
     + *((_QWORD *)this + 29)
     + *((_QWORD *)this + 30);
  *((_QWORD *)this + 31) = v7;
  *(_QWORD *)(*((_QWORD *)this + 9) + 48LL) = v7;
  v8 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3);
  if ( *((unsigned int *)this + 3) < v8 )
    LODWORD(v8) = *((_DWORD *)this + 3);
  v9 = (unsigned int)v8;
  *((_DWORD *)this + 3) = v8;
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"Parallelism is set to %u.\n",
    (const char *)(unsigned int)v8);
  v10 = (__int64 *)v53;
  if ( v9 > (v54 - (__int64)v53) >> 3 )
  {
    v11 = *((_QWORD *)&v53 + 1) - v53;
    v12 = 8 * v9;
    if ( 8 * v9 )
    {
      if ( v12 < 0x1000 )
      {
        v13 = operator new(8 * v9);
      }
      else
      {
        if ( v12 + 39 < v12 )
          __scrt_throw_std_bad_array_new_length();
        v14 = operator new(v12 + 39);
        if ( !v14 )
          __fastfail(5u);
        v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v13 - 1) = v14;
      }
      v10 = (__int64 *)v53;
    }
    else
    {
      v13 = 0;
    }
    v15 = v11 >> 3;
    v16 = (__int64 *)*((_QWORD *)&v53 + 1);
    v17 = v13;
    while ( v10 != v16 )
    {
      v18 = *v10;
      *v10 = 0;
      *v17++ = v18;
      ++v10;
    }
    std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Change_array(&v53, v13, v15, v9);
  }
  v19 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3);
  v20 = v19 / v9;
  v58 = v19 / v9;
  v21 = v19 % v9;
  v65 = v19 % v9;
  v22 = 0;
  LODWORD(v63) = 0;
  v59 = 0;
  v60 = 0;
  v23 = 0;
  v62 = 0;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 46) - *((_QWORD *)this + 45)) >> 3) )
  {
    CompressedStreamDump::GenerateThreadNodeMapping((char *)this + 360, (unsigned int)v9, &v59, v21);
    v23 = 1;
    v62 = 1;
    v21 = v65;
    v20 = v58;
  }
  while ( 1 )
  {
    v24 = v2 < v21;
    if ( v23 )
    {
      if ( (__int64)(*((_QWORD *)&v59 + 1) - v59) >> 2 <= (unsigned __int64)v2 )
        std::vector<MemoryBucket *>::_Xrange(v2, v59, v24, v21, v51);
      v25 = *(unsigned int *)(v59 + 4LL * v2);
      v26 = *((_QWORD *)this + 45);
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 46) - v26) >> 3) <= v25 )
        std::vector<MemoryBucket *>::_Xrange(v26, v25, v24, v21, v51);
      v27 = v26 + 40 * v25;
    }
    else
    {
      v27 = 0;
    }
    v64 = v24 + v20;
    v28 = *((_QWORD *)this + 9);
    *(_QWORD *)&v57 = operator new(0x158u);
    v52 = v27;
    v29 = (int)v63;
    v30 = CompressedStreamDump::ParallelDumpTask::ParallelDumpTask(
            (CompressedStreamDump::ParallelDumpTask *)v57,
            v64,
            *((_QWORD *)this + 26),
            v28,
            (_DWORD)v63,
            v52);
    v63 = (CompressedStreamDump::ParallelDumpTask *)v30;
    if ( *((_QWORD *)&v53 + 1) == v54 )
    {
      std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Emplace_reallocate<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(
        &v53,
        *((_QWORD *)&v53 + 1),
        &v63);
      v32 = v63;
    }
    else
    {
      v32 = 0;
      **((_QWORD **)&v53 + 1) = v30;
      *((_QWORD *)&v53 + 1) += 8LL;
    }
    if ( v32 )
    {
      CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(v32);
      operator delete(v32, 0x158u);
    }
    LODWORD(v63) = v29 + 1;
    v22 += v64;
    if ( ++v2 >= (unsigned int)v9 )
      break;
    v23 = v62;
    v21 = v65;
    v20 = v58;
  }
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"Spawn %u parallel dump tasks to read/compress/write memory.\n",
    (const char *)(unsigned int)v9,
    v31);
  v34 = (__int64 *)*((_QWORD *)&v53 + 1);
  v33 = (__int64 *)v53;
  if ( (_QWORD)v53 != *((_QWORD *)&v53 + 1) )
  {
    do
    {
      v35 = *v33;
      v36 = operator new(0x10u);
      *v36 = v35;
      v36[1] = CompressedStreamDump::ParallelDumpTask::DumpTaskThreadEntry;
      v37 = o__beginthreadex_0(
              0,
              0,
              std::thread::_Invoke<std::tuple<void (CompressedStreamDump::ParallelDumpTask::*)(void),CompressedStreamDump::ParallelDumpTask *>,0,1>,
              v36,
              0,
              (char *)&v57 + 8);
      *(_QWORD *)&v57 = v37;
      if ( !v37 )
      {
        DWORD2(v57) = 0;
        std::_Throw_Cpp_error(6);
      }
      if ( *(_DWORD *)(v35 + 312) )
        _std_terminate();
      v38 = DWORD2(v57);
      v39 = HIDWORD(v57);
      v57 = 0;
      *(_QWORD *)(v35 + 304) = v37;
      *(_DWORD *)(v35 + 312) = v38;
      *(_DWORD *)(v35 + 316) = v39;
      ++v33;
    }
    while ( v33 != v34 );
    v34 = (__int64 *)*((_QWORD *)&v53 + 1);
    v33 = (__int64 *)v53;
    if ( (_QWORD)v53 != *((_QWORD *)&v53 + 1) )
    {
      do
      {
        v40 = *v33;
        if ( !*(_DWORD *)(*v33 + 312) )
          std::_Throw_Cpp_error(1);
        if ( *(_DWORD *)(v40 + 312) == GetCurrentThreadId() )
          std::_Throw_Cpp_error(5);
        v41 = *(void **)(v40 + 304);
        if ( WaitForSingleObjectEx(v41, 0xFFFFFFFF, 0) == -1 || !CloseHandle(v41) )
          std::_Throw_Cpp_error(2);
        *(_OWORD *)(v40 + 304) = 0;
        ++v33;
      }
      while ( v33 != v34 );
      v34 = (__int64 *)*((_QWORD *)&v53 + 1);
      v33 = (__int64 *)v53;
    }
  }
  v42 = 0;
  v43 = 0;
  if ( v33 != v34 )
  {
    v44 = *((_QWORD *)this + 22);
    v45 = *((_QWORD *)this + 23);
    do
    {
      v42 += *(_DWORD *)(*v33 + 156);
      v44 += *(_QWORD *)(*v33 + 104);
      *((_QWORD *)this + 22) = v44;
      v45 += *(_QWORD *)(*v33 + 112);
      *((_QWORD *)this + 23) = v45;
      v43 += *(_QWORD *)(*v33++ + 128);
    }
    while ( v33 != v34 );
  }
  v46 = *((_QWORD *)this + 23);
  *((_QWORD *)this + 32) = v46;
  v47 = *((_QWORD *)this + 22);
  if ( v47 )
    v47 = 100 - 100 * v46 / v47;
  *((_QWORD *)this + 24) = v47;
  if ( *((_QWORD *)this + 32) + *((_QWORD *)this + 31) > *(_QWORD *)(*((_QWORD *)this + 9) + 48LL) )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Data loss occurred! m_streamHeader.BucketStreamOffset + m_streamHeader.BucketStreamSize is %I64u and it is no"
           "t equal to m_pMainDumpWriter->GetMaxFileOffset() (%I64u) !\n",
      (const char *)(*((_QWORD *)this + 32) + *((_QWORD *)this + 31)),
      *(_QWORD *)(*((_QWORD *)this + 9) + 48LL));
LABEL_57:
    std::vector<unsigned long>::~vector<unsigned long>(&v59);
    std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::~vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(&v53);
    return 0;
  }
  v48 = (const char *)(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 40) - *((_QWORD *)this + 39)) >> 3));
  if ( v48 != v43 )
  {
    ++v42;
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Data loss occurred! m_vMemoryBuckets.size() is %zu and it is not equal to processed bucket count (%I64u) !\n",
      v48);
  }
  if ( v42 )
  {
    CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"ExecuteParallelDumpTasks failed.\n", v48);
    goto LABEL_57;
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
  std::vector<unsigned long>::~vector<unsigned long>(&v59);
  std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::~vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(&v53);
  return 1;
}

```

## disassembly

```asm
0x18001e114  push    rbp
0x18001e116  push    rbx
0x18001e117  push    rsi
0x18001e118  push    rdi
0x18001e119  push    r12
0x18001e11b  push    r13
0x18001e11d  push    r14
0x18001e11f  push    r15
0x18001e121  lea     rbp, [rsp-1Fh]
0x18001e126  sub     rsp, 0C8h
0x18001e12d  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x18001e135  mov     rdi, rcx
0x18001e138  xor     r14d, r14d
0x18001e13b  mov     qword ptr [rbp+57h+PerformanceCount], r14
0x18001e13f  mov     qword ptr [rbp+57h+Frequency], r14
0x18001e143  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18001e147  call    cs:__imp_QueryPerformanceCounter
0x18001e14d  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x18001e151  call    cs:__imp_QueryPerformanceFrequency
0x18001e157  mov     rcx, [rdi+158h]
0x18001e15e  mov     [rdi+0C8h], rcx
0x18001e165  lea     r12, [rdi+138h]
0x18001e16c  mov     rax, [r12+8]
0x18001e171  sub     rax, [r12]
0x18001e175  sar     rax, 3
0x18001e179  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x18001e183  imul    rax, rbx
0x18001e187  mov     [rdi+0E0h], rax
0x18001e18e  shl     rcx, 5; this
0x18001e192  mov     [rdi+0D8h], rcx
0x18001e199  lea     rax, [rax+rax*4]
0x18001e19d  shl     rax, 3
0x18001e1a1  mov     [rdi+0F0h], rax
0x18001e1a8  xorps   xmm0, xmm0
0x18001e1ab  movdqu  [rbp+57h+var_B0], xmm0
0x18001e1b0  mov     [rbp+57h+var_A0], r14
0x18001e1b4  mov     edx, [rdi+28h]; unsigned __int64
0x18001e1b7  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18001e1bc  mov     ecx, eax
0x18001e1be  add     rcx, [rdi+0D0h]
0x18001e1c5  add     rcx, [rdi+0D8h]
0x18001e1cc  mov     [rdi+0E8h], rcx
0x18001e1d3  mov     edx, [rdi+28h]; unsigned __int64
0x18001e1d6  mov     rcx, [rdi+0F0h]; this
0x18001e1dd  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x18001e1e2  mov     ecx, eax
0x18001e1e4  mov     rdx, [rdi+0F0h]
0x18001e1eb  add     rdx, [rdi+0E8h]
0x18001e1f2  add     rdx, rcx
0x18001e1f5  mov     [rdi+0F8h], rdx
0x18001e1fc  mov     rax, [rdi+48h]
0x18001e200  mov     [rax+30h], rdx
0x18001e204  mov     ecx, [rdi+0Ch]
0x18001e207  mov     rax, [r12+8]
0x18001e20c  sub     rax, [r12]
0x18001e210  sar     rax, 3
0x18001e214  imul    rax, rbx
0x18001e218  cmp     rcx, rax
0x18001e21b  cmovb   eax, ecx
0x18001e21e  mov     esi, eax
0x18001e220  mov     [rdi+0Ch], esi
0x18001e223  mov     r8d, eax; char *
0x18001e226  lea     rdx, aParallelismIsS; "Parallelism is set to %u.\n"
0x18001e22d  lea     ecx, [r14+1]; this
0x18001e231  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e236  mov     rax, [rbp+57h+var_A0]
0x18001e23a  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18001e23e  sub     rax, rcx
0x18001e241  sar     rax, 3
0x18001e245  cmp     rsi, rax
0x18001e248  jbe     loc_18001E2E4
0x18001e24e  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x18001e252  sub     rbx, rcx
0x18001e255  lea     rax, ds:0[rsi*8]
0x18001e25d  test    rax, rax
0x18001e260  jnz     short loc_18001E267
0x18001e262  mov     edx, r14d
0x18001e265  jmp     short loc_18001E2A8
0x18001e267  cmp     rax, 1000h
0x18001e26d  jb      short loc_18001E299
0x18001e26f  lea     rcx, [rax+27h]; Size
0x18001e273  cmp     rcx, rax
0x18001e276  jbe     loc_18001E7BC
0x18001e27c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e281  test    rax, rax
0x18001e284  jnz     short loc_18001E28B
0x18001e286  lea     ecx, [rax+5]
0x18001e289  int     29h; Win8: RtlFailFast(ecx)
0x18001e28b  lea     rdx, [rax+27h]
0x18001e28f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001e293  mov     [rdx-8], rax
0x18001e297  jmp     short loc_18001E2A4
0x18001e299  mov     rcx, rax; Size
0x18001e29c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e2a1  mov     rdx, rax
0x18001e2a4  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18001e2a8  sar     rbx, 3
0x18001e2ac  mov     r9, qword ptr [rbp+57h+var_B0+8]
0x18001e2b0  mov     r8, rdx
0x18001e2b3  jmp     short loc_18001E2C6
0x18001e2b5  mov     rax, [rcx]
0x18001e2b8  mov     [rcx], r14
0x18001e2bb  mov     [r8], rax
0x18001e2be  lea     r8, [r8+8]
0x18001e2c2  add     rcx, 8
0x18001e2c6  cmp     rcx, r9
0x18001e2c9  jnz     short loc_18001E2B5
0x18001e2cb  mov     r9, rsi
0x18001e2ce  mov     r8, rbx
0x18001e2d1  lea     rcx, [rbp+57h+var_B0]
0x18001e2d5  call    ?_Change_array@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Change_array(std::unique_ptr<CompressedStreamDump::ParallelDumpTask> * const,unsigned __int64,unsigned __int64)
0x18001e2da  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x18001e2e4  mov     rcx, [r12+8]
0x18001e2e9  sub     rcx, [r12]
0x18001e2ed  sar     rcx, 3
0x18001e2f1  imul    rcx, rbx
0x18001e2f5  xor     edx, edx
0x18001e2f7  mov     rax, rcx
0x18001e2fa  div     rsi
0x18001e2fd  mov     r10, rax
0x18001e300  mov     [rbp+57h+var_70], rax
0x18001e304  xor     edx, edx
0x18001e306  mov     rax, rcx
0x18001e309  div     rsi
0x18001e30c  mov     r9, rdx
0x18001e30f  mov     [rbp+57h+arg_18], rdx
0x18001e313  mov     r13, r14
0x18001e316  mov     dword ptr [rbp+57h+arg_8], r14d
0x18001e31a  xorps   xmm0, xmm0
0x18001e31d  movdqu  [rbp+57h+var_68], xmm0
0x18001e322  mov     [rbp+57h+var_58], r14
0x18001e326  mov     dl, r14b
0x18001e329  mov     byte ptr [rbp+57h+arg_0], dl
0x18001e32c  lea     r15, [rdi+168h]
0x18001e333  mov     rax, [r15+8]
0x18001e337  sub     rax, [r15]
0x18001e33a  sar     rax, 3
0x18001e33e  imul    rax, rbx
0x18001e342  test    rax, rax
0x18001e345  jz      short loc_18001E362
0x18001e347  lea     r8, [rbp+57h+var_68]
0x18001e34b  mov     edx, esi
0x18001e34d  mov     rcx, r15
0x18001e350  call    ?GenerateThreadNodeMapping@CompressedStreamDump@@YAXAEBV?$vector@U_NUMA_NODE_RELATIONSHIP@@V?$allocator@U_NUMA_NODE_RELATIONSHIP@@@std@@@std@@IAEAV?$vector@KV?$allocator@K@std@@@3@@Z; CompressedStreamDump::GenerateThreadNodeMapping(std::vector<_NUMA_NODE_RELATIONSHIP> const &,uint,std::vector<ulong> &)
0x18001e355  mov     dl, 1
0x18001e357  mov     byte ptr [rbp+57h+arg_0], dl
0x18001e35a  mov     r9, [rbp+57h+arg_18]
0x18001e35e  mov     r10, [rbp+57h+var_70]
0x18001e362  test    esi, esi
0x18001e364  jz      loc_18001E48F
0x18001e36a  mov     ecx, r14d
0x18001e36d  xor     r8d, r8d
0x18001e370  cmp     rcx, r9
0x18001e373  setb    r8b
0x18001e377  test    dl, dl
0x18001e379  jz      short loc_18001E3BB
0x18001e37b  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18001e37f  mov     rdx, qword ptr [rbp+57h+var_68]
0x18001e383  sub     rax, rdx
0x18001e386  sar     rax, 2
0x18001e38a  cmp     rax, rcx
0x18001e38d  jbe     loc_18001E7C8
0x18001e393  mov     edx, [rdx+rcx*4]
0x18001e396  mov     rcx, [r15]
0x18001e399  mov     rax, [r15+8]
0x18001e39d  sub     rax, rcx
0x18001e3a0  sar     rax, 3
0x18001e3a4  imul    rax, rbx
0x18001e3a8  cmp     rax, rdx
0x18001e3ab  jbe     loc_18001E7C2
0x18001e3b1  lea     rax, [rdx+rdx*4]
0x18001e3b5  lea     r12, [rcx+rax*8]
0x18001e3b9  jmp     short loc_18001E3BE
0x18001e3bb  xor     r12d, r12d
0x18001e3be  lea     rax, [r8+r10]
0x18001e3c2  mov     [rbp+57h+arg_10], rax
0x18001e3c6  mov     rbx, [rdi+48h]
0x18001e3ca  mov     ecx, 158h; Size
0x18001e3cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e3d4  mov     qword ptr [rbp+57h+var_80], rax
0x18001e3d8  mov     [rsp+100h+var_C0], r12
0x18001e3dd  mov     r12d, dword ptr [rbp+57h+arg_8]
0x18001e3e1  mov     dword ptr [rsp+100h+var_C8], r12d
0x18001e3e6  mov     [rsp+100h+var_D0], rbx
0x18001e3eb  mov     rcx, [rdi+0D0h]
0x18001e3f2  mov     [rsp+100h+var_D8], rcx
0x18001e3f7  mov     rcx, [rbp+57h+arg_10]
0x18001e3fb  mov     [rsp+100h+var_E0], rcx
0x18001e400  mov     r9, r13
0x18001e403  lea     r8, [rdi+138h]
0x18001e40a  mov     rdx, rdi
0x18001e40d  mov     rcx, rax
0x18001e410  call    ??0ParallelDumpTask@CompressedStreamDump@@QEAA@AEBUCompressedMemoryDumpConfig@1@AEAV?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@_K22PEAVDumpWriter@1@IPEBU_NUMA_NODE_RELATIONSHIP@@@Z; CompressedStreamDump::ParallelDumpTask::ParallelDumpTask(CompressedStreamDump::CompressedMemoryDumpConfig const &,std::vector<MemoryBucket> &,unsigned __int64,unsigned __int64,unsigned __int64,CompressedStreamDump::DumpWriter *,uint,_NUMA_NODE_RELATIONSHIP const *)
0x18001e415  nop
0x18001e416  mov     [rbp+57h+arg_8], rax
0x18001e41a  mov     rdx, qword ptr [rbp+57h+var_B0+8]
0x18001e41e  cmp     rdx, [rbp+57h+var_A0]
0x18001e422  jz      short loc_18001E430
0x18001e424  xor     ebx, ebx
0x18001e426  mov     [rdx], rax
0x18001e429  add     qword ptr [rbp+57h+var_B0+8], 8
0x18001e42e  jmp     short loc_18001E441
0x18001e430  lea     r8, [rbp+57h+arg_8]
0x18001e434  lea     rcx, [rbp+57h+var_B0]
0x18001e438  call    ??$_Emplace_reallocate@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Emplace_reallocate<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(std::unique_ptr<CompressedStreamDump::ParallelDumpTask> * const,std::unique_ptr<CompressedStreamDump::ParallelDumpTask> &&)
0x18001e43d  mov     rbx, [rbp+57h+arg_8]
0x18001e441  test    rbx, rbx
0x18001e444  jz      short loc_18001E45B
0x18001e446  mov     rcx, rbx; this
0x18001e449  call    ??1ParallelDumpTask@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(void)
0x18001e44e  mov     edx, 158h; unsigned __int64
0x18001e453  mov     rcx, rbx; void *
0x18001e456  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e45b  inc     r12d
0x18001e45e  mov     dword ptr [rbp+57h+arg_8], r12d
0x18001e462  add     r13, [rbp+57h+arg_10]
0x18001e466  inc     r14d
0x18001e469  cmp     r14d, esi
0x18001e46c  jnb     short loc_18001E488
0x18001e46e  mov     dl, byte ptr [rbp+57h+arg_0]
0x18001e471  mov     r9, [rbp+57h+arg_18]
0x18001e475  mov     r10, [rbp+57h+var_70]
0x18001e479  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x18001e483  jmp     loc_18001E36A
0x18001e488  lea     r12, [rdi+138h]
0x18001e48f  mov     r8d, esi; char *
0x18001e492  lea     rdx, aSpawnUParallel; "Spawn %u parallel dump tasks to read/co"...
0x18001e499  mov     ecx, 1; this
0x18001e49e  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e4a3  mov     rbx, qword ptr [rbp+57h+var_B0]
0x18001e4a7  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x18001e4ab  cmp     rbx, rsi
0x18001e4ae  jz      loc_18001E5C4
0x18001e4b4  mov     r14, [rbx]
0x18001e4b7  mov     ecx, 10h; Size
0x18001e4bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e4c1  mov     [rax], r14
0x18001e4c4  lea     rcx, ?DumpTaskThreadEntry@ParallelDumpTask@CompressedStreamDump@@AEAAXXZ; CompressedStreamDump::ParallelDumpTask::DumpTaskThreadEntry(void)
0x18001e4cb  mov     [rax+8], rcx
0x18001e4cf  mov     [rbp+57h+arg_0], rax
0x18001e4d3  lea     rcx, [rbp+57h+var_80+8]
0x18001e4d7  mov     [rsp+100h+var_D8], rcx
0x18001e4dc  mov     dword ptr [rsp+100h+var_E0], 0
0x18001e4e4  mov     r9, rax
0x18001e4e7  lea     r8, ??$_Invoke@V?$tuple@P8ParallelDumpTask@CompressedStreamDump@@EAAXXZPEAV12@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (CompressedStreamDump::ParallelDumpTask::*)(void),CompressedStreamDump::ParallelDumpTask *>,0,1>(void *)
0x18001e4ee  xor     edx, edx
0x18001e4f0  xor     ecx, ecx
0x18001e4f2  call    _o__beginthreadex_0
0x18001e4f7  mov     qword ptr [rbp+57h+var_80], rax
0x18001e4fb  test    rax, rax
0x18001e4fe  jz      loc_18001E7D4
0x18001e504  cmp     dword ptr [r14+138h], 0
0x18001e50c  jnz     loc_18001E7CE
0x18001e512  xorps   xmm0, xmm0
0x18001e515  mov     edx, dword ptr [rbp+57h+var_80+8]
0x18001e518  mov     ecx, dword ptr [rbp+57h+var_80+0Ch]
0x18001e51b  movdqa  [rbp+57h+var_80], xmm0
0x18001e520  mov     [r14+130h], rax
0x18001e527  mov     [r14+138h], edx
0x18001e52e  mov     [r14+13Ch], ecx
0x18001e535  add     rbx, 8
0x18001e539  cmp     rbx, rsi
0x18001e53c  jnz     loc_18001E4B4
0x18001e542  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x18001e546  mov     rbx, qword ptr [rbp+57h+var_B0]
0x18001e54a  cmp     rbx, rsi
0x18001e54d  jz      short loc_18001E5C4
0x18001e54f  or      r13d, 0FFFFFFFFh
0x18001e553  mov     r14, [rbx]
0x18001e556  cmp     dword ptr [r14+138h], 0
0x18001e55e  jz      loc_18001E7B1
0x18001e564  call    cs:__imp_GetCurrentThreadId
0x18001e56a  cmp     [r14+138h], eax
0x18001e571  jz      loc_18001E7F1
0x18001e577  mov     r15, [r14+130h]
0x18001e57e  xor     r8d, r8d; bAlertable
0x18001e581  mov     edx, r13d; dwMilliseconds
0x18001e584  mov     rcx, r15; hHandle
0x18001e587  call    cs:__imp_WaitForSingleObjectEx
0x18001e58d  cmp     eax, r13d
0x18001e590  jz      loc_18001E7E6
0x18001e596  mov     rcx, r15; hObject
0x18001e599  call    cs:__imp_CloseHandle
0x18001e59f  test    eax, eax
0x18001e5a1  jz      loc_18001E7E6
0x18001e5a7  xorps   xmm0, xmm0
0x18001e5aa  movdqu  xmmword ptr [r14+130h], xmm0
0x18001e5b3  add     rbx, 8
0x18001e5b7  cmp     rbx, rsi
0x18001e5ba  jnz     short loc_18001E553
0x18001e5bc  mov     rsi, qword ptr [rbp+57h+var_B0+8]
0x18001e5c0  mov     rbx, qword ptr [rbp+57h+var_B0]
0x18001e5c4  xor     r14d, r14d
0x18001e5c7  xor     r9d, r9d
0x18001e5ca  cmp     rbx, rsi
0x18001e5cd  jz      short loc_18001E613
0x18001e5cf  mov     rdx, [rdi+0B0h]
0x18001e5d6  mov     r8, [rdi+0B8h]
0x18001e5dd  mov     rax, [rbx]
0x18001e5e0  add     r14d, [rax+9Ch]
  ... truncated ...
```
