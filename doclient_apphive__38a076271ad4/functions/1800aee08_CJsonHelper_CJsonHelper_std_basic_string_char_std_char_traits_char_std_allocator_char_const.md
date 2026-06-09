# CJsonHelper::CJsonHelper(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800aee08`
- end: `0x1800af1aa`
- name: `??0CJsonHelper@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `930`
- prototype: ``
- caller_count: `17`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002123c`
- `0x1800854d8`
- `0x180085a04`
- `0x1800d7db8`
- `0x1800d8434`
- `0x1800d9574`
- `0x1800e54d8`
- `0x1800e75b0`
- `0x1800e81e0`
- `0x1800eb264`
- `0x1800eb700`
- `0x1800eba4c`
- `0x1800ec0a0`
- `0x1800efc10`
- `0x1800f0620`
- `0x1800f1460`
- `0x1800f1cec`

## callees

- `0x18000cea4`
- `0x18000ef98`
- `0x18009c368`
- `0x1800a979c`
- `0x1800aee08`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aee6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aef3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aef9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800af04b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aee6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aef3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aef9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800af04b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aeea5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aefd7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aeea5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aefd7`

## string_xrefs

- `0x1800aee64`: `Windows.Data.Json.JsonObject`
- `0x1800aef96`: `Windows.Data.Json.JsonArray`
- `0x1800af113`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`
- `0x1800af13b`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`
- `0x1800af158`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`
- `0x1800af180`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`
- `0x1800af198`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\JsonHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
HSTRING __fastcall CJsonHelper::CJsonHelper(HSTRING a1, _QWORD *a2)
{
  __int64 *v4; // r15
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rdi
  __int64 v9; // rcx
  int ActivationFactory; // eax
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // r8d
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, HSTRING, HSTRING, _BYTE *); // r14
  __int64 v16; // rcx
  const WCHAR *v17; // rcx
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rdx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  HSTRING v28; // rbx
  __int64 v29; // rcx
  int v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, HSTRING, __int64 *, _BYTE *); // r14
  __int64 v36; // rcx
  const WCHAR *v37; // rcx
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  int v41; // eax
  wil::details::in1diag3 *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v46; // [rsp+20h] [rbp-49h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string[2]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v49[8]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v50; // [rsp+60h] [rbp-9h] BYREF
  __int64 v51; // [rsp+68h] [rbp-1h] BYREF
  PCWSTR sourceString[3]; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v53; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  string[1] = a1;
  *(_QWORD *)a1 = 0;
  v4 = (__int64 *)(a1 + 2);
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  v51 = 0;
  string[0] = 0;
  v5 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, string);
  if ( v5 < 0 )
    goto LABEL_41;
  v8 = string[0];
  v9 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  ActivationFactory = RoGetActivationFactory(v8, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v51);
  v11 = retaddr;
  if ( ActivationFactory < 0 )
LABEL_42:
    wil::details::in1diag3::Throw_Hr(
      v11,
      (void *)0xE,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v46);
  v12 = a2[2];
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  UTF8toWstr(sourceString, a2, v12);
  v49[0] = 0;
  v14 = v51;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v51 + 56LL);
  v16 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    *(_QWORD *)a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = (const WCHAR *)sourceString;
  if ( v53 > 7 )
    v17 = sourceString[0];
  string[0] = 0;
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( v17[v19] );
  if ( v19 > 0xFFFFFFFF )
  {
LABEL_40:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v13);
LABEL_41:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    goto LABEL_42;
  }
  if ( (int)v19 + 1 < (unsigned int)v19 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v13);
    __debugbreak();
  }
  v20 = WindowsCreateStringReference(v17, v19, &hstringHeader, string);
  if ( v20 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
LABEL_45:
    wil::details::in1diag3::Throw_Hr(
      v24,
      (void *)0x13,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)(unsigned int)v23,
      v46);
  }
  v23 = v15(v14, string[0], a1, v49);
  v24 = retaddr;
  if ( v23 < 0 )
    goto LABEL_45;
  if ( !sourceString[2] || v49[0] )
    goto LABEL_36;
  v50 = 0;
  string[0] = 0;
  v25 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
    goto LABEL_47;
  }
  v28 = string[0];
  v29 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = RoGetActivationFactory(v28, &GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba, &v50);
  v33 = retaddr;
  if ( v30 < 0 )
LABEL_47:
    wil::details::in1diag3::Throw_Hr(
      v33,
      (void *)0x18,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)(unsigned int)v30,
      v46);
  v34 = v50;
  v35 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *, _BYTE *))(*(_QWORD *)v50 + 56LL);
  v36 = *v4;
  if ( *v4 )
  {
    *v4 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = (const WCHAR *)sourceString;
  if ( v53 > 7 )
    v37 = sourceString[0];
  string[0] = 0;
  do
    ++v18;
  while ( v37[v18] );
  if ( v18 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v31, v32);
    goto LABEL_40;
  }
  if ( (int)v18 + 1 < (unsigned int)v18 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v31, v32);
    __debugbreak();
  }
  v38 = WindowsCreateStringReference(v37, v18, &hstringHeader, string);
  if ( v38 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
LABEL_50:
    wil::details::in1diag3::Throw_Hr(
      v42,
      (void *)0x1B,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)(unsigned int)v41,
      v46);
  }
  v41 = v35(v34, string[0], v4, v49);
  v42 = retaddr;
  if ( v41 < 0 )
    goto LABEL_50;
  if ( !v49[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\JsonHelper.cpp",
      (const char *)0x8007000DLL,
      v46);
  v43 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
LABEL_36:
  std::wstring::~wstring(sourceString);
  v44 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  return a1;
}

```

