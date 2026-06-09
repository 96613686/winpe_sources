# EventManParser::LocalizationResourcesType(std::map<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::unique_ptr<STRING_ENTRY,std::default_delete<STRING_ENTRY>>,std::less<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>,std::allocator<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,std::unique_ptr<STRING_ENTRY,std::default_delete<STRING_ENTRY>>>>> &,bool,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool)

- ea: `0x1800386fc`
- end: `0x180038896`
- name: `?LocalizationResourcesType@EventManParser@@AEAAXAEAV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@2@@std@@_NV?$basic_string_view@_WU?$char_traits@_W@std@@@3@1@Z`
- size: `410`
- prototype: `__int64 __usercall@<rax>(XmlReader *this@<rcx>, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18003889c`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18001ed1c`
- `0x1800207c0`
- `0x180033df0`
- `0x180035858`
- `0x180037e80`
- `0x1800386fc`
- `0x180038cc4`
- `0x18003b29c`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EventManParser::LocalizationResourcesType(XmlReader *this, _QWORD *a2, char a3, _OWORD *a4, char a5)
{
  char v9; // di
  _QWORD *Value; // rax
  __int64 v11; // r8
  const wchar_t *v13; // [rsp+30h] [rbp-51h] BYREF
  __int64 v14; // [rsp+38h] [rbp-49h]
  __int64 v15[2]; // [rsp+40h] [rbp-41h] BYREF
  __int128 v16; // [rsp+50h] [rbp-31h] BYREF
  __int128 v17; // [rsp+60h] [rbp-21h] BYREF
  _BYTE v18[16]; // [rsp+70h] [rbp-11h] BYREF
  _OWORD v19[2]; // [rsp+80h] [rbp-1h] BYREF

  v19[0] = 0;
  v19[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  v9 = 0;
  if ( !XmlReader::FirstAttribute(this) )
    goto LABEL_6;
  do
  {
    XmlReader::GetQualifiedName(this, &v13);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"culture", 7, v13, v14) )
    {
      Value = XmlReader::GetValue(this, v15);
      std::wstring::_Assign<wchar_t>(v19, *Value);
      v9 = 1;
    }
  }
  while ( XmlReader::NextAttribute(this) );
  if ( !v9 )
LABEL_6:
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"culture");
  if ( XmlReader::FirstChildElement(this) )
  {
    do
    {
      XmlReader::GetLocalName(this, &v17);
      v16 = v17;
      *(_OWORD *)v15 = *a4;
      v13 = L"stringTable";
      v14 = 11;
      if ( EventManParser::ElementMatches(this, &v13, v15, &v16) )
      {
        *(_OWORD *)v15 = *(_OWORD *)std::wstring::operator std::wstring_view(v19, v18);
        v16 = *a4;
        LOBYTE(v11) = a3;
        EventManParser::StringTableType(this, a2, v11, &v16, v15, a5);
      }
    }
    while ( XmlReader::NextChildElement((xp::XmlReader **)this) );
  }
  return std::wstring::_Tidy_deallocate(v19);
}

```

## disassembly

