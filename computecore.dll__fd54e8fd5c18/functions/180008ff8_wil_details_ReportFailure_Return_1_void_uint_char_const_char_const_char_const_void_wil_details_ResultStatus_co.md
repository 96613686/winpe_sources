# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008ff8`
- end: `0x18000929e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000871c`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180008ff8`
- `0x18000c36c`
- `0x18000df6c`
- `0x180011320`
- `0x1800115b4`
- `0x180099a90`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090be`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000923d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000923d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091b3`

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
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180008ff8  push    rbp
0x180008ffa  push    rbx
0x180008ffb  push    rsi
0x180008ffc  push    rdi
0x180008ffd  push    r12
0x180008fff  push    r14
0x180009001  push    r15
0x180009003  lea     rbp, [rsp-13D0h]
0x18000900b  mov     eax, 14D0h
0x180009010  call    _alloca_probe
0x180009015  sub     rsp, rax
0x180009018  mov     rax, cs:__security_cookie
0x18000901f  xor     rax, rsp
0x180009022  mov     [rbp+1400h+var_40], rax
0x180009029  mov     rsi, r8
0x18000902c  mov     edi, edx
0x18000902e  mov     rbx, rcx
0x180009031  mov     r14, [rbp+1400h+arg_28]
0x180009038  xor     edx, edx; Val
0x18000903a  mov     r8d, 98h; Size
0x180009040  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180009045  call    memset_0
0x18000904a  nop
0x18000904b  xor     r12d, r12d
0x18000904e  mov     [rbp+1400h+OutputString], r12w
0x180009056  mov     [rbp+1400h+var_1440], r12b
0x18000905a  mov     rdx, [rbp+1400h+arg_30]; int
0x180009061  mov     ecx, [rdx]; this
0x180009063  mov     [rsp+1500h+var_14D8], ecx
0x180009067  mov     eax, [rdx+4]
0x18000906a  mov     [rsp+1500h+var_14D4], eax
0x18000906e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009073  mov     r15d, eax
0x180009076  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000907e  mov     ecx, r12d
0x180009081  lea     eax, [r12+8]
0x180009086  cmp     dword ptr [rdx+8], 1
0x18000908a  cmovz   ecx, eax
0x18000908d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180009091  lea     ecx, [rax-7]
0x180009094  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000909c  inc     ecx
0x18000909e  mov     [rsp+1500h+var_14D0], ecx
0x1800090a2  mov     rcx, [rbp+1400h+arg_38]
0x1800090a9  test    rcx, rcx
0x1800090ac  jz      short loc_1800090B9
0x1800090ae  cmp     [rcx], r12w
0x1800090b2  mov     [rsp+1500h+var_14C8], rcx
0x1800090b7  jnz     short loc_1800090BE
0x1800090b9  mov     [rsp+1500h+var_14C8], r12
0x1800090be  call    cs:__imp_GetCurrentThreadId
0x1800090c4  mov     [rsp+1500h+var_14C0], eax
0x1800090c8  mov     [rsp+1500h+var_14A8], rsi
0x1800090cd  mov     [rsp+1500h+var_14A0], edi
0x1800090d1  mov     [rsp+1500h+var_149C], r15d
0x1800090d6  mov     [rsp+1500h+var_14B8], r12
0x1800090db  mov     [rsp+1500h+var_14B0], r12
0x1800090e0  mov     [rbp+1400h+var_1458], r14
0x1800090e4  mov     [rbp+1400h+var_1450], rbx
0x1800090e8  mov     [rsp+1500h+var_1498], r12
0x1800090ed  xorps   xmm0, xmm0
0x1800090f0  xor     eax, eax
0x1800090f2  movups  [rbp+1400h+var_1478], xmm0
0x1800090f6  mov     [rbp+1400h+var_1468], rax
0x1800090fa  xorps   xmm1, xmm1
0x1800090fd  movups  [rsp+1500h+var_1490], xmm1
0x180009102  mov     [rbp+1400h+var_1480], rax
0x180009106  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000910d  test    rax, rax
0x180009110  jz      short loc_18000911D
0x180009112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009117  mov     [rbp+1400h+var_1460], rax
0x18000911b  jmp     short loc_180009121
0x18000911d  mov     [rbp+1400h+var_1460], r12
0x180009121  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009128  test    rax, rax
0x18000912b  jz      short loc_180009137
0x18000912d  lea     rcx, [rsp+1500h+var_14E0]
0x180009132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009137  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000913e  test    rax, rax
0x180009141  jz      short loc_180009157
0x180009143  mov     r8d, 400h
0x180009149  lea     rdx, [rbp+1400h+var_1440]
0x18000914d  lea     rcx, [rsp+1500h+var_14E0]
0x180009152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009157  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000915e  test    rax, rax
0x180009161  jz      short loc_18000916D
0x180009163  lea     rcx, [rsp+1500h+var_14E0]
0x180009168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009174  test    rax, rax
0x180009177  jz      short loc_18000918A
0x180009179  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000917e  jnz     short loc_18000918A
0x180009180  lea     rcx, [rsp+1500h+var_14E0]
0x180009185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000918a  cmp     [rsp+1500h+var_14D8], r12d
0x18000918f  jge     loc_180009298
0x180009195  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000919c  jnz     short loc_1800091BD
0x18000919e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800091a5  test    rax, rax
0x1800091a8  jz      short loc_1800091B3
0x1800091aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091af  test    al, al
0x1800091b1  jmp     short loc_1800091BB
0x1800091b3  call    cs:__imp_IsDebuggerPresent
0x1800091b9  test    eax, eax
0x1800091bb  jz      short loc_1800091C4
0x1800091bd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800091c2  jz      short loc_1800091EA
0x1800091c4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800091cb  test    rax, rax
0x1800091ce  jz      short loc_180009243
0x1800091d0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800091d7  jnz     short loc_180009243
0x1800091d9  xor     r8d, r8d
0x1800091dc  xor     edx, edx
0x1800091de  lea     rcx, [rsp+1500h+var_14E0]
0x1800091e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e8  jmp     short loc_180009243
0x1800091ea  mov     ebx, 800h
0x1800091ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800091f6  test    rax, rax
0x1800091f9  jz      short loc_180009218
0x1800091fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009202  jnz     short loc_180009218
0x180009204  mov     r8d, ebx
0x180009207  lea     rdx, [rbp+1400h+OutputString]
0x18000920e  lea     rcx, [rsp+1500h+var_14E0]
0x180009213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009218  cmp     [rbp+1400h+OutputString], r12w
0x180009220  jnz     short loc_180009236
0x180009222  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180009227  mov     rdx, rbx; unsigned __int16 *
0x18000922a  lea     rcx, [rbp+1400h+OutputString]; this
0x180009231  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009236  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000923d  call    cs:__imp_OutputDebugStringW
0x180009243  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180009248  jnz     short loc_180009253
0x18000924a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009251  jz      short loc_180009265
0x180009253  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000925a  test    rax, rax
0x18000925d  jz      short loc_180009265
0x18000925f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009264  nop
0x180009265  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000926a  jnz     short loc_18000928D
0x18000926c  mov     rcx, [rbp+1400h+var_40]
0x180009273  xor     rcx, rsp; StackCookie
0x180009276  call    __security_check_cookie
0x18000927b  add     rsp, 14D0h
0x180009282  pop     r15
0x180009284  pop     r14
0x180009286  pop     r12
0x180009288  pop     rdi
0x180009289  pop     rsi
0x18000928a  pop     rbx
0x18000928b  pop     rbp
0x18000928c  retn
0x18000928d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180009292  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009298  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
