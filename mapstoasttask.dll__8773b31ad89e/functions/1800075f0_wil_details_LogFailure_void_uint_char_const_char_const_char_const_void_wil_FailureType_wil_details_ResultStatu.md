# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800075f0`
- end: `0x1800078e9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000730c`

## callees

- `0x180003b44`
- `0x180003f2c`
- `0x180004b40`
- `0x180006fe4`
- `0x1800075f0`
- `0x1800078f0`
- `0x18000790c`
- `0x180007928`
- `0x180007a6c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007713`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007713`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800078a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800078a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007832`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007832`

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
  wil::details::in1diag3 *v22; // rcx
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
0x1800075f0  mov     [rsp+arg_10], rbx
0x1800075f5  mov     [rsp+arg_8], edx
0x1800075f9  mov     [rsp+arg_0], rcx
0x1800075fe  push    rbp
0x1800075ff  push    rsi
0x180007600  push    rdi
0x180007601  push    r12
0x180007603  push    r13
0x180007605  push    r14
0x180007607  push    r15
0x180007609  sub     rsp, 40h
0x18000760d  mov     r12, r9
0x180007610  mov     r13, r8
0x180007613  mov     r10, rcx
0x180007616  xor     eax, eax
0x180007618  mov     rsi, [rsp+78h+lpOutputString]
0x180007620  mov     [rsi], ax
0x180007623  mov     rax, [rsp+78h+arg_60]
0x18000762b  mov     byte ptr [rax], 0
0x18000762e  mov     r14, [rsp+78h+arg_38]
0x180007636  mov     edi, [r14]
0x180007639  mov     rbx, [rsp+78h+arg_78]
0x180007641  mov     [rbx+8], edi
0x180007644  mov     eax, [r14+4]
0x180007648  mov     [rbx+0Ch], eax
0x18000764b  xor     ebp, ebp
0x18000764d  mov     r15d, [rsp+78h+arg_30]
0x180007655  mov     ecx, r15d
0x180007658  test    r15d, r15d
0x18000765b  jz      short loc_1800076C3
0x18000765d  sub     ecx, 1
0x180007660  jz      short loc_1800076BA
0x180007662  sub     ecx, 1
0x180007665  jz      short loc_180007675
0x180007667  cmp     ecx, 1
0x18000766a  jnz     short loc_1800076CC
0x18000766c  mov     ecx, edi; this
0x18000766e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007673  jmp     short loc_1800076CA
0x180007675  test    edi, edi
0x180007677  js      short loc_1800076B1
0x180007679  mov     edi, 8007029Ch
0x18000767e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007682  mov     rax, [rsp+78h+arg_28]
0x18000768a  mov     [rsp+78h+var_50], rax; __int64
0x18000768f  mov     rax, [rsp+78h+arg_20]
0x180007697  mov     [rsp+78h+var_58], rax; __int64
0x18000769c  mov     rcx, r10; int
0x18000769f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800076a4  mov     [rbx+8], edi
0x1800076a7  mov     ecx, edi; this
0x1800076a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800076ae  mov     [rbx+0Ch], eax
0x1800076b1  mov     ecx, edi; this
0x1800076b3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800076b8  jmp     short loc_1800076CA
0x1800076ba  mov     ecx, edi; this
0x1800076bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800076c1  jmp     short loc_1800076CA
0x1800076c3  mov     ecx, edi; this
0x1800076c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800076ca  mov     ebp, eax
0x1800076cc  mov     [rbx], r15d
0x1800076cf  mov     eax, [rsp+78h+arg_70]
0x1800076d6  mov     [rbx+4], eax
0x1800076d9  cmp     dword ptr [r14+8], 1
0x1800076de  jnz     short loc_1800076E6
0x1800076e0  or      eax, 8
0x1800076e3  mov     [rbx+4], eax
0x1800076e6  mov     eax, 1
0x1800076eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800076f3  inc     eax
0x1800076f5  mov     [rbx+10h], eax
0x1800076f8  mov     rax, [rsp+78h+arg_40]
0x180007700  xor     edi, edi
0x180007702  test    rax, rax
0x180007705  jz      short loc_18000770C
0x180007707  cmp     [rax], di
0x18000770a  jnz     short loc_18000770F
0x18000770c  mov     rax, rdi
0x18000770f  mov     [rbx+18h], rax
0x180007713  call    cs:__imp_GetCurrentThreadId
0x180007719  mov     [rbx+20h], eax
0x18000771c  mov     [rbx+38h], r13
0x180007720  mov     eax, [rsp+78h+arg_8]
0x180007727  mov     [rbx+40h], eax
0x18000772a  mov     [rbx+44h], ebp
0x18000772d  mov     rax, [rsp+78h+arg_20]
0x180007735  mov     [rbx+28h], rax
0x180007739  mov     [rbx+30h], r12
0x18000773d  mov     rax, [rsp+78h+arg_28]
0x180007745  mov     [rbx+88h], rax
0x18000774c  mov     rax, [rsp+78h+arg_0]
0x180007754  mov     [rbx+90h], rax
0x18000775b  mov     [rbx+48h], rdi
0x18000775f  xorps   xmm0, xmm0
0x180007762  xor     eax, eax
0x180007764  movups  xmmword ptr [rbx+68h], xmm0
0x180007768  mov     [rbx+78h], rax
0x18000776c  movups  xmmword ptr [rbx+50h], xmm0
0x180007770  mov     [rbx+60h], rax
0x180007774  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000777b  test    rax, rax
0x18000777e  jz      short loc_180007787
0x180007780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007785  jmp     short loc_18000778A
0x180007787  mov     rax, rdi
0x18000778a  mov     [rbx+80h], rax
0x180007791  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007798  test    rax, rax
0x18000779b  jz      short loc_1800077A5
0x18000779d  mov     rcx, rbx
0x1800077a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800077ac  test    rax, rax
0x1800077af  jz      short loc_1800077C7
0x1800077b1  mov     r8d, 400h
0x1800077b7  mov     rdx, [rsp+78h+arg_60]
0x1800077bf  mov     rcx, rbx
0x1800077c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800077ce  test    rax, rax
0x1800077d1  jz      short loc_1800077DB
0x1800077d3  mov     rcx, rbx
0x1800077d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800077e2  test    rax, rax
0x1800077e5  jz      short loc_1800077F5
0x1800077e7  test    byte ptr [rbx+4], 2
0x1800077eb  jnz     short loc_1800077F5
0x1800077ed  mov     rcx, rbx
0x1800077f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f5  cmp     [rbx+8], edi
0x1800077f8  jl      short loc_180007814
0x1800077fa  cmp     r15d, 3
0x1800077fe  jnz     loc_1800078E3
0x180007804  mov     ecx, 8000FFFFh; this
0x180007809  mov     [rbx+8], ecx
0x18000780c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007811  mov     [rbx+0Ch], eax
0x180007814  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000781b  jnz     short loc_18000783C
0x18000781d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007824  test    rax, rax
0x180007827  jz      short loc_180007832
0x180007829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782e  test    al, al
0x180007830  jmp     short loc_18000783A
0x180007832  call    cs:__imp_IsDebuggerPresent
0x180007838  test    eax, eax
0x18000783a  jz      short loc_180007842
0x18000783c  test    byte ptr [rbx+4], 2
0x180007840  jz      short loc_180007866
0x180007842  mov     rax, cs:g_pfnResultLoggingCallback
0x180007849  test    rax, rax
0x18000784c  jz      short loc_1800078AA
0x18000784e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007855  jnz     short loc_1800078AA
0x180007857  xor     r8d, r8d
0x18000785a  xor     edx, edx
0x18000785c  mov     rcx, rbx
0x18000785f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007864  jmp     short loc_1800078AA
0x180007866  mov     ebp, 800h
0x18000786b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007872  test    rax, rax
0x180007875  jz      short loc_18000788E
0x180007877  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000787e  jnz     short loc_18000788E
0x180007880  mov     r8d, ebp
0x180007883  mov     rdx, rsi
0x180007886  mov     rcx, rbx
0x180007889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000788e  cmp     [rsi], di
0x180007891  jnz     short loc_1800078A1
0x180007893  mov     r8, rbx; unsigned __int64
0x180007896  mov     rdx, rbp; unsigned __int16 *
0x180007899  mov     rcx, rsi; this
0x18000789c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800078a1  mov     rcx, rsi; lpOutputString
0x1800078a4  call    cs:__imp_OutputDebugStringW
0x1800078aa  test    byte ptr [rbx+4], 4
0x1800078ae  jnz     short loc_1800078B9
0x1800078b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800078b7  jz      short loc_1800078CB
0x1800078b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800078c0  test    rax, rax
0x1800078c3  jz      short loc_1800078CB
0x1800078c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ca  nop
0x1800078cb  mov     rbx, [rsp+78h+arg_10]
0x1800078d3  add     rsp, 40h
0x1800078d7  pop     r15
0x1800078d9  pop     r14
0x1800078db  pop     r13
0x1800078dd  pop     r12
0x1800078df  pop     rdi
0x1800078e0  pop     rsi
0x1800078e1  pop     rbp
0x1800078e2  retn
0x1800078e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