```asm
0x1800386fc  mov     [rsp-8+arg_10], rbx
0x180038701  push    rbp
0x180038702  push    rsi
0x180038703  push    rdi
0x180038704  push    r14
0x180038706  push    r15
0x180038708  lea     rbp, [rsp-2Fh]
0x18003870d  sub     rsp, 0B0h
0x180038714  mov     rax, cs:__security_cookie
0x18003871b  xor     rax, rsp
0x18003871e  mov     [rbp+4Fh+var_30], rax
0x180038722  mov     rsi, r9
0x180038725  mov     r14b, r8b
0x180038728  mov     r15, rdx
0x18003872b  mov     rbx, rcx
0x18003872e  xorps   xmm0, xmm0
0x180038731  movups  [rbp+4Fh+var_50], xmm0
0x180038735  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003873d  movdqu  [rbp+4Fh+var_40], xmm1
0x180038742  xor     eax, eax
0x180038744  mov     word ptr [rbp+4Fh+var_50], ax
0x180038748  xor     dil, dil
0x18003874b  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180038750  test    al, al
0x180038752  jz      short loc_1800387AD
0x180038754  lea     rdx, [rbp+4Fh+var_A0]
0x180038758  mov     rcx, rbx; this
0x18003875b  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180038760  mov     r9, [rbp+4Fh+var_98]
0x180038764  mov     r8, [rbp+4Fh+var_A0]
0x180038768  mov     edx, 7
0x18003876d  lea     rcx, aCulture; "culture"
0x180038774  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180038779  test    al, al
0x18003877b  jz      short loc_18003879C
0x18003877d  lea     rdx, [rbp+4Fh+var_90]
0x180038781  mov     rcx, rbx; this
0x180038784  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038789  mov     r8, [rax+8]
0x18003878d  mov     rdx, [rax]
0x180038790  lea     rcx, [rbp+4Fh+var_50]
0x180038794  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180038799  mov     dil, 1
0x18003879c  mov     rcx, rbx; this
0x18003879f  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x1800387a4  test    al, al
0x1800387a6  jnz     short loc_180038754
0x1800387a8  test    dil, dil
0x1800387ab  jnz     short loc_1800387C1
0x1800387ad  lea     r8, aCulture; "culture"
0x1800387b4  mov     edx, 0C007EF3Eh; int
0x1800387b9  mov     rcx, rbx; this
0x1800387bc  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x1800387c1  mov     rcx, rbx; this
0x1800387c4  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x1800387c9  test    al, al
0x1800387cb  jz      loc_18003886A
0x1800387d1  mov     dil, [rbp+4Fh+arg_20]
0x1800387d5  lea     rdx, [rbp+4Fh+var_70]
0x1800387d9  mov     rcx, rbx; this
0x1800387dc  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x1800387e1  movaps  xmm0, [rbp+4Fh+var_70]
0x1800387e5  movdqa  [rbp+4Fh+var_80], xmm0
0x1800387ea  movaps  xmm1, xmmword ptr [rsi]
0x1800387ed  movdqa  xmmword ptr [rbp+4Fh+var_90], xmm1
0x1800387f2  lea     rax, aStringtable; "stringTable"
0x1800387f9  mov     [rbp+4Fh+var_A0], rax
0x1800387fd  mov     [rbp+4Fh+var_98], 0Bh
0x180038805  lea     r9, [rbp+4Fh+var_80]
0x180038809  lea     r8, [rbp+4Fh+var_90]
0x18003880d  lea     rdx, [rbp+4Fh+var_A0]
0x180038811  mov     rcx, rbx; this
0x180038814  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x180038819  test    al, al
0x18003881b  jz      short loc_18003885A
0x18003881d  lea     rdx, [rbp+4Fh+var_60]
0x180038821  lea     rcx, [rbp+4Fh+var_50]
0x180038825  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18003882a  movups  xmm0, xmmword ptr [rax]
0x18003882d  movdqu  xmmword ptr [rbp+4Fh+var_90], xmm0
0x180038832  movaps  xmm1, xmmword ptr [rsi]
0x180038835  movdqa  [rbp+4Fh+var_80], xmm1
0x18003883a  mov     [rsp+0D0h+var_A8], dil; char
0x18003883f  lea     rax, [rbp+4Fh+var_90]
0x180038843  mov     [rsp+0D0h+var_B0], rax; __int64
0x180038848  lea     r9, [rbp+4Fh+var_80]
0x18003884c  mov     r8b, r14b
0x18003884f  mov     rdx, r15
0x180038852  mov     rcx, rbx; this
0x180038855  call    ?StringTableType@EventManParser@@AEAAXAEAV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@@2@@std@@_NV?$basic_string_view@_WU?$char_traits@_W@std@@@3@21@Z; EventManParser::StringTableType(std::map<std::wstring_view,std::unique_ptr<STRING_ENTRY>> &,bool,std::wstring_view,std::wstring_view,bool)
0x18003885a  mov     rcx, rbx; this
0x18003885d  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x180038862  test    al, al
0x180038864  jnz     loc_1800387D5
0x18003886a  lea     rcx, [rbp+4Fh+var_50]
0x18003886e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038873  mov     rcx, [rbp+4Fh+var_30]
0x180038877  xor     rcx, rsp; StackCookie
0x18003887a  call    __security_check_cookie
0x18003887f  mov     rbx, [rsp+0D0h+arg_10]
0x180038887  add     rsp, 0B0h
0x18003888e  pop     r15
0x180038890  pop     r14
0x180038892  pop     rdi
0x180038893  pop     rsi
0x180038894  pop     rbp
0x180038895  retn
```
