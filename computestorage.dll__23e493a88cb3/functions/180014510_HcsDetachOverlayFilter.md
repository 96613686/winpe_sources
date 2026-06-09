# HcsDetachOverlayFilter

- ea: `0x180014510`
- end: `0x1800146d3`
- name: `HcsDetachOverlayFilter`
- size: `451`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180004aac`
- `0x1800084c0`
- `0x180008ce8`
- `0x180008fac`
- `0x18000a578`
- `0x18000a964`
- `0x18000f708`
- `0x18000ffd4`
- `0x1800127bc`
- `0x1800137fc`
- `0x180014510`

## import_xrefs

- `container!WcCleanupFilesystemNamespace` at `0x1800145ea`
- `container!WcCleanupFilesystemNamespace` at `0x1800145ea`
- `wc_storage!WcDetachFilterEx` at `0x180014621`
- `wc_storage!WcDetachFilterEx` at `0x180014621`

## string_xrefs

- `0x180014564`: `ComputeStorage_HcsDetachOverlayFilter`
- `0x1800146ab`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x1800146c0`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HcsDetachOverlayFilter(PCWSTR pszPathIn, __int64 a2)
{
  __int64 v4; // rax
  __int128 *p_Src; // rdx
  int v6; // eax
  __int128 *v7; // rcx
  int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-1E8h]
  __int128 Src; // [rsp+30h] [rbp-1D8h] BYREF
  unsigned __int64 v13; // [rsp+48h] [rbp-1C0h]
  __int64 v14; // [rsp+50h] [rbp-1B8h] BYREF
  __int128 v15; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-1A0h]
  __int64 v17; // [rsp+70h] [rbp-198h]
  _QWORD v18[42]; // [rsp+80h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v18,
    (__int64)"ComputeStorage_HcsDetachOverlayFilter");
  v18[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachOverlayFilter::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachOverlayFilter::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachOverlayFilter *)v18);
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a2 + 2 * v4) );
  *(_QWORD *)&Src = a2;
  *((_QWORD *)&Src + 1) = v4;
  try
  {
    ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(&Src, (__int64)&v14);
    if ( (_DWORD)v17 == 1 )
    {
      Vml::CombineFilePath(&Src, pszPathIn, L".\\");
      p_Src = &Src;
      if ( v13 > 7 )
        p_Src = (__int128 *)Src;
      v6 = WcCleanupFilesystemNamespace(0, p_Src);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x194,
          (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
          (const char *)(unsigned int)v6,
          v11);
    }
    else
    {
      Vml::CombineFilePath(&Src, pszPathIn, L".\\");
      v7 = &Src;
      if ( v13 > 7 )
        v7 = (__int128 *)Src;
      v8 = WcDetachFilterEx(v7, 0);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
          (const char *)(unsigned int)v8,
          v11);
    }
    std::wstring::~wstring((char **)&Src);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v18);
    v18[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachOverlayFilter::`vftable';
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v18);
    std::vector<Schema::Common::Resources::Layer>::_Tidy((char ***)&v15);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x19D,
                           (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180014510  push    rbx
0x180014512  push    rsi
0x180014513  push    rdi
0x180014514  push    r14
0x180014516  sub     rsp, 1E8h
0x18001451d  mov     rax, cs:__security_cookie
0x180014524  xor     rax, rsp
0x180014527  mov     [rsp+208h+var_38], rax
0x18001452f  mov     rdi, rdx
0x180014532  mov     rbx, rcx
0x180014535  xor     esi, esi
0x180014537  mov     [rsp+208h+var_1B8], rsi
0x18001453c  xorps   xmm0, xmm0
0x18001453f  movdqu  [rsp+208h+var_1B0], xmm0
0x180014545  mov     [rsp+208h+var_1A0], rsi
0x18001454a  mov     [rsp+208h+var_198], rsi
0x18001454f  xor     edx, edx; Val
0x180014551  mov     r8d, 150h; Size
0x180014557  lea     rcx, [rsp+208h+var_188]; void *
0x18001455f  call    memset_0
0x180014564  lea     rdx, aComputestorage_11; "ComputeStorage_HcsDetachOverlayFilter"
0x18001456b  lea     rcx, [rsp+208h+var_188]
0x180014573  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014578  lea     r14, ??_7ComputeStorage_HcsDetachOverlayFilter@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachOverlayFilter::`vftable'
0x18001457f  mov     [rsp+208h+var_188], r14
0x180014587  lea     rcx, [rsp+208h+var_188]; this
0x18001458f  call    ?StartActivity@ComputeStorage_HcsDetachOverlayFilter@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachOverlayFilter::StartActivity(void)
0x180014594  nop
0x180014595  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014599  inc     rax
0x18001459c  cmp     [rdi+rax*2], si
0x1800145a0  jnz     short loc_180014599
0x1800145a2  mov     [rsp+208h+Src], rdi
0x1800145a7  mov     [rsp+208h+var_1D0], rax
0x1800145ac  lea     rdx, [rsp+208h+var_1B8]
0x1800145b1  lea     rcx, [rsp+208h+Src]
0x1800145b6  call    ??$FromJsonStrictThrow@ULayerData@LayerManagement@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAULayerData@LayerManagement@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(std::basic_string_view<ushort>,Schema::LayerManagement::LayerData *,Marshal::UnmarshalFlags)
0x1800145bb  lea     r8, pszMore; ".\\"
0x1800145c2  mov     rdx, rbx; pszPathIn
0x1800145c5  lea     rcx, [rsp+208h+Src]; Src
0x1800145ca  cmp     dword ptr [rsp+208h+var_198], 1
0x1800145cf  jnz     short loc_180014608
0x1800145d1  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800145d6  nop
0x1800145d7  lea     rdx, [rsp+208h+Src]
0x1800145dc  cmp     [rsp+208h+var_1C0], 7
0x1800145e2  cmova   rdx, [rsp+208h+Src]
0x1800145e8  xor     ecx, ecx
0x1800145ea  call    cs:__imp_WcCleanupFilesystemNamespace
0x1800145f1  nop     dword ptr [rax+rax+00h]
0x1800145f6  mov     rcx, [rsp+208h]; this
0x1800145fe  test    eax, eax
0x180014600  js      loc_1800146A8
0x180014606  jmp     short loc_18001463D
0x180014608  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001460d  nop
0x18001460e  lea     rcx, [rsp+208h+Src]
0x180014613  cmp     [rsp+208h+var_1C0], 7
0x180014619  cmova   rcx, [rsp+208h+Src]
0x18001461f  xor     edx, edx
0x180014621  call    cs:__imp_WcDetachFilterEx
0x180014628  nop     dword ptr [rax+rax+00h]
0x18001462d  mov     rcx, [rsp+208h]; this
0x180014635  test    eax, eax
0x180014637  js      loc_1800146BD
0x18001463d  lea     rcx, [rsp+208h+Src]
0x180014642  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014647  lea     rcx, [rsp+208h+var_188]
0x18001464f  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014654  nop
0x180014655  mov     [rsp+208h+var_188], r14
0x18001465d  lea     rcx, [rsp+208h+var_188]
0x180014665  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001466a  lea     rcx, [rsp+208h+var_188]
0x180014672  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014677  nop
0x180014678  lea     rcx, [rsp+208h+var_1B0]
0x18001467d  call    ?_Tidy@?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Common::Resources::Layer>::_Tidy(void)
0x180014682  xor     eax, eax
0x180014684  jmp     short loc_18001468A
0x180014686  mov     eax, [rsp+208h+var_1E8]
0x18001468a  mov     rcx, [rsp+208h+var_38]
0x180014692  xor     rcx, rsp; StackCookie
0x180014695  call    __security_check_cookie
0x18001469a  add     rsp, 1E8h
0x1800146a1  pop     r14
0x1800146a3  pop     rdi
0x1800146a4  pop     rsi
0x1800146a5  pop     rbx
0x1800146a6  retn
0x1800146a8  mov     r9d, eax; char *
0x1800146ab  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800146b2  mov     edx, 194h; void *
0x1800146b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800146bd  mov     r9d, eax; char *
0x1800146c0  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800146c7  mov     edx, 198h; void *
0x1800146cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
