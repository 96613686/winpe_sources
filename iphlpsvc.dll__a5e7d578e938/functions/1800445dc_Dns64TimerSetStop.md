# Dns64TimerSetStop

- ea: `0x1800445dc`
- end: `0x18004477f`
- name: `Dns64TimerSetStop`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180069d74`

## callees

- `0x1800445dc`
- `0x1800448d4`
- `0x180076760`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044616`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800446fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044616`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800446fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004472b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004472b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044714`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044714`

## pseudocode

```c
void __fastcall Dns64TimerSetStop(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // r8
  _QWORD *v4; // rdx
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 **v9; // rcx
  __int64 TimerWheelEntry; // rax
  __int64 v11; // rdi
  _QWORD *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 *v15; // rax
  __int64 *v16; // rcx
  __int64 *v17; // [rsp+20h] [rbp-18h] BYREF
  __int64 **v18; // [rsp+28h] [rbp-10h]
  char v19; // [rsp+60h] [rbp+28h] BYREF

  v18 = &v17;
  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  v17 = (__int64 *)&v17;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( *(_DWORD *)a1 )
  {
    v3 = *(_QWORD *)(a1 + 48);
    *(_DWORD *)a1 = 0;
    v4 = (_QWORD *)(v3 + 40);
    if ( (_QWORD *)*v4 != v4 )
      goto LABEL_9;
    v5 = *(_DWORD *)(v3 + 4) & (unsigned int)*(unsigned __int16 *)(v3 + 24);
    *(_DWORD *)(v3 + 32) = v5;
    v6 = (__int64 *)(v3 + 8 * (v5 + 2 * v5 + 7));
    v7 = *v6;
    if ( *(__int64 **)(*v6 + 8) != v6 )
      goto LABEL_17;
    *v4 = v7;
    *(_QWORD *)(v3 + 48) = v6;
    *(_QWORD *)(v7 + 8) = v4;
    *v6 = (__int64)v4;
LABEL_9:
    while ( 1 )
    {
      TimerWheelEntry = RtlEnumerateNextTimerWheelEntry(*(_QWORD *)(a1 + 48));
      v11 = TimerWheelEntry;
      if ( !TimerWheelEntry )
        break;
      v8 = *(_QWORD *)(a1 + 48);
      v19 = 0;
      RtlCleanupTimerWheelEntry(v8, TimerWheelEntry, &v19);
      v9 = v18;
      if ( *v18 != (__int64 *)&v17 )
        goto LABEL_17;
      *(_QWORD *)(v11 + 32) = v18;
      *(_QWORD *)(v11 + 24) = &v17;
      *v9 = (__int64 *)(v11 + 24);
      --*(_DWORD *)(a1 + 56);
      v18 = (__int64 **)(v11 + 24);
    }
    v12 = (_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL);
    v13 = *v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 || (v14 = *(_QWORD **)(*(_QWORD *)(a1 + 48) + 48LL), (_QWORD *)*v14 != v12) )
LABEL_17:
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    v12[1] = v12;
    *v12 = v12;
    LeaveCriticalSection(v2);
    SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 64), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 64), 1);
    while ( 1 )
    {
      v15 = v17;
      if ( v17 == (__int64 *)&v17 )
        break;
      if ( (__int64 **)v17[1] != &v17 )
        goto LABEL_17;
      v16 = (__int64 *)*v17;
      if ( *(__int64 **)(*v17 + 8) != v17 )
        goto LABEL_17;
      v17 = (__int64 *)*v17;
      v16[1] = (__int64)&v17;
      ((void (__fastcall *)(__int64, __int64))v15[8])(v15[7], 1);
    }
  }
  else
  {
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x1800445dc  push    rbp
0x1800445de  push    rbx
0x1800445df  push    rsi
0x1800445e0  push    rdi
0x1800445e1  mov     rbp, rsp
0x1800445e4  sub     rsp, 38h
0x1800445e8  lea     rax, [rbp+var_18]
0x1800445ec  mov     rbx, rcx
0x1800445ef  mov     [rbp+var_10], rax
0x1800445f3  lea     rsi, [rcx+8]
0x1800445f7  lea     rax, [rbp+var_18]
0x1800445fb  mov     rcx, rsi; lpCriticalSection
0x1800445fe  mov     [rbp+var_18], rax
0x180044602  call    cs:__imp_EnterCriticalSection
0x180044609  nop     dword ptr [rax+rax+00h]
0x18004460e  cmp     dword ptr [rbx], 0
0x180044611  jnz     short loc_18004462C
0x180044613  mov     rcx, rsi; lpCriticalSection
0x180044616  call    cs:__imp_LeaveCriticalSection
0x18004461d  nop     dword ptr [rax+rax+00h]
0x180044622  add     rsp, 38h
0x180044626  pop     rdi
0x180044627  pop     rsi
0x180044628  pop     rbx
0x180044629  pop     rbp
0x18004462a  retn
0x18004462c  mov     r8, [rbx+30h]
0x180044630  mov     dword ptr [rbx], 0
0x180044636  lea     rdx, [r8+28h]
0x18004463a  cmp     [rdx], rdx
0x18004463d  jnz     short loc_1800446B8
0x18004463f  movzx   eax, word ptr [r8+18h]
0x180044644  and     eax, [r8+4]
0x180044648  mov     ecx, eax
0x18004464a  mov     [r8+20h], ecx
0x18004464e  lea     rax, ds:7[rax*2]
0x180044656  add     rax, rcx
0x180044659  lea     rcx, [r8+rax*8]
0x18004465d  mov     rax, [rcx]
0x180044660  cmp     [rax+8], rcx
0x180044664  jnz     loc_180044778
0x18004466a  mov     [rdx], rax
0x18004466d  mov     [rdx+8], rcx
0x180044671  mov     [rax+8], rdx
0x180044675  mov     [rcx], rdx
0x180044678  jmp     short loc_1800446B8
0x18004467a  mov     rcx, [rbx+30h]
0x18004467e  lea     r8, [rbp+arg_0]
0x180044682  mov     rdx, rdi
0x180044685  mov     [rbp+arg_0], 0
0x180044689  call    RtlCleanupTimerWheelEntry
0x18004468e  mov     rcx, [rbp+var_10]
0x180044692  lea     rax, [rbp+var_18]
0x180044696  cmp     [rcx], rax
0x180044699  jnz     loc_180044778
0x18004469f  lea     rax, [rdi+18h]
0x1800446a3  mov     [rax+8], rcx
0x1800446a7  lea     rdx, [rbp+var_18]
0x1800446ab  mov     [rax], rdx
0x1800446ae  mov     [rcx], rax
0x1800446b1  dec     dword ptr [rbx+38h]
0x1800446b4  mov     [rbp+var_10], rax
0x1800446b8  mov     rcx, [rbx+30h]
0x1800446bc  call    RtlEnumerateNextTimerWheelEntry
0x1800446c1  mov     rdi, rax
0x1800446c4  test    rax, rax
0x1800446c7  jnz     short loc_18004467A
0x1800446c9  mov     rax, [rbx+30h]
0x1800446cd  add     rax, 28h ; '('
0x1800446d1  mov     rdx, [rax]
0x1800446d4  cmp     [rdx+8], rax
0x1800446d8  jnz     loc_180044778
0x1800446de  mov     rcx, [rax+8]
0x1800446e2  cmp     [rcx], rax
0x1800446e5  jnz     loc_180044778
0x1800446eb  mov     [rcx], rdx
0x1800446ee  mov     [rdx+8], rcx
0x1800446f2  mov     rcx, rsi; lpCriticalSection
0x1800446f5  mov     [rax+8], rax
0x1800446f9  mov     [rax], rax
0x1800446fc  call    cs:__imp_LeaveCriticalSection
0x180044703  nop     dword ptr [rax+rax+00h]
0x180044708  mov     rcx, [rbx+40h]; pti
0x18004470c  xor     r9d, r9d; msWindowLength
0x18004470f  xor     r8d, r8d; msPeriod
0x180044712  xor     edx, edx; pftDueTime
0x180044714  call    cs:__imp_SetThreadpoolTimer
0x18004471b  nop     dword ptr [rax+rax+00h]
0x180044720  mov     rcx, [rbx+40h]; pti
0x180044724  mov     edi, 1
0x180044729  mov     edx, edi; fCancelPendingCallbacks
0x18004472b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180044732  nop     dword ptr [rax+rax+00h]
0x180044737  mov     rax, [rbp+var_18]
0x18004473b  lea     rcx, [rbp+var_18]
0x18004473f  cmp     rax, rcx
0x180044742  jz      loc_180044622
0x180044748  lea     rcx, [rbp+var_18]
0x18004474c  cmp     [rax+8], rcx
0x180044750  jnz     short loc_180044778
0x180044752  mov     rcx, [rax]
0x180044755  cmp     [rcx+8], rax
0x180044759  jnz     short loc_180044778
0x18004475b  mov     [rbp+var_18], rcx
0x18004475f  lea     rdx, [rbp+var_18]
0x180044763  mov     [rcx+8], rdx
0x180044767  mov     edx, edi
0x180044769  mov     rcx, [rax+38h]
0x18004476d  mov     rax, [rax+40h]
0x180044771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044776  jmp     short loc_180044737
0x180044778  mov     ecx, 3
0x18004477d  int     29h; Win8: RtlFailFast(ecx)
```
