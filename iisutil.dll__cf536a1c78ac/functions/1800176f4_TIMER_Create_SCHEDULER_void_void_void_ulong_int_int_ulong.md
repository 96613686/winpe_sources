# TIMER::Create(SCHEDULER *,void (*)(void *),void *,ulong,int,int,ulong)

- ea: `0x1800176f4`
- end: `0x18001784d`
- name: `?Create@TIMER@@SAKPEAVSCHEDULER@@P6AXPEAX@Z1KHHK@Z`
- size: `345`
- prototype: `static unsigned int(struct SCHEDULER *, void (*)(void *), void *, unsigned int, int, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180017590`
- `0x180021370`

## callees

- `0x1800176f4`
- `0x18001909c`
- `0x180019230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017833`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017833`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x1800177e0`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x1800177e0`

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
0x1800176f4  push    rbx
0x1800176f6  push    rbp
0x1800176f7  push    rsi
0x1800176f8  push    rdi
0x1800176f9  push    r14
0x1800176fb  sub     rsp, 40h
0x1800176ff  mov     rdi, rcx
0x180017702  mov     r14d, r9d
0x180017705  mov     ecx, 58h ; 'X'; Size
0x18001770a  mov     rsi, r8
0x18001770d  mov     rbp, rdx
0x180017710  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017715  mov     rbx, rax
0x180017718  test    rax, rax
0x18001771b  jz      loc_18001782E
0x180017721  mov     dword ptr [rax], 524D4954h
0x180017727  mov     [rax+8], rdi
0x18001772b  mov     dword ptr [rax+38h], 0
0x180017732  lock inc dword ptr [rdi+18h]
0x180017736  mov     [rax+18h], rbp
0x18001773a  lea     rdx, [rbx+10h]
0x18001773e  mov     [rax+20h], rsi
0x180017742  mov     eax, [rsp+68h+arg_20]
0x180017749  mov     [rbx+28h], eax
0x18001774c  mov     eax, [rsp+68h+arg_28]
0x180017753  mov     [rbx+2Ch], eax
0x180017756  mov     eax, [rsp+68h+arg_30]
0x18001775d  mov     dword ptr [rbx+50h], 0
0x180017764  test    eax, eax
0x180017766  jz      short loc_18001776C
0x180017768  mov     [rdx], eax
0x18001776a  jmp     short loc_180017780
0x18001776c  mov     eax, 1
0x180017771  lock xadd cs:?sm_lLastCookie@TIMER@@0JA, eax; long TIMER::sm_lLastCookie
0x180017779  add     eax, 1
0x18001777c  mov     [rdx], eax
0x18001777e  jz      short loc_18001776C
0x180017780  lea     rax, [rdi+20h]
0x180017784  mov     rcx, [rax]
0x180017787  cmp     [rcx+8], rax
0x18001778b  jnz     loc_180017827
0x180017791  lea     rdi, [rbx+40h]
0x180017795  mov     [rdi], rcx
0x180017798  mov     [rdi+8], rax
0x18001779c  mov     [rcx+8], rdi
0x1800177a0  mov     [rax], rdi
0x1800177a3  mov     ecx, [rbx+28h]
0x1800177a6  mov     r9d, [rdx]; Parameter
0x1800177a9  mov     eax, ecx
0x1800177ab  mov     rdx, [rbx+8]
0x1800177af  neg     eax
0x1800177b1  sbb     r8d, r8d
0x1800177b4  and     r8d, 0FFFFFFF8h
0x1800177b8  mov     rdx, [rdx+8]; TimerQueue
0x1800177bc  add     r8d, 18h
0x1800177c0  mov     [rsp+68h+Flags], r8d; Flags
0x1800177c5  neg     ecx
0x1800177c7  lea     rcx, [rbx+30h]; phNewTimer
0x1800177cb  sbb     eax, eax
0x1800177cd  lea     r8, ?TimerCallback@TIMER@@SAXPEAXE@Z; Callback
0x1800177d4  and     eax, r14d
0x1800177d7  mov     [rsp+68h+Period], eax; Period
0x1800177db  mov     [rsp+68h+DueTime], r14d; DueTime
0x1800177e0  call    cs:__imp_CreateTimerQueueTimer
0x1800177e7  nop     dword ptr [rax+rax+00h]
0x1800177ec  test    eax, eax
0x1800177ee  jnz     short loc_180017822
0x1800177f0  mov     rax, [rdi]
0x1800177f3  cmp     [rax+8], rdi
0x1800177f7  jnz     short loc_180017827
0x1800177f9  mov     rcx, [rdi+8]
0x1800177fd  cmp     [rcx], rdi
0x180017800  jnz     short loc_180017827
0x180017802  mov     [rcx], rax
0x180017805  mov     [rax+8], rcx
0x180017809  mov     rcx, rbx; this
0x18001780c  mov     qword ptr [rdi], 0
0x180017813  mov     qword ptr [rbx+48h], 0
0x18001781b  call    ??_GTIMER@@AEAAPEAXI@Z; TIMER::`scalar deleting destructor'(uint)
0x180017820  jmp     short loc_18001783F
0x180017822  mov     eax, [rbx+10h]
0x180017825  jmp     short loc_180017841
0x180017827  mov     ecx, 3
0x18001782c  int     29h; Win8: RtlFailFast(ecx)
0x18001782e  mov     ecx, 8; dwErrCode
0x180017833  call    cs:__imp_SetLastError
0x18001783a  nop     dword ptr [rax+rax+00h]
0x18001783f  xor     eax, eax
0x180017841  add     rsp, 40h
0x180017845  pop     r14
0x180017847  pop     rdi
0x180017848  pop     rsi
0x180017849  pop     rbp
0x18001784a  pop     rbx
0x18001784b  retn
```
