# win_dox::OpcRelationshipSetImplementation::GenerateUniqueRelsID(void)

- ea: `0x1800c3c60`
- end: `0x1800c3dd7`
- name: `?GenerateUniqueRelsID@OpcRelationshipSetImplementation@win_dox@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f57cc`

## callees

- `0x180012468`
- `0x180019410`
- `0x18002db70`
- `0x180075b9c`
- `0x180096fd0`
- `0x1800c3c60`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800f6718`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c3cfa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c3cfa`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c3cdf`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c3cdf`

## string_xrefs

- `0x1800c3d7d`: `Call to ::CoCreateGuid failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationshipSetImplementation::GenerateUniqueRelsID(
        win_dox::OpcRelationshipSetImplementation *this,
        __int64 a2)
{
  HRESULT v4; // edi
  __int64 v5; // r8
  __int64 v6; // r9
  const wchar_t *v7; // rdx
  GUID pguid_8; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR sz; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v12[126]; // [rsp+11Ah] [rbp+12h] BYREF
  wchar_t v13[512]; // [rsp+198h] [rbp+90h] BYREF

  win_dox::OpcRelationshipSetImplementation::Initialize(this, 0);
  *(_QWORD *)(a2 + 32) = 7;
  *(_QWORD *)(a2 + 24) = 0;
  *(_WORD *)(a2 + 8) = 0;
  pguid_8 = 0;
  do
  {
    v4 = CoCreateGuid(&pguid_8);
    if ( v4 < 0 )
    {
      memset_0(v13, 0, sizeof(v13));
      StringCchPrintfW(v13, 0x200u, L"Call to ::CoCreateGuid failed with HResult 0x%X.", (unsigned int)v4);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x119u,
        v4,
        (struct win_musl::TStringEllipseBase *)v13);
      throw (SplException::THResultException *)pExceptionObject;
    }
    StringFromGUID2(&pguid_8, &sz, 64);
    std::wstring::assign(a2, L"R", v5, v6);
    std::wstring::append(a2, v12, 8);
    if ( *(_QWORD *)(a2 + 32) < 8u )
      v7 = (const wchar_t *)(a2 + 8);
    else
      v7 = *(const wchar_t **)(a2 + 8);
  }
  while ( win_dox::OpcRelationshipSetImplementation::RelationshipExists(this, v7) );
  return a2;
}

```

## disassembly

