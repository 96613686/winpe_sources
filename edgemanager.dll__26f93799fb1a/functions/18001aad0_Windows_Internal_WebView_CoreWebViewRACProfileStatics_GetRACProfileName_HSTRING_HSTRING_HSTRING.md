# Windows::Internal::WebView::CoreWebViewRACProfileStatics::GetRACProfileName(HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x18001aad0`
- end: `0x18001ad2b`
- name: `?GetRACProfileName@CoreWebViewRACProfileStatics@WebView@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAPEAU5@@Z`
- size: `603`
- prototype: `int(Windows::Internal::WebView::CoreWebViewRACProfileStatics *__hidden this, HSTRING, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180007810`
- `0x18000a290`
- `0x180018b30`
- `0x18001aad0`
- `0x18001b178`
- `0x18001b218`
- `0x18001b2f8`
- `0x18001b3c8`
- `0x18001b4b4`
- `0x18001b4f0`
- `0x18001b518`
- `0x180023298`
- `0x180025d68`
- `0x1800274e0`
- `0x18002b530`
- `0x18002c640`
- `0x180035b88`
- `0x18003692c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ab13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ab38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ab13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ab38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001acd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001acd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ad07`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::WebView::CoreWebViewRACProfileStatics::GetRACProfileName(
        HANDLE *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING *a4)
{
  const unsigned __int16 *StringRawBuffer; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  const char *v10; // r9
  unsigned __int64 v11; // rcx
  const char *v12; // r9
  _QWORD *v13; // rax
  HRESULT v14; // eax
  unsigned int v16; // [rsp+20h] [rbp-99h] BYREF
  HSTRING string; // [rsp+28h] [rbp-91h] BYREF
  _BYTE v18[16]; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-19h] BYREF
  wchar_t v23[4]; // [rsp+C0h] [rbp+7h] BYREF
  wchar_t Buffer; // [rsp+C8h] [rbp+Fh] BYREF
  int v25; // [rsp+CAh] [rbp+11h]
  __int16 v26; // [rsp+CEh] [rbp+15h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( (((unsigned __int64)this[8] + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    Windows::Internal::WebView::CoreWebViewRACProfileStatics::LoadRACProfileMap(this - 5, StringRawBuffer);
    Windows::Internal::WebView::CoreWebViewRACProfileStatics::LoadNextID((Windows::Internal::WebView::CoreWebViewRACProfileStatics *)(this - 5));
  }
  string = 0;
  WindowsGetStringRawBuffer(a2, 0);
  std::wstring::wstring(v19);
  v8 = *(_QWORD **)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                     this + 9,
                     v23,
                     v19);
  if ( v8 == this[9] )
  {
    Buffer = 0;
    v25 = 0;
    v26 = 0;
    if ( swprintf_s(&Buffer, 4u, L"%03u", *((unsigned int *)this + 14)) == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
        v10);
    std::wstring::wstring(v22);
    v16 = 0;
    v11 = -1;
    do
      ++v11;
    while ( *(&Buffer + v11) );
    if ( (int)ULongLongToULong(v11, &v16) >= 0 )
      Microsoft::WRL::Wrappers::HString::Set(&string, &Buffer, v16);
    std::wstring::wstring(v20, v19);
    std::wstring::wstring(v21, v22);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<std::wstring,std::wstring>>(
      this + 9,
      v18,
      v20);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v20);
    ++*((_DWORD *)this + 14);
    memset(v23, 0, sizeof(v23));
    if ( swprintf_s(v23, 4u, L"%03u", *((unsigned int *)this + 14)) == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
        v12);
    std::wstring::wstring(v20);
    v13 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(this + 9, v18);
    std::wstring::operator=(*v13 + 64LL, v20);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v22);
  }
  else
  {
    v9 = v8 + 8;
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    *(_QWORD *)v23 = v9;
    Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)&string);
  }
  v14 = WindowsDuplicateString(string, a4);
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
      (const char *)(unsigned int)v14,
      v16);
  std::wstring::_Tidy_deallocate(v19);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18001aad0  push    rbp
