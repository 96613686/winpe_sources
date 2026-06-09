# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000d610`
- end: `0x18000d909`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000be9c`
- `0x18000c208`
- `0x180018328`

## callees

- `0x180004e68`
- `0x18000bdd0`
- `0x18000cea4`
- `0x18000d610`
- `0x18000dd50`
- `0x18000dd70`
- `0x18000dd84`
- `0x18000dda0`
- `0x18000ec08`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d733`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d733`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d852`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d852`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d8c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d8c4`

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
0x18000d610  mov     [rsp+arg_10], rbx
0x18000d615  mov     [rsp+arg_8], edx
0x18000d619  mov     [rsp+arg_0], rcx
0x18000d61e  push    rbp
0x18000d61f  push    rsi
0x18000d620  push    rdi
0x18000d621  push    r12
0x18000d623  push    r13
0x18000d625  push    r14
0x18000d627  push    r15
0x18000d629  sub     rsp, 40h
0x18000d62d  mov     r12, r9
0x18000d630  mov     r13, r8
0x18000d633  mov     r10, rcx
0x18000d636  xor     eax, eax
0x18000d638  mov     rsi, [rsp+78h+lpOutputString]
0x18000d640  mov     [rsi], ax
0x18000d643  mov     rax, [rsp+78h+arg_60]
0x18000d64b  mov     byte ptr [rax], 0
0x18000d64e  mov     r14, [rsp+78h+arg_38]
0x18000d656  mov     edi, [r14]
0x18000d659  mov     rbx, [rsp+78h+arg_78]
0x18000d661  mov     [rbx+8], edi
0x18000d664  mov     eax, [r14+4]
0x18000d668  mov     [rbx+0Ch], eax
0x18000d66b  xor     ebp, ebp
0x18000d66d  mov     r15d, [rsp+78h+arg_30]
0x18000d675  mov     ecx, r15d
0x18000d678  test    r15d, r15d
0x18000d67b  jz      short loc_18000D6E3
0x18000d67d  sub     ecx, 1
0x18000d680  jz      short loc_18000D6DA
0x18000d682  sub     ecx, 1
0x18000d685  jz      short loc_18000D695
0x18000d687  cmp     ecx, 1
0x18000d68a  jnz     short loc_18000D6EC
0x18000d68c  mov     ecx, edi; this
0x18000d68e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000d693  jmp     short loc_18000D6EA
0x18000d695  test    edi, edi
0x18000d697  js      short loc_18000D6D1
0x18000d699  mov     edi, 8007029Ch
0x18000d69e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000d6a2  mov     rax, [rsp+78h+arg_28]
0x18000d6aa  mov     [rsp+78h+var_50], rax; __int64
0x18000d6af  mov     rax, [rsp+78h+arg_20]
0x18000d6b7  mov     [rsp+78h+var_58], rax; __int64
0x18000d6bc  mov     rcx, r10; int
0x18000d6bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d6c4  mov     [rbx+8], edi
0x18000d6c7  mov     ecx, edi; this
0x18000d6c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d6ce  mov     [rbx+0Ch], eax
0x18000d6d1  mov     ecx, edi; this
0x18000d6d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000d6d8  jmp     short loc_18000D6EA
0x18000d6da  mov     ecx, edi; this
0x18000d6dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d6e1  jmp     short loc_18000D6EA
0x18000d6e3  mov     ecx, edi; this
0x18000d6e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d6ea  mov     ebp, eax
0x18000d6ec  mov     [rbx], r15d
0x18000d6ef  mov     eax, [rsp+78h+arg_70]
0x18000d6f6  mov     [rbx+4], eax
0x18000d6f9  cmp     dword ptr [r14+8], 1
0x18000d6fe  jnz     short loc_18000D706
0x18000d700  or      eax, 8
0x18000d703  mov     [rbx+4], eax
0x18000d706  mov     eax, 1
0x18000d70b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d713  inc     eax
0x18000d715  mov     [rbx+10h], eax
0x18000d718  mov     rax, [rsp+78h+arg_40]
0x18000d720  xor     edi, edi
0x18000d722  test    rax, rax
0x18000d725  jz      short loc_18000D72C
0x18000d727  cmp     [rax], di
0x18000d72a  jnz     short loc_18000D72F
0x18000d72c  mov     rax, rdi
0x18000d72f  mov     [rbx+18h], rax
0x18000d733  call    cs:__imp_GetCurrentThreadId
0x18000d739  mov     [rbx+20h], eax
0x18000d73c  mov     [rbx+38h], r13
0x18000d740  mov     eax, [rsp+78h+arg_8]
0x18000d747  mov     [rbx+40h], eax
0x18000d74a  mov     [rbx+44h], ebp
0x18000d74d  mov     rax, [rsp+78h+arg_20]
0x18000d755  mov     [rbx+28h], rax
0x18000d759  mov     [rbx+30h], r12
0x18000d75d  mov     rax, [rsp+78h+arg_28]
0x18000d765  mov     [rbx+88h], rax
0x18000d76c  mov     rax, [rsp+78h+arg_0]
0x18000d774  mov     [rbx+90h], rax
0x18000d77b  mov     [rbx+48h], rdi
0x18000d77f  xorps   xmm0, xmm0
0x18000d782  xor     eax, eax
0x18000d784  movups  xmmword ptr [rbx+68h], xmm0
0x18000d788  mov     [rbx+78h], rax
0x18000d78c  movups  xmmword ptr [rbx+50h], xmm0
0x18000d790  mov     [rbx+60h], rax
0x18000d794  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d79b  test    rax, rax
0x18000d79e  jz      short loc_18000D7A7
0x18000d7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a5  jmp     short loc_18000D7AA
0x18000d7a7  mov     rax, rdi
0x18000d7aa  mov     [rbx+80h], rax
0x18000d7b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d7b8  test    rax, rax
0x18000d7bb  jz      short loc_18000D7C5
0x18000d7bd  mov     rcx, rbx
0x18000d7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d7cc  test    rax, rax
0x18000d7cf  jz      short loc_18000D7E7
0x18000d7d1  mov     r8d, 400h
0x18000d7d7  mov     rdx, [rsp+78h+arg_60]
0x18000d7df  mov     rcx, rbx
0x18000d7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d7ee  test    rax, rax
0x18000d7f1  jz      short loc_18000D7FB
0x18000d7f3  mov     rcx, rbx
0x18000d7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7fb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d802  test    rax, rax
0x18000d805  jz      short loc_18000D815
0x18000d807  test    byte ptr [rbx+4], 2
0x18000d80b  jnz     short loc_18000D815
0x18000d80d  mov     rcx, rbx
0x18000d810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d815  cmp     [rbx+8], edi
0x18000d818  jl      short loc_18000D834
0x18000d81a  cmp     r15d, 3
0x18000d81e  jnz     loc_18000D903
0x18000d824  mov     ecx, 8000FFFFh; this
0x18000d829  mov     [rbx+8], ecx
0x18000d82c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d831  mov     [rbx+0Ch], eax
0x18000d834  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000d83b  jnz     short loc_18000D85C
0x18000d83d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d844  test    rax, rax
0x18000d847  jz      short loc_18000D852
0x18000d849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d84e  test    al, al
0x18000d850  jmp     short loc_18000D85A
0x18000d852  call    cs:__imp_IsDebuggerPresent
0x18000d858  test    eax, eax
0x18000d85a  jz      short loc_18000D862
0x18000d85c  test    byte ptr [rbx+4], 2
0x18000d860  jz      short loc_18000D886
0x18000d862  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d869  test    rax, rax
0x18000d86c  jz      short loc_18000D8CA
0x18000d86e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d875  jnz     short loc_18000D8CA
0x18000d877  xor     r8d, r8d
0x18000d87a  xor     edx, edx
0x18000d87c  mov     rcx, rbx
0x18000d87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d884  jmp     short loc_18000D8CA
0x18000d886  mov     ebp, 800h
0x18000d88b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d892  test    rax, rax
0x18000d895  jz      short loc_18000D8AE
0x18000d897  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d89e  jnz     short loc_18000D8AE
0x18000d8a0  mov     r8d, ebp
0x18000d8a3  mov     rdx, rsi
0x18000d8a6  mov     rcx, rbx
0x18000d8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ae  cmp     [rsi], di
0x18000d8b1  jnz     short loc_18000D8C1
0x18000d8b3  mov     r8, rbx; unsigned __int64
0x18000d8b6  mov     rdx, rbp; unsigned __int16 *
0x18000d8b9  mov     rcx, rsi; this
0x18000d8bc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000d8c1  mov     rcx, rsi; lpOutputString
0x18000d8c4  call    cs:__imp_OutputDebugStringW
0x18000d8ca  test    byte ptr [rbx+4], 4
0x18000d8ce  jnz     short loc_18000D8D9
0x18000d8d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000d8d7  jz      short loc_18000D8EB
0x18000d8d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d8e0  test    rax, rax
0x18000d8e3  jz      short loc_18000D8EB
0x18000d8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ea  nop
0x18000d8eb  mov     rbx, [rsp+78h+arg_10]
0x18000d8f3  add     rsp, 40h
0x18000d8f7  pop     r15
0x18000d8f9  pop     r14
0x18000d8fb  pop     r13
0x18000d8fd  pop     r12
0x18000d8ff  pop     rdi
0x18000d900  pop     rsi
0x18000d901  pop     rbp
0x18000d902  retn
0x18000d903  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
