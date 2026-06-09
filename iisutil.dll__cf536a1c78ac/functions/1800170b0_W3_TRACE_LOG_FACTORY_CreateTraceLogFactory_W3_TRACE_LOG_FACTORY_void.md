# W3_TRACE_LOG_FACTORY::CreateTraceLogFactory(W3_TRACE_LOG_FACTORY * *,void *)

- ea: `0x1800170b0`
- end: `0x1800171a3`
- name: `?CreateTraceLogFactory@W3_TRACE_LOG_FACTORY@@SAJPEAPEAV1@PEAX@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct W3_TRACE_LOG_FACTORY **, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800170b0`
- `0x1800171b0`
- `0x180019230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017166`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180017110`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180017110`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180017156`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180017156`

## pseudocode

```c
__int64 __fastcall W3_TRACE_LOG_FACTORY::CreateTraceLogFactory(struct W3_TRACE_LOG_FACTORY **a1, void *a2)
{
  char *v4; // rax
  char *v5; // rdi
  char *v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx

  *a1 = 0;
  v4 = (char *)operator new(0x78u);
  v5 = v4;
  if ( v4 )
  {
    v6 = v4 + 24;
    *((_DWORD *)v6 + 10) = 32;
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 4) = v6;
    *((_WORD *)v6 + 22) = 256;
    *((_DWORD *)v5 + 28) = 0;
    *((_QWORD *)v5 + 1) = 0;
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v5 + 72), 0x800003E8)
      && (*((_DWORD *)v5 + 28) = 1,
          *(_QWORD *)v5 = a2,
          *((_DWORD *)v5 + 4) = 0,
          CreateTimerQueueTimer((PHANDLE)v5 + 1, 0, W3_TRACE_LOG_FACTORY::TimerCallback, v5, 0x7530u, 0x7530u, 0x10u)) )
    {
      *a1 = (struct W3_TRACE_LOG_FACTORY *)v5;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      W3_TRACE_LOG_FACTORY::DestroyTraceLogFactory((W3_TRACE_LOG_FACTORY *)v5);
    }
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return v8;
}

```

## disassembly

```asm
0x1800170b0  push    rbx
0x1800170b2  push    rbp
0x1800170b3  push    rsi
0x1800170b4  push    rdi
0x1800170b5  sub     rsp, 48h
0x1800170b9  mov     rbx, rcx
0x1800170bc  mov     qword ptr [rcx], 0
0x1800170c3  mov     ecx, 78h ; 'x'; Size
0x1800170c8  mov     rbp, rdx
0x1800170cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800170d0  mov     rdi, rax
0x1800170d3  test    rax, rax
0x1800170d6  jz      loc_180017192
0x1800170dc  add     rax, 18h
0x1800170e0  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800170e4  mov     edx, 800003E8h; dwSpinCount
0x1800170e9  mov     dword ptr [rax+28h], 20h ; ' '
0x1800170f0  mov     qword ptr [rax], 0
0x1800170f7  mov     [rax+20h], rax
0x1800170fb  mov     word ptr [rax+2Ch], 100h
0x180017101  mov     dword ptr [rdi+70h], 0
0x180017108  mov     qword ptr [rdi+8], 0
0x180017110  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180017117  nop     dword ptr [rax+rax+00h]
0x18001711c  test    eax, eax
0x18001711e  jz      short loc_180017166
0x180017120  mov     eax, 7530h
0x180017125  mov     [rsp+68h+Flags], 10h; Flags
0x18001712d  mov     [rsp+68h+Period], eax; Period
0x180017131  lea     r8, ?TimerCallback@W3_TRACE_LOG_FACTORY@@CAXPEAXE@Z; Callback
0x180017138  mov     r9, rdi; Parameter
0x18001713b  mov     [rsp+68h+DueTime], eax; DueTime
0x18001713f  xor     edx, edx; TimerQueue
0x180017141  mov     dword ptr [rdi+70h], 1
0x180017148  lea     rcx, [rdi+8]; phNewTimer
0x18001714c  mov     [rdi], rbp
0x18001714f  mov     dword ptr [rdi+10h], 0
0x180017156  call    cs:__imp_CreateTimerQueueTimer
0x18001715d  nop     dword ptr [rax+rax+00h]
0x180017162  test    eax, eax
0x180017164  jnz     short loc_18001718B
0x180017166  call    cs:__imp_GetLastError
0x18001716d  nop     dword ptr [rax+rax+00h]
0x180017172  mov     ebx, eax
0x180017174  test    eax, eax
0x180017176  jle     short loc_180017181
0x180017178  movzx   ebx, ax
0x18001717b  or      ebx, 80070000h
0x180017181  mov     rcx, rdi; this
0x180017184  call    ?DestroyTraceLogFactory@W3_TRACE_LOG_FACTORY@@QEAAXXZ; W3_TRACE_LOG_FACTORY::DestroyTraceLogFactory(void)
0x180017189  jmp     short loc_180017197
0x18001718b  mov     [rbx], rdi
0x18001718e  xor     ebx, ebx
0x180017190  jmp     short loc_180017197
0x180017192  mov     ebx, 80070008h
0x180017197  mov     eax, ebx
0x180017199  add     rsp, 48h
0x18001719d  pop     rdi
0x18001719e  pop     rsi
0x18001719f  pop     rbp
0x1800171a0  pop     rbx
0x1800171a1  retn
```