0x18001aad2  push    rbx
0x18001aad3  push    rsi
0x18001aad4  push    rdi
0x18001aad5  push    r14
0x18001aad7  push    r15
0x18001aad9  lea     rbp, [rsp-2Fh]
0x18001aade  sub     rsp, 0E8h
0x18001aae5  mov     rax, cs:__security_cookie
0x18001aaec  xor     rax, rsp
0x18001aaef  mov     [rbp+57h+var_40], rax
0x18001aaf3  mov     r14, r9
0x18001aaf6  mov     rsi, rdx
0x18001aaf9  mov     rdi, rcx
0x18001aafc  xor     r15d, r15d
0x18001aaff  mov     rax, [rcx+40h]
0x18001ab03  inc     rax
0x18001ab06  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001ab0c  jnz     short loc_18001AB2E
0x18001ab0e  xor     edx, edx; length
0x18001ab10  mov     rcx, r8; string
0x18001ab13  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ab19  mov     rdx, rax; unsigned __int16 *
0x18001ab1c  lea     rcx, [rdi-28h]; this
0x18001ab20  call    ?LoadRACProfileMap@CoreWebViewRACProfileStatics@WebView@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::WebView::CoreWebViewRACProfileStatics::LoadRACProfileMap(ushort const *)
0x18001ab25  lea     rcx, [rdi-28h]; this
0x18001ab29  call    ?LoadNextID@CoreWebViewRACProfileStatics@WebView@Internal@Windows@@AEAAXXZ; Windows::Internal::WebView::CoreWebViewRACProfileStatics::LoadNextID(void)
0x18001ab2e  mov     [rsp+110h+string], r15
0x18001ab33  xor     edx, edx; length
0x18001ab35  mov     rcx, rsi; string
0x18001ab38  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ab3e  mov     rdx, rax
0x18001ab41  lea     rcx, [rbp+57h+var_D0]
0x18001ab45  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ab4a  nop
0x18001ab4b  lea     rbx, [rdi+48h]
0x18001ab4f  lea     r8, [rbp+57h+var_D0]
0x18001ab53  lea     rdx, [rbp+57h+var_50]
0x18001ab57  mov     rcx, rbx
0x18001ab5a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001ab5f  mov     rax, [rax]
0x18001ab62  cmp     rax, [rbx]
0x18001ab65  jz      short loc_18001AB8C
0x18001ab67  add     rax, 40h ; '@'
0x18001ab6b  cmp     qword ptr [rax+18h], 7
0x18001ab70  jbe     short loc_18001AB75
0x18001ab72  mov     rax, [rax]
0x18001ab75  mov     qword ptr [rbp+57h+var_50], rax
0x18001ab79  lea     rdx, [rbp+57h+var_50]
0x18001ab7d  lea     rcx, [rsp+110h+string]; this
0x18001ab82  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ab87  jmp     loc_18001ACCD
0x18001ab8c  mov     [rbp+57h+Buffer], r15w
0x18001ab91  xor     eax, eax
0x18001ab93  mov     [rbp+57h+var_46], eax
0x18001ab96  mov     [rbp+57h+var_42], ax
0x18001ab9a  mov     rsi, [rbp+5Fh]
0x18001ab9e  mov     r9d, [rdi+38h]
0x18001aba2  lea     r8, a03u; "%03u"
0x18001aba9  lea     edx, [rax+4]; BufferCount
0x18001abac  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001abb0  call    swprintf_s
0x18001abb5  cmp     eax, 0FFFFFFFFh
0x18001abb8  jnz     short loc_18001ABCD
0x18001abba  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001abc1  lea     edx, [rax+41h]; void *
0x18001abc4  mov     rcx, rsi; this
0x18001abc7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001abcd  lea     rdx, [rbp+57h+Buffer]
0x18001abd1  lea     rcx, [rbp+57h+var_70]
0x18001abd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001abda  nop
0x18001abdb  mov     [rsp+110h+var_F0], r15d; int
0x18001abe0  lea     rax, [rbp+57h+Buffer]
0x18001abe4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001abe8  inc     rcx; unsigned __int64
0x18001abeb  cmp     [rax+rcx*2], r15w
0x18001abf0  jnz     short loc_18001ABE8
0x18001abf2  lea     rdx, [rsp+110h+var_F0]; unsigned int *
0x18001abf7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001abfc  test    eax, eax
0x18001abfe  js      short loc_18001AC13
0x18001ac00  mov     r8d, [rsp+110h+var_F0]; unsigned int
0x18001ac05  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x18001ac09  lea     rcx, [rsp+110h+string]; this
0x18001ac0e  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001ac13  lea     rdx, [rbp+57h+var_D0]
0x18001ac17  lea     rcx, [rbp+57h+var_B0]
0x18001ac1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ac20  nop
0x18001ac21  lea     rdx, [rbp+57h+var_70]
0x18001ac25  lea     rcx, [rbp+57h+var_90]
0x18001ac29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ac2e  nop
0x18001ac2f  lea     r8, [rbp+57h+var_B0]
0x18001ac33  lea     rdx, [rsp+110h+var_E0]
0x18001ac38  mov     rcx, rbx
0x18001ac3b  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x18001ac40  nop
0x18001ac41  lea     rcx, [rbp+57h+var_B0]
0x18001ac45  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18001ac4a  inc     dword ptr [rdi+38h]
0x18001ac4d  mov     [rbp+57h+var_50], r15w
0x18001ac52  xor     eax, eax
0x18001ac54  mov     dword ptr [rbp+57h+var_50+2], eax
0x18001ac57  mov     [rbp+57h+var_50+6], ax
0x18001ac5b  mov     rsi, [rbp+5Fh]
0x18001ac5f  mov     r9d, [rdi+38h]
0x18001ac63  lea     r8, a03u; "%03u"
0x18001ac6a  lea     edx, [rax+4]; BufferCount
0x18001ac6d  lea     rcx, [rbp+57h+var_50]; Buffer
0x18001ac71  call    swprintf_s
0x18001ac76  cmp     eax, 0FFFFFFFFh
0x18001ac79  jnz     short loc_18001AC8E
0x18001ac7b  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001ac82  lea     edx, [rax+49h]; void *
0x18001ac85  mov     rcx, rsi; this
0x18001ac88  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001ac8e  lea     rdx, [rbp+57h+var_50]
0x18001ac92  lea     rcx, [rbp+57h+var_B0]
0x18001ac96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ac9b  nop
0x18001ac9c  lea     rdx, [rsp+110h+var_E0]
0x18001aca1  mov     rcx, rbx
0x18001aca4  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18001aca9  mov     rcx, [rax]
0x18001acac  add     rcx, 40h ; '@'
0x18001acb0  lea     rdx, [rbp+57h+var_B0]
0x18001acb4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001acb9  nop
0x18001acba  lea     rcx, [rbp+57h+var_B0]
0x18001acbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001acc3  nop
0x18001acc4  lea     rcx, [rbp+57h+var_70]
0x18001acc8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001accd  mov     rdx, r14; newString
0x18001acd0  mov     rcx, [rsp+110h+string]; string
0x18001acd5  call    cs:__imp_WindowsDuplicateString
0x18001acdb  mov     rcx, [rbp+5Fh]; this
0x18001acdf  test    eax, eax
0x18001ace1  jns     short loc_18001ACF8
0x18001ace3  mov     r9d, eax; char *
0x18001ace6  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001aced  mov     edx, 4Fh ; 'O'; void *
0x18001acf2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001acf8  lea     rcx, [rbp+57h+var_D0]
0x18001acfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ad01  nop
0x18001ad02  mov     rcx, [rsp+110h+string]; string
0x18001ad07  call    cs:__imp_WindowsDeleteString
0x18001ad0d  xor     eax, eax
0x18001ad0f  mov     rcx, [rbp+57h+var_40]
0x18001ad13  xor     rcx, rsp; StackCookie
0x18001ad16  call    __security_check_cookie
0x18001ad1b  add     rsp, 0E8h
0x18001ad22  pop     r15
0x18001ad24  pop     r14
0x18001ad26  pop     rdi
0x18001ad27  pop     rsi
0x18001ad28  pop     rbx
0x18001ad29  pop     rbp
0x18001ad2a  retn
```
