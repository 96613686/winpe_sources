# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002cddc`
- end: `0x18002d0d5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800297d4`
- `0x180029b24`

## callees

- `0x18002971c`
- `0x18002ba78`
- `0x18002c7c4`
- `0x18002cddc`
- `0x18002e05c`
- `0x18002e080`
- `0x18002e094`
- `0x18002e0b0`
- `0x18002f560`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ceff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ceff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002d090`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002d090`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d01e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d01e`

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
0x18002cddc  mov     [rsp+arg_10], rbx
0x18002cde1  mov     [rsp+arg_8], edx
0x18002cde5  mov     [rsp+arg_0], rcx
0x18002cdea  push    rbp
0x18002cdeb  push    rsi
0x18002cdec  push    rdi
0x18002cded  push    r12
0x18002cdef  push    r13
0x18002cdf1  push    r14
0x18002cdf3  push    r15
0x18002cdf5  sub     rsp, 40h
0x18002cdf9  mov     r12, r9
0x18002cdfc  mov     r13, r8
0x18002cdff  mov     r10, rcx
0x18002ce02  xor     eax, eax
0x18002ce04  mov     rsi, [rsp+78h+lpOutputString]
0x18002ce0c  mov     [rsi], ax
0x18002ce0f  mov     rax, [rsp+78h+arg_60]
0x18002ce17  mov     byte ptr [rax], 0
0x18002ce1a  mov     r14, [rsp+78h+arg_38]
0x18002ce22  mov     edi, [r14]
0x18002ce25  mov     rbx, [rsp+78h+arg_78]
0x18002ce2d  mov     [rbx+8], edi
0x18002ce30  mov     eax, [r14+4]
0x18002ce34  mov     [rbx+0Ch], eax
0x18002ce37  xor     ebp, ebp
0x18002ce39  mov     r15d, [rsp+78h+arg_30]
0x18002ce41  mov     ecx, r15d
0x18002ce44  test    r15d, r15d
0x18002ce47  jz      short loc_18002CEAF
0x18002ce49  sub     ecx, 1
0x18002ce4c  jz      short loc_18002CEA6
0x18002ce4e  sub     ecx, 1
0x18002ce51  jz      short loc_18002CE61
0x18002ce53  cmp     ecx, 1
0x18002ce56  jnz     short loc_18002CEB8
0x18002ce58  mov     ecx, edi; this
0x18002ce5a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002ce5f  jmp     short loc_18002CEB6
0x18002ce61  test    edi, edi
0x18002ce63  js      short loc_18002CE9D
0x18002ce65  mov     edi, 8007029Ch
0x18002ce6a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002ce6e  mov     rax, [rsp+78h+arg_28]
0x18002ce76  mov     [rsp+78h+var_50], rax; __int64
0x18002ce7b  mov     rax, [rsp+78h+arg_20]
0x18002ce83  mov     [rsp+78h+var_58], rax; __int64
0x18002ce88  mov     rcx, r10; int
0x18002ce8b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002ce90  mov     [rbx+8], edi
0x18002ce93  mov     ecx, edi; this
0x18002ce95  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002ce9a  mov     [rbx+0Ch], eax
0x18002ce9d  mov     ecx, edi; this
0x18002ce9f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002cea4  jmp     short loc_18002CEB6
0x18002cea6  mov     ecx, edi; this
0x18002cea8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002cead  jmp     short loc_18002CEB6
0x18002ceaf  mov     ecx, edi; this
0x18002ceb1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002ceb6  mov     ebp, eax
0x18002ceb8  mov     [rbx], r15d
0x18002cebb  mov     eax, [rsp+78h+arg_70]
0x18002cec2  mov     [rbx+4], eax
0x18002cec5  cmp     dword ptr [r14+8], 1
0x18002ceca  jnz     short loc_18002CED2
0x18002cecc  or      eax, 8
0x18002cecf  mov     [rbx+4], eax
0x18002ced2  mov     eax, 1
0x18002ced7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002cedf  inc     eax
0x18002cee1  mov     [rbx+10h], eax
0x18002cee4  mov     rax, [rsp+78h+arg_40]
0x18002ceec  xor     edi, edi
0x18002ceee  test    rax, rax
0x18002cef1  jz      short loc_18002CEF8
0x18002cef3  cmp     [rax], di
0x18002cef6  jnz     short loc_18002CEFB
0x18002cef8  mov     rax, rdi
0x18002cefb  mov     [rbx+18h], rax
0x18002ceff  call    cs:__imp_GetCurrentThreadId
0x18002cf05  mov     [rbx+20h], eax
0x18002cf08  mov     [rbx+38h], r13
0x18002cf0c  mov     eax, [rsp+78h+arg_8]
0x18002cf13  mov     [rbx+40h], eax
0x18002cf16  mov     [rbx+44h], ebp
0x18002cf19  mov     rax, [rsp+78h+arg_20]
0x18002cf21  mov     [rbx+28h], rax
0x18002cf25  mov     [rbx+30h], r12
0x18002cf29  mov     rax, [rsp+78h+arg_28]
0x18002cf31  mov     [rbx+88h], rax
0x18002cf38  mov     rax, [rsp+78h+arg_0]
0x18002cf40  mov     [rbx+90h], rax
0x18002cf47  mov     [rbx+48h], rdi
0x18002cf4b  xorps   xmm0, xmm0
0x18002cf4e  xor     eax, eax
0x18002cf50  movups  xmmword ptr [rbx+68h], xmm0
0x18002cf54  mov     [rbx+78h], rax
0x18002cf58  movups  xmmword ptr [rbx+50h], xmm0
0x18002cf5c  mov     [rbx+60h], rax
0x18002cf60  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002cf67  test    rax, rax
0x18002cf6a  jz      short loc_18002CF73
0x18002cf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf71  jmp     short loc_18002CF76
0x18002cf73  mov     rax, rdi
0x18002cf76  mov     [rbx+80h], rax
0x18002cf7d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002cf84  test    rax, rax
0x18002cf87  jz      short loc_18002CF91
0x18002cf89  mov     rcx, rbx
0x18002cf8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf91  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002cf98  test    rax, rax
0x18002cf9b  jz      short loc_18002CFB3
0x18002cf9d  mov     r8d, 400h
0x18002cfa3  mov     rdx, [rsp+78h+arg_60]
0x18002cfab  mov     rcx, rbx
0x18002cfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfb3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002cfba  test    rax, rax
0x18002cfbd  jz      short loc_18002CFC7
0x18002cfbf  mov     rcx, rbx
0x18002cfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfc7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002cfce  test    rax, rax
0x18002cfd1  jz      short loc_18002CFE1
0x18002cfd3  test    byte ptr [rbx+4], 2
0x18002cfd7  jnz     short loc_18002CFE1
0x18002cfd9  mov     rcx, rbx
0x18002cfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfe1  cmp     [rbx+8], edi
0x18002cfe4  jl      short loc_18002D000
0x18002cfe6  cmp     r15d, 3
0x18002cfea  jnz     loc_18002D0CF
0x18002cff0  mov     ecx, 8000FFFFh; this
0x18002cff5  mov     [rbx+8], ecx
0x18002cff8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002cffd  mov     [rbx+0Ch], eax
0x18002d000  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002d007  jnz     short loc_18002D028
0x18002d009  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002d010  test    rax, rax
0x18002d013  jz      short loc_18002D01E
0x18002d015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d01a  test    al, al
0x18002d01c  jmp     short loc_18002D026
0x18002d01e  call    cs:__imp_IsDebuggerPresent
0x18002d024  test    eax, eax
0x18002d026  jz      short loc_18002D02E
0x18002d028  test    byte ptr [rbx+4], 2
0x18002d02c  jz      short loc_18002D052
0x18002d02e  mov     rax, cs:g_pfnResultLoggingCallback
0x18002d035  test    rax, rax
0x18002d038  jz      short loc_18002D096
0x18002d03a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002d041  jnz     short loc_18002D096
0x18002d043  xor     r8d, r8d
0x18002d046  xor     edx, edx
0x18002d048  mov     rcx, rbx
0x18002d04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d050  jmp     short loc_18002D096
0x18002d052  mov     ebp, 800h
0x18002d057  mov     rax, cs:g_pfnResultLoggingCallback
0x18002d05e  test    rax, rax
0x18002d061  jz      short loc_18002D07A
0x18002d063  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002d06a  jnz     short loc_18002D07A
0x18002d06c  mov     r8d, ebp
0x18002d06f  mov     rdx, rsi
0x18002d072  mov     rcx, rbx
0x18002d075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d07a  cmp     [rsi], di
0x18002d07d  jnz     short loc_18002D08D
0x18002d07f  mov     r8, rbx; unsigned __int64
0x18002d082  mov     rdx, rbp; unsigned __int16 *
0x18002d085  mov     rcx, rsi; this
0x18002d088  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002d08d  mov     rcx, rsi; lpOutputString
0x18002d090  call    cs:__imp_OutputDebugStringW
0x18002d096  test    byte ptr [rbx+4], 4
0x18002d09a  jnz     short loc_18002D0A5
0x18002d09c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002d0a3  jz      short loc_18002D0B7
0x18002d0a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002d0ac  test    rax, rax
0x18002d0af  jz      short loc_18002D0B7
0x18002d0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b6  nop
0x18002d0b7  mov     rbx, [rsp+78h+arg_10]
0x18002d0bf  add     rsp, 40h
0x18002d0c3  pop     r15
0x18002d0c5  pop     r14
0x18002d0c7  pop     r13
0x18002d0c9  pop     r12
0x18002d0cb  pop     rdi
0x18002d0cc  pop     rsi
0x18002d0cd  pop     rbp
0x18002d0ce  retn
0x18002d0cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
