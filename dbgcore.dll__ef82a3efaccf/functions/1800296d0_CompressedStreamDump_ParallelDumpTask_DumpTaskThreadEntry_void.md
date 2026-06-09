# CompressedStreamDump::ParallelDumpTask::DumpTaskThreadEntry(void)

- ea: `0x1800296d0`
- end: `0x180029784`
- name: `?DumpTaskThreadEntry@ParallelDumpTask@CompressedStreamDump@@AEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CompressedStreamDump::ParallelDumpTask *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800289b8`
- `0x1800296d0`
- `0x18002978c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800296f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800296f4`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x180029704`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x180029704`

## string_xrefs

- `0x18002971c`: `DumpTask Execute() failed.\n`
- `0x180029754`: `DumpTaskThreadEntry ran into exception. Exception code:%x, address: 0x%p\n`
- `0x180029767`: `DumpTaskThreadEntry ran into exception.\n`

## pseudocode

```c
void __fastcall CompressedStreamDump::ParallelDumpTask::DumpTaskThreadEntry(
        CompressedStreamDump::ParallelDumpTask *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rdi
  HANDLE CurrentThread; // rax
  const char *v7; // r8

  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadGroupAffinity(CurrentThread, (const GROUP_AFFINITY *)(v5 + 24), 0);
  }
  if ( !CompressedStreamDump::ParallelDumpTask::Execute(this, a2, a3, a4) )
  {
    ++*((_DWORD *)this + 39);
    CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"DumpTask Execute() failed.\n", v7);
  }
}

```

## disassembly

```asm
0x1800296d0  mov     [rsp+arg_8], rbx
0x1800296d5  mov     [rsp+arg_0], rcx
0x1800296da  push    rdi
0x1800296db  sub     rsp, 30h
0x1800296df  mov     rbx, rcx
0x1800296e2  mov     [rsp+38h+var_18], 0
0x1800296eb  mov     rdi, [rcx+8]
0x1800296ef  test    rdi, rdi
0x1800296f2  jz      short loc_18002970A
0x1800296f4  call    cs:__imp_GetCurrentThread
0x1800296fa  lea     rdx, [rdi+18h]; GroupAffinity
0x1800296fe  xor     r8d, r8d; PreviousGroupAffinity
0x180029701  mov     rcx, rax; hThread
0x180029704  call    cs:__imp_SetThreadGroupAffinity
0x18002970a  mov     rcx, rbx; this
0x18002970d  call    ?Execute@ParallelDumpTask@CompressedStreamDump@@QEAA_NXZ; CompressedStreamDump::ParallelDumpTask::Execute(void)
0x180029712  test    al, al
0x180029714  jnz     short loc_18002972D
0x180029716  inc     dword ptr [rbx+9Ch]
0x18002971c  lea     rdx, aDumptaskExecut; "DumpTask Execute() failed.\n"
0x180029723  mov     ecx, 4; this
0x180029728  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002972d  jmp     short loc_180029779
0x18002972f  mov     rcx, [rsp+38h+arg_0]
0x180029734  inc     dword ptr [rcx+9Ch]
0x18002973a  mov     r8, [rsp+38h+var_18]; char *
0x18002973f  test    r8, r8
0x180029742  jz      short loc_180029767
0x180029744  cmp     qword ptr [r8], 0
0x180029748  jz      short loc_180029767
0x18002974a  mov     r9, [r8]
0x18002974d  mov     r8d, [r9]; char *
0x180029750  mov     r9, [r9+10h]
0x180029754  lea     rdx, aDumptaskthread; "DumpTaskThreadEntry ran into exception."...
0x18002975b  mov     ecx, 4; this
0x180029760  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029765  jmp     short loc_180029779
0x180029767  lea     rdx, aDumptaskthread_0; "DumpTaskThreadEntry ran into exception."...
0x18002976e  mov     ecx, 4; this
0x180029773  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029778  nop
0x180029779  mov     rbx, [rsp+38h+arg_8]
0x18002977e  add     rsp, 30h
0x180029782  pop     rdi
0x180029783  retn
0x18002b81f  push    rbp
0x18002b821  sub     rsp, 20h
0x18002b825  mov     rbp, rdx
0x18002b828  mov     [rbp+20h], rcx
0x18002b82c  mov     eax, 1
0x18002b831  add     rsp, 20h
0x18002b835  pop     rbp
0x18002b836  retn
```
