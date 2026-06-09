# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013de4`
- end: `0x1800140d9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180011bbc`
- `0x180011c6c`
- `0x180011d60`

## callees

- `0x18000bca8`
- `0x180011b10`
- `0x180013294`
- `0x180013de4`
- `0x180014b8c`
- `0x180014bb0`
- `0x180014c6c`
- `0x180014c88`
- `0x1800166c8`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f07`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001409a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001409a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180014028`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180014028`

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
0x180013de4  mov     [rsp+arg_10], rbx
0x180013de9  mov     [rsp+arg_8], edx
0x180013ded  mov     [rsp+arg_0], rcx
0x180013df2  push    rbp
0x180013df3  push    rsi
0x180013df4  push    rdi
0x180013df5  push    r12
0x180013df7  push    r13
0x180013df9  push    r14
0x180013dfb  push    r15
0x180013dfd  sub     rsp, 40h
0x180013e01  mov     r12, r9
0x180013e04  mov     r13, r8
0x180013e07  mov     r10, rcx
0x180013e0a  xor     eax, eax
0x180013e0c  mov     rsi, [rsp+78h+lpOutputString]
0x180013e14  mov     [rsi], ax
0x180013e17  mov     rax, [rsp+78h+arg_60]
0x180013e1f  mov     byte ptr [rax], 0
0x180013e22  mov     r14, [rsp+78h+arg_38]
0x180013e2a  mov     edi, [r14]
0x180013e2d  mov     rbx, [rsp+78h+arg_78]
0x180013e35  mov     [rbx+8], edi
0x180013e38  mov     eax, [r14+4]
0x180013e3c  mov     [rbx+0Ch], eax
0x180013e3f  xor     ebp, ebp
0x180013e41  mov     r15d, [rsp+78h+arg_30]
0x180013e49  mov     ecx, r15d
0x180013e4c  test    r15d, r15d
0x180013e4f  jz      short loc_180013EB7
0x180013e51  sub     ecx, 1
0x180013e54  jz      short loc_180013EAE
0x180013e56  sub     ecx, 1
0x180013e59  jz      short loc_180013E69
0x180013e5b  cmp     ecx, 1
0x180013e5e  jnz     short loc_180013EC0
0x180013e60  mov     ecx, edi; this
0x180013e62  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013e67  jmp     short loc_180013EBE
0x180013e69  test    edi, edi
0x180013e6b  js      short loc_180013EA5
0x180013e6d  mov     edi, 8007029Ch
0x180013e72  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180013e76  mov     rax, [rsp+78h+arg_28]
0x180013e7e  mov     [rsp+78h+var_50], rax; __int64
0x180013e83  mov     rax, [rsp+78h+arg_20]
0x180013e8b  mov     [rsp+78h+var_58], rax; __int64
0x180013e90  mov     rcx, r10; int
0x180013e93  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013e98  mov     [rbx+8], edi
0x180013e9b  mov     ecx, edi; this
0x180013e9d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013ea2  mov     [rbx+0Ch], eax
0x180013ea5  mov     ecx, edi; this
0x180013ea7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013eac  jmp     short loc_180013EBE
0x180013eae  mov     ecx, edi; this
0x180013eb0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013eb5  jmp     short loc_180013EBE
0x180013eb7  mov     ecx, edi; this
0x180013eb9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013ebe  mov     ebp, eax
0x180013ec0  mov     [rbx], r15d
0x180013ec3  mov     eax, [rsp+78h+arg_70]
0x180013eca  mov     [rbx+4], eax
0x180013ecd  cmp     dword ptr [r14+8], 1
0x180013ed2  jnz     short loc_180013EDA
0x180013ed4  or      eax, 8
0x180013ed7  mov     [rbx+4], eax
0x180013eda  mov     eax, 1
0x180013edf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013ee7  inc     eax
0x180013ee9  mov     [rbx+10h], eax
0x180013eec  mov     rax, [rsp+78h+arg_40]
0x180013ef4  xor     edi, edi
0x180013ef6  test    rax, rax
0x180013ef9  jz      short loc_180013F00
0x180013efb  cmp     [rax], di
0x180013efe  jnz     short loc_180013F03
0x180013f00  mov     rax, rdi
0x180013f03  mov     [rbx+18h], rax
0x180013f07  call    cs:__imp_GetCurrentThreadId
0x180013f0d  mov     [rbx+20h], eax
0x180013f10  mov     [rbx+38h], r13
0x180013f14  mov     eax, [rsp+78h+arg_8]
0x180013f1b  mov     [rbx+40h], eax
0x180013f1e  mov     [rbx+44h], ebp
0x180013f21  mov     rax, [rsp+78h+arg_20]
0x180013f29  mov     [rbx+28h], rax
0x180013f2d  mov     [rbx+30h], r12
0x180013f31  mov     rax, [rsp+78h+arg_28]
0x180013f39  mov     [rbx+88h], rax
0x180013f40  mov     rax, [rsp+78h+arg_0]
0x180013f48  mov     [rbx+90h], rax
0x180013f4f  mov     [rbx+48h], rdi
0x180013f53  xorps   xmm0, xmm0
0x180013f56  xor     eax, eax
0x180013f58  movups  xmmword ptr [rbx+68h], xmm0
0x180013f5c  mov     [rbx+78h], rax
0x180013f60  movups  xmmword ptr [rbx+50h], xmm0
0x180013f64  mov     [rbx+60h], rax
0x180013f68  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013f6f  test    rax, rax
0x180013f72  jz      short loc_180013F7B
0x180013f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f79  jmp     short loc_180013F7E
0x180013f7b  mov     rax, rdi
0x180013f7e  mov     [rbx+80h], rax
0x180013f85  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013f8c  test    rax, rax
0x180013f8f  jz      short loc_180013F99
0x180013f91  mov     rcx, rbx
0x180013f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f99  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013fa0  test    rax, rax
0x180013fa3  jz      short loc_180013FBB
0x180013fa5  mov     r8d, 400h
0x180013fab  mov     rdx, [rsp+78h+arg_60]
0x180013fb3  mov     rcx, rbx
0x180013fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fbb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013fc2  test    rax, rax
0x180013fc5  jz      short loc_180013FCF
0x180013fc7  mov     rcx, rbx
0x180013fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fcf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013fd6  test    rax, rax
0x180013fd9  jz      short loc_180013FE9
0x180013fdb  test    byte ptr [rbx+4], 2
0x180013fdf  jnz     short loc_180013FE9
0x180013fe1  mov     rcx, rbx
0x180013fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe9  cmp     [rbx+8], edi
0x180013fec  jl      short loc_18001400A
0x180013fee  cmp     r15d, 3
0x180013ff2  jz      short loc_180013FFA
0x180013ff4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180013ffa  mov     ecx, 8000FFFFh; this
0x180013fff  mov     [rbx+8], ecx
0x180014002  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180014007  mov     [rbx+0Ch], eax
0x18001400a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180014011  jnz     short loc_180014032
0x180014013  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001401a  test    rax, rax
0x18001401d  jz      short loc_180014028
0x18001401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014024  test    al, al
0x180014026  jmp     short loc_180014030
0x180014028  call    cs:__imp_IsDebuggerPresent
0x18001402e  test    eax, eax
0x180014030  jz      short loc_180014038
0x180014032  test    byte ptr [rbx+4], 2
0x180014036  jz      short loc_18001405C
0x180014038  mov     rax, cs:g_pfnResultLoggingCallback
0x18001403f  test    rax, rax
0x180014042  jz      short loc_1800140A0
0x180014044  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001404b  jnz     short loc_1800140A0
0x18001404d  xor     r8d, r8d
0x180014050  xor     edx, edx
0x180014052  mov     rcx, rbx
0x180014055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001405a  jmp     short loc_1800140A0
0x18001405c  mov     ebp, 800h
0x180014061  mov     rax, cs:g_pfnResultLoggingCallback
0x180014068  test    rax, rax
0x18001406b  jz      short loc_180014084
0x18001406d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180014074  jnz     short loc_180014084
0x180014076  mov     r8d, ebp
0x180014079  mov     rdx, rsi
0x18001407c  mov     rcx, rbx
0x18001407f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014084  cmp     [rsi], di
0x180014087  jnz     short loc_180014097
0x180014089  mov     r8, rbx; unsigned __int64
0x18001408c  mov     rdx, rbp; unsigned __int16 *
0x18001408f  mov     rcx, rsi; this
0x180014092  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180014097  mov     rcx, rsi; lpOutputString
0x18001409a  call    cs:__imp_OutputDebugStringW
0x1800140a0  test    byte ptr [rbx+4], 4
0x1800140a4  jnz     short loc_1800140AF
0x1800140a6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800140ad  jz      short loc_1800140C1
0x1800140af  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800140b6  test    rax, rax
0x1800140b9  jz      short loc_1800140C1
0x1800140bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c0  nop
0x1800140c1  mov     rbx, [rsp+78h+arg_10]
0x1800140c9  add     rsp, 40h
0x1800140cd  pop     r15
0x1800140cf  pop     r14
0x1800140d1  pop     r13
0x1800140d3  pop     r12
0x1800140d5  pop     rdi
0x1800140d6  pop     rsi
0x1800140d7  pop     rbp
0x1800140d8  retn
```
