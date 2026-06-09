# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180020428`
- end: `0x1800206c6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b770`

## callees

- `0x1800161a0`
- `0x180019424`
- `0x18001f620`
- `0x18001ffb0`
- `0x180020428`
- `0x1800253a0`
- `0x180025714`
- `0x1800447f0`
- `0x180045010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18002065f`
- `KERNEL32!OutputDebugStringW` at `0x18002065f`
- `KERNEL32!GetCurrentThreadId` at `0x1800204d5`
- `KERNEL32!GetCurrentThreadId` at `0x1800204d5`
- `KERNEL32!IsDebuggerPresent` at `0x1800205cf`
- `KERNEL32!IsDebuggerPresent` at `0x1800205cf`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180020428  push    rbp
0x18002042a  push    rbx
0x18002042b  push    rsi
0x18002042c  push    rdi
0x18002042d  push    r12
0x18002042f  push    r14
0x180020431  push    r15
0x180020433  lea     rbp, [rsp-13D0h]
0x18002043b  mov     eax, 14D0h
0x180020440  call    _alloca_probe
0x180020445  sub     rsp, rax
0x180020448  mov     rax, cs:__security_cookie
0x18002044f  xor     rax, rsp
0x180020452  mov     [rbp+1400h+var_40], rax
0x180020459  mov     rdi, [rbp+1400h+arg_28]
0x180020460  mov     r14, r8
0x180020463  mov     esi, edx
0x180020465  mov     r15, rcx
0x180020468  xor     edx, edx; Val
0x18002046a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18002046f  mov     r8d, 98h; Size
0x180020475  call    memset_0
0x18002047a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180020481  xor     r12d, r12d
0x180020484  mov     [rbp+1400h+OutputString], r12w
0x18002048c  mov     [rbp+1400h+var_1440], r12b
0x180020490  mov     ecx, [rdx]; this
0x180020492  mov     eax, [rdx+4]
0x180020495  mov     [rsp+1500h+var_14D8], ecx
0x180020499  mov     [rsp+1500h+var_14D4], eax
0x18002049d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800204a2  cmp     dword ptr [rdx+8], 1
0x1800204a6  mov     ebx, eax
0x1800204a8  lea     eax, [r12+8]
0x1800204ad  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800204b5  mov     ecx, r12d
0x1800204b8  cmovz   ecx, eax
0x1800204bb  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800204bf  lea     ecx, [rax-7]
0x1800204c2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800204ca  inc     ecx
0x1800204cc  mov     [rsp+1500h+var_14C8], r12
0x1800204d1  mov     [rsp+1500h+var_14D0], ecx
0x1800204d5  call    cs:__imp_GetCurrentThreadId
0x1800204dc  nop     dword ptr [rax+rax+00h]
0x1800204e1  xorps   xmm0, xmm0
0x1800204e4  mov     [rsp+1500h+var_14A8], r14
0x1800204e9  mov     [rsp+1500h+var_14C0], eax
0x1800204ed  xorps   xmm1, xmm1
0x1800204f0  xor     eax, eax
0x1800204f2  mov     [rsp+1500h+var_14A0], esi
0x1800204f6  mov     [rbp+1400h+var_1468], rax
0x1800204fa  mov     [rbp+1400h+var_1480], rax
0x1800204fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180020505  mov     [rsp+1500h+var_149C], ebx
0x180020509  mov     [rsp+1500h+var_14B8], r12
0x18002050e  mov     [rsp+1500h+var_14B0], r12
0x180020513  mov     [rbp+1400h+var_1458], rdi
0x180020517  mov     [rbp+1400h+var_1450], r15
0x18002051b  mov     [rsp+1500h+var_1498], r12
0x180020520  movups  [rbp+1400h+var_1478], xmm0
0x180020524  movups  [rsp+1500h+var_1490], xmm1
0x180020529  test    rax, rax
0x18002052c  jz      short loc_180020539
0x18002052e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020533  mov     [rbp+1400h+var_1460], rax
0x180020537  jmp     short loc_18002053D
0x180020539  mov     [rbp+1400h+var_1460], r12
0x18002053d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180020544  test    rax, rax
0x180020547  jz      short loc_180020553
0x180020549  lea     rcx, [rsp+1500h+var_14E0]
0x18002054e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020553  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002055a  test    rax, rax
0x18002055d  jz      short loc_180020573
0x18002055f  mov     r8d, 400h
0x180020565  lea     rdx, [rbp+1400h+var_1440]
0x180020569  lea     rcx, [rsp+1500h+var_14E0]
0x18002056e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020573  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002057a  test    rax, rax
0x18002057d  jz      short loc_180020589
0x18002057f  lea     rcx, [rsp+1500h+var_14E0]
0x180020584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020589  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020590  test    rax, rax
0x180020593  jz      short loc_1800205A6
0x180020595  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002059a  jnz     short loc_1800205A6
0x18002059c  lea     rcx, [rsp+1500h+var_14E0]
0x1800205a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205a6  cmp     [rsp+1500h+var_14D8], r12d
0x1800205ab  jge     loc_1800206B5
0x1800205b1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800205b8  jnz     short loc_1800205DF
0x1800205ba  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800205c1  test    rax, rax
0x1800205c4  jz      short loc_1800205CF
0x1800205c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205cb  test    al, al
0x1800205cd  jmp     short loc_1800205DD
0x1800205cf  call    cs:__imp_IsDebuggerPresent
0x1800205d6  nop     dword ptr [rax+rax+00h]
0x1800205db  test    eax, eax
0x1800205dd  jz      short loc_1800205E6
0x1800205df  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800205e4  jz      short loc_18002060C
0x1800205e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800205ed  test    rax, rax
0x1800205f0  jz      short loc_18002066B
0x1800205f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800205f9  jnz     short loc_18002066B
0x1800205fb  xor     r8d, r8d
0x1800205fe  lea     rcx, [rsp+1500h+var_14E0]
0x180020603  xor     edx, edx
0x180020605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002060a  jmp     short loc_18002066B
0x18002060c  mov     rax, cs:g_pfnResultLoggingCallback
0x180020613  mov     ebx, 800h
0x180020618  test    rax, rax
0x18002061b  jz      short loc_18002063A
0x18002061d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180020624  jnz     short loc_18002063A
0x180020626  mov     r8d, ebx
0x180020629  lea     rdx, [rbp+1400h+OutputString]
0x180020630  lea     rcx, [rsp+1500h+var_14E0]
0x180020635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002063a  cmp     [rbp+1400h+OutputString], r12w
0x180020642  jnz     short loc_180020658
0x180020644  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180020649  mov     rdx, rbx; unsigned __int16 *
0x18002064c  lea     rcx, [rbp+1400h+OutputString]; this
0x180020653  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180020658  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18002065f  call    cs:__imp_OutputDebugStringW
0x180020666  nop     dword ptr [rax+rax+00h]
0x18002066b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180020670  jnz     short loc_18002067B
0x180020672  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180020679  jz      short loc_18002068C
0x18002067b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180020682  test    rax, rax
0x180020685  jz      short loc_18002068C
0x180020687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002068c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180020691  jnz     short loc_1800206BB
0x180020693  mov     rcx, [rbp+1400h+var_40]
0x18002069a  xor     rcx, rsp; StackCookie
0x18002069d  call    __security_check_cookie
0x1800206a2  add     rsp, 14D0h
0x1800206a9  pop     r15
0x1800206ab  pop     r14
0x1800206ad  pop     r12
0x1800206af  pop     rdi
0x1800206b0  pop     rsi
0x1800206b1  pop     rbx
0x1800206b2  pop     rbp
0x1800206b3  retn
0x1800206b5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800206bb  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800206c0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
