# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140007b00`
- end: `0x140007df9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003d70`

## callees

- `0x1400034b0`
- `0x140006c94`
- `0x1400074e4`
- `0x140007b00`
- `0x14000ab34`
- `0x14000ab50`
- `0x14000ab64`
- `0x14000ab80`
- `0x14000bc1c`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007c23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007c23`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007db4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007db4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007d42`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007d42`

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
0x140007b00  mov     [rsp+arg_10], rbx
0x140007b05  mov     [rsp+arg_8], edx
0x140007b09  mov     [rsp+arg_0], rcx
0x140007b0e  push    rbp
0x140007b0f  push    rsi
0x140007b10  push    rdi
0x140007b11  push    r12
0x140007b13  push    r13
0x140007b15  push    r14
0x140007b17  push    r15
0x140007b19  sub     rsp, 40h
0x140007b1d  mov     r12, r9
0x140007b20  mov     r13, r8
0x140007b23  mov     r10, rcx
0x140007b26  xor     eax, eax
0x140007b28  mov     rsi, [rsp+78h+lpOutputString]
0x140007b30  mov     [rsi], ax
0x140007b33  mov     rax, [rsp+78h+arg_60]
0x140007b3b  mov     byte ptr [rax], 0
0x140007b3e  mov     r14, [rsp+78h+arg_38]
0x140007b46  mov     edi, [r14]
0x140007b49  mov     rbx, [rsp+78h+arg_78]
0x140007b51  mov     [rbx+8], edi
0x140007b54  mov     eax, [r14+4]
0x140007b58  mov     [rbx+0Ch], eax
0x140007b5b  xor     ebp, ebp
0x140007b5d  mov     r15d, [rsp+78h+arg_30]
0x140007b65  mov     ecx, r15d
0x140007b68  test    r15d, r15d
0x140007b6b  jz      short loc_140007BD3
0x140007b6d  sub     ecx, 1
0x140007b70  jz      short loc_140007BCA
0x140007b72  sub     ecx, 1
0x140007b75  jz      short loc_140007B85
0x140007b77  cmp     ecx, 1
0x140007b7a  jnz     short loc_140007BDC
0x140007b7c  mov     ecx, edi; this
0x140007b7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007b83  jmp     short loc_140007BDA
0x140007b85  test    edi, edi
0x140007b87  js      short loc_140007BC1
0x140007b89  mov     edi, 8007029Ch
0x140007b8e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140007b92  mov     rax, [rsp+78h+arg_28]
0x140007b9a  mov     [rsp+78h+var_50], rax; __int64
0x140007b9f  mov     rax, [rsp+78h+arg_20]
0x140007ba7  mov     [rsp+78h+var_58], rax; __int64
0x140007bac  mov     rcx, r10; int
0x140007baf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007bb4  mov     [rbx+8], edi
0x140007bb7  mov     ecx, edi; this
0x140007bb9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007bbe  mov     [rbx+0Ch], eax
0x140007bc1  mov     ecx, edi; this
0x140007bc3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007bc8  jmp     short loc_140007BDA
0x140007bca  mov     ecx, edi; this
0x140007bcc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007bd1  jmp     short loc_140007BDA
0x140007bd3  mov     ecx, edi; this
0x140007bd5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140007bda  mov     ebp, eax
0x140007bdc  mov     [rbx], r15d
0x140007bdf  mov     eax, [rsp+78h+arg_70]
0x140007be6  mov     [rbx+4], eax
0x140007be9  cmp     dword ptr [r14+8], 1
0x140007bee  jnz     short loc_140007BF6
0x140007bf0  or      eax, 8
0x140007bf3  mov     [rbx+4], eax
0x140007bf6  mov     eax, 1
0x140007bfb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007c03  inc     eax
0x140007c05  mov     [rbx+10h], eax
0x140007c08  mov     rax, [rsp+78h+arg_40]
0x140007c10  xor     edi, edi
0x140007c12  test    rax, rax
0x140007c15  jz      short loc_140007C1C
0x140007c17  cmp     [rax], di
0x140007c1a  jnz     short loc_140007C1F
0x140007c1c  mov     rax, rdi
0x140007c1f  mov     [rbx+18h], rax
0x140007c23  call    cs:__imp_GetCurrentThreadId
0x140007c29  mov     [rbx+20h], eax
0x140007c2c  mov     [rbx+38h], r13
0x140007c30  mov     eax, [rsp+78h+arg_8]
0x140007c37  mov     [rbx+40h], eax
0x140007c3a  mov     [rbx+44h], ebp
0x140007c3d  mov     rax, [rsp+78h+arg_20]
0x140007c45  mov     [rbx+28h], rax
0x140007c49  mov     [rbx+30h], r12
0x140007c4d  mov     rax, [rsp+78h+arg_28]
0x140007c55  mov     [rbx+88h], rax
0x140007c5c  mov     rax, [rsp+78h+arg_0]
0x140007c64  mov     [rbx+90h], rax
0x140007c6b  mov     [rbx+48h], rdi
0x140007c6f  xorps   xmm0, xmm0
0x140007c72  xor     eax, eax
0x140007c74  movups  xmmword ptr [rbx+68h], xmm0
0x140007c78  mov     [rbx+78h], rax
0x140007c7c  movups  xmmword ptr [rbx+50h], xmm0
0x140007c80  mov     [rbx+60h], rax
0x140007c84  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007c8b  test    rax, rax
0x140007c8e  jz      short loc_140007C97
0x140007c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c95  jmp     short loc_140007C9A
0x140007c97  mov     rax, rdi
0x140007c9a  mov     [rbx+80h], rax
0x140007ca1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007ca8  test    rax, rax
0x140007cab  jz      short loc_140007CB5
0x140007cad  mov     rcx, rbx
0x140007cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cb5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007cbc  test    rax, rax
0x140007cbf  jz      short loc_140007CD7
0x140007cc1  mov     r8d, 400h
0x140007cc7  mov     rdx, [rsp+78h+arg_60]
0x140007ccf  mov     rcx, rbx
0x140007cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cd7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007cde  test    rax, rax
0x140007ce1  jz      short loc_140007CEB
0x140007ce3  mov     rcx, rbx
0x140007ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ceb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007cf2  test    rax, rax
0x140007cf5  jz      short loc_140007D05
0x140007cf7  test    byte ptr [rbx+4], 2
0x140007cfb  jnz     short loc_140007D05
0x140007cfd  mov     rcx, rbx
0x140007d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d05  cmp     [rbx+8], edi
0x140007d08  jl      short loc_140007D24
0x140007d0a  cmp     r15d, 3
0x140007d0e  jnz     loc_140007DF3
0x140007d14  mov     ecx, 8000FFFFh; this
0x140007d19  mov     [rbx+8], ecx
0x140007d1c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007d21  mov     [rbx+0Ch], eax
0x140007d24  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007d2b  jnz     short loc_140007D4C
0x140007d2d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007d34  test    rax, rax
0x140007d37  jz      short loc_140007D42
0x140007d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d3e  test    al, al
0x140007d40  jmp     short loc_140007D4A
0x140007d42  call    cs:__imp_IsDebuggerPresent
0x140007d48  test    eax, eax
0x140007d4a  jz      short loc_140007D52
0x140007d4c  test    byte ptr [rbx+4], 2
0x140007d50  jz      short loc_140007D76
0x140007d52  mov     rax, cs:g_pfnResultLoggingCallback
0x140007d59  test    rax, rax
0x140007d5c  jz      short loc_140007DBA
0x140007d5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007d65  jnz     short loc_140007DBA
0x140007d67  xor     r8d, r8d
0x140007d6a  xor     edx, edx
0x140007d6c  mov     rcx, rbx
0x140007d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d74  jmp     short loc_140007DBA
0x140007d76  mov     ebp, 800h
0x140007d7b  mov     rax, cs:g_pfnResultLoggingCallback
0x140007d82  test    rax, rax
0x140007d85  jz      short loc_140007D9E
0x140007d87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007d8e  jnz     short loc_140007D9E
0x140007d90  mov     r8d, ebp
0x140007d93  mov     rdx, rsi
0x140007d96  mov     rcx, rbx
0x140007d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d9e  cmp     [rsi], di
0x140007da1  jnz     short loc_140007DB1
0x140007da3  mov     r8, rbx; unsigned __int64
0x140007da6  mov     rdx, rbp; unsigned __int16 *
0x140007da9  mov     rcx, rsi; this
0x140007dac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007db1  mov     rcx, rsi; lpOutputString
0x140007db4  call    cs:__imp_OutputDebugStringW
0x140007dba  test    byte ptr [rbx+4], 4
0x140007dbe  jnz     short loc_140007DC9
0x140007dc0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007dc7  jz      short loc_140007DDB
0x140007dc9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007dd0  test    rax, rax
0x140007dd3  jz      short loc_140007DDB
0x140007dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dda  nop
0x140007ddb  mov     rbx, [rsp+78h+arg_10]
0x140007de3  add     rsp, 40h
0x140007de7  pop     r15
0x140007de9  pop     r14
0x140007deb  pop     r13
0x140007ded  pop     r12
0x140007def  pop     rdi
0x140007df0  pop     rsi
0x140007df1  pop     rbp
0x140007df2  retn
0x140007df3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
