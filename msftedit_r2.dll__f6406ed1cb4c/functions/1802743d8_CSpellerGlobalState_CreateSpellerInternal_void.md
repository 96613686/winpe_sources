# CSpellerGlobalState::CreateSpellerInternal(void)

- ea: `0x1802743d8`
- end: `0x1802744f0`
- name: `?CreateSpellerInternal@CSpellerGlobalState@@AEAAXXZ`
- size: `280`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180274500`

## callees

- `0x18006ad18`
- `0x1801247bc`
- `0x1802743d8`
- `0x180274664`
- `0x18027ba28`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1802743ee`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1802743ee`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1802744d3`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1802744d3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18027447d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18027447d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1802744a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1802744a2`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18027442b`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18027442b`

## pseudocode

```c
void __fastcall CSpellerGlobalState::CreateSpellerInternal(CSpellerGlobalState *this)
{
  HRESULT v2; // eax
  HRESULT *v3; // rsi
  HRESULT InterfaceAndReleaseStream; // eax
  unsigned int v5; // ebx
  HSTRING CurrentInputMethodLanguageTag; // rax
  IUnknown *Speller; // rax
  IUnknown *v8; // rbx
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = (HRESULT *)((char *)this + 68);
  *((_DWORD *)this + 17) = v2;
  if ( v2 < 0 )
  {
    LODWORD(ppv) = 4;
    CSpellCheckerTelemetry::LogSpellerBackCoInitStatus<enum TelemetrySpellCheckerBackFailure,long &>(
      &ppv,
      (char *)this + 68);
    CoReleaseMarshalData(*((LPSTREAM *)this + 14));
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                  *((LPSTREAM *)this + 14),
                                  &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
                                  &ppv);
    *v3 = InterfaceAndReleaseStream;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v5 = *((_DWORD *)this + 84);
      CurrentInputMethodLanguageTag = CSpellerGlobalState::GetCurrentInputMethodLanguageTag(this, v5);
      Speller = (IUnknown *)CreateSpeller(
                              (struct ISpellCheckerFactory *)ppv,
                              v5,
                              CurrentInputMethodLanguageTag,
                              *((_BYTE *)this + 340) == 0);
      v8 = Speller;
      if ( Speller )
      {
        *v3 = CoMarshalInterThreadInterfaceInStream(
                &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b,
                Speller,
                (LPSTREAM *)this + 15);
        ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
      }
    }
    *((_QWORD *)this + 14) = 0;
    CoUninitialize();
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
}

```

## disassembly

```asm
0x1802743d8  mov     [rsp+arg_8], rbx
0x1802743dd  mov     [rsp+arg_10], rsi
0x1802743e2  push    rdi
0x1802743e3  sub     rsp, 20h
0x1802743e7  mov     rdi, rcx
0x1802743ea  xor     edx, edx; dwCoInit
0x1802743ec  xor     ecx, ecx; pvReserved
0x1802743ee  call    cs:__imp_CoInitializeEx
0x1802743f5  nop     dword ptr [rax+rax+00h]
0x1802743fa  lea     rsi, [rdi+44h]
0x1802743fe  mov     [rsi], eax
0x180274400  test    eax, eax
0x180274402  js      loc_1802744BA
0x180274408  lea     rcx, [rsp+28h+ppv]
0x18027440d  mov     [rsp+28h+ppv], 0
0x180274416  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027441b  mov     rcx, [rdi+70h]; pStm
0x18027441f  lea     r8, [rsp+28h+ppv]; ppv
0x180274424  lea     rdx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; iid
0x18027442b  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180274432  nop     dword ptr [rax+rax+00h]
0x180274437  mov     [rsi], eax
0x180274439  test    eax, eax
0x18027443b  js      short loc_18027449A
0x18027443d  mov     ebx, [rdi+150h]
0x180274443  mov     rcx, rdi; this
0x180274446  mov     edx, ebx; unsigned int
0x180274448  call    ?GetCurrentInputMethodLanguageTag@CSpellerGlobalState@@AEBAPEAUHSTRING__@@K@Z; CSpellerGlobalState::GetCurrentInputMethodLanguageTag(ulong)
0x18027444d  cmp     byte ptr [rdi+154h], 0
0x180274454  mov     r8, rax; HSTRING
0x180274457  mov     rcx, [rsp+28h+ppv]; struct ISpellCheckerFactory *
0x18027445c  mov     edx, ebx; unsigned int
0x18027445e  setz    r9b; bool
0x180274462  call    ?CreateSpeller@@YAPEAUISpellChecker@@PEAUISpellCheckerFactory@@KPEAUHSTRING__@@_N@Z; CreateSpeller(ISpellCheckerFactory *,ulong,HSTRING__ *,bool)
0x180274467  mov     rbx, rax
0x18027446a  test    rax, rax
0x18027446d  jz      short loc_18027449A
0x18027446f  lea     r8, [rdi+78h]; ppStm
0x180274473  mov     rdx, rax; pUnk
0x180274476  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x18027447d  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180274484  nop     dword ptr [rax+rax+00h]
0x180274489  mov     [rsi], eax
0x18027448b  mov     rcx, [rbx]
0x18027448e  mov     rax, [rcx+10h]
0x180274492  mov     rcx, rbx
0x180274495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027449a  mov     qword ptr [rdi+70h], 0
0x1802744a2  call    cs:__imp_CoUninitialize
0x1802744a9  nop     dword ptr [rax+rax+00h]
0x1802744ae  lea     rcx, [rsp+28h+ppv]
0x1802744b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802744b8  jmp     short loc_1802744DF
0x1802744ba  mov     rdx, rsi
0x1802744bd  mov     dword ptr [rsp+28h+ppv], 4
0x1802744c5  lea     rcx, [rsp+28h+ppv]
0x1802744ca  call    ??$LogSpellerBackCoInitStatus@W4TelemetrySpellCheckerBackFailure@@AEAJ@CSpellCheckerTelemetry@@SAX$$QEAW4TelemetrySpellCheckerBackFailure@@AEAJ@Z; CSpellCheckerTelemetry::LogSpellerBackCoInitStatus<TelemetrySpellCheckerBackFailure,long &>(TelemetrySpellCheckerBackFailure &&,long &)
0x1802744cf  mov     rcx, [rdi+70h]; pStm
0x1802744d3  call    cs:__imp_CoReleaseMarshalData
0x1802744da  nop     dword ptr [rax+rax+00h]
0x1802744df  mov     rbx, [rsp+28h+arg_8]
0x1802744e4  mov     rsi, [rsp+28h+arg_10]
0x1802744e9  add     rsp, 20h
0x1802744ed  pop     rdi
0x1802744ee  retn
```
