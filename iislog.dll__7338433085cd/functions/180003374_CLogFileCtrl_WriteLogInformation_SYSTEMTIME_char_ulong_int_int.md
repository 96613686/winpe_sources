# CLogFileCtrl::WriteLogInformation(_SYSTEMTIME &,char *,ulong,int,int)

- ea: `0x180003374`
- end: `0x180003736`
- name: `?WriteLogInformation@CLogFileCtrl@@IEAAXAEAU_SYSTEMTIME@@PEADKHH@Z`
- size: `962`
- prototype: `void __fastcall(CLogFileCtrl *__hidden this, struct _SYSTEMTIME *, char *Src, size_t Size, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b50`
- `0x180005020`

## callees

- `0x180002c8c`
- `0x180003374`
- `0x1800083c4`
- `0x18000d598`
- `0x180010010`

## import_xrefs

- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x18000369d`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x180003700`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x18000369d`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x180003700`
- `IisRTL!ScheduleWorkItem` at `0x1800035d0`
- `IisRTL!ScheduleWorkItem` at `0x1800035d0`
- `KERNEL32!EnterCriticalSection` at `0x1800033a0`
- `KERNEL32!EnterCriticalSection` at `0x1800033a0`
- `KERNEL32!LeaveCriticalSection` at `0x18000372f`
- `KERNEL32!GetLastError` at `0x180003494`
- `KERNEL32!GetLastError` at `0x180003613`
- `KERNEL32!GetLastError` at `0x1800036a5`
- `KERNEL32!GetLastError` at `0x180003494`
- `KERNEL32!GetLastError` at `0x180003613`
- `KERNEL32!GetLastError` at `0x1800036a5`
- `KERNEL32!GetTickCount` at `0x180003459`
- `KERNEL32!GetTickCount` at `0x180003706`
- `KERNEL32!GetTickCount` at `0x180003459`
- `KERNEL32!GetTickCount` at `0x180003706`

## pseudocode

