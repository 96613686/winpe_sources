# CompressedStreamDump::ParallelDumpTask::FlushWriteCacheToFile(void)

- ea: `0x180029974`
- end: `0x180029b27`
- name: `?FlushWriteCacheToFile@ParallelDumpTask@CompressedStreamDump@@AEAA_NXZ`
- size: `435`
- prototype: `bool __fastcall(CompressedStreamDump::ParallelDumpTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002978c`

## callees

- `0x180003424`
- `0x18001f14c`
- `0x18002845c`
- `0x1800289b8`
- `0x180029974`
- `0x180029ff8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a9b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180029a91`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180029a91`

## string_xrefs

- `0x180029acd`: `WriteAsync->WriteFile failed with error. GetLastError: %u, Offset: 0x%p, BytesToWrite: %u.\n`
- `0x180029aeb`: `DumpWriter:WriteAsync failed because DumpWriter has errors.\n`
- `0x180029afe`: `FlushWriteCacheToFile - WriteAsync failed.\n`
- `0x18002999a`: `FlushWriteCacheToFile - WaitForBucketWriteComplete failed.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CompressedStreamDump::ParallelDumpTask::FlushWriteCacheToFile(
        CompressedStreamDump::ParallelDumpTask *this)
{
  bool v2; // bl
  const char *v3; // r8
  const char *v4; // rdx
  size_t v5; // r8
  const void *v6; // rdx
  void *v7; // rcx
  __int64 v8; // rdx
  CompressedStreamDump *v9; // rbx
  unsigned int v10; // r8d
  unsigned int v11; // ecx
  __int64 v12; // r9
  __int64 v13; // rax
  const char *v14; // r8
  __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // edx
  __int64 v19; // rax
  __int64 v20; // rbx
  DWORD LastError; // eax
  __int64 v22; // rax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-18h]

  if ( *((int *)this + 38) > 0 )
  {
    v2 = CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(this);
    if ( !v2 )
    {
      v4 = "FlushWriteCacheToFile - WaitForBucketWriteComplete failed.\n";
LABEL_19:
      CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)v4, v3);
      return v2;
    }
  }
  *((_OWORD *)this + 15) = 0;
  *((_OWORD *)this + 16) = 0;
  *((_OWORD *)this + 17) = 0;
  v5 = *((int *)this + 17);
  v6 = (const void *)*((_QWORD *)this + 7);
  v7 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 33) = *((_QWORD *)this + 29);
  memcpy_0(v7, v6, v5);
  v8 = *(_QWORD *)this;
  v9 = (CompressedStreamDump *)*((int *)this + 17);
  *((_QWORD *)this + 35) = *((_QWORD *)this + 6);
  v11 = CompressedStreamDump::GetPaddingBytes(v9, *(unsigned int *)(v8 + 40), v10) + (_DWORD)v9;
  v13 = *((_QWORD *)this + 2);
  *((_DWORD *)this + 68) = v11;
  v14 = (const char *)_InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 48), v11);
  *((_QWORD *)this + 32) = v14;
  v15 = *((_QWORD *)this + 9);
  if ( (*((_QWORD *)this + 10) - v15) >> 3 )
  {
    v16 = 0;
    do
    {
      if ( (*((_QWORD *)this + 10) - v15) >> 3 <= v16 )
        std::vector<MemoryBucket *>::_Xrange(v16, v15, v14, v12);
      v17 = *(_QWORD *)(v15 + 8 * v16);
      v18 = *(_DWORD *)(v17 + 12);
      if ( !v18 )
        v18 = *(_DWORD *)(v17 + 8);
      *(_QWORD *)(v17 + 16) = v14;
      ++v16;
      v19 = v18;
      v15 = *((_QWORD *)this + 9);
      v14 += v19;
    }
    while ( v16 < (*((_QWORD *)this + 10) - v15) >> 3 );
  }
  v20 = *((_QWORD *)this + 2);
  ++*((_QWORD *)this + 17);
  if ( *(_DWORD *)(v20 + 40) )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DumpWriter:WriteAsync failed because DumpWriter has errors.\n",
      v14);
    goto LABEL_18;
  }
  if ( !WriteFile(
          *(HANDLE *)(v20 + 24),
          *((LPCVOID *)this + 35),
          *((_DWORD *)this + 68),
          0,
          (LPOVERLAPPED)((char *)this + 240)) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      LODWORD(lpOverlapped) = *((_DWORD *)this + 68);
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        (int)"WriteAsync->WriteFile failed with error. GetLastError: %u, Offset: 0x%p, BytesToWrite: %u.\n",
        (const char *)LastError,
        *((_QWORD *)this + 32),
        lpOverlapped);
      ++*(_DWORD *)(v20 + 40);
