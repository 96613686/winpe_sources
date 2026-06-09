# TIMER::Create(SCHEDULER *,void (*)(void *),void *,ulong,int,int,ulong)

- ea: `0x180016a90`
- end: `0x180016bdc`
- name: `?Create@TIMER@@SAKPEAVSCHEDULER@@P6AXPEAX@Z1KHHK@Z`
- size: `332`
- prototype: `static unsigned int(struct SCHEDULER *, void (*)(void *), void *, unsigned int, int, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016940`
- `0x18001fff0`

## callees

- `0x180016a90`
- `0x180018278`
- `0x1800183f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016bc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016bc9`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180016b7c`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180016b7c`

## pseudocode

```c
__int64 __fastcall TIMER::Create(
        struct SCHEDULER *a1,
        void (*a2)(void *),
        void *a3,
        DWORD a4,
        int a5,
        int a6,
        unsigned int a7)
{
  char *v11; // rax
  char *v12; // rbx
  _DWORD *v13; // rdx
  signed __int32 v14; // eax
  _QWORD *v15; // rax
  __int64 v16; // rcx
  char *v17; // rdi
  unsigned int v18; // edx
  __int64 v19; // rax
  char **v20; // rcx

  v11 = (char *)operator new(0x58u);
  v12 = v11;
  if ( v11 )
  {
    *(_DWORD *)v11 = 1380796756;
    *((_QWORD *)v11 + 1) = a1;
    *((_DWORD *)v11 + 14) = 0;
    _InterlockedIncrement((volatile signed __int32 *)a1 + 6);
    *((_QWORD *)v11 + 3) = a2;
    v13 = v11 + 16;
    *((_QWORD *)v11 + 4) = a3;
    *((_DWORD *)v11 + 10) = a5;
    *((_DWORD *)v11 + 11) = a6;
    *((_DWORD *)v11 + 20) = 0;
    if ( a7 )
    {
      *v13 = a7;
    }
    else
    {
      do
      {
        v14 = _InterlockedExchangeAdd(&TIMER::sm_lLastCookie, 1u);
        *v13 = v14 + 1;
      }
      while ( v14 == -1 );
    }
    v15 = (_QWORD *)((char *)a1 + 32);
    v16 = *((_QWORD *)a1 + 4);
    if ( *(struct SCHEDULER **)(v16 + 8) != (struct SCHEDULER *)((char *)a1 + 32) )
      goto LABEL_11;
    v17 = v12 + 64;
    *((_QWORD *)v12 + 8) = v16;
    *((_QWORD *)v12 + 9) = v15;
    *(_QWORD *)(v16 + 8) = v12 + 64;
    *v15 = v12 + 64;
    if ( CreateTimerQueueTimer(
           (PHANDLE)v12 + 6,
           *(HANDLE *)(*((_QWORD *)v12 + 1) + 8LL),
           TIMER::TimerCallback,
           (PVOID)(unsigned int)*v13,
           a4,
           *((_DWORD *)v12 + 10) != 0 ? a4 : 0,
           *((_DWORD *)v12 + 10) != 0 ? 16 : 24) )
    {
      return *((unsigned int *)v12 + 4);
    }
    v19 = *(_QWORD *)v17;
    if ( *(char **)(*(_QWORD *)v17 + 8LL) != v17 || (v20 = (char **)*((_QWORD *)v12 + 9), *v20 != v17) )
LABEL_11:
      __fastfail(3u);
    *v20 = (char *)v19;
    *(_QWORD *)(v19 + 8) = v20;
    *(_QWORD *)v17 = 0;
    *((_QWORD *)v12 + 9) = 0;
    TIMER::`scalar deleting destructor'((TIMER *)v12, v18);
  }
  else
  {
    SetLastError(8u);
  }
  return 0;
}

