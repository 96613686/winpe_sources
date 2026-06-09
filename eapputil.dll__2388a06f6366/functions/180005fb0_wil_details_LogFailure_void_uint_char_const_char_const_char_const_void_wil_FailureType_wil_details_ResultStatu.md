# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005fb0`
- end: `0x1800062a9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004258`

## callees

- `0x180003c64`
- `0x180005584`
- `0x180005d24`
- `0x180005fb0`
- `0x1800065b8`
- `0x1800065e0`
- `0x1800065f4`
- `0x180006610`
- `0x180007a2c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800061f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800061f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006264`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006264`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180005fb0  mov     [rsp+arg_10], rbx
0x180005fb5  mov     [rsp+arg_8], edx
0x180005fb9  mov     [rsp+arg_0], rcx
0x180005fbe  push    rbp
0x180005fbf  push    rsi
0x180005fc0  push    rdi
0x180005fc1  push    r12
0x180005fc3  push    r13
0x180005fc5  push    r14
0x180005fc7  push    r15
0x180005fc9  sub     rsp, 40h
0x180005fcd  mov     r12, r9
0x180005fd0  mov     r13, r8
0x180005fd3  mov     r10, rcx
0x180005fd6  xor     eax, eax
0x180005fd8  mov     rsi, [rsp+78h+lpOutputString]
0x180005fe0  mov     [rsi], ax
0x180005fe3  mov     rax, [rsp+78h+arg_60]
0x180005feb  mov     byte ptr [rax], 0
0x180005fee  mov     r14, [rsp+78h+arg_38]
0x180005ff6  mov     edi, [r14]
0x180005ff9  mov     rbx, [rsp+78h+arg_78]
0x180006001  mov     [rbx+8], edi
0x180006004  mov     eax, [r14+4]
0x180006008  mov     [rbx+0Ch], eax
0x18000600b  xor     ebp, ebp
0x18000600d  mov     r15d, [rsp+78h+arg_30]
0x180006015  mov     ecx, r15d
0x180006018  test    r15d, r15d
0x18000601b  jz      short loc_180006083
0x18000601d  sub     ecx, 1
0x180006020  jz      short loc_18000607A
0x180006022  sub     ecx, 1
0x180006025  jz      short loc_180006035
0x180006027  cmp     ecx, 1
0x18000602a  jnz     short loc_18000608C
0x18000602c  mov     ecx, edi; this
0x18000602e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006033  jmp     short loc_18000608A
0x180006035  test    edi, edi
0x180006037  js      short loc_180006071
0x180006039  mov     edi, 8007029Ch
0x18000603e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006042  mov     rax, [rsp+78h+arg_28]
0x18000604a  mov     [rsp+78h+var_50], rax; __int64
0x18000604f  mov     rax, [rsp+78h+arg_20]
0x180006057  mov     [rsp+78h+var_58], rax; __int64
0x18000605c  mov     rcx, r10; int
0x18000605f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006064  mov     [rbx+8], edi
0x180006067  mov     ecx, edi; this
0x180006069  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000606e  mov     [rbx+0Ch], eax
0x180006071  mov     ecx, edi; this
0x180006073  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006078  jmp     short loc_18000608A
0x18000607a  mov     ecx, edi; this
0x18000607c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006081  jmp     short loc_18000608A
0x180006083  mov     ecx, edi; this
0x180006085  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000608a  mov     ebp, eax
0x18000608c  mov     [rbx], r15d
0x18000608f  mov     eax, [rsp+78h+arg_70]
0x180006096  mov     [rbx+4], eax
0x180006099  cmp     dword ptr [r14+8], 1
0x18000609e  jnz     short loc_1800060A6
0x1800060a0  or      eax, 8
0x1800060a3  mov     [rbx+4], eax
0x1800060a6  mov     eax, 1
0x1800060ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800060b3  inc     eax
0x1800060b5  mov     [rbx+10h], eax
0x1800060b8  mov     rax, [rsp+78h+arg_40]
0x1800060c0  xor     edi, edi
0x1800060c2  test    rax, rax
0x1800060c5  jz      short loc_1800060CC
0x1800060c7  cmp     [rax], di
0x1800060ca  jnz     short loc_1800060CF
0x1800060cc  mov     rax, rdi
0x1800060cf  mov     [rbx+18h], rax
0x1800060d3  call    cs:__imp_GetCurrentThreadId
0x1800060d9  mov     [rbx+20h], eax
0x1800060dc  mov     [rbx+38h], r13
0x1800060e0  mov     eax, [rsp+78h+arg_8]
0x1800060e7  mov     [rbx+40h], eax
0x1800060ea  mov     [rbx+44h], ebp
0x1800060ed  mov     rax, [rsp+78h+arg_20]
0x1800060f5  mov     [rbx+28h], rax
0x1800060f9  mov     [rbx+30h], r12
0x1800060fd  mov     rax, [rsp+78h+arg_28]
0x180006105  mov     [rbx+88h], rax
0x18000610c  mov     rax, [rsp+78h+arg_0]
0x180006114  mov     [rbx+90h], rax
0x18000611b  mov     [rbx+48h], rdi
0x18000611f  xorps   xmm0, xmm0
0x180006122  xor     eax, eax
0x180006124  movups  xmmword ptr [rbx+68h], xmm0
0x180006128  mov     [rbx+78h], rax
0x18000612c  movups  xmmword ptr [rbx+50h], xmm0
0x180006130  mov     [rbx+60h], rax
0x180006134  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000613b  test    rax, rax
0x18000613e  jz      short loc_180006147
0x180006140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006145  jmp     short loc_18000614A
0x180006147  mov     rax, rdi
0x18000614a  mov     [rbx+80h], rax
0x180006151  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006158  test    rax, rax
0x18000615b  jz      short loc_180006165
0x18000615d  mov     rcx, rbx
0x180006160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006165  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000616c  test    rax, rax
0x18000616f  jz      short loc_180006187
0x180006171  mov     r8d, 400h
0x180006177  mov     rdx, [rsp+78h+arg_60]
0x18000617f  mov     rcx, rbx
0x180006182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006187  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000618e  test    rax, rax
0x180006191  jz      short loc_18000619B
0x180006193  mov     rcx, rbx
0x180006196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800061a2  test    rax, rax
0x1800061a5  jz      short loc_1800061B5
0x1800061a7  test    byte ptr [rbx+4], 2
0x1800061ab  jnz     short loc_1800061B5
0x1800061ad  mov     rcx, rbx
0x1800061b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b5  cmp     [rbx+8], edi
0x1800061b8  jl      short loc_1800061D4
0x1800061ba  cmp     r15d, 3
0x1800061be  jnz     loc_1800062A3
0x1800061c4  mov     ecx, 8000FFFFh; this
0x1800061c9  mov     [rbx+8], ecx
0x1800061cc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800061d1  mov     [rbx+0Ch], eax
0x1800061d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800061db  jnz     short loc_1800061FC
0x1800061dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800061e4  test    rax, rax
0x1800061e7  jz      short loc_1800061F2
0x1800061e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ee  test    al, al
0x1800061f0  jmp     short loc_1800061FA
0x1800061f2  call    cs:__imp_IsDebuggerPresent
0x1800061f8  test    eax, eax
0x1800061fa  jz      short loc_180006202
0x1800061fc  test    byte ptr [rbx+4], 2
0x180006200  jz      short loc_180006226
0x180006202  mov     rax, cs:g_pfnResultLoggingCallback
0x180006209  test    rax, rax
0x18000620c  jz      short loc_18000626A
0x18000620e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006215  jnz     short loc_18000626A
0x180006217  xor     r8d, r8d
0x18000621a  xor     edx, edx
0x18000621c  mov     rcx, rbx
0x18000621f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006224  jmp     short loc_18000626A
0x180006226  mov     ebp, 800h
0x18000622b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006232  test    rax, rax
0x180006235  jz      short loc_18000624E
0x180006237  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000623e  jnz     short loc_18000624E
0x180006240  mov     r8d, ebp
0x180006243  mov     rdx, rsi
0x180006246  mov     rcx, rbx
0x180006249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624e  cmp     [rsi], di
0x180006251  jnz     short loc_180006261
0x180006253  mov     r8, rbx; unsigned __int64
0x180006256  mov     rdx, rbp; unsigned __int16 *
0x180006259  mov     rcx, rsi; this
0x18000625c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006261  mov     rcx, rsi; lpOutputString
0x180006264  call    cs:__imp_OutputDebugStringW
0x18000626a  test    byte ptr [rbx+4], 4
0x18000626e  jnz     short loc_180006279
0x180006270  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006277  jz      short loc_18000628B
0x180006279  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006280  test    rax, rax
0x180006283  jz      short loc_18000628B
0x180006285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628a  nop
0x18000628b  mov     rbx, [rsp+78h+arg_10]
0x180006293  add     rsp, 40h
0x180006297  pop     r15
0x180006299  pop     r14
0x18000629b  pop     r13
0x18000629d  pop     r12
0x18000629f  pop     rdi
0x1800062a0  pop     rsi
0x1800062a1  pop     rbp
0x1800062a2  retn
0x1800062a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
