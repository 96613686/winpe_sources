# std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>,std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>>>::~vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>,std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>>>(void)

- ea: `0x18001d8f8`
- end: `0x18001d9a4`
- name: `??1?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `172`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e114`
- `0x18002b49c`

## callees

- `0x180001ae0`
- `0x18001d8f8`
- `0x18001d9ac`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::~vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>(
        __int64 a1)
{
  CompressedStreamDump::ParallelDumpTask **v1; // rbx
  CompressedStreamDump::ParallelDumpTask **v3; // rbp
  CompressedStreamDump::ParallelDumpTask *v4; // rsi
  CompressedStreamDump::ParallelDumpTask **v5; // rcx
  CompressedStreamDump::ParallelDumpTask **v6; // rax

  v1 = *(CompressedStreamDump::ParallelDumpTask ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(CompressedStreamDump::ParallelDumpTask ***)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *v1;
      if ( *v1 )
      {
        CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(*v1);
        operator delete(v4);
      }
      ++v1;
    }
    v5 = *(CompressedStreamDump::ParallelDumpTask ***)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v6 = *(CompressedStreamDump::ParallelDumpTask ***)a1;
    }
    else
    {
      v6 = (CompressedStreamDump::ParallelDumpTask **)*(v5 - 1);
      if ( (unsigned __int64)((char *)v5 - (char *)v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001d8f8  push    rbx
0x18001d8fa  push    rbp
0x18001d8fb  push    rsi
0x18001d8fc  push    rdi
0x18001d8fd  sub     rsp, 28h
0x18001d901  mov     rbx, [rcx]
0x18001d904  mov     rdi, rcx
0x18001d907  test    rbx, rbx
0x18001d90a  jz      loc_18001D99B
0x18001d910  mov     rbp, [rcx+8]
0x18001d914  jmp     short loc_18001D937
0x18001d916  mov     rsi, [rbx]
0x18001d919  test    rsi, rsi
0x18001d91c  jz      short loc_18001D933
0x18001d91e  mov     rcx, rsi; this
0x18001d921  call    ??1ParallelDumpTask@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(void)
0x18001d926  mov     edx, 158h; unsigned __int64
0x18001d92b  mov     rcx, rsi; void *
0x18001d92e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d933  add     rbx, 8
0x18001d937  cmp     rbx, rbp
0x18001d93a  jnz     short loc_18001D916
0x18001d93c  mov     rcx, [rdi]
0x18001d93f  mov     rax, [rdi+10h]
0x18001d943  sub     rax, rcx
0x18001d946  sar     rax, 3
0x18001d94a  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001d952  cmp     rdx, 1000h
0x18001d959  jb      short loc_18001D979
0x18001d95b  mov     rax, [rcx-8]
0x18001d95f  sub     rcx, rax
0x18001d962  sub     rcx, 8
0x18001d966  cmp     rcx, 1Fh
0x18001d96a  ja      short loc_18001D972
0x18001d96c  add     rdx, 27h ; '''
0x18001d970  jmp     short loc_18001D97C
0x18001d972  mov     ecx, 5
0x18001d977  int     29h; Win8: RtlFailFast(ecx)
0x18001d979  mov     rax, rcx
0x18001d97c  mov     rcx, rax; void *
0x18001d97f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d984  mov     qword ptr [rdi], 0
0x18001d98b  mov     qword ptr [rdi+8], 0
0x18001d993  mov     qword ptr [rdi+10h], 0
0x18001d99b  add     rsp, 28h
0x18001d99f  pop     rdi
0x18001d9a0  pop     rsi
0x18001d9a1  pop     rbp
0x18001d9a2  pop     rbx
0x18001d9a3  retn
```
