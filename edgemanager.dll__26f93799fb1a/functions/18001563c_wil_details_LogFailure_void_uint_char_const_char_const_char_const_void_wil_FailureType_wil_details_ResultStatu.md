# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001563c`
- end: `0x180015931`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180008c5c`
- `0x18001554c`
- `0x1800344d0`

## callees

- `0x1800087e8`
- `0x18001563c`
- `0x180015940`
- `0x180030ae4`
- `0x180034418`
- `0x180035260`
- `0x18003527c`
- `0x180035298`
- `0x180035b78`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001575f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001575f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015880`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015880`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800158f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800158f2`

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
0x18001563c  mov     [rsp+arg_10], rbx
0x180015641  mov     [rsp+arg_8], edx
0x180015645  mov     [rsp+arg_0], rcx
0x18001564a  push    rbp
0x18001564b  push    rsi
0x18001564c  push    rdi
0x18001564d  push    r12
0x18001564f  push    r13
0x180015651  push    r14
0x180015653  push    r15
0x180015655  sub     rsp, 40h
0x180015659  mov     r12, r9
0x18001565c  mov     r13, r8
0x18001565f  mov     r10, rcx
0x180015662  xor     eax, eax
0x180015664  mov     rsi, [rsp+78h+lpOutputString]
0x18001566c  mov     [rsi], ax
0x18001566f  mov     rax, [rsp+78h+arg_60]
0x180015677  mov     byte ptr [rax], 0
0x18001567a  mov     r14, [rsp+78h+arg_38]
0x180015682  mov     edi, [r14]
0x180015685  mov     rbx, [rsp+78h+arg_78]
0x18001568d  mov     [rbx+8], edi
0x180015690  mov     eax, [r14+4]
0x180015694  mov     [rbx+0Ch], eax
0x180015697  xor     ebp, ebp
0x180015699  mov     r15d, [rsp+78h+arg_30]
0x1800156a1  mov     ecx, r15d
0x1800156a4  test    r15d, r15d
0x1800156a7  jz      short loc_18001570F
0x1800156a9  sub     ecx, 1
0x1800156ac  jz      short loc_180015706
0x1800156ae  sub     ecx, 1
0x1800156b1  jz      short loc_1800156C1
0x1800156b3  cmp     ecx, 1
0x1800156b6  jnz     short loc_180015718
0x1800156b8  mov     ecx, edi; this
0x1800156ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800156bf  jmp     short loc_180015716
0x1800156c1  test    edi, edi
0x1800156c3  js      short loc_1800156FD
0x1800156c5  mov     edi, 8007029Ch
0x1800156ca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800156ce  mov     rax, [rsp+78h+arg_28]
0x1800156d6  mov     [rsp+78h+var_50], rax; __int64
0x1800156db  mov     rax, [rsp+78h+arg_20]
0x1800156e3  mov     [rsp+78h+var_58], rax; __int64
0x1800156e8  mov     rcx, r10; int
0x1800156eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800156f0  mov     [rbx+8], edi
0x1800156f3  mov     ecx, edi; this
0x1800156f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800156fa  mov     [rbx+0Ch], eax
0x1800156fd  mov     ecx, edi; this
0x1800156ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180015704  jmp     short loc_180015716
0x180015706  mov     ecx, edi; this
0x180015708  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001570d  jmp     short loc_180015716
0x18001570f  mov     ecx, edi; this
0x180015711  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180015716  mov     ebp, eax
0x180015718  mov     [rbx], r15d
0x18001571b  mov     eax, [rsp+78h+arg_70]
0x180015722  mov     [rbx+4], eax
0x180015725  cmp     dword ptr [r14+8], 1
0x18001572a  jnz     short loc_180015732
0x18001572c  or      eax, 8
0x18001572f  mov     [rbx+4], eax
0x180015732  mov     eax, 1
0x180015737  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001573f  inc     eax
0x180015741  mov     [rbx+10h], eax
0x180015744  mov     rax, [rsp+78h+arg_40]
0x18001574c  xor     edi, edi
0x18001574e  test    rax, rax
0x180015751  jz      short loc_180015758
0x180015753  cmp     [rax], di
0x180015756  jnz     short loc_18001575B
0x180015758  mov     rax, rdi
0x18001575b  mov     [rbx+18h], rax
0x18001575f  call    cs:__imp_GetCurrentThreadId
0x180015765  mov     [rbx+20h], eax
0x180015768  mov     [rbx+38h], r13
0x18001576c  mov     eax, [rsp+78h+arg_8]
0x180015773  mov     [rbx+40h], eax
0x180015776  mov     [rbx+44h], ebp
0x180015779  mov     rax, [rsp+78h+arg_20]
0x180015781  mov     [rbx+28h], rax
0x180015785  mov     [rbx+30h], r12
0x180015789  mov     rax, [rsp+78h+arg_28]
0x180015791  mov     [rbx+88h], rax
0x180015798  mov     rax, [rsp+78h+arg_0]
0x1800157a0  mov     [rbx+90h], rax
0x1800157a7  mov     [rbx+48h], rdi
0x1800157ab  xorps   xmm0, xmm0
0x1800157ae  xor     eax, eax
0x1800157b0  movups  xmmword ptr [rbx+68h], xmm0
0x1800157b4  mov     [rbx+78h], rax
0x1800157b8  movups  xmmword ptr [rbx+50h], xmm0
0x1800157bc  mov     [rbx+60h], rax
0x1800157c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800157c7  test    rax, rax
0x1800157ca  jz      short loc_1800157D3
0x1800157cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d1  jmp     short loc_1800157D6
0x1800157d3  mov     rax, rdi
0x1800157d6  mov     [rbx+80h], rax
0x1800157dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800157e4  test    rax, rax
0x1800157e7  jz      short loc_1800157F1
0x1800157e9  mov     rcx, rbx
0x1800157ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800157f8  test    rax, rax
0x1800157fb  jz      short loc_180015813
0x1800157fd  mov     r8d, 400h
0x180015803  mov     rdx, [rsp+78h+arg_60]
0x18001580b  mov     rcx, rbx
0x18001580e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015813  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001581a  test    rax, rax
0x18001581d  jz      short loc_180015827
0x18001581f  mov     rcx, rbx
0x180015822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015827  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001582e  test    rax, rax
0x180015831  jz      short loc_180015841
0x180015833  test    byte ptr [rbx+4], 2
0x180015837  jnz     short loc_180015841
0x180015839  mov     rcx, rbx
0x18001583c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015841  cmp     [rbx+8], edi
0x180015844  jl      short loc_180015862
0x180015846  cmp     r15d, 3
0x18001584a  jz      short loc_180015852
0x18001584c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180015852  mov     ecx, 8000FFFFh; this
0x180015857  mov     [rbx+8], ecx
0x18001585a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001585f  mov     [rbx+0Ch], eax
0x180015862  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180015869  jnz     short loc_18001588A
0x18001586b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015872  test    rax, rax
0x180015875  jz      short loc_180015880
0x180015877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001587c  test    al, al
0x18001587e  jmp     short loc_180015888
0x180015880  call    cs:__imp_IsDebuggerPresent
0x180015886  test    eax, eax
0x180015888  jz      short loc_180015890
0x18001588a  test    byte ptr [rbx+4], 2
0x18001588e  jz      short loc_1800158B4
0x180015890  mov     rax, cs:g_pfnResultLoggingCallback
0x180015897  test    rax, rax
0x18001589a  jz      short loc_1800158F8
0x18001589c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800158a3  jnz     short loc_1800158F8
0x1800158a5  xor     r8d, r8d
0x1800158a8  xor     edx, edx
0x1800158aa  mov     rcx, rbx
0x1800158ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158b2  jmp     short loc_1800158F8
0x1800158b4  mov     ebp, 800h
0x1800158b9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800158c0  test    rax, rax
0x1800158c3  jz      short loc_1800158DC
0x1800158c5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800158cc  jnz     short loc_1800158DC
0x1800158ce  mov     r8d, ebp
0x1800158d1  mov     rdx, rsi
0x1800158d4  mov     rcx, rbx
0x1800158d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158dc  cmp     [rsi], di
0x1800158df  jnz     short loc_1800158EF
0x1800158e1  mov     r8, rbx; unsigned __int64
0x1800158e4  mov     rdx, rbp; unsigned __int16 *
0x1800158e7  mov     rcx, rsi; this
0x1800158ea  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800158ef  mov     rcx, rsi; lpOutputString
0x1800158f2  call    cs:__imp_OutputDebugStringW
0x1800158f8  test    byte ptr [rbx+4], 4
0x1800158fc  jnz     short loc_180015907
0x1800158fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180015905  jz      short loc_180015919
0x180015907  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001590e  test    rax, rax
0x180015911  jz      short loc_180015919
0x180015913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015918  nop
0x180015919  mov     rbx, [rsp+78h+arg_10]
0x180015921  add     rsp, 40h
0x180015925  pop     r15
0x180015927  pop     r14
0x180015929  pop     r13
0x18001592b  pop     r12
0x18001592d  pop     rdi
0x18001592e  pop     rsi
0x18001592f  pop     rbp
0x180015930  retn
```
