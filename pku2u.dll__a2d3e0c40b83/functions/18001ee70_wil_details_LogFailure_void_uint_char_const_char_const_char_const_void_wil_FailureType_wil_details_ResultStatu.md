# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001ee70`
- end: `0x18001f165`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001ed80`
- `0x180024e84`
- `0x180024f34`

## callees

- `0x18001ee70`
- `0x18001f170`
- `0x18001f184`
- `0x180024dd8`
- `0x1800258c4`
- `0x180026324`
- `0x180026340`
- `0x18002635c`
- `0x180026e40`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef93`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f126`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f126`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f0b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f0b4`

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
0x18001ee70  mov     [rsp+arg_10], rbx
0x18001ee75  mov     [rsp+arg_8], edx
0x18001ee79  mov     [rsp+arg_0], rcx
0x18001ee7e  push    rbp
0x18001ee7f  push    rsi
0x18001ee80  push    rdi
0x18001ee81  push    r12
0x18001ee83  push    r13
0x18001ee85  push    r14
0x18001ee87  push    r15
0x18001ee89  sub     rsp, 40h
0x18001ee8d  mov     r12, r9
0x18001ee90  mov     r13, r8
0x18001ee93  mov     r10, rcx
0x18001ee96  xor     eax, eax
0x18001ee98  mov     rsi, [rsp+78h+lpOutputString]
0x18001eea0  mov     [rsi], ax
0x18001eea3  mov     rax, [rsp+78h+arg_60]
0x18001eeab  mov     byte ptr [rax], 0
0x18001eeae  mov     r14, [rsp+78h+arg_38]
0x18001eeb6  mov     edi, [r14]
0x18001eeb9  mov     rbx, [rsp+78h+arg_78]
0x18001eec1  mov     [rbx+8], edi
0x18001eec4  mov     eax, [r14+4]
0x18001eec8  mov     [rbx+0Ch], eax
0x18001eecb  xor     ebp, ebp
0x18001eecd  mov     r15d, [rsp+78h+arg_30]
0x18001eed5  mov     ecx, r15d
0x18001eed8  test    r15d, r15d
0x18001eedb  jz      short loc_18001EF43
0x18001eedd  sub     ecx, 1
0x18001eee0  jz      short loc_18001EF3A
0x18001eee2  sub     ecx, 1
0x18001eee5  jz      short loc_18001EEF5
0x18001eee7  cmp     ecx, 1
0x18001eeea  jnz     short loc_18001EF4C
0x18001eeec  mov     ecx, edi; this
0x18001eeee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001eef3  jmp     short loc_18001EF4A
0x18001eef5  test    edi, edi
0x18001eef7  js      short loc_18001EF31
0x18001eef9  mov     edi, 8007029Ch
0x18001eefe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001ef02  mov     rax, [rsp+78h+arg_28]
0x18001ef0a  mov     [rsp+78h+var_50], rax; __int64
0x18001ef0f  mov     rax, [rsp+78h+arg_20]
0x18001ef17  mov     [rsp+78h+var_58], rax; __int64
0x18001ef1c  mov     rcx, r10; int
0x18001ef1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001ef24  mov     [rbx+8], edi
0x18001ef27  mov     ecx, edi; this
0x18001ef29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ef2e  mov     [rbx+0Ch], eax
0x18001ef31  mov     ecx, edi; this
0x18001ef33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001ef38  jmp     short loc_18001EF4A
0x18001ef3a  mov     ecx, edi; this
0x18001ef3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001ef41  jmp     short loc_18001EF4A
0x18001ef43  mov     ecx, edi; this
0x18001ef45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001ef4a  mov     ebp, eax
0x18001ef4c  mov     [rbx], r15d
0x18001ef4f  mov     eax, [rsp+78h+arg_70]
0x18001ef56  mov     [rbx+4], eax
0x18001ef59  cmp     dword ptr [r14+8], 1
0x18001ef5e  jnz     short loc_18001EF66
0x18001ef60  or      eax, 8
0x18001ef63  mov     [rbx+4], eax
0x18001ef66  mov     eax, 1
0x18001ef6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001ef73  inc     eax
0x18001ef75  mov     [rbx+10h], eax
0x18001ef78  mov     rax, [rsp+78h+arg_40]
0x18001ef80  xor     edi, edi
0x18001ef82  test    rax, rax
0x18001ef85  jz      short loc_18001EF8C
0x18001ef87  cmp     [rax], di
0x18001ef8a  jnz     short loc_18001EF8F
0x18001ef8c  mov     rax, rdi
0x18001ef8f  mov     [rbx+18h], rax
0x18001ef93  call    cs:__imp_GetCurrentThreadId
0x18001ef99  mov     [rbx+20h], eax
0x18001ef9c  mov     [rbx+38h], r13
0x18001efa0  mov     eax, [rsp+78h+arg_8]
0x18001efa7  mov     [rbx+40h], eax
0x18001efaa  mov     [rbx+44h], ebp
0x18001efad  mov     rax, [rsp+78h+arg_20]
0x18001efb5  mov     [rbx+28h], rax
0x18001efb9  mov     [rbx+30h], r12
0x18001efbd  mov     rax, [rsp+78h+arg_28]
0x18001efc5  mov     [rbx+88h], rax
0x18001efcc  mov     rax, [rsp+78h+arg_0]
0x18001efd4  mov     [rbx+90h], rax
0x18001efdb  mov     [rbx+48h], rdi
0x18001efdf  xorps   xmm0, xmm0
0x18001efe2  xor     eax, eax
0x18001efe4  movups  xmmword ptr [rbx+68h], xmm0
0x18001efe8  mov     [rbx+78h], rax
0x18001efec  movups  xmmword ptr [rbx+50h], xmm0
0x18001eff0  mov     [rbx+60h], rax
0x18001eff4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001effb  test    rax, rax
0x18001effe  jz      short loc_18001F007
0x18001f000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f005  jmp     short loc_18001F00A
0x18001f007  mov     rax, rdi
0x18001f00a  mov     [rbx+80h], rax
0x18001f011  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001f018  test    rax, rax
0x18001f01b  jz      short loc_18001F025
0x18001f01d  mov     rcx, rbx
0x18001f020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f025  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001f02c  test    rax, rax
0x18001f02f  jz      short loc_18001F047
0x18001f031  mov     r8d, 400h
0x18001f037  mov     rdx, [rsp+78h+arg_60]
0x18001f03f  mov     rcx, rbx
0x18001f042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f047  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f04e  test    rax, rax
0x18001f051  jz      short loc_18001F05B
0x18001f053  mov     rcx, rbx
0x18001f056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f05b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f062  test    rax, rax
0x18001f065  jz      short loc_18001F075
0x18001f067  test    byte ptr [rbx+4], 2
0x18001f06b  jnz     short loc_18001F075
0x18001f06d  mov     rcx, rbx
0x18001f070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f075  cmp     [rbx+8], edi
0x18001f078  jl      short loc_18001F096
0x18001f07a  cmp     r15d, 3
0x18001f07e  jz      short loc_18001F086
0x18001f080  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001f086  mov     ecx, 8000FFFFh; this
0x18001f08b  mov     [rbx+8], ecx
0x18001f08e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f093  mov     [rbx+0Ch], eax
0x18001f096  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001f09d  jnz     short loc_18001F0BE
0x18001f09f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001f0a6  test    rax, rax
0x18001f0a9  jz      short loc_18001F0B4
0x18001f0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b0  test    al, al
0x18001f0b2  jmp     short loc_18001F0BC
0x18001f0b4  call    cs:__imp_IsDebuggerPresent
0x18001f0ba  test    eax, eax
0x18001f0bc  jz      short loc_18001F0C4
0x18001f0be  test    byte ptr [rbx+4], 2
0x18001f0c2  jz      short loc_18001F0E8
0x18001f0c4  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f0cb  test    rax, rax
0x18001f0ce  jz      short loc_18001F12C
0x18001f0d0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f0d7  jnz     short loc_18001F12C
0x18001f0d9  xor     r8d, r8d
0x18001f0dc  xor     edx, edx
0x18001f0de  mov     rcx, rbx
0x18001f0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0e6  jmp     short loc_18001F12C
0x18001f0e8  mov     ebp, 800h
0x18001f0ed  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f0f4  test    rax, rax
0x18001f0f7  jz      short loc_18001F110
0x18001f0f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f100  jnz     short loc_18001F110
0x18001f102  mov     r8d, ebp
0x18001f105  mov     rdx, rsi
0x18001f108  mov     rcx, rbx
0x18001f10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f110  cmp     [rsi], di
0x18001f113  jnz     short loc_18001F123
0x18001f115  mov     r8, rbx; unsigned __int64
0x18001f118  mov     rdx, rbp; unsigned __int16 *
0x18001f11b  mov     rcx, rsi; this
0x18001f11e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f123  mov     rcx, rsi; lpOutputString
0x18001f126  call    cs:__imp_OutputDebugStringW
0x18001f12c  test    byte ptr [rbx+4], 4
0x18001f130  jnz     short loc_18001F13B
0x18001f132  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001f139  jz      short loc_18001F14D
0x18001f13b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001f142  test    rax, rax
0x18001f145  jz      short loc_18001F14D
0x18001f147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f14c  nop
0x18001f14d  mov     rbx, [rsp+78h+arg_10]
0x18001f155  add     rsp, 40h
0x18001f159  pop     r15
0x18001f15b  pop     r14
0x18001f15d  pop     r13
0x18001f15f  pop     r12
0x18001f161  pop     rdi
0x18001f162  pop     rsi
0x18001f163  pop     rbp
0x18001f164  retn
```
