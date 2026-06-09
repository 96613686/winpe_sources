# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400060f4`
- end: `0x140006400`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140004694`
- `0x140004a14`

## callees

- `0x1400045cc`
- `0x1400056e4`
- `0x140005f30`
- `0x1400060f4`
- `0x140006814`
- `0x140006840`
- `0x140006854`
- `0x140006874`
- `0x140007750`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006217`
- `KERNEL32!GetCurrentThreadId` at `0x140006217`
- `KERNEL32!OutputDebugStringW` at `0x1400063b4`
- `KERNEL32!OutputDebugStringW` at `0x1400063b4`
- `KERNEL32!IsDebuggerPresent` at `0x14000633c`
- `KERNEL32!IsDebuggerPresent` at `0x14000633c`

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
0x1400060f4  mov     [rsp+arg_10], rbx
0x1400060f9  mov     [rsp+arg_8], edx
0x1400060fd  mov     [rsp+arg_0], rcx
0x140006102  push    rbp
0x140006103  push    rsi
0x140006104  push    rdi
0x140006105  push    r12
0x140006107  push    r13
0x140006109  push    r14
0x14000610b  push    r15
0x14000610d  sub     rsp, 40h
0x140006111  mov     r12, r9
0x140006114  mov     r13, r8
0x140006117  mov     r10, rcx
0x14000611a  xor     eax, eax
0x14000611c  mov     rsi, [rsp+78h+lpOutputString]
0x140006124  mov     [rsi], ax
0x140006127  mov     rax, [rsp+78h+arg_60]
0x14000612f  mov     byte ptr [rax], 0
0x140006132  mov     r14, [rsp+78h+arg_38]
0x14000613a  mov     edi, [r14]
0x14000613d  mov     rbx, [rsp+78h+arg_78]
0x140006145  mov     [rbx+8], edi
0x140006148  mov     eax, [r14+4]
0x14000614c  mov     [rbx+0Ch], eax
0x14000614f  xor     ebp, ebp
0x140006151  mov     r15d, [rsp+78h+arg_30]
0x140006159  mov     ecx, r15d
0x14000615c  test    r15d, r15d
0x14000615f  jz      short loc_1400061C7
0x140006161  sub     ecx, 1
0x140006164  jz      short loc_1400061BE
0x140006166  sub     ecx, 1
0x140006169  jz      short loc_140006179
0x14000616b  cmp     ecx, 1
0x14000616e  jnz     short loc_1400061D0
0x140006170  mov     ecx, edi; this
0x140006172  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006177  jmp     short loc_1400061CE
0x140006179  test    edi, edi
0x14000617b  js      short loc_1400061B5
0x14000617d  mov     edi, 8007029Ch
0x140006182  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006186  mov     rax, [rsp+78h+arg_28]
0x14000618e  mov     [rsp+78h+var_50], rax; __int64
0x140006193  mov     rax, [rsp+78h+arg_20]
0x14000619b  mov     [rsp+78h+var_58], rax; __int64
0x1400061a0  mov     rcx, r10; int
0x1400061a3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400061a8  mov     [rbx+8], edi
0x1400061ab  mov     ecx, edi; this
0x1400061ad  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400061b2  mov     [rbx+0Ch], eax
0x1400061b5  mov     ecx, edi; this
0x1400061b7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400061bc  jmp     short loc_1400061CE
0x1400061be  mov     ecx, edi; this
0x1400061c0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400061c5  jmp     short loc_1400061CE
0x1400061c7  mov     ecx, edi; this
0x1400061c9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400061ce  mov     ebp, eax
0x1400061d0  mov     [rbx], r15d
0x1400061d3  mov     eax, [rsp+78h+arg_70]
0x1400061da  mov     [rbx+4], eax
0x1400061dd  cmp     dword ptr [r14+8], 1
0x1400061e2  jnz     short loc_1400061EA
0x1400061e4  or      eax, 8
0x1400061e7  mov     [rbx+4], eax
0x1400061ea  mov     eax, 1
0x1400061ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400061f7  inc     eax
0x1400061f9  mov     [rbx+10h], eax
0x1400061fc  mov     rax, [rsp+78h+arg_40]
0x140006204  xor     edi, edi
0x140006206  test    rax, rax
0x140006209  jz      short loc_140006210
0x14000620b  cmp     [rax], di
0x14000620e  jnz     short loc_140006213
0x140006210  mov     rax, rdi
0x140006213  mov     [rbx+18h], rax
0x140006217  call    cs:__imp_GetCurrentThreadId
0x14000621e  nop     dword ptr [rax+rax+00h]
0x140006223  mov     [rbx+20h], eax
0x140006226  mov     [rbx+38h], r13
0x14000622a  mov     eax, [rsp+78h+arg_8]
0x140006231  mov     [rbx+40h], eax
0x140006234  mov     [rbx+44h], ebp
0x140006237  mov     rax, [rsp+78h+arg_20]
0x14000623f  mov     [rbx+28h], rax
0x140006243  mov     [rbx+30h], r12
0x140006247  mov     rax, [rsp+78h+arg_28]
0x14000624f  mov     [rbx+88h], rax
0x140006256  mov     rax, [rsp+78h+arg_0]
0x14000625e  mov     [rbx+90h], rax
0x140006265  mov     [rbx+48h], rdi
0x140006269  xorps   xmm0, xmm0
0x14000626c  xor     eax, eax
0x14000626e  movups  xmmword ptr [rbx+68h], xmm0
0x140006272  mov     [rbx+78h], rax
0x140006276  movups  xmmword ptr [rbx+50h], xmm0
0x14000627a  mov     [rbx+60h], rax
0x14000627e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006285  test    rax, rax
0x140006288  jz      short loc_140006291
0x14000628a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000628f  jmp     short loc_140006294
0x140006291  mov     rax, rdi
0x140006294  mov     [rbx+80h], rax
0x14000629b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400062a2  test    rax, rax
0x1400062a5  jz      short loc_1400062AF
0x1400062a7  mov     rcx, rbx
0x1400062aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062af  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400062b6  test    rax, rax
0x1400062b9  jz      short loc_1400062D1
0x1400062bb  mov     r8d, 400h
0x1400062c1  mov     rdx, [rsp+78h+arg_60]
0x1400062c9  mov     rcx, rbx
0x1400062cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062d1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400062d8  test    rax, rax
0x1400062db  jz      short loc_1400062E5
0x1400062dd  mov     rcx, rbx
0x1400062e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062e5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400062ec  test    rax, rax
0x1400062ef  jz      short loc_1400062FF
0x1400062f1  test    byte ptr [rbx+4], 2
0x1400062f5  jnz     short loc_1400062FF
0x1400062f7  mov     rcx, rbx
0x1400062fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062ff  cmp     [rbx+8], edi
0x140006302  jl      short loc_14000631E
0x140006304  cmp     r15d, 3
0x140006308  jnz     loc_1400063FA
0x14000630e  mov     ecx, 8000FFFFh; this
0x140006313  mov     [rbx+8], ecx
0x140006316  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000631b  mov     [rbx+0Ch], eax
0x14000631e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006325  jnz     short loc_14000634C
0x140006327  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000632e  test    rax, rax
0x140006331  jz      short loc_14000633C
0x140006333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006338  test    al, al
0x14000633a  jmp     short loc_14000634A
0x14000633c  call    cs:__imp_IsDebuggerPresent
0x140006343  nop     dword ptr [rax+rax+00h]
0x140006348  test    eax, eax
0x14000634a  jz      short loc_140006352
0x14000634c  test    byte ptr [rbx+4], 2
0x140006350  jz      short loc_140006376
0x140006352  mov     rax, cs:g_pfnResultLoggingCallback
0x140006359  test    rax, rax
0x14000635c  jz      short loc_1400063C0
0x14000635e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006365  jnz     short loc_1400063C0
0x140006367  xor     r8d, r8d
0x14000636a  xor     edx, edx
0x14000636c  mov     rcx, rbx
0x14000636f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006374  jmp     short loc_1400063C0
0x140006376  mov     ebp, 800h
0x14000637b  mov     rax, cs:g_pfnResultLoggingCallback
0x140006382  test    rax, rax
0x140006385  jz      short loc_14000639E
0x140006387  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000638e  jnz     short loc_14000639E
0x140006390  mov     r8d, ebp
0x140006393  mov     rdx, rsi
0x140006396  mov     rcx, rbx
0x140006399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000639e  cmp     [rsi], di
0x1400063a1  jnz     short loc_1400063B1
0x1400063a3  mov     r8, rbx; unsigned __int64
0x1400063a6  mov     rdx, rbp; unsigned __int16 *
0x1400063a9  mov     rcx, rsi; this
0x1400063ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400063b1  mov     rcx, rsi; lpOutputString
0x1400063b4  call    cs:__imp_OutputDebugStringW
0x1400063bb  nop     dword ptr [rax+rax+00h]
0x1400063c0  test    byte ptr [rbx+4], 4
0x1400063c4  jnz     short loc_1400063CF
0x1400063c6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400063cd  jz      short loc_1400063E1
0x1400063cf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400063d6  test    rax, rax
0x1400063d9  jz      short loc_1400063E1
0x1400063db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063e0  nop
0x1400063e1  mov     rbx, [rsp+78h+arg_10]
0x1400063e9  add     rsp, 40h
0x1400063ed  pop     r15
0x1400063ef  pop     r14
0x1400063f1  pop     r13
0x1400063f3  pop     r12
0x1400063f5  pop     rdi
0x1400063f6  pop     rsi
0x1400063f7  pop     rbp
0x1400063f8  retn
0x1400063fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
