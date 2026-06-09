# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140018c9c`
- end: `0x140018f91`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, WCHAR *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140016730`
- `0x1400167e0`
- `0x1400168d4`

## callees

- `0x140016684`
- `0x140018204`
- `0x1400189a8`
- `0x140018c9c`
- `0x14001992c`
- `0x140019950`
- `0x140019ad8`
- `0x140019af4`
- `0x14001b50c`
- `0x140020010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140018ee0`
- `KERNEL32!IsDebuggerPresent` at `0x140018ee0`
- `KERNEL32!GetCurrentThreadId` at `0x140018dbf`
- `KERNEL32!GetCurrentThreadId` at `0x140018dbf`
- `KERNEL32!OutputDebugStringW` at `0x140018f52`
- `KERNEL32!OutputDebugStringW` at `0x140018f52`

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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x140018c9c  mov     [rsp+arg_10], rbx
0x140018ca1  mov     [rsp+arg_8], edx
0x140018ca5  mov     [rsp+arg_0], rcx
0x140018caa  push    rbp
0x140018cab  push    rsi
0x140018cac  push    rdi
0x140018cad  push    r12
0x140018caf  push    r13
0x140018cb1  push    r14
0x140018cb3  push    r15
0x140018cb5  sub     rsp, 40h
0x140018cb9  mov     r12, r9
0x140018cbc  mov     r13, r8
0x140018cbf  mov     r10, rcx
0x140018cc2  xor     eax, eax
0x140018cc4  mov     rsi, [rsp+78h+lpOutputString]
0x140018ccc  mov     [rsi], ax
0x140018ccf  mov     rax, [rsp+78h+arg_60]
0x140018cd7  mov     byte ptr [rax], 0
0x140018cda  mov     r14, [rsp+78h+arg_38]
0x140018ce2  mov     edi, [r14]
0x140018ce5  mov     rbx, [rsp+78h+arg_78]
0x140018ced  mov     [rbx+8], edi
0x140018cf0  mov     eax, [r14+4]
0x140018cf4  mov     [rbx+0Ch], eax
0x140018cf7  xor     ebp, ebp
0x140018cf9  mov     r15d, [rsp+78h+arg_30]
0x140018d01  mov     ecx, r15d
0x140018d04  test    r15d, r15d
0x140018d07  jz      short loc_140018D6F
0x140018d09  sub     ecx, 1
0x140018d0c  jz      short loc_140018D66
0x140018d0e  sub     ecx, 1
0x140018d11  jz      short loc_140018D21
0x140018d13  cmp     ecx, 1
0x140018d16  jnz     short loc_140018D78
0x140018d18  mov     ecx, edi; this
0x140018d1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140018d1f  jmp     short loc_140018D76
0x140018d21  test    edi, edi
0x140018d23  js      short loc_140018D5D
0x140018d25  mov     edi, 8007029Ch
0x140018d2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140018d2e  mov     rax, [rsp+78h+arg_28]
0x140018d36  mov     [rsp+78h+var_50], rax; __int64
0x140018d3b  mov     rax, [rsp+78h+arg_20]
0x140018d43  mov     [rsp+78h+var_58], rax; __int64
0x140018d48  mov     rcx, r10; int
0x140018d4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140018d50  mov     [rbx+8], edi
0x140018d53  mov     ecx, edi; this
0x140018d55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140018d5a  mov     [rbx+0Ch], eax
0x140018d5d  mov     ecx, edi; this
0x140018d5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140018d64  jmp     short loc_140018D76
0x140018d66  mov     ecx, edi; this
0x140018d68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140018d6d  jmp     short loc_140018D76
0x140018d6f  mov     ecx, edi; this
0x140018d71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140018d76  mov     ebp, eax
0x140018d78  mov     [rbx], r15d
0x140018d7b  mov     eax, [rsp+78h+arg_70]
0x140018d82  mov     [rbx+4], eax
0x140018d85  cmp     dword ptr [r14+8], 1
0x140018d8a  jnz     short loc_140018D92
0x140018d8c  or      eax, 8
0x140018d8f  mov     [rbx+4], eax
0x140018d92  mov     eax, 1
0x140018d97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140018d9f  inc     eax
0x140018da1  mov     [rbx+10h], eax
0x140018da4  mov     rax, [rsp+78h+arg_40]
0x140018dac  xor     edi, edi
0x140018dae  test    rax, rax
0x140018db1  jz      short loc_140018DB8
0x140018db3  cmp     [rax], di
0x140018db6  jnz     short loc_140018DBB
0x140018db8  mov     rax, rdi
0x140018dbb  mov     [rbx+18h], rax
0x140018dbf  call    cs:__imp_GetCurrentThreadId
0x140018dc5  mov     [rbx+20h], eax
0x140018dc8  mov     [rbx+38h], r13
0x140018dcc  mov     eax, [rsp+78h+arg_8]
0x140018dd3  mov     [rbx+40h], eax
0x140018dd6  mov     [rbx+44h], ebp
0x140018dd9  mov     rax, [rsp+78h+arg_20]
0x140018de1  mov     [rbx+28h], rax
0x140018de5  mov     [rbx+30h], r12
0x140018de9  mov     rax, [rsp+78h+arg_28]
0x140018df1  mov     [rbx+88h], rax
0x140018df8  mov     rax, [rsp+78h+arg_0]
0x140018e00  mov     [rbx+90h], rax
0x140018e07  mov     [rbx+48h], rdi
0x140018e0b  xorps   xmm0, xmm0
0x140018e0e  xor     eax, eax
0x140018e10  movups  xmmword ptr [rbx+68h], xmm0
0x140018e14  mov     [rbx+78h], rax
0x140018e18  movups  xmmword ptr [rbx+50h], xmm0
0x140018e1c  mov     [rbx+60h], rax
0x140018e20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140018e27  test    rax, rax
0x140018e2a  jz      short loc_140018E33
0x140018e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018e31  jmp     short loc_140018E36
0x140018e33  mov     rax, rdi
0x140018e36  mov     [rbx+80h], rax
0x140018e3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140018e44  test    rax, rax
0x140018e47  jz      short loc_140018E51
0x140018e49  mov     rcx, rbx
0x140018e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018e51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140018e58  test    rax, rax
0x140018e5b  jz      short loc_140018E73
0x140018e5d  mov     r8d, 400h
0x140018e63  mov     rdx, [rsp+78h+arg_60]
0x140018e6b  mov     rcx, rbx
0x140018e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018e73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140018e7a  test    rax, rax
0x140018e7d  jz      short loc_140018E87
0x140018e7f  mov     rcx, rbx
0x140018e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018e87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140018e8e  test    rax, rax
0x140018e91  jz      short loc_140018EA1
0x140018e93  test    byte ptr [rbx+4], 2
0x140018e97  jnz     short loc_140018EA1
0x140018e99  mov     rcx, rbx
0x140018e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ea1  cmp     [rbx+8], edi
0x140018ea4  jl      short loc_140018EC2
0x140018ea6  cmp     r15d, 3
0x140018eaa  jz      short loc_140018EB2
0x140018eac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140018eb2  mov     ecx, 8000FFFFh; this
0x140018eb7  mov     [rbx+8], ecx
0x140018eba  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140018ebf  mov     [rbx+0Ch], eax
0x140018ec2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140018ec9  jnz     short loc_140018EEA
0x140018ecb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140018ed2  test    rax, rax
0x140018ed5  jz      short loc_140018EE0
0x140018ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018edc  test    al, al
0x140018ede  jmp     short loc_140018EE8
0x140018ee0  call    cs:__imp_IsDebuggerPresent
0x140018ee6  test    eax, eax
0x140018ee8  jz      short loc_140018EF0
0x140018eea  test    byte ptr [rbx+4], 2
0x140018eee  jz      short loc_140018F14
0x140018ef0  mov     rax, cs:g_pfnResultLoggingCallback
0x140018ef7  test    rax, rax
0x140018efa  jz      short loc_140018F58
0x140018efc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140018f03  jnz     short loc_140018F58
0x140018f05  xor     r8d, r8d
0x140018f08  xor     edx, edx
0x140018f0a  mov     rcx, rbx
0x140018f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f12  jmp     short loc_140018F58
0x140018f14  mov     ebp, 800h
0x140018f19  mov     rax, cs:g_pfnResultLoggingCallback
0x140018f20  test    rax, rax
0x140018f23  jz      short loc_140018F3C
0x140018f25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140018f2c  jnz     short loc_140018F3C
0x140018f2e  mov     r8d, ebp
0x140018f31  mov     rdx, rsi
0x140018f34  mov     rcx, rbx
0x140018f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f3c  cmp     [rsi], di
0x140018f3f  jnz     short loc_140018F4F
0x140018f41  mov     r8, rbx; unsigned __int64
0x140018f44  mov     rdx, rbp; wchar_t *
0x140018f47  mov     rcx, rsi; this
0x140018f4a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140018f4f  mov     rcx, rsi; lpOutputString
0x140018f52  call    cs:__imp_OutputDebugStringW
0x140018f58  test    byte ptr [rbx+4], 4
0x140018f5c  jnz     short loc_140018F67
0x140018f5e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140018f65  jz      short loc_140018F79
0x140018f67  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140018f6e  test    rax, rax
0x140018f71  jz      short loc_140018F79
0x140018f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f78  nop
0x140018f79  mov     rbx, [rsp+78h+arg_10]
0x140018f81  add     rsp, 40h
0x140018f85  pop     r15
0x140018f87  pop     r14
0x140018f89  pop     r13
0x140018f8b  pop     r12
0x140018f8d  pop     rdi
0x140018f8e  pop     rsi
0x140018f8f  pop     rbp
0x140018f90  retn
```