```asm
0x1800c3c60  mov     rax, rsp
0x1800c3c63  push    rbp
0x1800c3c64  push    rdi
0x1800c3c65  push    r14
0x1800c3c67  lea     rbp, [rax-4B8h]
0x1800c3c6e  sub     rsp, 5A0h
0x1800c3c75  mov     [rsp+5B0h+var_568], 0FFFFFFFFFFFFFFFEh
0x1800c3c7e  mov     [rax+18h], rbx
0x1800c3c82  mov     [rax+20h], rsi
0x1800c3c86  mov     rax, cs:__security_cookie
0x1800c3c8d  xor     rax, rsp
0x1800c3c90  mov     [rbp+4B0h+var_20], rax
0x1800c3c97  mov     rbx, rdx
0x1800c3c9a  mov     r14, rcx
0x1800c3c9d  mov     qword ptr [rsp+5B0h+pguid.Data1], rdx
0x1800c3ca2  mov     dword ptr [rsp+5B0h+var_570], 0
0x1800c3caa  xor     edx, edx; bool
0x1800c3cac  call    ?Initialize@OpcRelationshipSetImplementation@win_dox@@AEAAX_N@Z; win_dox::OpcRelationshipSetImplementation::Initialize(bool)
0x1800c3cb1  mov     qword ptr [rbx+20h], 7
0x1800c3cb9  lea     rsi, [rbx+8]
0x1800c3cbd  mov     qword ptr [rbx+18h], 0
0x1800c3cc5  xor     eax, eax
0x1800c3cc7  mov     [rsi], ax
0x1800c3cca  mov     dword ptr [rsp+5B0h+var_570], 1
0x1800c3cd2  xorps   xmm0, xmm0
0x1800c3cd5  movups  xmmword ptr [rsp+5B0h+pguid.Data4], xmm0
0x1800c3cda  lea     rcx, [rsp+5B0h+pguid.Data4]; pguid
0x1800c3cdf  call    cs:__imp_CoCreateGuid
0x1800c3ce5  mov     edi, eax
0x1800c3ce7  test    eax, eax
0x1800c3ce9  js      short loc_1800C3D66
0x1800c3ceb  mov     r8d, 40h ; '@'; cchMax
0x1800c3cf1  lea     rdx, [rbp+4B0h+sz]; lpsz
0x1800c3cf5  lea     rcx, [rsp+5B0h+pguid.Data4]; rguid
0x1800c3cfa  call    cs:__imp_StringFromGUID2
0x1800c3d00  lea     rdx, aR; "R"
0x1800c3d07  mov     rcx, rbx
0x1800c3d0a  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x1800c3d0f  mov     r8d, 8
0x1800c3d15  lea     rdx, [rbp+4B0h+var_49E]
0x1800c3d19  mov     rcx, rbx
0x1800c3d1c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::wstring::append(wchar_t const *,unsigned __int64)
0x1800c3d21  cmp     qword ptr [rbx+20h], 8
0x1800c3d26  jb      short loc_1800C3D2D
0x1800c3d28  mov     rdx, [rsi]
0x1800c3d2b  jmp     short loc_1800C3D30
0x1800c3d2d  mov     rdx, rsi; wchar_t *
0x1800c3d30  mov     rcx, r14; this
0x1800c3d33  call    ?RelationshipExists@OpcRelationshipSetImplementation@win_dox@@QEAA_NPEB_W@Z; win_dox::OpcRelationshipSetImplementation::RelationshipExists(wchar_t const *)
0x1800c3d38  test    al, al
0x1800c3d3a  jnz     short loc_1800C3CDA
0x1800c3d3c  mov     rax, rbx
0x1800c3d3f  mov     rcx, [rbp+4B0h+var_20]
0x1800c3d46  xor     rcx, rsp; StackCookie
0x1800c3d49  call    __security_check_cookie
0x1800c3d4e  lea     r11, [rsp+5B0h+var_10]
0x1800c3d56  mov     rbx, [r11+30h]
0x1800c3d5a  mov     rsi, [r11+38h]
0x1800c3d5e  mov     rsp, r11
0x1800c3d61  pop     r14
0x1800c3d63  pop     rdi
0x1800c3d64  pop     rbp
0x1800c3d65  retn
0x1800c3d66  xor     edx, edx; Val
0x1800c3d68  mov     r8d, 400h; Size
0x1800c3d6e  lea     rcx, [rbp+4B0h+var_420]; void *
0x1800c3d75  call    memset_0
0x1800c3d7a  mov     r9d, edi
0x1800c3d7d  lea     r8, aCallToCocreate_1; "Call to ::CoCreateGuid failed with HRes"...
0x1800c3d84  mov     edx, 200h; unsigned __int64
0x1800c3d89  lea     rcx, [rbp+4B0h+var_420]; wchar_t *
0x1800c3d90  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800c3d95  lea     rax, [rbp+4B0h+var_420]
0x1800c3d9c  mov     [rsp+5B0h+var_580], rax; struct win_musl::TStringEllipseBase *
0x1800c3da1  mov     [rsp+5B0h+var_588], edi; unsigned int
0x1800c3da5  mov     [rsp+5B0h+var_590], 119h; unsigned int
0x1800c3dad  lea     r9, word_180139126
0x1800c3db4  lea     r8, aNoFilename; "(no filename)"
0x1800c3dbb  lea     rcx, [rsp+5B0h+pExceptionObject]; this
0x1800c3dc0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c3dc5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c3dcc  lea     rcx, [rsp+5B0h+pExceptionObject]; pExceptionObject
0x1800c3dd1  call    _CxxThrowException_0
```
