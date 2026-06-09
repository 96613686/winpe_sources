# std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>,std::allocator<std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>>>>::_Change_array(std::unique_ptr<CompressedStreamDump::ParallelDumpTask,std::default_delete<CompressedStreamDump::ParallelDumpTask>> * const,unsigned __int64,unsigned __int64)

- ea: `0x18001f04c`
- end: `0x18001f105`
- name: `?_Change_array@?$vector@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@V?$allocator@V?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VParallelDumpTask@CompressedStreamDump@@U?$default_delete@VParallelDumpTask@CompressedStreamDump@@@std@@@2@_K1@Z`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d478`
- `0x18001e114`

## callees

- `0x180001ae0`
- `0x18001d9ac`
- `0x18001f04c`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<CompressedStreamDump::ParallelDumpTask>>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  CompressedStreamDump::ParallelDumpTask **v4; // rdi
  CompressedStreamDump::ParallelDumpTask **v9; // rbp
  CompressedStreamDump::ParallelDumpTask *v10; // rsi
  CompressedStreamDump::ParallelDumpTask **v11; // rcx
  CompressedStreamDump::ParallelDumpTask **v12; // rax
  __int64 result; // rax

  v4 = *(CompressedStreamDump::ParallelDumpTask ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(CompressedStreamDump::ParallelDumpTask ***)(a1 + 8);
    while ( v4 != v9 )
    {
      v10 = *v4;
      if ( *v4 )
      {
        CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(*v4);
        operator delete(v10);
      }
      ++v4;
    }
    v11 = *(CompressedStreamDump::ParallelDumpTask ***)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v12 = *(CompressedStreamDump::ParallelDumpTask ***)a1;
    }
    else
    {
      v12 = (CompressedStreamDump::ParallelDumpTask **)*(v11 - 1);
      if ( (unsigned __int64)((char *)v11 - (char *)v12 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v12);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 8 * a3;
  result = a2 + 8 * a4;
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x18001f04c  push    rbx
0x18001f04e  push    rbp
0x18001f04f  push    rsi
0x18001f050  push    rdi
0x18001f051  push    r12
0x18001f053  push    r14
0x18001f055  push    r15
0x18001f057  sub     rsp, 20h
0x18001f05b  mov     rdi, [rcx]
0x18001f05e  mov     r15, r9
0x18001f061  mov     r12, r8
0x18001f064  mov     r14, rdx
0x18001f067  mov     rbx, rcx
0x18001f06a  test    rdi, rdi
0x18001f06d  jz      short loc_18001F0E3
0x18001f06f  mov     rbp, [rcx+8]
0x18001f073  jmp     short loc_18001F096
0x18001f075  mov     rsi, [rdi]
0x18001f078  test    rsi, rsi
0x18001f07b  jz      short loc_18001F092
0x18001f07d  mov     rcx, rsi; this
0x18001f080  call    ??1ParallelDumpTask@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::ParallelDumpTask::~ParallelDumpTask(void)
0x18001f085  mov     edx, 158h; unsigned __int64
0x18001f08a  mov     rcx, rsi; void *
0x18001f08d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f092  add     rdi, 8
0x18001f096  cmp     rdi, rbp
0x18001f099  jnz     short loc_18001F075
0x18001f09b  mov     rcx, [rbx]
0x18001f09e  mov     rax, [rbx+10h]
0x18001f0a2  sub     rax, rcx
0x18001f0a5  sar     rax, 3
0x18001f0a9  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001f0b1  cmp     rdx, 1000h
0x18001f0b8  jb      short loc_18001F0D8
0x18001f0ba  mov     rax, [rcx-8]
0x18001f0be  sub     rcx, rax
0x18001f0c1  sub     rcx, 8
0x18001f0c5  cmp     rcx, 1Fh
0x18001f0c9  ja      short loc_18001F0D1
0x18001f0cb  add     rdx, 27h ; '''
0x18001f0cf  jmp     short loc_18001F0DB
0x18001f0d1  mov     ecx, 5
0x18001f0d6  int     29h; Win8: RtlFailFast(ecx)
0x18001f0d8  mov     rax, rcx
0x18001f0db  mov     rcx, rax; void *
0x18001f0de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f0e3  lea     rax, [r14+r12*8]
0x18001f0e7  mov     [rbx], r14
0x18001f0ea  mov     [rbx+8], rax
0x18001f0ee  lea     rax, [r14+r15*8]
0x18001f0f2  mov     [rbx+10h], rax
0x18001f0f6  add     rsp, 20h
0x18001f0fa  pop     r15
0x18001f0fc  pop     r14
0x18001f0fe  pop     r12
0x18001f100  pop     rdi
0x18001f101  pop     rsi
0x18001f102  pop     rbp
0x18001f103  pop     rbx
0x18001f104  retn
```
