# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009768`
- end: `0x180009a61`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006b3c`
- `0x180006e90`
- `0x180018c8c`

## callees

- `0x180006a70`
- `0x180008b14`
- `0x180009380`
- `0x180009768`
- `0x18000a6f4`
- `0x18000a710`
- `0x18000a860`
- `0x18000a87c`
- `0x18000c594`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000988b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000988b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800099aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800099aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009a1c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009a1c`

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
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180009768  mov     [rsp+arg_10], rbx
0x18000976d  mov     [rsp+arg_8], edx
0x180009771  mov     [rsp+arg_0], rcx
0x180009776  push    rbp
0x180009777  push    rsi
0x180009778  push    rdi
0x180009779  push    r12
0x18000977b  push    r13
0x18000977d  push    r14
0x18000977f  push    r15
0x180009781  sub     rsp, 40h
0x180009785  mov     r12, r9
0x180009788  mov     r13, r8
0x18000978b  mov     r10, rcx
0x18000978e  xor     eax, eax
0x180009790  mov     rsi, [rsp+78h+lpOutputString]
0x180009798  mov     [rsi], ax
0x18000979b  mov     rax, [rsp+78h+arg_60]
0x1800097a3  mov     byte ptr [rax], 0
0x1800097a6  mov     r14, [rsp+78h+arg_38]
0x1800097ae  mov     edi, [r14]
0x1800097b1  mov     rbx, [rsp+78h+arg_78]
0x1800097b9  mov     [rbx+8], edi
0x1800097bc  mov     eax, [r14+4]
0x1800097c0  mov     [rbx+0Ch], eax
0x1800097c3  xor     ebp, ebp
0x1800097c5  mov     r15d, [rsp+78h+arg_30]
0x1800097cd  mov     ecx, r15d
0x1800097d0  test    r15d, r15d
0x1800097d3  jz      short loc_18000983B
0x1800097d5  sub     ecx, 1
0x1800097d8  jz      short loc_180009832
0x1800097da  sub     ecx, 1
0x1800097dd  jz      short loc_1800097ED
0x1800097df  cmp     ecx, 1
0x1800097e2  jnz     short loc_180009844
0x1800097e4  mov     ecx, edi; this
0x1800097e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800097eb  jmp     short loc_180009842
0x1800097ed  test    edi, edi
0x1800097ef  js      short loc_180009829
0x1800097f1  mov     edi, 8007029Ch
0x1800097f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800097fa  mov     rax, [rsp+78h+arg_28]
0x180009802  mov     [rsp+78h+var_50], rax; __int64
0x180009807  mov     rax, [rsp+78h+arg_20]
0x18000980f  mov     [rsp+78h+var_58], rax; __int64
0x180009814  mov     rcx, r10; int
0x180009817  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000981c  mov     [rbx+8], edi
0x18000981f  mov     ecx, edi; this
0x180009821  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009826  mov     [rbx+0Ch], eax
0x180009829  mov     ecx, edi; this
0x18000982b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009830  jmp     short loc_180009842
0x180009832  mov     ecx, edi; this
0x180009834  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009839  jmp     short loc_180009842
0x18000983b  mov     ecx, edi; this
0x18000983d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009842  mov     ebp, eax
0x180009844  mov     [rbx], r15d
0x180009847  mov     eax, [rsp+78h+arg_70]
0x18000984e  mov     [rbx+4], eax
0x180009851  cmp     dword ptr [r14+8], 1
0x180009856  jnz     short loc_18000985E
0x180009858  or      eax, 8
0x18000985b  mov     [rbx+4], eax
0x18000985e  mov     eax, 1
0x180009863  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000986b  inc     eax
0x18000986d  mov     [rbx+10h], eax
0x180009870  mov     rax, [rsp+78h+arg_40]
0x180009878  xor     edi, edi
0x18000987a  test    rax, rax
0x18000987d  jz      short loc_180009884
0x18000987f  cmp     [rax], di
0x180009882  jnz     short loc_180009887
0x180009884  mov     rax, rdi
0x180009887  mov     [rbx+18h], rax
0x18000988b  call    cs:__imp_GetCurrentThreadId
0x180009891  mov     [rbx+20h], eax
0x180009894  mov     [rbx+38h], r13
0x180009898  mov     eax, [rsp+78h+arg_8]
0x18000989f  mov     [rbx+40h], eax
0x1800098a2  mov     [rbx+44h], ebp
0x1800098a5  mov     rax, [rsp+78h+arg_20]
0x1800098ad  mov     [rbx+28h], rax
0x1800098b1  mov     [rbx+30h], r12
0x1800098b5  mov     rax, [rsp+78h+arg_28]
0x1800098bd  mov     [rbx+88h], rax
0x1800098c4  mov     rax, [rsp+78h+arg_0]
0x1800098cc  mov     [rbx+90h], rax
0x1800098d3  mov     [rbx+48h], rdi
0x1800098d7  xorps   xmm0, xmm0
0x1800098da  xor     eax, eax
0x1800098dc  movups  xmmword ptr [rbx+68h], xmm0
0x1800098e0  mov     [rbx+78h], rax
0x1800098e4  movups  xmmword ptr [rbx+50h], xmm0
0x1800098e8  mov     [rbx+60h], rax
0x1800098ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800098f3  test    rax, rax
0x1800098f6  jz      short loc_1800098FF
0x1800098f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fd  jmp     short loc_180009902
0x1800098ff  mov     rax, rdi
0x180009902  mov     [rbx+80h], rax
0x180009909  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009910  test    rax, rax
0x180009913  jz      short loc_18000991D
0x180009915  mov     rcx, rbx
0x180009918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009924  test    rax, rax
0x180009927  jz      short loc_18000993F
0x180009929  mov     r8d, 400h
0x18000992f  mov     rdx, [rsp+78h+arg_60]
0x180009937  mov     rcx, rbx
0x18000993a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009946  test    rax, rax
0x180009949  jz      short loc_180009953
0x18000994b  mov     rcx, rbx
0x18000994e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009953  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000995a  test    rax, rax
0x18000995d  jz      short loc_18000996D
0x18000995f  test    byte ptr [rbx+4], 2
0x180009963  jnz     short loc_18000996D
0x180009965  mov     rcx, rbx
0x180009968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996d  cmp     [rbx+8], edi
0x180009970  jl      short loc_18000998C
0x180009972  cmp     r15d, 3
0x180009976  jnz     loc_180009A5B
0x18000997c  mov     ecx, 8000FFFFh; this
0x180009981  mov     [rbx+8], ecx
0x180009984  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009989  mov     [rbx+0Ch], eax
0x18000998c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009993  jnz     short loc_1800099B4
0x180009995  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000999c  test    rax, rax
0x18000999f  jz      short loc_1800099AA
0x1800099a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a6  test    al, al
0x1800099a8  jmp     short loc_1800099B2
0x1800099aa  call    cs:__imp_IsDebuggerPresent
0x1800099b0  test    eax, eax
0x1800099b2  jz      short loc_1800099BA
0x1800099b4  test    byte ptr [rbx+4], 2
0x1800099b8  jz      short loc_1800099DE
0x1800099ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1800099c1  test    rax, rax
0x1800099c4  jz      short loc_180009A22
0x1800099c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800099cd  jnz     short loc_180009A22
0x1800099cf  xor     r8d, r8d
0x1800099d2  xor     edx, edx
0x1800099d4  mov     rcx, rbx
0x1800099d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099dc  jmp     short loc_180009A22
0x1800099de  mov     ebp, 800h
0x1800099e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800099ea  test    rax, rax
0x1800099ed  jz      short loc_180009A06
0x1800099ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800099f6  jnz     short loc_180009A06
0x1800099f8  mov     r8d, ebp
0x1800099fb  mov     rdx, rsi
0x1800099fe  mov     rcx, rbx
0x180009a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a06  cmp     [rsi], di
0x180009a09  jnz     short loc_180009A19
0x180009a0b  mov     r8, rbx; unsigned __int64
0x180009a0e  mov     rdx, rbp; unsigned __int16 *
0x180009a11  mov     rcx, rsi; this
0x180009a14  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009a19  mov     rcx, rsi; lpOutputString
0x180009a1c  call    cs:__imp_OutputDebugStringW
0x180009a22  test    byte ptr [rbx+4], 4
0x180009a26  jnz     short loc_180009A31
0x180009a28  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009a2f  jz      short loc_180009A43
0x180009a31  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009a38  test    rax, rax
0x180009a3b  jz      short loc_180009A43
0x180009a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a42  nop
0x180009a43  mov     rbx, [rsp+78h+arg_10]
0x180009a4b  add     rsp, 40h
0x180009a4f  pop     r15
0x180009a51  pop     r14
0x180009a53  pop     r13
0x180009a55  pop     r12
0x180009a57  pop     rdi
0x180009a58  pop     rsi
0x180009a59  pop     rbp
0x180009a5a  retn
0x180009a5b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
