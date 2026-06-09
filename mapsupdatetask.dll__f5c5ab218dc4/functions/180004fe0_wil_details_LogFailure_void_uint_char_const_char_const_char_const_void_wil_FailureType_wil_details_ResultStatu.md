# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004fe0`
- end: `0x1800052d9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002fc0`

## callees

- `0x1800029fc`
- `0x180004534`
- `0x180004cd0`
- `0x180004fe0`
- `0x18000574c`
- `0x180005770`
- `0x180005784`
- `0x1800057a0`
- `0x1800075d4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005103`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005294`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005294`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005222`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005222`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
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
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180004fe0  mov     [rsp+arg_10], rbx
0x180004fe5  mov     [rsp+arg_8], edx
0x180004fe9  mov     [rsp+arg_0], rcx
0x180004fee  push    rbp
0x180004fef  push    rsi
0x180004ff0  push    rdi
0x180004ff1  push    r12
0x180004ff3  push    r13
0x180004ff5  push    r14
0x180004ff7  push    r15
0x180004ff9  sub     rsp, 40h
0x180004ffd  mov     r12, r9
0x180005000  mov     r13, r8
0x180005003  mov     r10, rcx
0x180005006  xor     eax, eax
0x180005008  mov     rsi, [rsp+78h+lpOutputString]
0x180005010  mov     [rsi], ax
0x180005013  mov     rax, [rsp+78h+arg_60]
0x18000501b  mov     byte ptr [rax], 0
0x18000501e  mov     r14, [rsp+78h+arg_38]
0x180005026  mov     edi, [r14]
0x180005029  mov     rbx, [rsp+78h+arg_78]
0x180005031  mov     [rbx+8], edi
0x180005034  mov     eax, [r14+4]
0x180005038  mov     [rbx+0Ch], eax
0x18000503b  xor     ebp, ebp
0x18000503d  mov     r15d, [rsp+78h+arg_30]
0x180005045  mov     ecx, r15d
0x180005048  test    r15d, r15d
0x18000504b  jz      short loc_1800050B3
0x18000504d  sub     ecx, 1
0x180005050  jz      short loc_1800050AA
0x180005052  sub     ecx, 1
0x180005055  jz      short loc_180005065
0x180005057  cmp     ecx, 1
0x18000505a  jnz     short loc_1800050BC
0x18000505c  mov     ecx, edi; this
0x18000505e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005063  jmp     short loc_1800050BA
0x180005065  test    edi, edi
0x180005067  js      short loc_1800050A1
0x180005069  mov     edi, 8007029Ch
0x18000506e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005072  mov     rax, [rsp+78h+arg_28]
0x18000507a  mov     [rsp+78h+var_50], rax; __int64
0x18000507f  mov     rax, [rsp+78h+arg_20]
0x180005087  mov     [rsp+78h+var_58], rax; __int64
0x18000508c  mov     rcx, r10; int
0x18000508f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005094  mov     [rbx+8], edi
0x180005097  mov     ecx, edi; this
0x180005099  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000509e  mov     [rbx+0Ch], eax
0x1800050a1  mov     ecx, edi; this
0x1800050a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800050a8  jmp     short loc_1800050BA
0x1800050aa  mov     ecx, edi; this
0x1800050ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800050b1  jmp     short loc_1800050BA
0x1800050b3  mov     ecx, edi; this
0x1800050b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800050ba  mov     ebp, eax
0x1800050bc  mov     [rbx], r15d
0x1800050bf  mov     eax, [rsp+78h+arg_70]
0x1800050c6  mov     [rbx+4], eax
0x1800050c9  cmp     dword ptr [r14+8], 1
0x1800050ce  jnz     short loc_1800050D6
0x1800050d0  or      eax, 8
0x1800050d3  mov     [rbx+4], eax
0x1800050d6  mov     eax, 1
0x1800050db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800050e3  inc     eax
0x1800050e5  mov     [rbx+10h], eax
0x1800050e8  mov     rax, [rsp+78h+arg_40]
0x1800050f0  xor     edi, edi
0x1800050f2  test    rax, rax
0x1800050f5  jz      short loc_1800050FC
0x1800050f7  cmp     [rax], di
0x1800050fa  jnz     short loc_1800050FF
0x1800050fc  mov     rax, rdi
0x1800050ff  mov     [rbx+18h], rax
0x180005103  call    cs:__imp_GetCurrentThreadId
0x180005109  mov     [rbx+20h], eax
0x18000510c  mov     [rbx+38h], r13
0x180005110  mov     eax, [rsp+78h+arg_8]
0x180005117  mov     [rbx+40h], eax
0x18000511a  mov     [rbx+44h], ebp
0x18000511d  mov     rax, [rsp+78h+arg_20]
0x180005125  mov     [rbx+28h], rax
0x180005129  mov     [rbx+30h], r12
0x18000512d  mov     rax, [rsp+78h+arg_28]
0x180005135  mov     [rbx+88h], rax
0x18000513c  mov     rax, [rsp+78h+arg_0]
0x180005144  mov     [rbx+90h], rax
0x18000514b  mov     [rbx+48h], rdi
0x18000514f  xorps   xmm0, xmm0
0x180005152  xor     eax, eax
0x180005154  movups  xmmword ptr [rbx+68h], xmm0
0x180005158  mov     [rbx+78h], rax
0x18000515c  movups  xmmword ptr [rbx+50h], xmm0
0x180005160  mov     [rbx+60h], rax
0x180005164  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000516b  test    rax, rax
0x18000516e  jz      short loc_180005177
0x180005170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005175  jmp     short loc_18000517A
0x180005177  mov     rax, rdi
0x18000517a  mov     [rbx+80h], rax
0x180005181  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005188  test    rax, rax
0x18000518b  jz      short loc_180005195
0x18000518d  mov     rcx, rbx
0x180005190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005195  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000519c  test    rax, rax
0x18000519f  jz      short loc_1800051B7
0x1800051a1  mov     r8d, 400h
0x1800051a7  mov     rdx, [rsp+78h+arg_60]
0x1800051af  mov     rcx, rbx
0x1800051b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800051be  test    rax, rax
0x1800051c1  jz      short loc_1800051CB
0x1800051c3  mov     rcx, rbx
0x1800051c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800051d2  test    rax, rax
0x1800051d5  jz      short loc_1800051E5
0x1800051d7  test    byte ptr [rbx+4], 2
0x1800051db  jnz     short loc_1800051E5
0x1800051dd  mov     rcx, rbx
0x1800051e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e5  cmp     [rbx+8], edi
0x1800051e8  jl      short loc_180005204
0x1800051ea  cmp     r15d, 3
0x1800051ee  jnz     loc_1800052D3
0x1800051f4  mov     ecx, 8000FFFFh; this
0x1800051f9  mov     [rbx+8], ecx
0x1800051fc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005201  mov     [rbx+0Ch], eax
0x180005204  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000520b  jnz     short loc_18000522C
0x18000520d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005214  test    rax, rax
0x180005217  jz      short loc_180005222
0x180005219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000521e  test    al, al
0x180005220  jmp     short loc_18000522A
0x180005222  call    cs:__imp_IsDebuggerPresent
0x180005228  test    eax, eax
0x18000522a  jz      short loc_180005232
0x18000522c  test    byte ptr [rbx+4], 2
0x180005230  jz      short loc_180005256
0x180005232  mov     rax, cs:g_pfnResultLoggingCallback
0x180005239  test    rax, rax
0x18000523c  jz      short loc_18000529A
0x18000523e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005245  jnz     short loc_18000529A
0x180005247  xor     r8d, r8d
0x18000524a  xor     edx, edx
0x18000524c  mov     rcx, rbx
0x18000524f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005254  jmp     short loc_18000529A
0x180005256  mov     ebp, 800h
0x18000525b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005262  test    rax, rax
0x180005265  jz      short loc_18000527E
0x180005267  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000526e  jnz     short loc_18000527E
0x180005270  mov     r8d, ebp
0x180005273  mov     rdx, rsi
0x180005276  mov     rcx, rbx
0x180005279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000527e  cmp     [rsi], di
0x180005281  jnz     short loc_180005291
0x180005283  mov     r8, rbx; unsigned __int64
0x180005286  mov     rdx, rbp; unsigned __int16 *
0x180005289  mov     rcx, rsi; this
0x18000528c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005291  mov     rcx, rsi; lpOutputString
0x180005294  call    cs:__imp_OutputDebugStringW
0x18000529a  test    byte ptr [rbx+4], 4
0x18000529e  jnz     short loc_1800052A9
0x1800052a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800052a7  jz      short loc_1800052BB
0x1800052a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800052b0  test    rax, rax
0x1800052b3  jz      short loc_1800052BB
0x1800052b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ba  nop
0x1800052bb  mov     rbx, [rsp+78h+arg_10]
0x1800052c3  add     rsp, 40h
0x1800052c7  pop     r15
0x1800052c9  pop     r14
0x1800052cb  pop     r13
0x1800052cd  pop     r12
0x1800052cf  pop     rdi
0x1800052d0  pop     rsi
0x1800052d1  pop     rbp
0x1800052d2  retn
0x1800052d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