```

## disassembly

```asm
0x180016a90  push    rbx
0x180016a92  push    rbp
0x180016a93  push    rsi
0x180016a94  push    rdi
0x180016a95  push    r14
0x180016a97  sub     rsp, 40h
0x180016a9b  mov     rdi, rcx
0x180016a9e  mov     r14d, r9d
0x180016aa1  mov     ecx, 58h ; 'X'; Size
0x180016aa6  mov     rsi, r8
0x180016aa9  mov     rbp, rdx
0x180016aac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016ab1  mov     rbx, rax
0x180016ab4  test    rax, rax
0x180016ab7  jz      loc_180016BC4
0x180016abd  mov     dword ptr [rax], 524D4954h
0x180016ac3  mov     [rax+8], rdi
0x180016ac7  mov     dword ptr [rax+38h], 0
0x180016ace  lock inc dword ptr [rdi+18h]
0x180016ad2  mov     [rax+18h], rbp
0x180016ad6  lea     rdx, [rbx+10h]
0x180016ada  mov     [rax+20h], rsi
0x180016ade  mov     eax, [rsp+68h+arg_20]
0x180016ae5  mov     [rbx+28h], eax
0x180016ae8  mov     eax, [rsp+68h+arg_28]
0x180016aef  mov     [rbx+2Ch], eax
0x180016af2  mov     eax, [rsp+68h+arg_30]
0x180016af9  mov     dword ptr [rbx+50h], 0
0x180016b00  test    eax, eax
0x180016b02  jz      short loc_180016B08
0x180016b04  mov     [rdx], eax
0x180016b06  jmp     short loc_180016B1C
0x180016b08  mov     eax, 1
0x180016b0d  lock xadd cs:?sm_lLastCookie@TIMER@@0JA, eax; long TIMER::sm_lLastCookie
0x180016b15  add     eax, 1
0x180016b18  mov     [rdx], eax
0x180016b1a  jz      short loc_180016B08
0x180016b1c  lea     rax, [rdi+20h]
0x180016b20  mov     rcx, [rax]
0x180016b23  cmp     [rcx+8], rax
0x180016b27  jnz     loc_180016BBD
0x180016b2d  lea     rdi, [rbx+40h]
0x180016b31  mov     [rdi], rcx
0x180016b34  mov     [rdi+8], rax
0x180016b38  mov     [rcx+8], rdi
0x180016b3c  mov     [rax], rdi
0x180016b3f  mov     ecx, [rbx+28h]
0x180016b42  mov     r9d, [rdx]; Parameter
0x180016b45  mov     eax, ecx
0x180016b47  mov     rdx, [rbx+8]
0x180016b4b  neg     eax
0x180016b4d  sbb     r8d, r8d
0x180016b50  and     r8d, 0FFFFFFF8h
0x180016b54  mov     rdx, [rdx+8]; TimerQueue
0x180016b58  add     r8d, 18h
0x180016b5c  mov     [rsp+68h+Flags], r8d; Flags
0x180016b61  neg     ecx
0x180016b63  lea     rcx, [rbx+30h]; phNewTimer
0x180016b67  sbb     eax, eax
0x180016b69  lea     r8, ?TimerCallback@TIMER@@SAXPEAXE@Z; Callback
0x180016b70  and     eax, r14d
0x180016b73  mov     [rsp+68h+Period], eax; Period
0x180016b77  mov     [rsp+68h+DueTime], r14d; DueTime
0x180016b7c  call    cs:__imp_CreateTimerQueueTimer
0x180016b82  test    eax, eax
0x180016b84  jnz     short loc_180016BB8
0x180016b86  mov     rax, [rdi]
0x180016b89  cmp     [rax+8], rdi
0x180016b8d  jnz     short loc_180016BBD
0x180016b8f  mov     rcx, [rdi+8]
0x180016b93  cmp     [rcx], rdi
0x180016b96  jnz     short loc_180016BBD
0x180016b98  mov     [rcx], rax
0x180016b9b  mov     [rax+8], rcx
0x180016b9f  mov     rcx, rbx; this
0x180016ba2  mov     qword ptr [rdi], 0
0x180016ba9  mov     qword ptr [rbx+48h], 0
0x180016bb1  call    ??_GTIMER@@AEAAPEAXI@Z; TIMER::`scalar deleting destructor'(uint)
0x180016bb6  jmp     short loc_180016BCF
0x180016bb8  mov     eax, [rbx+10h]
0x180016bbb  jmp     short loc_180016BD1
0x180016bbd  mov     ecx, 3
0x180016bc2  int     29h; Win8: RtlFailFast(ecx)
0x180016bc4  mov     ecx, 8; dwErrCode
0x180016bc9  call    cs:__imp_SetLastError
0x180016bcf  xor     eax, eax
0x180016bd1  add     rsp, 40h
0x180016bd5  pop     r14
0x180016bd7  pop     rdi
0x180016bd8  pop     rsi
0x180016bd9  pop     rbp
0x180016bda  pop     rbx
0x180016bdb  retn
```
