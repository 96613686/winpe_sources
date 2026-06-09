# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140014ed0`
- end: `0x1400151c8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140012b64`

## callees

- `0x1400125a0`
- `0x140014574`
- `0x140014d0c`
- `0x140014ed0`
- `0x1400158b8`
- `0x1400158e0`
- `0x140015a08`
- `0x140015a24`
- `0x1400176cc`
- `0x140019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140015112`
- `KERNEL32!IsDebuggerPresent` at `0x140015112`
- `KERNEL32!OutputDebugStringW` at `0x140015184`
- `KERNEL32!OutputDebugStringW` at `0x140015184`
- `KERNEL32!GetCurrentThreadId` at `0x140014ff3`
- `KERNEL32!GetCurrentThreadId` at `0x140014ff3`

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
  *(_WORD *)lpOutputString = 0;
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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x140014ed0  mov     [rsp+arg_10], rbx
0x140014ed5  mov     [rsp+arg_8], edx
0x140014ed9  mov     [rsp+arg_0], rcx
0x140014ede  push    rbp
0x140014edf  push    rsi
0x140014ee0  push    rdi
0x140014ee1  push    r12
0x140014ee3  push    r13
0x140014ee5  push    r14
0x140014ee7  push    r15
0x140014ee9  sub     rsp, 40h
0x140014eed  mov     r14, [rsp+78h+arg_38]
0x140014ef5  xor     eax, eax
0x140014ef7  mov     rbx, [rsp+78h+arg_78]
0x140014eff  xor     ebp, ebp
0x140014f01  mov     r15d, [rsp+78h+arg_30]
0x140014f09  mov     r10, rcx
0x140014f0c  mov     rsi, [rsp+78h+lpOutputString]
0x140014f14  mov     r12, r9
0x140014f17  mov     r13, r8
0x140014f1a  mov     ecx, r15d
0x140014f1d  mov     [rsi], ax
0x140014f20  mov     rax, [rsp+78h+arg_60]
0x140014f28  mov     byte ptr [rax], 0
0x140014f2b  mov     edi, [r14]
0x140014f2e  mov     [rbx+8], edi
0x140014f31  mov     eax, [r14+4]
0x140014f35  mov     [rbx+0Ch], eax
0x140014f38  test    r15d, r15d
0x140014f3b  jz      short loc_140014FA3
0x140014f3d  sub     ecx, 1
0x140014f40  jz      short loc_140014F9A
0x140014f42  sub     ecx, 1
0x140014f45  jz      short loc_140014F55
0x140014f47  cmp     ecx, 1
0x140014f4a  jnz     short loc_140014FAC
0x140014f4c  mov     ecx, edi; this
0x140014f4e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140014f53  jmp     short loc_140014FAA
0x140014f55  test    edi, edi
0x140014f57  js      short loc_140014F91
0x140014f59  mov     rax, [rsp+78h+arg_28]
0x140014f61  mov     edi, 8007029Ch
0x140014f66  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140014f6a  mov     rcx, r10; int
0x140014f6d  mov     [rsp+78h+var_50], rax; __int64
0x140014f72  mov     rax, [rsp+78h+arg_20]
0x140014f7a  mov     [rsp+78h+var_58], rax; __int64
0x140014f7f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140014f84  mov     ecx, edi; this
0x140014f86  mov     [rbx+8], edi
0x140014f89  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140014f8e  mov     [rbx+0Ch], eax
0x140014f91  mov     ecx, edi; this
0x140014f93  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140014f98  jmp     short loc_140014FAA
0x140014f9a  mov     ecx, edi; this
0x140014f9c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140014fa1  jmp     short loc_140014FAA
0x140014fa3  mov     ecx, edi; this
0x140014fa5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140014faa  mov     ebp, eax
0x140014fac  mov     eax, [rsp+78h+arg_70]
0x140014fb3  mov     [rbx+4], eax
0x140014fb6  mov     [rbx], r15d
0x140014fb9  cmp     dword ptr [r14+8], 1
0x140014fbe  jnz     short loc_140014FC6
0x140014fc0  or      eax, 8
0x140014fc3  mov     [rbx+4], eax
0x140014fc6  mov     eax, 1
0x140014fcb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140014fd3  inc     eax
0x140014fd5  xor     edi, edi
0x140014fd7  mov     [rbx+10h], eax
0x140014fda  mov     rax, [rsp+78h+arg_40]
0x140014fe2  test    rax, rax
0x140014fe5  jz      short loc_140014FEC
0x140014fe7  cmp     [rax], di
0x140014fea  jnz     short loc_140014FEF
0x140014fec  mov     rax, rdi
0x140014fef  mov     [rbx+18h], rax
0x140014ff3  call    cs:__imp_GetCurrentThreadId
0x140014ff9  mov     [rbx+38h], r13
0x140014ffd  xorps   xmm0, xmm0
0x140015000  mov     [rbx+20h], eax
0x140015003  mov     eax, [rsp+78h+arg_8]
0x14001500a  mov     [rbx+40h], eax
0x14001500d  mov     rax, [rsp+78h+arg_20]
0x140015015  mov     [rbx+28h], rax
0x140015019  mov     rax, [rsp+78h+arg_28]
0x140015021  mov     [rbx+88h], rax
0x140015028  mov     rax, [rsp+78h+arg_0]
0x140015030  mov     [rbx+90h], rax
0x140015037  xor     eax, eax
0x140015039  mov     [rbx+44h], ebp
0x14001503c  mov     [rbx+30h], r12
0x140015040  mov     [rbx+48h], rdi
0x140015044  movups  xmmword ptr [rbx+68h], xmm0
0x140015048  mov     [rbx+78h], rax
0x14001504c  movups  xmmword ptr [rbx+50h], xmm0
0x140015050  mov     [rbx+60h], rax
0x140015054  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001505b  test    rax, rax
0x14001505e  jz      short loc_140015067
0x140015060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015065  jmp     short loc_14001506A
0x140015067  mov     rax, rdi
0x14001506a  mov     [rbx+80h], rax
0x140015071  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140015078  test    rax, rax
0x14001507b  jz      short loc_140015085
0x14001507d  mov     rcx, rbx
0x140015080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015085  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14001508c  test    rax, rax
0x14001508f  jz      short loc_1400150A7
0x140015091  mov     rdx, [rsp+78h+arg_60]
0x140015099  mov     r8d, 400h
0x14001509f  mov     rcx, rbx
0x1400150a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400150ae  test    rax, rax
0x1400150b1  jz      short loc_1400150BB
0x1400150b3  mov     rcx, rbx
0x1400150b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400150c2  test    rax, rax
0x1400150c5  jz      short loc_1400150D5
0x1400150c7  test    byte ptr [rbx+4], 2
0x1400150cb  jnz     short loc_1400150D5
0x1400150cd  mov     rcx, rbx
0x1400150d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150d5  cmp     [rbx+8], edi
0x1400150d8  jl      short loc_1400150F4
0x1400150da  cmp     r15d, 3
0x1400150de  jnz     loc_1400151C2
0x1400150e4  mov     ecx, 8000FFFFh; this
0x1400150e9  mov     [rbx+8], ecx
0x1400150ec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400150f1  mov     [rbx+0Ch], eax
0x1400150f4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400150fb  jnz     short loc_14001511C
0x1400150fd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140015104  test    rax, rax
0x140015107  jz      short loc_140015112
0x140015109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001510e  test    al, al
0x140015110  jmp     short loc_14001511A
0x140015112  call    cs:__imp_IsDebuggerPresent
0x140015118  test    eax, eax
0x14001511a  jz      short loc_140015122
0x14001511c  test    byte ptr [rbx+4], 2
0x140015120  jz      short loc_140015146
0x140015122  mov     rax, cs:g_pfnResultLoggingCallback
0x140015129  test    rax, rax
0x14001512c  jz      short loc_14001518A
0x14001512e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140015135  jnz     short loc_14001518A
0x140015137  xor     r8d, r8d
0x14001513a  xor     edx, edx
0x14001513c  mov     rcx, rbx
0x14001513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015144  jmp     short loc_14001518A
0x140015146  mov     rax, cs:g_pfnResultLoggingCallback
0x14001514d  mov     ebp, 800h
0x140015152  test    rax, rax
0x140015155  jz      short loc_14001516E
0x140015157  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001515e  jnz     short loc_14001516E
0x140015160  mov     r8d, ebp
0x140015163  mov     rdx, rsi
0x140015166  mov     rcx, rbx
0x140015169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001516e  cmp     [rsi], di
0x140015171  jnz     short loc_140015181
0x140015173  mov     r8, rbx; unsigned __int64
0x140015176  mov     rdx, rbp; unsigned __int16 *
0x140015179  mov     rcx, rsi; this
0x14001517c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140015181  mov     rcx, rsi; lpOutputString
0x140015184  call    cs:__imp_OutputDebugStringW
0x14001518a  test    byte ptr [rbx+4], 4
0x14001518e  jnz     short loc_140015199
0x140015190  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140015197  jz      short loc_1400151AA
0x140015199  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400151a0  test    rax, rax
0x1400151a3  jz      short loc_1400151AA
0x1400151a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151aa  mov     rbx, [rsp+78h+arg_10]
0x1400151b2  add     rsp, 40h
0x1400151b6  pop     r15
0x1400151b8  pop     r14
0x1400151ba  pop     r13
0x1400151bc  pop     r12
0x1400151be  pop     rdi
0x1400151bf  pop     rsi
0x1400151c0  pop     rbp
0x1400151c1  retn
0x1400151c2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
