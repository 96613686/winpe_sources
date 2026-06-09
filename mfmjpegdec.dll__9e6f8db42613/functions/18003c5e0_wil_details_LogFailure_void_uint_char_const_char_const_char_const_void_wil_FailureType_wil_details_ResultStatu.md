# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003c5e0`
- end: `0x18003c8d4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18003aa58`
- `0x18003ab0c`
- `0x18003ac00`

## callees

- `0x18003a9ac`
- `0x18003bc34`
- `0x18003c41c`
- `0x18003c5e0`
- `0x18003cce0`
- `0x18003cd00`
- `0x18003cd14`
- `0x18003cd30`
- `0x18003dafc`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c703`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c896`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c896`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c824`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c824`

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
0x18003c5e0  mov     [rsp+arg_10], rbx
0x18003c5e5  mov     [rsp+arg_8], edx
0x18003c5e9  mov     [rsp+arg_0], rcx
0x18003c5ee  push    rbp
0x18003c5ef  push    rsi
0x18003c5f0  push    rdi
0x18003c5f1  push    r12
0x18003c5f3  push    r13
0x18003c5f5  push    r14
0x18003c5f7  push    r15
0x18003c5f9  sub     rsp, 40h
0x18003c5fd  mov     r14, [rsp+78h+arg_38]
0x18003c605  xor     eax, eax
0x18003c607  mov     rbx, [rsp+78h+arg_78]
0x18003c60f  xor     ebp, ebp
0x18003c611  mov     r15d, [rsp+78h+arg_30]
0x18003c619  mov     r10, rcx
0x18003c61c  mov     rsi, [rsp+78h+lpOutputString]
0x18003c624  mov     r12, r9
0x18003c627  mov     r13, r8
0x18003c62a  mov     ecx, r15d
0x18003c62d  mov     [rsi], ax
0x18003c630  mov     rax, [rsp+78h+arg_60]
0x18003c638  mov     byte ptr [rax], 0
0x18003c63b  mov     edi, [r14]
0x18003c63e  mov     [rbx+8], edi
0x18003c641  mov     eax, [r14+4]
0x18003c645  mov     [rbx+0Ch], eax
0x18003c648  test    r15d, r15d
0x18003c64b  jz      short loc_18003C6B3
0x18003c64d  sub     ecx, 1
0x18003c650  jz      short loc_18003C6AA
0x18003c652  sub     ecx, 1
0x18003c655  jz      short loc_18003C665
0x18003c657  cmp     ecx, 1
0x18003c65a  jnz     short loc_18003C6BC
0x18003c65c  mov     ecx, edi; this
0x18003c65e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003c663  jmp     short loc_18003C6BA
0x18003c665  test    edi, edi
0x18003c667  js      short loc_18003C6A1
0x18003c669  mov     rax, [rsp+78h+arg_28]
0x18003c671  mov     edi, 8007029Ch
0x18003c676  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003c67a  mov     rcx, r10; int
0x18003c67d  mov     [rsp+78h+var_50], rax; __int64
0x18003c682  mov     rax, [rsp+78h+arg_20]
0x18003c68a  mov     [rsp+78h+var_58], rax; __int64
0x18003c68f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003c694  mov     ecx, edi; this
0x18003c696  mov     [rbx+8], edi
0x18003c699  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c69e  mov     [rbx+0Ch], eax
0x18003c6a1  mov     ecx, edi; this
0x18003c6a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003c6a8  jmp     short loc_18003C6BA
0x18003c6aa  mov     ecx, edi; this
0x18003c6ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003c6b1  jmp     short loc_18003C6BA
0x18003c6b3  mov     ecx, edi; this
0x18003c6b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003c6ba  mov     ebp, eax
0x18003c6bc  mov     eax, [rsp+78h+arg_70]
0x18003c6c3  mov     [rbx+4], eax
0x18003c6c6  mov     [rbx], r15d
0x18003c6c9  cmp     dword ptr [r14+8], 1
0x18003c6ce  jnz     short loc_18003C6D6
0x18003c6d0  or      eax, 8
0x18003c6d3  mov     [rbx+4], eax
0x18003c6d6  mov     eax, 1
0x18003c6db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003c6e3  inc     eax
0x18003c6e5  xor     edi, edi
0x18003c6e7  mov     [rbx+10h], eax
0x18003c6ea  mov     rax, [rsp+78h+arg_40]
0x18003c6f2  test    rax, rax
0x18003c6f5  jz      short loc_18003C6FC
0x18003c6f7  cmp     [rax], di
0x18003c6fa  jnz     short loc_18003C6FF
0x18003c6fc  mov     rax, rdi
0x18003c6ff  mov     [rbx+18h], rax
0x18003c703  call    cs:__imp_GetCurrentThreadId
0x18003c709  mov     [rbx+38h], r13
0x18003c70d  xorps   xmm0, xmm0
0x18003c710  mov     [rbx+20h], eax
0x18003c713  mov     eax, [rsp+78h+arg_8]
0x18003c71a  mov     [rbx+40h], eax
0x18003c71d  mov     rax, [rsp+78h+arg_20]
0x18003c725  mov     [rbx+28h], rax
0x18003c729  mov     rax, [rsp+78h+arg_28]
0x18003c731  mov     [rbx+88h], rax
0x18003c738  mov     rax, [rsp+78h+arg_0]
0x18003c740  mov     [rbx+90h], rax
0x18003c747  xor     eax, eax
0x18003c749  mov     [rbx+44h], ebp
0x18003c74c  mov     [rbx+30h], r12
0x18003c750  mov     [rbx+48h], rdi
0x18003c754  movups  xmmword ptr [rbx+68h], xmm0
0x18003c758  mov     [rbx+78h], rax
0x18003c75c  movups  xmmword ptr [rbx+50h], xmm0
0x18003c760  mov     [rbx+60h], rax
0x18003c764  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003c76b  test    rax, rax
0x18003c76e  jz      short loc_18003C777
0x18003c770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c775  jmp     short loc_18003C77A
0x18003c777  mov     rax, rdi
0x18003c77a  mov     [rbx+80h], rax
0x18003c781  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c788  test    rax, rax
0x18003c78b  jz      short loc_18003C795
0x18003c78d  mov     rcx, rbx
0x18003c790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c795  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c79c  test    rax, rax
0x18003c79f  jz      short loc_18003C7B7
0x18003c7a1  mov     rdx, [rsp+78h+arg_60]
0x18003c7a9  mov     r8d, 400h
0x18003c7af  mov     rcx, rbx
0x18003c7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c7be  test    rax, rax
0x18003c7c1  jz      short loc_18003C7CB
0x18003c7c3  mov     rcx, rbx
0x18003c7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c7d2  test    rax, rax
0x18003c7d5  jz      short loc_18003C7E5
0x18003c7d7  test    byte ptr [rbx+4], 2
0x18003c7db  jnz     short loc_18003C7E5
0x18003c7dd  mov     rcx, rbx
0x18003c7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7e5  cmp     [rbx+8], edi
0x18003c7e8  jl      short loc_18003C806
0x18003c7ea  cmp     r15d, 3
0x18003c7ee  jz      short loc_18003C7F6
0x18003c7f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003c7f6  mov     ecx, 8000FFFFh; this
0x18003c7fb  mov     [rbx+8], ecx
0x18003c7fe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c803  mov     [rbx+0Ch], eax
0x18003c806  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003c80d  jnz     short loc_18003C82E
0x18003c80f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c816  test    rax, rax
0x18003c819  jz      short loc_18003C824
0x18003c81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c820  test    al, al
0x18003c822  jmp     short loc_18003C82C
0x18003c824  call    cs:__imp_IsDebuggerPresent
0x18003c82a  test    eax, eax
0x18003c82c  jz      short loc_18003C834
0x18003c82e  test    byte ptr [rbx+4], 2
0x18003c832  jz      short loc_18003C858
0x18003c834  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c83b  test    rax, rax
0x18003c83e  jz      short loc_18003C89C
0x18003c840  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003c847  jnz     short loc_18003C89C
0x18003c849  xor     r8d, r8d
0x18003c84c  xor     edx, edx
0x18003c84e  mov     rcx, rbx
0x18003c851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c856  jmp     short loc_18003C89C
0x18003c858  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c85f  mov     ebp, 800h
0x18003c864  test    rax, rax
0x18003c867  jz      short loc_18003C880
0x18003c869  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003c870  jnz     short loc_18003C880
0x18003c872  mov     r8d, ebp
0x18003c875  mov     rdx, rsi
0x18003c878  mov     rcx, rbx
0x18003c87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c880  cmp     [rsi], di
0x18003c883  jnz     short loc_18003C893
0x18003c885  mov     r8, rbx; unsigned __int64
0x18003c888  mov     rdx, rbp; unsigned __int16 *
0x18003c88b  mov     rcx, rsi; this
0x18003c88e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003c893  mov     rcx, rsi; lpOutputString
0x18003c896  call    cs:__imp_OutputDebugStringW
0x18003c89c  test    byte ptr [rbx+4], 4
0x18003c8a0  jnz     short loc_18003C8AB
0x18003c8a2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003c8a9  jz      short loc_18003C8BC
0x18003c8ab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c8b2  test    rax, rax
0x18003c8b5  jz      short loc_18003C8BC
0x18003c8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8bc  mov     rbx, [rsp+78h+arg_10]
0x18003c8c4  add     rsp, 40h
0x18003c8c8  pop     r15
0x18003c8ca  pop     r14
0x18003c8cc  pop     r13
0x18003c8ce  pop     r12
0x18003c8d0  pop     rdi
0x18003c8d1  pop     rsi
0x18003c8d2  pop     rbp
0x18003c8d3  retn
```
