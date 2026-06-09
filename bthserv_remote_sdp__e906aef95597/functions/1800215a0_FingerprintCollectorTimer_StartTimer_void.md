# FingerprintCollectorTimer::StartTimer(void)

- ea: `0x1800215a0`
- end: `0x180021819`
- name: `?StartTimer@FingerprintCollectorTimer@@IEAAXXZ`
- size: `633`
- prototype: `void __fastcall(FingerprintCollectorTimer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800208f0`

## callees

- `0x1800017a0`
- `0x180003740`
- `0x18000b330`
- `0x180012384`
- `0x1800215a0`
- `0x180021b44`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002171c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002171c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800216b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800216b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180021748`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180021748`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800216e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800216e7`

## string_xrefs

- `0x1800217fb`: `Cannot start if start already started.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FingerprintCollectorTimer::StartTimer(FingerprintCollectorTimer *this)
{
  char v2; // di
  _BYTE *v3; // rcx
  bool v4; // dl
  _UNKNOWN **v5; // rax
  bool v6; // dl
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned int v9; // eax
  const char *v10; // [rsp+28h] [rbp-E0h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v12[8]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v13[13]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v14; // [rsp+C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v3 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v6 = v3 != (_BYTE *)&WPP_GLOBAL_Control && v3[25] >= 4u;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v3 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v3 + 5));
  v7 = *((_QWORD *)this + 10);
  v13[0] = off_18003A580;
  v13[1] = this;
  v14 = v13;
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 32));
  pftDueTime = (struct _FILETIME)(v7 + 32);
  if ( *(_BYTE *)(v7 + 40) )
  {
    v9 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateMachines.h",
      (const char *)v9,
      (int)"Cannot start if start already started.",
      v10);
  }
  *(_BYTE *)(v7 + 40) = 1;
  *(_BYTE *)(v7 + 168) = 1;
  *(_QWORD *)(v7 + 184) = 0;
  QueryPerformanceCounter((LARGE_INTEGER *)(v7 + 176));
  wistd::function<void (void)>::operator=(v7 + 48, v12);
  *(_QWORD *)(v7 + 192) = 1000LL * *((_QWORD *)this + 12);
  *(_BYTE *)(v7 + 41) = 0;
  if ( v7 != -32 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 32));
  v8 = *(_QWORD *)(v7 + 24);
  pftDueTime = (struct _FILETIME)(-10000000LL * *((_QWORD *)this + 12));
  SetThreadpoolTimerEx(*(PTP_TIMER *)(v8 + 80), &pftDueTime, 0, 0);
  if ( v14 )
    (*(void (__fastcall **)(_QWORD *))(*v14 + 24LL))(v14);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
}

