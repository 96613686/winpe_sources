# TapProcessor::Initialize(void)

- ea: `0x1800bc4b8`
- end: `0x1800bc590`
- name: `?Initialize@TapProcessor@@IEAAJXZ`
- size: `216`
- prototype: `int(TapProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801acecc`

## callees

- `0x180012b74`
- `0x18008dcac`
- `0x18008e0d8`
- `0x1800bc4b8`
- `0x1800bc598`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x1800bc4d2`
- `CoreMessaging!CoreUICreate` at `0x1800bc4d2`
- `NInput!CreateInteractionContext` at `0x1800bc4fa`
- `NInput!CreateInteractionContext` at `0x1800bc4fa`

## pseudocode

```c
__int64 __fastcall TapProcessor::Initialize(TapProcessor *this)
{
  int v2; // eax
  int InteractionContext; // eax
  int v4; // eax
  int InputServiceProxy; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 40);
  v2 = CoreUICreate((char *)this + 40);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\lasttap\\system\\lib\\tapprocessor.cpp",
      (const char *)(unsigned int)v2,
      v7);
  InteractionContext = CreateInteractionContext((char *)this + 56);
  if ( InteractionContext < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\lasttap\\system\\lib\\tapprocessor.cpp",
      (const char *)(unsigned int)InteractionContext,
      v7);
  v4 = TapProcessor::ResetAndInitializeInteractionContext(this);
  if ( v4 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\lasttap\\system\\lib\\tapprocessor.cpp",
      (const char *)(unsigned int)v4,
      v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
  InputServiceProxy = CreateInputServiceProxy(((unsigned __int64)this + 8) & -(__int64)(this != 0), (char *)this + 48);
  if ( InputServiceProxy < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\lasttap\\system\\lib\\tapprocessor.cpp",
      (const char *)(unsigned int)InputServiceProxy,
      v7);
  return 0;
}

```

## disassembly

```asm
0x1800bc4b8  mov     [rsp+arg_0], rbx
0x1800bc4bd  push    rdi; int
0x1800bc4be  sub     rsp, 20h
0x1800bc4c2  mov     rdi, rcx
0x1800bc4c5  add     rcx, 28h ; '('
0x1800bc4c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc4ce  lea     rcx, [rdi+28h]
0x1800bc4d2  call    cs:__imp_CoreUICreate
0x1800bc4d8  test    eax, eax
0x1800bc4da  jns     short loc_1800BC4F6
0x1800bc4dc  mov     rcx, [rsp+28h]; this
0x1800bc4e1  lea     r8, aOnecoreuapWind_143; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bc4e8  mov     r9d, eax; char *
0x1800bc4eb  mov     edx, 3Bh ; ';'; void *
0x1800bc4f0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800bc4f6  lea     rcx, [rdi+38h]
0x1800bc4fa  call    cs:__imp_CreateInteractionContext
0x1800bc500  test    eax, eax
0x1800bc502  jns     short loc_1800BC51E
0x1800bc504  mov     rcx, [rsp+28h]; this
0x1800bc509  lea     r8, aOnecoreuapWind_143; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bc510  mov     r9d, eax; char *
0x1800bc513  mov     edx, 3Eh ; '>'; void *
0x1800bc518  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800bc51e  mov     rcx, rdi; this
0x1800bc521  call    ?ResetAndInitializeInteractionContext@TapProcessor@@AEAAJXZ; TapProcessor::ResetAndInitializeInteractionContext(void)
0x1800bc526  test    eax, eax
0x1800bc528  jns     short loc_1800BC544
0x1800bc52a  mov     rcx, [rsp+28h]; this
0x1800bc52f  lea     r8, aOnecoreuapWind_143; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bc536  mov     r9d, eax; char *
0x1800bc539  mov     edx, 3Fh ; '?'; void *
0x1800bc53e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800bc544  lea     rbx, [rdi+30h]
0x1800bc548  mov     rcx, rbx
0x1800bc54b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc550  lea     rax, [rdi+8]
0x1800bc554  mov     rdx, rbx
0x1800bc557  neg     rdi
0x1800bc55a  sbb     rcx, rcx
0x1800bc55d  and     rcx, rax
0x1800bc560  call    CreateInputServiceProxy
0x1800bc565  test    eax, eax
0x1800bc567  jns     short loc_1800BC583
0x1800bc569  mov     rcx, [rsp+28h]; this
0x1800bc56e  lea     r8, aOnecoreuapWind_143; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bc575  mov     r9d, eax; char *
0x1800bc578  mov     edx, 41h ; 'A'; void *
0x1800bc57d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800bc583  mov     rbx, [rsp+28h+arg_0]
0x1800bc588  xor     eax, eax
0x1800bc58a  add     rsp, 20h
0x1800bc58e  pop     rdi
0x1800bc58f  retn
```
