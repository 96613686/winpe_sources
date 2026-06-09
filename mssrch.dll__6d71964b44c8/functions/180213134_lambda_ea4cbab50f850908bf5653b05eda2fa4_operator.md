# _lambda_ea4cbab50f850908bf5653b05eda2fa4_::operator()

- ea: `0x180213134`
- end: `0x180213279`
- name: `_lambda_ea4cbab50f850908bf5653b05eda2fa4_::operator()`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180211084`

## callees

- `0x18000f880`
- `0x18002dc6c`
- `0x1800a4348`
- `0x180213134`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802131f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802131f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021318f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021324c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021325e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021318f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021324c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021325e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802131d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802131e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802131d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802131e5`

## string_xrefs

- `0x1802131bd`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x180213179`: `@ProtocolName`
- `0x1802131a4`: `@ProtocolActivatorCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_ea4cbab50f850908bf5653b05eda2fa4_::operator()(__int64 *a1, __int64 a2, _BYTE *a3)
{
  int ElementValue; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  PCWSTR StringRawBuffer; // rax
  _QWORD *v10; // rax
  __int64 v11; // rbx
  __int64 *v12; // rsi
  HSTRING v14; // [rsp+20h] [rbp-10h] BYREF
  __int64 v15; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  string = 0;
  WindowsDeleteString(0);
  v14 = 0;
  ElementValue = StateRepoHelper::GetElementValue(L"@ProtocolName", a2, &v14);
  v7 = ElementValue;
  if ( ElementValue >= 0
    && (WindowsDeleteString(string),
        string = 0,
        ElementValue = StateRepoHelper::GetElementValue(L"@ProtocolActivatorCLSID", a2, &string),
        v7 = ElementValue,
        ElementValue >= 0) )
  {
    v8 = *a1;
    WindowsGetStringRawBuffer(string, 0);
    StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
    if ( !(unsigned int)_o__wcsicmp(**(_QWORD **)v8, StringRawBuffer) )
    {
      v10 = *(_QWORD **)(v8 + 16);
      v11 = *v10;
      v12 = *(__int64 **)(v8 + 8);
      if ( *v12 != *v10 )
      {
        if ( v11 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11 + 8LL))(*v10);
        v15 = *v12;
        *v12 = v11;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
      **(_BYTE **)(v8 + 24) = 1;
    }
    *a3 = **(_BYTE **)(v8 + 24);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)ElementValue,
      (int)v14);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v14);
  return v7;
}

```

## disassembly

```asm
0x180213134  mov     [rsp-18h+arg_0], rbx
0x180213139  mov     [rsp-18h+arg_8], rsi
0x18021313e  push    rbp
0x18021313f  push    rdi
0x180213140  push    r14
0x180213142  mov     rbp, rsp
0x180213145  sub     rsp, 30h
0x180213149  mov     r14, r8
0x18021314c  mov     rdi, rdx
0x18021314f  mov     rsi, rcx
0x180213152  mov     [rbp+var_10], 0
0x18021315a  mov     [rbp+string], 0
0x180213162  xor     ecx, ecx; string
0x180213164  call    cs:__imp_WindowsDeleteString
0x18021316a  mov     [rbp+var_10], 0
0x180213172  lea     r8, [rbp+var_10]
0x180213176  mov     rdx, rdi
0x180213179  lea     rcx, aProtocolname; "@ProtocolName"
0x180213180  call    ?GetElementValue@StateRepoHelper@@YAJPEB_WPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; StateRepoHelper::GetElementValue(wchar_t const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ * *)
0x180213185  mov     ebx, eax
0x180213187  test    eax, eax
0x180213189  js      short loc_1802131B6
0x18021318b  mov     rcx, [rbp+string]; string
0x18021318f  call    cs:__imp_WindowsDeleteString
0x180213195  mov     [rbp+string], 0
0x18021319d  lea     r8, [rbp+string]
0x1802131a1  mov     rdx, rdi
0x1802131a4  lea     rcx, aProtocolactiva; "@ProtocolActivatorCLSID"
0x1802131ab  call    ?GetElementValue@StateRepoHelper@@YAJPEB_WPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; StateRepoHelper::GetElementValue(wchar_t const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ * *)
0x1802131b0  mov     ebx, eax
0x1802131b2  test    eax, eax
0x1802131b4  jns     short loc_1802131D0
0x1802131b6  mov     rcx, [rbp+18h]; this
0x1802131ba  mov     r9d, eax; char *
0x1802131bd  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x1802131c4  mov     edx, 8Eh; void *
0x1802131c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802131ce  jmp     short loc_180213248
0x1802131d0  mov     rdi, [rsi]
0x1802131d3  xor     edx, edx; length
0x1802131d5  mov     rcx, [rbp+string]; string
0x1802131d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1802131df  xor     edx, edx; length
0x1802131e1  mov     rcx, [rbp+var_10]; string
0x1802131e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1802131eb  mov     rcx, [rdi]
0x1802131ee  mov     rdx, rax
0x1802131f1  mov     rcx, [rcx]
0x1802131f4  call    cs:__imp__o__wcsicmp
0x1802131fa  test    eax, eax
0x1802131fc  jnz     short loc_18021323D
0x1802131fe  mov     rax, [rdi+10h]
0x180213202  mov     rbx, [rax]
0x180213205  mov     rsi, [rdi+8]
0x180213209  cmp     [rsi], rbx
0x18021320c  jz      short loc_180213236
0x18021320e  test    rbx, rbx
0x180213211  jz      short loc_180213223
0x180213213  mov     rax, [rbx]
0x180213216  mov     rcx, rbx
0x180213219  mov     rax, [rax+8]
0x18021321d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180213222  nop
0x180213223  mov     rax, [rsi]
0x180213226  mov     [rbp+var_8], rax
0x18021322a  mov     [rsi], rbx
0x18021322d  lea     rcx, [rbp+var_8]
0x180213231  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180213236  mov     rax, [rdi+18h]
0x18021323a  mov     byte ptr [rax], 1
0x18021323d  mov     rax, [rdi+18h]
0x180213241  mov     cl, [rax]
0x180213243  mov     [r14], cl
0x180213246  xor     ebx, ebx
0x180213248  mov     rcx, [rbp+string]; string
0x18021324c  call    cs:__imp_WindowsDeleteString
0x180213252  mov     [rbp+string], 0
0x18021325a  mov     rcx, [rbp+var_10]; string
0x18021325e  call    cs:__imp_WindowsDeleteString
0x180213264  mov     eax, ebx
0x180213266  mov     rbx, [rsp+30h+arg_0]
0x18021326b  mov     rsi, [rsp+30h+arg_8]
0x180213270  add     rsp, 30h
0x180213274  pop     r14
0x180213276  pop     rdi
0x180213277  pop     rbp
0x180213278  retn
```
