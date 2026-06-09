# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180015604`
- end: `0x1800158aa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013ab8`

## callees

- `0x18001309c`
- `0x180014130`
- `0x180014ff0`
- `0x180015604`
- `0x180017124`
- `0x180018ad0`
- `0x18001a580`
- `0x180023310`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015849`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015849`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800157bf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800157bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180015604  push    rbp
0x180015606  push    rbx
0x180015607  push    rsi
0x180015608  push    rdi
0x180015609  push    r12
0x18001560b  push    r14
0x18001560d  push    r15
0x18001560f  lea     rbp, [rsp-13D0h]
0x180015617  mov     eax, 14D0h
0x18001561c  call    _alloca_probe
0x180015621  sub     rsp, rax
0x180015624  mov     rax, cs:__security_cookie
0x18001562b  xor     rax, rsp
0x18001562e  mov     [rbp+1400h+var_40], rax
0x180015635  mov     rsi, r8
0x180015638  mov     edi, edx
0x18001563a  mov     rbx, rcx
0x18001563d  mov     r14, [rbp+1400h+arg_28]
0x180015644  xor     edx, edx; Val
0x180015646  mov     r8d, 98h; Size
0x18001564c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180015651  call    memset_0
0x180015656  nop
0x180015657  xor     r12d, r12d
0x18001565a  mov     [rbp+1400h+OutputString], r12w
0x180015662  mov     [rbp+1400h+var_1440], r12b
0x180015666  mov     rdx, [rbp+1400h+arg_30]; int
0x18001566d  mov     ecx, [rdx]; this
0x18001566f  mov     [rsp+1500h+var_14D8], ecx
0x180015673  mov     eax, [rdx+4]
0x180015676  mov     [rsp+1500h+var_14D4], eax
0x18001567a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001567f  mov     r15d, eax
0x180015682  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001568a  mov     ecx, r12d
0x18001568d  lea     eax, [r12+8]
0x180015692  cmp     dword ptr [rdx+8], 1
0x180015696  cmovz   ecx, eax
0x180015699  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18001569d  lea     ecx, [rax-7]
0x1800156a0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800156a8  inc     ecx
0x1800156aa  mov     [rsp+1500h+var_14D0], ecx
0x1800156ae  mov     rcx, [rbp+1400h+arg_38]
0x1800156b5  test    rcx, rcx
0x1800156b8  jz      short loc_1800156C5
0x1800156ba  cmp     [rcx], r12w
0x1800156be  mov     [rsp+1500h+var_14C8], rcx
0x1800156c3  jnz     short loc_1800156CA
0x1800156c5  mov     [rsp+1500h+var_14C8], r12
0x1800156ca  call    cs:__imp_GetCurrentThreadId
0x1800156d0  mov     [rsp+1500h+var_14C0], eax
0x1800156d4  mov     [rsp+1500h+var_14A8], rsi
0x1800156d9  mov     [rsp+1500h+var_14A0], edi
0x1800156dd  mov     [rsp+1500h+var_149C], r15d
0x1800156e2  mov     [rsp+1500h+var_14B8], r12
0x1800156e7  mov     [rsp+1500h+var_14B0], r12
0x1800156ec  mov     [rbp+1400h+var_1458], r14
0x1800156f0  mov     [rbp+1400h+var_1450], rbx
0x1800156f4  mov     [rsp+1500h+var_1498], r12
0x1800156f9  xorps   xmm0, xmm0
0x1800156fc  xor     eax, eax
0x1800156fe  movups  [rbp+1400h+var_1478], xmm0
0x180015702  mov     [rbp+1400h+var_1468], rax
0x180015706  xorps   xmm1, xmm1
0x180015709  movups  [rsp+1500h+var_1490], xmm1
0x18001570e  mov     [rbp+1400h+var_1480], rax
0x180015712  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015719  test    rax, rax
0x18001571c  jz      short loc_180015729
0x18001571e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015723  mov     [rbp+1400h+var_1460], rax
0x180015727  jmp     short loc_18001572D
0x180015729  mov     [rbp+1400h+var_1460], r12
0x18001572d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015734  test    rax, rax
0x180015737  jz      short loc_180015743
0x180015739  lea     rcx, [rsp+1500h+var_14E0]
0x18001573e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015743  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001574a  test    rax, rax
0x18001574d  jz      short loc_180015763
0x18001574f  mov     r8d, 400h
0x180015755  lea     rdx, [rbp+1400h+var_1440]
0x180015759  lea     rcx, [rsp+1500h+var_14E0]
0x18001575e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015763  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001576a  test    rax, rax
0x18001576d  jz      short loc_180015779
0x18001576f  lea     rcx, [rsp+1500h+var_14E0]
0x180015774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015779  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015780  test    rax, rax
0x180015783  jz      short loc_180015796
0x180015785  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001578a  jnz     short loc_180015796
0x18001578c  lea     rcx, [rsp+1500h+var_14E0]
0x180015791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015796  cmp     [rsp+1500h+var_14D8], r12d
0x18001579b  jge     loc_1800158A4
0x1800157a1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800157a8  jnz     short loc_1800157C9
0x1800157aa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800157b1  test    rax, rax
0x1800157b4  jz      short loc_1800157BF
0x1800157b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157bb  test    al, al
0x1800157bd  jmp     short loc_1800157C7
0x1800157bf  call    cs:__imp_IsDebuggerPresent
0x1800157c5  test    eax, eax
0x1800157c7  jz      short loc_1800157D0
0x1800157c9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800157ce  jz      short loc_1800157F6
0x1800157d0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800157d7  test    rax, rax
0x1800157da  jz      short loc_18001584F
0x1800157dc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800157e3  jnz     short loc_18001584F
0x1800157e5  xor     r8d, r8d
0x1800157e8  xor     edx, edx
0x1800157ea  lea     rcx, [rsp+1500h+var_14E0]
0x1800157ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f4  jmp     short loc_18001584F
0x1800157f6  mov     ebx, 800h
0x1800157fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180015802  test    rax, rax
0x180015805  jz      short loc_180015824
0x180015807  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001580e  jnz     short loc_180015824
0x180015810  mov     r8d, ebx
0x180015813  lea     rdx, [rbp+1400h+OutputString]
0x18001581a  lea     rcx, [rsp+1500h+var_14E0]
0x18001581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015824  cmp     [rbp+1400h+OutputString], r12w
0x18001582c  jnz     short loc_180015842
0x18001582e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180015833  mov     rdx, rbx; wchar_t *
0x180015836  lea     rcx, [rbp+1400h+OutputString]; this
0x18001583d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180015842  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180015849  call    cs:__imp_OutputDebugStringW
0x18001584f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180015854  jnz     short loc_18001585F
0x180015856  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001585d  jz      short loc_180015871
0x18001585f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015866  test    rax, rax
0x180015869  jz      short loc_180015871
0x18001586b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015870  nop
0x180015871  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180015876  jnz     short loc_180015899
0x180015878  mov     rcx, [rbp+1400h+var_40]
0x18001587f  xor     rcx, rsp; StackCookie
0x180015882  call    __security_check_cookie
0x180015887  add     rsp, 14D0h
0x18001588e  pop     r15
0x180015890  pop     r14
0x180015892  pop     r12
0x180015894  pop     rdi
0x180015895  pop     rsi
0x180015896  pop     rbx
0x180015897  pop     rbp
0x180015898  retn
0x180015899  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001589e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800158a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
