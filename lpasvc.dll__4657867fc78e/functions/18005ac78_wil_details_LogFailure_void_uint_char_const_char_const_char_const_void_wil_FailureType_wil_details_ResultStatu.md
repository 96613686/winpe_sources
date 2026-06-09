# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005ac78`
- end: `0x18005af71`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180058784`
- `0x180099d28`

## callees

- `0x180058190`
- `0x180059fb4`
- `0x18005a868`
- `0x18005ac78`
- `0x18005ba94`
- `0x18005bab0`
- `0x18005bc34`
- `0x18005bc50`
- `0x18005d994`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ad9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ad9b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005aeba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005aeba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005af2c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005af2c`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x18005ac78  mov     [rsp+arg_10], rbx
0x18005ac7d  mov     [rsp+arg_8], edx
0x18005ac81  mov     [rsp+arg_0], rcx
0x18005ac86  push    rbp
0x18005ac87  push    rsi
0x18005ac88  push    rdi
0x18005ac89  push    r12
0x18005ac8b  push    r13
0x18005ac8d  push    r14
0x18005ac8f  push    r15
0x18005ac91  sub     rsp, 40h
0x18005ac95  mov     r12, r9
0x18005ac98  mov     r13, r8
0x18005ac9b  mov     r10, rcx
0x18005ac9e  xor     eax, eax
0x18005aca0  mov     rsi, [rsp+78h+lpOutputString]
0x18005aca8  mov     [rsi], ax
0x18005acab  mov     rax, [rsp+78h+arg_60]
0x18005acb3  mov     byte ptr [rax], 0
0x18005acb6  mov     r14, [rsp+78h+arg_38]
0x18005acbe  mov     edi, [r14]
0x18005acc1  mov     rbx, [rsp+78h+arg_78]
0x18005acc9  mov     [rbx+8], edi
0x18005accc  mov     eax, [r14+4]
0x18005acd0  mov     [rbx+0Ch], eax
0x18005acd3  xor     ebp, ebp
0x18005acd5  mov     r15d, [rsp+78h+arg_30]
0x18005acdd  mov     ecx, r15d
0x18005ace0  test    r15d, r15d
0x18005ace3  jz      short loc_18005AD4B
0x18005ace5  sub     ecx, 1
0x18005ace8  jz      short loc_18005AD42
0x18005acea  sub     ecx, 1
0x18005aced  jz      short loc_18005ACFD
0x18005acef  cmp     ecx, 1
0x18005acf2  jnz     short loc_18005AD54
0x18005acf4  mov     ecx, edi; this
0x18005acf6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005acfb  jmp     short loc_18005AD52
0x18005acfd  test    edi, edi
0x18005acff  js      short loc_18005AD39
0x18005ad01  mov     edi, 8007029Ch
0x18005ad06  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005ad0a  mov     rax, [rsp+78h+arg_28]
0x18005ad12  mov     [rsp+78h+var_50], rax; __int64
0x18005ad17  mov     rax, [rsp+78h+arg_20]
0x18005ad1f  mov     [rsp+78h+var_58], rax; __int64
0x18005ad24  mov     rcx, r10; int
0x18005ad27  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18005ad2c  mov     [rbx+8], edi
0x18005ad2f  mov     ecx, edi; this
0x18005ad31  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005ad36  mov     [rbx+0Ch], eax
0x18005ad39  mov     ecx, edi; this
0x18005ad3b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005ad40  jmp     short loc_18005AD52
0x18005ad42  mov     ecx, edi; this
0x18005ad44  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005ad49  jmp     short loc_18005AD52
0x18005ad4b  mov     ecx, edi; this
0x18005ad4d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005ad52  mov     ebp, eax
0x18005ad54  mov     [rbx], r15d
0x18005ad57  mov     eax, [rsp+78h+arg_70]
0x18005ad5e  mov     [rbx+4], eax
0x18005ad61  cmp     dword ptr [r14+8], 1
0x18005ad66  jnz     short loc_18005AD6E
0x18005ad68  or      eax, 8
0x18005ad6b  mov     [rbx+4], eax
0x18005ad6e  mov     eax, 1
0x18005ad73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005ad7b  inc     eax
0x18005ad7d  mov     [rbx+10h], eax
0x18005ad80  mov     rax, [rsp+78h+arg_40]
0x18005ad88  xor     edi, edi
0x18005ad8a  test    rax, rax
0x18005ad8d  jz      short loc_18005AD94
0x18005ad8f  cmp     [rax], di
0x18005ad92  jnz     short loc_18005AD97
0x18005ad94  mov     rax, rdi
0x18005ad97  mov     [rbx+18h], rax
0x18005ad9b  call    cs:__imp_GetCurrentThreadId
0x18005ada1  mov     [rbx+20h], eax
0x18005ada4  mov     [rbx+38h], r13
0x18005ada8  mov     eax, [rsp+78h+arg_8]
0x18005adaf  mov     [rbx+40h], eax
0x18005adb2  mov     [rbx+44h], ebp
0x18005adb5  mov     rax, [rsp+78h+arg_20]
0x18005adbd  mov     [rbx+28h], rax
0x18005adc1  mov     [rbx+30h], r12
0x18005adc5  mov     rax, [rsp+78h+arg_28]
0x18005adcd  mov     [rbx+88h], rax
0x18005add4  mov     rax, [rsp+78h+arg_0]
0x18005addc  mov     [rbx+90h], rax
0x18005ade3  mov     [rbx+48h], rdi
0x18005ade7  xorps   xmm0, xmm0
0x18005adea  xor     eax, eax
0x18005adec  movups  xmmword ptr [rbx+68h], xmm0
0x18005adf0  mov     [rbx+78h], rax
0x18005adf4  movups  xmmword ptr [rbx+50h], xmm0
0x18005adf8  mov     [rbx+60h], rax
0x18005adfc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005ae03  test    rax, rax
0x18005ae06  jz      short loc_18005AE0F
0x18005ae08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae0d  jmp     short loc_18005AE12
0x18005ae0f  mov     rax, rdi
0x18005ae12  mov     [rbx+80h], rax
0x18005ae19  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005ae20  test    rax, rax
0x18005ae23  jz      short loc_18005AE2D
0x18005ae25  mov     rcx, rbx
0x18005ae28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005ae34  test    rax, rax
0x18005ae37  jz      short loc_18005AE4F
0x18005ae39  mov     r8d, 400h
0x18005ae3f  mov     rdx, [rsp+78h+arg_60]
0x18005ae47  mov     rcx, rbx
0x18005ae4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae4f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005ae56  test    rax, rax
0x18005ae59  jz      short loc_18005AE63
0x18005ae5b  mov     rcx, rbx
0x18005ae5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005ae6a  test    rax, rax
0x18005ae6d  jz      short loc_18005AE7D
0x18005ae6f  test    byte ptr [rbx+4], 2
0x18005ae73  jnz     short loc_18005AE7D
0x18005ae75  mov     rcx, rbx
0x18005ae78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae7d  cmp     [rbx+8], edi
0x18005ae80  jl      short loc_18005AE9C
0x18005ae82  cmp     r15d, 3
0x18005ae86  jnz     loc_18005AF6B
0x18005ae8c  mov     ecx, 8000FFFFh; this
0x18005ae91  mov     [rbx+8], ecx
0x18005ae94  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005ae99  mov     [rbx+0Ch], eax
0x18005ae9c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005aea3  jnz     short loc_18005AEC4
0x18005aea5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005aeac  test    rax, rax
0x18005aeaf  jz      short loc_18005AEBA
0x18005aeb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aeb6  test    al, al
0x18005aeb8  jmp     short loc_18005AEC2
0x18005aeba  call    cs:__imp_IsDebuggerPresent
0x18005aec0  test    eax, eax
0x18005aec2  jz      short loc_18005AECA
0x18005aec4  test    byte ptr [rbx+4], 2
0x18005aec8  jz      short loc_18005AEEE
0x18005aeca  mov     rax, cs:g_pfnResultLoggingCallback
0x18005aed1  test    rax, rax
0x18005aed4  jz      short loc_18005AF32
0x18005aed6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005aedd  jnz     short loc_18005AF32
0x18005aedf  xor     r8d, r8d
0x18005aee2  xor     edx, edx
0x18005aee4  mov     rcx, rbx
0x18005aee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aeec  jmp     short loc_18005AF32
0x18005aeee  mov     ebp, 800h
0x18005aef3  mov     rax, cs:g_pfnResultLoggingCallback
0x18005aefa  test    rax, rax
0x18005aefd  jz      short loc_18005AF16
0x18005aeff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005af06  jnz     short loc_18005AF16
0x18005af08  mov     r8d, ebp
0x18005af0b  mov     rdx, rsi
0x18005af0e  mov     rcx, rbx
0x18005af11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af16  cmp     [rsi], di
0x18005af19  jnz     short loc_18005AF29
0x18005af1b  mov     r8, rbx; unsigned __int64
0x18005af1e  mov     rdx, rbp; unsigned __int16 *
0x18005af21  mov     rcx, rsi; this
0x18005af24  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005af29  mov     rcx, rsi; lpOutputString
0x18005af2c  call    cs:__imp_OutputDebugStringW
0x18005af32  test    byte ptr [rbx+4], 4
0x18005af36  jnz     short loc_18005AF41
0x18005af38  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005af3f  jz      short loc_18005AF53
0x18005af41  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005af48  test    rax, rax
0x18005af4b  jz      short loc_18005AF53
0x18005af4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af52  nop
0x18005af53  mov     rbx, [rsp+78h+arg_10]
0x18005af5b  add     rsp, 40h
0x18005af5f  pop     r15
0x18005af61  pop     r14
0x18005af63  pop     r13
0x18005af65  pop     r12
0x18005af67  pop     rdi
0x18005af68  pop     rsi
0x18005af69  pop     rbp
0x18005af6a  retn
0x18005af6b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