```

## disassembly

```asm
0x1800215a0  mov     [rsp+arg_8], rbx
0x1800215a5  mov     [rsp+arg_10], rbp
0x1800215aa  push    rsi
0x1800215ab  push    rdi
0x1800215ac  push    r12
0x1800215ae  push    r13
0x1800215b0  push    r15
0x1800215b2  sub     rsp, 0E0h
0x1800215b9  mov     rax, cs:__security_cookie
0x1800215c0  xor     rax, rsp
0x1800215c3  mov     [rsp+108h+var_38], rax
0x1800215cb  mov     rbp, rcx
0x1800215ce  lea     r15, WPP_GLOBAL_Control
0x1800215d5  mov     edi, 1
0x1800215da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215e1  cmp     rcx, r15
0x1800215e4  jz      short loc_1800215F1
0x1800215e6  cmp     byte ptr [rcx+19h], 5
0x1800215ea  jb      short loc_1800215F1
0x1800215ec  mov     dl, dil
0x1800215ef  jmp     short loc_1800215F3
0x1800215f1  xor     dl, dl
0x1800215f3  lea     r12, WPP_RECORDER_INITIALIZED
0x1800215fa  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180021601  cmp     rax, r12
0x180021604  setnz   r8b
0x180021608  lea     r13, WPP_839c6382b2ad3f346a7c505e6bed1a32_Traceguids
0x18002160f  test    dl, dl
0x180021611  jnz     short loc_180021618
0x180021613  test    r8b, r8b
0x180021616  jz      short loc_180021644
0x180021618  mov     [rsp+108h+var_C0], rbp
0x18002161d  mov     [rsp+108h+var_D0], r13
0x180021622  mov     [rsp+108h+var_D8], 0Eh
0x180021629  mov     r9, [rcx+28h]
0x18002162d  mov     rcx, [rcx+10h]
0x180021631  call    WPP_RECORDER_AND_TRACE_SF_si
0x180021636  mov     rcx, cs:WPP_GLOBAL_Control
0x18002163d  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180021644  cmp     rcx, r15
0x180021647  jz      short loc_180021654
0x180021649  cmp     byte ptr [rcx+19h], 4
0x18002164d  jb      short loc_180021654
0x18002164f  mov     dl, dil
0x180021652  jmp     short loc_180021656
0x180021654  xor     dl, dl
0x180021656  cmp     rax, r12
0x180021659  setnz   r8b
0x18002165d  test    dl, dl
0x18002165f  jnz     short loc_180021666
0x180021661  test    r8b, r8b
0x180021664  jz      short loc_180021688
0x180021666  mov     rax, [rbp+48h]
0x18002166a  mov     [rsp+108h+var_C0], rax
0x18002166f  mov     [rsp+108h+var_D0], r13
0x180021674  mov     [rsp+108h+var_D8], 0Fh
0x18002167b  mov     r9, [rcx+28h]
0x18002167f  mov     rcx, [rcx+10h]
0x180021683  call    WPP_RECORDER_AND_TRACE_SF_si
0x180021688  mov     rbx, [rbp+50h]
0x18002168c  lea     rax, off_18003A580
0x180021693  mov     [rsp+108h+var_A8], rax
0x180021698  mov     [rsp+108h+var_A0], rbp
0x18002169d  lea     rax, [rsp+108h+var_A8]
0x1800216a2  mov     [rsp+108h+var_40], rax
0x1800216aa  lea     rsi, [rbx+20h]
0x1800216ae  mov     rcx, rsi; SRWLock
0x1800216b1  call    cs:__imp_AcquireSRWLockExclusive
0x1800216b8  nop     dword ptr [rax+rax+00h]
0x1800216bd  mov     qword ptr [rsp+108h+pftDueTime.dwLowDateTime], rsi
0x1800216c2  cmp     byte ptr [rbx+28h], 0
0x1800216c6  jnz     loc_1800217E6
0x1800216cc  mov     [rbx+28h], dil
0x1800216d0  mov     eax, edi
0x1800216d2  xchg    al, [rbx+0A8h]
0x1800216d8  and     qword ptr [rbx+0B8h], 0
0x1800216e0  lea     rcx, [rbx+0B0h]; lpPerformanceCount
0x1800216e7  call    cs:__imp_QueryPerformanceCounter
0x1800216ee  nop     dword ptr [rax+rax+00h]
0x1800216f3  lea     rcx, [rbx+30h]
0x1800216f7  lea     rdx, [rsp+108h+var_B0]
0x1800216fc  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::function<void (void)>::operator=(wistd::function<void (void)> &&)
0x180021701  imul    rax, [rbp+60h], 3E8h
0x180021709  mov     [rbx+0C0h], rax
0x180021710  mov     byte ptr [rbx+29h], 0
0x180021714  test    rsi, rsi
0x180021717  jz      short loc_180021728
0x180021719  mov     rcx, rsi; SRWLock
0x18002171c  call    cs:__imp_ReleaseSRWLockExclusive
0x180021723  nop     dword ptr [rax+rax+00h]
0x180021728  mov     rcx, [rbx+18h]
0x18002172c  imul    rax, [rbp+60h], 0FFFFFFFFFF676980h
0x180021734  mov     qword ptr [rsp+108h+pftDueTime.dwLowDateTime], rax
0x180021739  xor     r9d, r9d; msWindowLength
0x18002173c  xor     r8d, r8d; msPeriod
0x18002173f  lea     rdx, [rsp+108h+pftDueTime]; pftDueTime
0x180021744  mov     rcx, [rcx+50h]; pti
0x180021748  call    cs:__imp_SetThreadpoolTimerEx
0x18002174f  nop     dword ptr [rax+rax+00h]
0x180021754  nop
0x180021755  mov     rcx, [rsp+108h+var_40]
0x18002175d  test    rcx, rcx
0x180021760  jz      short loc_18002176E
0x180021762  mov     rax, [rcx]
0x180021765  mov     rax, [rax+18h]
0x180021769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002176e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021775  cmp     rcx, r15
0x180021778  jz      short loc_180021780
0x18002177a  cmp     byte ptr [rcx+19h], 5
0x18002177e  jnb     short loc_180021783
0x180021780  xor     dil, dil
0x180021783  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002178a  setnz   r8b
0x18002178e  test    dil, dil
0x180021791  jnz     short loc_180021798
0x180021793  test    r8b, r8b
0x180021796  jz      short loc_1800217B9
0x180021798  mov     [rsp+108h+var_C0], rbp
0x18002179d  mov     [rsp+108h+var_D0], r13
0x1800217a2  mov     [rsp+108h+var_D8], 11h
0x1800217a9  mov     r9, [rcx+28h]
0x1800217ad  mov     dl, dil
0x1800217b0  mov     rcx, [rcx+10h]
0x1800217b4  call    WPP_RECORDER_AND_TRACE_SF_si
0x1800217b9  mov     rcx, [rsp+108h+var_38]
0x1800217c1  xor     rcx, rsp; StackCookie
0x1800217c4  call    __security_check_cookie
0x1800217c9  lea     r11, [rsp+108h+var_28]
0x1800217d1  mov     rbx, [r11+38h]
0x1800217d5  mov     rbp, [r11+40h]
0x1800217d9  mov     rsp, r11
0x1800217dc  pop     r15
0x1800217de  pop     r13
0x1800217e0  pop     r12
0x1800217e2  pop     rdi
0x1800217e3  pop     rsi
0x1800217e4  retn
0x1800217e6  mov     ecx, 8000FFFFh
0x1800217eb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800217f0  mov     r9d, eax; char *
0x1800217f3  mov     rcx, [rsp+108h]; this
0x1800217fb  lea     rax, aCannotStartIfS; "Cannot start if start already started."
0x180021802  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180021807  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\bluetooth\\foundation"...
0x18002180e  mov     edx, 3Ch ; '<'; void *
0x180021813  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
