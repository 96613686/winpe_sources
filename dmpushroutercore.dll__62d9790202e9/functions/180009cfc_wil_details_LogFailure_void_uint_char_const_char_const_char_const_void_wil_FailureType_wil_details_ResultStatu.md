# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009cfc`
- end: `0x180009ff5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007114`

## callees

- `0x180006b20`
- `0x180009204`
- `0x180009a50`
- `0x180009cfc`
- `0x18000aa3c`
- `0x18000aa60`
- `0x18000ab8c`
- `0x18000aba8`
- `0x18000d438`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e1f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009fb0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009fb0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009f3e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009f3e`

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
0x180009cfc  mov     [rsp+arg_10], rbx
0x180009d01  mov     [rsp+arg_8], edx
0x180009d05  mov     [rsp+arg_0], rcx
0x180009d0a  push    rbp
0x180009d0b  push    rsi
0x180009d0c  push    rdi
0x180009d0d  push    r12
0x180009d0f  push    r13
0x180009d11  push    r14
0x180009d13  push    r15
0x180009d15  sub     rsp, 40h
0x180009d19  mov     r12, r9
0x180009d1c  mov     r13, r8
0x180009d1f  mov     r10, rcx
0x180009d22  xor     eax, eax
0x180009d24  mov     rsi, [rsp+78h+lpOutputString]
0x180009d2c  mov     [rsi], ax
0x180009d2f  mov     rax, [rsp+78h+arg_60]
0x180009d37  mov     byte ptr [rax], 0
0x180009d3a  mov     r14, [rsp+78h+arg_38]
0x180009d42  mov     edi, [r14]
0x180009d45  mov     rbx, [rsp+78h+arg_78]
0x180009d4d  mov     [rbx+8], edi
0x180009d50  mov     eax, [r14+4]
0x180009d54  mov     [rbx+0Ch], eax
0x180009d57  xor     ebp, ebp
0x180009d59  mov     r15d, [rsp+78h+arg_30]
0x180009d61  mov     ecx, r15d
0x180009d64  test    r15d, r15d
0x180009d67  jz      short loc_180009DCF
0x180009d69  sub     ecx, 1
0x180009d6c  jz      short loc_180009DC6
0x180009d6e  sub     ecx, 1
0x180009d71  jz      short loc_180009D81
0x180009d73  cmp     ecx, 1
0x180009d76  jnz     short loc_180009DD8
0x180009d78  mov     ecx, edi; this
0x180009d7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009d7f  jmp     short loc_180009DD6
0x180009d81  test    edi, edi
0x180009d83  js      short loc_180009DBD
0x180009d85  mov     edi, 8007029Ch
0x180009d8a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009d8e  mov     rax, [rsp+78h+arg_28]
0x180009d96  mov     [rsp+78h+var_50], rax; __int64
0x180009d9b  mov     rax, [rsp+78h+arg_20]
0x180009da3  mov     [rsp+78h+var_58], rax; __int64
0x180009da8  mov     rcx, r10; int
0x180009dab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009db0  mov     [rbx+8], edi
0x180009db3  mov     ecx, edi; this
0x180009db5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009dba  mov     [rbx+0Ch], eax
0x180009dbd  mov     ecx, edi; this
0x180009dbf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009dc4  jmp     short loc_180009DD6
0x180009dc6  mov     ecx, edi; this
0x180009dc8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009dcd  jmp     short loc_180009DD6
0x180009dcf  mov     ecx, edi; this
0x180009dd1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009dd6  mov     ebp, eax
0x180009dd8  mov     [rbx], r15d
0x180009ddb  mov     eax, [rsp+78h+arg_70]
0x180009de2  mov     [rbx+4], eax
0x180009de5  cmp     dword ptr [r14+8], 1
0x180009dea  jnz     short loc_180009DF2
0x180009dec  or      eax, 8
0x180009def  mov     [rbx+4], eax
0x180009df2  mov     eax, 1
0x180009df7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009dff  inc     eax
0x180009e01  mov     [rbx+10h], eax
0x180009e04  mov     rax, [rsp+78h+arg_40]
0x180009e0c  xor     edi, edi
0x180009e0e  test    rax, rax
0x180009e11  jz      short loc_180009E18
0x180009e13  cmp     [rax], di
0x180009e16  jnz     short loc_180009E1B
0x180009e18  mov     rax, rdi
0x180009e1b  mov     [rbx+18h], rax
0x180009e1f  call    cs:__imp_GetCurrentThreadId
0x180009e25  mov     [rbx+20h], eax
0x180009e28  mov     [rbx+38h], r13
0x180009e2c  mov     eax, [rsp+78h+arg_8]
0x180009e33  mov     [rbx+40h], eax
0x180009e36  mov     [rbx+44h], ebp
0x180009e39  mov     rax, [rsp+78h+arg_20]
0x180009e41  mov     [rbx+28h], rax
0x180009e45  mov     [rbx+30h], r12
0x180009e49  mov     rax, [rsp+78h+arg_28]
0x180009e51  mov     [rbx+88h], rax
0x180009e58  mov     rax, [rsp+78h+arg_0]
0x180009e60  mov     [rbx+90h], rax
0x180009e67  mov     [rbx+48h], rdi
0x180009e6b  xorps   xmm0, xmm0
0x180009e6e  xor     eax, eax
0x180009e70  movups  xmmword ptr [rbx+68h], xmm0
0x180009e74  mov     [rbx+78h], rax
0x180009e78  movups  xmmword ptr [rbx+50h], xmm0
0x180009e7c  mov     [rbx+60h], rax
0x180009e80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009e87  test    rax, rax
0x180009e8a  jz      short loc_180009E93
0x180009e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e91  jmp     short loc_180009E96
0x180009e93  mov     rax, rdi
0x180009e96  mov     [rbx+80h], rax
0x180009e9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009ea4  test    rax, rax
0x180009ea7  jz      short loc_180009EB1
0x180009ea9  mov     rcx, rbx
0x180009eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009eb8  test    rax, rax
0x180009ebb  jz      short loc_180009ED3
0x180009ebd  mov     r8d, 400h
0x180009ec3  mov     rdx, [rsp+78h+arg_60]
0x180009ecb  mov     rcx, rbx
0x180009ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009eda  test    rax, rax
0x180009edd  jz      short loc_180009EE7
0x180009edf  mov     rcx, rbx
0x180009ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ee7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009eee  test    rax, rax
0x180009ef1  jz      short loc_180009F01
0x180009ef3  test    byte ptr [rbx+4], 2
0x180009ef7  jnz     short loc_180009F01
0x180009ef9  mov     rcx, rbx
0x180009efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f01  cmp     [rbx+8], edi
0x180009f04  jl      short loc_180009F20
0x180009f06  cmp     r15d, 3
0x180009f0a  jnz     loc_180009FEF
0x180009f10  mov     ecx, 8000FFFFh; this
0x180009f15  mov     [rbx+8], ecx
0x180009f18  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009f1d  mov     [rbx+0Ch], eax
0x180009f20  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009f27  jnz     short loc_180009F48
0x180009f29  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009f30  test    rax, rax
0x180009f33  jz      short loc_180009F3E
0x180009f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3a  test    al, al
0x180009f3c  jmp     short loc_180009F46
0x180009f3e  call    cs:__imp_IsDebuggerPresent
0x180009f44  test    eax, eax
0x180009f46  jz      short loc_180009F4E
0x180009f48  test    byte ptr [rbx+4], 2
0x180009f4c  jz      short loc_180009F72
0x180009f4e  mov     rax, cs:g_pfnResultLoggingCallback
0x180009f55  test    rax, rax
0x180009f58  jz      short loc_180009FB6
0x180009f5a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009f61  jnz     short loc_180009FB6
0x180009f63  xor     r8d, r8d
0x180009f66  xor     edx, edx
0x180009f68  mov     rcx, rbx
0x180009f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f70  jmp     short loc_180009FB6
0x180009f72  mov     ebp, 800h
0x180009f77  mov     rax, cs:g_pfnResultLoggingCallback
0x180009f7e  test    rax, rax
0x180009f81  jz      short loc_180009F9A
0x180009f83  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009f8a  jnz     short loc_180009F9A
0x180009f8c  mov     r8d, ebp
0x180009f8f  mov     rdx, rsi
0x180009f92  mov     rcx, rbx
0x180009f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f9a  cmp     [rsi], di
0x180009f9d  jnz     short loc_180009FAD
0x180009f9f  mov     r8, rbx; unsigned __int64
0x180009fa2  mov     rdx, rbp; unsigned __int16 *
0x180009fa5  mov     rcx, rsi; this
0x180009fa8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009fad  mov     rcx, rsi; lpOutputString
0x180009fb0  call    cs:__imp_OutputDebugStringW
0x180009fb6  test    byte ptr [rbx+4], 4
0x180009fba  jnz     short loc_180009FC5
0x180009fbc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009fc3  jz      short loc_180009FD7
0x180009fc5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009fcc  test    rax, rax
0x180009fcf  jz      short loc_180009FD7
0x180009fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd6  nop
0x180009fd7  mov     rbx, [rsp+78h+arg_10]
0x180009fdf  add     rsp, 40h
0x180009fe3  pop     r15
0x180009fe5  pop     r14
0x180009fe7  pop     r13
0x180009fe9  pop     r12
0x180009feb  pop     rdi
0x180009fec  pop     rsi
0x180009fed  pop     rbp
0x180009fee  retn
0x180009fef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
