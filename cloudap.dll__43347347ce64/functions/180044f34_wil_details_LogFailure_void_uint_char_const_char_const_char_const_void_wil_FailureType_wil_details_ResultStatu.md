# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180044f34`
- end: `0x18004522d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180043a9c`
- `0x180043df8`

## callees

- `0x18003ab68`
- `0x18003ffb4`
- `0x1800401a4`
- `0x180040c98`
- `0x180044f34`
- `0x180045684`
- `0x1800456a0`
- `0x1800456b4`
- `0x180046544`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045057`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800451e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800451e8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180045176`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180045176`

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
0x180044f34  mov     [rsp+arg_10], rbx
0x180044f39  mov     [rsp+arg_8], edx
0x180044f3d  mov     [rsp+arg_0], rcx
0x180044f42  push    rbp
0x180044f43  push    rsi
0x180044f44  push    rdi
0x180044f45  push    r12
0x180044f47  push    r13
0x180044f49  push    r14
0x180044f4b  push    r15
0x180044f4d  sub     rsp, 40h
0x180044f51  mov     r12, r9
0x180044f54  mov     r13, r8
0x180044f57  mov     r10, rcx
0x180044f5a  xor     eax, eax
0x180044f5c  mov     rsi, [rsp+78h+lpOutputString]
0x180044f64  mov     [rsi], ax
0x180044f67  mov     rax, [rsp+78h+arg_60]
0x180044f6f  mov     byte ptr [rax], 0
0x180044f72  mov     r14, [rsp+78h+arg_38]
0x180044f7a  mov     edi, [r14]
0x180044f7d  mov     rbx, [rsp+78h+arg_78]
0x180044f85  mov     [rbx+8], edi
0x180044f88  mov     eax, [r14+4]
0x180044f8c  mov     [rbx+0Ch], eax
0x180044f8f  xor     ebp, ebp
0x180044f91  mov     r15d, [rsp+78h+arg_30]
0x180044f99  mov     ecx, r15d
0x180044f9c  test    r15d, r15d
0x180044f9f  jz      short loc_180045007
0x180044fa1  sub     ecx, 1
0x180044fa4  jz      short loc_180044FFE
0x180044fa6  sub     ecx, 1
0x180044fa9  jz      short loc_180044FB9
0x180044fab  cmp     ecx, 1
0x180044fae  jnz     short loc_180045010
0x180044fb0  mov     ecx, edi; this
0x180044fb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180044fb7  jmp     short loc_18004500E
0x180044fb9  test    edi, edi
0x180044fbb  js      short loc_180044FF5
0x180044fbd  mov     edi, 8007029Ch
0x180044fc2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180044fc6  mov     rax, [rsp+78h+arg_28]
0x180044fce  mov     [rsp+78h+var_50], rax; __int64
0x180044fd3  mov     rax, [rsp+78h+arg_20]
0x180044fdb  mov     [rsp+78h+var_58], rax; __int64
0x180044fe0  mov     rcx, r10; int
0x180044fe3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180044fe8  mov     [rbx+8], edi
0x180044feb  mov     ecx, edi; this
0x180044fed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180044ff2  mov     [rbx+0Ch], eax
0x180044ff5  mov     ecx, edi; this
0x180044ff7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180044ffc  jmp     short loc_18004500E
0x180044ffe  mov     ecx, edi; this
0x180045000  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180045005  jmp     short loc_18004500E
0x180045007  mov     ecx, edi; this
0x180045009  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004500e  mov     ebp, eax
0x180045010  mov     [rbx], r15d
0x180045013  mov     eax, [rsp+78h+arg_70]
0x18004501a  mov     [rbx+4], eax
0x18004501d  cmp     dword ptr [r14+8], 1
0x180045022  jnz     short loc_18004502A
0x180045024  or      eax, 8
0x180045027  mov     [rbx+4], eax
0x18004502a  mov     eax, 1
0x18004502f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180045037  inc     eax
0x180045039  mov     [rbx+10h], eax
0x18004503c  mov     rax, [rsp+78h+arg_40]
0x180045044  xor     edi, edi
0x180045046  test    rax, rax
0x180045049  jz      short loc_180045050
0x18004504b  cmp     [rax], di
0x18004504e  jnz     short loc_180045053
0x180045050  mov     rax, rdi
0x180045053  mov     [rbx+18h], rax
0x180045057  call    cs:__imp_GetCurrentThreadId
0x18004505d  mov     [rbx+20h], eax
0x180045060  mov     [rbx+38h], r13
0x180045064  mov     eax, [rsp+78h+arg_8]
0x18004506b  mov     [rbx+40h], eax
0x18004506e  mov     [rbx+44h], ebp
0x180045071  mov     rax, [rsp+78h+arg_20]
0x180045079  mov     [rbx+28h], rax
0x18004507d  mov     [rbx+30h], r12
0x180045081  mov     rax, [rsp+78h+arg_28]
0x180045089  mov     [rbx+88h], rax
0x180045090  mov     rax, [rsp+78h+arg_0]
0x180045098  mov     [rbx+90h], rax
0x18004509f  mov     [rbx+48h], rdi
0x1800450a3  xorps   xmm0, xmm0
0x1800450a6  xor     eax, eax
0x1800450a8  movups  xmmword ptr [rbx+68h], xmm0
0x1800450ac  mov     [rbx+78h], rax
0x1800450b0  movups  xmmword ptr [rbx+50h], xmm0
0x1800450b4  mov     [rbx+60h], rax
0x1800450b8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800450bf  test    rax, rax
0x1800450c2  jz      short loc_1800450CB
0x1800450c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450c9  jmp     short loc_1800450CE
0x1800450cb  mov     rax, rdi
0x1800450ce  mov     [rbx+80h], rax
0x1800450d5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800450dc  test    rax, rax
0x1800450df  jz      short loc_1800450E9
0x1800450e1  mov     rcx, rbx
0x1800450e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800450f0  test    rax, rax
0x1800450f3  jz      short loc_18004510B
0x1800450f5  mov     r8d, 400h
0x1800450fb  mov     rdx, [rsp+78h+arg_60]
0x180045103  mov     rcx, rbx
0x180045106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004510b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180045112  test    rax, rax
0x180045115  jz      short loc_18004511F
0x180045117  mov     rcx, rbx
0x18004511a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004511f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180045126  test    rax, rax
0x180045129  jz      short loc_180045139
0x18004512b  test    byte ptr [rbx+4], 2
0x18004512f  jnz     short loc_180045139
0x180045131  mov     rcx, rbx
0x180045134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045139  cmp     [rbx+8], edi
0x18004513c  jl      short loc_180045158
0x18004513e  cmp     r15d, 3
0x180045142  jnz     loc_180045227
0x180045148  mov     ecx, 8000FFFFh; this
0x18004514d  mov     [rbx+8], ecx
0x180045150  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180045155  mov     [rbx+0Ch], eax
0x180045158  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004515f  jnz     short loc_180045180
0x180045161  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180045168  test    rax, rax
0x18004516b  jz      short loc_180045176
0x18004516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045172  test    al, al
0x180045174  jmp     short loc_18004517E
0x180045176  call    cs:__imp_IsDebuggerPresent
0x18004517c  test    eax, eax
0x18004517e  jz      short loc_180045186
0x180045180  test    byte ptr [rbx+4], 2
0x180045184  jz      short loc_1800451AA
0x180045186  mov     rax, cs:g_pfnResultLoggingCallback
0x18004518d  test    rax, rax
0x180045190  jz      short loc_1800451EE
0x180045192  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180045199  jnz     short loc_1800451EE
0x18004519b  xor     r8d, r8d
0x18004519e  xor     edx, edx
0x1800451a0  mov     rcx, rbx
0x1800451a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451a8  jmp     short loc_1800451EE
0x1800451aa  mov     ebp, 800h
0x1800451af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800451b6  test    rax, rax
0x1800451b9  jz      short loc_1800451D2
0x1800451bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800451c2  jnz     short loc_1800451D2
0x1800451c4  mov     r8d, ebp
0x1800451c7  mov     rdx, rsi
0x1800451ca  mov     rcx, rbx
0x1800451cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451d2  cmp     [rsi], di
0x1800451d5  jnz     short loc_1800451E5
0x1800451d7  mov     r8, rbx; unsigned __int64
0x1800451da  mov     rdx, rbp; unsigned __int16 *
0x1800451dd  mov     rcx, rsi; this
0x1800451e0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800451e5  mov     rcx, rsi; lpOutputString
0x1800451e8  call    cs:__imp_OutputDebugStringW
0x1800451ee  test    byte ptr [rbx+4], 4
0x1800451f2  jnz     short loc_1800451FD
0x1800451f4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800451fb  jz      short loc_18004520F
0x1800451fd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180045204  test    rax, rax
0x180045207  jz      short loc_18004520F
0x180045209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004520e  nop
0x18004520f  mov     rbx, [rsp+78h+arg_10]
0x180045217  add     rsp, 40h
0x18004521b  pop     r15
0x18004521d  pop     r14
0x18004521f  pop     r13
0x180045221  pop     r12
0x180045223  pop     rdi
0x180045224  pop     rsi
0x180045225  pop     rbp
0x180045226  retn
0x180045227  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
