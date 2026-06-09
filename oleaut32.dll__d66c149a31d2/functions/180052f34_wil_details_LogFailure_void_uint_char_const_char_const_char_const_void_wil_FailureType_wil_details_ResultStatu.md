# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180052f34`
- end: `0x18005322c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18004f544`
- `0x18004f888`

## callees

- `0x180042a5c`
- `0x1800438c8`
- `0x18004f484`
- `0x1800520a4`
- `0x180052f34`
- `0x18005427c`
- `0x1800542a0`
- `0x1800543f0`
- `0x18005674c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053057`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800531e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800531e8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180053176`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180053176`

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
        WCHAR *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW(lpOutputString);
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
0x180052f34  mov     [rsp+arg_10], rbx
0x180052f39  mov     [rsp+arg_8], edx
0x180052f3d  mov     [rsp+arg_0], rcx
0x180052f42  push    rbp
0x180052f43  push    rsi
0x180052f44  push    rdi
0x180052f45  push    r12
0x180052f47  push    r13
0x180052f49  push    r14
0x180052f4b  push    r15
0x180052f4d  sub     rsp, 40h
0x180052f51  mov     r14, [rsp+78h+arg_38]
0x180052f59  xor     eax, eax
0x180052f5b  mov     rbx, [rsp+78h+arg_78]
0x180052f63  xor     ebp, ebp
0x180052f65  mov     r15d, [rsp+78h+arg_30]
0x180052f6d  mov     r10, rcx
0x180052f70  mov     rsi, [rsp+78h+lpOutputString]
0x180052f78  mov     r12, r9
0x180052f7b  mov     r13, r8
0x180052f7e  mov     ecx, r15d
0x180052f81  mov     [rsi], ax
0x180052f84  mov     rax, [rsp+78h+arg_60]
0x180052f8c  mov     byte ptr [rax], 0
0x180052f8f  mov     edi, [r14]
0x180052f92  mov     [rbx+8], edi
0x180052f95  mov     eax, [r14+4]
0x180052f99  mov     [rbx+0Ch], eax
0x180052f9c  test    r15d, r15d
0x180052f9f  jz      short loc_180053007
0x180052fa1  sub     ecx, 1
0x180052fa4  jz      short loc_180052FFE
0x180052fa6  sub     ecx, 1
0x180052fa9  jz      short loc_180052FB9
0x180052fab  cmp     ecx, 1
0x180052fae  jnz     short loc_180053010
0x180052fb0  mov     ecx, edi; this
0x180052fb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180052fb7  jmp     short loc_18005300E
0x180052fb9  test    edi, edi
0x180052fbb  js      short loc_180052FF5
0x180052fbd  mov     rax, [rsp+78h+arg_28]
0x180052fc5  mov     edi, 8007029Ch
0x180052fca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180052fce  mov     rcx, r10; int
0x180052fd1  mov     [rsp+78h+var_50], rax; __int64
0x180052fd6  mov     rax, [rsp+78h+arg_20]
0x180052fde  mov     [rsp+78h+var_58], rax; __int64
0x180052fe3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180052fe8  mov     ecx, edi; this
0x180052fea  mov     [rbx+8], edi
0x180052fed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180052ff2  mov     [rbx+0Ch], eax
0x180052ff5  mov     ecx, edi; this
0x180052ff7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180052ffc  jmp     short loc_18005300E
0x180052ffe  mov     ecx, edi; this
0x180053000  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180053005  jmp     short loc_18005300E
0x180053007  mov     ecx, edi; this
0x180053009  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005300e  mov     ebp, eax
0x180053010  mov     eax, [rsp+78h+arg_70]
0x180053017  mov     [rbx+4], eax
0x18005301a  mov     [rbx], r15d
0x18005301d  cmp     dword ptr [r14+8], 1
0x180053022  jnz     short loc_18005302A
0x180053024  or      eax, 8
0x180053027  mov     [rbx+4], eax
0x18005302a  mov     eax, 1
0x18005302f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180053037  inc     eax
0x180053039  xor     edi, edi
0x18005303b  mov     [rbx+10h], eax
0x18005303e  mov     rax, [rsp+78h+arg_40]
0x180053046  test    rax, rax
0x180053049  jz      short loc_180053050
0x18005304b  cmp     [rax], di
0x18005304e  jnz     short loc_180053053
0x180053050  mov     rax, rdi
0x180053053  mov     [rbx+18h], rax
0x180053057  call    cs:__imp_GetCurrentThreadId
0x18005305d  mov     [rbx+38h], r13
0x180053061  xorps   xmm0, xmm0
0x180053064  mov     [rbx+20h], eax
0x180053067  mov     eax, [rsp+78h+arg_8]
0x18005306e  mov     [rbx+40h], eax
0x180053071  mov     rax, [rsp+78h+arg_20]
0x180053079  mov     [rbx+28h], rax
0x18005307d  mov     rax, [rsp+78h+arg_28]
0x180053085  mov     [rbx+88h], rax
0x18005308c  mov     rax, [rsp+78h+arg_0]
0x180053094  mov     [rbx+90h], rax
0x18005309b  xor     eax, eax
0x18005309d  mov     [rbx+44h], ebp
0x1800530a0  mov     [rbx+30h], r12
0x1800530a4  mov     [rbx+48h], rdi
0x1800530a8  movups  xmmword ptr [rbx+68h], xmm0
0x1800530ac  mov     [rbx+78h], rax
0x1800530b0  movups  xmmword ptr [rbx+50h], xmm0
0x1800530b4  mov     [rbx+60h], rax
0x1800530b8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800530bf  test    rax, rax
0x1800530c2  jz      short loc_1800530CB
0x1800530c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530c9  jmp     short loc_1800530CE
0x1800530cb  mov     rax, rdi
0x1800530ce  mov     [rbx+80h], rax
0x1800530d5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800530dc  test    rax, rax
0x1800530df  jz      short loc_1800530E9
0x1800530e1  mov     rcx, rbx
0x1800530e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800530f0  test    rax, rax
0x1800530f3  jz      short loc_18005310B
0x1800530f5  mov     rdx, [rsp+78h+arg_60]
0x1800530fd  mov     r8d, 400h
0x180053103  mov     rcx, rbx
0x180053106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005310b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180053112  test    rax, rax
0x180053115  jz      short loc_18005311F
0x180053117  mov     rcx, rbx
0x18005311a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005311f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180053126  test    rax, rax
0x180053129  jz      short loc_180053139
0x18005312b  test    byte ptr [rbx+4], 2
0x18005312f  jnz     short loc_180053139
0x180053131  mov     rcx, rbx
0x180053134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053139  cmp     [rbx+8], edi
0x18005313c  jl      short loc_180053158
0x18005313e  cmp     r15d, 3
0x180053142  jnz     loc_180053226
0x180053148  mov     ecx, 8000FFFFh; this
0x18005314d  mov     [rbx+8], ecx
0x180053150  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180053155  mov     [rbx+0Ch], eax
0x180053158  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005315f  jnz     short loc_180053180
0x180053161  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180053168  test    rax, rax
0x18005316b  jz      short loc_180053176
0x18005316d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053172  test    al, al
0x180053174  jmp     short loc_18005317E
0x180053176  call    cs:__imp_IsDebuggerPresent
0x18005317c  test    eax, eax
0x18005317e  jz      short loc_180053186
0x180053180  test    byte ptr [rbx+4], 2
0x180053184  jz      short loc_1800531AA
0x180053186  mov     rax, cs:g_pfnResultLoggingCallback
0x18005318d  test    rax, rax
0x180053190  jz      short loc_1800531EE
0x180053192  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180053199  jnz     short loc_1800531EE
0x18005319b  xor     r8d, r8d
0x18005319e  xor     edx, edx
0x1800531a0  mov     rcx, rbx
0x1800531a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531a8  jmp     short loc_1800531EE
0x1800531aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800531b1  mov     ebp, 800h
0x1800531b6  test    rax, rax
0x1800531b9  jz      short loc_1800531D2
0x1800531bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800531c2  jnz     short loc_1800531D2
0x1800531c4  mov     r8d, ebp
0x1800531c7  mov     rdx, rsi
0x1800531ca  mov     rcx, rbx
0x1800531cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531d2  cmp     [rsi], di
0x1800531d5  jnz     short loc_1800531E5
0x1800531d7  mov     r8, rbx; unsigned __int64
0x1800531da  mov     rdx, rbp; unsigned __int16 *
0x1800531dd  mov     rcx, rsi; pszDest
0x1800531e0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800531e5  mov     rcx, rsi; lpOutputString
0x1800531e8  call    cs:__imp_OutputDebugStringW
0x1800531ee  test    byte ptr [rbx+4], 4
0x1800531f2  jnz     short loc_1800531FD
0x1800531f4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800531fb  jz      short loc_18005320E
0x1800531fd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180053204  test    rax, rax
0x180053207  jz      short loc_18005320E
0x180053209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005320e  mov     rbx, [rsp+78h+arg_10]
0x180053216  add     rsp, 40h
0x18005321a  pop     r15
0x18005321c  pop     r14
0x18005321e  pop     r13
0x180053220  pop     r12
0x180053222  pop     rdi
0x180053223  pop     rsi
0x180053224  pop     rbp
0x180053225  retn
0x180053226  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
