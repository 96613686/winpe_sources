# CompressedStreamDump::ParallelDumpTask::Execute(void)

- ea: `0x18002978c`
- end: `0x18002996c`
- name: `?Execute@ParallelDumpTask@CompressedStreamDump@@QEAA_NXZ`
- size: `480`
- prototype: `char __fastcall(CompressedStreamDump::ParallelDumpTask *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800296d0`

## callees

- `0x180002210`
- `0x180003424`
- `0x18001f14c`
- `0x1800289b8`
- `0x18002956c`
- `0x18002978c`
- `0x180029974`
- `0x180029d68`
- `0x180029ff8`

## string_xrefs

- `0x180029881`: `Compression failed to compress the bucket. id: %I64u,  size: %u. Compression error count: %u.\n`
- `0x180029934`: `Task %d-Bucket processed: %I64u, %I64u bytes.\n`

## pseudocode

```c
char __fastcall CompressedStreamDump::ParallelDumpTask::Execute(
        CompressedStreamDump::ParallelDumpTask *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rbp
  char Bucket; // di
  unsigned __int64 *v7; // rax
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rsi
  unsigned int v12; // ecx
  unsigned int v13; // r9d
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-38h]

  v4 = 0;
  Bucket = 1;
  if ( *((_QWORD *)this + 22) )
  {
    while ( 1 )
    {
      v7 = (unsigned __int64 *)*((_QWORD *)this + 20);
      v8 = v4 + *((_QWORD *)this + 21);
      v9 = *v7;
      v10 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v7[1] - *v7) >> 3);
      if ( v10 <= v8 )
        std::vector<MemoryBucket *>::_Xrange(v10, v8, v9, a4, v16);
      v11 = v9 + 40 * v8;
      Bucket = CompressedStreamDump::ParallelDumpTask::ReadBucket(this, (struct MemoryBucket *)v11, v9, a4);
      if ( !Bucket )
        break;
      v12 = *((_DWORD *)this + 6);
      if ( v12 <= 0x7E000000 )
        v13 = v12 / 0xFF + v12 + 16;
      else
        v13 = 0;
      v14 = LZ4_compress_fast(*((_QWORD *)this + 4), *((_QWORD *)this + 5), *(_DWORD *)(v11 + 8), v13, 1);
      if ( v14 <= *((_DWORD *)this + 6) )
      {
        if ( v14 <= 0 )
        {
          memcpy_0(*((void **)this + 5), *((const void **)this + 4), *(unsigned int *)(v11 + 8));
          *((_QWORD *)this + 14) += *(unsigned int *)(v11 + 8);
          *(_DWORD *)(v11 + 12) = 0;
          LODWORD(v16) = ++*((_DWORD *)this + 80);
          CompressedStreamDump::LogMessage(
            (CompressedStreamDump *)4,
            (int)"Compression failed to compress the bucket. id: %I64u,  size: %u. Compression error count: %u.\n",
            *(const char **)v11,
            *(unsigned int *)(v11 + 8));
        }
        else
        {
          *(_DWORD *)(v11 + 12) = v14;
          *((_QWORD *)this + 14) += v14;
        }
      }
      else
      {
        memcpy_0(*((void **)this + 5), *((const void **)this + 4), *(unsigned int *)(v11 + 8));
        *((_QWORD *)this + 14) += *(unsigned int *)(v11 + 8);
        *(_DWORD *)(v11 + 12) = 0;
      }
      *((_QWORD *)this + 15) += *(unsigned int *)(v11 + 32);
      Bucket = 1;
      if ( !CompressedStreamDump::ParallelDumpTask::AddBucketToCache(this, (struct MemoryBucket *)v11) )
      {
        if ( !CompressedStreamDump::ParallelDumpTask::FlushWriteCacheToFile(this) )
        {
          Bucket = 0;
          break;
        }
        Bucket = CompressedStreamDump::ParallelDumpTask::AddBucketToCache(this, (struct MemoryBucket *)v11);
      }
      if ( !Bucket )
        break;
      ++*((_QWORD *)this + 16);
      if ( (unsigned __int64)++v4 >= *((_QWORD *)this + 22) )
        goto LABEL_17;
    }
  }
  else
  {
LABEL_17:
    if ( (*((int *)this + 17) <= 0 || (Bucket = CompressedStreamDump::ParallelDumpTask::FlushWriteCacheToFile(this)) != 0)
      && *((int *)this + 38) > 0 )
    {
      Bucket = CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(this);
    }
  }
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)1,
    (int)"Task %d-Bucket processed: %I64u, %I64u bytes.\n",
    (const char *)*((unsigned int *)this + 24),
    *((_QWORD *)this + 16),
    *((_QWORD *)this + 13));
  return Bucket;
}

```

