# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007474`
- end: `0x18000777f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180005ec0`
- `0x180006224`

## callees

- `0x180004d88`
- `0x180005e08`
- `0x180006cd4`
- `0x180007474`
- `0x180007b30`
- `0x180007b50`
- `0x180007b64`
- `0x180007b84`
- `0x1800083d8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007597`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007734`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007734`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076bc`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180007474  mov     [rsp+arg_10], rbx
0x180007479  mov     [rsp+arg_8], edx
0x18000747d  mov     [rsp+arg_0], rcx
0x180007482  push    rbp
0x180007483  push    rsi
0x180007484  push    rdi
0x180007485  push    r12
0x180007487  push    r13
0x180007489  push    r14
0x18000748b  push    r15
0x18000748d  sub     rsp, 40h
0x180007491  mov     r14, [rsp+78h+arg_38]
0x180007499  xor     eax, eax
0x18000749b  mov     rbx, [rsp+78h+arg_78]
0x1800074a3  xor     ebp, ebp
0x1800074a5  mov     r15d, [rsp+78h+arg_30]
0x1800074ad  mov     r10, rcx
0x1800074b0  mov     rsi, [rsp+78h+lpOutputString]
0x1800074b8  mov     r12, r9
0x1800074bb  mov     r13, r8
0x1800074be  mov     ecx, r15d
0x1800074c1  mov     [rsi], ax
0x1800074c4  mov     rax, [rsp+78h+arg_60]
0x1800074cc  mov     byte ptr [rax], 0
0x1800074cf  mov     edi, [r14]
0x1800074d2  mov     [rbx+8], edi
0x1800074d5  mov     eax, [r14+4]
0x1800074d9  mov     [rbx+0Ch], eax
0x1800074dc  test    r15d, r15d
0x1800074df  jz      short loc_180007547
0x1800074e1  sub     ecx, 1
0x1800074e4  jz      short loc_18000753E
0x1800074e6  sub     ecx, 1
0x1800074e9  jz      short loc_1800074F9
0x1800074eb  cmp     ecx, 1
0x1800074ee  jnz     short loc_180007550
0x1800074f0  mov     ecx, edi; this
0x1800074f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800074f7  jmp     short loc_18000754E
0x1800074f9  test    edi, edi
0x1800074fb  js      short loc_180007535
0x1800074fd  mov     rax, [rsp+78h+arg_28]
0x180007505  mov     edi, 8007029Ch
0x18000750a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000750e  mov     rcx, r10; int
0x180007511  mov     [rsp+78h+var_50], rax; __int64
0x180007516  mov     rax, [rsp+78h+arg_20]
0x18000751e  mov     [rsp+78h+var_58], rax; __int64
0x180007523  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007528  mov     ecx, edi; this
0x18000752a  mov     [rbx+8], edi
0x18000752d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007532  mov     [rbx+0Ch], eax
0x180007535  mov     ecx, edi; this
0x180007537  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000753c  jmp     short loc_18000754E
0x18000753e  mov     ecx, edi; this
0x180007540  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007545  jmp     short loc_18000754E
0x180007547  mov     ecx, edi; this
0x180007549  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000754e  mov     ebp, eax
0x180007550  mov     eax, [rsp+78h+arg_70]
0x180007557  mov     [rbx+4], eax
0x18000755a  mov     [rbx], r15d
0x18000755d  cmp     dword ptr [r14+8], 1
0x180007562  jnz     short loc_18000756A
0x180007564  or      eax, 8
0x180007567  mov     [rbx+4], eax
0x18000756a  mov     eax, 1
0x18000756f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007577  inc     eax
0x180007579  xor     edi, edi
0x18000757b  mov     [rbx+10h], eax
0x18000757e  mov     rax, [rsp+78h+arg_40]
0x180007586  test    rax, rax
0x180007589  jz      short loc_180007590
0x18000758b  cmp     [rax], di
0x18000758e  jnz     short loc_180007593
0x180007590  mov     rax, rdi
0x180007593  mov     [rbx+18h], rax
0x180007597  call    cs:__imp_GetCurrentThreadId
0x18000759e  nop     dword ptr [rax+rax+00h]
0x1800075a3  mov     [rbx+38h], r13
0x1800075a7  xorps   xmm0, xmm0
0x1800075aa  mov     [rbx+20h], eax
0x1800075ad  mov     eax, [rsp+78h+arg_8]
0x1800075b4  mov     [rbx+40h], eax
0x1800075b7  mov     rax, [rsp+78h+arg_20]
0x1800075bf  mov     [rbx+28h], rax
0x1800075c3  mov     rax, [rsp+78h+arg_28]
0x1800075cb  mov     [rbx+88h], rax
0x1800075d2  mov     rax, [rsp+78h+arg_0]
0x1800075da  mov     [rbx+90h], rax
0x1800075e1  xor     eax, eax
0x1800075e3  mov     [rbx+44h], ebp
0x1800075e6  mov     [rbx+30h], r12
0x1800075ea  mov     [rbx+48h], rdi
0x1800075ee  movups  xmmword ptr [rbx+68h], xmm0
0x1800075f2  mov     [rbx+78h], rax
0x1800075f6  movups  xmmword ptr [rbx+50h], xmm0
0x1800075fa  mov     [rbx+60h], rax
0x1800075fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007605  test    rax, rax
0x180007608  jz      short loc_180007611
0x18000760a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000760f  jmp     short loc_180007614
0x180007611  mov     rax, rdi
0x180007614  mov     [rbx+80h], rax
0x18000761b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007622  test    rax, rax
0x180007625  jz      short loc_18000762F
0x180007627  mov     rcx, rbx
0x18000762a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000762f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007636  test    rax, rax
0x180007639  jz      short loc_180007651
0x18000763b  mov     rdx, [rsp+78h+arg_60]
0x180007643  mov     r8d, 400h
0x180007649  mov     rcx, rbx
0x18000764c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007651  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007658  test    rax, rax
0x18000765b  jz      short loc_180007665
0x18000765d  mov     rcx, rbx
0x180007660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007665  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000766c  test    rax, rax
0x18000766f  jz      short loc_18000767F
0x180007671  test    byte ptr [rbx+4], 2
0x180007675  jnz     short loc_18000767F
0x180007677  mov     rcx, rbx
0x18000767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767f  cmp     [rbx+8], edi
0x180007682  jl      short loc_18000769E
0x180007684  cmp     r15d, 3
0x180007688  jnz     loc_180007779
0x18000768e  mov     ecx, 8000FFFFh; this
0x180007693  mov     [rbx+8], ecx
0x180007696  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000769b  mov     [rbx+0Ch], eax
0x18000769e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800076a5  jnz     short loc_1800076CC
0x1800076a7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800076ae  test    rax, rax
0x1800076b1  jz      short loc_1800076BC
0x1800076b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b8  test    al, al
0x1800076ba  jmp     short loc_1800076CA
0x1800076bc  call    cs:__imp_IsDebuggerPresent
0x1800076c3  nop     dword ptr [rax+rax+00h]
0x1800076c8  test    eax, eax
0x1800076ca  jz      short loc_1800076D2
0x1800076cc  test    byte ptr [rbx+4], 2
0x1800076d0  jz      short loc_1800076F6
0x1800076d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076d9  test    rax, rax
0x1800076dc  jz      short loc_180007740
0x1800076de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800076e5  jnz     short loc_180007740
0x1800076e7  xor     r8d, r8d
0x1800076ea  xor     edx, edx
0x1800076ec  mov     rcx, rbx
0x1800076ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f4  jmp     short loc_180007740
0x1800076f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076fd  mov     ebp, 800h
0x180007702  test    rax, rax
0x180007705  jz      short loc_18000771E
0x180007707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000770e  jnz     short loc_18000771E
0x180007710  mov     r8d, ebp
0x180007713  mov     rdx, rsi
0x180007716  mov     rcx, rbx
0x180007719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771e  cmp     [rsi], di
0x180007721  jnz     short loc_180007731
0x180007723  mov     r8, rbx; unsigned __int64
0x180007726  mov     rdx, rbp; unsigned __int16 *
0x180007729  mov     rcx, rsi; this
0x18000772c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007731  mov     rcx, rsi; lpOutputString
0x180007734  call    cs:__imp_OutputDebugStringW
0x18000773b  nop     dword ptr [rax+rax+00h]
0x180007740  test    byte ptr [rbx+4], 4
0x180007744  jnz     short loc_18000774F
0x180007746  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000774d  jz      short loc_180007760
0x18000774f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007756  test    rax, rax
0x180007759  jz      short loc_180007760
0x18000775b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007760  mov     rbx, [rsp+78h+arg_10]
0x180007768  add     rsp, 40h
0x18000776c  pop     r15
0x18000776e  pop     r14
0x180007770  pop     r13
0x180007772  pop     r12
0x180007774  pop     rdi
0x180007775  pop     rsi
0x180007776  pop     rbp
0x180007777  retn
0x180007779  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
