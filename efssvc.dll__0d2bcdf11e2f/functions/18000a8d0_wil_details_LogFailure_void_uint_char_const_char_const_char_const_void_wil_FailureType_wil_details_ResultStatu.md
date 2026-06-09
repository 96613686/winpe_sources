# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a8d0`
- end: `0x18000abdb`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000970c`

## callees

- `0x180002b70`
- `0x180009124`
- `0x18000a03c`
- `0x18000a70c`
- `0x18000a8d0`
- `0x18000afec`
- `0x18000b00c`
- `0x18000b02c`
- `0x18000bd5c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ab18`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ab18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab90`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a9f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a9f3`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18000a8d0  mov     [rsp+arg_10], rbx
0x18000a8d5  mov     [rsp+arg_8], edx
0x18000a8d9  mov     [rsp+arg_0], rcx
0x18000a8de  push    rbp
0x18000a8df  push    rsi
0x18000a8e0  push    rdi
0x18000a8e1  push    r12
0x18000a8e3  push    r13
0x18000a8e5  push    r14
0x18000a8e7  push    r15
0x18000a8e9  sub     rsp, 40h
0x18000a8ed  mov     r14, [rsp+78h+arg_38]
0x18000a8f5  xor     eax, eax
0x18000a8f7  mov     rbx, [rsp+78h+arg_78]
0x18000a8ff  xor     ebp, ebp
0x18000a901  mov     r15d, [rsp+78h+arg_30]
0x18000a909  mov     r10, rcx
0x18000a90c  mov     rsi, [rsp+78h+lpOutputString]
0x18000a914  mov     r12, r9
0x18000a917  mov     r13, r8
0x18000a91a  mov     ecx, r15d
0x18000a91d  mov     [rsi], ax
0x18000a920  mov     rax, [rsp+78h+arg_60]
0x18000a928  mov     byte ptr [rax], 0
0x18000a92b  mov     edi, [r14]
0x18000a92e  mov     [rbx+8], edi
0x18000a931  mov     eax, [r14+4]
0x18000a935  mov     [rbx+0Ch], eax
0x18000a938  test    r15d, r15d
0x18000a93b  jz      short loc_18000A9A3
0x18000a93d  sub     ecx, 1
0x18000a940  jz      short loc_18000A99A
0x18000a942  sub     ecx, 1
0x18000a945  jz      short loc_18000A955
0x18000a947  cmp     ecx, 1
0x18000a94a  jnz     short loc_18000A9AC
0x18000a94c  mov     ecx, edi; this
0x18000a94e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a953  jmp     short loc_18000A9AA
0x18000a955  test    edi, edi
0x18000a957  js      short loc_18000A991
0x18000a959  mov     rax, [rsp+78h+arg_28]
0x18000a961  mov     edi, 8007029Ch
0x18000a966  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a96a  mov     rcx, r10; int
0x18000a96d  mov     [rsp+78h+var_50], rax; __int64
0x18000a972  mov     rax, [rsp+78h+arg_20]
0x18000a97a  mov     [rsp+78h+var_58], rax; __int64
0x18000a97f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a984  mov     ecx, edi; this
0x18000a986  mov     [rbx+8], edi
0x18000a989  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a98e  mov     [rbx+0Ch], eax
0x18000a991  mov     ecx, edi; this
0x18000a993  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a998  jmp     short loc_18000A9AA
0x18000a99a  mov     ecx, edi; this
0x18000a99c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a9a1  jmp     short loc_18000A9AA
0x18000a9a3  mov     ecx, edi; this
0x18000a9a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a9aa  mov     ebp, eax
0x18000a9ac  mov     eax, [rsp+78h+arg_70]
0x18000a9b3  mov     [rbx+4], eax
0x18000a9b6  mov     [rbx], r15d
0x18000a9b9  cmp     dword ptr [r14+8], 1
0x18000a9be  jnz     short loc_18000A9C6
0x18000a9c0  or      eax, 8
0x18000a9c3  mov     [rbx+4], eax
0x18000a9c6  mov     eax, 1
0x18000a9cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a9d3  inc     eax
0x18000a9d5  xor     edi, edi
0x18000a9d7  mov     [rbx+10h], eax
0x18000a9da  mov     rax, [rsp+78h+arg_40]
0x18000a9e2  test    rax, rax
0x18000a9e5  jz      short loc_18000A9EC
0x18000a9e7  cmp     [rax], di
0x18000a9ea  jnz     short loc_18000A9EF
0x18000a9ec  mov     rax, rdi
0x18000a9ef  mov     [rbx+18h], rax
0x18000a9f3  call    cs:__imp_GetCurrentThreadId
0x18000a9fa  nop     dword ptr [rax+rax+00h]
0x18000a9ff  mov     [rbx+38h], r13
0x18000aa03  xorps   xmm0, xmm0
0x18000aa06  mov     [rbx+20h], eax
0x18000aa09  mov     eax, [rsp+78h+arg_8]
0x18000aa10  mov     [rbx+40h], eax
0x18000aa13  mov     rax, [rsp+78h+arg_20]
0x18000aa1b  mov     [rbx+28h], rax
0x18000aa1f  mov     rax, [rsp+78h+arg_28]
0x18000aa27  mov     [rbx+88h], rax
0x18000aa2e  mov     rax, [rsp+78h+arg_0]
0x18000aa36  mov     [rbx+90h], rax
0x18000aa3d  xor     eax, eax
0x18000aa3f  mov     [rbx+44h], ebp
0x18000aa42  mov     [rbx+30h], r12
0x18000aa46  mov     [rbx+48h], rdi
0x18000aa4a  movups  xmmword ptr [rbx+68h], xmm0
0x18000aa4e  mov     [rbx+78h], rax
0x18000aa52  movups  xmmword ptr [rbx+50h], xmm0
0x18000aa56  mov     [rbx+60h], rax
0x18000aa5a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000aa61  test    rax, rax
0x18000aa64  jz      short loc_18000AA6D
0x18000aa66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa6b  jmp     short loc_18000AA70
0x18000aa6d  mov     rax, rdi
0x18000aa70  mov     [rbx+80h], rax
0x18000aa77  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000aa7e  test    rax, rax
0x18000aa81  jz      short loc_18000AA8B
0x18000aa83  mov     rcx, rbx
0x18000aa86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa8b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000aa92  test    rax, rax
0x18000aa95  jz      short loc_18000AAAD
0x18000aa97  mov     rdx, [rsp+78h+arg_60]
0x18000aa9f  mov     r8d, 400h
0x18000aaa5  mov     rcx, rbx
0x18000aaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000aab4  test    rax, rax
0x18000aab7  jz      short loc_18000AAC1
0x18000aab9  mov     rcx, rbx
0x18000aabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aac1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000aac8  test    rax, rax
0x18000aacb  jz      short loc_18000AADB
0x18000aacd  test    byte ptr [rbx+4], 2
0x18000aad1  jnz     short loc_18000AADB
0x18000aad3  mov     rcx, rbx
0x18000aad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aadb  cmp     [rbx+8], edi
0x18000aade  jl      short loc_18000AAFA
0x18000aae0  cmp     r15d, 3
0x18000aae4  jnz     loc_18000ABD5
0x18000aaea  mov     ecx, 8000FFFFh; this
0x18000aaef  mov     [rbx+8], ecx
0x18000aaf2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000aaf7  mov     [rbx+0Ch], eax
0x18000aafa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000ab01  jnz     short loc_18000AB28
0x18000ab03  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ab0a  test    rax, rax
0x18000ab0d  jz      short loc_18000AB18
0x18000ab0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab14  test    al, al
0x18000ab16  jmp     short loc_18000AB26
0x18000ab18  call    cs:__imp_IsDebuggerPresent
0x18000ab1f  nop     dword ptr [rax+rax+00h]
0x18000ab24  test    eax, eax
0x18000ab26  jz      short loc_18000AB2E
0x18000ab28  test    byte ptr [rbx+4], 2
0x18000ab2c  jz      short loc_18000AB52
0x18000ab2e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ab35  test    rax, rax
0x18000ab38  jz      short loc_18000AB9C
0x18000ab3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ab41  jnz     short loc_18000AB9C
0x18000ab43  xor     r8d, r8d
0x18000ab46  xor     edx, edx
0x18000ab48  mov     rcx, rbx
0x18000ab4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab50  jmp     short loc_18000AB9C
0x18000ab52  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ab59  mov     ebp, 800h
0x18000ab5e  test    rax, rax
0x18000ab61  jz      short loc_18000AB7A
0x18000ab63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ab6a  jnz     short loc_18000AB7A
0x18000ab6c  mov     r8d, ebp
0x18000ab6f  mov     rdx, rsi
0x18000ab72  mov     rcx, rbx
0x18000ab75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab7a  cmp     [rsi], di
0x18000ab7d  jnz     short loc_18000AB8D
0x18000ab7f  mov     r8, rbx; unsigned __int64
0x18000ab82  mov     rdx, rbp; unsigned __int16 *
0x18000ab85  mov     rcx, rsi; this
0x18000ab88  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ab8d  mov     rcx, rsi; lpOutputString
0x18000ab90  call    cs:__imp_OutputDebugStringW
0x18000ab97  nop     dword ptr [rax+rax+00h]
0x18000ab9c  test    byte ptr [rbx+4], 4
0x18000aba0  jnz     short loc_18000ABAB
0x18000aba2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000aba9  jz      short loc_18000ABBC
0x18000abab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000abb2  test    rax, rax
0x18000abb5  jz      short loc_18000ABBC
0x18000abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abbc  mov     rbx, [rsp+78h+arg_10]
0x18000abc4  add     rsp, 40h
0x18000abc8  pop     r15
0x18000abca  pop     r14
0x18000abcc  pop     r13
0x18000abce  pop     r12
0x18000abd0  pop     rdi
0x18000abd1  pop     rsi
0x18000abd2  pop     rbp
0x18000abd3  retn
0x18000abd5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
