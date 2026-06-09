# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007688`
- end: `0x18000798a`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `770`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800052f0`
- `0x180005670`

## callees

- `0x180003bc0`
- `0x180005098`
- `0x180006d54`
- `0x180007688`
- `0x180008488`
- `0x1800084b0`
- `0x180008574`
- `0x180008590`
- `0x180009e10`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077ab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800078ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800078ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007921`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007921`

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
  _WORD *v21; // rax
  wil::details::in1diag5 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
      wil::details::in1diag5::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
    || !wil::g_fResultOutputDebugString
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
0x180007688  mov     [rsp+arg_10], rbx
0x18000768d  mov     [rsp+arg_8], edx
0x180007691  mov     [rsp+arg_0], rcx
0x180007696  push    rbp
0x180007697  push    rsi
0x180007698  push    rdi
0x180007699  push    r12
0x18000769b  push    r13
0x18000769d  push    r14
0x18000769f  push    r15
0x1800076a1  sub     rsp, 40h
0x1800076a5  mov     r12, r9
0x1800076a8  mov     r13, r8
0x1800076ab  mov     r10, rcx
0x1800076ae  xor     eax, eax
0x1800076b0  mov     rsi, [rsp+78h+lpOutputString]
0x1800076b8  mov     [rsi], ax
0x1800076bb  mov     rax, [rsp+78h+arg_60]
0x1800076c3  mov     byte ptr [rax], 0
0x1800076c6  mov     r14, [rsp+78h+arg_38]
0x1800076ce  mov     edi, [r14]
0x1800076d1  mov     rbx, [rsp+78h+arg_78]
0x1800076d9  mov     [rbx+8], edi
0x1800076dc  mov     eax, [r14+4]
0x1800076e0  mov     [rbx+0Ch], eax
0x1800076e3  xor     ebp, ebp
0x1800076e5  mov     r15d, [rsp+78h+arg_30]
0x1800076ed  mov     ecx, r15d
0x1800076f0  test    r15d, r15d
0x1800076f3  jz      short loc_18000775B
0x1800076f5  sub     ecx, 1
0x1800076f8  jz      short loc_180007752
0x1800076fa  sub     ecx, 1
0x1800076fd  jz      short loc_18000770D
0x1800076ff  cmp     ecx, 1
0x180007702  jnz     short loc_180007764
0x180007704  mov     ecx, edi; this
0x180007706  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000770b  jmp     short loc_180007762
0x18000770d  test    edi, edi
0x18000770f  js      short loc_180007749
0x180007711  mov     edi, 8007029Ch
0x180007716  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000771a  mov     rax, [rsp+78h+arg_28]
0x180007722  mov     [rsp+78h+var_50], rax; __int64
0x180007727  mov     rax, [rsp+78h+arg_20]
0x18000772f  mov     [rsp+78h+var_58], rax; __int64
0x180007734  mov     rcx, r10; int
0x180007737  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000773c  mov     [rbx+8], edi
0x18000773f  mov     ecx, edi; this
0x180007741  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007746  mov     [rbx+0Ch], eax
0x180007749  mov     ecx, edi; this
0x18000774b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007750  jmp     short loc_180007762
0x180007752  mov     ecx, edi; this
0x180007754  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007759  jmp     short loc_180007762
0x18000775b  mov     ecx, edi; this
0x18000775d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007762  mov     ebp, eax
0x180007764  mov     [rbx], r15d
0x180007767  mov     eax, [rsp+78h+arg_70]
0x18000776e  mov     [rbx+4], eax
0x180007771  cmp     dword ptr [r14+8], 1
0x180007776  jnz     short loc_18000777E
0x180007778  or      eax, 8
0x18000777b  mov     [rbx+4], eax
0x18000777e  mov     eax, 1
0x180007783  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000778b  inc     eax
0x18000778d  mov     [rbx+10h], eax
0x180007790  mov     rax, [rsp+78h+arg_40]
0x180007798  xor     edi, edi
0x18000779a  test    rax, rax
0x18000779d  jz      short loc_1800077A4
0x18000779f  cmp     [rax], di
0x1800077a2  jnz     short loc_1800077A7
0x1800077a4  mov     rax, rdi
0x1800077a7  mov     [rbx+18h], rax
0x1800077ab  call    cs:__imp_GetCurrentThreadId
0x1800077b1  mov     [rbx+20h], eax
0x1800077b4  mov     [rbx+38h], r13
0x1800077b8  mov     eax, [rsp+78h+arg_8]
0x1800077bf  mov     [rbx+40h], eax
0x1800077c2  mov     [rbx+44h], ebp
0x1800077c5  mov     rax, [rsp+78h+arg_20]
0x1800077cd  mov     [rbx+28h], rax
0x1800077d1  mov     [rbx+30h], r12
0x1800077d5  mov     rax, [rsp+78h+arg_28]
0x1800077dd  mov     [rbx+88h], rax
0x1800077e4  mov     rax, [rsp+78h+arg_0]
0x1800077ec  mov     [rbx+90h], rax
0x1800077f3  mov     [rbx+48h], rdi
0x1800077f7  xorps   xmm0, xmm0
0x1800077fa  xor     eax, eax
0x1800077fc  movups  xmmword ptr [rbx+68h], xmm0
0x180007800  mov     [rbx+78h], rax
0x180007804  movups  xmmword ptr [rbx+50h], xmm0
0x180007808  mov     [rbx+60h], rax
0x18000780c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007813  test    rax, rax
0x180007816  jz      short loc_18000781F
0x180007818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781d  jmp     short loc_180007822
0x18000781f  mov     rax, rdi
0x180007822  mov     [rbx+80h], rax
0x180007829  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007830  test    rax, rax
0x180007833  jz      short loc_18000783D
0x180007835  mov     rcx, rbx
0x180007838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000783d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007844  test    rax, rax
0x180007847  jz      short loc_18000785F
0x180007849  mov     r8d, 400h
0x18000784f  mov     rdx, [rsp+78h+arg_60]
0x180007857  mov     rcx, rbx
0x18000785a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007866  test    rax, rax
0x180007869  jz      short loc_180007873
0x18000786b  mov     rcx, rbx
0x18000786e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007873  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000787a  test    rax, rax
0x18000787d  jz      short loc_18000788D
0x18000787f  test    byte ptr [rbx+4], 2
0x180007883  jnz     short loc_18000788D
0x180007885  mov     rcx, rbx
0x180007888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000788d  cmp     [rbx+8], edi
0x180007890  jl      short loc_1800078AC
0x180007892  cmp     r15d, 3
0x180007896  jnz     loc_180007984
0x18000789c  mov     ecx, 8000FFFFh; this
0x1800078a1  mov     [rbx+8], ecx
0x1800078a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800078a9  mov     [rbx+0Ch], eax
0x1800078ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800078b3  jnz     short loc_1800078D4
0x1800078b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800078bc  test    rax, rax
0x1800078bf  jz      short loc_1800078CA
0x1800078c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c6  test    al, al
0x1800078c8  jmp     short loc_1800078D2
0x1800078ca  call    cs:__imp_IsDebuggerPresent
0x1800078d0  test    eax, eax
0x1800078d2  jz      short loc_180007929
0x1800078d4  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, dil; bool wil::g_fResultOutputDebugString
0x1800078db  jz      short loc_180007929
0x1800078dd  test    byte ptr [rbx+4], 2
0x1800078e1  jnz     short loc_180007929
0x1800078e3  mov     ebp, 800h
0x1800078e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800078ef  test    rax, rax
0x1800078f2  jz      short loc_18000790B
0x1800078f4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800078fb  jnz     short loc_18000790B
0x1800078fd  mov     r8d, ebp
0x180007900  mov     rdx, rsi
0x180007903  mov     rcx, rbx
0x180007906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000790b  cmp     [rsi], di
0x18000790e  jnz     short loc_18000791E
0x180007910  mov     r8, rbx; unsigned __int64
0x180007913  mov     rdx, rbp; unsigned __int16 *
0x180007916  mov     rcx, rsi; this
0x180007919  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000791e  mov     rcx, rsi; lpOutputString
0x180007921  call    cs:__imp_OutputDebugStringW
0x180007927  jmp     short loc_18000794B
0x180007929  mov     rax, cs:g_pfnResultLoggingCallback
0x180007930  test    rax, rax
0x180007933  jz      short loc_18000794B
0x180007935  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000793c  jnz     short loc_18000794B
0x18000793e  xor     r8d, r8d
0x180007941  xor     edx, edx
0x180007943  mov     rcx, rbx
0x180007946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000794b  test    byte ptr [rbx+4], 4
0x18000794f  jnz     short loc_18000795A
0x180007951  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007958  jz      short loc_18000796C
0x18000795a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007961  test    rax, rax
0x180007964  jz      short loc_18000796C
0x180007966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000796b  nop
0x18000796c  mov     rbx, [rsp+78h+arg_10]
0x180007974  add     rsp, 40h
0x180007978  pop     r15
0x18000797a  pop     r14
0x18000797c  pop     r13
0x18000797e  pop     r12
0x180007980  pop     rdi
0x180007981  pop     rsi
0x180007982  pop     rbp
0x180007983  retn
0x180007984  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
```
