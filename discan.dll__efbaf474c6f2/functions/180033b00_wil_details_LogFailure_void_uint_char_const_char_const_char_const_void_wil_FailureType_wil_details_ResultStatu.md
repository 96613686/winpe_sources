# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180033b00`
- end: `0x180033df8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800318d8`
- `0x180031c24`

## callees

- `0x180031818`
- `0x180032fa4`
- `0x180033804`
- `0x180033b00`
- `0x1800347b4`
- `0x1800347d0`
- `0x180034920`
- `0x18003493c`
- `0x1800361f8`
- `0x180039010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180033db4`
- `KERNEL32!OutputDebugStringW` at `0x180033db4`
- `KERNEL32!IsDebuggerPresent` at `0x180033d42`
- `KERNEL32!IsDebuggerPresent` at `0x180033d42`
- `KERNEL32!GetCurrentThreadId` at `0x180033c23`
- `KERNEL32!GetCurrentThreadId` at `0x180033c23`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180033b00  mov     [rsp+arg_10], rbx
0x180033b05  mov     [rsp+arg_8], edx
0x180033b09  mov     [rsp+arg_0], rcx
0x180033b0e  push    rbp
0x180033b0f  push    rsi
0x180033b10  push    rdi
0x180033b11  push    r12
0x180033b13  push    r13
0x180033b15  push    r14
0x180033b17  push    r15
0x180033b19  sub     rsp, 40h
0x180033b1d  mov     r14, [rsp+78h+arg_38]
0x180033b25  xor     eax, eax
0x180033b27  mov     rbx, [rsp+78h+arg_78]
0x180033b2f  xor     ebp, ebp
0x180033b31  mov     r15d, [rsp+78h+arg_30]
0x180033b39  mov     r10, rcx
0x180033b3c  mov     rsi, [rsp+78h+lpOutputString]
0x180033b44  mov     r12, r9
0x180033b47  mov     r13, r8
0x180033b4a  mov     ecx, r15d
0x180033b4d  mov     [rsi], ax
0x180033b50  mov     rax, [rsp+78h+arg_60]
0x180033b58  mov     byte ptr [rax], 0
0x180033b5b  mov     edi, [r14]
0x180033b5e  mov     [rbx+8], edi
0x180033b61  mov     eax, [r14+4]
0x180033b65  mov     [rbx+0Ch], eax
0x180033b68  test    r15d, r15d
0x180033b6b  jz      short loc_180033BD3
0x180033b6d  sub     ecx, 1
0x180033b70  jz      short loc_180033BCA
0x180033b72  sub     ecx, 1
0x180033b75  jz      short loc_180033B85
0x180033b77  cmp     ecx, 1
0x180033b7a  jnz     short loc_180033BDC
0x180033b7c  mov     ecx, edi; this
0x180033b7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180033b83  jmp     short loc_180033BDA
0x180033b85  test    edi, edi
0x180033b87  js      short loc_180033BC1
0x180033b89  mov     rax, [rsp+78h+arg_28]
0x180033b91  mov     edi, 8007029Ch
0x180033b96  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180033b9a  mov     rcx, r10; int
0x180033b9d  mov     [rsp+78h+var_50], rax; __int64
0x180033ba2  mov     rax, [rsp+78h+arg_20]
0x180033baa  mov     [rsp+78h+var_58], rax; __int64
0x180033baf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180033bb4  mov     ecx, edi; this
0x180033bb6  mov     [rbx+8], edi
0x180033bb9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180033bbe  mov     [rbx+0Ch], eax
0x180033bc1  mov     ecx, edi; this
0x180033bc3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180033bc8  jmp     short loc_180033BDA
0x180033bca  mov     ecx, edi; this
0x180033bcc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180033bd1  jmp     short loc_180033BDA
0x180033bd3  mov     ecx, edi; this
0x180033bd5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180033bda  mov     ebp, eax
0x180033bdc  mov     eax, [rsp+78h+arg_70]
0x180033be3  mov     [rbx+4], eax
0x180033be6  mov     [rbx], r15d
0x180033be9  cmp     dword ptr [r14+8], 1
0x180033bee  jnz     short loc_180033BF6
0x180033bf0  or      eax, 8
0x180033bf3  mov     [rbx+4], eax
0x180033bf6  mov     eax, 1
0x180033bfb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180033c03  inc     eax
0x180033c05  xor     edi, edi
0x180033c07  mov     [rbx+10h], eax
0x180033c0a  mov     rax, [rsp+78h+arg_40]
0x180033c12  test    rax, rax
0x180033c15  jz      short loc_180033C1C
0x180033c17  cmp     [rax], di
0x180033c1a  jnz     short loc_180033C1F
0x180033c1c  mov     rax, rdi
0x180033c1f  mov     [rbx+18h], rax
0x180033c23  call    cs:__imp_GetCurrentThreadId
0x180033c29  mov     [rbx+38h], r13
0x180033c2d  xorps   xmm0, xmm0
0x180033c30  mov     [rbx+20h], eax
0x180033c33  mov     eax, [rsp+78h+arg_8]
0x180033c3a  mov     [rbx+40h], eax
0x180033c3d  mov     rax, [rsp+78h+arg_20]
0x180033c45  mov     [rbx+28h], rax
0x180033c49  mov     rax, [rsp+78h+arg_28]
0x180033c51  mov     [rbx+88h], rax
0x180033c58  mov     rax, [rsp+78h+arg_0]
0x180033c60  mov     [rbx+90h], rax
0x180033c67  xor     eax, eax
0x180033c69  mov     [rbx+44h], ebp
0x180033c6c  mov     [rbx+30h], r12
0x180033c70  mov     [rbx+48h], rdi
0x180033c74  movups  xmmword ptr [rbx+68h], xmm0
0x180033c78  mov     [rbx+78h], rax
0x180033c7c  movups  xmmword ptr [rbx+50h], xmm0
0x180033c80  mov     [rbx+60h], rax
0x180033c84  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180033c8b  test    rax, rax
0x180033c8e  jz      short loc_180033C97
0x180033c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c95  jmp     short loc_180033C9A
0x180033c97  mov     rax, rdi
0x180033c9a  mov     [rbx+80h], rax
0x180033ca1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180033ca8  test    rax, rax
0x180033cab  jz      short loc_180033CB5
0x180033cad  mov     rcx, rbx
0x180033cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cb5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180033cbc  test    rax, rax
0x180033cbf  jz      short loc_180033CD7
0x180033cc1  mov     rdx, [rsp+78h+arg_60]
0x180033cc9  mov     r8d, 400h
0x180033ccf  mov     rcx, rbx
0x180033cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cd7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180033cde  test    rax, rax
0x180033ce1  jz      short loc_180033CEB
0x180033ce3  mov     rcx, rbx
0x180033ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ceb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180033cf2  test    rax, rax
0x180033cf5  jz      short loc_180033D05
0x180033cf7  test    byte ptr [rbx+4], 2
0x180033cfb  jnz     short loc_180033D05
0x180033cfd  mov     rcx, rbx
0x180033d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d05  cmp     [rbx+8], edi
0x180033d08  jl      short loc_180033D24
0x180033d0a  cmp     r15d, 3
0x180033d0e  jnz     loc_180033DF2
0x180033d14  mov     ecx, 8000FFFFh; this
0x180033d19  mov     [rbx+8], ecx
0x180033d1c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180033d21  mov     [rbx+0Ch], eax
0x180033d24  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180033d2b  jnz     short loc_180033D4C
0x180033d2d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180033d34  test    rax, rax
0x180033d37  jz      short loc_180033D42
0x180033d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d3e  test    al, al
0x180033d40  jmp     short loc_180033D4A
0x180033d42  call    cs:__imp_IsDebuggerPresent
0x180033d48  test    eax, eax
0x180033d4a  jz      short loc_180033D52
0x180033d4c  test    byte ptr [rbx+4], 2
0x180033d50  jz      short loc_180033D76
0x180033d52  mov     rax, cs:g_pfnResultLoggingCallback
0x180033d59  test    rax, rax
0x180033d5c  jz      short loc_180033DBA
0x180033d5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180033d65  jnz     short loc_180033DBA
0x180033d67  xor     r8d, r8d
0x180033d6a  xor     edx, edx
0x180033d6c  mov     rcx, rbx
0x180033d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d74  jmp     short loc_180033DBA
0x180033d76  mov     rax, cs:g_pfnResultLoggingCallback
0x180033d7d  mov     ebp, 800h
0x180033d82  test    rax, rax
0x180033d85  jz      short loc_180033D9E
0x180033d87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180033d8e  jnz     short loc_180033D9E
0x180033d90  mov     r8d, ebp
0x180033d93  mov     rdx, rsi
0x180033d96  mov     rcx, rbx
0x180033d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d9e  cmp     [rsi], di
0x180033da1  jnz     short loc_180033DB1
0x180033da3  mov     r8, rbx; unsigned __int64
0x180033da6  mov     rdx, rbp; unsigned __int16 *
0x180033da9  mov     rcx, rsi; this
0x180033dac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180033db1  mov     rcx, rsi; lpOutputString
0x180033db4  call    cs:__imp_OutputDebugStringW
0x180033dba  test    byte ptr [rbx+4], 4
0x180033dbe  jnz     short loc_180033DC9
0x180033dc0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180033dc7  jz      short loc_180033DDA
0x180033dc9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180033dd0  test    rax, rax
0x180033dd3  jz      short loc_180033DDA
0x180033dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dda  mov     rbx, [rsp+78h+arg_10]
0x180033de2  add     rsp, 40h
0x180033de6  pop     r15
0x180033de8  pop     r14
0x180033dea  pop     r13
0x180033dec  pop     r12
0x180033dee  pop     rdi
0x180033def  pop     rsi
0x180033df0  pop     rbp
0x180033df1  retn
0x180033df2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
