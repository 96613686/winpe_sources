# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003fac`
- end: `0x1400042b8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002a38`

## callees

- `0x14000244c`
- `0x1400035e4`
- `0x140003de8`
- `0x140003fac`
- `0x140004764`
- `0x140004790`
- `0x1400047a4`
- `0x1400047c4`
- `0x1400056d8`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400040cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400040cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000426c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000426c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400041f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400041f4`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x140003fac  mov     [rsp+arg_10], rbx
0x140003fb1  mov     [rsp+arg_8], edx
0x140003fb5  mov     [rsp+arg_0], rcx
0x140003fba  push    rbp
0x140003fbb  push    rsi
0x140003fbc  push    rdi
0x140003fbd  push    r12
0x140003fbf  push    r13
0x140003fc1  push    r14
0x140003fc3  push    r15
0x140003fc5  sub     rsp, 40h
0x140003fc9  mov     r12, r9
0x140003fcc  mov     r13, r8
0x140003fcf  mov     r10, rcx
0x140003fd2  xor     eax, eax
0x140003fd4  mov     rsi, [rsp+78h+lpOutputString]
0x140003fdc  mov     [rsi], ax
0x140003fdf  mov     rax, [rsp+78h+arg_60]
0x140003fe7  mov     byte ptr [rax], 0
0x140003fea  mov     r14, [rsp+78h+arg_38]
0x140003ff2  mov     edi, [r14]
0x140003ff5  mov     rbx, [rsp+78h+arg_78]
0x140003ffd  mov     [rbx+8], edi
0x140004000  mov     eax, [r14+4]
0x140004004  mov     [rbx+0Ch], eax
0x140004007  xor     ebp, ebp
0x140004009  mov     r15d, [rsp+78h+arg_30]
0x140004011  mov     ecx, r15d
0x140004014  test    r15d, r15d
0x140004017  jz      short loc_14000407F
0x140004019  sub     ecx, 1
0x14000401c  jz      short loc_140004076
0x14000401e  sub     ecx, 1
0x140004021  jz      short loc_140004031
0x140004023  cmp     ecx, 1
0x140004026  jnz     short loc_140004088
0x140004028  mov     ecx, edi; this
0x14000402a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000402f  jmp     short loc_140004086
0x140004031  test    edi, edi
0x140004033  js      short loc_14000406D
0x140004035  mov     edi, 8007029Ch
0x14000403a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000403e  mov     rax, [rsp+78h+arg_28]
0x140004046  mov     [rsp+78h+var_50], rax; __int64
0x14000404b  mov     rax, [rsp+78h+arg_20]
0x140004053  mov     [rsp+78h+var_58], rax; __int64
0x140004058  mov     rcx, r10; int
0x14000405b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004060  mov     [rbx+8], edi
0x140004063  mov     ecx, edi; this
0x140004065  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000406a  mov     [rbx+0Ch], eax
0x14000406d  mov     ecx, edi; this
0x14000406f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004074  jmp     short loc_140004086
0x140004076  mov     ecx, edi; this
0x140004078  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000407d  jmp     short loc_140004086
0x14000407f  mov     ecx, edi; this
0x140004081  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004086  mov     ebp, eax
0x140004088  mov     [rbx], r15d
0x14000408b  mov     eax, [rsp+78h+arg_70]
0x140004092  mov     [rbx+4], eax
0x140004095  cmp     dword ptr [r14+8], 1
0x14000409a  jnz     short loc_1400040A2
0x14000409c  or      eax, 8
0x14000409f  mov     [rbx+4], eax
0x1400040a2  mov     eax, 1
0x1400040a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400040af  inc     eax
0x1400040b1  mov     [rbx+10h], eax
0x1400040b4  mov     rax, [rsp+78h+arg_40]
0x1400040bc  xor     edi, edi
0x1400040be  test    rax, rax
0x1400040c1  jz      short loc_1400040C8
0x1400040c3  cmp     [rax], di
0x1400040c6  jnz     short loc_1400040CB
0x1400040c8  mov     rax, rdi
0x1400040cb  mov     [rbx+18h], rax
0x1400040cf  call    cs:__imp_GetCurrentThreadId
0x1400040d6  nop     dword ptr [rax+rax+00h]
0x1400040db  mov     [rbx+20h], eax
0x1400040de  mov     [rbx+38h], r13
0x1400040e2  mov     eax, [rsp+78h+arg_8]
0x1400040e9  mov     [rbx+40h], eax
0x1400040ec  mov     [rbx+44h], ebp
0x1400040ef  mov     rax, [rsp+78h+arg_20]
0x1400040f7  mov     [rbx+28h], rax
0x1400040fb  mov     [rbx+30h], r12
0x1400040ff  mov     rax, [rsp+78h+arg_28]
0x140004107  mov     [rbx+88h], rax
0x14000410e  mov     rax, [rsp+78h+arg_0]
0x140004116  mov     [rbx+90h], rax
0x14000411d  mov     [rbx+48h], rdi
0x140004121  xorps   xmm0, xmm0
0x140004124  xor     eax, eax
0x140004126  movups  xmmword ptr [rbx+68h], xmm0
0x14000412a  mov     [rbx+78h], rax
0x14000412e  movups  xmmword ptr [rbx+50h], xmm0
0x140004132  mov     [rbx+60h], rax
0x140004136  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000413d  test    rax, rax
0x140004140  jz      short loc_140004149
0x140004142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004147  jmp     short loc_14000414C
0x140004149  mov     rax, rdi
0x14000414c  mov     [rbx+80h], rax
0x140004153  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000415a  test    rax, rax
0x14000415d  jz      short loc_140004167
0x14000415f  mov     rcx, rbx
0x140004162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004167  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000416e  test    rax, rax
0x140004171  jz      short loc_140004189
0x140004173  mov     r8d, 400h
0x140004179  mov     rdx, [rsp+78h+arg_60]
0x140004181  mov     rcx, rbx
0x140004184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004189  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004190  test    rax, rax
0x140004193  jz      short loc_14000419D
0x140004195  mov     rcx, rbx
0x140004198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000419d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400041a4  test    rax, rax
0x1400041a7  jz      short loc_1400041B7
0x1400041a9  test    byte ptr [rbx+4], 2
0x1400041ad  jnz     short loc_1400041B7
0x1400041af  mov     rcx, rbx
0x1400041b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041b7  cmp     [rbx+8], edi
0x1400041ba  jl      short loc_1400041D6
0x1400041bc  cmp     r15d, 3
0x1400041c0  jnz     loc_1400042B2
0x1400041c6  mov     ecx, 8000FFFFh; this
0x1400041cb  mov     [rbx+8], ecx
0x1400041ce  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400041d3  mov     [rbx+0Ch], eax
0x1400041d6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400041dd  jnz     short loc_140004204
0x1400041df  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400041e6  test    rax, rax
0x1400041e9  jz      short loc_1400041F4
0x1400041eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041f0  test    al, al
0x1400041f2  jmp     short loc_140004202
0x1400041f4  call    cs:__imp_IsDebuggerPresent
0x1400041fb  nop     dword ptr [rax+rax+00h]
0x140004200  test    eax, eax
0x140004202  jz      short loc_14000420A
0x140004204  test    byte ptr [rbx+4], 2
0x140004208  jz      short loc_14000422E
0x14000420a  mov     rax, cs:g_pfnResultLoggingCallback
0x140004211  test    rax, rax
0x140004214  jz      short loc_140004278
0x140004216  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000421d  jnz     short loc_140004278
0x14000421f  xor     r8d, r8d
0x140004222  xor     edx, edx
0x140004224  mov     rcx, rbx
0x140004227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000422c  jmp     short loc_140004278
0x14000422e  mov     ebp, 800h
0x140004233  mov     rax, cs:g_pfnResultLoggingCallback
0x14000423a  test    rax, rax
0x14000423d  jz      short loc_140004256
0x14000423f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004246  jnz     short loc_140004256
0x140004248  mov     r8d, ebp
0x14000424b  mov     rdx, rsi
0x14000424e  mov     rcx, rbx
0x140004251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004256  cmp     [rsi], di
0x140004259  jnz     short loc_140004269
0x14000425b  mov     r8, rbx; unsigned __int64
0x14000425e  mov     rdx, rbp; unsigned __int16 *
0x140004261  mov     rcx, rsi; this
0x140004264  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004269  mov     rcx, rsi; lpOutputString
0x14000426c  call    cs:__imp_OutputDebugStringW
0x140004273  nop     dword ptr [rax+rax+00h]
0x140004278  test    byte ptr [rbx+4], 4
0x14000427c  jnz     short loc_140004287
0x14000427e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004285  jz      short loc_140004299
0x140004287  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000428e  test    rax, rax
0x140004291  jz      short loc_140004299
0x140004293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004298  nop
0x140004299  mov     rbx, [rsp+78h+arg_10]
0x1400042a1  add     rsp, 40h
0x1400042a5  pop     r15
0x1400042a7  pop     r14
0x1400042a9  pop     r13
0x1400042ab  pop     r12
0x1400042ad  pop     rdi
0x1400042ae  pop     rsi
0x1400042af  pop     rbp
0x1400042b0  retn
0x1400042b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
