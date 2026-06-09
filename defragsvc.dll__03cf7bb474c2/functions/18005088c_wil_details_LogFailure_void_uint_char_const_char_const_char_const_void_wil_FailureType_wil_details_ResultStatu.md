# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005088c`
- end: `0x180050b80`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18004edfc`
- `0x18004eeac`
- `0x18004efa0`

## callees

- `0x18004144c`
- `0x18004ed50`
- `0x18004ff04`
- `0x18005088c`
- `0x180051338`
- `0x180051360`
- `0x18005141c`
- `0x180051438`
- `0x1800526dc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800509af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800509af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180050b42`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180050b42`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180050ad0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180050ad0`

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
0x18005088c  mov     [rsp+arg_10], rbx
0x180050891  mov     [rsp+arg_8], edx
0x180050895  mov     [rsp+arg_0], rcx
0x18005089a  push    rbp
0x18005089b  push    rsi
0x18005089c  push    rdi
0x18005089d  push    r12
0x18005089f  push    r13
0x1800508a1  push    r14
0x1800508a3  push    r15
0x1800508a5  sub     rsp, 40h
0x1800508a9  mov     r14, [rsp+78h+arg_38]
0x1800508b1  xor     eax, eax
0x1800508b3  mov     rbx, [rsp+78h+arg_78]
0x1800508bb  xor     ebp, ebp
0x1800508bd  mov     r15d, [rsp+78h+arg_30]
0x1800508c5  mov     r10, rcx
0x1800508c8  mov     rsi, [rsp+78h+lpOutputString]
0x1800508d0  mov     r12, r9
0x1800508d3  mov     r13, r8
0x1800508d6  mov     ecx, r15d
0x1800508d9  mov     [rsi], ax
0x1800508dc  mov     rax, [rsp+78h+arg_60]
0x1800508e4  mov     byte ptr [rax], 0
0x1800508e7  mov     edi, [r14]
0x1800508ea  mov     [rbx+8], edi
0x1800508ed  mov     eax, [r14+4]
0x1800508f1  mov     [rbx+0Ch], eax
0x1800508f4  test    r15d, r15d
0x1800508f7  jz      short loc_18005095F
0x1800508f9  sub     ecx, 1
0x1800508fc  jz      short loc_180050956
0x1800508fe  sub     ecx, 1
0x180050901  jz      short loc_180050911
0x180050903  cmp     ecx, 1
0x180050906  jnz     short loc_180050968
0x180050908  mov     ecx, edi; this
0x18005090a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005090f  jmp     short loc_180050966
0x180050911  test    edi, edi
0x180050913  js      short loc_18005094D
0x180050915  mov     rax, [rsp+78h+arg_28]
0x18005091d  mov     edi, 8007029Ch
0x180050922  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180050926  mov     rcx, r10; int
0x180050929  mov     [rsp+78h+var_50], rax; __int64
0x18005092e  mov     rax, [rsp+78h+arg_20]
0x180050936  mov     [rsp+78h+var_58], rax; __int64
0x18005093b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180050940  mov     ecx, edi; this
0x180050942  mov     [rbx+8], edi
0x180050945  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005094a  mov     [rbx+0Ch], eax
0x18005094d  mov     ecx, edi; this
0x18005094f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180050954  jmp     short loc_180050966
0x180050956  mov     ecx, edi; this
0x180050958  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005095d  jmp     short loc_180050966
0x18005095f  mov     ecx, edi; this
0x180050961  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180050966  mov     ebp, eax
0x180050968  mov     eax, [rsp+78h+arg_70]
0x18005096f  mov     [rbx+4], eax
0x180050972  mov     [rbx], r15d
0x180050975  cmp     dword ptr [r14+8], 1
0x18005097a  jnz     short loc_180050982
0x18005097c  or      eax, 8
0x18005097f  mov     [rbx+4], eax
0x180050982  mov     eax, 1
0x180050987  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005098f  inc     eax
0x180050991  xor     edi, edi
0x180050993  mov     [rbx+10h], eax
0x180050996  mov     rax, [rsp+78h+arg_40]
0x18005099e  test    rax, rax
0x1800509a1  jz      short loc_1800509A8
0x1800509a3  cmp     [rax], di
0x1800509a6  jnz     short loc_1800509AB
0x1800509a8  mov     rax, rdi
0x1800509ab  mov     [rbx+18h], rax
0x1800509af  call    cs:__imp_GetCurrentThreadId
0x1800509b5  mov     [rbx+38h], r13
0x1800509b9  xorps   xmm0, xmm0
0x1800509bc  mov     [rbx+20h], eax
0x1800509bf  mov     eax, [rsp+78h+arg_8]
0x1800509c6  mov     [rbx+40h], eax
0x1800509c9  mov     rax, [rsp+78h+arg_20]
0x1800509d1  mov     [rbx+28h], rax
0x1800509d5  mov     rax, [rsp+78h+arg_28]
0x1800509dd  mov     [rbx+88h], rax
0x1800509e4  mov     rax, [rsp+78h+arg_0]
0x1800509ec  mov     [rbx+90h], rax
0x1800509f3  xor     eax, eax
0x1800509f5  mov     [rbx+44h], ebp
0x1800509f8  mov     [rbx+30h], r12
0x1800509fc  mov     [rbx+48h], rdi
0x180050a00  movups  xmmword ptr [rbx+68h], xmm0
0x180050a04  mov     [rbx+78h], rax
0x180050a08  movups  xmmword ptr [rbx+50h], xmm0
0x180050a0c  mov     [rbx+60h], rax
0x180050a10  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180050a17  test    rax, rax
0x180050a1a  jz      short loc_180050A23
0x180050a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a21  jmp     short loc_180050A26
0x180050a23  mov     rax, rdi
0x180050a26  mov     [rbx+80h], rax
0x180050a2d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180050a34  test    rax, rax
0x180050a37  jz      short loc_180050A41
0x180050a39  mov     rcx, rbx
0x180050a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a41  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180050a48  test    rax, rax
0x180050a4b  jz      short loc_180050A63
0x180050a4d  mov     rdx, [rsp+78h+arg_60]
0x180050a55  mov     r8d, 400h
0x180050a5b  mov     rcx, rbx
0x180050a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a63  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180050a6a  test    rax, rax
0x180050a6d  jz      short loc_180050A77
0x180050a6f  mov     rcx, rbx
0x180050a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a77  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180050a7e  test    rax, rax
0x180050a81  jz      short loc_180050A91
0x180050a83  test    byte ptr [rbx+4], 2
0x180050a87  jnz     short loc_180050A91
0x180050a89  mov     rcx, rbx
0x180050a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a91  cmp     [rbx+8], edi
0x180050a94  jl      short loc_180050AB2
0x180050a96  cmp     r15d, 3
0x180050a9a  jz      short loc_180050AA2
0x180050a9c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180050aa2  mov     ecx, 8000FFFFh; this
0x180050aa7  mov     [rbx+8], ecx
0x180050aaa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180050aaf  mov     [rbx+0Ch], eax
0x180050ab2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180050ab9  jnz     short loc_180050ADA
0x180050abb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180050ac2  test    rax, rax
0x180050ac5  jz      short loc_180050AD0
0x180050ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050acc  test    al, al
0x180050ace  jmp     short loc_180050AD8
0x180050ad0  call    cs:__imp_IsDebuggerPresent
0x180050ad6  test    eax, eax
0x180050ad8  jz      short loc_180050AE0
0x180050ada  test    byte ptr [rbx+4], 2
0x180050ade  jz      short loc_180050B04
0x180050ae0  mov     rax, cs:g_pfnResultLoggingCallback
0x180050ae7  test    rax, rax
0x180050aea  jz      short loc_180050B48
0x180050aec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180050af3  jnz     short loc_180050B48
0x180050af5  xor     r8d, r8d
0x180050af8  xor     edx, edx
0x180050afa  mov     rcx, rbx
0x180050afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b02  jmp     short loc_180050B48
0x180050b04  mov     rax, cs:g_pfnResultLoggingCallback
0x180050b0b  mov     ebp, 800h
0x180050b10  test    rax, rax
0x180050b13  jz      short loc_180050B2C
0x180050b15  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180050b1c  jnz     short loc_180050B2C
0x180050b1e  mov     r8d, ebp
0x180050b21  mov     rdx, rsi
0x180050b24  mov     rcx, rbx
0x180050b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b2c  cmp     [rsi], di
0x180050b2f  jnz     short loc_180050B3F
0x180050b31  mov     r8, rbx; unsigned __int64
0x180050b34  mov     rdx, rbp; unsigned __int16 *
0x180050b37  mov     rcx, rsi; this
0x180050b3a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180050b3f  mov     rcx, rsi; lpOutputString
0x180050b42  call    cs:__imp_OutputDebugStringW
0x180050b48  test    byte ptr [rbx+4], 4
0x180050b4c  jnz     short loc_180050B57
0x180050b4e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180050b55  jz      short loc_180050B68
0x180050b57  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180050b5e  test    rax, rax
0x180050b61  jz      short loc_180050B68
0x180050b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b68  mov     rbx, [rsp+78h+arg_10]
0x180050b70  add     rsp, 40h
0x180050b74  pop     r15
0x180050b76  pop     r14
0x180050b78  pop     r13
0x180050b7a  pop     r12
0x180050b7c  pop     rdi
0x180050b7d  pop     rsi
0x180050b7e  pop     rbp
0x180050b7f  retn
```
