# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180035ed8`
- end: `0x1800361d1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180032b50`

## callees

- `0x18003258c`
- `0x180034b54`
- `0x180035bd4`
- `0x180035ed8`
- `0x180036c0c`
- `0x180036c30`
- `0x180036db4`
- `0x180036dd0`
- `0x180038c18`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035ffb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003611a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003611a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003618c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003618c`

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
0x180035ed8  mov     [rsp+arg_10], rbx
0x180035edd  mov     [rsp+arg_8], edx
0x180035ee1  mov     [rsp+arg_0], rcx
0x180035ee6  push    rbp
0x180035ee7  push    rsi
0x180035ee8  push    rdi
0x180035ee9  push    r12
0x180035eeb  push    r13
0x180035eed  push    r14
0x180035eef  push    r15
0x180035ef1  sub     rsp, 40h
0x180035ef5  mov     r12, r9
0x180035ef8  mov     r13, r8
0x180035efb  mov     r10, rcx
0x180035efe  xor     eax, eax
0x180035f00  mov     rsi, [rsp+78h+lpOutputString]
0x180035f08  mov     [rsi], ax
0x180035f0b  mov     rax, [rsp+78h+arg_60]
0x180035f13  mov     byte ptr [rax], 0
0x180035f16  mov     r14, [rsp+78h+arg_38]
0x180035f1e  mov     edi, [r14]
0x180035f21  mov     rbx, [rsp+78h+arg_78]
0x180035f29  mov     [rbx+8], edi
0x180035f2c  mov     eax, [r14+4]
0x180035f30  mov     [rbx+0Ch], eax
0x180035f33  xor     ebp, ebp
0x180035f35  mov     r15d, [rsp+78h+arg_30]
0x180035f3d  mov     ecx, r15d
0x180035f40  test    r15d, r15d
0x180035f43  jz      short loc_180035FAB
0x180035f45  sub     ecx, 1
0x180035f48  jz      short loc_180035FA2
0x180035f4a  sub     ecx, 1
0x180035f4d  jz      short loc_180035F5D
0x180035f4f  cmp     ecx, 1
0x180035f52  jnz     short loc_180035FB4
0x180035f54  mov     ecx, edi; this
0x180035f56  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180035f5b  jmp     short loc_180035FB2
0x180035f5d  test    edi, edi
0x180035f5f  js      short loc_180035F99
0x180035f61  mov     edi, 8007029Ch
0x180035f66  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180035f6a  mov     rax, [rsp+78h+arg_28]
0x180035f72  mov     [rsp+78h+var_50], rax; __int64
0x180035f77  mov     rax, [rsp+78h+arg_20]
0x180035f7f  mov     [rsp+78h+var_58], rax; __int64
0x180035f84  mov     rcx, r10; int
0x180035f87  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180035f8c  mov     [rbx+8], edi
0x180035f8f  mov     ecx, edi; this
0x180035f91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180035f96  mov     [rbx+0Ch], eax
0x180035f99  mov     ecx, edi; this
0x180035f9b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180035fa0  jmp     short loc_180035FB2
0x180035fa2  mov     ecx, edi; this
0x180035fa4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180035fa9  jmp     short loc_180035FB2
0x180035fab  mov     ecx, edi; this
0x180035fad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180035fb2  mov     ebp, eax
0x180035fb4  mov     [rbx], r15d
0x180035fb7  mov     eax, [rsp+78h+arg_70]
0x180035fbe  mov     [rbx+4], eax
0x180035fc1  cmp     dword ptr [r14+8], 1
0x180035fc6  jnz     short loc_180035FCE
0x180035fc8  or      eax, 8
0x180035fcb  mov     [rbx+4], eax
0x180035fce  mov     eax, 1
0x180035fd3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180035fdb  inc     eax
0x180035fdd  mov     [rbx+10h], eax
0x180035fe0  mov     rax, [rsp+78h+arg_40]
0x180035fe8  xor     edi, edi
0x180035fea  test    rax, rax
0x180035fed  jz      short loc_180035FF4
0x180035fef  cmp     [rax], di
0x180035ff2  jnz     short loc_180035FF7
0x180035ff4  mov     rax, rdi
0x180035ff7  mov     [rbx+18h], rax
0x180035ffb  call    cs:__imp_GetCurrentThreadId
0x180036001  mov     [rbx+20h], eax
0x180036004  mov     [rbx+38h], r13
0x180036008  mov     eax, [rsp+78h+arg_8]
0x18003600f  mov     [rbx+40h], eax
0x180036012  mov     [rbx+44h], ebp
0x180036015  mov     rax, [rsp+78h+arg_20]
0x18003601d  mov     [rbx+28h], rax
0x180036021  mov     [rbx+30h], r12
0x180036025  mov     rax, [rsp+78h+arg_28]
0x18003602d  mov     [rbx+88h], rax
0x180036034  mov     rax, [rsp+78h+arg_0]
0x18003603c  mov     [rbx+90h], rax
0x180036043  mov     [rbx+48h], rdi
0x180036047  xorps   xmm0, xmm0
0x18003604a  xor     eax, eax
0x18003604c  movups  xmmword ptr [rbx+68h], xmm0
0x180036050  mov     [rbx+78h], rax
0x180036054  movups  xmmword ptr [rbx+50h], xmm0
0x180036058  mov     [rbx+60h], rax
0x18003605c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180036063  test    rax, rax
0x180036066  jz      short loc_18003606F
0x180036068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003606d  jmp     short loc_180036072
0x18003606f  mov     rax, rdi
0x180036072  mov     [rbx+80h], rax
0x180036079  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180036080  test    rax, rax
0x180036083  jz      short loc_18003608D
0x180036085  mov     rcx, rbx
0x180036088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003608d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180036094  test    rax, rax
0x180036097  jz      short loc_1800360AF
0x180036099  mov     r8d, 400h
0x18003609f  mov     rdx, [rsp+78h+arg_60]
0x1800360a7  mov     rcx, rbx
0x1800360aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360af  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800360b6  test    rax, rax
0x1800360b9  jz      short loc_1800360C3
0x1800360bb  mov     rcx, rbx
0x1800360be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800360ca  test    rax, rax
0x1800360cd  jz      short loc_1800360DD
0x1800360cf  test    byte ptr [rbx+4], 2
0x1800360d3  jnz     short loc_1800360DD
0x1800360d5  mov     rcx, rbx
0x1800360d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360dd  cmp     [rbx+8], edi
0x1800360e0  jl      short loc_1800360FC
0x1800360e2  cmp     r15d, 3
0x1800360e6  jnz     loc_1800361CB
0x1800360ec  mov     ecx, 8000FFFFh; this
0x1800360f1  mov     [rbx+8], ecx
0x1800360f4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800360f9  mov     [rbx+0Ch], eax
0x1800360fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180036103  jnz     short loc_180036124
0x180036105  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003610c  test    rax, rax
0x18003610f  jz      short loc_18003611A
0x180036111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036116  test    al, al
0x180036118  jmp     short loc_180036122
0x18003611a  call    cs:__imp_IsDebuggerPresent
0x180036120  test    eax, eax
0x180036122  jz      short loc_18003612A
0x180036124  test    byte ptr [rbx+4], 2
0x180036128  jz      short loc_18003614E
0x18003612a  mov     rax, cs:g_pfnResultLoggingCallback
0x180036131  test    rax, rax
0x180036134  jz      short loc_180036192
0x180036136  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003613d  jnz     short loc_180036192
0x18003613f  xor     r8d, r8d
0x180036142  xor     edx, edx
0x180036144  mov     rcx, rbx
0x180036147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003614c  jmp     short loc_180036192
0x18003614e  mov     ebp, 800h
0x180036153  mov     rax, cs:g_pfnResultLoggingCallback
0x18003615a  test    rax, rax
0x18003615d  jz      short loc_180036176
0x18003615f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180036166  jnz     short loc_180036176
0x180036168  mov     r8d, ebp
0x18003616b  mov     rdx, rsi
0x18003616e  mov     rcx, rbx
0x180036171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036176  cmp     [rsi], di
0x180036179  jnz     short loc_180036189
0x18003617b  mov     r8, rbx; unsigned __int64
0x18003617e  mov     rdx, rbp; unsigned __int16 *
0x180036181  mov     rcx, rsi; this
0x180036184  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180036189  mov     rcx, rsi; lpOutputString
0x18003618c  call    cs:__imp_OutputDebugStringW
0x180036192  test    byte ptr [rbx+4], 4
0x180036196  jnz     short loc_1800361A1
0x180036198  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003619f  jz      short loc_1800361B3
0x1800361a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800361a8  test    rax, rax
0x1800361ab  jz      short loc_1800361B3
0x1800361ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361b2  nop
0x1800361b3  mov     rbx, [rsp+78h+arg_10]
0x1800361bb  add     rsp, 40h
0x1800361bf  pop     r15
0x1800361c1  pop     r14
0x1800361c3  pop     r13
0x1800361c5  pop     r12
0x1800361c7  pop     rdi
0x1800361c8  pop     rsi
0x1800361c9  pop     rbp
0x1800361ca  retn
0x1800361cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
