# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140012400`
- end: `0x1400126f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1400111a8`
- `0x1400114ec`
- `0x140018a80`

## callees

- `0x14000abcc`
- `0x1400110e8`
- `0x140011e14`
- `0x140012400`
- `0x140012a74`
- `0x140012a90`
- `0x140012aa4`
- `0x140012ac0`
- `0x140013674`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012523`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140012642`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140012642`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400126b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400126b4`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        __int64 a2,
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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]
  int v28; // [rsp+88h] [rbp+10h]

  v28 = a2;
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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = v28;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x140012400  mov     [rsp+arg_10], rbx
0x140012405  mov     [rsp+arg_8], edx
0x140012409  mov     [rsp+arg_0], rcx
0x14001240e  push    rbp
0x14001240f  push    rsi
0x140012410  push    rdi
0x140012411  push    r12
0x140012413  push    r13
0x140012415  push    r14
0x140012417  push    r15
0x140012419  sub     rsp, 40h
0x14001241d  mov     r12, r9
0x140012420  mov     r13, r8
0x140012423  mov     r10, rcx
0x140012426  xor     eax, eax
0x140012428  mov     rsi, [rsp+78h+lpOutputString]
0x140012430  mov     [rsi], ax
0x140012433  mov     rax, [rsp+78h+arg_60]
0x14001243b  mov     byte ptr [rax], 0
0x14001243e  mov     r14, [rsp+78h+arg_38]
0x140012446  mov     edi, [r14]
0x140012449  mov     rbx, [rsp+78h+arg_78]
0x140012451  mov     [rbx+8], edi
0x140012454  mov     eax, [r14+4]
0x140012458  mov     [rbx+0Ch], eax
0x14001245b  xor     ebp, ebp
0x14001245d  mov     r15d, [rsp+78h+arg_30]
0x140012465  mov     ecx, r15d
0x140012468  test    r15d, r15d
0x14001246b  jz      short loc_1400124D3
0x14001246d  sub     ecx, 1
0x140012470  jz      short loc_1400124CA
0x140012472  sub     ecx, 1
0x140012475  jz      short loc_140012485
0x140012477  cmp     ecx, 1
0x14001247a  jnz     short loc_1400124DC
0x14001247c  mov     ecx, edi; this
0x14001247e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140012483  jmp     short loc_1400124DA
0x140012485  test    edi, edi
0x140012487  js      short loc_1400124C1
0x140012489  mov     edi, 8007029Ch
0x14001248e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140012492  mov     rax, [rsp+78h+arg_28]
0x14001249a  mov     [rsp+78h+var_50], rax; __int64
0x14001249f  mov     rax, [rsp+78h+arg_20]
0x1400124a7  mov     [rsp+78h+var_58], rax; __int64
0x1400124ac  mov     rcx, r10; int
0x1400124af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400124b4  mov     [rbx+8], edi
0x1400124b7  mov     ecx, edi; this
0x1400124b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400124be  mov     [rbx+0Ch], eax
0x1400124c1  mov     ecx, edi; this
0x1400124c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400124c8  jmp     short loc_1400124DA
0x1400124ca  mov     ecx, edi; this
0x1400124cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400124d1  jmp     short loc_1400124DA
0x1400124d3  mov     ecx, edi; this
0x1400124d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400124da  mov     ebp, eax
0x1400124dc  mov     [rbx], r15d
0x1400124df  mov     eax, [rsp+78h+arg_70]
0x1400124e6  mov     [rbx+4], eax
0x1400124e9  cmp     dword ptr [r14+8], 1
0x1400124ee  jnz     short loc_1400124F6
0x1400124f0  or      eax, 8
0x1400124f3  mov     [rbx+4], eax
0x1400124f6  mov     eax, 1
0x1400124fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140012503  inc     eax
0x140012505  mov     [rbx+10h], eax
0x140012508  mov     rax, [rsp+78h+arg_40]
0x140012510  xor     edi, edi
0x140012512  test    rax, rax
0x140012515  jz      short loc_14001251C
0x140012517  cmp     [rax], di
0x14001251a  jnz     short loc_14001251F
0x14001251c  mov     rax, rdi
0x14001251f  mov     [rbx+18h], rax
0x140012523  call    cs:__imp_GetCurrentThreadId
0x140012529  mov     [rbx+20h], eax
0x14001252c  mov     [rbx+38h], r13
0x140012530  mov     eax, [rsp+78h+arg_8]
0x140012537  mov     [rbx+40h], eax
0x14001253a  mov     [rbx+44h], ebp
0x14001253d  mov     rax, [rsp+78h+arg_20]
0x140012545  mov     [rbx+28h], rax
0x140012549  mov     [rbx+30h], r12
0x14001254d  mov     rax, [rsp+78h+arg_28]
0x140012555  mov     [rbx+88h], rax
0x14001255c  mov     rax, [rsp+78h+arg_0]
0x140012564  mov     [rbx+90h], rax
0x14001256b  mov     [rbx+48h], rdi
0x14001256f  xorps   xmm0, xmm0
0x140012572  xor     eax, eax
0x140012574  movups  xmmword ptr [rbx+68h], xmm0
0x140012578  mov     [rbx+78h], rax
0x14001257c  movups  xmmword ptr [rbx+50h], xmm0
0x140012580  mov     [rbx+60h], rax
0x140012584  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001258b  test    rax, rax
0x14001258e  jz      short loc_140012597
0x140012590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012595  jmp     short loc_14001259A
0x140012597  mov     rax, rdi
0x14001259a  mov     [rbx+80h], rax
0x1400125a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400125a8  test    rax, rax
0x1400125ab  jz      short loc_1400125B5
0x1400125ad  mov     rcx, rbx
0x1400125b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400125bc  test    rax, rax
0x1400125bf  jz      short loc_1400125D7
0x1400125c1  mov     r8d, 400h
0x1400125c7  mov     rdx, [rsp+78h+arg_60]
0x1400125cf  mov     rcx, rbx
0x1400125d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400125de  test    rax, rax
0x1400125e1  jz      short loc_1400125EB
0x1400125e3  mov     rcx, rbx
0x1400125e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400125f2  test    rax, rax
0x1400125f5  jz      short loc_140012605
0x1400125f7  test    byte ptr [rbx+4], 2
0x1400125fb  jnz     short loc_140012605
0x1400125fd  mov     rcx, rbx
0x140012600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012605  cmp     [rbx+8], edi
0x140012608  jl      short loc_140012624
0x14001260a  cmp     r15d, 3
0x14001260e  jnz     loc_1400126F3
0x140012614  mov     ecx, 8000FFFFh; this
0x140012619  mov     [rbx+8], ecx
0x14001261c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140012621  mov     [rbx+0Ch], eax
0x140012624  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14001262b  jnz     short loc_14001264C
0x14001262d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140012634  test    rax, rax
0x140012637  jz      short loc_140012642
0x140012639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001263e  test    al, al
0x140012640  jmp     short loc_14001264A
0x140012642  call    cs:__imp_IsDebuggerPresent
0x140012648  test    eax, eax
0x14001264a  jz      short loc_140012652
0x14001264c  test    byte ptr [rbx+4], 2
0x140012650  jz      short loc_140012676
0x140012652  mov     rax, cs:g_pfnResultLoggingCallback
0x140012659  test    rax, rax
0x14001265c  jz      short loc_1400126BA
0x14001265e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140012665  jnz     short loc_1400126BA
0x140012667  xor     r8d, r8d
0x14001266a  xor     edx, edx
0x14001266c  mov     rcx, rbx
0x14001266f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012674  jmp     short loc_1400126BA
0x140012676  mov     ebp, 800h
0x14001267b  mov     rax, cs:g_pfnResultLoggingCallback
0x140012682  test    rax, rax
0x140012685  jz      short loc_14001269E
0x140012687  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001268e  jnz     short loc_14001269E
0x140012690  mov     r8d, ebp
0x140012693  mov     rdx, rsi
0x140012696  mov     rcx, rbx
0x140012699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001269e  cmp     [rsi], di
0x1400126a1  jnz     short loc_1400126B1
0x1400126a3  mov     r8, rbx; unsigned __int64
0x1400126a6  mov     rdx, rbp; unsigned __int16 *
0x1400126a9  mov     rcx, rsi; this
0x1400126ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400126b1  mov     rcx, rsi; lpOutputString
0x1400126b4  call    cs:__imp_OutputDebugStringW
0x1400126ba  test    byte ptr [rbx+4], 4
0x1400126be  jnz     short loc_1400126C9
0x1400126c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400126c7  jz      short loc_1400126DB
0x1400126c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400126d0  test    rax, rax
0x1400126d3  jz      short loc_1400126DB
0x1400126d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126da  nop
0x1400126db  mov     rbx, [rsp+78h+arg_10]
0x1400126e3  add     rsp, 40h
0x1400126e7  pop     r15
0x1400126e9  pop     r14
0x1400126eb  pop     r13
0x1400126ed  pop     r12
0x1400126ef  pop     rdi
0x1400126f0  pop     rsi
0x1400126f1  pop     rbp
0x1400126f2  retn
0x1400126f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
