# CSpellerGlobalState::BackgroundInitialize(void)

- ea: `0x18027789c`
- end: `0x180277b1c`
- name: `?BackgroundInitialize@CSpellerGlobalState@@AEAAXXZ`
- size: `640`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180273f60`

## callees

- `0x18006ad18`
- `0x1800ff2b4`
- `0x180124800`
- `0x180128980`
- `0x18013d268`
- `0x180273f78`
- `0x180274664`
- `0x180274fe4`
- `0x180277848`
- `0x18027789c`
- `0x180277b24`
- `0x18027ba28`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1802778bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1802778bf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180277967`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18027798d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180277967`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18027798d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180277ad0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180277ad0`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180277a6f`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180277aa0`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180277a6f`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180277aa0`

## pseudocode

```c
void __fastcall CSpellerGlobalState::BackgroundInitialize(CSpellerGlobalState *this)
{
  HRESULT v2; // eax
  unsigned __int64 v3; // rdx
  unsigned __int8 v4; // cl
  HRESULT MultilingualSpellers; // r14d
  char v6; // r15
  unsigned int v7; // r12d
  __int64 (__fastcall *v8)(LPUNKNOWN *); // rbx
  HSTRING CurrentInputMethodLanguageTag; // rax
  struct ISpellChecker *Speller; // rax
  HRESULT v11; // eax
  LPUNKNOWN v12; // rbx
  _DWORD *v13; // rax
  struct ISpellCheckerFactory *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  LPUNKNOWN v17; // [rsp+50h] [rbp+30h] BYREF
  LPUNKNOWN v18; // [rsp+58h] [rbp+38h] BYREF
  LPUNKNOWN pUnk; // [rsp+60h] [rbp+40h] BYREF

  CSpellerGlobalState::CalculateSettings(this);
  v2 = CoInitializeEx(0, 2u);
  MultilingualSpellers = v2;
  if ( v2 == -2147417850 )
  {
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v7 = 0;
    v6 = 1;
    if ( v2 < 0 )
      goto LABEL_24;
  }
  v8 = (__int64 (__fastcall *)(LPUNKNOWN *))*((_QWORD *)this + 12);
  v18 = 0;
  pUnk = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  MultilingualSpellers = v8(&v18);
  if ( MultilingualSpellers >= 0 )
  {
    CurrentInputMethodLanguageTag = CSpellerGlobalState::GetCurrentInputMethodLanguageTag(this, *((_DWORD *)this + 18));
    Speller = CreateSpeller(
                (struct ISpellCheckerFactory *)v18,
                *((_DWORD *)this + 18),
                CurrentInputMethodLanguageTag,
                *((_BYTE *)this + 340) == 0);
    Microsoft::WRL::ComPtr<ISpellChecker>::operator=(&pUnk, Speller);
    if ( !pUnk
      || (MultilingualSpellers = CoMarshalInterThreadInterfaceInStream(
                                   &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b,
                                   pUnk,
                                   (LPSTREAM *)this + 15),
          MultilingualSpellers >= 0) )
    {
      v11 = CoMarshalInterThreadInterfaceInStream(
              &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
              v18,
              (LPSTREAM *)this + 14);
      v12 = v18;
      MultilingualSpellers = v11;
      if ( *((LPUNKNOWN *)this + 6) != v18 )
      {
        v17 = v18;
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalAddRef(&v17);
        v17 = (LPUNKNOWN)*((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = v12;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      }
      if ( MultilingualSpellers >= 0 )
      {
        v13 = operator new(0x18u);
        *(_QWORD *)v13 = 0;
        v13[2] = 8;
        *((_QWORD *)v13 + 2) = 0;
        v14 = (struct ISpellCheckerFactory *)v18;
        *((_QWORD *)this + 3) = v13;
        MultilingualSpellers = CSpellerGlobalState::CreateMultilingualSpellers(this, v14, 1);
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
  if ( MultilingualSpellers < 0 )
    goto LABEL_14;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 3, 1) != 1 )
  {
    MultilingualSpellers = -2147467260;
LABEL_14:
    _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 4, 1);
    if ( v18 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( pUnk )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( CoGetInterfaceAndReleaseStream(
           *((LPSTREAM *)this + 15),
           &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b,
           (LPVOID *)&pUnk) >= 0 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( CoGetInterfaceAndReleaseStream(
           *((LPSTREAM *)this + 14),
           &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
           (LPVOID *)&v18) >= 0 )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  if ( v6 )
    CoUninitialize();
LABEL_24:
  if ( CSpellCheckerTelemetry::IsEnabled(v4, v3) )
  {
    wil::details::static_lazy<CSpellCheckerTelemetry>::get(
      v15,
      _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_);
    CSpellCheckerTelemetry::LogSpellerBackCoInitStatus_(v16, v7, (unsigned int)MultilingualSpellers);
  }
  (*(void (__fastcall **)(CSpellerGlobalState *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18027789c  mov     [rsp-28h+arg_18], rbx
0x1802778a1  push    rbp
0x1802778a2  push    rsi
0x1802778a3  push    r12
0x1802778a5  push    r14
0x1802778a7  push    r15
0x1802778a9  mov     rbp, rsp
0x1802778ac  sub     rsp, 20h
0x1802778b0  mov     rsi, rcx
0x1802778b3  call    ?CalculateSettings@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::CalculateSettings(void)
0x1802778b8  mov     edx, 2; dwCoInit
0x1802778bd  xor     ecx, ecx; pvReserved
0x1802778bf  call    cs:__imp_CoInitializeEx
0x1802778c6  nop     dword ptr [rax+rax+00h]
0x1802778cb  mov     r14d, eax
0x1802778ce  cmp     eax, 80010106h
0x1802778d3  jnz     short loc_1802778E0
0x1802778d5  xor     r15b, r15b
0x1802778d8  mov     r12d, 1
0x1802778de  jmp     short loc_1802778EE
0x1802778e0  xor     r12d, r12d
0x1802778e3  mov     r15b, 1
0x1802778e6  test    eax, eax
0x1802778e8  js      loc_180277ADC
0x1802778ee  mov     rbx, [rsi+60h]
0x1802778f2  lea     rcx, [rbp+arg_8]
0x1802778f6  mov     [rbp+arg_8], 0
0x1802778fe  mov     [rbp+pUnk], 0
0x180277906  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027790b  lea     rcx, [rbp+arg_8]
0x18027790f  mov     rax, rbx
0x180277912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180277917  mov     r14d, eax
0x18027791a  test    eax, eax
0x18027791c  js      loc_180277A03
0x180277922  mov     edx, [rsi+48h]; unsigned int
0x180277925  mov     rcx, rsi; this
0x180277928  call    ?GetCurrentInputMethodLanguageTag@CSpellerGlobalState@@AEBAPEAUHSTRING__@@K@Z; CSpellerGlobalState::GetCurrentInputMethodLanguageTag(ulong)
0x18027792d  cmp     byte ptr [rsi+154h], 0
0x180277934  mov     r8, rax; HSTRING
0x180277937  mov     edx, [rsi+48h]; unsigned int
0x18027793a  mov     rcx, [rbp+arg_8]; struct ISpellCheckerFactory *
0x18027793e  setz    r9b; bool
0x180277942  call    ?CreateSpeller@@YAPEAUISpellChecker@@PEAUISpellCheckerFactory@@KPEAUHSTRING__@@_N@Z; CreateSpeller(ISpellCheckerFactory *,ulong,HSTRING__ *,bool)
0x180277947  mov     rdx, rax
0x18027794a  lea     rcx, [rbp+pUnk]
0x18027794e  call    ??4?$ComPtr@UISpellChecker@@@WRL@Microsoft@@QEAAAEAV012@PEAUISpellChecker@@@Z; Microsoft::WRL::ComPtr<ISpellChecker>::operator=(ISpellChecker *)
0x180277953  mov     rdx, [rbp+pUnk]; pUnk
0x180277957  test    rdx, rdx
0x18027795a  jz      short loc_18027797E
0x18027795c  lea     r8, [rsi+78h]; ppStm
0x180277960  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x180277967  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18027796e  nop     dword ptr [rax+rax+00h]
0x180277973  mov     r14d, eax
0x180277976  test    eax, eax
0x180277978  js      loc_180277A03
0x18027797e  mov     rdx, [rbp+arg_8]; pUnk
0x180277982  lea     r8, [rsi+70h]; ppStm
0x180277986  lea     rcx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; riid
0x18027798d  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180277994  nop     dword ptr [rax+rax+00h]
0x180277999  mov     rbx, [rbp+arg_8]
0x18027799d  mov     r14d, eax
0x1802779a0  cmp     [rsi+30h], rbx
0x1802779a4  jz      short loc_1802779C8
0x1802779a6  lea     rcx, [rbp+arg_0]
0x1802779aa  mov     [rbp+arg_0], rbx
0x1802779ae  call    ?InternalAddRef@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalAddRef(void)
0x1802779b3  mov     rax, [rsi+30h]
0x1802779b7  lea     rcx, [rbp+arg_0]
0x1802779bb  mov     [rbp+arg_0], rax
0x1802779bf  mov     [rsi+30h], rbx
0x1802779c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802779c8  test    r14d, r14d
0x1802779cb  js      short loc_180277A03
0x1802779cd  mov     ecx, 18h; Size
0x1802779d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802779d7  mov     r8b, 1; bool
0x1802779da  mov     rcx, rsi; this
0x1802779dd  mov     qword ptr [rax], 0
0x1802779e4  mov     dword ptr [rax+8], 8
0x1802779eb  mov     qword ptr [rax+10h], 0
0x1802779f3  mov     rdx, [rbp+arg_8]; struct ISpellCheckerFactory *
0x1802779f7  mov     [rsi+18h], rax
0x1802779fb  call    ?CreateMultilingualSpellers@CSpellerGlobalState@@QEAAJPEAUISpellCheckerFactory@@_N@Z; CSpellerGlobalState::CreateMultilingualSpellers(ISpellCheckerFactory *,bool)
0x180277a00  mov     r14d, eax
0x180277a03  lea     rcx, [rsi+30h]
0x180277a07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277a0c  test    r14d, r14d
0x180277a0f  js      short loc_180277A2A
0x180277a11  mov     ecx, 3
0x180277a16  lea     eax, [rcx-2]
0x180277a19  lock cmpxchg [rsi+68h], ecx
0x180277a1e  jz      loc_180277AB9
0x180277a24  mov     r14d, 80004004h
0x180277a2a  mov     ecx, 4
0x180277a2f  lea     eax, [rcx-3]
0x180277a32  lock cmpxchg [rsi+68h], ecx
0x180277a37  cmp     [rbp+arg_8], 0
0x180277a3c  jz      short loc_180277A47
0x180277a3e  lea     rcx, [rbp+arg_8]
0x180277a42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277a47  cmp     [rbp+pUnk], 0
0x180277a4c  jz      short loc_180277A57
0x180277a4e  lea     rcx, [rbp+pUnk]
0x180277a52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277a57  lea     rcx, [rbp+pUnk]
0x180277a5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277a60  mov     rcx, [rsi+78h]; pStm
0x180277a64  lea     r8, [rbp+pUnk]; ppv
0x180277a68  lea     rdx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; iid
0x180277a6f  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180277a76  nop     dword ptr [rax+rax+00h]
0x180277a7b  test    eax, eax
0x180277a7d  js      short loc_180277A88
0x180277a7f  lea     rcx, [rbp+pUnk]
0x180277a83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277a88  lea     rcx, [rbp+arg_8]
0x180277a8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277a91  mov     rcx, [rsi+70h]; pStm
0x180277a95  lea     r8, [rbp+arg_8]; ppv
0x180277a99  lea     rdx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; iid
0x180277aa0  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180277aa7  nop     dword ptr [rax+rax+00h]
0x180277aac  test    eax, eax
0x180277aae  js      short loc_180277AB9
0x180277ab0  lea     rcx, [rbp+arg_8]
0x180277ab4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277ab9  lea     rcx, [rbp+pUnk]
0x180277abd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277ac2  lea     rcx, [rbp+arg_8]
0x180277ac6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180277acb  test    r15b, r15b
0x180277ace  jz      short loc_180277ADC
0x180277ad0  call    cs:__imp_CoUninitialize
0x180277ad7  nop     dword ptr [rax+rax+00h]
0x180277adc  call    ?IsEnabled@CSpellCheckerTelemetry@@SA_NE_K@Z; CSpellCheckerTelemetry::IsEnabled(uchar,unsigned __int64)
0x180277ae1  test    al, al
0x180277ae3  jz      short loc_180277AFC
0x180277ae5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3c853e741dc03bb96b7f8662095382b4_@@CA@XZ; _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_(void)
0x180277aec  call    ?get@?$static_lazy@VCSpellCheckerTelemetry@@@details@wil@@QEAAPEAVCSpellCheckerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CSpellCheckerTelemetry>::get(void (*)(void))
0x180277af1  mov     r8d, r14d
0x180277af4  mov     edx, r12d
0x180277af7  call    ?LogSpellerBackCoInitStatus_@CSpellCheckerTelemetry@@QEBAXW4TelemetrySpellCheckerBackFailure@@J@Z; CSpellCheckerTelemetry::LogSpellerBackCoInitStatus_(TelemetrySpellCheckerBackFailure,long)
0x180277afc  mov     rax, [rsi]
0x180277aff  mov     rcx, rsi
0x180277b02  mov     rax, [rax+10h]
0x180277b06  mov     rbx, [rsp+20h+arg_18]
0x180277b0b  add     rsp, 20h
0x180277b0f  pop     r15
0x180277b11  pop     r14
0x180277b13  pop     r12
0x180277b15  pop     rsi
0x180277b16  pop     rbp
0x180277b17  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
