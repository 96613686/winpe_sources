# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c830`
- end: `0x18000cb28`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b324`

## callees

- `0x18000ad60`
- `0x18000bed4`
- `0x18000c66c`
- `0x18000c830`
- `0x18000cd6c`
- `0x18000cd90`
- `0x18000cda4`
- `0x18000cdc0`
- `0x18000d71c`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c953`
- `KERNEL32!GetCurrentThreadId` at `0x18000c953`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ca72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ca72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cae4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cae4`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x18000c830  mov     [rsp+arg_10], rbx
0x18000c835  mov     [rsp+arg_8], edx
0x18000c839  mov     [rsp+arg_0], rcx
0x18000c83e  push    rbp
0x18000c83f  push    rsi
0x18000c840  push    rdi
0x18000c841  push    r12
0x18000c843  push    r13
0x18000c845  push    r14
0x18000c847  push    r15
0x18000c849  sub     rsp, 40h
0x18000c84d  mov     r14, [rsp+78h+arg_38]
0x18000c855  xor     eax, eax
0x18000c857  mov     rbx, [rsp+78h+arg_78]
0x18000c85f  xor     ebp, ebp
0x18000c861  mov     r15d, [rsp+78h+arg_30]
0x18000c869  mov     r10, rcx
0x18000c86c  mov     rsi, [rsp+78h+lpOutputString]
0x18000c874  mov     r12, r9
0x18000c877  mov     r13, r8
0x18000c87a  mov     ecx, r15d
0x18000c87d  mov     [rsi], ax
0x18000c880  mov     rax, [rsp+78h+arg_60]
0x18000c888  mov     byte ptr [rax], 0
0x18000c88b  mov     edi, [r14]
0x18000c88e  mov     [rbx+8], edi
0x18000c891  mov     eax, [r14+4]
0x18000c895  mov     [rbx+0Ch], eax
0x18000c898  test    r15d, r15d
0x18000c89b  jz      short loc_18000C903
0x18000c89d  sub     ecx, 1
0x18000c8a0  jz      short loc_18000C8FA
0x18000c8a2  sub     ecx, 1
0x18000c8a5  jz      short loc_18000C8B5
0x18000c8a7  cmp     ecx, 1
0x18000c8aa  jnz     short loc_18000C90C
0x18000c8ac  mov     ecx, edi; this
0x18000c8ae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c8b3  jmp     short loc_18000C90A
0x18000c8b5  test    edi, edi
0x18000c8b7  js      short loc_18000C8F1
0x18000c8b9  mov     rax, [rsp+78h+arg_28]
0x18000c8c1  mov     edi, 8007029Ch
0x18000c8c6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c8ca  mov     rcx, r10; int
0x18000c8cd  mov     [rsp+78h+var_50], rax; __int64
0x18000c8d2  mov     rax, [rsp+78h+arg_20]
0x18000c8da  mov     [rsp+78h+var_58], rax; __int64
0x18000c8df  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c8e4  mov     ecx, edi; this
0x18000c8e6  mov     [rbx+8], edi
0x18000c8e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c8ee  mov     [rbx+0Ch], eax
0x18000c8f1  mov     ecx, edi; this
0x18000c8f3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c8f8  jmp     short loc_18000C90A
0x18000c8fa  mov     ecx, edi; this
0x18000c8fc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c901  jmp     short loc_18000C90A
0x18000c903  mov     ecx, edi; this
0x18000c905  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c90a  mov     ebp, eax
0x18000c90c  mov     eax, [rsp+78h+arg_70]
0x18000c913  mov     [rbx+4], eax
0x18000c916  mov     [rbx], r15d
0x18000c919  cmp     dword ptr [r14+8], 1
0x18000c91e  jnz     short loc_18000C926
0x18000c920  or      eax, 8
0x18000c923  mov     [rbx+4], eax
0x18000c926  mov     eax, 1
0x18000c92b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c933  inc     eax
0x18000c935  xor     edi, edi
0x18000c937  mov     [rbx+10h], eax
0x18000c93a  mov     rax, [rsp+78h+arg_40]
0x18000c942  test    rax, rax
0x18000c945  jz      short loc_18000C94C
0x18000c947  cmp     [rax], di
0x18000c94a  jnz     short loc_18000C94F
0x18000c94c  mov     rax, rdi
0x18000c94f  mov     [rbx+18h], rax
0x18000c953  call    cs:__imp_GetCurrentThreadId
0x18000c959  mov     [rbx+38h], r13
0x18000c95d  xorps   xmm0, xmm0
0x18000c960  mov     [rbx+20h], eax
0x18000c963  mov     eax, [rsp+78h+arg_8]
0x18000c96a  mov     [rbx+40h], eax
0x18000c96d  mov     rax, [rsp+78h+arg_20]
0x18000c975  mov     [rbx+28h], rax
0x18000c979  mov     rax, [rsp+78h+arg_28]
0x18000c981  mov     [rbx+88h], rax
0x18000c988  mov     rax, [rsp+78h+arg_0]
0x18000c990  mov     [rbx+90h], rax
0x18000c997  xor     eax, eax
0x18000c999  mov     [rbx+44h], ebp
0x18000c99c  mov     [rbx+30h], r12
0x18000c9a0  mov     [rbx+48h], rdi
0x18000c9a4  movups  xmmword ptr [rbx+68h], xmm0
0x18000c9a8  mov     [rbx+78h], rax
0x18000c9ac  movups  xmmword ptr [rbx+50h], xmm0
0x18000c9b0  mov     [rbx+60h], rax
0x18000c9b4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c9bb  test    rax, rax
0x18000c9be  jz      short loc_18000C9C7
0x18000c9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9c5  jmp     short loc_18000C9CA
0x18000c9c7  mov     rax, rdi
0x18000c9ca  mov     [rbx+80h], rax
0x18000c9d1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c9d8  test    rax, rax
0x18000c9db  jz      short loc_18000C9E5
0x18000c9dd  mov     rcx, rbx
0x18000c9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c9ec  test    rax, rax
0x18000c9ef  jz      short loc_18000CA07
0x18000c9f1  mov     rdx, [rsp+78h+arg_60]
0x18000c9f9  mov     r8d, 400h
0x18000c9ff  mov     rcx, rbx
0x18000ca02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ca0e  test    rax, rax
0x18000ca11  jz      short loc_18000CA1B
0x18000ca13  mov     rcx, rbx
0x18000ca16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca1b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ca22  test    rax, rax
0x18000ca25  jz      short loc_18000CA35
0x18000ca27  test    byte ptr [rbx+4], 2
0x18000ca2b  jnz     short loc_18000CA35
0x18000ca2d  mov     rcx, rbx
0x18000ca30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca35  cmp     [rbx+8], edi
0x18000ca38  jl      short loc_18000CA54
0x18000ca3a  cmp     r15d, 3
0x18000ca3e  jnz     loc_18000CB22
0x18000ca44  mov     ecx, 8000FFFFh; this
0x18000ca49  mov     [rbx+8], ecx
0x18000ca4c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ca51  mov     [rbx+0Ch], eax
0x18000ca54  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000ca5b  jnz     short loc_18000CA7C
0x18000ca5d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ca64  test    rax, rax
0x18000ca67  jz      short loc_18000CA72
0x18000ca69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6e  test    al, al
0x18000ca70  jmp     short loc_18000CA7A
0x18000ca72  call    cs:__imp_IsDebuggerPresent
0x18000ca78  test    eax, eax
0x18000ca7a  jz      short loc_18000CA82
0x18000ca7c  test    byte ptr [rbx+4], 2
0x18000ca80  jz      short loc_18000CAA6
0x18000ca82  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ca89  test    rax, rax
0x18000ca8c  jz      short loc_18000CAEA
0x18000ca8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ca95  jnz     short loc_18000CAEA
0x18000ca97  xor     r8d, r8d
0x18000ca9a  xor     edx, edx
0x18000ca9c  mov     rcx, rbx
0x18000ca9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caa4  jmp     short loc_18000CAEA
0x18000caa6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000caad  mov     ebp, 800h
0x18000cab2  test    rax, rax
0x18000cab5  jz      short loc_18000CACE
0x18000cab7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cabe  jnz     short loc_18000CACE
0x18000cac0  mov     r8d, ebp
0x18000cac3  mov     rdx, rsi
0x18000cac6  mov     rcx, rbx
0x18000cac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cace  cmp     [rsi], di
0x18000cad1  jnz     short loc_18000CAE1
0x18000cad3  mov     r8, rbx; unsigned __int64
0x18000cad6  mov     rdx, rbp; unsigned __int16 *
0x18000cad9  mov     rcx, rsi; this
0x18000cadc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cae1  mov     rcx, rsi; lpOutputString
0x18000cae4  call    cs:__imp_OutputDebugStringW
0x18000caea  test    byte ptr [rbx+4], 4
0x18000caee  jnz     short loc_18000CAF9
0x18000caf0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000caf7  jz      short loc_18000CB0A
0x18000caf9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cb00  test    rax, rax
0x18000cb03  jz      short loc_18000CB0A
0x18000cb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb0a  mov     rbx, [rsp+78h+arg_10]
0x18000cb12  add     rsp, 40h
0x18000cb16  pop     r15
0x18000cb18  pop     r14
0x18000cb1a  pop     r13
0x18000cb1c  pop     r12
0x18000cb1e  pop     rdi
0x18000cb1f  pop     rsi
0x18000cb20  pop     rbp
0x18000cb21  retn
0x18000cb22  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