```c
void __fastcall CLogFileCtrl::WriteLogInformation(
        CLogFileCtrl *this,
        struct _SYSTEMTIME *a2,
        char *Src,
        size_t Size,
        int a5,
        int a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  __int64 v7; // rbp
  __int64 v11; // r8
  int v12; // r14d
  unsigned int v13; // esi
  int v14; // eax
  DWORD TickCount; // eax
  DWORD LastError; // esi
  __int64 v17; // rax
  int v18; // edx
  int v19; // ecx
  int v20; // edx
  unsigned int wMonth; // edx
  int v22; // ecx
  int v23; // ecx
  unsigned int wYear; // r8d
  int wMilliseconds; // eax
  __int64 v26; // rax
  unsigned int (__fastcall *v27)(CLogFileCtrl *, _QWORD, __int64); // rax
  EVENT_LOG *v28; // rcx
  EVENT_LOG *v29; // rcx
  const char *v30; // [rsp+30h] [rbp-38h] BYREF
  const char *v31; // [rsp+70h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 368);
  v7 = (unsigned int)Size;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  v12 = a5;
  if ( !*((_QWORD *)this + 7) )
    goto LABEL_18;
  v13 = *((_DWORD *)this + 27);
  if ( v13 == 1 )
  {
    if ( *((_WORD *)this + 41) == a2->wDay && *((_WORD *)this + 39) == a2->wMonth )
    {
      v14 = a6;
      goto LABEL_15;
    }
LABEL_18:
    if ( !*((_DWORD *)this + 29) )
      goto LABEL_21;
    TickCount = GetTickCount();
    if ( TickCount >= *((_DWORD *)this + 29) && TickCount + 60000 >= TickCount )
      goto LABEL_21;
    goto LABEL_65;
  }
  if ( (unsigned int)IsBeginningOfNewPeriod(v13, (struct _SYSTEMTIME *)((char *)this + 76), a2)
    || !v13
    && *((_DWORD *)this + 26) != -1
    && *((_QWORD *)this + 12) + v7 >= (unsigned __int64)*((unsigned int *)this + 26) )
  {
    goto LABEL_18;
  }
  if ( !a6 )
  {
    v14 = *((_WORD *)this + 41) != a2->wDay || *((_WORD *)this + 39) != a2->wMonth;
LABEL_15:
    if ( v14 || v12 != *((_DWORD *)this + 90) )
      goto LABEL_47;
    goto LABEL_54;
  }
LABEL_47:
  while ( 1 )
  {
    v26 = *(_QWORD *)this;
    if ( v12 )
    {
      v27 = *(unsigned int (__fastcall **)(CLogFileCtrl *, _QWORD, __int64))(v26 + 152);
      *((_DWORD *)this + 90) = 1;
    }
    else
    {
      v27 = *(unsigned int (__fastcall **)(CLogFileCtrl *, _QWORD, __int64))(v26 + 144);
      *((_DWORD *)this + 90) = 0;
    }
    if ( v27(this, (unsigned int)v7, v11) )
      break;
    LastError = GetLastError();
    v17 = *(_QWORD *)this;
    if ( LastError != 122 )
      goto LABEL_59;
    while ( 1 )
    {
      (*(void (__fastcall **)(CLogFileCtrl *, struct _SYSTEMTIME *))(v17 + 96))(this, a2);
LABEL_21:
      (*(void (__fastcall **)(CLogFileCtrl *))(*(_QWORD *)this + 32LL))(this);
      if ( (unsigned int)CLogFileCtrl::OpenLogFile(this, a2) )
        break;
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_60;
      v17 = *(_QWORD *)this;
    }
    v18 = 0;
    switch ( *((_DWORD *)this + 27) )
    {
      case 1:
        v20 = 60 * (60 * (24 - a2->wHour) - a2->wMinute);
        goto LABEL_44;
      case 2:
        v19 = 60 * (24 * (7 - a2->wDayOfWeek) - a2->wHour);
        goto LABEL_30;
      case 3:
        wMonth = a2->wMonth;
        if ( wMonth <= 9 && (v22 = 592, _bittest(&v22, wMonth)) || (v23 = 31, (_WORD)wMonth == 11) )
          v23 = 30;
        if ( (_WORD)wMonth == 2 )
        {
          wYear = a2->wYear;
          if ( ((wYear & 3) != 0 || wYear == 100 * (wYear / 0x64)) && wYear != 400 * (wYear / 0x190) )
            v23 = 28;
          else
            v23 = 29;
        }
        v19 = 60 * (24 * (v23 - a2->wDay) - a2->wHour);
        goto LABEL_30;
      case 4:
        v19 = 60;
LABEL_30:
        v20 = 60 * (v19 - a2->wMinute);
LABEL_44:
        v18 = v20 - a2->wSecond;
        break;
    }
    wMilliseconds = a2->wMilliseconds;
    v11 = (unsigned int)(1000 * v18 - wMilliseconds);
    if ( 1000 * v18 != wMilliseconds )
      *((_DWORD *)this + 30) = ScheduleWorkItem((void (*)(void *))LoggingSchedulerCallback, this, v11, 0);
  }
  *(struct _SYSTEMTIME *)((char *)this + 76) = *a2;
LABEL_54:
  if ( (unsigned int)ILOG_FILE::Write(*((ILOG_FILE **)this + 7), Src, (unsigned int)v7) )
  {
    *((_QWORD *)this + 12) += v7;
    if ( *((_DWORD *)this + 89) )
    {
      v28 = (EVENT_LOG *)g_eventLog;
      *((_DWORD *)this + 89) = 0;
      *((_DWORD *)this + 29) = 0;
      if ( v28 )
      {
        v31 = (const char *)*((_QWORD *)this + 20);
        EVENT_LOG::LogEvent(v28, 0x40000004u, 1u, &v31, 0);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v17 = *(_QWORD *)this;
LABEL_59:
    (*(void (__fastcall **)(CLogFileCtrl *))(v17 + 32))(this);
LABEL_60:
    if ( LastError == 112 )
    {
      if ( !*((_DWORD *)this + 89) )
      {
        v29 = (EVENT_LOG *)g_eventLog;
        *((_DWORD *)this + 89) = 1;
        if ( v29 )
        {
          v30 = (const char *)*((_QWORD *)this + 20);
          EVENT_LOG::LogEvent(v29, 0xC0000001, 1u, &v30, 0);
        }
      }
      *((_DWORD *)this + 29) = GetTickCount() + 60000;
    }
  }
LABEL_65:
  LeaveCriticalSection(v6);
}

```

## disassembly

