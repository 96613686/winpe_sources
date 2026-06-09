# CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForInputLanguage(CloudExperienceHostAPI::IOobeInputLanguage *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)

- ea: `0x180048960`
- end: `0x180048a56`
- name: `?GetKeyboardsForInputLanguage@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@UEAAJPEAUIOobeInputLanguage@2@PEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800076d4`
- `0x18000b7f8`
- `0x18000b9b8`
- `0x18000bc70`
- `0x180048960`
- `0x180048a5c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048a05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048a05`

## string_xrefs

- `0x180048a21`: `shellcommon\shell\oobe\core\components\winrt\oobekeyboardcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForInputLanguage(
        __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rcx
  CloudExperienceHostCoreTelemetry *v7; // rcx
  __int64 v8; // rcx
  __int64 (__fastcall *v10)(unsigned __int64, HSTRING *); // rbx
  int KeyboardsForLocaleByName; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  PCWSTR StringRawBuffer; // rax
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  if ( CloudExperienceHostCoreTelemetry::IsEnabled(a1, a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v6,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v7,
      "CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForInputLanguage");
  }
  *a3 = 0;
  v8 = *(_QWORD *)(a1 + 56);
  if ( v8 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD *))(*(_QWORD *)v8 + 64LL))(v8, a2, a3);
  string = 0;
  v10 = *(__int64 (__fastcall **)(unsigned __int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  KeyboardsForLocaleByName = v10(a2, &string);
  v12 = KeyboardsForLocaleByName;
  if ( KeyboardsForLocaleByName >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    KeyboardsForLocaleByName = CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForLocaleByName(
                                 (__int64)StringRawBuffer,
                                 a3);
    v12 = KeyboardsForLocaleByName;
    if ( KeyboardsForLocaleByName >= 0 )
    {
      v12 = 0;
      goto LABEL_11;
    }
    v13 = 180;
  }
  else
  {
    v13 = 179;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobekeyboardcore.cpp",
    (const char *)(unsigned int)KeyboardsForLocaleByName,
    v15);
LABEL_11:
  WindowsDeleteString(string);
  return v12;
}

```

## disassembly

```asm
0x180048960  mov     [rsp+arg_8], rbx
0x180048965  mov     [rsp+arg_10], rsi
0x18004896a  push    rdi; int
0x18004896b  sub     rsp, 20h
0x18004896f  mov     rdi, r8
0x180048972  mov     rsi, rdx
0x180048975  mov     rbx, rcx
0x180048978  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18004897d  test    al, al
0x18004897f  jz      short loc_180048999
0x180048981  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x180048988  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x18004898d  lea     rdx, aCloudexperienc_35; "CloudExperienceHostAPI::OobeKeyboardSta"...
0x180048994  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x180048999  mov     qword ptr [rdi], 0
0x1800489a0  mov     rcx, [rbx+38h]
0x1800489a4  test    rcx, rcx
0x1800489a7  jz      short loc_1800489C0
0x1800489a9  mov     rax, [rcx]
0x1800489ac  mov     r8, rdi
0x1800489af  mov     rdx, rsi
0x1800489b2  mov     rax, [rax+40h]
0x1800489b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489bb  jmp     loc_180048A46
0x1800489c0  mov     [rsp+28h+string], 0
0x1800489c9  mov     rax, [rsi]
0x1800489cc  mov     rbx, [rax+30h]
0x1800489d0  xor     ecx, ecx; string
0x1800489d2  call    cs:__imp_WindowsDeleteString
0x1800489d8  mov     [rsp+28h+string], 0
0x1800489e1  lea     rdx, [rsp+28h+string]
0x1800489e6  mov     rcx, rsi
0x1800489e9  mov     rax, rbx
0x1800489ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489f1  mov     ebx, eax
0x1800489f3  test    eax, eax
0x1800489f5  jns     short loc_1800489FE
0x1800489f7  mov     edx, 0B3h
0x1800489fc  jmp     short loc_180048A21
0x1800489fe  xor     edx, edx; length
0x180048a00  mov     rcx, [rsp+28h+string]; string
0x180048a05  call    cs:__imp_WindowsGetStringRawBuffer
0x180048a0b  mov     rdx, rdi
0x180048a0e  mov     rcx, rax
0x180048a11  call    ?GetKeyboardsForLocaleByName@OobeKeyboardStaticsCore@CloudExperienceHostAPI@@CAJPEBGPEAPEAU?$IVectorView@PEAUIOobeKeyboard@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z; CloudExperienceHostAPI::OobeKeyboardStaticsCore::GetKeyboardsForLocaleByName(ushort const *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeKeyboard *> * *)
0x180048a16  mov     ebx, eax
0x180048a18  test    eax, eax
0x180048a1a  jns     short loc_180048A37
0x180048a1c  mov     edx, 0B4h; void *
0x180048a21  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\oobe\\core\\compone"...
0x180048a28  mov     r9d, eax; char *
0x180048a2b  mov     rcx, [rsp+28h]; this
0x180048a30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048a35  jmp     short loc_180048A39
0x180048a37  xor     ebx, ebx
0x180048a39  mov     rcx, [rsp+28h+string]; string
0x180048a3e  call    cs:__imp_WindowsDeleteString
0x180048a44  mov     eax, ebx
0x180048a46  mov     rbx, [rsp+28h+arg_8]
0x180048a4b  mov     rsi, [rsp+28h+arg_10]
0x180048a50  add     rsp, 20h
0x180048a54  pop     rdi
0x180048a55  retn
```
