# CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream(void)

- ea: `0x18001ddd8`
- end: `0x18001df6b`
- name: `?AppendCompressedMemoryStream@CompressedMemStream@CompressedStreamDump@@QEAA_NXZ`
- size: `403`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *this, __int64, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d6f4`

## callees

- `0x18001ddd8`
- `0x18001e028`
- `0x18001e114`
- `0x18001e804`
- `0x18001ee10`
- `0x18001f14c`
- `0x1800289b8`

## string_xrefs

- `0x18001df07`: `ExecuteParallelDumpTasks failed.\n`
- `0x18001df28`: `WriteCompressedStreamMetaData failed.\n`
- `0x18001df45`: `Appended CompressedMemoryStream to dump successfully.\n`

## pseudocode

```c
bool __fastcall CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream(
        CompressedStreamDump::CompressedMemStream *this,
        __int64 a2,
        const char *a3)
{
  __int64 v4; // rdx
  bool result; // al
  __int64 v6; // r10
  __int64 v7; // r9
  unsigned __int64 i; // r8
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  const char *v11; // r8
  const char *v12; // r8
  const char *v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  const std::bad_alloc *v16; // [rsp+28h] [rbp-20h] BYREF
  const std::exception *v17; // [rsp+30h] [rbp-18h] BYREF

  if ( *((_QWORD *)this + 10) != *((_QWORD *)this + 11) )
    CompressedStreamDump::CompressedMemStream::FlushCachedRegionsToStorage(this);
  v4 = *((_QWORD *)this + 39);
  if ( v4 == *((_QWORD *)this + 40) )
  {
    CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"Memory bucket list is empty!\n", a3);
    return 0;
  }
  v6 = *(unsigned int *)(v4 + 8);
  v7 = *(unsigned int *)(v4 + 32);
  for ( i = 1; ; ++i )
  {
    v9 = 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 40) - v4) >> 3);
    if ( i >= v9 )
      break;
    if ( *(_QWORD *)(v4 + 40 * i) != i )
      goto LABEL_11;
    v10 = i - 1;
    if ( v9 <= i - 1 )
      std::vector<MemoryBucket *>::_Xrange(v10, v4, i, v7, -2);
    if ( *(_QWORD *)(v4 + 40 * i + 24) != *(_QWORD *)(v4 + 40 * v10 + 24) + *(unsigned int *)(v4 + 40 * v10 + 32) )
    {
LABEL_11:
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        (int)"Memory bucket %zu has invalid content.\n",
        (const char *)i,
        v7,
        -2);
      return 0;
    }
    v6 += *(unsigned int *)(v4 + 40 * i + 8);
    v7 += *(unsigned int *)(v4 + 40 * i + 32);
  }
  if ( v6 != *((_QWORD *)this + 44) )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Total bucket size is not equal to total region size!\n",
      (const char *)i,
      v7,
      -2);
    return 0;
  }
  if ( v7 != *((_QWORD *)this + 43) )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"Total memory region count in buckets is not equal to total region count!\n",
      (const char *)i);
    return 0;
  }
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"Generated %zu memory buckets.\n",
    (const char *)(0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)this + 40) - v4) >> 3)));
  try
  {
    if ( CompressedStreamDump::CompressedMemStream::ExecuteParallelDumpTasks(this) )
    {
      if ( CompressedStreamDump::CompressedMemStream::WriteCompressedStreamMetaData(this) )
      {
        CompressedStreamDump::CompressedMemStream::DumpStreamHeader(this);
        CompressedStreamDump::LogMessage(
          (CompressedStreamDump *)1,
          (int)"Appended CompressedMemoryStream to dump successfully.\n",
          v13);
        result = 1;
      }
      else
      {
        CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"WriteCompressedStreamMetaData failed.\n", v12);
        result = 0;
      }
    }
    else
    {
      CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"ExecuteParallelDumpTasks failed.\n", v11);
      result = 0;
    }
  }
  catch ( const std::bad_alloc *v16 )
  {
    v14 = (*(__int64 (__fastcall **)(const std::bad_alloc *))(*(_QWORD *)v16 + 8LL))(v16);
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"%s: memory allocation error: %s.\n",
      "AppendCompressedMemoryStream",
      v14);
    return 0;
  }
  catch ( const std::exception *v17 )
  {
    v15 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v17 + 8LL))(v17);
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"%s: standard exception: %s.\n",
      "AppendCompressedMemoryStream",
      v15);
    return 0;
  }
  catch ( ... )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"%s: unknown exception occured.\n",
      "AppendCompressedMemoryStream");
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001ddd8  push    rbx
0x18001ddda  sub     rsp, 40h
0x18001ddde  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001dde7  mov     rbx, rcx
0x18001ddea  mov     rax, [rcx+58h]
0x18001ddee  cmp     [rcx+50h], rax
0x18001ddf2  jz      short loc_18001DDF9
0x18001ddf4  call    ?FlushCachedRegionsToStorage@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::CompressedMemStream::FlushCachedRegionsToStorage(void)
0x18001ddf9  mov     rdx, [rbx+138h]
0x18001de00  cmp     rdx, [rbx+140h]
0x18001de07  jnz     short loc_18001DE21
0x18001de09  lea     rdx, aMemoryBucketLi; "Memory bucket list is empty!\n"
0x18001de10  mov     ecx, 4; this
0x18001de15  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001de1a  xor     al, al
0x18001de1c  jmp     loc_18001DF5C
0x18001de21  mov     r10d, [rdx+8]
0x18001de25  mov     r9d, [rdx+20h]
0x18001de29  mov     r8d, 1; char *
0x18001de2f  mov     rax, [rbx+140h]
0x18001de36  sub     rax, rdx
0x18001de39  sar     rax, 3
0x18001de3d  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18001de47  imul    rax, rcx
0x18001de4b  cmp     r8, rax
0x18001de4e  jnb     short loc_18001DEA8
0x18001de50  lea     r11, [r8+r8*4]
0x18001de54  cmp     [rdx+r11*8], r8
0x18001de58  jnz     short loc_18001DE90
0x18001de5a  lea     rcx, [r8-1]
0x18001de5e  cmp     rax, rcx
0x18001de61  jbe     loc_18001DF64
0x18001de67  lea     rcx, [rcx+rcx*4]
0x18001de6b  mov     eax, [rdx+rcx*8+20h]
0x18001de6f  add     rax, [rdx+rcx*8+18h]
0x18001de74  cmp     [rdx+r11*8+18h], rax
0x18001de79  jnz     short loc_18001DE90
0x18001de7b  mov     eax, [rdx+r11*8+8]
0x18001de80  add     r10, rax
0x18001de83  mov     eax, [rdx+r11*8+20h]
0x18001de88  add     r9, rax
0x18001de8b  inc     r8
0x18001de8e  jmp     short loc_18001DE2F
0x18001de90  lea     rdx, aMemoryBucketZu; "Memory bucket %zu has invalid content."...
0x18001de97  mov     ecx, 4; this
0x18001de9c  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001dea1  xor     al, al
0x18001dea3  jmp     loc_18001DF5C
0x18001dea8  cmp     r10, [rbx+160h]
0x18001deaf  jz      short loc_18001DEC9
0x18001deb1  lea     rdx, aTotalBucketSiz; "Total bucket size is not equal to total"...
0x18001deb8  mov     ecx, 4; this
0x18001debd  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001dec2  xor     al, al
0x18001dec4  jmp     loc_18001DF5C
0x18001dec9  cmp     r9, [rbx+158h]
0x18001ded0  jz      short loc_18001DEE7
0x18001ded2  lea     rdx, aTotalMemoryReg; "Total memory region count in buckets is"...
0x18001ded9  mov     ecx, 4; this
0x18001dede  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001dee3  xor     al, al
0x18001dee5  jmp     short loc_18001DF5C
0x18001dee7  mov     r8, rax; char *
0x18001deea  lea     rdx, aGeneratedZuMem; "Generated %zu memory buckets.\n"
0x18001def1  mov     ecx, 1; this
0x18001def6  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001defb  mov     rcx, rbx; this
0x18001defe  call    ?ExecuteParallelDumpTasks@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::CompressedMemStream::ExecuteParallelDumpTasks(void)
0x18001df03  test    al, al
0x18001df05  jnz     short loc_18001DF1C
0x18001df07  lea     rdx, aExecuteparalle; "ExecuteParallelDumpTasks failed.\n"
0x18001df0e  mov     ecx, 4; this
0x18001df13  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001df18  xor     al, al
0x18001df1a  jmp     short loc_18001DF5C
0x18001df1c  mov     rcx, rbx; this
0x18001df1f  call    ?WriteCompressedStreamMetaData@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::CompressedMemStream::WriteCompressedStreamMetaData(void)
0x18001df24  test    al, al
0x18001df26  jnz     short loc_18001DF3D
0x18001df28  lea     rdx, aWritecompresse_0; "WriteCompressedStreamMetaData failed.\n"
0x18001df2f  mov     ecx, 4; this
0x18001df34  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001df39  xor     al, al
0x18001df3b  jmp     short loc_18001DF5C
0x18001df3d  mov     rcx, rbx; this
0x18001df40  call    ?DumpStreamHeader@CompressedMemStream@CompressedStreamDump@@AEAAXXZ; CompressedStreamDump::CompressedMemStream::DumpStreamHeader(void)
0x18001df45  lea     rdx, aAppendedCompre; "Appended CompressedMemoryStream to dump"...
0x18001df4c  mov     ecx, 1; this
0x18001df51  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001df56  mov     al, 1
0x18001df58  jmp     short loc_18001DF5C
0x18001df5a  xor     al, al
0x18001df5c  add     rsp, 40h
0x18001df60  pop     rbx
0x18001df61  retn
0x18001df62  jmp     short loc_18001DF5A
0x18001df64  call    ?_Xrange@?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@CAXXZ; std::vector<MemoryBucket *>::_Xrange(void)
```
