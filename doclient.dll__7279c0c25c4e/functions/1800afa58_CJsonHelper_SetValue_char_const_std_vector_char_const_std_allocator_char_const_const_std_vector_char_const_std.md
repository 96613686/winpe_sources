# CJsonHelper::SetValue(char const *,std::vector<char const *,std::allocator<char const *>> const &,std::vector<char const *,std::allocator<char const *>> const &)

- ea: `0x1800afa58`
- end: `0x1800afdea`
- name: `?SetValue@CJsonHelper@@QEAAJPEBDAEBV?$vector@PEBDV?$allocator@PEBD@std@@@std@@1@Z`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d9378`

## callees

- `0x18000ef98`
- `0x18009c2f0`
- `0x18009c368`
- `0x1800a979c`
- `0x1800afa58`
- `0x1800f82f0`
- `0x180108e50`
- `0x1801099b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afb25`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800afb60`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800afb60`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800afaf7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800afaf7`

## string_xrefs

- `0x1800afab9`: `Windows.Data.Json.JsonValue`
- `0x1800afb1e`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CJsonHelper::SetValue(_QWORD *a1, const WCHAR *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v6; // r15
  signed int ActivationFactory; // r14d
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  HSTRING v11; // rbx
  __int64 v12; // rcx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  HSTRING v16; // rbx
  __int64 v17; // rcx
  unsigned __int64 i; // r14
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PVOID, __int64 *); // rbx
  unsigned int v21; // r8d
  const WCHAR *p_hstringHeader; // rdx
  HSTRING_HEADER *v23; // rax
  int v24; // ebx
  __int64 v25; // rbx
  void (__fastcall *v26)(__int64, PVOID, __int64); // rsi
  __int64 v27; // rdi
  unsigned int v28; // r8d
  const WCHAR *Reserved1; // rcx
  HSTRING_HEADER *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rsi
  void (__fastcall *v33)(__int64, PVOID, __int64); // rdi
  __int64 v34; // rbx
  unsigned int v35; // r8d
  const WCHAR *v36; // rdx
  HSTRING_HEADER *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  const WCHAR *v43; // [rsp+40h] [rbp-29h] BYREF
  const WCHAR *v44; // [rsp+48h] [rbp-21h] BYREF
  HSTRING_HEADER v45; // [rsp+50h] [rbp-19h] BYREF
  __int64 v46; // [rsp+68h] [rbp-1h]
  __int64 v47; // [rsp+70h] [rbp+7h] BYREF
  __int64 v48; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v49; // [rsp+80h] [rbp+17h] BYREF

  v44 = a2;
  v6 = a1 + 2;
  ActivationFactory = a1[2] == 0 ? 0x80004005 : 0;
  if ( !a1[2] )
  {
    string = 0;
    v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
    if ( v8 < 0 )
    {
LABEL_35:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
      JUMPOUT(0x1800AFDE9LL);
    }
    v11 = string;
    v12 = *v6;
    if ( *v6 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    ActivationFactory = RoGetActivationFactory(v11, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, v6);
  }
  if ( ActivationFactory < 0 )
    return (unsigned int)ActivationFactory;
  v47 = 0;
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    goto LABEL_35;
  }
  v16 = string;
  v17 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v47 = 0;
  v48 = 0;
  ActivationFactory = RoActivateInstance(v16, &v48);
  if ( ActivationFactory >= 0 )
  {
    if ( !memcmp(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v47 = v48;
    }
    else
    {
      ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v48)(
                            v48,
                            &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                            &v47);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
  }
  if ( ActivationFactory >= 0 )
  {
    for ( i = 0; i < (qword_180195E20 - qword_180195E18) >> 3; ++i )
    {
      v48 = 0;
      v19 = *v6;
      v20 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)*v6 + 80LL);
      UTF8toWstr(&hstringHeader, *(_QWORD *)(*a4 + 8 * i), 0);
      p_hstringHeader = (const WCHAR *)&hstringHeader;
      if ( (unsigned __int64)string > 7 )
        p_hstringHeader = (const WCHAR *)hstringHeader.Reserved.Reserved1;
      v43 = p_hstringHeader;
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v45, &v43, v21);
      v24 = v20(v19, v23[1].Reserved.Reserved1, &v48);
      v46 = 0;
      std::wstring::~wstring((__int64)&hstringHeader);
      if ( v24 >= 0 )
      {
        v25 = v47;
        v26 = *(void (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v47 + 56LL);
        v27 = v48;
        UTF8toWstr(&hstringHeader, *(_QWORD *)(qword_180195E18 + 8 * i), 0);
        Reserved1 = (const WCHAR *)&hstringHeader;
        if ( (unsigned __int64)string > 7 )
          Reserved1 = (const WCHAR *)hstringHeader.Reserved.Reserved1;
        v43 = Reserved1;
        v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v45, &v43, v28);
        v26(v25, v30[1].Reserved.Reserved1, v27);
        v46 = 0;
        std::wstring::~wstring((__int64)&hstringHeader);
      }
      v31 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    v49 = 0;
    ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v47)(
                          v47,
                          &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
                          &v49);
    if ( ActivationFactory >= 0 )
    {
      v32 = *a1;
      v33 = *(void (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)*a1 + 56LL);
      v34 = v49;
      UTF8toWstr(&hstringHeader, v44, 0);
      v36 = (const WCHAR *)&hstringHeader;
      if ( (unsigned __int64)string > 7 )
        v36 = (const WCHAR *)hstringHeader.Reserved.Reserved1;
      v44 = v36;
      v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v45, &v44, v35);
      v33(v32, v37[1].Reserved.Reserved1, v34);
      v46 = 0;
      std::wstring::~wstring((__int64)&hstringHeader);
    }
    v38 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  v39 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800afa58  mov     [rsp-8+arg_10], rbx
