# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180003e7c`
- end: `0x180004188`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800028d4`

## callees

- `0x1800022e8`
- `0x1800034b4`
- `0x180003cb8`
- `0x180003e7c`
- `0x180004644`
- `0x180004670`
- `0x180004684`
- `0x1800046a4`
- `0x1800055d8`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f9f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000413c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000413c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800040c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800040c4`

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
0x180003e7c  mov     [rsp+arg_10], rbx
0x180003e81  mov     [rsp+arg_8], edx
0x180003e85  mov     [rsp+arg_0], rcx
0x180003e8a  push    rbp
0x180003e8b  push    rsi
0x180003e8c  push    rdi
0x180003e8d  push    r12
0x180003e8f  push    r13
0x180003e91  push    r14
0x180003e93  push    r15
0x180003e95  sub     rsp, 40h
0x180003e99  mov     r12, r9
0x180003e9c  mov     r13, r8
0x180003e9f  mov     r10, rcx
0x180003ea2  xor     eax, eax
0x180003ea4  mov     rsi, [rsp+78h+lpOutputString]
0x180003eac  mov     [rsi], ax
0x180003eaf  mov     rax, [rsp+78h+arg_60]
0x180003eb7  mov     byte ptr [rax], 0
0x180003eba  mov     r14, [rsp+78h+arg_38]
0x180003ec2  mov     edi, [r14]
0x180003ec5  mov     rbx, [rsp+78h+arg_78]
0x180003ecd  mov     [rbx+8], edi
0x180003ed0  mov     eax, [r14+4]
0x180003ed4  mov     [rbx+0Ch], eax
0x180003ed7  xor     ebp, ebp
0x180003ed9  mov     r15d, [rsp+78h+arg_30]
0x180003ee1  mov     ecx, r15d
0x180003ee4  test    r15d, r15d
0x180003ee7  jz      short loc_180003F4F
0x180003ee9  sub     ecx, 1
0x180003eec  jz      short loc_180003F46
0x180003eee  sub     ecx, 1
0x180003ef1  jz      short loc_180003F01
0x180003ef3  cmp     ecx, 1
0x180003ef6  jnz     short loc_180003F58
0x180003ef8  mov     ecx, edi; this
0x180003efa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003eff  jmp     short loc_180003F56
0x180003f01  test    edi, edi
0x180003f03  js      short loc_180003F3D
0x180003f05  mov     edi, 8007029Ch
0x180003f0a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180003f0e  mov     rax, [rsp+78h+arg_28]
0x180003f16  mov     [rsp+78h+var_50], rax; __int64
0x180003f1b  mov     rax, [rsp+78h+arg_20]
0x180003f23  mov     [rsp+78h+var_58], rax; __int64
0x180003f28  mov     rcx, r10; int
0x180003f2b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003f30  mov     [rbx+8], edi
0x180003f33  mov     ecx, edi; this
0x180003f35  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003f3a  mov     [rbx+0Ch], eax
0x180003f3d  mov     ecx, edi; this
0x180003f3f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180003f44  jmp     short loc_180003F56
0x180003f46  mov     ecx, edi; this
0x180003f48  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003f4d  jmp     short loc_180003F56
0x180003f4f  mov     ecx, edi; this
0x180003f51  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180003f56  mov     ebp, eax
0x180003f58  mov     [rbx], r15d
0x180003f5b  mov     eax, [rsp+78h+arg_70]
0x180003f62  mov     [rbx+4], eax
0x180003f65  cmp     dword ptr [r14+8], 1
0x180003f6a  jnz     short loc_180003F72
0x180003f6c  or      eax, 8
0x180003f6f  mov     [rbx+4], eax
0x180003f72  mov     eax, 1
0x180003f77  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003f7f  inc     eax
0x180003f81  mov     [rbx+10h], eax
0x180003f84  mov     rax, [rsp+78h+arg_40]
0x180003f8c  xor     edi, edi
0x180003f8e  test    rax, rax
0x180003f91  jz      short loc_180003F98
0x180003f93  cmp     [rax], di
0x180003f96  jnz     short loc_180003F9B
0x180003f98  mov     rax, rdi
0x180003f9b  mov     [rbx+18h], rax
0x180003f9f  call    cs:__imp_GetCurrentThreadId
0x180003fa6  nop     dword ptr [rax+rax+00h]
0x180003fab  mov     [rbx+20h], eax
0x180003fae  mov     [rbx+38h], r13
0x180003fb2  mov     eax, [rsp+78h+arg_8]
0x180003fb9  mov     [rbx+40h], eax
0x180003fbc  mov     [rbx+44h], ebp
0x180003fbf  mov     rax, [rsp+78h+arg_20]
0x180003fc7  mov     [rbx+28h], rax
0x180003fcb  mov     [rbx+30h], r12
0x180003fcf  mov     rax, [rsp+78h+arg_28]
0x180003fd7  mov     [rbx+88h], rax
0x180003fde  mov     rax, [rsp+78h+arg_0]
0x180003fe6  mov     [rbx+90h], rax
0x180003fed  mov     [rbx+48h], rdi
0x180003ff1  xorps   xmm0, xmm0
0x180003ff4  xor     eax, eax
0x180003ff6  movups  xmmword ptr [rbx+68h], xmm0
0x180003ffa  mov     [rbx+78h], rax
0x180003ffe  movups  xmmword ptr [rbx+50h], xmm0
0x180004002  mov     [rbx+60h], rax
0x180004006  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000400d  test    rax, rax
0x180004010  jz      short loc_180004019
0x180004012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004017  jmp     short loc_18000401C
0x180004019  mov     rax, rdi
0x18000401c  mov     [rbx+80h], rax
0x180004023  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000402a  test    rax, rax
0x18000402d  jz      short loc_180004037
0x18000402f  mov     rcx, rbx
0x180004032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004037  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000403e  test    rax, rax
0x180004041  jz      short loc_180004059
0x180004043  mov     r8d, 400h
0x180004049  mov     rdx, [rsp+78h+arg_60]
0x180004051  mov     rcx, rbx
0x180004054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004059  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004060  test    rax, rax
0x180004063  jz      short loc_18000406D
0x180004065  mov     rcx, rbx
0x180004068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004074  test    rax, rax
0x180004077  jz      short loc_180004087
0x180004079  test    byte ptr [rbx+4], 2
0x18000407d  jnz     short loc_180004087
0x18000407f  mov     rcx, rbx
0x180004082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004087  cmp     [rbx+8], edi
0x18000408a  jl      short loc_1800040A6
0x18000408c  cmp     r15d, 3
0x180004090  jnz     loc_180004182
0x180004096  mov     ecx, 8000FFFFh; this
0x18000409b  mov     [rbx+8], ecx
0x18000409e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800040a3  mov     [rbx+0Ch], eax
0x1800040a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800040ad  jnz     short loc_1800040D4
0x1800040af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800040b6  test    rax, rax
0x1800040b9  jz      short loc_1800040C4
0x1800040bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c0  test    al, al
0x1800040c2  jmp     short loc_1800040D2
0x1800040c4  call    cs:__imp_IsDebuggerPresent
0x1800040cb  nop     dword ptr [rax+rax+00h]
0x1800040d0  test    eax, eax
0x1800040d2  jz      short loc_1800040DA
0x1800040d4  test    byte ptr [rbx+4], 2
0x1800040d8  jz      short loc_1800040FE
0x1800040da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800040e1  test    rax, rax
0x1800040e4  jz      short loc_180004148
0x1800040e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800040ed  jnz     short loc_180004148
0x1800040ef  xor     r8d, r8d
0x1800040f2  xor     edx, edx
0x1800040f4  mov     rcx, rbx
0x1800040f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040fc  jmp     short loc_180004148
0x1800040fe  mov     ebp, 800h
0x180004103  mov     rax, cs:g_pfnResultLoggingCallback
0x18000410a  test    rax, rax
0x18000410d  jz      short loc_180004126
0x18000410f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004116  jnz     short loc_180004126
0x180004118  mov     r8d, ebp
0x18000411b  mov     rdx, rsi
0x18000411e  mov     rcx, rbx
0x180004121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004126  cmp     [rsi], di
0x180004129  jnz     short loc_180004139
0x18000412b  mov     r8, rbx; unsigned __int64
0x18000412e  mov     rdx, rbp; unsigned __int16 *
0x180004131  mov     rcx, rsi; this
0x180004134  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004139  mov     rcx, rsi; lpOutputString
0x18000413c  call    cs:__imp_OutputDebugStringW
0x180004143  nop     dword ptr [rax+rax+00h]
0x180004148  test    byte ptr [rbx+4], 4
0x18000414c  jnz     short loc_180004157
0x18000414e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004155  jz      short loc_180004169
0x180004157  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000415e  test    rax, rax
0x180004161  jz      short loc_180004169
0x180004163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004168  nop
0x180004169  mov     rbx, [rsp+78h+arg_10]
0x180004171  add     rsp, 40h
0x180004175  pop     r15
0x180004177  pop     r14
0x180004179  pop     r13
0x18000417b  pop     r12
0x18000417d  pop     rdi
0x18000417e  pop     rsi
0x18000417f  pop     rbp
0x180004180  retn
0x180004182  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
