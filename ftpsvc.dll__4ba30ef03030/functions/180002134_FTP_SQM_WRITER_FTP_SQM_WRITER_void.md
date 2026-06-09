# FTP_SQM_WRITER::~FTP_SQM_WRITER(void)

- ea: `0x180002134`
- end: `0x1800021af`
- name: `??1FTP_SQM_WRITER@@UEAA@XZ`
- size: `123`
- prototype: `void __fastcall(FTP_SQM_WRITER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002400`

## callees

- `0x180002134`
- `0x18001eea4`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18000216f`
- `ntdll!WinSqmSetDWORD` at `0x180002180`
- `ntdll!WinSqmSetDWORD` at `0x180002191`
- `ntdll!WinSqmSetDWORD` at `0x18000216f`
- `ntdll!WinSqmSetDWORD` at `0x180002180`
- `ntdll!WinSqmSetDWORD` at `0x180002191`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180002156`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180002156`
- `KERNEL32!DeleteCriticalSection` at `0x1800021a8`

## pseudocode

```c
void __fastcall FTP_SQM_WRITER::~FTP_SQM_WRITER(FTP_SQM_WRITER *this)
{
  void *v1; // rdx
  __int64 v3; // r8

  v1 = (void *)*((_QWORD *)this + 9);
  *(_QWORD *)this = &FTP_SQM_WRITER::`vftable';
  if ( v1 )
  {
    DeleteTimerQueueTimer(0, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v3 = *((unsigned int *)this + 2);
    *((_QWORD *)this + 9) = 0;
    WinSqmSetDWORD(0, 9000, v3);
    WinSqmSetDWORD(0, 9002, *((unsigned int *)this + 3));
    WinSqmSetDWORD(0, 9001, *((unsigned int *)this + 4));
    FTP_SQM_WRITER::WriteTraceLoggingRuntimeData(this);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
}

```

## disassembly

```asm
0x180002134  push    rbx
0x180002136  sub     rsp, 20h
0x18000213a  mov     rdx, [rcx+48h]; Timer
0x18000213e  lea     rax, ??_7FTP_SQM_WRITER@@6B@; const FTP_SQM_WRITER::`vftable'
0x180002145  mov     [rcx], rax
0x180002148  mov     rbx, rcx
0x18000214b  test    rdx, rdx
0x18000214e  jz      short loc_18000219F
0x180002150  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180002154  xor     ecx, ecx; TimerQueue
0x180002156  call    cs:__imp_DeleteTimerQueueTimer
0x18000215c  mov     r8d, [rbx+8]
0x180002160  mov     edx, 2328h
0x180002165  xor     ecx, ecx
0x180002167  mov     qword ptr [rbx+48h], 0
0x18000216f  call    cs:__imp_WinSqmSetDWORD
0x180002175  mov     r8d, [rbx+0Ch]
0x180002179  mov     edx, 232Ah
0x18000217e  xor     ecx, ecx
0x180002180  call    cs:__imp_WinSqmSetDWORD
0x180002186  mov     r8d, [rbx+10h]
0x18000218a  mov     edx, 2329h
0x18000218f  xor     ecx, ecx
0x180002191  call    cs:__imp_WinSqmSetDWORD
0x180002197  mov     rcx, rbx; this
0x18000219a  call    ?WriteTraceLoggingRuntimeData@FTP_SQM_WRITER@@QEAAXXZ; FTP_SQM_WRITER::WriteTraceLoggingRuntimeData(void)
0x18000219f  lea     rcx, [rbx+20h]
0x1800021a3  add     rsp, 20h
0x1800021a7  pop     rbx
0x1800021a8  jmp     cs:__imp_DeleteCriticalSection
```
