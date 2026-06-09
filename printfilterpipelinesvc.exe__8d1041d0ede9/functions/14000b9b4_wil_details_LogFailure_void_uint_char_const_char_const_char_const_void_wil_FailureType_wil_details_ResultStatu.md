# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000b9b4`
- end: `0x14000bc8e`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `730`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x140008b00`
- `0x140008bb0`
- `0x140008ca4`

## callees

- `0x140008a54`
- `0x14000ab34`
- `0x14000b33c`
- `0x14000b75c`
- `0x14000b9b4`
- `0x14000c8a4`
- `0x14000c8c0`
- `0x14000ca44`
- `0x14000ca60`
- `0x14000e998`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000badb`
- `KERNEL32!GetCurrentThreadId` at `0x14000badb`
- `KERNEL32!OutputDebugStringW` at `0x14000bc2b`
- `KERNEL32!OutputDebugStringW` at `0x14000bc2b`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v26; // r9
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v26);
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
0x14000b9b4  mov     [rsp+arg_10], rbx
0x14000b9b9  mov     [rsp+arg_8], edx
0x14000b9bd  mov     [rsp+arg_0], rcx
0x14000b9c2  push    rbp
0x14000b9c3  push    rsi
0x14000b9c4  push    rdi
0x14000b9c5  push    r12
0x14000b9c7  push    r13
0x14000b9c9  push    r14
0x14000b9cb  push    r15
0x14000b9cd  sub     rsp, 40h
0x14000b9d1  mov     r12, r9
0x14000b9d4  mov     r13, r8
0x14000b9d7  mov     r10, rcx
0x14000b9da  xor     eax, eax
0x14000b9dc  mov     rsi, [rsp+78h+lpOutputString]
0x14000b9e4  mov     [rsi], ax
0x14000b9e7  mov     rax, [rsp+78h+arg_60]
0x14000b9ef  mov     byte ptr [rax], 0
0x14000b9f2  mov     r14, [rsp+78h+arg_38]
0x14000b9fa  mov     edi, [r14]
0x14000b9fd  mov     rbx, [rsp+78h+arg_78]
0x14000ba05  mov     [rbx+8], edi
0x14000ba08  mov     eax, [r14+4]
0x14000ba0c  mov     [rbx+0Ch], eax
0x14000ba0f  xor     ebp, ebp
0x14000ba11  mov     r15d, [rsp+78h+arg_30]
0x14000ba19  mov     ecx, r15d
0x14000ba1c  test    r15d, r15d
0x14000ba1f  jz      short loc_14000BA8B
0x14000ba21  sub     ecx, 1
0x14000ba24  jz      short loc_14000BA82
0x14000ba26  sub     ecx, 1
0x14000ba29  jz      short loc_14000BA39
0x14000ba2b  cmp     ecx, 1
0x14000ba2e  jnz     short loc_14000BA94
0x14000ba30  mov     ecx, edi; this
0x14000ba32  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000ba37  jmp     short loc_14000BA92
0x14000ba39  test    edi, edi
0x14000ba3b  js      short loc_14000BA79
0x14000ba3d  mov     [rsp+78h+var_40], ebp
0x14000ba41  mov     edi, 8007029Ch
0x14000ba46  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000ba4a  mov     rax, [rsp+78h+arg_28]
0x14000ba52  mov     [rsp+78h+var_50], rax; __int64
0x14000ba57  mov     rax, [rsp+78h+arg_20]
0x14000ba5f  mov     [rsp+78h+var_58], rax; __int64
0x14000ba64  mov     rcx, r10; int
0x14000ba67  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000ba6c  mov     [rbx+8], edi
0x14000ba6f  mov     ecx, edi; this
0x14000ba71  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000ba76  mov     [rbx+0Ch], eax
0x14000ba79  mov     ecx, edi; this
0x14000ba7b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000ba80  jmp     short loc_14000BA92
0x14000ba82  mov     ecx, edi; this
0x14000ba84  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000ba89  jmp     short loc_14000BA92
0x14000ba8b  mov     ecx, edi; this
0x14000ba8d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000ba92  mov     ebp, eax
0x14000ba94  mov     [rbx], r15d
0x14000ba97  mov     eax, [rsp+78h+arg_70]
0x14000ba9e  mov     [rbx+4], eax
0x14000baa1  cmp     dword ptr [r14+8], 1
0x14000baa6  jnz     short loc_14000BAAE
0x14000baa8  or      eax, 8
0x14000baab  mov     [rbx+4], eax
0x14000baae  mov     eax, 1
0x14000bab3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000babb  inc     eax
0x14000babd  mov     [rbx+10h], eax
0x14000bac0  mov     rax, [rsp+78h+arg_40]
0x14000bac8  xor     edi, edi
0x14000baca  test    rax, rax
0x14000bacd  jz      short loc_14000BAD4
0x14000bacf  cmp     [rax], di
0x14000bad2  jnz     short loc_14000BAD7
0x14000bad4  mov     rax, rdi
0x14000bad7  mov     [rbx+18h], rax
0x14000badb  call    cs:__imp_GetCurrentThreadId
0x14000bae1  mov     [rbx+20h], eax
0x14000bae4  mov     [rbx+38h], r13
0x14000bae8  mov     eax, [rsp+78h+arg_8]
0x14000baef  mov     [rbx+40h], eax
0x14000baf2  mov     [rbx+44h], ebp
0x14000baf5  mov     rax, [rsp+78h+arg_20]
0x14000bafd  mov     [rbx+28h], rax
0x14000bb01  mov     [rbx+30h], r12
0x14000bb05  mov     rax, [rsp+78h+arg_28]
0x14000bb0d  mov     [rbx+88h], rax
0x14000bb14  mov     rax, [rsp+78h+arg_0]
0x14000bb1c  mov     [rbx+90h], rax
0x14000bb23  mov     [rbx+48h], rdi
0x14000bb27  xorps   xmm0, xmm0
0x14000bb2a  xor     eax, eax
0x14000bb2c  movups  xmmword ptr [rbx+68h], xmm0
0x14000bb30  mov     [rbx+78h], rax
0x14000bb34  movups  xmmword ptr [rbx+50h], xmm0
0x14000bb38  mov     [rbx+60h], rax
0x14000bb3c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000bb43  test    rax, rax
0x14000bb46  jz      short loc_14000BB4F
0x14000bb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb4d  jmp     short loc_14000BB52
0x14000bb4f  mov     rax, rdi
0x14000bb52  mov     [rbx+80h], rax
0x14000bb59  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000bb60  test    rax, rax
0x14000bb63  jz      short loc_14000BB6D
0x14000bb65  mov     rcx, rbx
0x14000bb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb6d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000bb74  test    rax, rax
0x14000bb77  jz      short loc_14000BB8F
0x14000bb79  mov     r8d, 400h
0x14000bb7f  mov     rdx, [rsp+78h+arg_60]
0x14000bb87  mov     rcx, rbx
0x14000bb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb8f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000bb96  test    rax, rax
0x14000bb99  jz      short loc_14000BBA3
0x14000bb9b  mov     rcx, rbx
0x14000bb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bba3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000bbaa  test    rax, rax
0x14000bbad  jz      short loc_14000BBBD
0x14000bbaf  test    byte ptr [rbx+4], 2
0x14000bbb3  jnz     short loc_14000BBBD
0x14000bbb5  mov     rcx, rbx
0x14000bbb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bbbd  cmp     [rbx+8], edi
0x14000bbc0  jl      short loc_14000BBDE
0x14000bbc2  cmp     r15d, 3
0x14000bbc6  jz      short loc_14000BBCE
0x14000bbc8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000bbce  mov     ecx, 8000FFFFh; this
0x14000bbd3  mov     [rbx+8], ecx
0x14000bbd6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000bbdb  mov     [rbx+0Ch], eax
0x14000bbde  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x14000bbe3  test    al, al
0x14000bbe5  jz      short loc_14000BC33
0x14000bbe7  test    byte ptr [rbx+4], 2
0x14000bbeb  jnz     short loc_14000BC33
0x14000bbed  mov     ebp, 800h
0x14000bbf2  mov     rax, cs:g_pfnResultLoggingCallback
0x14000bbf9  test    rax, rax
0x14000bbfc  jz      short loc_14000BC15
0x14000bbfe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000bc05  jnz     short loc_14000BC15
0x14000bc07  mov     r8d, ebp
0x14000bc0a  mov     rdx, rsi
0x14000bc0d  mov     rcx, rbx
0x14000bc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc15  cmp     [rsi], di
0x14000bc18  jnz     short loc_14000BC28
0x14000bc1a  mov     r8, rbx; unsigned __int64
0x14000bc1d  mov     rdx, rbp; wchar_t *
0x14000bc20  mov     rcx, rsi; this
0x14000bc23  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000bc28  mov     rcx, rsi; lpOutputString
0x14000bc2b  call    cs:__imp_OutputDebugStringW
0x14000bc31  jmp     short loc_14000BC55
0x14000bc33  mov     rax, cs:g_pfnResultLoggingCallback
0x14000bc3a  test    rax, rax
0x14000bc3d  jz      short loc_14000BC55
0x14000bc3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000bc46  jnz     short loc_14000BC55
0x14000bc48  xor     r8d, r8d
0x14000bc4b  xor     edx, edx
0x14000bc4d  mov     rcx, rbx
0x14000bc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc55  test    byte ptr [rbx+4], 4
0x14000bc59  jnz     short loc_14000BC64
0x14000bc5b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000bc62  jz      short loc_14000BC76
0x14000bc64  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000bc6b  test    rax, rax
0x14000bc6e  jz      short loc_14000BC76
0x14000bc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc75  nop
0x14000bc76  mov     rbx, [rsp+78h+arg_10]
0x14000bc7e  add     rsp, 40h
0x14000bc82  pop     r15
0x14000bc84  pop     r14
0x14000bc86  pop     r13
0x14000bc88  pop     r12
0x14000bc8a  pop     rdi
0x14000bc8b  pop     rsi
0x14000bc8c  pop     rbp
0x14000bc8d  retn
```
