# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005a884`
- end: `0x18005ab8f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18005964c`
- `0x1800599ac`

## callees

- `0x18004eccc`
- `0x18005958c`
- `0x18005a264`
- `0x18005a884`
- `0x18005aea0`
- `0x18005aec0`
- `0x18005af30`
- `0x18005af50`
- `0x18005b8f8`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005a9a7`
- `KERNEL32!GetCurrentThreadId` at `0x18005a9a7`
- `KERNEL32!OutputDebugStringW` at `0x18005ab44`
- `KERNEL32!OutputDebugStringW` at `0x18005ab44`
- `KERNEL32!IsDebuggerPresent` at `0x18005aacc`
- `KERNEL32!IsDebuggerPresent` at `0x18005aacc`

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
0x18005a884  mov     [rsp+arg_10], rbx
0x18005a889  mov     [rsp+arg_8], edx
0x18005a88d  mov     [rsp+arg_0], rcx
0x18005a892  push    rbp
0x18005a893  push    rsi
0x18005a894  push    rdi
0x18005a895  push    r12
0x18005a897  push    r13
0x18005a899  push    r14
0x18005a89b  push    r15
0x18005a89d  sub     rsp, 40h
0x18005a8a1  mov     r14, [rsp+78h+arg_38]
0x18005a8a9  xor     eax, eax
0x18005a8ab  mov     rbx, [rsp+78h+arg_78]
0x18005a8b3  xor     ebp, ebp
0x18005a8b5  mov     r15d, [rsp+78h+arg_30]
0x18005a8bd  mov     r10, rcx
0x18005a8c0  mov     rsi, [rsp+78h+lpOutputString]
0x18005a8c8  mov     r12, r9
0x18005a8cb  mov     r13, r8
0x18005a8ce  mov     ecx, r15d
0x18005a8d1  mov     [rsi], ax
0x18005a8d4  mov     rax, [rsp+78h+arg_60]
0x18005a8dc  mov     byte ptr [rax], 0
0x18005a8df  mov     edi, [r14]
0x18005a8e2  mov     [rbx+8], edi
0x18005a8e5  mov     eax, [r14+4]
0x18005a8e9  mov     [rbx+0Ch], eax
0x18005a8ec  test    r15d, r15d
0x18005a8ef  jz      short loc_18005A957
0x18005a8f1  sub     ecx, 1
0x18005a8f4  jz      short loc_18005A94E
0x18005a8f6  sub     ecx, 1
0x18005a8f9  jz      short loc_18005A909
0x18005a8fb  cmp     ecx, 1
0x18005a8fe  jnz     short loc_18005A960
0x18005a900  mov     ecx, edi; this
0x18005a902  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005a907  jmp     short loc_18005A95E
0x18005a909  test    edi, edi
0x18005a90b  js      short loc_18005A945
0x18005a90d  mov     rax, [rsp+78h+arg_28]
0x18005a915  mov     edi, 8007029Ch
0x18005a91a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005a91e  mov     rcx, r10; int
0x18005a921  mov     [rsp+78h+var_50], rax; __int64
0x18005a926  mov     rax, [rsp+78h+arg_20]
0x18005a92e  mov     [rsp+78h+var_58], rax; __int64
0x18005a933  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18005a938  mov     ecx, edi; this
0x18005a93a  mov     [rbx+8], edi
0x18005a93d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005a942  mov     [rbx+0Ch], eax
0x18005a945  mov     ecx, edi; this
0x18005a947  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005a94c  jmp     short loc_18005A95E
0x18005a94e  mov     ecx, edi; this
0x18005a950  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005a955  jmp     short loc_18005A95E
0x18005a957  mov     ecx, edi; this
0x18005a959  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005a95e  mov     ebp, eax
0x18005a960  mov     eax, [rsp+78h+arg_70]
0x18005a967  mov     [rbx+4], eax
0x18005a96a  mov     [rbx], r15d
0x18005a96d  cmp     dword ptr [r14+8], 1
0x18005a972  jnz     short loc_18005A97A
0x18005a974  or      eax, 8
0x18005a977  mov     [rbx+4], eax
0x18005a97a  mov     eax, 1
0x18005a97f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005a987  inc     eax
0x18005a989  xor     edi, edi
0x18005a98b  mov     [rbx+10h], eax
0x18005a98e  mov     rax, [rsp+78h+arg_40]
0x18005a996  test    rax, rax
0x18005a999  jz      short loc_18005A9A0
0x18005a99b  cmp     [rax], di
0x18005a99e  jnz     short loc_18005A9A3
0x18005a9a0  mov     rax, rdi
0x18005a9a3  mov     [rbx+18h], rax
0x18005a9a7  call    cs:__imp_GetCurrentThreadId
0x18005a9ae  nop     dword ptr [rax+rax+00h]
0x18005a9b3  mov     [rbx+38h], r13
0x18005a9b7  xorps   xmm0, xmm0
0x18005a9ba  mov     [rbx+20h], eax
0x18005a9bd  mov     eax, [rsp+78h+arg_8]
0x18005a9c4  mov     [rbx+40h], eax
0x18005a9c7  mov     rax, [rsp+78h+arg_20]
0x18005a9cf  mov     [rbx+28h], rax
0x18005a9d3  mov     rax, [rsp+78h+arg_28]
0x18005a9db  mov     [rbx+88h], rax
0x18005a9e2  mov     rax, [rsp+78h+arg_0]
0x18005a9ea  mov     [rbx+90h], rax
0x18005a9f1  xor     eax, eax
0x18005a9f3  mov     [rbx+44h], ebp
0x18005a9f6  mov     [rbx+30h], r12
0x18005a9fa  mov     [rbx+48h], rdi
0x18005a9fe  movups  xmmword ptr [rbx+68h], xmm0
0x18005aa02  mov     [rbx+78h], rax
0x18005aa06  movups  xmmword ptr [rbx+50h], xmm0
0x18005aa0a  mov     [rbx+60h], rax
0x18005aa0e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005aa15  test    rax, rax
0x18005aa18  jz      short loc_18005AA21
0x18005aa1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa1f  jmp     short loc_18005AA24
0x18005aa21  mov     rax, rdi
0x18005aa24  mov     [rbx+80h], rax
0x18005aa2b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005aa32  test    rax, rax
0x18005aa35  jz      short loc_18005AA3F
0x18005aa37  mov     rcx, rbx
0x18005aa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa3f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005aa46  test    rax, rax
0x18005aa49  jz      short loc_18005AA61
0x18005aa4b  mov     rdx, [rsp+78h+arg_60]
0x18005aa53  mov     r8d, 400h
0x18005aa59  mov     rcx, rbx
0x18005aa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa61  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005aa68  test    rax, rax
0x18005aa6b  jz      short loc_18005AA75
0x18005aa6d  mov     rcx, rbx
0x18005aa70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa75  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005aa7c  test    rax, rax
0x18005aa7f  jz      short loc_18005AA8F
0x18005aa81  test    byte ptr [rbx+4], 2
0x18005aa85  jnz     short loc_18005AA8F
0x18005aa87  mov     rcx, rbx
0x18005aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa8f  cmp     [rbx+8], edi
0x18005aa92  jl      short loc_18005AAAE
0x18005aa94  cmp     r15d, 3
0x18005aa98  jnz     loc_18005AB89
0x18005aa9e  mov     ecx, 8000FFFFh; this
0x18005aaa3  mov     [rbx+8], ecx
0x18005aaa6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005aaab  mov     [rbx+0Ch], eax
0x18005aaae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005aab5  jnz     short loc_18005AADC
0x18005aab7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005aabe  test    rax, rax
0x18005aac1  jz      short loc_18005AACC
0x18005aac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aac8  test    al, al
0x18005aaca  jmp     short loc_18005AADA
0x18005aacc  call    cs:__imp_IsDebuggerPresent
0x18005aad3  nop     dword ptr [rax+rax+00h]
0x18005aad8  test    eax, eax
0x18005aada  jz      short loc_18005AAE2
0x18005aadc  test    byte ptr [rbx+4], 2
0x18005aae0  jz      short loc_18005AB06
0x18005aae2  mov     rax, cs:g_pfnResultLoggingCallback
0x18005aae9  test    rax, rax
0x18005aaec  jz      short loc_18005AB50
0x18005aaee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005aaf5  jnz     short loc_18005AB50
0x18005aaf7  xor     r8d, r8d
0x18005aafa  xor     edx, edx
0x18005aafc  mov     rcx, rbx
0x18005aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab04  jmp     short loc_18005AB50
0x18005ab06  mov     rax, cs:g_pfnResultLoggingCallback
0x18005ab0d  mov     ebp, 800h
0x18005ab12  test    rax, rax
0x18005ab15  jz      short loc_18005AB2E
0x18005ab17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005ab1e  jnz     short loc_18005AB2E
0x18005ab20  mov     r8d, ebp
0x18005ab23  mov     rdx, rsi
0x18005ab26  mov     rcx, rbx
0x18005ab29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab2e  cmp     [rsi], di
0x18005ab31  jnz     short loc_18005AB41
0x18005ab33  mov     r8, rbx; unsigned __int64
0x18005ab36  mov     rdx, rbp; unsigned __int16 *
0x18005ab39  mov     rcx, rsi; this
0x18005ab3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005ab41  mov     rcx, rsi; lpOutputString
0x18005ab44  call    cs:__imp_OutputDebugStringW
0x18005ab4b  nop     dword ptr [rax+rax+00h]
0x18005ab50  test    byte ptr [rbx+4], 4
0x18005ab54  jnz     short loc_18005AB5F
0x18005ab56  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005ab5d  jz      short loc_18005AB70
0x18005ab5f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005ab66  test    rax, rax
0x18005ab69  jz      short loc_18005AB70
0x18005ab6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab70  mov     rbx, [rsp+78h+arg_10]
0x18005ab78  add     rsp, 40h
0x18005ab7c  pop     r15
0x18005ab7e  pop     r14
0x18005ab80  pop     r13
0x18005ab82  pop     r12
0x18005ab84  pop     rdi
0x18005ab85  pop     rsi
0x18005ab86  pop     rbp
0x18005ab87  retn
0x18005ab89  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
