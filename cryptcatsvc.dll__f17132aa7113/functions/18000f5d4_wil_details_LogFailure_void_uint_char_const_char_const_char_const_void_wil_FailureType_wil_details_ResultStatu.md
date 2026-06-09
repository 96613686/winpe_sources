# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000f5d4`
- end: `0x18000f8d5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d40c`
- `0x18000d764`

## callees

- `0x18000b348`
- `0x18000d34c`
- `0x18000ebd4`
- `0x18000f5d4`
- `0x180010214`
- `0x180010230`
- `0x18001037c`
- `0x180010398`
- `0x180011e40`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f6ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f6ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f81e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f81e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f890`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f890`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
0x18000f5d4  mov     rax, rsp
0x18000f5d7  mov     [rax+10h], edx
0x18000f5da  mov     [rax+8], rcx
0x18000f5de  push    rbp
0x18000f5df  push    rsi
0x18000f5e0  push    rdi
0x18000f5e1  push    r12
0x18000f5e3  push    r13
0x18000f5e5  push    r14
0x18000f5e7  push    r15
0x18000f5e9  sub     rsp, 50h
0x18000f5ed  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000f5f5  mov     [rax+18h], rbx
0x18000f5f9  mov     r12, r9
0x18000f5fc  mov     r13, r8
0x18000f5ff  mov     r10, rcx
0x18000f602  xor     eax, eax
0x18000f604  mov     rsi, [rsp+88h+lpOutputString]
0x18000f60c  mov     [rsi], ax
0x18000f60f  mov     rax, [rsp+88h+arg_60]
0x18000f617  mov     byte ptr [rax], 0
0x18000f61a  mov     r14, [rsp+88h+arg_38]
0x18000f622  mov     edi, [r14]
0x18000f625  mov     rbx, [rsp+88h+arg_78]
0x18000f62d  mov     [rbx+8], edi
0x18000f630  mov     eax, [r14+4]
0x18000f634  mov     [rbx+0Ch], eax
0x18000f637  xor     ebp, ebp
0x18000f639  mov     r15d, [rsp+88h+arg_30]
0x18000f641  mov     ecx, r15d
0x18000f644  test    r15d, r15d
0x18000f647  jz      short loc_18000F6AF
0x18000f649  sub     ecx, 1
0x18000f64c  jz      short loc_18000F6A6
0x18000f64e  sub     ecx, 1
0x18000f651  jz      short loc_18000F661
0x18000f653  cmp     ecx, 1
0x18000f656  jnz     short loc_18000F6B8
0x18000f658  mov     ecx, edi; this
0x18000f65a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000f65f  jmp     short loc_18000F6B6
0x18000f661  test    edi, edi
0x18000f663  js      short loc_18000F69D
0x18000f665  mov     edi, 8007029Ch
0x18000f66a  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18000f66e  mov     rax, [rsp+88h+arg_28]
0x18000f676  mov     [rsp+88h+var_60], rax; __int64
0x18000f67b  mov     rax, [rsp+88h+arg_20]
0x18000f683  mov     [rsp+88h+var_68], rax; __int64
0x18000f688  mov     rcx, r10; int
0x18000f68b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000f690  mov     [rbx+8], edi
0x18000f693  mov     ecx, edi; this
0x18000f695  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f69a  mov     [rbx+0Ch], eax
0x18000f69d  mov     ecx, edi; this
0x18000f69f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000f6a4  jmp     short loc_18000F6B6
0x18000f6a6  mov     ecx, edi; this
0x18000f6a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000f6ad  jmp     short loc_18000F6B6
0x18000f6af  mov     ecx, edi; this
0x18000f6b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000f6b6  mov     ebp, eax
0x18000f6b8  mov     [rbx], r15d
0x18000f6bb  mov     eax, [rsp+88h+arg_70]
0x18000f6c2  mov     [rbx+4], eax
0x18000f6c5  cmp     dword ptr [r14+8], 1
0x18000f6ca  jnz     short loc_18000F6D2
0x18000f6cc  or      eax, 8
0x18000f6cf  mov     [rbx+4], eax
0x18000f6d2  mov     eax, 1
0x18000f6d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f6df  inc     eax
0x18000f6e1  mov     [rbx+10h], eax
0x18000f6e4  mov     rax, [rsp+88h+arg_40]
0x18000f6ec  xor     edi, edi
0x18000f6ee  test    rax, rax
0x18000f6f1  jz      short loc_18000F6F8
0x18000f6f3  cmp     [rax], di
0x18000f6f6  jnz     short loc_18000F6FB
0x18000f6f8  mov     rax, rdi
0x18000f6fb  mov     [rbx+18h], rax
0x18000f6ff  call    cs:__imp_GetCurrentThreadId
0x18000f705  mov     [rbx+20h], eax
0x18000f708  mov     [rbx+38h], r13
0x18000f70c  mov     eax, [rsp+88h+arg_8]
0x18000f713  mov     [rbx+40h], eax
0x18000f716  mov     [rbx+44h], ebp
0x18000f719  mov     rax, [rsp+88h+arg_20]
0x18000f721  mov     [rbx+28h], rax
0x18000f725  mov     [rbx+30h], r12
0x18000f729  mov     rax, [rsp+88h+arg_28]
0x18000f731  mov     [rbx+88h], rax
0x18000f738  mov     rax, [rsp+88h+arg_0]
0x18000f740  mov     [rbx+90h], rax
0x18000f747  mov     [rbx+48h], rdi
0x18000f74b  xorps   xmm0, xmm0
0x18000f74e  xor     eax, eax
0x18000f750  movups  xmmword ptr [rbx+68h], xmm0
0x18000f754  mov     [rbx+78h], rax
0x18000f758  movups  xmmword ptr [rbx+50h], xmm0
0x18000f75c  mov     [rbx+60h], rax
0x18000f760  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f767  test    rax, rax
0x18000f76a  jz      short loc_18000F773
0x18000f76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f771  jmp     short loc_18000F776
0x18000f773  mov     rax, rdi
0x18000f776  mov     [rbx+80h], rax
0x18000f77d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f784  test    rax, rax
0x18000f787  jz      short loc_18000F791
0x18000f789  mov     rcx, rbx
0x18000f78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f791  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f798  test    rax, rax
0x18000f79b  jz      short loc_18000F7B3
0x18000f79d  mov     r8d, 400h
0x18000f7a3  mov     rdx, [rsp+88h+arg_60]
0x18000f7ab  mov     rcx, rbx
0x18000f7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f7ba  test    rax, rax
0x18000f7bd  jz      short loc_18000F7C7
0x18000f7bf  mov     rcx, rbx
0x18000f7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f7ce  test    rax, rax
0x18000f7d1  jz      short loc_18000F7E1
0x18000f7d3  test    byte ptr [rbx+4], 2
0x18000f7d7  jnz     short loc_18000F7E1
0x18000f7d9  mov     rcx, rbx
0x18000f7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7e1  cmp     [rbx+8], edi
0x18000f7e4  jl      short loc_18000F800
0x18000f7e6  cmp     r15d, 3
0x18000f7ea  jnz     loc_18000F8CF
0x18000f7f0  mov     ecx, 8000FFFFh; this
0x18000f7f5  mov     [rbx+8], ecx
0x18000f7f8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f7fd  mov     [rbx+0Ch], eax
0x18000f800  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000f807  jnz     short loc_18000F828
0x18000f809  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f810  test    rax, rax
0x18000f813  jz      short loc_18000F81E
0x18000f815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f81a  test    al, al
0x18000f81c  jmp     short loc_18000F826
0x18000f81e  call    cs:__imp_IsDebuggerPresent
0x18000f824  test    eax, eax
0x18000f826  jz      short loc_18000F82E
0x18000f828  test    byte ptr [rbx+4], 2
0x18000f82c  jz      short loc_18000F852
0x18000f82e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f835  test    rax, rax
0x18000f838  jz      short loc_18000F896
0x18000f83a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f841  jnz     short loc_18000F896
0x18000f843  xor     r8d, r8d
0x18000f846  xor     edx, edx
0x18000f848  mov     rcx, rbx
0x18000f84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f850  jmp     short loc_18000F896
0x18000f852  mov     ebp, 800h
0x18000f857  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f85e  test    rax, rax
0x18000f861  jz      short loc_18000F87A
0x18000f863  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f86a  jnz     short loc_18000F87A
0x18000f86c  mov     r8d, ebp
0x18000f86f  mov     rdx, rsi
0x18000f872  mov     rcx, rbx
0x18000f875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87a  cmp     [rsi], di
0x18000f87d  jnz     short loc_18000F88D
0x18000f87f  mov     r8, rbx; unsigned __int64
0x18000f882  mov     rdx, rbp; unsigned __int16 *
0x18000f885  mov     rcx, rsi; this
0x18000f888  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f88d  mov     rcx, rsi; lpOutputString
0x18000f890  call    cs:__imp_OutputDebugStringW
0x18000f896  test    byte ptr [rbx+4], 4
0x18000f89a  jnz     short loc_18000F8A5
0x18000f89c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000f8a3  jz      short loc_18000F8B7
0x18000f8a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f8ac  test    rax, rax
0x18000f8af  jz      short loc_18000F8B7
0x18000f8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8b6  nop
0x18000f8b7  mov     rbx, [rsp+88h+arg_10]
0x18000f8bf  add     rsp, 50h
0x18000f8c3  pop     r15
0x18000f8c5  pop     r14
0x18000f8c7  pop     r13
0x18000f8c9  pop     r12
0x18000f8cb  pop     rdi
0x18000f8cc  pop     rsi
0x18000f8cd  pop     rbp
0x18000f8ce  retn
0x18000f8cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
