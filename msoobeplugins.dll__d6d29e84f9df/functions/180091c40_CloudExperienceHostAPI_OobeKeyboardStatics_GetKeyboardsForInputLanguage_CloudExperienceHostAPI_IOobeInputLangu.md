# CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForInputLanguage(CloudExperienceHostAPI::IOobeInputLanguage *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)

- ea: `0x180091c40`
- end: `0x180091d16`
- name: `?GetKeyboardsForInputLanguage@OobeKeyboardStatics@CloudExperienceHostAPI@@UEAAJPEAUIOobeInputLanguage@2@PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180008544`
- `0x1800599d0`
- `0x180059b90`
- `0x180059cc0`
- `0x180091c40`
- `0x180091d1c`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091cfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180091cfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180091cc3`

## string_xrefs

- `0x180091ce1`: `shell\oobe\machine\plugins\adapters\winrt\oobekeyboard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForInputLanguage(
        unsigned __int8 a1,
        unsigned __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  CloudExperienceHostCoreTelemetry *v6; // rcx
  __int64 (__fastcall *v7)(unsigned __int64, HSTRING *); // rbx
  int KeyboardsForLocaleByName; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned __int16 *StringRawBuffer; // rax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  if ( CloudExperienceHostCoreTelemetry::IsEnabled(a1, a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v5,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v6,
      "CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForInputLanguage");
  }
  *a3 = 0;
  string = 0;
  v7 = *(__int64 (__fastcall **)(unsigned __int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  KeyboardsForLocaleByName = v7(a2, &string);
  v9 = KeyboardsForLocaleByName;
  if ( KeyboardsForLocaleByName >= 0 )
  {
    StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
    KeyboardsForLocaleByName = CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(
                                 StringRawBuffer,
                                 0,
                                 a3);
    v9 = KeyboardsForLocaleByName;
    if ( KeyboardsForLocaleByName >= 0 )
    {
      v9 = 0;
      goto LABEL_9;
    }
    v10 = 190;
  }
  else
  {
    v10 = 189;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobekeyboard.cpp",
    (const char *)(unsigned int)KeyboardsForLocaleByName,
    v13);
LABEL_9:
  WindowsDeleteString(string);
  return v9;
}

```

## disassembly

```asm
0x180091c40  mov     [rsp+arg_0], rbx
0x180091c45  mov     [rsp+arg_10], rsi
0x180091c4a  push    rdi; int
0x180091c4b  sub     rsp, 20h
0x180091c4f  mov     rdi, r8
0x180091c52  mov     rsi, rdx
0x180091c55  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x180091c5a  test    al, al
0x180091c5c  jz      short loc_180091C77
0x180091c5e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x180091c65  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x180091c6a  lea     rdx, aCloudexperienc_21; "CloudExperienceHostAPI::OobeKeyboardSta"...
0x180091c71  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x180091c76  nop
0x180091c77  mov     qword ptr [rdi], 0
0x180091c7e  mov     [rsp+28h+string], 0
0x180091c87  mov     rax, [rsi]
0x180091c8a  mov     rbx, [rax+30h]
0x180091c8e  xor     ecx, ecx; string
0x180091c90  call    cs:__imp_WindowsDeleteString
0x180091c96  mov     [rsp+28h+string], 0
0x180091c9f  lea     rdx, [rsp+28h+string]
0x180091ca4  mov     rcx, rsi
0x180091ca7  mov     rax, rbx
0x180091caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091caf  mov     ebx, eax
0x180091cb1  test    eax, eax
0x180091cb3  jns     short loc_180091CBC
0x180091cb5  mov     edx, 0BDh
0x180091cba  jmp     short loc_180091CE1
0x180091cbc  xor     edx, edx; length
0x180091cbe  mov     rcx, [rsp+28h+string]; string
0x180091cc3  call    cs:__imp_WindowsGetStringRawBuffer
0x180091cc9  mov     r8, rdi
0x180091ccc  xor     edx, edx
0x180091cce  mov     rcx, rax; unsigned __int16 *
0x180091cd1  call    ?GetKeyboardsForLocaleByName@OobeKeyboardStatics@CloudExperienceHostAPI@@CAJPEBG0PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z; CloudExperienceHostAPI::OobeKeyboardStatics::GetKeyboardsForLocaleByName(ushort const *,ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)
0x180091cd6  mov     ebx, eax
0x180091cd8  test    eax, eax
0x180091cda  jns     short loc_180091CF7
0x180091cdc  mov     edx, 0BEh; void *
0x180091ce1  lea     r8, aShellOobeMachi_22; "shell\\oobe\\machine\\plugins\\adapters"...
0x180091ce8  mov     r9d, eax; char *
0x180091ceb  mov     rcx, [rsp+28h]; this
0x180091cf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091cf5  jmp     short loc_180091CF9
0x180091cf7  xor     ebx, ebx
0x180091cf9  mov     rcx, [rsp+28h+string]; string
0x180091cfe  call    cs:__imp_WindowsDeleteString
0x180091d04  mov     eax, ebx
0x180091d06  mov     rbx, [rsp+28h+arg_0]
0x180091d0b  mov     rsi, [rsp+28h+arg_10]
0x180091d10  add     rsp, 20h
0x180091d14  pop     rdi
0x180091d15  retn
```
