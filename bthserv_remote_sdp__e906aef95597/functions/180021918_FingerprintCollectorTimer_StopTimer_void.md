# FingerprintCollectorTimer::StopTimer(void)

- ea: `0x180021918`
- end: `0x180021af6`
- name: `?StopTimer@FingerprintCollectorTimer@@IEAA?AW4StopTimerResult@SmFx@@XZ`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020920`

## callees

- `0x180012384`
- `0x180021918`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021a7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800219fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800219fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180021a18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180021a18`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021a65`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021a65`

## pseudocode

```c
__int64 __fastcall FingerprintCollectorTimer::StopTimer(__int64 a1)
{
  _BYTE *v2; // rcx
  char v3; // di
  bool v4; // dl
  _UNKNOWN **v5; // rax
  bool v6; // dl
  __int64 v7; // rbx
  int v8; // esi
  __int64 v9; // rcx
  char v10; // al

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v6 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v2 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v2 + 5));
  v7 = *(_QWORD *)(a1 + 80);
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 32));
  if ( SetThreadpoolTimerEx(*(PTP_TIMER *)(*(_QWORD *)(v7 + 24) + 80LL), 0, 0, 0) )
  {
    v9 = *(_QWORD *)(v7 + 160);
    *(_QWORD *)(v7 + 160) = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
    *(_BYTE *)(v7 + 40) = 0;
    v10 = *(_BYTE *)(v7 + 168);
    *(_BYTE *)(v7 + 168) = 0;
    v8 = 0;
    if ( v10 )
      QueryPerformanceCounter((LARGE_INTEGER *)(v7 + 184));
  }
  else
  {
    v8 = 1;
  }
  *(_BYTE *)(v7 + 41) = 1;
  if ( v7 != -32 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 32));
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  return (unsigned int)(v8 + 1);
}

```

## disassembly

