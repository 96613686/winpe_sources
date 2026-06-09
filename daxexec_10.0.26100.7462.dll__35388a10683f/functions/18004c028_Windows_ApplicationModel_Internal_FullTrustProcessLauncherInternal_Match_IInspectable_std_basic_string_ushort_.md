# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(IInspectable *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004c028`
- end: `0x18004c427`
- name: `?Match@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CA_NPEAUIInspectable@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004c680`

## callees

- `0x1800053a0`
- `0x180010a84`
- `0x180011b04`
- `0x180038318`
- `0x18003ddd0`
- `0x18004acc0`
- `0x18004c028`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c0d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c0d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004c1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c2aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c30f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c2aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c30f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c27a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c27a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004c193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004c193`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
char __fastcall Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(
        __int64 a1,
        HSTRING a2,
        void *a3)
{
  int v6; // eax
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // rsi
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // r15
  int v15; // ebx
  int v16; // esi
  int v17; // eax
  __int64 v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, HSTRING, char *); // r14
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // r14
  int v28; // ebx
  HSTRING v29; // rcx
  WCHAR *StringRawBuffer; // rax
  __int64 v31; // rcx
  __int64 v33; // rcx
  HSTRING string1; // [rsp+20h] [rbp-69h] BYREF
  __int64 v35; // [rsp+28h] [rbp-61h] BYREF
  INT32 result; // [rsp+30h] [rbp-59h] BYREF
  HSTRING v37; // [rsp+38h] [rbp-51h] BYREF
  __int64 v38; // [rsp+40h] [rbp-49h] BYREF
  __int64 v39; // [rsp+48h] [rbp-41h] BYREF
  char *v40; // [rsp+50h] [rbp-39h]
  __int64 v41; // [rsp+58h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-29h] BYREF
  HSTRING string; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER v44; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v45; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v41 = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v35 = 0;
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
         a1,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v35);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v6,
      (int)string1);
  v39 = 0;
  LODWORD(v40) = 0;
  v7 = v35;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v35 + 48LL);
  v37 = (HSTRING)&v39;
  v38 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"@GroupId", 8u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
LABEL_39:
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0x160,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v12,
      (int)string1);
  }
  v12 = v8(v7, string, &v38);
  v13 = retaddr;
  if ( v12 < 0 )
    goto LABEL_39;
  string = 0;
  RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v37);
  v14 = v39;
  v15 = (int)v40;
  WindowsDeleteString(0);
  string1 = 0;
  v16 = -2147316576;
  if ( v15 == 7 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 152LL))(v14, &string1);
  }
  else
  {
    v17 = -2147316576;
    if ( v15 < 0 )
      v17 = v15;
  }
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v17,
      (int)string1);
  result = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(HSTRING *)a2;
  v37 = a2;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v44, &v37);
  v19 = WindowsCompareStringOrdinal(string1, *(HSTRING *)(v18 + 24), &result);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v19,
      (int)string1);
  if ( !result )
  {
    v20 = v35;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v35 + 48LL);
    hstringHeader.Reserved.Reserved1 = &v39;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    v45 = 0;
    v22 = WindowsCreateStringReference(L"@Parameters", 0xBu, &v44, &v45);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
    }
    else
    {
      v25 = v21(v20, v45, &hstringHeader.Reserved.Reserved2[8]);
      v26 = retaddr;
      if ( v25 >= 0 )
      {
        v45 = 0;
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&hstringHeader);
        v37 = 0;
        v27 = v39;
        v28 = (int)v40;
        WindowsDeleteString(0);
        v29 = 0;
        v37 = 0;
        if ( v28 == 7 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 152LL))(v27, &v37);
          v29 = v37;
        }
        else if ( v28 < 0 )
        {
          v16 = v28;
        }
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x170,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
            (const char *)(unsigned int)v16,
            (int)string1);
        StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(v29, 0);
        std::wstring::operator=(a3, StringRawBuffer);
        WindowsDeleteString(v37);
        v37 = 0;
        WindowsDeleteString(string1);
        string1 = 0;
        if ( v39 && (((_DWORD)v40 - 3) & 0xFFFFFFFB) == 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        v31 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
        return 1;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v26,
      (void *)0x16D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v25,
      (int)string1);
  }
  WindowsDeleteString(string1);
  string1 = 0;
  if ( v39 && (((_DWORD)v40 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  v33 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18004c028  mov     [rsp-8+arg_0], rbx
0x18004c02d  push    rbp
0x18004c02e  push    rsi
0x18004c02f  push    rdi
0x18004c030  push    r12
0x18004c032  push    r13
0x18004c034  push    r14
0x18004c036  push    r15
0x18004c038  lea     rbp, [rsp-27h]
0x18004c03d  sub     rsp, 0B0h
0x18004c044  mov     rax, cs:__security_cookie
0x18004c04b  xor     rax, rsp
0x18004c04e  mov     [rbp+57h+var_40], rax
0x18004c052  mov     r12, r8
0x18004c055  mov     r14, rdx
0x18004c058  mov     rdi, rcx
0x18004c05b  mov     [rbp+57h+var_88], rcx
0x18004c05f  xor     r13d, r13d
0x18004c062  test    rcx, rcx
0x18004c065  jz      short loc_18004C074
0x18004c067  mov     rax, [rcx]
0x18004c06a  mov     rax, [rax+8]
0x18004c06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c073  nop
0x18004c074  mov     [rbp+57h+var_B8], r13
0x18004c078  mov     rax, [rdi]
0x18004c07b  lea     r8, [rbp+57h+var_B8]
0x18004c07f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004c086  mov     rcx, rdi
0x18004c089  mov     rax, [rax]
0x18004c08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c091  nop
0x18004c092  mov     rcx, [rbp+5Fh]; this
0x18004c096  test    eax, eax
0x18004c098  js      loc_18004C3AE
0x18004c09e  mov     [rbp+57h+var_98], r13
0x18004c0a2  mov     dword ptr [rbp+57h+var_90], r13d
0x18004c0a6  mov     rbx, [rbp+57h+var_B8]
0x18004c0aa  mov     rax, [rbx]
0x18004c0ad  mov     rsi, [rax+30h]
0x18004c0b1  lea     rax, [rbp+57h+var_98]
0x18004c0b5  mov     [rbp+57h+var_A8], rax
0x18004c0b9  mov     [rbp+57h+var_A0], r13
0x18004c0bd  mov     [rbp+57h+string], r13
0x18004c0c1  lea     r9, [rbp+57h+string]; string
0x18004c0c5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004c0c9  mov     edx, 8; length
0x18004c0ce  lea     rcx, aGroupid; "@GroupId"
0x18004c0d5  call    cs:__imp_WindowsCreateStringReference
0x18004c0dc  nop     dword ptr [rax+rax+00h]
0x18004c0e1  test    eax, eax
0x18004c0e3  js      loc_18004C3C3
0x18004c0e9  lea     r8, [rbp+57h+var_A0]
0x18004c0ed  mov     rdx, [rbp+57h+string]
0x18004c0f1  mov     rcx, rbx
0x18004c0f4  mov     rax, rsi
0x18004c0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0fc  mov     rcx, [rbp+5Fh]
0x18004c100  test    eax, eax
0x18004c102  js      loc_18004C3CB
0x18004c108  mov     [rbp+57h+string], r13
0x18004c10c  lea     rcx, [rbp+57h+var_A8]; this
0x18004c110  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18004c115  mov     [rbp+57h+string1], r13
0x18004c119  mov     r15, [rbp+57h+var_98]
0x18004c11d  mov     ebx, dword ptr [rbp+57h+var_90]
0x18004c120  xor     ecx, ecx; string
0x18004c122  call    cs:__imp_WindowsDeleteString
0x18004c129  nop     dword ptr [rax+rax+00h]
0x18004c12e  mov     [rbp+57h+string1], r13
0x18004c132  mov     esi, 80028CA0h
0x18004c137  cmp     ebx, 7
0x18004c13a  jz      short loc_18004C145
0x18004c13c  mov     eax, esi
0x18004c13e  test    ebx, ebx
0x18004c140  cmovs   eax, ebx
0x18004c143  jmp     short loc_18004C15B
0x18004c145  mov     rax, [r15]
0x18004c148  lea     rdx, [rbp+57h+string1]
0x18004c14c  mov     rcx, r15
0x18004c14f  mov     rax, [rax+98h]
0x18004c156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c15b  mov     rcx, [rbp+5Fh]; this
0x18004c15f  test    eax, eax
0x18004c161  js      loc_18004C3E0
0x18004c167  mov     [rbp+57h+result], r13d
0x18004c16b  cmp     qword ptr [r14+18h], 7
0x18004c170  jbe     short loc_18004C175
0x18004c172  mov     r14, [r14]
0x18004c175  mov     [rbp+57h+var_A8], r14
0x18004c179  lea     rdx, [rbp+57h+var_A8]
0x18004c17d  lea     rcx, [rbp+57h+var_60]
0x18004c181  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004c186  nop
0x18004c187  lea     r8, [rbp+57h+result]; result
0x18004c18b  mov     rdx, [rax+18h]; string2
0x18004c18f  mov     rcx, [rbp+57h+string1]; string1
0x18004c193  call    cs:__imp_WindowsCompareStringOrdinal
0x18004c19a  nop     dword ptr [rax+rax+00h]
0x18004c19f  mov     rcx, [rbp+5Fh]; this
0x18004c1a3  test    eax, eax
0x18004c1a5  js      loc_18004C3F5
0x18004c1ab  cmp     [rbp+57h+result], r13d
0x18004c1af  jnz     loc_18004C30B
0x18004c1b5  mov     rbx, [rbp+57h+var_B8]
0x18004c1b9  mov     rax, [rbx]
0x18004c1bc  mov     r14, [rax+30h]
0x18004c1c0  lea     rax, [rbp+57h+var_98]
0x18004c1c4  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18004c1c8  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x18004c1cc  mov     [rbp+57h+var_48], r13
0x18004c1d0  lea     r9, [rbp+57h+var_48]; string
0x18004c1d4  lea     r8, [rbp+57h+var_60]; hstringHeader
0x18004c1d8  mov     edx, 0Bh; length
0x18004c1dd  lea     rcx, aParameters_0; "@Parameters"
0x18004c1e4  call    cs:__imp_WindowsCreateStringReference
0x18004c1eb  nop     dword ptr [rax+rax+00h]
0x18004c1f0  test    eax, eax
0x18004c1f2  js      loc_18004C40A
0x18004c1f8  lea     r8, [rbp+57h+hstringHeader.Reserved+8]
0x18004c1fc  mov     rdx, [rbp+57h+var_48]
0x18004c200  mov     rcx, rbx
0x18004c203  mov     rax, r14
0x18004c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c20b  mov     rcx, [rbp+5Fh]
0x18004c20f  test    eax, eax
0x18004c211  js      loc_18004C412
0x18004c217  mov     [rbp+57h+var_48], r13
0x18004c21b  lea     rcx, [rbp+57h+hstringHeader]; this
0x18004c21f  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18004c224  mov     [rbp+57h+var_A8], r13
0x18004c228  mov     r14, [rbp+57h+var_98]
0x18004c22c  mov     ebx, dword ptr [rbp+57h+var_90]
0x18004c22f  xor     ecx, ecx; string
0x18004c231  call    cs:__imp_WindowsDeleteString
0x18004c238  nop     dword ptr [rax+rax+00h]
0x18004c23d  mov     rcx, r13
0x18004c240  mov     [rbp+57h+var_A8], rcx
0x18004c244  cmp     ebx, 7
0x18004c247  jz      short loc_18004C250
0x18004c249  test    ebx, ebx
0x18004c24b  cmovs   esi, ebx
0x18004c24e  jmp     short loc_18004C26C
0x18004c250  mov     rax, [r14]
0x18004c253  lea     rdx, [rbp+57h+var_A8]
0x18004c257  mov     rcx, r14
0x18004c25a  mov     rax, [rax+98h]
0x18004c261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c266  mov     esi, eax
0x18004c268  mov     rcx, [rbp+57h+var_A8]; string
0x18004c26c  mov     rax, [rbp+5Fh]
0x18004c270  test    esi, esi
0x18004c272  js      loc_18004C396
0x18004c278  xor     edx, edx; length
0x18004c27a  call    cs:__imp_WindowsGetStringRawBuffer
0x18004c281  nop     dword ptr [rax+rax+00h]
0x18004c286  mov     rdx, rax; Src
0x18004c289  mov     rcx, r12; void *
0x18004c28c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18004c291  nop
0x18004c292  mov     rcx, [rbp+57h+var_A8]; string
0x18004c296  call    cs:__imp_WindowsDeleteString
0x18004c29d  nop     dword ptr [rax+rax+00h]
0x18004c2a2  mov     [rbp+57h+var_A8], r13
0x18004c2a6  mov     rcx, [rbp+57h+string1]; string
0x18004c2aa  call    cs:__imp_WindowsDeleteString
0x18004c2b1  nop     dword ptr [rax+rax+00h]
0x18004c2b6  mov     [rbp+57h+string1], r13
0x18004c2ba  mov     rcx, [rbp+57h+var_98]
0x18004c2be  test    rcx, rcx
0x18004c2c1  jz      short loc_18004C2DD
0x18004c2c3  mov     eax, dword ptr [rbp+57h+var_90]
0x18004c2c6  add     eax, 0FFFFFFFDh
0x18004c2c9  test    eax, 0FFFFFFFBh
0x18004c2ce  jnz     short loc_18004C2DD
0x18004c2d0  mov     rax, [rcx]
0x18004c2d3  mov     rax, [rax+10h]
0x18004c2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2dc  nop
0x18004c2dd  mov     rcx, [rbp+57h+var_B8]
0x18004c2e1  test    rcx, rcx
0x18004c2e4  jz      short loc_18004C2F7
0x18004c2e6  mov     [rbp+57h+var_B8], r13
0x18004c2ea  mov     rax, [rcx]
0x18004c2ed  mov     rax, [rax+10h]
0x18004c2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2f6  nop
0x18004c2f7  mov     rax, [rdi]
0x18004c2fa  mov     rcx, rdi
0x18004c2fd  mov     rax, [rax+10h]
0x18004c301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c306  nop
0x18004c307  mov     al, 1
0x18004c309  jmp     short loc_18004C36E
0x18004c30b  mov     rcx, [rbp+57h+string1]; string
0x18004c30f  call    cs:__imp_WindowsDeleteString
0x18004c316  nop     dword ptr [rax+rax+00h]
0x18004c31b  mov     [rbp+57h+string1], r13
0x18004c31f  mov     rcx, [rbp+57h+var_98]
0x18004c323  test    rcx, rcx
0x18004c326  jz      short loc_18004C342
0x18004c328  mov     eax, dword ptr [rbp+57h+var_90]
0x18004c32b  add     eax, 0FFFFFFFDh
0x18004c32e  test    eax, 0FFFFFFFBh
0x18004c333  jnz     short loc_18004C342
0x18004c335  mov     rax, [rcx]
0x18004c338  mov     rax, [rax+10h]
0x18004c33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c341  nop
0x18004c342  mov     rcx, [rbp+57h+var_B8]
0x18004c346  test    rcx, rcx
0x18004c349  jz      short loc_18004C35C
0x18004c34b  mov     [rbp+57h+var_B8], r13
0x18004c34f  mov     rax, [rcx]
0x18004c352  mov     rax, [rax+10h]
0x18004c356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c35b  nop
0x18004c35c  mov     rax, [rdi]
0x18004c35f  mov     rcx, rdi
0x18004c362  mov     rax, [rax+10h]
0x18004c366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c36b  nop
0x18004c36c  xor     al, al
0x18004c36e  mov     rcx, [rbp+57h+var_40]
0x18004c372  xor     rcx, rsp; StackCookie
0x18004c375  call    __security_check_cookie
0x18004c37a  mov     rbx, [rsp+0E0h+arg_0]
0x18004c382  add     rsp, 0B0h
0x18004c389  pop     r15
0x18004c38b  pop     r14
0x18004c38d  pop     r13
0x18004c38f  pop     r12
0x18004c391  pop     rdi
0x18004c392  pop     rsi
0x18004c393  pop     rbp
0x18004c394  retn
0x18004c396  mov     r9d, esi; char *
0x18004c399  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c3a0  mov     edx, 170h; void *
0x18004c3a5  mov     rcx, rax; this
0x18004c3a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c3ae  mov     r9d, eax; char *
0x18004c3b1  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c3b8  mov     edx, 15Dh; void *
0x18004c3bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c3c3  mov     ecx, eax; this
0x18004c3c5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004c3ca  nop
0x18004c3cb  mov     r9d, eax; char *
0x18004c3ce  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c3d5  mov     edx, 160h; void *
0x18004c3da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c3e0  mov     r9d, eax; char *
0x18004c3e3  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c3ea  mov     edx, 163h; void *
0x18004c3ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c3f5  mov     r9d, eax; char *
0x18004c3f8  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c3ff  mov     edx, 169h; void *
0x18004c404  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c40a  mov     ecx, eax; this
0x18004c40c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004c411  nop
0x18004c412  mov     r9d, eax; char *
0x18004c415  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004c41c  mov     edx, 16Dh; void *
0x18004c421  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
