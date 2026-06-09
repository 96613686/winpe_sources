# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000468c`
- end: `0x180004984`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003194`

## callees

- `0x180002bd0`
- `0x180003d14`
- `0x1800044ac`
- `0x18000468c`
- `0x180004bcc`
- `0x180004bf0`
- `0x180004c04`
- `0x180004c20`
- `0x1800056fc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004940`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004940`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048ce`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18000468c  mov     [rsp+arg_10], rbx
0x180004691  mov     [rsp+arg_8], edx
0x180004695  mov     [rsp+arg_0], rcx
0x18000469a  push    rbp
0x18000469b  push    rsi
0x18000469c  push    rdi
0x18000469d  push    r12
0x18000469f  push    r13
0x1800046a1  push    r14
0x1800046a3  push    r15
0x1800046a5  sub     rsp, 40h
0x1800046a9  mov     r14, [rsp+78h+arg_38]
0x1800046b1  xor     eax, eax
0x1800046b3  mov     rbx, [rsp+78h+arg_78]
0x1800046bb  xor     ebp, ebp
0x1800046bd  mov     r15d, [rsp+78h+arg_30]
0x1800046c5  mov     r10, rcx
0x1800046c8  mov     rsi, [rsp+78h+lpOutputString]
0x1800046d0  mov     r12, r9
0x1800046d3  mov     r13, r8
0x1800046d6  mov     ecx, r15d
0x1800046d9  mov     [rsi], ax
0x1800046dc  mov     rax, [rsp+78h+arg_60]
0x1800046e4  mov     byte ptr [rax], 0
0x1800046e7  mov     edi, [r14]
0x1800046ea  mov     [rbx+8], edi
0x1800046ed  mov     eax, [r14+4]
0x1800046f1  mov     [rbx+0Ch], eax
0x1800046f4  test    r15d, r15d
0x1800046f7  jz      short loc_18000475F
0x1800046f9  sub     ecx, 1
0x1800046fc  jz      short loc_180004756
0x1800046fe  sub     ecx, 1
0x180004701  jz      short loc_180004711
0x180004703  cmp     ecx, 1
0x180004706  jnz     short loc_180004768
0x180004708  mov     ecx, edi; this
0x18000470a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000470f  jmp     short loc_180004766
0x180004711  test    edi, edi
0x180004713  js      short loc_18000474D
0x180004715  mov     rax, [rsp+78h+arg_28]
0x18000471d  mov     edi, 8007029Ch
0x180004722  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004726  mov     rcx, r10; int
0x180004729  mov     [rsp+78h+var_50], rax; __int64
0x18000472e  mov     rax, [rsp+78h+arg_20]
0x180004736  mov     [rsp+78h+var_58], rax; __int64
0x18000473b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004740  mov     ecx, edi; this
0x180004742  mov     [rbx+8], edi
0x180004745  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000474a  mov     [rbx+0Ch], eax
0x18000474d  mov     ecx, edi; this
0x18000474f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004754  jmp     short loc_180004766
0x180004756  mov     ecx, edi; this
0x180004758  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000475d  jmp     short loc_180004766
0x18000475f  mov     ecx, edi; this
0x180004761  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004766  mov     ebp, eax
0x180004768  mov     eax, [rsp+78h+arg_70]
0x18000476f  mov     [rbx+4], eax
0x180004772  mov     [rbx], r15d
0x180004775  cmp     dword ptr [r14+8], 1
0x18000477a  jnz     short loc_180004782
0x18000477c  or      eax, 8
0x18000477f  mov     [rbx+4], eax
0x180004782  mov     eax, 1
0x180004787  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000478f  inc     eax
0x180004791  xor     edi, edi
0x180004793  mov     [rbx+10h], eax
0x180004796  mov     rax, [rsp+78h+arg_40]
0x18000479e  test    rax, rax
0x1800047a1  jz      short loc_1800047A8
0x1800047a3  cmp     [rax], di
0x1800047a6  jnz     short loc_1800047AB
0x1800047a8  mov     rax, rdi
0x1800047ab  mov     [rbx+18h], rax
0x1800047af  call    cs:__imp_GetCurrentThreadId
0x1800047b5  mov     [rbx+38h], r13
0x1800047b9  xorps   xmm0, xmm0
0x1800047bc  mov     [rbx+20h], eax
0x1800047bf  mov     eax, [rsp+78h+arg_8]
0x1800047c6  mov     [rbx+40h], eax
0x1800047c9  mov     rax, [rsp+78h+arg_20]
0x1800047d1  mov     [rbx+28h], rax
0x1800047d5  mov     rax, [rsp+78h+arg_28]
0x1800047dd  mov     [rbx+88h], rax
0x1800047e4  mov     rax, [rsp+78h+arg_0]
0x1800047ec  mov     [rbx+90h], rax
0x1800047f3  xor     eax, eax
0x1800047f5  mov     [rbx+44h], ebp
0x1800047f8  mov     [rbx+30h], r12
0x1800047fc  mov     [rbx+48h], rdi
0x180004800  movups  xmmword ptr [rbx+68h], xmm0
0x180004804  mov     [rbx+78h], rax
0x180004808  movups  xmmword ptr [rbx+50h], xmm0
0x18000480c  mov     [rbx+60h], rax
0x180004810  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004817  test    rax, rax
0x18000481a  jz      short loc_180004823
0x18000481c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004821  jmp     short loc_180004826
0x180004823  mov     rax, rdi
0x180004826  mov     [rbx+80h], rax
0x18000482d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004834  test    rax, rax
0x180004837  jz      short loc_180004841
0x180004839  mov     rcx, rbx
0x18000483c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004841  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004848  test    rax, rax
0x18000484b  jz      short loc_180004863
0x18000484d  mov     rdx, [rsp+78h+arg_60]
0x180004855  mov     r8d, 400h
0x18000485b  mov     rcx, rbx
0x18000485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004863  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000486a  test    rax, rax
0x18000486d  jz      short loc_180004877
0x18000486f  mov     rcx, rbx
0x180004872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004877  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000487e  test    rax, rax
0x180004881  jz      short loc_180004891
0x180004883  test    byte ptr [rbx+4], 2
0x180004887  jnz     short loc_180004891
0x180004889  mov     rcx, rbx
0x18000488c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004891  cmp     [rbx+8], edi
0x180004894  jl      short loc_1800048B0
0x180004896  cmp     r15d, 3
0x18000489a  jnz     loc_18000497E
0x1800048a0  mov     ecx, 8000FFFFh; this
0x1800048a5  mov     [rbx+8], ecx
0x1800048a8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800048ad  mov     [rbx+0Ch], eax
0x1800048b0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800048b7  jnz     short loc_1800048D8
0x1800048b9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800048c0  test    rax, rax
0x1800048c3  jz      short loc_1800048CE
0x1800048c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ca  test    al, al
0x1800048cc  jmp     short loc_1800048D6
0x1800048ce  call    cs:__imp_IsDebuggerPresent
0x1800048d4  test    eax, eax
0x1800048d6  jz      short loc_1800048DE
0x1800048d8  test    byte ptr [rbx+4], 2
0x1800048dc  jz      short loc_180004902
0x1800048de  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048e5  test    rax, rax
0x1800048e8  jz      short loc_180004946
0x1800048ea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800048f1  jnz     short loc_180004946
0x1800048f3  xor     r8d, r8d
0x1800048f6  xor     edx, edx
0x1800048f8  mov     rcx, rbx
0x1800048fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004900  jmp     short loc_180004946
0x180004902  mov     rax, cs:g_pfnResultLoggingCallback
0x180004909  mov     ebp, 800h
0x18000490e  test    rax, rax
0x180004911  jz      short loc_18000492A
0x180004913  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000491a  jnz     short loc_18000492A
0x18000491c  mov     r8d, ebp
0x18000491f  mov     rdx, rsi
0x180004922  mov     rcx, rbx
0x180004925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492a  cmp     [rsi], di
0x18000492d  jnz     short loc_18000493D
0x18000492f  mov     r8, rbx; unsigned __int64
0x180004932  mov     rdx, rbp; unsigned __int16 *
0x180004935  mov     rcx, rsi; this
0x180004938  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000493d  mov     rcx, rsi; lpOutputString
0x180004940  call    cs:__imp_OutputDebugStringW
0x180004946  test    byte ptr [rbx+4], 4
0x18000494a  jnz     short loc_180004955
0x18000494c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004953  jz      short loc_180004966
0x180004955  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000495c  test    rax, rax
0x18000495f  jz      short loc_180004966
0x180004961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004966  mov     rbx, [rsp+78h+arg_10]
0x18000496e  add     rsp, 40h
0x180004972  pop     r15
0x180004974  pop     r14
0x180004976  pop     r13
0x180004978  pop     r12
0x18000497a  pop     rdi
0x18000497b  pop     rsi
0x18000497c  pop     rbp
0x18000497d  retn
0x18000497e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