```asm
0x180021918  mov     [rsp+arg_0], rbx
0x18002191d  mov     [rsp+arg_8], rbp
0x180021922  mov     [rsp+arg_10], rsi
0x180021927  push    rdi
0x180021928  push    r12
0x18002192a  push    r13
0x18002192c  push    r14
0x18002192e  push    r15
0x180021930  sub     rsp, 50h
0x180021934  mov     r14, rcx
0x180021937  mov     rcx, cs:WPP_GLOBAL_Control
0x18002193e  lea     r15, WPP_GLOBAL_Control
0x180021945  mov     edi, 1
0x18002194a  cmp     rcx, r15
0x18002194d  jz      short loc_18002195A
0x18002194f  cmp     byte ptr [rcx+19h], 5
0x180021953  jb      short loc_18002195A
0x180021955  mov     dl, dil
0x180021958  jmp     short loc_18002195C
0x18002195a  xor     dl, dl
0x18002195c  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180021963  lea     r12, WPP_RECORDER_INITIALIZED
0x18002196a  cmp     rax, r12
0x18002196d  lea     r13, WPP_839c6382b2ad3f346a7c505e6bed1a32_Traceguids
0x180021974  setnz   r8b
0x180021978  test    dl, dl
0x18002197a  jnz     short loc_180021981
0x18002197c  test    r8b, r8b
0x18002197f  jz      short loc_1800219AD
0x180021981  mov     r9, [rcx+28h]
0x180021985  mov     rcx, [rcx+10h]
0x180021989  mov     [rsp+78h+var_30], r14
0x18002198e  mov     [rsp+78h+var_40], r13
0x180021993  mov     [rsp+78h+var_48], 12h
0x18002199a  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002199f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219a6  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x1800219ad  cmp     rcx, r15
0x1800219b0  jz      short loc_1800219BD
0x1800219b2  cmp     byte ptr [rcx+19h], 4
0x1800219b6  jb      short loc_1800219BD
0x1800219b8  mov     dl, dil
0x1800219bb  jmp     short loc_1800219BF
0x1800219bd  xor     dl, dl
0x1800219bf  cmp     rax, r12
0x1800219c2  setnz   r8b
0x1800219c6  test    dl, dl
0x1800219c8  jnz     short loc_1800219CF
0x1800219ca  test    r8b, r8b
0x1800219cd  jz      short loc_1800219F1
0x1800219cf  mov     rax, [r14+48h]
0x1800219d3  mov     r9, [rcx+28h]
0x1800219d7  mov     rcx, [rcx+10h]
0x1800219db  mov     [rsp+78h+var_30], rax
0x1800219e0  mov     [rsp+78h+var_40], r13
0x1800219e5  mov     [rsp+78h+var_48], 13h
0x1800219ec  call    WPP_RECORDER_AND_TRACE_SF_si
0x1800219f1  mov     rbx, [r14+50h]
0x1800219f5  lea     rbp, [rbx+20h]
0x1800219f9  mov     rcx, rbp; SRWLock
0x1800219fc  call    cs:__imp_AcquireSRWLockExclusive
0x180021a03  nop     dword ptr [rax+rax+00h]
0x180021a08  mov     rcx, [rbx+18h]
0x180021a0c  xor     r9d, r9d; msWindowLength
0x180021a0f  xor     r8d, r8d; msPeriod
0x180021a12  xor     edx, edx; pftDueTime
0x180021a14  mov     rcx, [rcx+50h]; pti
0x180021a18  call    cs:__imp_SetThreadpoolTimerEx
0x180021a1f  nop     dword ptr [rax+rax+00h]
0x180021a24  test    eax, eax
0x180021a26  jnz     short loc_180021A2C
0x180021a28  mov     esi, edi
0x180021a2a  jmp     short loc_180021A71
0x180021a2c  mov     rcx, [rbx+0A0h]
0x180021a33  and     qword ptr [rbx+0A0h], 0
0x180021a3b  test    rcx, rcx
0x180021a3e  jz      short loc_180021A4C
0x180021a40  mov     rax, [rcx]
0x180021a43  mov     rax, [rax+18h]
0x180021a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a4c  xor     eax, eax
0x180021a4e  mov     byte ptr [rbx+28h], 0
0x180021a52  xchg    al, [rbx+0A8h]
0x180021a58  xor     esi, esi
0x180021a5a  test    al, al
0x180021a5c  jz      short loc_180021A71
0x180021a5e  lea     rcx, [rbx+0B8h]; lpPerformanceCount
0x180021a65  call    cs:__imp_QueryPerformanceCounter
0x180021a6c  nop     dword ptr [rax+rax+00h]
0x180021a71  mov     [rbx+29h], dil
0x180021a75  test    rbp, rbp
0x180021a78  jz      short loc_180021A89
0x180021a7a  mov     rcx, rbp; SRWLock
0x180021a7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180021a84  nop     dword ptr [rax+rax+00h]
0x180021a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a90  cmp     rcx, r15
0x180021a93  jz      short loc_180021A9B
0x180021a95  cmp     byte ptr [rcx+19h], 5
0x180021a99  jnb     short loc_180021A9E
0x180021a9b  xor     dil, dil
0x180021a9e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180021aa5  setnz   r8b
0x180021aa9  test    dil, dil
0x180021aac  jnz     short loc_180021AB3
0x180021aae  test    r8b, r8b
0x180021ab1  jz      short loc_180021AD4
0x180021ab3  mov     r9, [rcx+28h]
0x180021ab7  mov     dl, dil
0x180021aba  mov     rcx, [rcx+10h]
0x180021abe  mov     [rsp+78h+var_30], r14
0x180021ac3  mov     [rsp+78h+var_40], r13
0x180021ac8  mov     [rsp+78h+var_48], 14h
0x180021acf  call    WPP_RECORDER_AND_TRACE_SF_si
0x180021ad4  lea     r11, [rsp+78h+var_28]
0x180021ad9  mov     rbx, [r11+30h]
0x180021add  lea     eax, [rsi+1]
0x180021ae0  mov     rbp, [r11+38h]
0x180021ae4  mov     rsi, [r11+40h]
0x180021ae8  mov     rsp, r11
0x180021aeb  pop     r15
0x180021aed  pop     r14
0x180021aef  pop     r13
0x180021af1  pop     r12
0x180021af3  pop     rdi
0x180021af4  retn
```
