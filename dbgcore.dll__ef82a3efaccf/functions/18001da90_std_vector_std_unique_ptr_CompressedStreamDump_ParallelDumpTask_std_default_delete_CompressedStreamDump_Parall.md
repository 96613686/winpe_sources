# std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>,std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18001da90`
- end: `0x18001db1e`
- name: `??1_Reallocation_guard@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d478`

## callees

- `0x180001ae0`
- `0x18001d9ac`
- `0x18001da90`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  CompressedStreamDump::ParallelDumpTask **v2; // rbp
  CompressedStreamDump::ParallelDumpTask **i; // rdi
  CompressedStreamDump::ParallelDumpTask *v4; // rsi
  __int64 v5; // rcx
  void *v6; // rax

  if ( a1[1] )
  {
    v2 = (CompressedStreamDump::ParallelDumpTask **)a1[4];
    for ( i = (CompressedStreamDump::ParallelDumpTask **)a1[3]; i != v2; ++i )
    {
      v4 = *i;
      if ( *i )
      {
        CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(*i);
        operator delete(v4);
      }
    }
    v5 = a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v5 - 8);
      if ( (unsigned __int64)(v5 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x18001da90  push    rbx
0x18001da92  push    rbp
0x18001da93  push    rsi
0x18001da94  push    rdi
0x18001da95  sub     rsp, 28h
0x18001da99  cmp     qword ptr [rcx+8], 0
0x18001da9e  mov     rbx, rcx
0x18001daa1  jz      short loc_18001DB15
0x18001daa3  mov     rbp, [rcx+20h]
0x18001daa7  mov     rdi, [rcx+18h]
0x18001daab  jmp     short loc_18001DACE
0x18001daad  mov     rsi, [rdi]
0x18001dab0  test    rsi, rsi
0x18001dab3  jz      short loc_18001DACA
0x18001dab5  mov     rcx, rsi; this
0x18001dab8  call    ??1ParallelDumpTask@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(void)
0x18001dabd  mov     edx, 158h; unsigned __int64
0x18001dac2  mov     rcx, rsi; void *
0x18001dac5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001daca  add     rdi, 8
0x18001dace  cmp     rdi, rbp
0x18001dad1  jnz     short loc_18001DAAD
0x18001dad3  mov     rax, [rbx+10h]
0x18001dad7  mov     rcx, [rbx+8]
0x18001dadb  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001dae3  cmp     rdx, 1000h
0x18001daea  jb      short loc_18001DB0A
0x18001daec  mov     rax, [rcx-8]
0x18001daf0  sub     rcx, rax
0x18001daf3  sub     rcx, 8
0x18001daf7  cmp     rcx, 1Fh
0x18001dafb  ja      short loc_18001DB03
0x18001dafd  add     rdx, 27h ; '''
0x18001db01  jmp     short loc_18001DB0D
0x18001db03  mov     ecx, 5
0x18001db08  int     29h; Win8: RtlFailFast(ecx)
0x18001db0a  mov     rax, rcx
0x18001db0d  mov     rcx, rax; void *
0x18001db10  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001db15  add     rsp, 28h
0x18001db19  pop     rdi
0x18001db1a  pop     rsi
0x18001db1b  pop     rbp
0x18001db1c  pop     rbx
0x18001db1d  retn
```
