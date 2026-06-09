# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180017014`
- end: `0x1800172b4`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013784`

## callees

- `0x180014330`
- `0x180015174`
- `0x180017014`
- `0x1800199f4`
- `0x18001b244`
- `0x18001d010`
- `0x18001d4fc`
- `0x18002e480`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800170c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001724c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001724c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800171bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800171bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180017014  push    rbp
0x180017016  push    rbx
0x180017017  push    rsi
0x180017018  push    rdi
0x180017019  push    r12
0x18001701b  push    r14
0x18001701d  push    r15
0x18001701f  lea     rbp, [rsp-13D0h]
0x180017027  mov     eax, 14D0h
0x18001702c  call    _alloca_probe
0x180017031  sub     rsp, rax
0x180017034  mov     rax, cs:__security_cookie
0x18001703b  xor     rax, rsp
0x18001703e  mov     [rbp+1400h+var_40], rax
0x180017045  mov     r14, r8
0x180017048  mov     esi, edx
0x18001704a  mov     r15, rcx
0x18001704d  mov     rdi, [rbp+1400h+arg_28]
0x180017054  xor     edx, edx; Val
0x180017056  mov     r8d, 98h; Size
0x18001705c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180017061  call    memset_0
0x180017066  nop
0x180017067  xor     r12d, r12d
0x18001706a  mov     [rbp+1400h+OutputString], r12w
0x180017072  mov     [rbp+1400h+var_1440], r12b
0x180017076  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18001707d  mov     ecx, [rdx]; this
0x18001707f  mov     [rsp+1500h+var_14D8], ecx
0x180017083  mov     eax, [rdx+4]
0x180017086  mov     [rsp+1500h+var_14D4], eax
0x18001708a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001708f  mov     ebx, eax
0x180017091  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180017099  mov     ecx, r12d
0x18001709c  lea     eax, [r12+8]
0x1800170a1  cmp     dword ptr [rdx+8], 1
0x1800170a5  cmovz   ecx, eax
0x1800170a8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800170ac  lea     ecx, [rax-7]
0x1800170af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800170b7  inc     ecx
0x1800170b9  mov     [rsp+1500h+var_14D0], ecx
0x1800170bd  mov     [rsp+1500h+var_14C8], r12
0x1800170c2  call    cs:__imp_GetCurrentThreadId
0x1800170c9  nop     dword ptr [rax+rax+00h]
0x1800170ce  mov     [rsp+1500h+var_14C0], eax
0x1800170d2  mov     [rsp+1500h+var_14A8], r14
0x1800170d7  mov     [rsp+1500h+var_14A0], esi
0x1800170db  mov     [rsp+1500h+var_149C], ebx
0x1800170df  mov     [rsp+1500h+var_14B8], r12
0x1800170e4  mov     [rsp+1500h+var_14B0], r12
0x1800170e9  mov     [rbp+1400h+var_1458], rdi
0x1800170ed  mov     [rbp+1400h+var_1450], r15
0x1800170f1  mov     [rsp+1500h+var_1498], r12
0x1800170f6  xorps   xmm0, xmm0
0x1800170f9  xor     eax, eax
0x1800170fb  movups  [rbp+1400h+var_1478], xmm0
0x1800170ff  mov     [rbp+1400h+var_1468], rax
0x180017103  xorps   xmm1, xmm1
0x180017106  movups  [rsp+1500h+var_1490], xmm1
0x18001710b  mov     [rbp+1400h+var_1480], rax
0x18001710f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180017116  test    rax, rax
0x180017119  jz      short loc_180017126
0x18001711b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017120  mov     [rbp+1400h+var_1460], rax
0x180017124  jmp     short loc_18001712A
0x180017126  mov     [rbp+1400h+var_1460], r12
0x18001712a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180017131  test    rax, rax
0x180017134  jz      short loc_180017140
0x180017136  lea     rcx, [rsp+1500h+var_14E0]
0x18001713b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017140  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180017147  test    rax, rax
0x18001714a  jz      short loc_180017160
0x18001714c  mov     r8d, 400h
0x180017152  lea     rdx, [rbp+1400h+var_1440]
0x180017156  lea     rcx, [rsp+1500h+var_14E0]
0x18001715b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017160  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017167  test    rax, rax
0x18001716a  jz      short loc_180017176
0x18001716c  lea     rcx, [rsp+1500h+var_14E0]
0x180017171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017176  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001717d  test    rax, rax
0x180017180  jz      short loc_180017193
0x180017182  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180017187  jnz     short loc_180017193
0x180017189  lea     rcx, [rsp+1500h+var_14E0]
0x18001718e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017193  cmp     [rsp+1500h+var_14D8], r12d
0x180017198  jge     loc_1800172AE
0x18001719e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800171a5  jnz     short loc_1800171CC
0x1800171a7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800171ae  test    rax, rax
0x1800171b1  jz      short loc_1800171BC
0x1800171b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b8  test    al, al
0x1800171ba  jmp     short loc_1800171CA
0x1800171bc  call    cs:__imp_IsDebuggerPresent
0x1800171c3  nop     dword ptr [rax+rax+00h]
0x1800171c8  test    eax, eax
0x1800171ca  jz      short loc_1800171D3
0x1800171cc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800171d1  jz      short loc_1800171F9
0x1800171d3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800171da  test    rax, rax
0x1800171dd  jz      short loc_180017258
0x1800171df  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800171e6  jnz     short loc_180017258
0x1800171e8  xor     r8d, r8d
0x1800171eb  xor     edx, edx
0x1800171ed  lea     rcx, [rsp+1500h+var_14E0]
0x1800171f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f7  jmp     short loc_180017258
0x1800171f9  mov     ebx, 800h
0x1800171fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180017205  test    rax, rax
0x180017208  jz      short loc_180017227
0x18001720a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180017211  jnz     short loc_180017227
0x180017213  mov     r8d, ebx
0x180017216  lea     rdx, [rbp+1400h+OutputString]
0x18001721d  lea     rcx, [rsp+1500h+var_14E0]
0x180017222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017227  cmp     [rbp+1400h+OutputString], r12w
0x18001722f  jnz     short loc_180017245
0x180017231  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180017236  mov     rdx, rbx; unsigned __int16 *
0x180017239  lea     rcx, [rbp+1400h+OutputString]; this
0x180017240  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180017245  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001724c  call    cs:__imp_OutputDebugStringW
0x180017253  nop     dword ptr [rax+rax+00h]
0x180017258  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001725d  jnz     short loc_180017268
0x18001725f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180017266  jz      short loc_18001727A
0x180017268  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001726f  test    rax, rax
0x180017272  jz      short loc_18001727A
0x180017274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017279  nop
0x18001727a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001727f  jnz     short loc_1800172A3
0x180017281  mov     rcx, [rbp+1400h+var_40]
0x180017288  xor     rcx, rsp; StackCookie
0x18001728b  call    __security_check_cookie
0x180017290  add     rsp, 14D0h
0x180017297  pop     r15
0x180017299  pop     r14
0x18001729b  pop     r12
0x18001729d  pop     rdi
0x18001729e  pop     rsi
0x18001729f  pop     rbx
0x1800172a0  pop     rbp
0x1800172a1  retn
0x1800172a3  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800172a8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800172ae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
