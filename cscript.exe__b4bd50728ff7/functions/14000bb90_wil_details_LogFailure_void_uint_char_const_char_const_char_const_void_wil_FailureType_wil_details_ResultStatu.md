# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000bb90`
- end: `0x14000be88`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000ac38`

## callees

- `0x14000a674`
- `0x14000b49c`
- `0x14000b9cc`
- `0x14000bb90`
- `0x14000c154`
- `0x14000c170`
- `0x14000c184`
- `0x14000c1a0`
- `0x14000c9c4`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000bcb3`
- `KERNEL32!GetCurrentThreadId` at `0x14000bcb3`
- `KERNEL32!OutputDebugStringW` at `0x14000be44`
- `KERNEL32!OutputDebugStringW` at `0x14000be44`
- `KERNEL32!IsDebuggerPresent` at `0x14000bdd2`
- `KERNEL32!IsDebuggerPresent` at `0x14000bdd2`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x14000bb90  mov     [rsp+arg_10], rbx
0x14000bb95  mov     [rsp+arg_8], edx
0x14000bb99  mov     [rsp+arg_0], rcx
0x14000bb9e  push    rbp
0x14000bb9f  push    rsi
0x14000bba0  push    rdi
0x14000bba1  push    r12
0x14000bba3  push    r13
0x14000bba5  push    r14
0x14000bba7  push    r15
0x14000bba9  sub     rsp, 40h
0x14000bbad  mov     r14, [rsp+78h+arg_38]
0x14000bbb5  xor     eax, eax
0x14000bbb7  mov     rbx, [rsp+78h+arg_78]
0x14000bbbf  xor     ebp, ebp
0x14000bbc1  mov     r15d, [rsp+78h+arg_30]
0x14000bbc9  mov     r10, rcx
0x14000bbcc  mov     rsi, [rsp+78h+lpOutputString]
0x14000bbd4  mov     r12, r9
0x14000bbd7  mov     r13, r8
0x14000bbda  mov     ecx, r15d
0x14000bbdd  mov     [rsi], ax
0x14000bbe0  mov     rax, [rsp+78h+arg_60]
0x14000bbe8  mov     byte ptr [rax], 0
0x14000bbeb  mov     edi, [r14]
0x14000bbee  mov     [rbx+8], edi
0x14000bbf1  mov     eax, [r14+4]
0x14000bbf5  mov     [rbx+0Ch], eax
0x14000bbf8  test    r15d, r15d
0x14000bbfb  jz      short loc_14000BC63
0x14000bbfd  sub     ecx, 1
0x14000bc00  jz      short loc_14000BC5A
0x14000bc02  sub     ecx, 1
0x14000bc05  jz      short loc_14000BC15
0x14000bc07  cmp     ecx, 1
0x14000bc0a  jnz     short loc_14000BC6C
0x14000bc0c  mov     ecx, edi; this
0x14000bc0e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000bc13  jmp     short loc_14000BC6A
0x14000bc15  test    edi, edi
0x14000bc17  js      short loc_14000BC51
0x14000bc19  mov     rax, [rsp+78h+arg_28]
0x14000bc21  mov     edi, 8007029Ch
0x14000bc26  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000bc2a  mov     rcx, r10; int
0x14000bc2d  mov     [rsp+78h+var_50], rax; __int64
0x14000bc32  mov     rax, [rsp+78h+arg_20]
0x14000bc3a  mov     [rsp+78h+var_58], rax; __int64
0x14000bc3f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000bc44  mov     ecx, edi; this
0x14000bc46  mov     [rbx+8], edi
0x14000bc49  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000bc4e  mov     [rbx+0Ch], eax
0x14000bc51  mov     ecx, edi; this
0x14000bc53  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000bc58  jmp     short loc_14000BC6A
0x14000bc5a  mov     ecx, edi; this
0x14000bc5c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000bc61  jmp     short loc_14000BC6A
0x14000bc63  mov     ecx, edi; this
0x14000bc65  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000bc6a  mov     ebp, eax
0x14000bc6c  mov     eax, [rsp+78h+arg_70]
0x14000bc73  mov     [rbx+4], eax
0x14000bc76  mov     [rbx], r15d
0x14000bc79  cmp     dword ptr [r14+8], 1
0x14000bc7e  jnz     short loc_14000BC86
0x14000bc80  or      eax, 8
0x14000bc83  mov     [rbx+4], eax
0x14000bc86  mov     eax, 1
0x14000bc8b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000bc93  inc     eax
0x14000bc95  xor     edi, edi
0x14000bc97  mov     [rbx+10h], eax
0x14000bc9a  mov     rax, [rsp+78h+arg_40]
0x14000bca2  test    rax, rax
0x14000bca5  jz      short loc_14000BCAC
0x14000bca7  cmp     [rax], di
0x14000bcaa  jnz     short loc_14000BCAF
0x14000bcac  mov     rax, rdi
0x14000bcaf  mov     [rbx+18h], rax
0x14000bcb3  call    cs:__imp_GetCurrentThreadId
0x14000bcb9  mov     [rbx+38h], r13
0x14000bcbd  xorps   xmm0, xmm0
0x14000bcc0  mov     [rbx+20h], eax
0x14000bcc3  mov     eax, [rsp+78h+arg_8]
0x14000bcca  mov     [rbx+40h], eax
0x14000bccd  mov     rax, [rsp+78h+arg_20]
0x14000bcd5  mov     [rbx+28h], rax
0x14000bcd9  mov     rax, [rsp+78h+arg_28]
0x14000bce1  mov     [rbx+88h], rax
0x14000bce8  mov     rax, [rsp+78h+arg_0]
0x14000bcf0  mov     [rbx+90h], rax
0x14000bcf7  xor     eax, eax
0x14000bcf9  mov     [rbx+44h], ebp
0x14000bcfc  mov     [rbx+30h], r12
0x14000bd00  mov     [rbx+48h], rdi
0x14000bd04  movups  xmmword ptr [rbx+68h], xmm0
0x14000bd08  mov     [rbx+78h], rax
0x14000bd0c  movups  xmmword ptr [rbx+50h], xmm0
0x14000bd10  mov     [rbx+60h], rax
0x14000bd14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000bd1b  test    rax, rax
0x14000bd1e  jz      short loc_14000BD27
0x14000bd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd25  jmp     short loc_14000BD2A
0x14000bd27  mov     rax, rdi
0x14000bd2a  mov     [rbx+80h], rax
0x14000bd31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000bd38  test    rax, rax
0x14000bd3b  jz      short loc_14000BD45
0x14000bd3d  mov     rcx, rbx
0x14000bd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000bd4c  test    rax, rax
0x14000bd4f  jz      short loc_14000BD67
0x14000bd51  mov     rdx, [rsp+78h+arg_60]
0x14000bd59  mov     r8d, 400h
0x14000bd5f  mov     rcx, rbx
0x14000bd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000bd6e  test    rax, rax
0x14000bd71  jz      short loc_14000BD7B
0x14000bd73  mov     rcx, rbx
0x14000bd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000bd82  test    rax, rax
0x14000bd85  jz      short loc_14000BD95
0x14000bd87  test    byte ptr [rbx+4], 2
0x14000bd8b  jnz     short loc_14000BD95
0x14000bd8d  mov     rcx, rbx
0x14000bd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd95  cmp     [rbx+8], edi
0x14000bd98  jl      short loc_14000BDB4
0x14000bd9a  cmp     r15d, 3
0x14000bd9e  jnz     loc_14000BE82
0x14000bda4  mov     ecx, 8000FFFFh; this
0x14000bda9  mov     [rbx+8], ecx
0x14000bdac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000bdb1  mov     [rbx+0Ch], eax
0x14000bdb4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000bdbb  jnz     short loc_14000BDDC
0x14000bdbd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000bdc4  test    rax, rax
0x14000bdc7  jz      short loc_14000BDD2
0x14000bdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bdce  test    al, al
0x14000bdd0  jmp     short loc_14000BDDA
0x14000bdd2  call    cs:__imp_IsDebuggerPresent
0x14000bdd8  test    eax, eax
0x14000bdda  jz      short loc_14000BDE2
0x14000bddc  test    byte ptr [rbx+4], 2
0x14000bde0  jz      short loc_14000BE06
0x14000bde2  mov     rax, cs:g_pfnResultLoggingCallback
0x14000bde9  test    rax, rax
0x14000bdec  jz      short loc_14000BE4A
0x14000bdee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000bdf5  jnz     short loc_14000BE4A
0x14000bdf7  xor     r8d, r8d
0x14000bdfa  xor     edx, edx
0x14000bdfc  mov     rcx, rbx
0x14000bdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be04  jmp     short loc_14000BE4A
0x14000be06  mov     rax, cs:g_pfnResultLoggingCallback
0x14000be0d  mov     ebp, 800h
0x14000be12  test    rax, rax
0x14000be15  jz      short loc_14000BE2E
0x14000be17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000be1e  jnz     short loc_14000BE2E
0x14000be20  mov     r8d, ebp
0x14000be23  mov     rdx, rsi
0x14000be26  mov     rcx, rbx
0x14000be29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be2e  cmp     [rsi], di
0x14000be31  jnz     short loc_14000BE41
0x14000be33  mov     r8, rbx; unsigned __int64
0x14000be36  mov     rdx, rbp; unsigned __int16 *
0x14000be39  mov     rcx, rsi; this
0x14000be3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000be41  mov     rcx, rsi; lpOutputString
0x14000be44  call    cs:__imp_OutputDebugStringW
0x14000be4a  test    byte ptr [rbx+4], 4
0x14000be4e  jnz     short loc_14000BE59
0x14000be50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000be57  jz      short loc_14000BE6A
0x14000be59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000be60  test    rax, rax
0x14000be63  jz      short loc_14000BE6A
0x14000be65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be6a  mov     rbx, [rsp+78h+arg_10]
0x14000be72  add     rsp, 40h
0x14000be76  pop     r15
0x14000be78  pop     r14
0x14000be7a  pop     r13
0x14000be7c  pop     r12
0x14000be7e  pop     rdi
0x14000be7f  pop     rsi
0x14000be80  pop     rbp
0x14000be81  retn
0x14000be82  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
