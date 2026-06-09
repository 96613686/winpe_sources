# CSmbFile::CompletionRoutine(ulong,ulong)

- ea: `0x180058450`
- end: `0x1800586e6`
- name: `?CompletionRoutine@CSmbFile@@IEAAXKK@Z`
- size: `662`
- prototype: `void __fastcall(CSmbFile *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180058350`

## callees

- `0x180058450`
- `0x18007db64`
- `0x18009e9c8`
- `0x1800ab7fc`
- `0x1800ee768`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800584bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005867f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800584bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005867f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800584ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005868d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800584ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005868d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800586a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800586a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058573`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058573`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058674`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058674`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800584b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058503`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800584b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180058503`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSmbFile::CompletionRoutine(CSmbFile *this, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  int v4; // r14d
  char v6; // bl
  int TickCount64; // edi
  HANDLE CurrentThread; // rax
  EVENT_LOG *v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rdx
  int v12; // eax
  int v13; // ecx
  HANDLE v14; // rax
  DWORD v15; // eax
  ComError *v16; // [rsp+30h] [rbp-48h] BYREF
  char v17[8]; // [rsp+38h] [rbp-40h] BYREF
  char *v18; // [rsp+40h] [rbp-38h]

  v3 = (unsigned int)a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_qdD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, this, a3, a2);
  v6 = 0;
  if ( !*((_BYTE *)this + 120) )
    goto LABEL_13;
  TickCount64 = GetTickCount64();
  CurrentThread = GetCurrentThread();
  if ( SetThreadPriority(CurrentThread, 0x10000) )
  {
    v6 = 1;
    v12 = GetTickCount64();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = v12 - TickCount64;
      v11 = 51;
      goto LABEL_12;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      v11 = 50;
      v9 = WPP_GLOBAL_Control;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v9 + 2), v11, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, LastError);
LABEL_13:
      v9 = WPP_GLOBAL_Control;
    }
  }
  v18 = (char *)this + 8;
  if ( *((_BYTE *)this + 48) && v9 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)v9 + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, (char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v17[0] = 1;
  v13 = *((_DWORD *)this + 102);
  if ( v13
    && *((_DWORD *)this + 52) != 1
    && (*((_BYTE *)this + 376) != 1 || *((_QWORD *)this + 20) + v3 != *((_QWORD *)this + 19)) )
  {
    LODWORD(v3) = v3 - v13;
    *((_DWORD *)this + 102) = 0;
  }
  if ( !v4 )
  {
    *((_DWORD *)this + 31) += v3 + *((_DWORD *)this + 43);
    if ( *((_BYTE *)this + 376) )
    {
      CAbstractFile::_OnReadCompleted(this, (unsigned int)v3);
    }
    else if ( *((_DWORD *)this + 32) == 1 )
    {
      *((_QWORD *)this + 20) += (unsigned int)v3;
      *((_QWORD *)this + 23) += (unsigned int)v3;
    }
  }
  try
  {
    (*(void (**)(void))(*(_QWORD *)this + 488LL))();
    if ( *((_BYTE *)this + 48)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids,
        (char *)this + 8);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( v6 )
    {
      v14 = GetCurrentThread();
      if ( !SetThreadPriority(v14, 0x20000)
        && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v15);
      }
    }
  }
  catch ( ComError *v16 )
  {
    v18 = (char *)this + 8;
    CCritSec2::enter((CSmbFile *)((char *)this + 8));
    v17[0] = 1;
    (*(void (__fastcall **)(CSmbFile *, _QWORD, _QWORD))(*(_QWORD *)this + 488LL))(this, *((unsigned int *)v16 + 6), 0);
    HoldCritSec::~HoldCritSec((HoldCritSec *)v17);
  }
}

