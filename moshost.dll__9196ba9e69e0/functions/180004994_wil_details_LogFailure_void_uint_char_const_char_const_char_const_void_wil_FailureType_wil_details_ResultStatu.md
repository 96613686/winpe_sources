# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004994`
- end: `0x180004c8d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003194`

## callees

- `0x180002bd0`
- `0x180004034`
- `0x1800047d0`
- `0x180004994`
- `0x180004f14`
- `0x180004f30`
- `0x180004f44`
- `0x180004f60`
- `0x18000608c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ab7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bd6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c48`

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
0x180004994  mov     [rsp+arg_10], rbx
0x180004999  mov     [rsp+arg_8], edx
0x18000499d  mov     [rsp+arg_0], rcx
0x1800049a2  push    rbp
0x1800049a3  push    rsi
0x1800049a4  push    rdi
0x1800049a5  push    r12
0x1800049a7  push    r13
0x1800049a9  push    r14
0x1800049ab  push    r15
0x1800049ad  sub     rsp, 40h
0x1800049b1  mov     r12, r9
0x1800049b4  mov     r13, r8
0x1800049b7  mov     r10, rcx
0x1800049ba  xor     eax, eax
0x1800049bc  mov     rsi, [rsp+78h+lpOutputString]
0x1800049c4  mov     [rsi], ax
0x1800049c7  mov     rax, [rsp+78h+arg_60]
0x1800049cf  mov     byte ptr [rax], 0
0x1800049d2  mov     r14, [rsp+78h+arg_38]
0x1800049da  mov     edi, [r14]
0x1800049dd  mov     rbx, [rsp+78h+arg_78]
0x1800049e5  mov     [rbx+8], edi
0x1800049e8  mov     eax, [r14+4]
0x1800049ec  mov     [rbx+0Ch], eax
0x1800049ef  xor     ebp, ebp
0x1800049f1  mov     r15d, [rsp+78h+arg_30]
0x1800049f9  mov     ecx, r15d
0x1800049fc  test    r15d, r15d
0x1800049ff  jz      short loc_180004A67
0x180004a01  sub     ecx, 1
0x180004a04  jz      short loc_180004A5E
0x180004a06  sub     ecx, 1
0x180004a09  jz      short loc_180004A19
0x180004a0b  cmp     ecx, 1
0x180004a0e  jnz     short loc_180004A70
0x180004a10  mov     ecx, edi; this
0x180004a12  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004a17  jmp     short loc_180004A6E
0x180004a19  test    edi, edi
0x180004a1b  js      short loc_180004A55
0x180004a1d  mov     edi, 8007029Ch
0x180004a22  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004a26  mov     rax, [rsp+78h+arg_28]
0x180004a2e  mov     [rsp+78h+var_50], rax; __int64
0x180004a33  mov     rax, [rsp+78h+arg_20]
0x180004a3b  mov     [rsp+78h+var_58], rax; __int64
0x180004a40  mov     rcx, r10; int
0x180004a43  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004a48  mov     [rbx+8], edi
0x180004a4b  mov     ecx, edi; this
0x180004a4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004a52  mov     [rbx+0Ch], eax
0x180004a55  mov     ecx, edi; this
0x180004a57  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004a5c  jmp     short loc_180004A6E
0x180004a5e  mov     ecx, edi; this
0x180004a60  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a65  jmp     short loc_180004A6E
0x180004a67  mov     ecx, edi; this
0x180004a69  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004a6e  mov     ebp, eax
0x180004a70  mov     [rbx], r15d
0x180004a73  mov     eax, [rsp+78h+arg_70]
0x180004a7a  mov     [rbx+4], eax
0x180004a7d  cmp     dword ptr [r14+8], 1
0x180004a82  jnz     short loc_180004A8A
0x180004a84  or      eax, 8
0x180004a87  mov     [rbx+4], eax
0x180004a8a  mov     eax, 1
0x180004a8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a97  inc     eax
0x180004a99  mov     [rbx+10h], eax
0x180004a9c  mov     rax, [rsp+78h+arg_40]
0x180004aa4  xor     edi, edi
0x180004aa6  test    rax, rax
0x180004aa9  jz      short loc_180004AB0
0x180004aab  cmp     [rax], di
0x180004aae  jnz     short loc_180004AB3
0x180004ab0  mov     rax, rdi
0x180004ab3  mov     [rbx+18h], rax
0x180004ab7  call    cs:__imp_GetCurrentThreadId
0x180004abd  mov     [rbx+20h], eax
0x180004ac0  mov     [rbx+38h], r13
0x180004ac4  mov     eax, [rsp+78h+arg_8]
0x180004acb  mov     [rbx+40h], eax
0x180004ace  mov     [rbx+44h], ebp
0x180004ad1  mov     rax, [rsp+78h+arg_20]
0x180004ad9  mov     [rbx+28h], rax
0x180004add  mov     [rbx+30h], r12
0x180004ae1  mov     rax, [rsp+78h+arg_28]
0x180004ae9  mov     [rbx+88h], rax
0x180004af0  mov     rax, [rsp+78h+arg_0]
0x180004af8  mov     [rbx+90h], rax
0x180004aff  mov     [rbx+48h], rdi
0x180004b03  xorps   xmm0, xmm0
0x180004b06  xor     eax, eax
0x180004b08  movups  xmmword ptr [rbx+68h], xmm0
0x180004b0c  mov     [rbx+78h], rax
0x180004b10  movups  xmmword ptr [rbx+50h], xmm0
0x180004b14  mov     [rbx+60h], rax
0x180004b18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b1f  test    rax, rax
0x180004b22  jz      short loc_180004B2B
0x180004b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b29  jmp     short loc_180004B2E
0x180004b2b  mov     rax, rdi
0x180004b2e  mov     [rbx+80h], rax
0x180004b35  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b3c  test    rax, rax
0x180004b3f  jz      short loc_180004B49
0x180004b41  mov     rcx, rbx
0x180004b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b50  test    rax, rax
0x180004b53  jz      short loc_180004B6B
0x180004b55  mov     r8d, 400h
0x180004b5b  mov     rdx, [rsp+78h+arg_60]
0x180004b63  mov     rcx, rbx
0x180004b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b72  test    rax, rax
0x180004b75  jz      short loc_180004B7F
0x180004b77  mov     rcx, rbx
0x180004b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b86  test    rax, rax
0x180004b89  jz      short loc_180004B99
0x180004b8b  test    byte ptr [rbx+4], 2
0x180004b8f  jnz     short loc_180004B99
0x180004b91  mov     rcx, rbx
0x180004b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b99  cmp     [rbx+8], edi
0x180004b9c  jl      short loc_180004BB8
0x180004b9e  cmp     r15d, 3
0x180004ba2  jnz     loc_180004C87
0x180004ba8  mov     ecx, 8000FFFFh; this
0x180004bad  mov     [rbx+8], ecx
0x180004bb0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004bb5  mov     [rbx+0Ch], eax
0x180004bb8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004bbf  jnz     short loc_180004BE0
0x180004bc1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bc8  test    rax, rax
0x180004bcb  jz      short loc_180004BD6
0x180004bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd2  test    al, al
0x180004bd4  jmp     short loc_180004BDE
0x180004bd6  call    cs:__imp_IsDebuggerPresent
0x180004bdc  test    eax, eax
0x180004bde  jz      short loc_180004BE6
0x180004be0  test    byte ptr [rbx+4], 2
0x180004be4  jz      short loc_180004C0A
0x180004be6  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bed  test    rax, rax
0x180004bf0  jz      short loc_180004C4E
0x180004bf2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004bf9  jnz     short loc_180004C4E
0x180004bfb  xor     r8d, r8d
0x180004bfe  xor     edx, edx
0x180004c00  mov     rcx, rbx
0x180004c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c08  jmp     short loc_180004C4E
0x180004c0a  mov     ebp, 800h
0x180004c0f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c16  test    rax, rax
0x180004c19  jz      short loc_180004C32
0x180004c1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004c22  jnz     short loc_180004C32
0x180004c24  mov     r8d, ebp
0x180004c27  mov     rdx, rsi
0x180004c2a  mov     rcx, rbx
0x180004c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c32  cmp     [rsi], di
0x180004c35  jnz     short loc_180004C45
0x180004c37  mov     r8, rbx; unsigned __int64
0x180004c3a  mov     rdx, rbp; unsigned __int16 *
0x180004c3d  mov     rcx, rsi; this
0x180004c40  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c45  mov     rcx, rsi; lpOutputString
0x180004c48  call    cs:__imp_OutputDebugStringW
0x180004c4e  test    byte ptr [rbx+4], 4
0x180004c52  jnz     short loc_180004C5D
0x180004c54  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004c5b  jz      short loc_180004C6F
0x180004c5d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c64  test    rax, rax
0x180004c67  jz      short loc_180004C6F
0x180004c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c6e  nop
0x180004c6f  mov     rbx, [rsp+78h+arg_10]
0x180004c77  add     rsp, 40h
0x180004c7b  pop     r15
0x180004c7d  pop     r14
0x180004c7f  pop     r13
0x180004c81  pop     r12
0x180004c83  pop     rdi
0x180004c84  pop     rsi
0x180004c85  pop     rbp
0x180004c86  retn
0x180004c87  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
