# QTableEntry::StartTimer(ushort const *,ushort)

- ea: `0x180019548`
- end: `0x18001970d`
- name: `?StartTimer@QTableEntry@@QEAAJPEBGG@Z`
- size: `453`
- prototype: `__int64 __fastcall(QTableEntry *this, const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800194b8`

## callees

- `0x180008b00`
- `0x180019548`
- `0x180019720`
- `0x180046ec0`
- `0x180086ab0`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019671`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001962d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001962d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800195ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800195ea`

## pseudocode

```c
__int64 __fastcall QTableEntry::StartTimer(QTableEntry *this, const unsigned __int16 *a2, __int16 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  unsigned int v9; // ebx
  DWORD LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-18h] BYREF

  pftDueTime = 0;
  if ( a2 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_Sd(1035, 16, (unsigned int)WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, (_DWORD)a2, a3);
    v6 = StringCchCopyW((unsigned __int16 *)this + 44, (unsigned __int64)a2, a2);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 17, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, (unsigned int)v6);
      v9 = WX_WIN32_FROM_HR(v7);
    }
    else
    {
      *((_QWORD *)this + 76) = *((_QWORD *)this + 5);
      *((_DWORD *)this + 154) = *((_DWORD *)this + 6);
      *((_DWORD *)this + 156) = *((_DWORD *)this + 7);
      *((_DWORD *)this + 157) = *((_DWORD *)this + 8);
      *((_WORD *)this + 300) = a3;
      *((_DWORD *)this + 155) = 1;
      ThreadpoolTimer = CreateThreadpoolTimer(ContinuousQuery_TimerCallback, (char *)this + 88, 0);
      *((_QWORD *)this + 10) = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        v9 = 0;
        if ( *((_DWORD *)this + 8) )
          pftDueTime = (struct _FILETIME)-4100000LL;
        else
          pftDueTime = (struct _FILETIME)(-10000000LL * (unsigned int)g_ContinuousQueryTimerIntervals);
        SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          return v9;
        WPP_SF_d(1035, 18, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, LastError);
      }
    }
  }
  else
  {
    v9 = 87;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 19, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180019548  mov     [rsp+arg_10], rbx
0x18001954d  mov     [rsp+arg_18], rsi
0x180019552  push    rdi
0x180019553  sub     rsp, 40h
0x180019557  mov     rax, cs:__security_cookie
0x18001955e  xor     rax, rsp
0x180019561  mov     [rsp+48h+var_10], rax
0x180019566  movzx   esi, r8w
0x18001956a  mov     rbx, rdx
0x18001956d  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0
0x180019576  mov     rdi, rcx
0x180019579  test    rdx, rdx
0x18001957c  jz      loc_18001966A
0x180019582  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180019589  jnz     loc_18001969D
0x18001958f  mov     r8, rbx; unsigned __int16 *
0x180019592  lea     rcx, [rdi+58h]; unsigned __int16 *
0x180019596  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001959b  mov     ebx, eax
0x18001959d  test    eax, eax
0x18001959f  js      loc_1800196BF
0x1800195a5  mov     rax, [rdi+28h]
0x1800195a9  lea     rdx, [rdi+58h]; pv
0x1800195ad  mov     [rdi+260h], rax
0x1800195b4  lea     rcx, ContinuousQuery_TimerCallback; pfnti
0x1800195bb  mov     eax, [rdi+18h]
0x1800195be  xor     r8d, r8d; pcbe
0x1800195c1  mov     [rdi+268h], eax
0x1800195c7  mov     eax, [rdi+1Ch]
0x1800195ca  mov     [rdi+270h], eax
0x1800195d0  mov     eax, [rdi+20h]
0x1800195d3  mov     [rdi+274h], eax
0x1800195d9  mov     [rdi+258h], si
0x1800195e0  mov     dword ptr [rdi+26Ch], 1
0x1800195ea  call    cs:__imp_CreateThreadpoolTimer
0x1800195f0  mov     [rdi+50h], rax
0x1800195f4  mov     r10, rax
0x1800195f7  test    rax, rax
0x1800195fa  jz      short loc_180019671
0x1800195fc  xor     ebx, ebx
0x1800195fe  cmp     [rdi+20h], ebx
0x180019601  jnz     short loc_18001965F
0x180019603  mov     eax, cs:?g_ContinuousQueryTimerIntervals@@3PAKA; ulong near * g_ContinuousQueryTimerIntervals
0x180019609  imul    rax, 0FFFFFFFFFF676980h
0x180019610  mov     rcx, rax
0x180019613  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x180019617  shr     rcx, 20h
0x18001961b  mov     [rsp+48h+pftDueTime.dwHighDateTime], ecx
0x18001961f  xor     r9d, r9d; msWindowLength
0x180019622  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180019627  xor     r8d, r8d; msPeriod
0x18001962a  mov     rcx, r10; pti
0x18001962d  call    cs:__imp_SetThreadpoolTimer
0x180019633  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001963a  jnz     loc_1800196EF
0x180019640  mov     eax, ebx
0x180019642  mov     rcx, [rsp+48h+var_10]
0x180019647  xor     rcx, rsp; StackCookie
0x18001964a  call    __security_check_cookie
0x18001964f  mov     rbx, [rsp+48h+arg_10]
0x180019654  mov     rsi, [rsp+48h+arg_18]
0x180019659  add     rsp, 40h
0x18001965d  pop     rdi
0x18001965e  retn
0x18001965f  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFC17060h
0x180019668  jmp     short loc_18001961F
0x18001966a  mov     ebx, 57h ; 'W'
0x18001966f  jmp     short loc_180019633
0x180019671  call    cs:__imp_GetLastError
0x180019677  mov     ebx, eax
0x180019679  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180019680  jz      short loc_180019640
0x180019682  mov     edx, 12h
0x180019687  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x18001968e  mov     ecx, 40Bh
0x180019693  mov     r9d, eax
0x180019696  call    WPP_SF_d
0x18001969b  jmp     short loc_180019633
0x18001969d  mov     edx, 10h
0x1800196a2  mov     [rsp+48h+var_28], esi
0x1800196a6  mov     ecx, 40Bh
0x1800196ab  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x1800196b2  mov     r9, rbx
0x1800196b5  call    WPP_SF_Sd
0x1800196ba  jmp     loc_18001958F
0x1800196bf  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800196c6  jz      short loc_1800196E1
0x1800196c8  mov     edx, 11h
0x1800196cd  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x1800196d4  mov     ecx, 40Bh
0x1800196d9  mov     r9d, ebx
0x1800196dc  call    WPP_SF_d
0x1800196e1  mov     ecx, ebx
0x1800196e3  call    WX_WIN32_FROM_HR
0x1800196e8  mov     ebx, eax
0x1800196ea  jmp     loc_180019633
0x1800196ef  mov     edx, 13h
0x1800196f4  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x1800196fb  mov     ecx, 40Bh
0x180019700  mov     r9d, ebx
0x180019703  call    WPP_SF_d
0x180019708  jmp     loc_180019640
```