```

## disassembly

```asm
0x180058450  mov     [rsp+arg_10], rbx
0x180058455  mov     [rsp+arg_0], rcx
0x18005845a  push    rsi
0x18005845b  push    rdi
0x18005845c  push    r12
0x18005845e  push    r14
0x180058460  push    r15
0x180058462  sub     rsp, 50h
0x180058466  mov     r15d, r8d
0x180058469  mov     r14d, edx
0x18005846c  mov     rsi, rcx
0x18005846f  lea     r12, WPP_GLOBAL_Control
0x180058476  mov     rcx, cs:WPP_GLOBAL_Control
0x18005847d  cmp     rcx, r12
0x180058480  jz      short loc_1800584A1
0x180058482  test    dword ptr [rcx+1Ch], 800h
0x180058489  jz      short loc_1800584A1
0x18005848b  mov     [rsp+78h+var_50], edx
0x18005848f  mov     [rsp+78h+var_58], r15d
0x180058494  mov     r9, rsi
0x180058497  mov     rcx, [rcx+10h]
0x18005849b  call    WPP_SF_qdD
0x1800584a0  nop
0x1800584a1  xor     bl, bl
0x1800584a3  mov     [rsp+78h+arg_8], bl
0x1800584aa  cmp     [rsi+78h], bl
0x1800584ad  jz      loc_180058534
0x1800584b3  call    cs:__imp_GetTickCount64
0x1800584b9  mov     rdi, rax
0x1800584bc  call    cs:__imp_GetCurrentThread
0x1800584c2  mov     rcx, rax; hThread
0x1800584c5  mov     edx, 10000h; nPriority
0x1800584ca  call    cs:__imp_SetThreadPriority
0x1800584d0  test    eax, eax
0x1800584d2  jnz     short loc_1800584FA
0x1800584d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800584db  cmp     rcx, r12
0x1800584de  jz      short loc_18005853B
0x1800584e0  test    byte ptr [rcx+1Ch], 2
0x1800584e4  jz      short loc_18005853B
0x1800584e6  call    cs:__imp_GetLastError
0x1800584ec  mov     edx, 32h ; '2'
0x1800584f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800584f8  jmp     short loc_180058521
0x1800584fa  mov     bl, 1
0x1800584fc  mov     [rsp+78h+arg_8], bl
0x180058503  call    cs:__imp_GetTickCount64
0x180058509  mov     rcx, cs:WPP_GLOBAL_Control
0x180058510  cmp     rcx, r12
0x180058513  jz      short loc_18005853B
0x180058515  test    [rcx+1Ch], bl
0x180058518  jz      short loc_18005853B
0x18005851a  sub     eax, edi
0x18005851c  mov     edx, 33h ; '3'
0x180058521  mov     r9d, eax
0x180058524  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x18005852b  mov     rcx, [rcx+10h]
0x18005852f  call    WPP_SF_d
0x180058534  mov     rcx, cs:WPP_GLOBAL_Control
0x18005853b  lea     rdi, [rsi+8]
0x18005853f  mov     [rsp+78h+var_38], rdi
0x180058544  cmp     byte ptr [rdi+28h], 0
0x180058548  jz      short loc_180058570
0x18005854a  cmp     rcx, r12
0x18005854d  jz      short loc_180058570
0x18005854f  test    dword ptr [rcx+1Ch], 100h
0x180058556  jz      short loc_180058570
0x180058558  mov     edx, 0Fh
0x18005855d  mov     r9, rdi
0x180058560  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180058567  mov     rcx, [rcx+10h]
0x18005856b  call    WPP_SF_q
0x180058570  mov     rcx, rdi; lpCriticalSection
0x180058573  call    cs:__imp_EnterCriticalSection
0x180058579  mov     [rsp+78h+var_40], 1
0x18005857e  mov     ecx, [rsi+198h]
0x180058584  test    ecx, ecx
0x180058586  jz      short loc_1800585BC
0x180058588  cmp     dword ptr [rsi+0D0h], 1
0x18005858f  jz      short loc_1800585BC
0x180058591  cmp     byte ptr [rsi+178h], 1
0x180058598  jnz     short loc_1800585AD
0x18005859a  mov     rax, r15
0x18005859d  add     rax, [rsi+0A0h]
0x1800585a4  cmp     rax, [rsi+98h]
0x1800585ab  jz      short loc_1800585BC
0x1800585ad  sub     r15d, ecx
0x1800585b0  xor     r9d, r9d
0x1800585b3  mov     [rsi+198h], r9d
0x1800585ba  jmp     short loc_1800585BF
0x1800585bc  xor     r9d, r9d
0x1800585bf  test    r14d, r14d
0x1800585c2  jnz     short loc_1800585FF
0x1800585c4  mov     eax, [rsi+0ACh]
0x1800585ca  add     eax, r15d
0x1800585cd  add     [rsi+7Ch], eax
0x1800585d0  mov     edx, r15d; unsigned __int64
0x1800585d3  cmp     [rsi+178h], r14b
0x1800585da  jz      short loc_1800585E6
0x1800585dc  mov     rcx, rsi; this
0x1800585df  call    ?_OnReadCompleted@CAbstractFile@@IEAAX_K@Z; CAbstractFile::_OnReadCompleted(unsigned __int64)
0x1800585e4  jmp     short loc_180058625
0x1800585e6  cmp     dword ptr [rsi+80h], 1
0x1800585ed  jnz     short loc_180058625
0x1800585ef  add     [rsi+0A0h], rdx
0x1800585f6  add     [rsi+0B8h], rdx
0x1800585fd  jmp     short loc_180058625
0x1800585ff  cmp     r14d, 0C000026Eh
0x180058606  jnz     short loc_180058610
0x180058608  mov     r9d, 8020000Dh
0x18005860e  jmp     short loc_180058625
0x180058610  test    r14d, r14d
0x180058613  jg      short loc_18005861A
0x180058615  mov     r9d, r14d
0x180058618  jmp     short loc_180058625
0x18005861a  movzx   r9d, r14w
0x18005861e  or      r9d, 80070000h
0x180058625  mov     rax, [rsi]
0x180058628  mov     r8d, r15d
0x18005862b  mov     edx, r9d
0x18005862e  mov     rcx, rsi
0x180058631  mov     rax, [rax+1E8h]
0x180058638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005863d  nop
0x18005863e  cmp     byte ptr [rdi+28h], 0
0x180058642  jz      short loc_180058671
0x180058644  mov     rcx, cs:WPP_GLOBAL_Control
0x18005864b  cmp     rcx, r12
0x18005864e  jz      short loc_180058671
0x180058650  test    dword ptr [rcx+1Ch], 100h
0x180058657  jz      short loc_180058671
0x180058659  mov     edx, 10h
0x18005865e  mov     r9, rdi
0x180058661  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180058668  mov     rcx, [rcx+10h]
0x18005866c  call    WPP_SF_q
0x180058671  mov     rcx, rdi; lpCriticalSection
0x180058674  call    cs:__imp_LeaveCriticalSection
0x18005867a  nop
0x18005867b  test    bl, bl
0x18005867d  jz      short loc_1800586CF
0x18005867f  call    cs:__imp_GetCurrentThread
0x180058685  mov     rcx, rax; hThread
0x180058688  mov     edx, 20000h; nPriority
0x18005868d  call    cs:__imp_SetThreadPriority
0x180058693  test    eax, eax
0x180058695  jnz     short loc_1800586CF
0x180058697  mov     rax, cs:WPP_GLOBAL_Control
0x18005869e  cmp     rax, r12
0x1800586a1  jz      short loc_1800586CF
0x1800586a3  test    byte ptr [rax+1Ch], 2
0x1800586a7  jz      short loc_1800586CF
0x1800586a9  call    cs:__imp_GetLastError
0x1800586af  mov     edx, 34h ; '4'
0x1800586b4  mov     r9d, eax
0x1800586b7  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x1800586be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800586c5  mov     rcx, [rcx+10h]
0x1800586c9  call    WPP_SF_d
0x1800586ce  nop
0x1800586cf  jmp     short $+2
0x1800586d1  mov     rbx, [rsp+78h+arg_10]
0x1800586d9  add     rsp, 50h
0x1800586dd  pop     r15
0x1800586df  pop     r14
0x1800586e1  pop     r12
0x1800586e3  pop     rdi
0x1800586e4  pop     rsi
0x1800586e5  retn
```
