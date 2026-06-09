# Dns64TimerSetStop

- ea: `0x18004461c`
- end: `0x1800447bf`
- name: `Dns64TimerSetStop`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180069d54`

## callees

- `0x18004461c`
- `0x180044914`
- `0x180076740`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044642`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044656`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004473c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044656`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004473c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004476b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004476b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044754`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044754`

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
0x18004461c  push    rbp
0x18004461e  push    rbx
0x18004461f  push    rsi
0x180044620  push    rdi
0x180044621  mov     rbp, rsp
0x180044624  sub     rsp, 38h
0x180044628  lea     rax, [rbp+var_18]
0x18004462c  mov     rbx, rcx
0x18004462f  mov     [rbp+var_10], rax
0x180044633  lea     rsi, [rcx+8]
0x180044637  lea     rax, [rbp+var_18]
0x18004463b  mov     rcx, rsi; lpCriticalSection
0x18004463e  mov     [rbp+var_18], rax
0x180044642  call    cs:__imp_EnterCriticalSection
0x180044649  nop     dword ptr [rax+rax+00h]
0x18004464e  cmp     dword ptr [rbx], 0
0x180044651  jnz     short loc_18004466C
0x180044653  mov     rcx, rsi; lpCriticalSection
0x180044656  call    cs:__imp_LeaveCriticalSection
0x18004465d  nop     dword ptr [rax+rax+00h]
0x180044662  add     rsp, 38h
0x180044666  pop     rdi
0x180044667  pop     rsi
0x180044668  pop     rbx
0x180044669  pop     rbp
0x18004466a  retn
0x18004466c  mov     r8, [rbx+30h]
0x180044670  mov     dword ptr [rbx], 0
0x180044676  lea     rdx, [r8+28h]
0x18004467a  cmp     [rdx], rdx
0x18004467d  jnz     short loc_1800446F8
0x18004467f  movzx   eax, word ptr [r8+18h]
0x180044684  and     eax, [r8+4]
0x180044688  mov     ecx, eax
0x18004468a  mov     [r8+20h], ecx
0x18004468e  lea     rax, ds:7[rax*2]
0x180044696  add     rax, rcx
0x180044699  lea     rcx, [r8+rax*8]
0x18004469d  mov     rax, [rcx]
0x1800446a0  cmp     [rax+8], rcx
0x1800446a4  jnz     loc_1800447B8
0x1800446aa  mov     [rdx], rax
0x1800446ad  mov     [rdx+8], rcx
0x1800446b1  mov     [rax+8], rdx
0x1800446b5  mov     [rcx], rdx
0x1800446b8  jmp     short loc_1800446F8
0x1800446ba  mov     rcx, [rbx+30h]
0x1800446be  lea     r8, [rbp+arg_0]
0x1800446c2  mov     rdx, rdi
0x1800446c5  mov     [rbp+arg_0], 0
0x1800446c9  call    RtlCleanupTimerWheelEntry
0x1800446ce  mov     rcx, [rbp+var_10]
0x1800446d2  lea     rax, [rbp+var_18]
0x1800446d6  cmp     [rcx], rax
0x1800446d9  jnz     loc_1800447B8
0x1800446df  lea     rax, [rdi+18h]
0x1800446e3  mov     [rax+8], rcx
0x1800446e7  lea     rdx, [rbp+var_18]
0x1800446eb  mov     [rax], rdx
0x1800446ee  mov     [rcx], rax
0x1800446f1  dec     dword ptr [rbx+38h]
0x1800446f4  mov     [rbp+var_10], rax
0x1800446f8  mov     rcx, [rbx+30h]
0x1800446fc  call    RtlEnumerateNextTimerWheelEntry
0x180044701  mov     rdi, rax
0x180044704  test    rax, rax
0x180044707  jnz     short loc_1800446BA
0x180044709  mov     rax, [rbx+30h]
0x18004470d  add     rax, 28h ; '('
0x180044711  mov     rdx, [rax]
0x180044714  cmp     [rdx+8], rax
0x180044718  jnz     loc_1800447B8
0x18004471e  mov     rcx, [rax+8]
0x180044722  cmp     [rcx], rax
0x180044725  jnz     loc_1800447B8
0x18004472b  mov     [rcx], rdx
0x18004472e  mov     [rdx+8], rcx
0x180044732  mov     rcx, rsi; lpCriticalSection
0x180044735  mov     [rax+8], rax
0x180044739  mov     [rax], rax
0x18004473c  call    cs:__imp_LeaveCriticalSection
0x180044743  nop     dword ptr [rax+rax+00h]
0x180044748  mov     rcx, [rbx+40h]; pti
0x18004474c  xor     r9d, r9d; msWindowLength
0x18004474f  xor     r8d, r8d; msPeriod
0x180044752  xor     edx, edx; pftDueTime
0x180044754  call    cs:__imp_SetThreadpoolTimer
0x18004475b  nop     dword ptr [rax+rax+00h]
0x180044760  mov     rcx, [rbx+40h]; pti
0x180044764  mov     edi, 1
0x180044769  mov     edx, edi; fCancelPendingCallbacks
0x18004476b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180044772  nop     dword ptr [rax+rax+00h]
0x180044777  mov     rax, [rbp+var_18]
0x18004477b  lea     rcx, [rbp+var_18]
0x18004477f  cmp     rax, rcx
0x180044782  jz      loc_180044662
0x180044788  lea     rcx, [rbp+var_18]
0x18004478c  cmp     [rax+8], rcx
0x180044790  jnz     short loc_1800447B8
0x180044792  mov     rcx, [rax]
0x180044795  cmp     [rcx+8], rax
0x180044799  jnz     short loc_1800447B8
0x18004479b  mov     [rbp+var_18], rcx
0x18004479f  lea     rdx, [rbp+var_18]
0x1800447a3  mov     [rcx+8], rdx
0x1800447a7  mov     edx, edi
0x1800447a9  mov     rcx, [rax+38h]
0x1800447ad  mov     rax, [rax+40h]
0x1800447b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447b6  jmp     short loc_180044777
0x1800447b8  mov     ecx, 3
0x1800447bd  int     29h; Win8: RtlFailFast(ecx)
```
