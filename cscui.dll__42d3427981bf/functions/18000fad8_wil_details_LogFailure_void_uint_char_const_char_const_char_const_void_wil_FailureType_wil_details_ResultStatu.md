# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000fad8`
- end: `0x18000fdd0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000e724`
- `0x18000ea70`

## callees

- `0x18000a7c0`
- `0x18000e664`
- `0x18000f3e4`
- `0x18000fad8`
- `0x18000ff84`
- `0x18000ffa0`
- `0x18000ffb4`
- `0x18000ffd0`
- `0x180010928`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fd8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000fd8c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fd1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000fd1a`

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
0x18000fad8  mov     [rsp+arg_10], rbx
0x18000fadd  mov     [rsp+arg_8], edx
0x18000fae1  mov     [rsp+arg_0], rcx
0x18000fae6  push    rbp
0x18000fae7  push    rsi
0x18000fae8  push    rdi
0x18000fae9  push    r12
0x18000faeb  push    r13
0x18000faed  push    r14
0x18000faef  push    r15
0x18000faf1  sub     rsp, 40h
0x18000faf5  mov     r14, [rsp+78h+arg_38]
0x18000fafd  xor     eax, eax
0x18000faff  mov     rbx, [rsp+78h+arg_78]
0x18000fb07  xor     ebp, ebp
0x18000fb09  mov     r15d, [rsp+78h+arg_30]
0x18000fb11  mov     r10, rcx
0x18000fb14  mov     rsi, [rsp+78h+lpOutputString]
0x18000fb1c  mov     r12, r9
0x18000fb1f  mov     r13, r8
0x18000fb22  mov     ecx, r15d
0x18000fb25  mov     [rsi], ax
0x18000fb28  mov     rax, [rsp+78h+arg_60]
0x18000fb30  mov     byte ptr [rax], 0
0x18000fb33  mov     edi, [r14]
0x18000fb36  mov     [rbx+8], edi
0x18000fb39  mov     eax, [r14+4]
0x18000fb3d  mov     [rbx+0Ch], eax
0x18000fb40  test    r15d, r15d
0x18000fb43  jz      short loc_18000FBAB
0x18000fb45  sub     ecx, 1
0x18000fb48  jz      short loc_18000FBA2
0x18000fb4a  sub     ecx, 1
0x18000fb4d  jz      short loc_18000FB5D
0x18000fb4f  cmp     ecx, 1
0x18000fb52  jnz     short loc_18000FBB4
0x18000fb54  mov     ecx, edi; this
0x18000fb56  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000fb5b  jmp     short loc_18000FBB2
0x18000fb5d  test    edi, edi
0x18000fb5f  js      short loc_18000FB99
0x18000fb61  mov     rax, [rsp+78h+arg_28]
0x18000fb69  mov     edi, 8007029Ch
0x18000fb6e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000fb72  mov     rcx, r10; int
0x18000fb75  mov     [rsp+78h+var_50], rax; __int64
0x18000fb7a  mov     rax, [rsp+78h+arg_20]
0x18000fb82  mov     [rsp+78h+var_58], rax; __int64
0x18000fb87  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000fb8c  mov     ecx, edi; this
0x18000fb8e  mov     [rbx+8], edi
0x18000fb91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fb96  mov     [rbx+0Ch], eax
0x18000fb99  mov     ecx, edi; this
0x18000fb9b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000fba0  jmp     short loc_18000FBB2
0x18000fba2  mov     ecx, edi; this
0x18000fba4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000fba9  jmp     short loc_18000FBB2
0x18000fbab  mov     ecx, edi; this
0x18000fbad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000fbb2  mov     ebp, eax
0x18000fbb4  mov     eax, [rsp+78h+arg_70]
0x18000fbbb  mov     [rbx+4], eax
0x18000fbbe  mov     [rbx], r15d
0x18000fbc1  cmp     dword ptr [r14+8], 1
0x18000fbc6  jnz     short loc_18000FBCE
0x18000fbc8  or      eax, 8
0x18000fbcb  mov     [rbx+4], eax
0x18000fbce  mov     eax, 1
0x18000fbd3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000fbdb  inc     eax
0x18000fbdd  xor     edi, edi
0x18000fbdf  mov     [rbx+10h], eax
0x18000fbe2  mov     rax, [rsp+78h+arg_40]
0x18000fbea  test    rax, rax
0x18000fbed  jz      short loc_18000FBF4
0x18000fbef  cmp     [rax], di
0x18000fbf2  jnz     short loc_18000FBF7
0x18000fbf4  mov     rax, rdi
0x18000fbf7  mov     [rbx+18h], rax
0x18000fbfb  call    cs:__imp_GetCurrentThreadId
0x18000fc01  mov     [rbx+38h], r13
0x18000fc05  xorps   xmm0, xmm0
0x18000fc08  mov     [rbx+20h], eax
0x18000fc0b  mov     eax, [rsp+78h+arg_8]
0x18000fc12  mov     [rbx+40h], eax
0x18000fc15  mov     rax, [rsp+78h+arg_20]
0x18000fc1d  mov     [rbx+28h], rax
0x18000fc21  mov     rax, [rsp+78h+arg_28]
0x18000fc29  mov     [rbx+88h], rax
0x18000fc30  mov     rax, [rsp+78h+arg_0]
0x18000fc38  mov     [rbx+90h], rax
0x18000fc3f  xor     eax, eax
0x18000fc41  mov     [rbx+44h], ebp
0x18000fc44  mov     [rbx+30h], r12
0x18000fc48  mov     [rbx+48h], rdi
0x18000fc4c  movups  xmmword ptr [rbx+68h], xmm0
0x18000fc50  mov     [rbx+78h], rax
0x18000fc54  movups  xmmword ptr [rbx+50h], xmm0
0x18000fc58  mov     [rbx+60h], rax
0x18000fc5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000fc63  test    rax, rax
0x18000fc66  jz      short loc_18000FC6F
0x18000fc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc6d  jmp     short loc_18000FC72
0x18000fc6f  mov     rax, rdi
0x18000fc72  mov     [rbx+80h], rax
0x18000fc79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fc80  test    rax, rax
0x18000fc83  jz      short loc_18000FC8D
0x18000fc85  mov     rcx, rbx
0x18000fc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fc94  test    rax, rax
0x18000fc97  jz      short loc_18000FCAF
0x18000fc99  mov     rdx, [rsp+78h+arg_60]
0x18000fca1  mov     r8d, 400h
0x18000fca7  mov     rcx, rbx
0x18000fcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcaf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fcb6  test    rax, rax
0x18000fcb9  jz      short loc_18000FCC3
0x18000fcbb  mov     rcx, rbx
0x18000fcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcc3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fcca  test    rax, rax
0x18000fccd  jz      short loc_18000FCDD
0x18000fccf  test    byte ptr [rbx+4], 2
0x18000fcd3  jnz     short loc_18000FCDD
0x18000fcd5  mov     rcx, rbx
0x18000fcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcdd  cmp     [rbx+8], edi
0x18000fce0  jl      short loc_18000FCFC
0x18000fce2  cmp     r15d, 3
0x18000fce6  jnz     loc_18000FDCA
0x18000fcec  mov     ecx, 8000FFFFh; this
0x18000fcf1  mov     [rbx+8], ecx
0x18000fcf4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fcf9  mov     [rbx+0Ch], eax
0x18000fcfc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000fd03  jnz     short loc_18000FD24
0x18000fd05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000fd0c  test    rax, rax
0x18000fd0f  jz      short loc_18000FD1A
0x18000fd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd16  test    al, al
0x18000fd18  jmp     short loc_18000FD22
0x18000fd1a  call    cs:__imp_IsDebuggerPresent
0x18000fd20  test    eax, eax
0x18000fd22  jz      short loc_18000FD2A
0x18000fd24  test    byte ptr [rbx+4], 2
0x18000fd28  jz      short loc_18000FD4E
0x18000fd2a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fd31  test    rax, rax
0x18000fd34  jz      short loc_18000FD92
0x18000fd36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000fd3d  jnz     short loc_18000FD92
0x18000fd3f  xor     r8d, r8d
0x18000fd42  xor     edx, edx
0x18000fd44  mov     rcx, rbx
0x18000fd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd4c  jmp     short loc_18000FD92
0x18000fd4e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fd55  mov     ebp, 800h
0x18000fd5a  test    rax, rax
0x18000fd5d  jz      short loc_18000FD76
0x18000fd5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000fd66  jnz     short loc_18000FD76
0x18000fd68  mov     r8d, ebp
0x18000fd6b  mov     rdx, rsi
0x18000fd6e  mov     rcx, rbx
0x18000fd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd76  cmp     [rsi], di
0x18000fd79  jnz     short loc_18000FD89
0x18000fd7b  mov     r8, rbx; unsigned __int64
0x18000fd7e  mov     rdx, rbp; unsigned __int16 *
0x18000fd81  mov     rcx, rsi; this
0x18000fd84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000fd89  mov     rcx, rsi; lpOutputString
0x18000fd8c  call    cs:__imp_OutputDebugStringW
0x18000fd92  test    byte ptr [rbx+4], 4
0x18000fd96  jnz     short loc_18000FDA1
0x18000fd98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000fd9f  jz      short loc_18000FDB2
0x18000fda1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000fda8  test    rax, rax
0x18000fdab  jz      short loc_18000FDB2
0x18000fdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb2  mov     rbx, [rsp+78h+arg_10]
0x18000fdba  add     rsp, 40h
0x18000fdbe  pop     r15
0x18000fdc0  pop     r14
0x18000fdc2  pop     r13
0x18000fdc4  pop     r12
0x18000fdc6  pop     rdi
0x18000fdc7  pop     rsi
0x18000fdc8  pop     rbp
0x18000fdc9  retn
0x18000fdca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
