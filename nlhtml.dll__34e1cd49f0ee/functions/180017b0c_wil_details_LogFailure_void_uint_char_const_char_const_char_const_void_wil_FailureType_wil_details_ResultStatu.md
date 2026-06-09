# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180017b0c`
- end: `0x180017e05`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180012f94`
- `0x180015544`
- `0x1800158b0`

## callees

- `0x18001316c`
- `0x18001547c`
- `0x180017124`
- `0x180017b0c`
- `0x18001890c`
- `0x180018930`
- `0x180018ab4`
- `0x180018ad0`
- `0x18001a580`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017c2f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017dc0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017dc0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180017d4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180017d4e`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180017b0c  mov     [rsp+arg_10], rbx
0x180017b11  mov     [rsp+arg_8], edx
0x180017b15  mov     [rsp+arg_0], rcx
0x180017b1a  push    rbp
0x180017b1b  push    rsi
0x180017b1c  push    rdi
0x180017b1d  push    r12
0x180017b1f  push    r13
0x180017b21  push    r14
0x180017b23  push    r15
0x180017b25  sub     rsp, 40h
0x180017b29  mov     r12, r9
0x180017b2c  mov     r13, r8
0x180017b2f  mov     r10, rcx
0x180017b32  xor     eax, eax
0x180017b34  mov     rsi, [rsp+78h+lpOutputString]
0x180017b3c  mov     [rsi], ax
0x180017b3f  mov     rax, [rsp+78h+arg_60]
0x180017b47  mov     byte ptr [rax], 0
0x180017b4a  mov     r14, [rsp+78h+arg_38]
0x180017b52  mov     edi, [r14]
0x180017b55  mov     rbx, [rsp+78h+arg_78]
0x180017b5d  mov     [rbx+8], edi
0x180017b60  mov     eax, [r14+4]
0x180017b64  mov     [rbx+0Ch], eax
0x180017b67  xor     ebp, ebp
0x180017b69  mov     r15d, [rsp+78h+arg_30]
0x180017b71  mov     ecx, r15d
0x180017b74  test    r15d, r15d
0x180017b77  jz      short loc_180017BDF
0x180017b79  sub     ecx, 1
0x180017b7c  jz      short loc_180017BD6
0x180017b7e  sub     ecx, 1
0x180017b81  jz      short loc_180017B91
0x180017b83  cmp     ecx, 1
0x180017b86  jnz     short loc_180017BE8
0x180017b88  mov     ecx, edi; this
0x180017b8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180017b8f  jmp     short loc_180017BE6
0x180017b91  test    edi, edi
0x180017b93  js      short loc_180017BCD
0x180017b95  mov     edi, 8007029Ch
0x180017b9a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180017b9e  mov     rax, [rsp+78h+arg_28]
0x180017ba6  mov     [rsp+78h+var_50], rax; __int64
0x180017bab  mov     rax, [rsp+78h+arg_20]
0x180017bb3  mov     [rsp+78h+var_58], rax; __int64
0x180017bb8  mov     rcx, r10; int
0x180017bbb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180017bc0  mov     [rbx+8], edi
0x180017bc3  mov     ecx, edi; this
0x180017bc5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180017bca  mov     [rbx+0Ch], eax
0x180017bcd  mov     ecx, edi; this
0x180017bcf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180017bd4  jmp     short loc_180017BE6
0x180017bd6  mov     ecx, edi; this
0x180017bd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180017bdd  jmp     short loc_180017BE6
0x180017bdf  mov     ecx, edi; this
0x180017be1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180017be6  mov     ebp, eax
0x180017be8  mov     [rbx], r15d
0x180017beb  mov     eax, [rsp+78h+arg_70]
0x180017bf2  mov     [rbx+4], eax
0x180017bf5  cmp     dword ptr [r14+8], 1
0x180017bfa  jnz     short loc_180017C02
0x180017bfc  or      eax, 8
0x180017bff  mov     [rbx+4], eax
0x180017c02  mov     eax, 1
0x180017c07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180017c0f  inc     eax
0x180017c11  mov     [rbx+10h], eax
0x180017c14  mov     rax, [rsp+78h+arg_40]
0x180017c1c  xor     edi, edi
0x180017c1e  test    rax, rax
0x180017c21  jz      short loc_180017C28
0x180017c23  cmp     [rax], di
0x180017c26  jnz     short loc_180017C2B
0x180017c28  mov     rax, rdi
0x180017c2b  mov     [rbx+18h], rax
0x180017c2f  call    cs:__imp_GetCurrentThreadId
0x180017c35  mov     [rbx+20h], eax
0x180017c38  mov     [rbx+38h], r13
0x180017c3c  mov     eax, [rsp+78h+arg_8]
0x180017c43  mov     [rbx+40h], eax
0x180017c46  mov     [rbx+44h], ebp
0x180017c49  mov     rax, [rsp+78h+arg_20]
0x180017c51  mov     [rbx+28h], rax
0x180017c55  mov     [rbx+30h], r12
0x180017c59  mov     rax, [rsp+78h+arg_28]
0x180017c61  mov     [rbx+88h], rax
0x180017c68  mov     rax, [rsp+78h+arg_0]
0x180017c70  mov     [rbx+90h], rax
0x180017c77  mov     [rbx+48h], rdi
0x180017c7b  xorps   xmm0, xmm0
0x180017c7e  xor     eax, eax
0x180017c80  movups  xmmword ptr [rbx+68h], xmm0
0x180017c84  mov     [rbx+78h], rax
0x180017c88  movups  xmmword ptr [rbx+50h], xmm0
0x180017c8c  mov     [rbx+60h], rax
0x180017c90  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180017c97  test    rax, rax
0x180017c9a  jz      short loc_180017CA3
0x180017c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca1  jmp     short loc_180017CA6
0x180017ca3  mov     rax, rdi
0x180017ca6  mov     [rbx+80h], rax
0x180017cad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180017cb4  test    rax, rax
0x180017cb7  jz      short loc_180017CC1
0x180017cb9  mov     rcx, rbx
0x180017cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180017cc8  test    rax, rax
0x180017ccb  jz      short loc_180017CE3
0x180017ccd  mov     r8d, 400h
0x180017cd3  mov     rdx, [rsp+78h+arg_60]
0x180017cdb  mov     rcx, rbx
0x180017cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017cea  test    rax, rax
0x180017ced  jz      short loc_180017CF7
0x180017cef  mov     rcx, rbx
0x180017cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017cfe  test    rax, rax
0x180017d01  jz      short loc_180017D11
0x180017d03  test    byte ptr [rbx+4], 2
0x180017d07  jnz     short loc_180017D11
0x180017d09  mov     rcx, rbx
0x180017d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d11  cmp     [rbx+8], edi
0x180017d14  jl      short loc_180017D30
0x180017d16  cmp     r15d, 3
0x180017d1a  jnz     loc_180017DFF
0x180017d20  mov     ecx, 8000FFFFh; this
0x180017d25  mov     [rbx+8], ecx
0x180017d28  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180017d2d  mov     [rbx+0Ch], eax
0x180017d30  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180017d37  jnz     short loc_180017D58
0x180017d39  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180017d40  test    rax, rax
0x180017d43  jz      short loc_180017D4E
0x180017d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d4a  test    al, al
0x180017d4c  jmp     short loc_180017D56
0x180017d4e  call    cs:__imp_IsDebuggerPresent
0x180017d54  test    eax, eax
0x180017d56  jz      short loc_180017D5E
0x180017d58  test    byte ptr [rbx+4], 2
0x180017d5c  jz      short loc_180017D82
0x180017d5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180017d65  test    rax, rax
0x180017d68  jz      short loc_180017DC6
0x180017d6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180017d71  jnz     short loc_180017DC6
0x180017d73  xor     r8d, r8d
0x180017d76  xor     edx, edx
0x180017d78  mov     rcx, rbx
0x180017d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d80  jmp     short loc_180017DC6
0x180017d82  mov     ebp, 800h
0x180017d87  mov     rax, cs:g_pfnResultLoggingCallback
0x180017d8e  test    rax, rax
0x180017d91  jz      short loc_180017DAA
0x180017d93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180017d9a  jnz     short loc_180017DAA
0x180017d9c  mov     r8d, ebp
0x180017d9f  mov     rdx, rsi
0x180017da2  mov     rcx, rbx
0x180017da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017daa  cmp     [rsi], di
0x180017dad  jnz     short loc_180017DBD
0x180017daf  mov     r8, rbx; unsigned __int64
0x180017db2  mov     rdx, rbp; wchar_t *
0x180017db5  mov     rcx, rsi; this
0x180017db8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180017dbd  mov     rcx, rsi; lpOutputString
0x180017dc0  call    cs:__imp_OutputDebugStringW
0x180017dc6  test    byte ptr [rbx+4], 4
0x180017dca  jnz     short loc_180017DD5
0x180017dcc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180017dd3  jz      short loc_180017DE7
0x180017dd5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180017ddc  test    rax, rax
0x180017ddf  jz      short loc_180017DE7
0x180017de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017de6  nop
0x180017de7  mov     rbx, [rsp+78h+arg_10]
0x180017def  add     rsp, 40h
0x180017df3  pop     r15
0x180017df5  pop     r14
0x180017df7  pop     r13
0x180017df9  pop     r12
0x180017dfb  pop     rdi
0x180017dfc  pop     rsi
0x180017dfd  pop     rbp
0x180017dfe  retn
0x180017dff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