LABEL_18:
      v2 = 0;
      v4 = "FlushWriteCacheToFile - WriteAsync failed.\n";
      goto LABEL_19;
    }
  }
  ++*((_DWORD *)this + 38);
  v2 = 1;
  v22 = *((_QWORD *)this + 9);
  if ( v22 != *((_QWORD *)this + 10) )
    *((_QWORD *)this + 10) = v22;
  *((_DWORD *)this + 17) = 0;
  return v2;
}

```

## disassembly

```asm
0x180029974  mov     [rsp+arg_0], rbx
0x180029979  mov     [rsp+arg_8], rsi
0x18002997e  push    rdi
0x18002997f  sub     rsp, 30h
0x180029983  cmp     dword ptr [rcx+98h], 0
0x18002998a  mov     rdi, rcx
0x18002998d  jle     short loc_1800299A6
0x18002998f  call    ?WaitForBucketWriteComplete@ParallelDumpTask@CompressedStreamDump@@QEAA_NXZ; CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(void)
0x180029994  mov     bl, al
0x180029996  test    al, al
0x180029998  jnz     short loc_1800299A6
0x18002999a  lea     rdx, aFlushwritecach_0; "FlushWriteCacheToFile - WaitForBucketWr"...
0x1800299a1  jmp     loc_180029B05
0x1800299a6  xorps   xmm0, xmm0
0x1800299a9  lea     rsi, [rdi+0F0h]
0x1800299b0  movups  xmmword ptr [rsi], xmm0
0x1800299b3  movups  xmmword ptr [rsi+10h], xmm0
0x1800299b7  movups  xmmword ptr [rsi+20h], xmm0
0x1800299bb  mov     rax, [rdi+0E8h]
0x1800299c2  movsxd  r8, dword ptr [rdi+44h]; Size
0x1800299c6  mov     rdx, [rdi+38h]; Src
0x1800299ca  mov     rcx, [rdi+30h]; void *
0x1800299ce  mov     [rdi+108h], rax
0x1800299d5  call    memcpy_0
0x1800299da  mov     rdx, [rdi]
0x1800299dd  mov     rax, [rdi+30h]
0x1800299e1  movsxd  rbx, dword ptr [rdi+44h]
0x1800299e5  mov     [rdi+118h], rax
0x1800299ec  mov     rcx, rbx; this
0x1800299ef  mov     edx, [rdx+28h]; unsigned __int64
0x1800299f2  call    ?GetPaddingBytes@CompressedStreamDump@@YAI_KI@Z; CompressedStreamDump::GetPaddingBytes(unsigned __int64,uint)
0x1800299f7  lea     ecx, [rax+rbx]
0x1800299fa  mov     rax, [rdi+10h]
0x1800299fe  mov     [rdi+110h], ecx
0x180029a04  mov     r8d, ecx
0x180029a07  lock xadd [rax+30h], r8
0x180029a0d  mov     [rdi+100h], r8
0x180029a14  mov     rdx, [rdi+48h]
0x180029a18  mov     rax, [rdi+50h]
0x180029a1c  sub     rax, rdx
0x180029a1f  sar     rax, 3
0x180029a23  test    rax, rax
0x180029a26  jz      short loc_180029A6C
0x180029a28  xor     ecx, ecx
0x180029a2a  mov     rax, [rdi+50h]
0x180029a2e  sub     rax, rdx
0x180029a31  sar     rax, 3
0x180029a35  cmp     rax, rcx
0x180029a38  jbe     loc_180029B21
0x180029a3e  mov     rax, [rdx+rcx*8]
0x180029a42  mov     edx, [rax+0Ch]
0x180029a45  test    edx, edx
0x180029a47  jnz     short loc_180029A4C
0x180029a49  mov     edx, [rax+8]
0x180029a4c  mov     [rax+10h], r8
0x180029a50  inc     rcx
0x180029a53  mov     eax, edx
0x180029a55  mov     rdx, [rdi+48h]
0x180029a59  add     r8, rax; char *
0x180029a5c  mov     rax, [rdi+50h]
0x180029a60  sub     rax, rdx
0x180029a63  sar     rax, 3
0x180029a67  cmp     rcx, rax
0x180029a6a  jb      short loc_180029A2A
0x180029a6c  mov     rbx, [rdi+10h]
0x180029a70  inc     qword ptr [rdi+88h]
0x180029a77  cmp     dword ptr [rbx+28h], 0
0x180029a7b  jnz     short loc_180029AEB
0x180029a7d  mov     r8d, [rsi+20h]; nNumberOfBytesToWrite
0x180029a81  xor     r9d, r9d; lpNumberOfBytesWritten
0x180029a84  mov     rdx, [rsi+28h]; lpBuffer
0x180029a88  mov     rcx, [rbx+18h]; hFile
0x180029a8c  mov     [rsp+38h+lpOverlapped], rsi; lpOverlapped
0x180029a91  call    cs:__imp_WriteFile
0x180029a97  test    eax, eax
0x180029a99  jnz     short loc_180029AAB
0x180029a9b  call    cs:__imp_GetLastError
0x180029aa1  mov     r8d, eax; char *
0x180029aa4  cmp     eax, 3E5h
0x180029aa9  jnz     short loc_180029ACA
0x180029aab  inc     dword ptr [rdi+98h]
0x180029ab1  mov     bl, 1
0x180029ab3  mov     rax, [rdi+48h]
0x180029ab7  cmp     rax, [rdi+50h]
0x180029abb  jz      short loc_180029AC1
0x180029abd  mov     [rdi+50h], rax
0x180029ac1  mov     dword ptr [rdi+44h], 0
0x180029ac8  jmp     short loc_180029B0F
0x180029aca  mov     eax, [rsi+20h]
0x180029acd  lea     rdx, aWriteasyncWrit; "WriteAsync->WriteFile failed with error"...
0x180029ad4  mov     r9, [rsi+10h]
0x180029ad8  mov     ecx, 4; this
0x180029add  mov     dword ptr [rsp+38h+lpOverlapped], eax
0x180029ae1  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029ae6  inc     dword ptr [rbx+28h]
0x180029ae9  jmp     short loc_180029AFC
0x180029aeb  lea     rdx, aDumpwriterWrit; "DumpWriter:WriteAsync failed because Du"...
0x180029af2  mov     ecx, 4; this
0x180029af7  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029afc  xor     bl, bl
0x180029afe  lea     rdx, aFlushwritecach; "FlushWriteCacheToFile - WriteAsync fail"...
0x180029b05  mov     ecx, 4; this
0x180029b0a  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029b0f  mov     rsi, [rsp+38h+arg_8]
0x180029b14  mov     al, bl
0x180029b16  mov     rbx, [rsp+38h+arg_0]
0x180029b1b  add     rsp, 30h
0x180029b1f  pop     rdi
0x180029b20  retn
0x180029b21  call    ?_Xrange@?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@CAXXZ; std::vector<MemoryBucket *>::_Xrange(void)
```
