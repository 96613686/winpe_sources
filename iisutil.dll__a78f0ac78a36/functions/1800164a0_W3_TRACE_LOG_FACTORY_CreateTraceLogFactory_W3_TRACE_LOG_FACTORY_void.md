# W3_TRACE_LOG_FACTORY::CreateTraceLogFactory(W3_TRACE_LOG_FACTORY * *,void *)

- ea: `0x1800164a0`
- end: `0x180016580`
- name: `?CreateTraceLogFactory@W3_TRACE_LOG_FACTORY@@SAJPEAPEAV1@PEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct W3_TRACE_LOG_FACTORY **, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800164a0`
- `0x180016590`
- `0x1800183f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001654a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001654a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180016500`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180016500`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180016540`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180016540`

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
0x1800164a0  push    rbx
0x1800164a2  push    rbp
0x1800164a3  push    rsi
0x1800164a4  push    rdi
0x1800164a5  sub     rsp, 48h
0x1800164a9  mov     rbx, rcx
0x1800164ac  mov     qword ptr [rcx], 0
0x1800164b3  mov     ecx, 78h ; 'x'; Size
0x1800164b8  mov     rbp, rdx
0x1800164bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800164c0  mov     rdi, rax
0x1800164c3  test    rax, rax
0x1800164c6  jz      loc_180016570
0x1800164cc  add     rax, 18h
0x1800164d0  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800164d4  mov     edx, 800003E8h; dwSpinCount
0x1800164d9  mov     dword ptr [rax+28h], 20h ; ' '
0x1800164e0  mov     qword ptr [rax], 0
0x1800164e7  mov     [rax+20h], rax
0x1800164eb  mov     word ptr [rax+2Ch], 100h
0x1800164f1  mov     dword ptr [rdi+70h], 0
0x1800164f8  mov     qword ptr [rdi+8], 0
0x180016500  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180016506  test    eax, eax
0x180016508  jz      short loc_18001654A
0x18001650a  mov     eax, 7530h
0x18001650f  mov     [rsp+68h+Flags], 10h; Flags
0x180016517  mov     [rsp+68h+Period], eax; Period
0x18001651b  lea     r8, ?TimerCallback@W3_TRACE_LOG_FACTORY@@CAXPEAXE@Z; Callback
0x180016522  mov     r9, rdi; Parameter
0x180016525  mov     [rsp+68h+DueTime], eax; DueTime
0x180016529  xor     edx, edx; TimerQueue
0x18001652b  mov     dword ptr [rdi+70h], 1
0x180016532  lea     rcx, [rdi+8]; phNewTimer
0x180016536  mov     [rdi], rbp
0x180016539  mov     dword ptr [rdi+10h], 0
0x180016540  call    cs:__imp_CreateTimerQueueTimer
0x180016546  test    eax, eax
0x180016548  jnz     short loc_180016569
0x18001654a  call    cs:__imp_GetLastError
0x180016550  mov     ebx, eax
0x180016552  test    eax, eax
0x180016554  jle     short loc_18001655F
0x180016556  movzx   ebx, ax
0x180016559  or      ebx, 80070000h
0x18001655f  mov     rcx, rdi; this
0x180016562  call    ?DestroyTraceLogFactory@W3_TRACE_LOG_FACTORY@@QEAAXXZ; W3_TRACE_LOG_FACTORY::DestroyTraceLogFactory(void)
0x180016567  jmp     short loc_180016575
0x180016569  mov     [rbx], rdi
0x18001656c  xor     ebx, ebx
0x18001656e  jmp     short loc_180016575
0x180016570  mov     ebx, 80070008h
0x180016575  mov     eax, ebx
0x180016577  add     rsp, 48h
0x18001657b  pop     rdi
0x18001657c  pop     rsi
0x18001657d  pop     rbp
0x18001657e  pop     rbx
0x18001657f  retn
```
