# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800b3c70`
- end: `0x1800b3f69`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800b21d0`
- `0x1800b251c`

## callees

- `0x18009f2f8`
- `0x1800b2110`
- `0x1800b3314`
- `0x1800b3c70`
- `0x1800b43e4`
- `0x1800b4400`
- `0x1800b4414`
- `0x1800b4430`
- `0x1800b55e4`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b3d93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b3d93`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b3f24`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b3f24`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800b3eb2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800b3eb2`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x1800b3c70  mov     [rsp+arg_10], rbx
0x1800b3c75  mov     [rsp+arg_8], edx
0x1800b3c79  mov     [rsp+arg_0], rcx
0x1800b3c7e  push    rbp
0x1800b3c7f  push    rsi
0x1800b3c80  push    rdi
0x1800b3c81  push    r12
0x1800b3c83  push    r13
0x1800b3c85  push    r14
0x1800b3c87  push    r15
0x1800b3c89  sub     rsp, 40h
0x1800b3c8d  mov     r12, r9
0x1800b3c90  mov     r13, r8
0x1800b3c93  mov     r10, rcx
0x1800b3c96  xor     eax, eax
0x1800b3c98  mov     rsi, [rsp+78h+lpOutputString]
0x1800b3ca0  mov     [rsi], ax
0x1800b3ca3  mov     rax, [rsp+78h+arg_60]
0x1800b3cab  mov     byte ptr [rax], 0
0x1800b3cae  mov     r14, [rsp+78h+arg_38]
0x1800b3cb6  mov     edi, [r14]
0x1800b3cb9  mov     rbx, [rsp+78h+arg_78]
0x1800b3cc1  mov     [rbx+8], edi
0x1800b3cc4  mov     eax, [r14+4]
0x1800b3cc8  mov     [rbx+0Ch], eax
0x1800b3ccb  xor     ebp, ebp
0x1800b3ccd  mov     r15d, [rsp+78h+arg_30]
0x1800b3cd5  mov     ecx, r15d
0x1800b3cd8  test    r15d, r15d
0x1800b3cdb  jz      short loc_1800B3D43
0x1800b3cdd  sub     ecx, 1
0x1800b3ce0  jz      short loc_1800B3D3A
0x1800b3ce2  sub     ecx, 1
0x1800b3ce5  jz      short loc_1800B3CF5
0x1800b3ce7  cmp     ecx, 1
0x1800b3cea  jnz     short loc_1800B3D4C
0x1800b3cec  mov     ecx, edi; this
0x1800b3cee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800b3cf3  jmp     short loc_1800B3D4A
0x1800b3cf5  test    edi, edi
0x1800b3cf7  js      short loc_1800B3D31
0x1800b3cf9  mov     edi, 8007029Ch
0x1800b3cfe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800b3d02  mov     rax, [rsp+78h+arg_28]
0x1800b3d0a  mov     [rsp+78h+var_50], rax; __int64
0x1800b3d0f  mov     rax, [rsp+78h+arg_20]
0x1800b3d17  mov     [rsp+78h+var_58], rax; __int64
0x1800b3d1c  mov     rcx, r10; int
0x1800b3d1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800b3d24  mov     [rbx+8], edi
0x1800b3d27  mov     ecx, edi; this
0x1800b3d29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800b3d2e  mov     [rbx+0Ch], eax
0x1800b3d31  mov     ecx, edi; this
0x1800b3d33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800b3d38  jmp     short loc_1800B3D4A
0x1800b3d3a  mov     ecx, edi; this
0x1800b3d3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800b3d41  jmp     short loc_1800B3D4A
0x1800b3d43  mov     ecx, edi; this
0x1800b3d45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800b3d4a  mov     ebp, eax
0x1800b3d4c  mov     [rbx], r15d
0x1800b3d4f  mov     eax, [rsp+78h+arg_70]
0x1800b3d56  mov     [rbx+4], eax
0x1800b3d59  cmp     dword ptr [r14+8], 1
0x1800b3d5e  jnz     short loc_1800B3D66
0x1800b3d60  or      eax, 8
0x1800b3d63  mov     [rbx+4], eax
0x1800b3d66  mov     eax, 1
0x1800b3d6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800b3d73  inc     eax
0x1800b3d75  mov     [rbx+10h], eax
0x1800b3d78  mov     rax, [rsp+78h+arg_40]
0x1800b3d80  xor     edi, edi
0x1800b3d82  test    rax, rax
0x1800b3d85  jz      short loc_1800B3D8C
0x1800b3d87  cmp     [rax], di
0x1800b3d8a  jnz     short loc_1800B3D8F
0x1800b3d8c  mov     rax, rdi
0x1800b3d8f  mov     [rbx+18h], rax
0x1800b3d93  call    cs:__imp_GetCurrentThreadId
0x1800b3d99  mov     [rbx+20h], eax
0x1800b3d9c  mov     [rbx+38h], r13
0x1800b3da0  mov     eax, [rsp+78h+arg_8]
0x1800b3da7  mov     [rbx+40h], eax
0x1800b3daa  mov     [rbx+44h], ebp
0x1800b3dad  mov     rax, [rsp+78h+arg_20]
0x1800b3db5  mov     [rbx+28h], rax
0x1800b3db9  mov     [rbx+30h], r12
0x1800b3dbd  mov     rax, [rsp+78h+arg_28]
0x1800b3dc5  mov     [rbx+88h], rax
0x1800b3dcc  mov     rax, [rsp+78h+arg_0]
0x1800b3dd4  mov     [rbx+90h], rax
0x1800b3ddb  mov     [rbx+48h], rdi
0x1800b3ddf  xorps   xmm0, xmm0
0x1800b3de2  xor     eax, eax
0x1800b3de4  movups  xmmword ptr [rbx+68h], xmm0
0x1800b3de8  mov     [rbx+78h], rax
0x1800b3dec  movups  xmmword ptr [rbx+50h], xmm0
0x1800b3df0  mov     [rbx+60h], rax
0x1800b3df4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800b3dfb  test    rax, rax
0x1800b3dfe  jz      short loc_1800B3E07
0x1800b3e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e05  jmp     short loc_1800B3E0A
0x1800b3e07  mov     rax, rdi
0x1800b3e0a  mov     [rbx+80h], rax
0x1800b3e11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800b3e18  test    rax, rax
0x1800b3e1b  jz      short loc_1800B3E25
0x1800b3e1d  mov     rcx, rbx
0x1800b3e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800b3e2c  test    rax, rax
0x1800b3e2f  jz      short loc_1800B3E47
0x1800b3e31  mov     r8d, 400h
0x1800b3e37  mov     rdx, [rsp+78h+arg_60]
0x1800b3e3f  mov     rcx, rbx
0x1800b3e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800b3e4e  test    rax, rax
0x1800b3e51  jz      short loc_1800B3E5B
0x1800b3e53  mov     rcx, rbx
0x1800b3e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800b3e62  test    rax, rax
0x1800b3e65  jz      short loc_1800B3E75
0x1800b3e67  test    byte ptr [rbx+4], 2
0x1800b3e6b  jnz     short loc_1800B3E75
0x1800b3e6d  mov     rcx, rbx
0x1800b3e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e75  cmp     [rbx+8], edi
0x1800b3e78  jl      short loc_1800B3E94
0x1800b3e7a  cmp     r15d, 3
0x1800b3e7e  jnz     loc_1800B3F63
0x1800b3e84  mov     ecx, 8000FFFFh; this
0x1800b3e89  mov     [rbx+8], ecx
0x1800b3e8c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800b3e91  mov     [rbx+0Ch], eax
0x1800b3e94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800b3e9b  jnz     short loc_1800B3EBC
0x1800b3e9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800b3ea4  test    rax, rax
0x1800b3ea7  jz      short loc_1800B3EB2
0x1800b3ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3eae  test    al, al
0x1800b3eb0  jmp     short loc_1800B3EBA
0x1800b3eb2  call    cs:__imp_IsDebuggerPresent
0x1800b3eb8  test    eax, eax
0x1800b3eba  jz      short loc_1800B3EC2
0x1800b3ebc  test    byte ptr [rbx+4], 2
0x1800b3ec0  jz      short loc_1800B3EE6
0x1800b3ec2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800b3ec9  test    rax, rax
0x1800b3ecc  jz      short loc_1800B3F2A
0x1800b3ece  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800b3ed5  jnz     short loc_1800B3F2A
0x1800b3ed7  xor     r8d, r8d
0x1800b3eda  xor     edx, edx
0x1800b3edc  mov     rcx, rbx
0x1800b3edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ee4  jmp     short loc_1800B3F2A
0x1800b3ee6  mov     ebp, 800h
0x1800b3eeb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800b3ef2  test    rax, rax
0x1800b3ef5  jz      short loc_1800B3F0E
0x1800b3ef7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800b3efe  jnz     short loc_1800B3F0E
0x1800b3f00  mov     r8d, ebp
0x1800b3f03  mov     rdx, rsi
0x1800b3f06  mov     rcx, rbx
0x1800b3f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f0e  cmp     [rsi], di
0x1800b3f11  jnz     short loc_1800B3F21
0x1800b3f13  mov     r8, rbx; unsigned __int64
0x1800b3f16  mov     rdx, rbp; unsigned __int16 *
0x1800b3f19  mov     rcx, rsi; String
0x1800b3f1c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800b3f21  mov     rcx, rsi; lpOutputString
0x1800b3f24  call    cs:__imp_OutputDebugStringW
0x1800b3f2a  test    byte ptr [rbx+4], 4
0x1800b3f2e  jnz     short loc_1800B3F39
0x1800b3f30  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800b3f37  jz      short loc_1800B3F4B
0x1800b3f39  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800b3f40  test    rax, rax
0x1800b3f43  jz      short loc_1800B3F4B
0x1800b3f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f4a  nop
0x1800b3f4b  mov     rbx, [rsp+78h+arg_10]
0x1800b3f53  add     rsp, 40h
0x1800b3f57  pop     r15
0x1800b3f59  pop     r14
0x1800b3f5b  pop     r13
0x1800b3f5d  pop     r12
0x1800b3f5f  pop     rdi
0x1800b3f60  pop     rsi
0x1800b3f61  pop     rbp
0x1800b3f62  retn
0x1800b3f63  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
