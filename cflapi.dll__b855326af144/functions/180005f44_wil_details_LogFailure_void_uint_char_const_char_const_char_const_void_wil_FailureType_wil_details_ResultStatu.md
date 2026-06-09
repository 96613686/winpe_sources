# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005f44`
- end: `0x18000623d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004590`

## callees

- `0x180003f9c`
- `0x180005534`
- `0x180005d80`
- `0x180005f44`
- `0x1800064c4`
- `0x1800064e0`
- `0x1800064f4`
- `0x180006510`
- `0x180007798`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006067`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006067`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006186`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006186`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x180005f44  mov     [rsp+arg_10], rbx
0x180005f49  mov     [rsp+arg_8], edx
0x180005f4d  mov     [rsp+arg_0], rcx
0x180005f52  push    rbp
0x180005f53  push    rsi
0x180005f54  push    rdi
0x180005f55  push    r12
0x180005f57  push    r13
0x180005f59  push    r14
0x180005f5b  push    r15
0x180005f5d  sub     rsp, 40h
0x180005f61  mov     r12, r9
0x180005f64  mov     r13, r8
0x180005f67  mov     r10, rcx
0x180005f6a  xor     eax, eax
0x180005f6c  mov     rsi, [rsp+78h+lpOutputString]
0x180005f74  mov     [rsi], ax
0x180005f77  mov     rax, [rsp+78h+arg_60]
0x180005f7f  mov     byte ptr [rax], 0
0x180005f82  mov     r14, [rsp+78h+arg_38]
0x180005f8a  mov     edi, [r14]
0x180005f8d  mov     rbx, [rsp+78h+arg_78]
0x180005f95  mov     [rbx+8], edi
0x180005f98  mov     eax, [r14+4]
0x180005f9c  mov     [rbx+0Ch], eax
0x180005f9f  xor     ebp, ebp
0x180005fa1  mov     r15d, [rsp+78h+arg_30]
0x180005fa9  mov     ecx, r15d
0x180005fac  test    r15d, r15d
0x180005faf  jz      short loc_180006017
0x180005fb1  sub     ecx, 1
0x180005fb4  jz      short loc_18000600E
0x180005fb6  sub     ecx, 1
0x180005fb9  jz      short loc_180005FC9
0x180005fbb  cmp     ecx, 1
0x180005fbe  jnz     short loc_180006020
0x180005fc0  mov     ecx, edi; this
0x180005fc2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005fc7  jmp     short loc_18000601E
0x180005fc9  test    edi, edi
0x180005fcb  js      short loc_180006005
0x180005fcd  mov     edi, 8007029Ch
0x180005fd2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005fd6  mov     rax, [rsp+78h+arg_28]
0x180005fde  mov     [rsp+78h+var_50], rax; __int64
0x180005fe3  mov     rax, [rsp+78h+arg_20]
0x180005feb  mov     [rsp+78h+var_58], rax; __int64
0x180005ff0  mov     rcx, r10; int
0x180005ff3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005ff8  mov     [rbx+8], edi
0x180005ffb  mov     ecx, edi; this
0x180005ffd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006002  mov     [rbx+0Ch], eax
0x180006005  mov     ecx, edi; this
0x180006007  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000600c  jmp     short loc_18000601E
0x18000600e  mov     ecx, edi; this
0x180006010  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006015  jmp     short loc_18000601E
0x180006017  mov     ecx, edi; this
0x180006019  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000601e  mov     ebp, eax
0x180006020  mov     [rbx], r15d
0x180006023  mov     eax, [rsp+78h+arg_70]
0x18000602a  mov     [rbx+4], eax
0x18000602d  cmp     dword ptr [r14+8], 1
0x180006032  jnz     short loc_18000603A
0x180006034  or      eax, 8
0x180006037  mov     [rbx+4], eax
0x18000603a  mov     eax, 1
0x18000603f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006047  inc     eax
0x180006049  mov     [rbx+10h], eax
0x18000604c  mov     rax, [rsp+78h+arg_40]
0x180006054  xor     edi, edi
0x180006056  test    rax, rax
0x180006059  jz      short loc_180006060
0x18000605b  cmp     [rax], di
0x18000605e  jnz     short loc_180006063
0x180006060  mov     rax, rdi
0x180006063  mov     [rbx+18h], rax
0x180006067  call    cs:__imp_GetCurrentThreadId
0x18000606d  mov     [rbx+20h], eax
0x180006070  mov     [rbx+38h], r13
0x180006074  mov     eax, [rsp+78h+arg_8]
0x18000607b  mov     [rbx+40h], eax
0x18000607e  mov     [rbx+44h], ebp
0x180006081  mov     rax, [rsp+78h+arg_20]
0x180006089  mov     [rbx+28h], rax
0x18000608d  mov     [rbx+30h], r12
0x180006091  mov     rax, [rsp+78h+arg_28]
0x180006099  mov     [rbx+88h], rax
0x1800060a0  mov     rax, [rsp+78h+arg_0]
0x1800060a8  mov     [rbx+90h], rax
0x1800060af  mov     [rbx+48h], rdi
0x1800060b3  xorps   xmm0, xmm0
0x1800060b6  xor     eax, eax
0x1800060b8  movups  xmmword ptr [rbx+68h], xmm0
0x1800060bc  mov     [rbx+78h], rax
0x1800060c0  movups  xmmword ptr [rbx+50h], xmm0
0x1800060c4  mov     [rbx+60h], rax
0x1800060c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800060cf  test    rax, rax
0x1800060d2  jz      short loc_1800060DB
0x1800060d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d9  jmp     short loc_1800060DE
0x1800060db  mov     rax, rdi
0x1800060de  mov     [rbx+80h], rax
0x1800060e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800060ec  test    rax, rax
0x1800060ef  jz      short loc_1800060F9
0x1800060f1  mov     rcx, rbx
0x1800060f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006100  test    rax, rax
0x180006103  jz      short loc_18000611B
0x180006105  mov     r8d, 400h
0x18000610b  mov     rdx, [rsp+78h+arg_60]
0x180006113  mov     rcx, rbx
0x180006116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006122  test    rax, rax
0x180006125  jz      short loc_18000612F
0x180006127  mov     rcx, rbx
0x18000612a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006136  test    rax, rax
0x180006139  jz      short loc_180006149
0x18000613b  test    byte ptr [rbx+4], 2
0x18000613f  jnz     short loc_180006149
0x180006141  mov     rcx, rbx
0x180006144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006149  cmp     [rbx+8], edi
0x18000614c  jl      short loc_180006168
0x18000614e  cmp     r15d, 3
0x180006152  jnz     loc_180006237
0x180006158  mov     ecx, 8000FFFFh; this
0x18000615d  mov     [rbx+8], ecx
0x180006160  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006165  mov     [rbx+0Ch], eax
0x180006168  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000616f  jnz     short loc_180006190
0x180006171  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006178  test    rax, rax
0x18000617b  jz      short loc_180006186
0x18000617d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006182  test    al, al
0x180006184  jmp     short loc_18000618E
0x180006186  call    cs:__imp_IsDebuggerPresent
0x18000618c  test    eax, eax
0x18000618e  jz      short loc_180006196
0x180006190  test    byte ptr [rbx+4], 2
0x180006194  jz      short loc_1800061BA
0x180006196  mov     rax, cs:g_pfnResultLoggingCallback
0x18000619d  test    rax, rax
0x1800061a0  jz      short loc_1800061FE
0x1800061a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800061a9  jnz     short loc_1800061FE
0x1800061ab  xor     r8d, r8d
0x1800061ae  xor     edx, edx
0x1800061b0  mov     rcx, rbx
0x1800061b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b8  jmp     short loc_1800061FE
0x1800061ba  mov     ebp, 800h
0x1800061bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800061c6  test    rax, rax
0x1800061c9  jz      short loc_1800061E2
0x1800061cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800061d2  jnz     short loc_1800061E2
0x1800061d4  mov     r8d, ebp
0x1800061d7  mov     rdx, rsi
0x1800061da  mov     rcx, rbx
0x1800061dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e2  cmp     [rsi], di
0x1800061e5  jnz     short loc_1800061F5
0x1800061e7  mov     r8, rbx; unsigned __int64
0x1800061ea  mov     rdx, rbp; unsigned __int16 *
0x1800061ed  mov     rcx, rsi; this
0x1800061f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800061f5  mov     rcx, rsi; lpOutputString
0x1800061f8  call    cs:__imp_OutputDebugStringW
0x1800061fe  test    byte ptr [rbx+4], 4
0x180006202  jnz     short loc_18000620D
0x180006204  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000620b  jz      short loc_18000621F
0x18000620d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006214  test    rax, rax
0x180006217  jz      short loc_18000621F
0x180006219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000621e  nop
0x18000621f  mov     rbx, [rsp+78h+arg_10]
0x180006227  add     rsp, 40h
0x18000622b  pop     r15
0x18000622d  pop     r14
0x18000622f  pop     r13
0x180006231  pop     r12
0x180006233  pop     rdi
0x180006234  pop     rsi
0x180006235  pop     rbp
0x180006236  retn
0x180006237  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
