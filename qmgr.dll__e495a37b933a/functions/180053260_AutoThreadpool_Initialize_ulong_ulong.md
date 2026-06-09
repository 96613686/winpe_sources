# AutoThreadpool::Initialize(ulong,ulong)

- ea: `0x180053260`
- end: `0x180053525`
- name: `?Initialize@AutoThreadpool@@QEAAJKK@Z`
- size: `709`
- prototype: `__int64 __fastcall(AutoThreadpool *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180052f90`
- `0x1800b3aa0`
- `0x1800e9230`

## callees

- `0x180033480`
- `0x180053260`
- `0x180063e30`
- `0x18009d024`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800532f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005330a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005339a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800532f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005330a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005339a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053438`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800532cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800532cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800534f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800534f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180053414`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180053414`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800532e9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800532e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180053390`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180053390`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005340e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005340e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoThreadpool::Initialize(AutoThreadpool *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct _TP_POOL *Threadpool; // rax
  unsigned int LastError; // eax
  unsigned int v5; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  unsigned int v7; // eax
  EVENT_LOG *v8; // rcx
  const ComError *v10; // rbx
  const ComError *v11; // [rsp+30h] [rbp-158h] BYREF
  char v12[8]; // [rsp+38h] [rbp-150h] BYREF
  char *v13; // [rsp+40h] [rbp-148h]
  void **pExceptionObject; // [rsp+50h] [rbp-138h] BYREF
  __int128 v15; // [rsp+58h] [rbp-130h]
  unsigned int v16; // [rsp+68h] [rbp-120h]
  int v17; // [rsp+6Ch] [rbp-11Ch]
  int v18; // [rsp+70h] [rbp-118h]
  void **v19; // [rsp+B0h] [rbp-D8h] BYREF
  __int128 v20; // [rsp+B8h] [rbp-D0h]
  unsigned int v21; // [rsp+C8h] [rbp-C0h]
  int v22; // [rsp+CCh] [rbp-BCh]
  int v23; // [rsp+D0h] [rbp-B8h]
  void **v24; // [rsp+110h] [rbp-78h] BYREF
  __int128 v25; // [rsp+118h] [rbp-70h]
  unsigned int v26; // [rsp+128h] [rbp-60h]
  int v27; // [rsp+12Ch] [rbp-5Ch]
  int v28; // [rsp+130h] [rbp-58h]
  unsigned int v30; // [rsp+1A0h] [rbp+18h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v13 = (char *)this + 8;
  if ( *((_BYTE *)this + 48)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v2);
  }
  EnterCriticalSection(v2);
  v12[0] = 1;
  if ( *((_QWORD *)this + 7) )
    AutoThreadpool::UninitializeAndWaitForPendingWorkItems(this);
  Threadpool = CreateThreadpool(0);
  try
  {
    *((_QWORD *)this + 7) = Threadpool;
    if ( !Threadpool )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = LastError;
      v17 = 43;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    *((_DWORD *)this + 16) = 3;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 14) = 0;
    *((_DWORD *)this + 30) = 0;
    *((_DWORD *)this + 31) = 1;
    *((_DWORD *)this + 32) = 72;
    *((_QWORD *)this + 9) = Threadpool;
    if ( !SetThreadpoolThreadMinimum(Threadpool, 1u) )
    {
      if ( (int)GetLastError() > 0 )
        v5 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v5 = GetLastError();
      v20 = 0;
      v19 = &ComError::`vftable';
      v21 = v5;
      v22 = 51;
      v23 = 1;
      throw (ComError *)&v19;
    }
    SetThreadpoolThreadMaximum(*((PTP_POOL *)this + 7), 1u);
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *((_QWORD *)this + 17) = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
    {
      if ( (int)GetLastError() > 0 )
        v7 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v7 = GetLastError();
      v25 = 0;
      v24 = &ComError::`vftable';
      v26 = v7;
      v27 = 59;
      v28 = 1;
      throw (ComError *)&v24;
    }
    *((_QWORD *)this + 10) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 11) = 0;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7a43e90641713c5942580354798d2ea8_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
  }
  catch ( const ComError *v11 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v10 = v11;
    }
    else
    {
      v10 = v11;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_7a43e90641713c5942580354798d2ea8_Traceguids,
        *((unsigned int *)v10 + 6),
        *((_DWORD *)v10 + 7));
    }
    AutoThreadpool::UninitializeAndWaitForPendingWorkItems(this);
    v30 = *((_DWORD *)v10 + 6);
    HoldCritSec::~HoldCritSec((HoldCritSec *)v12);
    return v30;
  }
  if ( LOBYTE(v2[1].DebugInfo) && v8 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)v8 + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v2);
  LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x180053260  mov     [rsp+arg_8], rbx
0x180053265  mov     [rsp+arg_10], r8d
0x18005326a  mov     [rsp+arg_0], rcx
0x18005326f  push    rsi
0x180053270  push    rdi
0x180053271  push    r14
0x180053273  sub     rsp, 170h
0x18005327a  mov     rbx, rcx
0x18005327d  lea     rdi, [rcx+8]
0x180053281  mov     [rsp+188h+var_148], rdi
0x180053286  cmp     byte ptr [rdi+28h], 0
0x18005328a  jz      short loc_1800532C2
0x18005328c  lea     rsi, WPP_GLOBAL_Control
0x180053293  mov     rcx, cs:WPP_GLOBAL_Control
0x18005329a  cmp     rcx, rsi
0x18005329d  jz      short loc_1800532C9
0x18005329f  test    dword ptr [rcx+1Ch], 100h
0x1800532a6  jz      short loc_1800532C9
0x1800532a8  mov     edx, 0Fh
0x1800532ad  mov     r9, rdi
0x1800532b0  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800532b7  mov     rcx, [rcx+10h]
0x1800532bb  call    WPP_SF_q
0x1800532c0  jmp     short loc_1800532C9
0x1800532c2  lea     rsi, WPP_GLOBAL_Control
0x1800532c9  mov     rcx, rdi; lpCriticalSection
0x1800532cc  call    cs:__imp_EnterCriticalSection
0x1800532d2  mov     [rsp+188h+var_150], 1
0x1800532d7  cmp     qword ptr [rbx+38h], 0
0x1800532dc  jz      short loc_1800532E7
0x1800532de  mov     rcx, rbx; this
0x1800532e1  call    ?UninitializeAndWaitForPendingWorkItems@AutoThreadpool@@QEAAXXZ; AutoThreadpool::UninitializeAndWaitForPendingWorkItems(void)
0x1800532e6  nop
0x1800532e7  xor     ecx, ecx; reserved
0x1800532e9  call    cs:__imp_CreateThreadpool
0x1800532ef  mov     [rbx+38h], rax
0x1800532f3  test    rax, rax
0x1800532f6  jnz     short loc_180053351
0x1800532f8  call    cs:__imp_GetLastError
0x1800532fe  test    eax, eax
0x180053300  jg      short loc_18005330A
0x180053302  call    cs:__imp_GetLastError
0x180053308  jmp     short loc_180053318
0x18005330a  call    cs:__imp_GetLastError
0x180053310  movzx   eax, ax
0x180053313  or      eax, 80070000h
0x180053318  xorps   xmm0, xmm0
0x18005331b  movups  [rsp+188h+var_130], xmm0
0x180053320  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180053327  mov     [rsp+188h+pExceptionObject], rcx
0x18005332c  mov     [rsp+188h+var_120], eax
0x180053330  mov     [rsp+188h+var_11C], 2Bh ; '+'
0x180053338  mov     [rsp+188h+var_118], 1
0x180053340  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180053347  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18005334c  call    _CxxThrowException_0
0x180053351  mov     dword ptr [rbx+40h], 3
0x180053358  xor     r14d, r14d
0x18005335b  mov     [rbx+50h], r14
0x18005335f  mov     [rbx+58h], r14
0x180053363  mov     [rbx+60h], r14
0x180053367  mov     [rbx+68h], r14
0x18005336b  mov     [rbx+70h], r14
0x18005336f  mov     [rbx+78h], r14d
0x180053373  mov     dword ptr [rbx+7Ch], 1
0x18005337a  mov     dword ptr [rbx+80h], 48h ; 'H'
0x180053384  mov     rcx, rax; ptpp
0x180053387  mov     [rbx+48h], rax
0x18005338b  mov     edx, 1; cthrdMic
0x180053390  call    cs:__imp_SetThreadpoolThreadMinimum
0x180053396  test    eax, eax
0x180053398  jnz     short loc_180053405
0x18005339a  call    cs:__imp_GetLastError
0x1800533a0  test    eax, eax
0x1800533a2  jg      short loc_1800533AC
0x1800533a4  call    cs:__imp_GetLastError
0x1800533aa  jmp     short loc_1800533BA
0x1800533ac  call    cs:__imp_GetLastError
0x1800533b2  movzx   eax, ax
0x1800533b5  or      eax, 80070000h
0x1800533ba  xorps   xmm0, xmm0
0x1800533bd  movups  [rsp+188h+var_D0], xmm0
0x1800533c5  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800533cc  mov     [rsp+188h+var_D8], rcx
0x1800533d4  mov     [rsp+188h+var_C0], eax
0x1800533db  mov     [rsp+188h+var_BC], 33h ; '3'
0x1800533e6  mov     [rsp+188h+var_B8], 1
0x1800533f1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800533f8  lea     rcx, [rsp+188h+var_D8]; pExceptionObject
0x180053400  call    _CxxThrowException_0
0x180053405  mov     edx, 1; cthrdMost
0x18005340a  mov     rcx, [rbx+38h]; ptpp
0x18005340e  call    cs:__imp_SetThreadpoolThreadMaximum
0x180053414  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18005341a  mov     [rbx+88h], rax
0x180053421  test    rax, rax
0x180053424  jnz     short loc_180053491
0x180053426  call    cs:__imp_GetLastError
0x18005342c  test    eax, eax
0x18005342e  jg      short loc_180053438
0x180053430  call    cs:__imp_GetLastError
0x180053436  jmp     short loc_180053446
0x180053438  call    cs:__imp_GetLastError
0x18005343e  movzx   eax, ax
0x180053441  or      eax, 80070000h
0x180053446  xorps   xmm0, xmm0
0x180053449  movups  [rsp+188h+var_70], xmm0
0x180053451  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180053458  mov     [rsp+188h+var_78], rcx
0x180053460  mov     [rsp+188h+var_60], eax
0x180053467  mov     [rsp+188h+var_5C], 3Bh ; ';'
0x180053472  mov     [rsp+188h+var_58], 1
0x18005347d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180053484  lea     rcx, [rsp+188h+var_78]; pExceptionObject
0x18005348c  call    _CxxThrowException_0
0x180053491  mov     [rbx+50h], rax
0x180053495  mov     [rbx+58h], r14
0x180053499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800534a0  cmp     rcx, rsi
0x1800534a3  jz      short loc_1800534C7
0x1800534a5  test    byte ptr [rcx+1Ch], 1
0x1800534a9  jz      short loc_1800534C7
0x1800534ab  mov     edx, 0Ah
0x1800534b0  lea     r8, WPP_7a43e90641713c5942580354798d2ea8_Traceguids
0x1800534b7  mov     rcx, [rcx+10h]
0x1800534bb  call    WPP_SF_
0x1800534c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800534c7  cmp     byte ptr [rdi+28h], 0
0x1800534cb  jz      short loc_1800534F3
0x1800534cd  cmp     rcx, rsi
0x1800534d0  jz      short loc_1800534F3
0x1800534d2  test    dword ptr [rcx+1Ch], 100h
0x1800534d9  jz      short loc_1800534F3
0x1800534db  mov     edx, 10h
0x1800534e0  mov     r9, rdi
0x1800534e3  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800534ea  mov     rcx, [rcx+10h]
0x1800534ee  call    WPP_SF_q
0x1800534f3  mov     rcx, rdi; lpCriticalSection
0x1800534f6  call    cs:__imp_LeaveCriticalSection
0x1800534fc  xor     eax, eax
0x1800534fe  jmp     short loc_180053511
0x180053500  lea     rcx, [rsp+188h+var_150]; this
0x180053505  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18005350a  mov     eax, [rsp+188h+arg_10]
0x180053511  mov     rbx, [rsp+188h+arg_8]
0x180053519  add     rsp, 170h
0x180053520  pop     r14
0x180053522  pop     rdi
0x180053523  pop     rsi
0x180053524  retn
```
