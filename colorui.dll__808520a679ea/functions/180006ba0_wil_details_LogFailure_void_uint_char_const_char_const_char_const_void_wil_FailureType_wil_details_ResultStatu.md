# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ba0`
- end: `0x180006e98`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002b18`

## callees

- `0x18000255c`
- `0x180005c74`
- `0x1800064a0`
- `0x180006ba0`
- `0x180007d60`
- `0x180007d80`
- `0x180007ea8`
- `0x180007ec4`
- `0x18000b3f4`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006cc3`
- `KERNEL32!GetCurrentThreadId` at `0x180006cc3`
- `KERNEL32!OutputDebugStringW` at `0x180006e54`
- `KERNEL32!OutputDebugStringW` at `0x180006e54`
- `KERNEL32!IsDebuggerPresent` at `0x180006de2`
- `KERNEL32!IsDebuggerPresent` at `0x180006de2`

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
0x180006ba0  mov     [rsp+arg_10], rbx
0x180006ba5  mov     [rsp+arg_8], edx
0x180006ba9  mov     [rsp+arg_0], rcx
0x180006bae  push    rbp
0x180006baf  push    rsi
0x180006bb0  push    rdi
0x180006bb1  push    r12
0x180006bb3  push    r13
0x180006bb5  push    r14
0x180006bb7  push    r15
0x180006bb9  sub     rsp, 40h
0x180006bbd  mov     r14, [rsp+78h+arg_38]
0x180006bc5  xor     eax, eax
0x180006bc7  mov     rbx, [rsp+78h+arg_78]
0x180006bcf  xor     ebp, ebp
0x180006bd1  mov     r15d, [rsp+78h+arg_30]
0x180006bd9  mov     r10, rcx
0x180006bdc  mov     rsi, [rsp+78h+lpOutputString]
0x180006be4  mov     r12, r9
0x180006be7  mov     r13, r8
0x180006bea  mov     ecx, r15d
0x180006bed  mov     [rsi], ax
0x180006bf0  mov     rax, [rsp+78h+arg_60]
0x180006bf8  mov     byte ptr [rax], 0
0x180006bfb  mov     edi, [r14]
0x180006bfe  mov     [rbx+8], edi
0x180006c01  mov     eax, [r14+4]
0x180006c05  mov     [rbx+0Ch], eax
0x180006c08  test    r15d, r15d
0x180006c0b  jz      short loc_180006C73
0x180006c0d  sub     ecx, 1
0x180006c10  jz      short loc_180006C6A
0x180006c12  sub     ecx, 1
0x180006c15  jz      short loc_180006C25
0x180006c17  cmp     ecx, 1
0x180006c1a  jnz     short loc_180006C7C
0x180006c1c  mov     ecx, edi; this
0x180006c1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006c23  jmp     short loc_180006C7A
0x180006c25  test    edi, edi
0x180006c27  js      short loc_180006C61
0x180006c29  mov     rax, [rsp+78h+arg_28]
0x180006c31  mov     edi, 8007029Ch
0x180006c36  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006c3a  mov     rcx, r10; int
0x180006c3d  mov     [rsp+78h+var_50], rax; __int64
0x180006c42  mov     rax, [rsp+78h+arg_20]
0x180006c4a  mov     [rsp+78h+var_58], rax; __int64
0x180006c4f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006c54  mov     ecx, edi; this
0x180006c56  mov     [rbx+8], edi
0x180006c59  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006c5e  mov     [rbx+0Ch], eax
0x180006c61  mov     ecx, edi; this
0x180006c63  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006c68  jmp     short loc_180006C7A
0x180006c6a  mov     ecx, edi; this
0x180006c6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006c71  jmp     short loc_180006C7A
0x180006c73  mov     ecx, edi; this
0x180006c75  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006c7a  mov     ebp, eax
0x180006c7c  mov     eax, [rsp+78h+arg_70]
0x180006c83  mov     [rbx+4], eax
0x180006c86  mov     [rbx], r15d
0x180006c89  cmp     dword ptr [r14+8], 1
0x180006c8e  jnz     short loc_180006C96
0x180006c90  or      eax, 8
0x180006c93  mov     [rbx+4], eax
0x180006c96  mov     eax, 1
0x180006c9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006ca3  inc     eax
0x180006ca5  xor     edi, edi
0x180006ca7  mov     [rbx+10h], eax
0x180006caa  mov     rax, [rsp+78h+arg_40]
0x180006cb2  test    rax, rax
0x180006cb5  jz      short loc_180006CBC
0x180006cb7  cmp     [rax], di
0x180006cba  jnz     short loc_180006CBF
0x180006cbc  mov     rax, rdi
0x180006cbf  mov     [rbx+18h], rax
0x180006cc3  call    cs:__imp_GetCurrentThreadId
0x180006cc9  mov     [rbx+38h], r13
0x180006ccd  xorps   xmm0, xmm0
0x180006cd0  mov     [rbx+20h], eax
0x180006cd3  mov     eax, [rsp+78h+arg_8]
0x180006cda  mov     [rbx+40h], eax
0x180006cdd  mov     rax, [rsp+78h+arg_20]
0x180006ce5  mov     [rbx+28h], rax
0x180006ce9  mov     rax, [rsp+78h+arg_28]
0x180006cf1  mov     [rbx+88h], rax
0x180006cf8  mov     rax, [rsp+78h+arg_0]
0x180006d00  mov     [rbx+90h], rax
0x180006d07  xor     eax, eax
0x180006d09  mov     [rbx+44h], ebp
0x180006d0c  mov     [rbx+30h], r12
0x180006d10  mov     [rbx+48h], rdi
0x180006d14  movups  xmmword ptr [rbx+68h], xmm0
0x180006d18  mov     [rbx+78h], rax
0x180006d1c  movups  xmmword ptr [rbx+50h], xmm0
0x180006d20  mov     [rbx+60h], rax
0x180006d24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006d2b  test    rax, rax
0x180006d2e  jz      short loc_180006D37
0x180006d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d35  jmp     short loc_180006D3A
0x180006d37  mov     rax, rdi
0x180006d3a  mov     [rbx+80h], rax
0x180006d41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006d48  test    rax, rax
0x180006d4b  jz      short loc_180006D55
0x180006d4d  mov     rcx, rbx
0x180006d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d55  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006d5c  test    rax, rax
0x180006d5f  jz      short loc_180006D77
0x180006d61  mov     rdx, [rsp+78h+arg_60]
0x180006d69  mov     r8d, 400h
0x180006d6f  mov     rcx, rbx
0x180006d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d7e  test    rax, rax
0x180006d81  jz      short loc_180006D8B
0x180006d83  mov     rcx, rbx
0x180006d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d8b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d92  test    rax, rax
0x180006d95  jz      short loc_180006DA5
0x180006d97  test    byte ptr [rbx+4], 2
0x180006d9b  jnz     short loc_180006DA5
0x180006d9d  mov     rcx, rbx
0x180006da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da5  cmp     [rbx+8], edi
0x180006da8  jl      short loc_180006DC4
0x180006daa  cmp     r15d, 3
0x180006dae  jnz     loc_180006E92
0x180006db4  mov     ecx, 8000FFFFh; this
0x180006db9  mov     [rbx+8], ecx
0x180006dbc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006dc1  mov     [rbx+0Ch], eax
0x180006dc4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006dcb  jnz     short loc_180006DEC
0x180006dcd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006dd4  test    rax, rax
0x180006dd7  jz      short loc_180006DE2
0x180006dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dde  test    al, al
0x180006de0  jmp     short loc_180006DEA
0x180006de2  call    cs:__imp_IsDebuggerPresent
0x180006de8  test    eax, eax
0x180006dea  jz      short loc_180006DF2
0x180006dec  test    byte ptr [rbx+4], 2
0x180006df0  jz      short loc_180006E16
0x180006df2  mov     rax, cs:g_pfnResultLoggingCallback
0x180006df9  test    rax, rax
0x180006dfc  jz      short loc_180006E5A
0x180006dfe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006e05  jnz     short loc_180006E5A
0x180006e07  xor     r8d, r8d
0x180006e0a  xor     edx, edx
0x180006e0c  mov     rcx, rbx
0x180006e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e14  jmp     short loc_180006E5A
0x180006e16  mov     rax, cs:g_pfnResultLoggingCallback
0x180006e1d  mov     ebp, 800h
0x180006e22  test    rax, rax
0x180006e25  jz      short loc_180006E3E
0x180006e27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006e2e  jnz     short loc_180006E3E
0x180006e30  mov     r8d, ebp
0x180006e33  mov     rdx, rsi
0x180006e36  mov     rcx, rbx
0x180006e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3e  cmp     [rsi], di
0x180006e41  jnz     short loc_180006E51
0x180006e43  mov     r8, rbx; unsigned __int64
0x180006e46  mov     rdx, rbp; unsigned __int16 *
0x180006e49  mov     rcx, rsi; this
0x180006e4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006e51  mov     rcx, rsi; lpOutputString
0x180006e54  call    cs:__imp_OutputDebugStringW
0x180006e5a  test    byte ptr [rbx+4], 4
0x180006e5e  jnz     short loc_180006E69
0x180006e60  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006e67  jz      short loc_180006E7A
0x180006e69  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006e70  test    rax, rax
0x180006e73  jz      short loc_180006E7A
0x180006e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e7a  mov     rbx, [rsp+78h+arg_10]
0x180006e82  add     rsp, 40h
0x180006e86  pop     r15
0x180006e88  pop     r14
0x180006e8a  pop     r13
0x180006e8c  pop     r12
0x180006e8e  pop     rdi
0x180006e8f  pop     rsi
0x180006e90  pop     rbp
0x180006e91  retn
0x180006e92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
