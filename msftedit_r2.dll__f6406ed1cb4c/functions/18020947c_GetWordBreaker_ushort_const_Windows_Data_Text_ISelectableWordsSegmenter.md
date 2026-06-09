# GetWordBreaker(ushort const *,Windows::Data::Text::ISelectableWordsSegmenter * *)

- ea: `0x18020947c`
- end: `0x180209561`
- name: `?GetWordBreaker@@YAXPEBGPEAPEAUISelectableWordsSegmenter@Text@Data@Windows@@@Z`
- size: `229`
- prototype: `void __fastcall(const unsigned __int16 *, struct Windows::Data::Text::ISelectableWordsSegmenter **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006afa0`

## callees

- `0x18006ad18`
- `0x18006af48`
- `0x18006b190`
- `0x18020947c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180209500`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180209500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020952b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180209543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020952b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180209543`

## pseudocode

```c
void __fastcall GetWordBreaker(const unsigned __int16 *a1, struct Windows::Data::Text::ISelectableWordsSegmenter **a2)
{
  bool v2; // zf
  int v4; // eax
  HSTRING v5; // rbx
  const unsigned __int16 *v6; // [rsp+40h] [rbp+20h] BYREF
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  __int64 v8; // [rsp+50h] [rbp+30h] BYREF
  HSTRING v9; // [rsp+58h] [rbp+38h] BYREF

  v6 = a1;
  v2 = !CW32System::_fOnWin81OrLater;
  v8 = 0;
  *a2 = 0;
  if ( !v2 )
  {
    v9 = 0;
    v4 = Microsoft::WRL::Wrappers::HString::Set(
           (Microsoft::WRL::Wrappers::HString *)&v9,
           L"Windows.Data.Text.SelectableWordsSegmenter",
           0x2Au);
    string = 0;
    if ( !v4 && !(unsigned int)Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v6) )
    {
      v5 = v9;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      if ( (int)RoGetActivationFactory(v5, &GUID_8c7a7648_6057_4339_bc70_f210010a4150, &v8) >= 0 )
        (*(void (__fastcall **)(__int64, HSTRING, struct Windows::Data::Text::ISelectableWordsSegmenter **))(*(_QWORD *)v8 + 48LL))(
          v8,
          string,
          a2);
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
}

```

## disassembly

```asm
0x18020947c  mov     [rsp-18h+arg_0], rcx
0x180209481  push    rbp
0x180209482  push    rbx
0x180209483  push    rdi
0x180209484  mov     rbp, rsp
0x180209487  sub     rsp, 20h
0x18020948b  cmp     cs:?_fOnWin81OrLater@CW32System@@0_NA, 0; bool CW32System::_fOnWin81OrLater
0x180209492  mov     rdi, rdx
0x180209495  mov     [rbp+arg_10], 0
0x18020949d  mov     qword ptr [rdx], 0
0x1802094a4  jz      loc_18020954F
0x1802094aa  mov     r8d, 2Ah ; '*'; unsigned int
0x1802094b0  mov     [rbp+arg_18], 0
0x1802094b8  lea     rdx, ?RuntimeClass_Windows_Data_Text_SelectableWordsSegmenter@@3QBGB; "Windows.Data.Text.SelectableWordsSegmen"...
0x1802094bf  lea     rcx, [rbp+arg_18]; this
0x1802094c3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1802094c8  mov     [rbp+string], 0
0x1802094d0  test    eax, eax
0x1802094d2  jnz     short loc_180209527
0x1802094d4  lea     rdx, [rbp+arg_0]
0x1802094d8  lea     rcx, [rbp+string]
0x1802094dc  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802094e1  test    eax, eax
0x1802094e3  jnz     short loc_180209527
0x1802094e5  mov     rbx, [rbp+arg_18]
0x1802094e9  lea     rcx, [rbp+arg_10]
0x1802094ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802094f2  lea     r8, [rbp+arg_10]
0x1802094f6  mov     rcx, rbx
0x1802094f9  lea     rdx, _GUID_8c7a7648_6057_4339_bc70_f210010a4150
0x180209500  call    cs:__imp_RoGetActivationFactory
0x180209507  nop     dword ptr [rax+rax+00h]
0x18020950c  test    eax, eax
0x18020950e  js      short loc_180209527
0x180209510  mov     rcx, [rbp+arg_10]
0x180209514  mov     r8, rdi
0x180209517  mov     rdx, [rbp+string]
0x18020951b  mov     rax, [rcx]
0x18020951e  mov     rax, [rax+30h]
0x180209522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180209527  mov     rcx, [rbp+string]; string
0x18020952b  call    cs:__imp_WindowsDeleteString
0x180209532  nop     dword ptr [rax+rax+00h]
0x180209537  mov     rcx, [rbp+arg_18]; string
0x18020953b  mov     [rbp+string], 0
0x180209543  call    cs:__imp_WindowsDeleteString
0x18020954a  nop     dword ptr [rax+rax+00h]
0x18020954f  lea     rcx, [rbp+arg_10]
0x180209553  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180209558  add     rsp, 20h
0x18020955c  pop     rdi
0x18020955d  pop     rbx
0x18020955e  pop     rbp
0x18020955f  retn
```