## disassembly

```asm
0x18002978c  push    rbx
0x18002978e  push    rbp
0x18002978f  push    rsi
0x180029790  push    rdi
0x180029791  sub     rsp, 38h
0x180029795  xor     ebp, ebp
0x180029797  mov     rbx, rcx
0x18002979a  mov     dil, 1
0x18002979d  cmp     [rcx+0B0h], rbp
0x1800297a4  jbe     loc_180029907
0x1800297aa  mov     rax, [rbx+0A0h]
0x1800297b1  mov     rdx, [rbx+0A8h]
0x1800297b8  add     rdx, rbp
0x1800297bb  mov     r8, [rax]
0x1800297be  mov     rcx, [rax+8]
0x1800297c2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800297cc  sub     rcx, r8
0x1800297cf  sar     rcx, 3
0x1800297d3  imul    rcx, rax
0x1800297d7  cmp     rcx, rdx
0x1800297da  jbe     loc_180029966
0x1800297e0  lea     rax, [rdx+rdx*4]
0x1800297e4  mov     rcx, rbx; this
0x1800297e7  lea     rsi, [r8+rax*8]
0x1800297eb  mov     rdx, rsi; struct MemoryBucket *
0x1800297ee  call    ?ReadBucket@ParallelDumpTask@CompressedStreamDump@@QEAA_NPEAUMemoryBucket@@@Z; CompressedStreamDump::ParallelDumpTask::ReadBucket(MemoryBucket *)
0x1800297f3  mov     dil, al
0x1800297f6  test    al, al
0x1800297f8  jz      loc_180029930
0x1800297fe  mov     ecx, [rbx+18h]
0x180029801  cmp     ecx, 7E000000h
0x180029807  jbe     short loc_18002980E
0x180029809  xor     r9d, r9d
0x18002980c  jmp     short loc_18002981F
0x18002980e  mov     eax, 80808081h
0x180029813  lea     r9d, [rcx+10h]
0x180029817  mul     ecx
0x180029819  shr     edx, 7
0x18002981c  add     r9d, edx
0x18002981f  mov     r8d, [rsi+8]
0x180029823  mov     rdx, [rbx+28h]
0x180029827  mov     rcx, [rbx+20h]
0x18002982b  mov     dword ptr [rsp+58h+var_38], 1
0x180029833  call    LZ4_compress_fast
0x180029838  cmp     eax, [rbx+18h]
0x18002983b  jle     short loc_18002985E
0x18002983d  mov     r8d, [rsi+8]; Size
0x180029841  mov     rdx, [rbx+20h]; Src
0x180029845  mov     rcx, [rbx+28h]; void *
0x180029849  call    memcpy_0
0x18002984e  mov     eax, [rsi+8]
0x180029851  add     [rbx+70h], rax
0x180029855  mov     dword ptr [rsi+0Ch], 0
0x18002985c  jmp     short loc_1800298B4
0x18002985e  test    eax, eax
0x180029860  jle     short loc_18002986D
0x180029862  mov     [rsi+0Ch], eax
0x180029865  cdqe
0x180029867  add     [rbx+70h], rax
0x18002986b  jmp     short loc_1800298B4
0x18002986d  mov     r8d, [rsi+8]; Size
0x180029871  mov     rdx, [rbx+20h]; Src
0x180029875  mov     rcx, [rbx+28h]; void *
0x180029879  call    memcpy_0
0x18002987e  mov     eax, [rsi+8]
0x180029881  lea     rdx, aCompressionFai; "Compression failed to compress the buck"...
0x180029888  add     [rbx+70h], rax
0x18002988c  mov     ecx, 4; this
0x180029891  mov     dword ptr [rsi+0Ch], 0
0x180029898  inc     dword ptr [rbx+140h]
0x18002989e  mov     eax, [rbx+140h]
0x1800298a4  mov     r9d, [rsi+8]
0x1800298a8  mov     r8, [rsi]; char *
0x1800298ab  mov     dword ptr [rsp+58h+var_38], eax
0x1800298af  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x1800298b4  mov     eax, [rsi+20h]
0x1800298b7  mov     rdx, rsi; struct MemoryBucket *
0x1800298ba  add     [rbx+78h], rax
0x1800298be  mov     rcx, rbx; this
0x1800298c1  mov     dil, 1
0x1800298c4  call    ?AddBucketToCache@ParallelDumpTask@CompressedStreamDump@@AEAA_NPEAUMemoryBucket@@@Z; CompressedStreamDump::ParallelDumpTask::AddBucketToCache(MemoryBucket *)
0x1800298c9  test    al, al
0x1800298cb  jnz     short loc_1800298EB
0x1800298cd  mov     rcx, rbx; this
0x1800298d0  call    ?FlushWriteCacheToFile@ParallelDumpTask@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::ParallelDumpTask::FlushWriteCacheToFile(void)
0x1800298d5  test    al, al
0x1800298d7  jz      loc_180029961
0x1800298dd  mov     rdx, rsi; struct MemoryBucket *
0x1800298e0  mov     rcx, rbx; this
0x1800298e3  call    ?AddBucketToCache@ParallelDumpTask@CompressedStreamDump@@AEAA_NPEAUMemoryBucket@@@Z; CompressedStreamDump::ParallelDumpTask::AddBucketToCache(MemoryBucket *)
0x1800298e8  mov     dil, al
0x1800298eb  test    dil, dil
0x1800298ee  jz      short loc_180029930
0x1800298f0  inc     qword ptr [rbx+80h]
0x1800298f7  inc     rbp
0x1800298fa  cmp     rbp, [rbx+0B0h]
0x180029901  jb      loc_1800297AA
0x180029907  cmp     dword ptr [rbx+44h], 0
0x18002990b  jle     short loc_18002991C
0x18002990d  mov     rcx, rbx; this
0x180029910  call    ?FlushWriteCacheToFile@ParallelDumpTask@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::ParallelDumpTask::FlushWriteCacheToFile(void)
0x180029915  mov     dil, al
0x180029918  test    al, al
0x18002991a  jz      short loc_180029930
0x18002991c  cmp     dword ptr [rbx+98h], 0
0x180029923  jle     short loc_180029930
0x180029925  mov     rcx, rbx; this
0x180029928  call    ?WaitForBucketWriteComplete@ParallelDumpTask@CompressedStreamDump@@QEAA_NXZ; CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(void)
0x18002992d  mov     dil, al
0x180029930  mov     rax, [rbx+68h]
0x180029934  lea     rdx, aTaskDBucketPro; "Task %d-Bucket processed: %I64u, %I64u "...
0x18002993b  mov     r9, [rbx+80h]
0x180029942  mov     ecx, 1; this
0x180029947  mov     r8d, [rbx+60h]; char *
0x18002994b  mov     [rsp+58h+var_38], rax
0x180029950  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029955  mov     al, dil
0x180029958  add     rsp, 38h
0x18002995c  pop     rdi
0x18002995d  pop     rsi
0x18002995e  pop     rbp
0x18002995f  pop     rbx
0x180029960  retn
0x180029961  xor     dil, dil
0x180029964  jmp     short loc_180029930
0x180029966  call    ?_Xrange@?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@CAXXZ; std::vector<MemoryBucket *>::_Xrange(void)
```
