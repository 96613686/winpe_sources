# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180428050`
- end: `0x18042837e`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `814`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1804250b4`
- `0x180425470`

## callees

- `0x180424fb0`
- `0x180426d14`
- `0x180427b14`
- `0x180428050`
- `0x180428ef0`
- `0x180428f20`
- `0x1804290a0`
- `0x1804290c8`
- `0x18042b28c`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180428194`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180428194`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1804282c0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1804282c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180428339`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180428339`

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
  unsigned int v16; // edi
  int v17; // ebp
  int v18; // eax
  int v19; // edx
  _WORD *v20; // rax
  int v21; // edx
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 (*ModuleName)(void); // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-68h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v16 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v17 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v18 = wil::details::RecordReturn((wil::details *)v16, a2);
        break;
      case 2:
        if ( (v16 & 0x80000000) == 0 )
        {
          v16 = -2147024228;
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v19);
        }
        v18 = wil::details::RecordLog((wil::details *)v16, a2);
        break;
      case 3:
        v18 = wil::details::RecordFailFast((wil::details *)v16, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v18 = wil::details::RecordException((wil::details *)v16, a2);
  }
  v17 = v18;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v17;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (*)(void))wil::details::g_pfnGetModuleName();
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v21);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180428050  mov     qword ptr [rsp+arg_18], r9
0x180428055  mov     qword ptr [rsp+arg_10], r8
0x18042805a  mov     [rsp+arg_8], edx
0x18042805e  mov     qword ptr [rsp+arg_0], rcx
0x180428063  push    rbx
0x180428064  push    rbp
0x180428065  push    rsi
0x180428066  push    rdi
0x180428067  push    r12
0x180428069  push    r13
0x18042806b  push    r14
0x18042806d  push    r15
0x18042806f  sub     rsp, 58h
0x180428073  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFEh
0x18042807c  xor     eax, eax
0x18042807e  mov     rsi, [rsp+98h+lpOutputString]
0x180428086  mov     [rsi], ax
0x180428089  mov     r12, [rsp+98h+arg_60]
0x180428091  mov     [r12], al
0x180428095  mov     r14, [rsp+98h+arg_38]
0x18042809d  mov     edi, [r14]
0x1804280a0  mov     rbx, [rsp+98h+arg_78]
0x1804280a8  mov     [rbx+8], edi
0x1804280ab  mov     eax, [r14+4]
0x1804280af  mov     [rbx+0Ch], eax
0x1804280b2  xor     ebp, ebp
0x1804280b4  mov     r15d, [rsp+98h+arg_30]
0x1804280bc  mov     ecx, r15d
0x1804280bf  mov     r13, [rsp+98h+arg_28]
0x1804280c7  test    r15d, r15d
0x1804280ca  jz      short loc_180428146
0x1804280cc  sub     ecx, 1
0x1804280cf  jz      short loc_18042813D
0x1804280d1  sub     ecx, 1
0x1804280d4  jz      short loc_1804280E4
0x1804280d6  cmp     ecx, 1
0x1804280d9  jnz     short loc_18042814F
0x1804280db  mov     ecx, edi; this
0x1804280dd  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1804280e2  jmp     short loc_18042814D
0x1804280e4  test    edi, edi
0x1804280e6  js      short loc_180428134
0x1804280e8  mov     edi, 8007029Ch
0x1804280ed  mov     dword ptr [rsp+98h+var_68], edi; wil::details *
0x1804280f1  mov     [rsp+98h+var_70], r13; __int64
0x1804280f6  mov     rax, [rsp+98h+arg_20]
0x1804280fe  mov     [rsp+98h+var_78], rax; __int64
0x180428103  mov     r9, qword ptr [rsp+98h+arg_18]; int
0x18042810b  mov     r8, qword ptr [rsp+98h+arg_10]; int
0x180428113  mov     edx, [rsp+98h+arg_8]; int
0x18042811a  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x180428122  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180428127  mov     [rbx+8], edi
0x18042812a  mov     ecx, edi; this
0x18042812c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180428131  mov     [rbx+0Ch], eax
0x180428134  mov     ecx, edi; this
0x180428136  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18042813b  jmp     short loc_18042814D
0x18042813d  mov     ecx, edi; this
0x18042813f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180428144  jmp     short loc_18042814D
0x180428146  mov     ecx, edi; this
0x180428148  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18042814d  mov     ebp, eax
0x18042814f  mov     [rbx], r15d
0x180428152  mov     eax, [rsp+98h+arg_70]
0x180428159  mov     [rbx+4], eax
0x18042815c  cmp     dword ptr [r14+8], 1
0x180428161  jnz     short loc_180428169
0x180428163  or      eax, 8
0x180428166  mov     [rbx+4], eax
0x180428169  mov     eax, 1
0x18042816e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180428176  inc     eax
0x180428178  mov     [rbx+10h], eax
0x18042817b  mov     rax, [rsp+98h+arg_40]
0x180428183  test    rax, rax
0x180428186  jz      short loc_18042818E
0x180428188  cmp     word ptr [rax], 0
0x18042818c  jnz     short loc_180428190
0x18042818e  xor     eax, eax
0x180428190  mov     [rbx+18h], rax
0x180428194  call    cs:__imp_GetCurrentThreadId
0x18042819b  nop     dword ptr [rax+rax+00h]
0x1804281a0  mov     [rbx+20h], eax
0x1804281a3  mov     rax, qword ptr [rsp+98h+arg_10]
0x1804281ab  mov     [rbx+38h], rax
0x1804281af  mov     eax, [rsp+98h+arg_8]
0x1804281b6  mov     [rbx+40h], eax
0x1804281b9  mov     [rbx+44h], ebp
0x1804281bc  mov     rax, [rsp+98h+arg_20]
0x1804281c4  mov     [rbx+28h], rax
0x1804281c8  mov     rax, qword ptr [rsp+98h+arg_18]
0x1804281d0  mov     [rbx+30h], rax
0x1804281d4  mov     [rbx+88h], r13
0x1804281db  mov     rax, qword ptr [rsp+98h+arg_0]
0x1804281e3  mov     [rbx+90h], rax
0x1804281ea  mov     qword ptr [rbx+48h], 0
0x1804281f2  xorps   xmm0, xmm0
0x1804281f5  xor     eax, eax
0x1804281f7  movups  xmmword ptr [rbx+68h], xmm0
0x1804281fb  mov     [rbx+78h], rax
0x1804281ff  movups  xmmword ptr [rbx+50h], xmm0
0x180428203  mov     [rbx+60h], rax
0x180428207  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18042820e  test    rax, rax
0x180428211  jz      short loc_180428218
0x180428213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428218  mov     [rbx+80h], rax
0x18042821f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180428226  test    rax, rax
0x180428229  jz      short loc_180428233
0x18042822b  mov     rcx, rbx
0x18042822e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428233  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18042823a  test    rax, rax
0x18042823d  jz      short loc_180428250
0x18042823f  mov     r8d, 400h
0x180428245  mov     rdx, r12
0x180428248  mov     rcx, rbx
0x18042824b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428250  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180428257  test    rax, rax
0x18042825a  jz      short loc_180428264
0x18042825c  mov     rcx, rbx
0x18042825f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428264  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18042826b  test    rax, rax
0x18042826e  jz      short loc_18042827E
0x180428270  test    byte ptr [rbx+4], 2
0x180428274  jnz     short loc_18042827E
0x180428276  mov     rcx, rbx
0x180428279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042827e  cmp     dword ptr [rbx+8], 0
0x180428282  jl      short loc_1804282A2
0x180428284  cmp     r15d, 3
0x180428288  jnz     loc_180428378
0x18042828e  mov     dword ptr [rbx+8], 8000FFFFh
0x180428295  mov     ecx, 8000FFFFh; this
0x18042829a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18042829f  mov     [rbx+0Ch], eax
0x1804282a2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1804282a9  jnz     short loc_1804282D0
0x1804282ab  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1804282b2  test    rax, rax
0x1804282b5  jz      short loc_1804282C0
0x1804282b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804282bc  test    al, al
0x1804282be  jmp     short loc_1804282CE
0x1804282c0  call    cs:__imp_IsDebuggerPresent
0x1804282c7  nop     dword ptr [rax+rax+00h]
0x1804282cc  test    eax, eax
0x1804282ce  jz      short loc_1804282D6
0x1804282d0  test    byte ptr [rbx+4], 2
0x1804282d4  jz      short loc_1804282FA
0x1804282d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1804282dd  test    rax, rax
0x1804282e0  jz      short loc_180428345
0x1804282e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1804282e9  jnz     short loc_180428345
0x1804282eb  xor     r8d, r8d
0x1804282ee  xor     edx, edx
0x1804282f0  mov     rcx, rbx
0x1804282f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804282f8  jmp     short loc_180428345
0x1804282fa  mov     rax, cs:g_pfnResultLoggingCallback
0x180428301  test    rax, rax
0x180428304  jz      short loc_180428320
0x180428306  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18042830d  jnz     short loc_180428320
0x18042830f  mov     r8d, 800h
0x180428315  mov     rdx, rsi
0x180428318  mov     rcx, rbx
0x18042831b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428320  cmp     word ptr [rsi], 0
0x180428324  jnz     short loc_180428336
0x180428326  mov     r8, rbx; unsigned __int64
0x180428329  mov     edx, 800h; unsigned __int16 *
0x18042832e  mov     rcx, rsi; this
0x180428331  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180428336  mov     rcx, rsi; lpOutputString
0x180428339  call    cs:__imp_OutputDebugStringW
0x180428340  nop     dword ptr [rax+rax+00h]
0x180428345  test    byte ptr [rbx+4], 4
0x180428349  jnz     short loc_180428354
0x18042834b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180428352  jz      short loc_180428366
0x180428354  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18042835b  test    rax, rax
0x18042835e  jz      short loc_180428366
0x180428360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180428365  nop
0x180428366  add     rsp, 58h
0x18042836a  pop     r15
0x18042836c  pop     r14
0x18042836e  pop     r13
0x180428370  pop     r12
0x180428372  pop     rdi
0x180428373  pop     rsi
0x180428374  pop     rbp
0x180428375  pop     rbx
0x180428376  retn
0x180428378  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
