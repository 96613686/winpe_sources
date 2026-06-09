# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005fe8`
- end: `0x1800062f4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004500`

## callees

- `0x180003ee4`
- `0x180005534`
- `0x180005e24`
- `0x180005fe8`
- `0x1800065ec`
- `0x180006610`
- `0x180006624`
- `0x180006644`
- `0x180007824`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000610b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000610b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006230`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006230`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800062a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800062a8`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x180005fe8  mov     [rsp+arg_10], rbx
0x180005fed  mov     [rsp+arg_8], edx
0x180005ff1  mov     [rsp+arg_0], rcx
0x180005ff6  push    rbp
0x180005ff7  push    rsi
0x180005ff8  push    rdi
0x180005ff9  push    r12
0x180005ffb  push    r13
0x180005ffd  push    r14
0x180005fff  push    r15
0x180006001  sub     rsp, 40h
0x180006005  mov     r12, r9
0x180006008  mov     r13, r8
0x18000600b  mov     r10, rcx
0x18000600e  xor     eax, eax
0x180006010  mov     rsi, [rsp+78h+lpOutputString]
0x180006018  mov     [rsi], ax
0x18000601b  mov     rax, [rsp+78h+arg_60]
0x180006023  mov     byte ptr [rax], 0
0x180006026  mov     r14, [rsp+78h+arg_38]
0x18000602e  mov     edi, [r14]
0x180006031  mov     rbx, [rsp+78h+arg_78]
0x180006039  mov     [rbx+8], edi
0x18000603c  mov     eax, [r14+4]
0x180006040  mov     [rbx+0Ch], eax
0x180006043  xor     ebp, ebp
0x180006045  mov     r15d, [rsp+78h+arg_30]
0x18000604d  mov     ecx, r15d
0x180006050  test    r15d, r15d
0x180006053  jz      short loc_1800060BB
0x180006055  sub     ecx, 1
0x180006058  jz      short loc_1800060B2
0x18000605a  sub     ecx, 1
0x18000605d  jz      short loc_18000606D
0x18000605f  cmp     ecx, 1
0x180006062  jnz     short loc_1800060C4
0x180006064  mov     ecx, edi; this
0x180006066  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000606b  jmp     short loc_1800060C2
0x18000606d  test    edi, edi
0x18000606f  js      short loc_1800060A9
0x180006071  mov     edi, 8007029Ch
0x180006076  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000607a  mov     rax, [rsp+78h+arg_28]
0x180006082  mov     [rsp+78h+var_50], rax; __int64
0x180006087  mov     rax, [rsp+78h+arg_20]
0x18000608f  mov     [rsp+78h+var_58], rax; __int64
0x180006094  mov     rcx, r10; int
0x180006097  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000609c  mov     [rbx+8], edi
0x18000609f  mov     ecx, edi; this
0x1800060a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800060a6  mov     [rbx+0Ch], eax
0x1800060a9  mov     ecx, edi; this
0x1800060ab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800060b0  jmp     short loc_1800060C2
0x1800060b2  mov     ecx, edi; this
0x1800060b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800060b9  jmp     short loc_1800060C2
0x1800060bb  mov     ecx, edi; this
0x1800060bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800060c2  mov     ebp, eax
0x1800060c4  mov     [rbx], r15d
0x1800060c7  mov     eax, [rsp+78h+arg_70]
0x1800060ce  mov     [rbx+4], eax
0x1800060d1  cmp     dword ptr [r14+8], 1
0x1800060d6  jnz     short loc_1800060DE
0x1800060d8  or      eax, 8
0x1800060db  mov     [rbx+4], eax
0x1800060de  mov     eax, 1
0x1800060e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800060eb  inc     eax
0x1800060ed  mov     [rbx+10h], eax
0x1800060f0  mov     rax, [rsp+78h+arg_40]
0x1800060f8  xor     edi, edi
0x1800060fa  test    rax, rax
0x1800060fd  jz      short loc_180006104
0x1800060ff  cmp     [rax], di
0x180006102  jnz     short loc_180006107
0x180006104  mov     rax, rdi
0x180006107  mov     [rbx+18h], rax
0x18000610b  call    cs:__imp_GetCurrentThreadId
0x180006112  nop     dword ptr [rax+rax+00h]
0x180006117  mov     [rbx+20h], eax
0x18000611a  mov     [rbx+38h], r13
0x18000611e  mov     eax, [rsp+78h+arg_8]
0x180006125  mov     [rbx+40h], eax
0x180006128  mov     [rbx+44h], ebp
0x18000612b  mov     rax, [rsp+78h+arg_20]
0x180006133  mov     [rbx+28h], rax
0x180006137  mov     [rbx+30h], r12
0x18000613b  mov     rax, [rsp+78h+arg_28]
0x180006143  mov     [rbx+88h], rax
0x18000614a  mov     rax, [rsp+78h+arg_0]
0x180006152  mov     [rbx+90h], rax
0x180006159  mov     [rbx+48h], rdi
0x18000615d  xorps   xmm0, xmm0
0x180006160  xor     eax, eax
0x180006162  movups  xmmword ptr [rbx+68h], xmm0
0x180006166  mov     [rbx+78h], rax
0x18000616a  movups  xmmword ptr [rbx+50h], xmm0
0x18000616e  mov     [rbx+60h], rax
0x180006172  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006179  test    rax, rax
0x18000617c  jz      short loc_180006185
0x18000617e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006183  jmp     short loc_180006188
0x180006185  mov     rax, rdi
0x180006188  mov     [rbx+80h], rax
0x18000618f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006196  test    rax, rax
0x180006199  jz      short loc_1800061A3
0x18000619b  mov     rcx, rbx
0x18000619e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800061aa  test    rax, rax
0x1800061ad  jz      short loc_1800061C5
0x1800061af  mov     r8d, 400h
0x1800061b5  mov     rdx, [rsp+78h+arg_60]
0x1800061bd  mov     rcx, rbx
0x1800061c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800061cc  test    rax, rax
0x1800061cf  jz      short loc_1800061D9
0x1800061d1  mov     rcx, rbx
0x1800061d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800061e0  test    rax, rax
0x1800061e3  jz      short loc_1800061F3
0x1800061e5  test    byte ptr [rbx+4], 2
0x1800061e9  jnz     short loc_1800061F3
0x1800061eb  mov     rcx, rbx
0x1800061ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f3  cmp     [rbx+8], edi
0x1800061f6  jl      short loc_180006212
0x1800061f8  cmp     r15d, 3
0x1800061fc  jnz     loc_1800062EE
0x180006202  mov     ecx, 8000FFFFh; this
0x180006207  mov     [rbx+8], ecx
0x18000620a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000620f  mov     [rbx+0Ch], eax
0x180006212  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006219  jnz     short loc_180006240
0x18000621b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006222  test    rax, rax
0x180006225  jz      short loc_180006230
0x180006227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622c  test    al, al
0x18000622e  jmp     short loc_18000623E
0x180006230  call    cs:__imp_IsDebuggerPresent
0x180006237  nop     dword ptr [rax+rax+00h]
0x18000623c  test    eax, eax
0x18000623e  jz      short loc_180006246
0x180006240  test    byte ptr [rbx+4], 2
0x180006244  jz      short loc_18000626A
0x180006246  mov     rax, cs:g_pfnResultLoggingCallback
0x18000624d  test    rax, rax
0x180006250  jz      short loc_1800062B4
0x180006252  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006259  jnz     short loc_1800062B4
0x18000625b  xor     r8d, r8d
0x18000625e  xor     edx, edx
0x180006260  mov     rcx, rbx
0x180006263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006268  jmp     short loc_1800062B4
0x18000626a  mov     ebp, 800h
0x18000626f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006276  test    rax, rax
0x180006279  jz      short loc_180006292
0x18000627b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006282  jnz     short loc_180006292
0x180006284  mov     r8d, ebp
0x180006287  mov     rdx, rsi
0x18000628a  mov     rcx, rbx
0x18000628d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006292  cmp     [rsi], di
0x180006295  jnz     short loc_1800062A5
0x180006297  mov     r8, rbx; unsigned __int64
0x18000629a  mov     rdx, rbp; unsigned __int16 *
0x18000629d  mov     rcx, rsi; this
0x1800062a0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800062a5  mov     rcx, rsi; lpOutputString
0x1800062a8  call    cs:__imp_OutputDebugStringW
0x1800062af  nop     dword ptr [rax+rax+00h]
0x1800062b4  test    byte ptr [rbx+4], 4
0x1800062b8  jnz     short loc_1800062C3
0x1800062ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800062c1  jz      short loc_1800062D5
0x1800062c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800062ca  test    rax, rax
0x1800062cd  jz      short loc_1800062D5
0x1800062cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d4  nop
0x1800062d5  mov     rbx, [rsp+78h+arg_10]
0x1800062dd  add     rsp, 40h
0x1800062e1  pop     r15
0x1800062e3  pop     r14
0x1800062e5  pop     r13
0x1800062e7  pop     r12
0x1800062e9  pop     rdi
0x1800062ea  pop     rsi
0x1800062eb  pop     rbp
0x1800062ec  retn
0x1800062ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