0x1800afa5d  push    rbp
0x1800afa5e  push    rsi
0x1800afa5f  push    rdi
0x1800afa60  push    r12
0x1800afa62  push    r13
0x1800afa64  push    r14
0x1800afa66  push    r15
0x1800afa68  lea     rbp, [rsp-27h]
0x1800afa6d  sub     rsp, 90h
0x1800afa74  mov     rax, cs:__security_cookie
0x1800afa7b  xor     rax, rsp
0x1800afa7e  mov     [rbp+57h+var_38], rax
0x1800afa82  mov     r13, r9
0x1800afa85  mov     [rbp+57h+var_78], rdx
0x1800afa89  mov     r12, rcx
0x1800afa8c  xor     esi, esi
0x1800afa8e  lea     r15, [rcx+10h]
0x1800afa92  mov     rax, [r15]
0x1800afa95  neg     rax
0x1800afa98  sbb     r14d, r14d
0x1800afa9b  not     r14d
0x1800afa9e  and     r14d, 80004005h
0x1800afaa5  cmp     [r15], rsi
0x1800afaa8  jnz     short loc_1800AFB00
0x1800afaaa  mov     [rbp+57h+string], rsi
0x1800afaae  lea     r9, [rbp+57h+string]; string
0x1800afab2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800afab6  lea     edx, [rsi+1Bh]; length
0x1800afab9  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x1800afac0  call    cs:__imp_WindowsCreateStringReference
0x1800afac6  test    eax, eax
0x1800afac8  js      loc_1800AFDE2
0x1800aface  mov     rbx, [rbp+57h+string]
0x1800afad2  mov     rcx, [r15]
0x1800afad5  test    rcx, rcx
0x1800afad8  jz      short loc_1800AFAEA
0x1800afada  mov     [r15], rsi
0x1800afadd  mov     rax, [rcx]
0x1800afae0  mov     rax, [rax+10h]
0x1800afae4  call    _guard_dispatch_icall
0x1800afae9  nop
0x1800afaea  mov     r8, r15
0x1800afaed  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800afaf4  mov     rcx, rbx
0x1800afaf7  call    cs:__imp_RoGetActivationFactory
0x1800afafd  mov     r14d, eax
0x1800afb00  test    r14d, r14d
0x1800afb03  js      loc_1800AFDB0
0x1800afb09  mov     [rbp+57h+var_50], rsi
0x1800afb0d  mov     [rbp+57h+string], rsi
0x1800afb11  lea     r9, [rbp+57h+string]; string
0x1800afb15  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800afb19  mov     edx, 1Ch; length
0x1800afb1e  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x1800afb25  call    cs:__imp_WindowsCreateStringReference
0x1800afb2b  test    eax, eax
0x1800afb2d  js      loc_1800AFDDA
0x1800afb33  mov     rbx, [rbp+57h+string]
0x1800afb37  mov     rcx, [rbp+57h+var_50]
0x1800afb3b  test    rcx, rcx
0x1800afb3e  jz      short loc_1800AFB51
0x1800afb40  mov     [rbp+57h+var_50], rsi
0x1800afb44  mov     rax, [rcx]
0x1800afb47  mov     rax, [rax+10h]
0x1800afb4b  call    _guard_dispatch_icall
0x1800afb50  nop
0x1800afb51  mov     [rbp+57h+var_50], rsi
0x1800afb55  mov     [rbp+57h+var_48], rsi
0x1800afb59  lea     rdx, [rbp+57h+var_48]
0x1800afb5d  mov     rcx, rbx
0x1800afb60  call    cs:__imp_RoActivateInstance
0x1800afb66  mov     r14d, eax
0x1800afb69  test    eax, eax
0x1800afb6b  js      short loc_1800AFBC2
0x1800afb6d  mov     r8d, 10h; Size
0x1800afb73  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800afb7a  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x1800afb81  call    memcmp
0x1800afb86  test    eax, eax
0x1800afb88  jnz     short loc_1800AFB94
0x1800afb8a  mov     rax, [rbp+57h+var_48]
0x1800afb8e  mov     [rbp+57h+var_50], rax
0x1800afb92  jmp     short loc_1800AFBC2
0x1800afb94  mov     rcx, [rbp+57h+var_48]
0x1800afb98  mov     rax, [rcx]
0x1800afb9b  lea     r8, [rbp+57h+var_50]
0x1800afb9f  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x1800afba6  mov     rax, [rax]
0x1800afba9  call    _guard_dispatch_icall
0x1800afbae  mov     r14d, eax
0x1800afbb1  mov     rcx, [rbp+57h+var_48]
0x1800afbb5  mov     rax, [rcx]
0x1800afbb8  mov     rax, [rax+10h]
0x1800afbbc  call    _guard_dispatch_icall
0x1800afbc1  nop
0x1800afbc2  test    r14d, r14d
0x1800afbc5  js      loc_1800AFD96
0x1800afbcb  mov     r14, rsi
0x1800afbce  mov     rax, cs:qword_180195E20
0x1800afbd5  sub     rax, cs:qword_180195E18
0x1800afbdc  sar     rax, 3
0x1800afbe0  test    rax, rax
0x1800afbe3  jz      loc_1800AFCF4
0x1800afbe9  mov     [rbp+57h+var_48], rsi
0x1800afbed  mov     rdi, [r15]
0x1800afbf0  mov     rax, [rdi]
0x1800afbf3  mov     rbx, [rax+50h]
0x1800afbf7  mov     rdx, [r13+0]
0x1800afbfb  xor     r8d, r8d
0x1800afbfe  mov     rdx, [rdx+r14*8]
0x1800afc02  lea     rcx, [rbp+57h+hstringHeader]
0x1800afc06  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800afc0b  nop
0x1800afc0c  lea     rdx, [rbp+57h+hstringHeader]
0x1800afc10  cmp     [rbp+57h+string], 7
0x1800afc15  cmova   rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800afc1a  mov     [rbp+57h+var_80], rdx
0x1800afc1e  lea     rdx, [rbp+57h+var_80]
0x1800afc22  lea     rcx, [rbp+57h+var_70]
0x1800afc26  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800afc2b  nop
0x1800afc2c  lea     r8, [rbp+57h+var_48]
0x1800afc30  mov     rdx, [rax+18h]
0x1800afc34  mov     rcx, rdi
0x1800afc37  mov     rax, rbx
0x1800afc3a  call    _guard_dispatch_icall
0x1800afc3f  mov     ebx, eax
0x1800afc41  mov     [rbp+57h+var_58], rsi
0x1800afc45  lea     rcx, [rbp+57h+hstringHeader]
0x1800afc49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800afc4e  test    ebx, ebx
0x1800afc50  js      short loc_1800AFCBC
0x1800afc52  mov     rbx, [rbp+57h+var_50]
0x1800afc56  mov     rax, [rbx]
0x1800afc59  mov     rsi, [rax+38h]
0x1800afc5d  mov     rdi, [rbp+57h+var_48]
0x1800afc61  xor     r8d, r8d
0x1800afc64  mov     rdx, cs:qword_180195E18
0x1800afc6b  mov     rdx, [rdx+r14*8]
0x1800afc6f  lea     rcx, [rbp+57h+hstringHeader]
0x1800afc73  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800afc78  nop
0x1800afc79  lea     rcx, [rbp+57h+hstringHeader]
0x1800afc7d  cmp     [rbp+57h+string], 7
0x1800afc82  cmova   rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800afc87  mov     [rbp+57h+var_80], rcx
0x1800afc8b  lea     rdx, [rbp+57h+var_80]
0x1800afc8f  lea     rcx, [rbp+57h+var_70]
0x1800afc93  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800afc98  nop
0x1800afc99  mov     r8, rdi
0x1800afc9c  mov     rdx, [rax+18h]
0x1800afca0  mov     rcx, rbx
0x1800afca3  mov     rax, rsi
0x1800afca6  call    _guard_dispatch_icall
0x1800afcab  nop
0x1800afcac  xor     esi, esi
0x1800afcae  mov     [rbp+57h+var_58], rsi
0x1800afcb2  lea     rcx, [rbp+57h+hstringHeader]
0x1800afcb6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800afcbb  nop
0x1800afcbc  mov     rcx, [rbp+57h+var_48]
0x1800afcc0  test    rcx, rcx
0x1800afcc3  jz      short loc_1800AFCD6
0x1800afcc5  mov     [rbp+57h+var_48], rsi
0x1800afcc9  mov     rax, [rcx]
0x1800afccc  mov     rax, [rax+10h]
0x1800afcd0  call    _guard_dispatch_icall
0x1800afcd5  nop
0x1800afcd6  inc     r14
0x1800afcd9  mov     rax, cs:qword_180195E20
0x1800afce0  sub     rax, cs:qword_180195E18
0x1800afce7  sar     rax, 3
0x1800afceb  cmp     r14, rax
0x1800afcee  jb      loc_1800AFBE9
0x1800afcf4  mov     [rbp+57h+var_40], rsi
0x1800afcf8  mov     rcx, [rbp+57h+var_50]
0x1800afcfc  mov     rax, [rcx]
0x1800afcff  lea     r8, [rbp+57h+var_40]
0x1800afd03  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800afd0a  mov     rax, [rax]
0x1800afd0d  call    _guard_dispatch_icall
0x1800afd12  mov     r14d, eax
0x1800afd15  test    eax, eax
0x1800afd17  js      short loc_1800AFD7C
0x1800afd19  mov     rsi, [r12]
0x1800afd1d  mov     rax, [rsi]
0x1800afd20  mov     rdi, [rax+38h]
0x1800afd24  mov     rbx, [rbp+57h+var_40]
0x1800afd28  xor     r8d, r8d
0x1800afd2b  mov     rdx, [rbp+57h+var_78]
0x1800afd2f  lea     rcx, [rbp+57h+hstringHeader]
0x1800afd33  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800afd38  nop
0x1800afd39  lea     rdx, [rbp+57h+hstringHeader]
0x1800afd3d  cmp     [rbp+57h+string], 7
0x1800afd42  cmova   rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800afd47  mov     [rbp+57h+var_78], rdx
0x1800afd4b  lea     rdx, [rbp+57h+var_78]
0x1800afd4f  lea     rcx, [rbp+57h+var_70]
0x1800afd53  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800afd58  nop
0x1800afd59  mov     r8, rbx
0x1800afd5c  mov     rdx, [rax+18h]
0x1800afd60  mov     rcx, rsi
0x1800afd63  mov     rax, rdi
0x1800afd66  call    _guard_dispatch_icall
0x1800afd6b  nop
0x1800afd6c  xor     esi, esi
0x1800afd6e  mov     [rbp+57h+var_58], rsi
0x1800afd72  lea     rcx, [rbp+57h+hstringHeader]
0x1800afd76  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800afd7b  nop
0x1800afd7c  mov     rcx, [rbp+57h+var_40]
0x1800afd80  test    rcx, rcx
0x1800afd83  jz      short loc_1800AFD96
0x1800afd85  mov     [rbp+57h+var_40], rsi
0x1800afd89  mov     rax, [rcx]
0x1800afd8c  mov     rax, [rax+10h]
0x1800afd90  call    _guard_dispatch_icall
0x1800afd95  nop
0x1800afd96  mov     rcx, [rbp+57h+var_50]
0x1800afd9a  test    rcx, rcx
0x1800afd9d  jz      short loc_1800AFDB0
0x1800afd9f  mov     [rbp+57h+var_50], rsi
0x1800afda3  mov     rax, [rcx]
0x1800afda6  mov     rax, [rax+10h]
0x1800afdaa  call    _guard_dispatch_icall
0x1800afdaf  nop
0x1800afdb0  mov     eax, r14d
0x1800afdb3  mov     rcx, [rbp+57h+var_38]
0x1800afdb7  xor     rcx, rsp; StackCookie
0x1800afdba  call    __security_check_cookie
0x1800afdbf  mov     rbx, [rsp+0C0h+arg_10]
0x1800afdc7  add     rsp, 90h
0x1800afdce  pop     r15
0x1800afdd0  pop     r14
0x1800afdd2  pop     r13
0x1800afdd4  pop     r12
0x1800afdd6  pop     rdi
0x1800afdd7  pop     rsi
0x1800afdd8  pop     rbp
0x1800afdd9  retn
0x1800afdda  mov     ecx, eax; this
0x1800afddc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800afde1  nop
0x1800afde2  mov     ecx, eax; this
0x1800afde4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