```asm
0x180003374  mov     [rsp+arg_8], rbx
0x180003379  mov     [rsp+arg_10], rbp
0x18000337e  push    rsi
0x18000337f  push    rdi
0x180003380  push    r12
0x180003382  push    r14
0x180003384  push    r15
0x180003386  sub     rsp, 40h
0x18000338a  lea     r15, [rcx+170h]
0x180003391  mov     ebp, r9d
0x180003394  mov     rbx, rcx
0x180003397  mov     r12, r8
0x18000339a  mov     rcx, r15; lpCriticalSection
0x18000339d  mov     rdi, rdx
0x1800033a0  call    cs:__imp_EnterCriticalSection
0x1800033a6  cmp     qword ptr [rbx+38h], 0
0x1800033ab  mov     r14d, [rsp+68h+arg_20]
0x1800033b3  jz      loc_180003453
0x1800033b9  mov     esi, [rbx+6Ch]
0x1800033bc  lea     rdx, [rbx+4Ch]; struct _SYSTEMTIME *
0x1800033c0  cmp     esi, 1
0x1800033c3  jnz     short loc_1800033E6
0x1800033c5  movzx   eax, word ptr [rdi+6]
0x1800033c9  cmp     [rdx+6], ax
0x1800033cd  jnz     loc_180003453
0x1800033d3  movzx   eax, word ptr [rdi+2]
0x1800033d7  cmp     [rbx+4Eh], ax
0x1800033db  jnz     short loc_180003453
0x1800033dd  mov     eax, [rsp+68h+arg_28]
0x1800033e4  jmp     short loc_180003439
0x1800033e6  mov     r8, rdi; struct _SYSTEMTIME *
0x1800033e9  mov     ecx, esi; unsigned int
0x1800033eb  call    ?IsBeginningOfNewPeriod@@YAHKPEAU_SYSTEMTIME@@0@Z; IsBeginningOfNewPeriod(ulong,_SYSTEMTIME *,_SYSTEMTIME *)
0x1800033f0  test    eax, eax
0x1800033f2  jnz     short loc_180003453
0x1800033f4  test    esi, esi
0x1800033f6  jnz     short loc_18000340D
0x1800033f8  cmp     dword ptr [rbx+68h], 0FFFFFFFFh
0x1800033fc  jz      short loc_18000340D
0x1800033fe  mov     eax, [rbx+68h]
0x180003401  mov     rcx, rbp
0x180003404  add     rcx, [rbx+60h]
0x180003408  cmp     rcx, rax
0x18000340b  jnb     short loc_180003453
0x18000340d  mov     eax, [rsp+68h+arg_28]
0x180003414  test    eax, eax
0x180003416  jnz     loc_1800035D9
0x18000341c  movzx   eax, word ptr [rdi+6]
0x180003420  cmp     [rbx+52h], ax
0x180003424  jnz     short loc_180003434
0x180003426  movzx   eax, word ptr [rdi+2]
0x18000342a  cmp     [rbx+4Eh], ax
0x18000342e  jnz     short loc_180003434
0x180003430  xor     eax, eax
0x180003432  jmp     short loc_180003439
0x180003434  mov     eax, 1
0x180003439  test    eax, eax
0x18000343b  jnz     loc_1800035D9
0x180003441  cmp     r14d, [rbx+168h]
0x180003448  jz      loc_180003634
0x18000344e  jmp     loc_1800035D9
0x180003453  cmp     dword ptr [rbx+74h], 0
0x180003457  jz      short loc_180003476
0x180003459  call    cs:__imp_GetTickCount
0x18000345f  cmp     eax, [rbx+74h]
0x180003462  jb      loc_180003714
0x180003468  lea     ecx, [rax+0EA60h]
0x18000346e  cmp     ecx, eax
0x180003470  jb      loc_180003714
0x180003476  mov     rax, [rbx]
0x180003479  mov     rcx, rbx
0x18000347c  mov     rax, [rax+20h]
0x180003480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003485  mov     rdx, rdi; struct _SYSTEMTIME *
0x180003488  mov     rcx, rbx; this
0x18000348b  call    ?OpenLogFile@CLogFileCtrl@@AEAAHPEAU_SYSTEMTIME@@@Z; CLogFileCtrl::OpenLogFile(_SYSTEMTIME *)
0x180003490  test    eax, eax
0x180003492  jnz     short loc_1800034B9
0x180003494  call    cs:__imp_GetLastError
0x18000349a  mov     esi, eax
0x18000349c  cmp     eax, 7Ah ; 'z'
0x18000349f  jnz     loc_1800036BC
0x1800034a5  mov     rax, [rbx]
0x1800034a8  mov     rax, [rax+60h]
0x1800034ac  mov     rdx, rdi
0x1800034af  mov     rcx, rbx
0x1800034b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b7  jmp     short loc_180003476
0x1800034b9  mov     ecx, [rbx+6Ch]
0x1800034bc  xor     edx, edx
0x1800034be  sub     ecx, 1
0x1800034c1  jz      loc_180003596
0x1800034c7  sub     ecx, 1
0x1800034ca  jz      loc_180003577
0x1800034d0  sub     ecx, 1
0x1800034d3  jz      short loc_1800034EF
0x1800034d5  cmp     ecx, 1
0x1800034d8  jnz     loc_1800035B3
0x1800034de  lea     ecx, [rdx+3Ch]
0x1800034e1  movzx   eax, word ptr [rdi+0Ah]
0x1800034e5  sub     ecx, eax
0x1800034e7  imul    edx, ecx, 3Ch ; '<'
0x1800034ea  jmp     loc_1800035AD
0x1800034ef  movzx   edx, word ptr [rdi+2]
0x1800034f3  cmp     edx, 9
0x1800034f6  ja      short loc_180003502
0x1800034f8  mov     ecx, 250h
0x1800034fd  bt      ecx, edx
0x180003500  jb      short loc_18000350F
0x180003502  mov     ecx, 1Fh
0x180003507  lea     eax, [rcx-14h]
0x18000350a  cmp     ax, dx
0x18000350d  jnz     short loc_180003514
0x18000350f  mov     ecx, 1Eh
0x180003514  mov     eax, 2
0x180003519  cmp     ax, dx
0x18000351c  jnz     short loc_18000355D
0x18000351e  movzx   r8d, word ptr [rdi]
0x180003522  test    r8b, 3
0x180003526  jnz     short loc_18000353B
0x180003528  mov     eax, 51EB851Fh
0x18000352d  mul     r8d
0x180003530  shr     edx, 5
0x180003533  imul    ecx, edx, 64h ; 'd'
0x180003536  cmp     r8d, ecx
0x180003539  jnz     short loc_180003551
0x18000353b  mov     eax, 51EB851Fh
0x180003540  mul     r8d
0x180003543  shr     edx, 7
0x180003546  imul    eax, edx, 190h
0x18000354c  cmp     r8d, eax
0x18000354f  jnz     short loc_180003558
0x180003551  mov     ecx, 1Dh
0x180003556  jmp     short loc_18000355D
0x180003558  mov     ecx, 1Ch
0x18000355d  movzx   eax, word ptr [rdi+6]
0x180003561  sub     ecx, eax
0x180003563  movzx   eax, word ptr [rdi+8]
0x180003567  lea     ecx, [rcx+rcx*2]
0x18000356a  shl     ecx, 3
0x18000356d  sub     ecx, eax
0x18000356f  imul    ecx, 3Ch ; '<'
0x180003572  jmp     loc_1800034E1
0x180003577  movzx   eax, word ptr [rdi+4]
0x18000357b  mov     ecx, 7
0x180003580  sub     ecx, eax
0x180003582  movzx   eax, word ptr [rdi+8]
0x180003586  lea     edx, [rcx+rcx*2]
0x180003589  shl     edx, 3
0x18000358c  sub     edx, eax
0x18000358e  imul    ecx, edx, 3Ch ; '<'
0x180003591  jmp     loc_1800034E1
0x180003596  movzx   eax, word ptr [rdi+8]
0x18000359a  mov     ecx, 18h
0x18000359f  sub     ecx, eax
0x1800035a1  movzx   eax, word ptr [rdi+0Ah]
0x1800035a5  imul    edx, ecx, 3Ch ; '<'
0x1800035a8  sub     edx, eax
0x1800035aa  imul    edx, 3Ch ; '<'
0x1800035ad  movzx   eax, word ptr [rdi+0Ch]
0x1800035b1  sub     edx, eax
0x1800035b3  movzx   eax, word ptr [rdi+0Eh]
0x1800035b7  imul    r8d, edx, 3E8h
0x1800035be  sub     r8d, eax
0x1800035c1  jz      short loc_1800035D9
0x1800035c3  xor     r9d, r9d
0x1800035c6  lea     rcx, ?LoggingSchedulerCallback@@YAXPEAX@Z; LoggingSchedulerCallback(void *)
0x1800035cd  mov     rdx, rbx
0x1800035d0  call    cs:__imp_?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z; ScheduleWorkItem(void (*)(void *),void *,ulong,int)
0x1800035d6  mov     [rbx+78h], eax
0x1800035d9  mov     rax, [rbx]
0x1800035dc  mov     edx, ebp
0x1800035de  mov     rcx, rbx
0x1800035e1  test    r14d, r14d
0x1800035e4  jz      short loc_1800035F9
0x1800035e6  mov     rax, [rax+98h]
0x1800035ed  mov     dword ptr [rbx+168h], 1
0x1800035f7  jmp     short loc_18000360A
0x1800035f9  mov     rax, [rax+90h]
0x180003600  mov     dword ptr [rbx+168h], 0
0x18000360a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000360f  test    eax, eax
0x180003611  jnz     short loc_18000362C
0x180003613  call    cs:__imp_GetLastError
0x180003619  mov     esi, eax
0x18000361b  mov     rax, [rbx]
0x18000361e  cmp     esi, 7Ah ; 'z'
0x180003621  jz      loc_1800034A8
0x180003627  jmp     loc_1800036B0
0x18000362c  movups  xmm0, xmmword ptr [rdi]
0x18000362f  movdqu  xmmword ptr [rbx+4Ch], xmm0
0x180003634  mov     rcx, [rbx+38h]; this
0x180003638  mov     r8d, ebp; Size
0x18000363b  mov     rdx, r12; Src
0x18000363e  call    ?Write@ILOG_FILE@@QEAAHPEADK@Z; ILOG_FILE::Write(char *,ulong)
0x180003643  test    eax, eax
0x180003645  jz      short loc_1800036A5
0x180003647  add     [rbx+60h], rbp
0x18000364b  cmp     dword ptr [rbx+164h], 0
0x180003652  jz      loc_180003714
0x180003658  mov     rcx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x18000365f  mov     dword ptr [rbx+164h], 0
0x180003669  mov     dword ptr [rbx+74h], 0
0x180003670  test    rcx, rcx
0x180003673  jz      loc_180003714
0x180003679  mov     rax, [rbx+0A0h]
0x180003680  lea     r9, [rsp+68h+arg_0]
0x180003685  mov     r8d, 1
0x18000368b  mov     [rsp+68h+arg_0], rax
0x180003690  mov     edx, 40000004h
0x180003695  mov     [rsp+68h+var_48], 0
0x18000369d  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z; EVENT_LOG::LogEvent(ulong,ushort,char const * * const,ulong)
0x1800036a3  jmp     short loc_180003714
0x1800036a5  call    cs:__imp_GetLastError
0x1800036ab  mov     esi, eax
0x1800036ad  mov     rax, [rbx]
0x1800036b0  mov     rax, [rax+20h]
0x1800036b4  mov     rcx, rbx
0x1800036b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036bc  cmp     esi, 70h ; 'p'
0x1800036bf  jnz     short loc_180003714
0x1800036c1  cmp     dword ptr [rbx+164h], 0
0x1800036c8  jnz     short loc_180003706
0x1800036ca  mov     rcx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x1800036d1  lea     edx, [rsi-6Fh]
0x1800036d4  mov     [rbx+164h], edx
0x1800036da  test    rcx, rcx
0x1800036dd  jz      short loc_180003706
0x1800036df  mov     rax, [rbx+0A0h]
0x1800036e6  lea     r9, [rsp+68h+var_38]
0x1800036eb  mov     r8d, edx
0x1800036ee  mov     [rsp+68h+var_38], rax
0x1800036f3  mov     edx, 0C0000001h
0x1800036f8  mov     [rsp+68h+var_48], 0
0x180003700  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z; EVENT_LOG::LogEvent(ulong,ushort,char const * * const,ulong)
0x180003706  call    cs:__imp_GetTickCount
0x18000370c  add     eax, 0EA60h
0x180003711  mov     [rbx+74h], eax
0x180003714  mov     rcx, r15
0x180003717  lea     r11, [rsp+68h+var_28]
0x18000371c  mov     rbx, [r11+38h]
0x180003720  mov     rbp, [r11+40h]
0x180003724  mov     rsp, r11
0x180003727  pop     r15
0x180003729  pop     r14
0x18000372b  pop     r12
0x18000372d  pop     rdi
0x18000372e  pop     rsi
0x18000372f  jmp     cs:__imp_LeaveCriticalSection
```