## disassembly

```asm
0x1800aee08  mov     [rsp-8+arg_10], rbx
0x1800aee0d  mov     [rsp-8+arg_18], rsi
0x1800aee12  push    rbp
0x1800aee13  push    rdi
0x1800aee14  push    r12
0x1800aee16  push    r14
0x1800aee18  push    r15
0x1800aee1a  lea     rbp, [rsp-37h]
0x1800aee1f  sub     rsp, 0A0h
0x1800aee26  mov     rax, cs:__security_cookie
0x1800aee2d  xor     rax, rsp
0x1800aee30  mov     [rbp+57h+var_30], rax
0x1800aee34  mov     rbx, rdx
0x1800aee37  mov     rsi, rcx
0x1800aee3a  mov     [rbp+57h+var_70], rcx
0x1800aee3e  xor     r12d, r12d
0x1800aee41  mov     [rcx], r12
0x1800aee44  lea     r15, [rcx+8]
0x1800aee48  mov     [r15], r12
0x1800aee4b  mov     [rcx+10h], r12
0x1800aee4f  mov     [rbp+57h+var_58], r12
0x1800aee53  mov     [rbp+57h+string], r12
0x1800aee57  lea     r9, [rbp+57h+string]; string
0x1800aee5b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800aee5f  lea     edx, [r12+1Ch]; length
0x1800aee64  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x1800aee6b  call    cs:__imp_WindowsCreateStringReference
0x1800aee71  test    eax, eax
0x1800aee73  js      loc_1800AF108
0x1800aee79  mov     rdi, [rbp+57h+string]
0x1800aee7d  mov     rcx, [rbp+57h+var_58]
0x1800aee81  test    rcx, rcx
0x1800aee84  jz      short loc_1800AEE97
0x1800aee86  mov     [rbp+57h+var_58], r12
0x1800aee8a  mov     rax, [rcx]
0x1800aee8d  mov     rax, [rax+10h]
0x1800aee91  call    _guard_dispatch_icall
0x1800aee96  nop
0x1800aee97  lea     r8, [rbp+57h+var_58]
0x1800aee9b  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1800aeea2  mov     rcx, rdi
0x1800aeea5  call    cs:__imp_RoGetActivationFactory
0x1800aeeab  mov     rcx, [rbp+5Fh]
0x1800aeeaf  test    eax, eax
0x1800aeeb1  js      loc_1800AF110
0x1800aeeb7  mov     r8, [rbx+10h]
0x1800aeebb  cmp     qword ptr [rbx+18h], 0Fh
0x1800aeec0  jbe     short loc_1800AEEC5
0x1800aeec2  mov     rbx, [rbx]
0x1800aeec5  mov     rdx, rbx
0x1800aeec8  lea     rcx, [rbp+57h+sourceString]
0x1800aeecc  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800aeed1  nop
0x1800aeed2  mov     [rbp+57h+var_68], r12b
0x1800aeed6  mov     rbx, [rbp+57h+var_58]
0x1800aeeda  mov     rax, [rbx]
0x1800aeedd  mov     r14, [rax+38h]
0x1800aeee1  mov     rcx, [rsi]
0x1800aeee4  test    rcx, rcx
0x1800aeee7  jz      short loc_1800AEEF9
0x1800aeee9  mov     [rsi], r12
0x1800aeeec  mov     rax, [rcx]
0x1800aeeef  mov     rax, [rax+10h]
0x1800aeef3  call    _guard_dispatch_icall
0x1800aeef8  nop
0x1800aeef9  lea     rcx, [rbp+57h+sourceString]
0x1800aeefd  cmp     [rbp+57h+var_38], 7
0x1800aef02  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x1800aef07  mov     [rbp+57h+string], r12
0x1800aef0b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800aef0f  mov     rdx, rdi
0x1800aef12  inc     rdx; int
0x1800aef15  cmp     [rcx+rdx*2], r12w
0x1800aef1a  jnz     short loc_1800AEF12
0x1800aef1c  mov     eax, 0FFFFFFFFh
0x1800aef21  cmp     rdx, rax
0x1800aef24  ja      loc_1800AF0FD
0x1800aef2a  lea     eax, [rdx+1]
0x1800aef2d  cmp     eax, edx
0x1800aef2f  jb      loc_1800AF125
0x1800aef35  lea     r9, [rbp+57h+string]; string
0x1800aef39  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800aef3d  call    cs:__imp_WindowsCreateStringReference
0x1800aef43  test    eax, eax
0x1800aef45  js      loc_1800AF130
0x1800aef4b  lea     r9, [rbp+57h+var_68]
0x1800aef4f  mov     r8, rsi
0x1800aef52  mov     rdx, [rbp+57h+string]
0x1800aef56  mov     rcx, rbx
0x1800aef59  mov     rax, r14
0x1800aef5c  call    _guard_dispatch_icall
0x1800aef61  mov     rcx, [rbp+5Fh]
0x1800aef65  test    eax, eax
0x1800aef67  js      loc_1800AF138
0x1800aef6d  cmp     [rbp+57h+var_40], r12
0x1800aef71  jz      loc_1800AF0A3
0x1800aef77  cmp     [rbp+57h+var_68], r12b
0x1800aef7b  jnz     loc_1800AF0A3
0x1800aef81  mov     [rbp+57h+var_60], r12
0x1800aef85  mov     [rbp+57h+string], r12
0x1800aef89  lea     r9, [rbp+57h+string]; string
0x1800aef8d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800aef91  mov     edx, 1Bh; length
0x1800aef96  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QB_WB; "Windows.Data.Json.JsonArray"
0x1800aef9d  call    cs:__imp_WindowsCreateStringReference
0x1800aefa3  test    eax, eax
0x1800aefa5  js      loc_1800AF14D
0x1800aefab  mov     rbx, [rbp+57h+string]
0x1800aefaf  mov     rcx, [rbp+57h+var_60]
0x1800aefb3  test    rcx, rcx
0x1800aefb6  jz      short loc_1800AEFC9
0x1800aefb8  mov     [rbp+57h+var_60], r12
0x1800aefbc  mov     rax, [rcx]
0x1800aefbf  mov     rax, [rax+10h]
0x1800aefc3  call    _guard_dispatch_icall
0x1800aefc8  nop
0x1800aefc9  lea     r8, [rbp+57h+var_60]
0x1800aefcd  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x1800aefd4  mov     rcx, rbx
0x1800aefd7  call    cs:__imp_RoGetActivationFactory
0x1800aefdd  mov     rcx, [rbp+5Fh]
0x1800aefe1  test    eax, eax
0x1800aefe3  js      loc_1800AF155
0x1800aefe9  mov     rbx, [rbp+57h+var_60]
0x1800aefed  mov     rax, [rbx]
0x1800aeff0  mov     r14, [rax+38h]
0x1800aeff4  mov     rcx, [r15]
0x1800aeff7  test    rcx, rcx
0x1800aeffa  jz      short loc_1800AF00C
0x1800aeffc  mov     [r15], r12
0x1800aefff  mov     rax, [rcx]
0x1800af002  mov     rax, [rax+10h]
0x1800af006  call    _guard_dispatch_icall
0x1800af00b  nop
0x1800af00c  lea     rcx, [rbp+57h+sourceString]
0x1800af010  cmp     [rbp+57h+var_38], 7
0x1800af015  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x1800af01a  mov     [rbp+57h+string], r12
0x1800af01e  inc     rdi
0x1800af021  cmp     [rcx+rdi*2], r12w
0x1800af026  jnz     short loc_1800AF01E
0x1800af028  mov     eax, 0FFFFFFFFh
0x1800af02d  cmp     rdi, rax
0x1800af030  ja      loc_1800AF0F2
0x1800af036  lea     eax, [rdi+1]
0x1800af039  cmp     eax, edi
0x1800af03b  jb      loc_1800AF16A
0x1800af041  lea     r9, [rbp+57h+string]; string
0x1800af045  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800af049  mov     edx, edi; length
0x1800af04b  call    cs:__imp_WindowsCreateStringReference
0x1800af051  test    eax, eax
0x1800af053  js      loc_1800AF175
0x1800af059  lea     r9, [rbp+57h+var_68]
0x1800af05d  mov     r8, r15
0x1800af060  mov     rdx, [rbp+57h+string]
0x1800af064  mov     rcx, rbx
0x1800af067  mov     rax, r14
0x1800af06a  call    _guard_dispatch_icall
0x1800af06f  mov     rcx, [rbp+5Fh]
0x1800af073  test    eax, eax
0x1800af075  js      loc_1800AF17D
0x1800af07b  mov     rcx, [rbp+5Fh]; this
0x1800af07f  cmp     [rbp+57h+var_68], r12b
0x1800af083  jz      loc_1800AF192
0x1800af089  mov     rcx, [rbp+57h+var_60]
0x1800af08d  test    rcx, rcx
0x1800af090  jz      short loc_1800AF0A3
0x1800af092  mov     [rbp+57h+var_60], r12
0x1800af096  mov     rax, [rcx]
0x1800af099  mov     rax, [rax+10h]
0x1800af09d  call    _guard_dispatch_icall
0x1800af0a2  nop
0x1800af0a3  lea     rcx, [rbp+57h+sourceString]
0x1800af0a7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800af0ac  nop
0x1800af0ad  mov     rcx, [rbp+57h+var_58]
0x1800af0b1  test    rcx, rcx
0x1800af0b4  jz      short loc_1800AF0C7
0x1800af0b6  mov     [rbp+57h+var_58], r12
0x1800af0ba  mov     rdx, [rcx]
0x1800af0bd  mov     rax, [rdx+10h]
0x1800af0c1  call    _guard_dispatch_icall
0x1800af0c6  nop
0x1800af0c7  mov     rax, rsi
0x1800af0ca  mov     rcx, [rbp+57h+var_30]
0x1800af0ce  xor     rcx, rsp; StackCookie
0x1800af0d1  call    __security_check_cookie
0x1800af0d6  lea     r11, [rsp+0C0h+var_20]
0x1800af0de  mov     rbx, [r11+40h]
0x1800af0e2  mov     rsi, [r11+48h]
0x1800af0e6  mov     rsp, r11
0x1800af0e9  pop     r15
0x1800af0eb  pop     r14
0x1800af0ed  pop     r12
0x1800af0ef  pop     rdi
0x1800af0f0  pop     rbp
0x1800af0f1  retn
0x1800af0f2  mov     ecx, 80070216h; this
0x1800af0f7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af0fc  nop
0x1800af0fd  mov     ecx, 80070216h; this
0x1800af102  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af107  nop
0x1800af108  mov     ecx, eax; this
0x1800af10a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af10f  nop
0x1800af110  mov     r9d, eax; char *
0x1800af113  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800af11a  mov     edx, 0Eh; void *
0x1800af11f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af125  mov     ecx, 80070216h; this
0x1800af12a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af12f  int     3; Trap to Debugger
0x1800af130  mov     ecx, eax; this
0x1800af132  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af137  nop
0x1800af138  mov     r9d, eax; char *
0x1800af13b  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800af142  mov     edx, 13h; void *
0x1800af147  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af14d  mov     ecx, eax; this
0x1800af14f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af154  nop
0x1800af155  mov     r9d, eax; char *
0x1800af158  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800af15f  mov     edx, 18h; void *
0x1800af164  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af16a  mov     ecx, 80070216h; this
0x1800af16f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af174  int     3; Trap to Debugger
0x1800af175  mov     ecx, eax; this
0x1800af177  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800af17c  nop
0x1800af17d  mov     r9d, eax; char *
0x1800af180  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800af187  mov     edx, 1Bh; void *
0x1800af18c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800af192  mov     r9d, 8007000Dh; char *
0x1800af198  lea     r8, aCW1SSrcDeliver_40; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800af19f  mov     edx, 1Ch; void *
0x1800af1a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
