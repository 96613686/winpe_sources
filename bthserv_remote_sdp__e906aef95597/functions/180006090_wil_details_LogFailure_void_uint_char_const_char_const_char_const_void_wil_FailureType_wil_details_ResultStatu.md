# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x180006090`
- end: `0x1800063a0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000359c`

## callees

- `0x180002f80`
- `0x1800055c4`
- `0x180005de4`
- `0x180006090`
- `0x180006e7c`
- `0x180006ea0`
- `0x180007000`
- `0x180007020`
- `0x180009934`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800062d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800062d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006354`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006354`

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
        unsigned __int64 a15)
{
  unsigned int v17; // edi
  int v18; // esi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  int IsDebuggerPresent; // ecx
  wil::details *v27; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  *(_DWORD *)(a15 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 64) = a2;
  *(_DWORD *)(a15 + 68) = v18;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && (*(_BYTE *)(a15 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048, v24);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a15, 0, 0, v24);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180006090  mov     [rsp+arg_10], rbx
0x180006095  mov     [rsp+arg_8], edx
0x180006099  mov     [rsp+arg_0], rcx
0x18000609e  push    rbp
0x18000609f  push    rsi
0x1800060a0  push    rdi
0x1800060a1  push    r12
0x1800060a3  push    r13
0x1800060a5  push    r14
0x1800060a7  push    r15
0x1800060a9  sub     rsp, 40h
0x1800060ad  mov     r12, r9
0x1800060b0  mov     r13, r8
0x1800060b3  mov     r10, rcx
0x1800060b6  xor     r8d, r8d
0x1800060b9  mov     r14, [rsp+78h+lpOutputString]
0x1800060c1  mov     [r14], r8w
0x1800060c5  mov     rax, [rsp+78h+arg_60]
0x1800060cd  mov     [rax], r8b
0x1800060d0  mov     rbx, [rsp+78h+arg_70]
0x1800060d8  mov     r15, [rsp+78h+arg_38]
0x1800060e0  mov     edi, [r15]
0x1800060e3  mov     [rbx+8], edi
0x1800060e6  mov     eax, [r15+4]
0x1800060ea  mov     [rbx+0Ch], eax
0x1800060ed  mov     esi, r8d
0x1800060f0  mov     ebp, [rsp+78h+arg_30]
0x1800060f7  mov     ecx, ebp
0x1800060f9  test    ebp, ebp
0x1800060fb  jz      short loc_180006166
0x1800060fd  sub     ecx, 1
0x180006100  jz      short loc_18000615D
0x180006102  sub     ecx, 1
0x180006105  jz      short loc_180006115
0x180006107  cmp     ecx, 1
0x18000610a  jnz     short loc_18000616F
0x18000610c  mov     ecx, edi; this
0x18000610e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006113  jmp     short loc_18000616D
0x180006115  test    edi, edi
0x180006117  js      short loc_180006154
0x180006119  mov     edi, 8007029Ch
0x18000611e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006122  mov     rax, [rsp+78h+arg_28]
0x18000612a  mov     [rsp+78h+var_50], rax; __int64
0x18000612f  mov     rax, [rsp+78h+arg_20]
0x180006137  mov     [rsp+78h+var_58], rax; __int64
0x18000613c  mov     r8, r13; int
0x18000613f  mov     rcx, r10; int
0x180006142  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180006147  mov     [rbx+8], edi
0x18000614a  mov     ecx, edi; this
0x18000614c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006151  mov     [rbx+0Ch], eax
0x180006154  mov     ecx, edi; this
0x180006156  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000615b  jmp     short loc_18000616D
0x18000615d  mov     ecx, edi; this
0x18000615f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006164  jmp     short loc_18000616D
0x180006166  mov     ecx, edi; this
0x180006168  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000616d  mov     esi, eax
0x18000616f  mov     [rbx], ebp
0x180006171  xor     edi, edi
0x180006173  mov     [rbx+4], edi
0x180006176  cmp     dword ptr [r15+8], 1
0x18000617b  jnz     short loc_180006184
0x18000617d  mov     dword ptr [rbx+4], 8
0x180006184  mov     eax, 1
0x180006189  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180006191  inc     eax
0x180006193  mov     [rbx+10h], eax
0x180006196  mov     rax, [rsp+78h+arg_40]
0x18000619e  test    rax, rax
0x1800061a1  jz      short loc_1800061A8
0x1800061a3  cmp     [rax], di
0x1800061a6  jnz     short loc_1800061AB
0x1800061a8  mov     rax, rdi
0x1800061ab  mov     [rbx+18h], rax
0x1800061af  call    cs:__imp_GetCurrentThreadId
0x1800061b6  nop     dword ptr [rax+rax+00h]
0x1800061bb  mov     [rbx+20h], eax
0x1800061be  mov     [rbx+38h], r13
0x1800061c2  mov     eax, [rsp+78h+arg_8]
0x1800061c9  mov     [rbx+40h], eax
0x1800061cc  mov     [rbx+44h], esi
0x1800061cf  mov     rax, [rsp+78h+arg_20]
0x1800061d7  mov     [rbx+28h], rax
0x1800061db  mov     [rbx+30h], r12
0x1800061df  mov     rax, [rsp+78h+arg_28]
0x1800061e7  mov     [rbx+88h], rax
0x1800061ee  mov     rax, [rsp+78h+arg_0]
0x1800061f6  mov     [rbx+90h], rax
0x1800061fd  mov     [rbx+48h], rdi
0x180006201  xorps   xmm0, xmm0
0x180006204  xor     eax, eax
0x180006206  movups  xmmword ptr [rbx+68h], xmm0
0x18000620a  mov     [rbx+78h], rax
0x18000620e  movups  xmmword ptr [rbx+50h], xmm0
0x180006212  mov     [rbx+60h], rax
0x180006216  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000621d  test    rax, rax
0x180006220  jz      short loc_180006229
0x180006222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006227  jmp     short loc_18000622C
0x180006229  mov     rax, rdi
0x18000622c  mov     [rbx+80h], rax
0x180006233  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000623a  test    rax, rax
0x18000623d  jz      short loc_180006247
0x18000623f  mov     rcx, rbx
0x180006242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006247  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000624e  test    rax, rax
0x180006251  jz      short loc_180006269
0x180006253  mov     r8d, 400h
0x180006259  mov     rdx, [rsp+78h+arg_60]
0x180006261  mov     rcx, rbx
0x180006264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006269  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006270  test    rax, rax
0x180006273  jz      short loc_18000627D
0x180006275  mov     rcx, rbx
0x180006278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000627d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006284  test    rax, rax
0x180006287  jz      short loc_180006297
0x180006289  test    byte ptr [rbx+4], 2
0x18000628d  jnz     short loc_180006297
0x18000628f  mov     rcx, rbx
0x180006292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006297  cmp     [rbx+8], edi
0x18000629a  jl      short loc_1800062B5
0x18000629c  cmp     ebp, 3
0x18000629f  jnz     loc_18000639A
0x1800062a5  mov     ecx, 8000FFFFh; this
0x1800062aa  mov     [rbx+8], ecx
0x1800062ad  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800062b2  mov     [rbx+0Ch], eax
0x1800062b5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800062bc  jnz     short loc_1800062EB
0x1800062be  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800062c5  test    rax, rax
0x1800062c8  jz      short loc_1800062D4
0x1800062ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062cf  movzx   ecx, al
0x1800062d2  jmp     short loc_1800062E7
0x1800062d4  call    cs:__imp_IsDebuggerPresent
0x1800062db  nop     dword ptr [rax+rax+00h]
0x1800062e0  mov     ecx, edi
0x1800062e2  test    eax, eax
0x1800062e4  setnz   cl
0x1800062e7  test    ecx, ecx
0x1800062e9  jz      short loc_1800062F1
0x1800062eb  test    byte ptr [rbx+4], 2
0x1800062ef  jz      short loc_180006315
0x1800062f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800062f8  test    rax, rax
0x1800062fb  jz      short loc_180006360
0x1800062fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006304  jnz     short loc_180006360
0x180006306  xor     r8d, r8d
0x180006309  xor     edx, edx
0x18000630b  mov     rcx, rbx
0x18000630e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006313  jmp     short loc_180006360
0x180006315  mov     esi, 800h
0x18000631a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006321  test    rax, rax
0x180006324  jz      short loc_18000633D
0x180006326  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000632d  jnz     short loc_18000633D
0x18000632f  mov     r8d, esi
0x180006332  mov     rdx, r14
0x180006335  mov     rcx, rbx
0x180006338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000633d  cmp     [r14], di
0x180006341  jnz     short loc_180006351
0x180006343  mov     r8, rbx; unsigned __int64
0x180006346  mov     rdx, rsi; unsigned __int16 *
0x180006349  mov     rcx, r14; this
0x18000634c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006351  mov     rcx, r14; lpOutputString
0x180006354  call    cs:__imp_OutputDebugStringW
0x18000635b  nop     dword ptr [rax+rax+00h]
0x180006360  test    byte ptr [rbx+4], 4
0x180006364  jnz     short loc_18000636F
0x180006366  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000636d  jz      short loc_180006381
0x18000636f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006376  test    rax, rax
0x180006379  jz      short loc_180006381
0x18000637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006380  nop
0x180006381  mov     rbx, [rsp+78h+arg_10]
0x180006389  add     rsp, 40h
0x18000638d  pop     r15
0x18000638f  pop     r14
0x180006391  pop     r13
0x180006393  pop     r12
0x180006395  pop     rdi
0x180006396  pop     rsi
0x180006397  pop     rbp
0x180006398  retn
0x18000639a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
