# EventManParser::BitMapValueType(void)

- ea: `0x180034974`
- end: `0x180034b22`
- name: `?BitMapValueType@EventManParser@@AEAA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@XZ`
- size: `430`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x18003479c`

## callees

- `0x18001df64`
- `0x18001e0cc`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x1800207c0`
- `0x180031310`
- `0x180033da0`
- `0x180034974`
- `0x1800358f4`
- `0x180037670`
- `0x1800396e0`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall EventManParser::BitMapValueType(XmlReader *this, _QWORD *a2)
{
  char v4; // bl
  char AttributeId; // al
  const wchar_t **v6; // rax
  const wchar_t *v7; // r14
  const wchar_t *v8; // rax
  __int64 v9; // rbx
  _QWORD *Value; // rax
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-59h] BYREF
  int v14; // [rsp+24h] [rbp-55h]
  __int128 v15; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v16[3]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v17; // [rsp+58h] [rbp-21h] BYREF
  __int64 v18; // [rsp+68h] [rbp-11h] BYREF
  __int64 v19; // [rsp+78h] [rbp-1h] BYREF
  __int64 v20; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v21[32]; // [rsp+98h] [rbp+1Fh] BYREF

  v16[2] = a2;
  v14 = 0;
  v13 = 2;
  std::make_unique<MAP_ENTRY,enum _MAP_FLAGS,0>(a2, &v13);
  v14 = 1;
  v4 = 0;
  if ( !XmlReader::FirstAttribute(this) )
    goto LABEL_12;
  do
  {
    v15 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v17);
    AttributeId = GetAttributeId(&v15);
    switch ( AttributeId )
    {
      case 22:
        v15 = *(_OWORD *)XmlReader::GetValue(this, &v20);
        v11 = EventManParser::ParseStrTableRef(this, v21, &v15);
        std::wstring::operator=(*a2 + 32LL, v11);
        std::wstring::_Tidy_deallocate(v21);
        break;
      case 34:
        Value = XmlReader::GetValue(this, &v19);
        std::wstring::_Assign<wchar_t>(*a2, *Value);
        break;
      case 40:
        v6 = (const wchar_t **)XmlReader::GetValue(this, &v18);
        v7 = *v6;
        v8 = v6[1];
        v16[0] = v7;
        v16[1] = v8;
        v9 = EventManParser::ParseUlong(v16, 16);
        if ( !BYTE4(v9) )
          EventManParser::ErrorWithPrintf(this, -2147024809, "Invalid value \"%ls\", expected HexInt32.", v7);
        *(_DWORD *)(*a2 + 64LL) = v9;
        v4 = 1;
        break;
    }
  }
  while ( XmlReader::NextAttribute(this) );
  if ( !v4 )
LABEL_12:
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"value");
  if ( !*(_QWORD *)(*a2 + 48LL) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"message");
  return a2;
}

```

## disassembly

```asm
0x180034974  mov     [rsp-8+arg_10], rbx
0x180034979  mov     [rsp-8+arg_18], rsi
0x18003497e  push    rbp
0x18003497f  push    rdi
0x180034980  push    r14
0x180034982  lea     rbp, [rsp-47h]
0x180034987  sub     rsp, 0C0h
0x18003498e  mov     rax, cs:__security_cookie
0x180034995  xor     rax, rsp
0x180034998  mov     [rbp+57h+var_18], rax
0x18003499c  mov     rsi, rdx
0x18003499f  mov     rdi, rcx
0x1800349a2  mov     [rbp+57h+var_80], rdx
0x1800349a6  mov     [rbp+57h+var_AC], 0
0x1800349ad  mov     [rbp+57h+var_B0], 2
0x1800349b4  lea     rdx, [rbp+57h+var_B0]
0x1800349b8  mov     rcx, rsi
0x1800349bb  call    ??$make_unique@VMAP_ENTRY@@W4_MAP_FLAGS@@$0A@@std@@YA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@0@$$QEAW4_MAP_FLAGS@@@Z; std::make_unique<MAP_ENTRY,_MAP_FLAGS,0>(_MAP_FLAGS &&)
0x1800349c0  mov     [rbp+57h+var_AC], 1
0x1800349c7  xor     bl, bl
0x1800349c9  mov     rcx, rdi; this
0x1800349cc  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x1800349d1  test    al, al
0x1800349d3  jz      loc_180034AC8
0x1800349d9  lea     rdx, [rbp+57h+var_78]
0x1800349dd  mov     rcx, rdi; this
0x1800349e0  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x1800349e5  movups  xmm0, xmmword ptr [rax]
0x1800349e8  movdqu  [rbp+57h+var_A0], xmm0
0x1800349ed  lea     rcx, [rbp+57h+var_A0]
0x1800349f1  call    GetAttributeId
0x1800349f6  cmp     al, 16h
0x1800349f8  jz      short loc_180034A78
0x1800349fa  cmp     al, 22h ; '"'
0x1800349fc  jz      short loc_180034A5B
0x1800349fe  cmp     al, 28h ; '('
0x180034a00  jnz     loc_180034AB4
0x180034a06  lea     rdx, [rbp+57h+var_68]
0x180034a0a  mov     rcx, rdi; this
0x180034a0d  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180034a12  mov     r14, [rax]
0x180034a15  mov     rax, [rax+8]
0x180034a19  mov     [rbp+57h+var_90], r14
0x180034a1d  mov     [rbp+57h+var_88], rax
0x180034a21  mov     edx, 10h
0x180034a26  lea     rcx, [rbp+57h+var_90]
0x180034a2a  call    ?ParseUlong@EventManParser@@CA?AUParseUlongResult@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@H@Z; EventManParser::ParseUlong(std::wstring_view,int)
0x180034a2f  mov     rbx, rax
0x180034a32  shr     rax, 20h
0x180034a36  test    al, al
0x180034a38  jnz     short loc_180034A51
0x180034a3a  mov     r9, r14
0x180034a3d  lea     r8, aInvalidValueLs_4; "Invalid value \"%ls\", expected HexInt3"...
0x180034a44  mov     edx, 80070057h; int
0x180034a49  mov     rcx, rdi; this
0x180034a4c  call    ?ErrorWithPrintf@EventManParser@@AEAAXJPEBDZZ; EventManParser::ErrorWithPrintf(long,char const *,...)
0x180034a51  mov     rax, [rsi]
0x180034a54  mov     [rax+40h], ebx
0x180034a57  mov     bl, 1
0x180034a59  jmp     short loc_180034AB4
0x180034a5b  lea     rdx, [rbp+57h+var_58]
0x180034a5f  mov     rcx, rdi; this
0x180034a62  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180034a67  mov     r8, [rax+8]
0x180034a6b  mov     rdx, [rax]
0x180034a6e  mov     rcx, [rsi]
0x180034a71  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180034a76  jmp     short loc_180034AB4
0x180034a78  lea     rdx, [rbp+57h+var_48]
0x180034a7c  mov     rcx, rdi; this
0x180034a7f  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180034a84  movups  xmm0, xmmword ptr [rax]
0x180034a87  movdqu  [rbp+57h+var_A0], xmm0
0x180034a8c  lea     r8, [rbp+57h+var_A0]
0x180034a90  lea     rdx, [rbp+57h+var_38]
0x180034a94  mov     rcx, rdi
0x180034a97  call    ?ParseStrTableRef@EventManParser@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; EventManParser::ParseStrTableRef(std::wstring_view)
0x180034a9c  mov     rcx, [rsi]
0x180034a9f  add     rcx, 20h ; ' '
0x180034aa3  mov     rdx, rax
0x180034aa6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034aab  lea     rcx, [rbp+57h+var_38]
0x180034aaf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034ab4  mov     rcx, rdi; this
0x180034ab7  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180034abc  test    al, al
0x180034abe  jnz     loc_1800349D9
0x180034ac4  test    bl, bl
0x180034ac6  jnz     short loc_180034ADC
0x180034ac8  lea     r8, aValue; "value"
0x180034acf  mov     edx, 0C007EF3Eh; int
0x180034ad4  mov     rcx, rdi; this
0x180034ad7  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180034adc  mov     r8, [rsi]
0x180034adf  cmp     qword ptr [r8+30h], 0
0x180034ae4  jnz     short loc_180034AFA
0x180034ae6  lea     r8, aMessage; "message"
0x180034aed  mov     edx, 0C007EF3Eh; int
0x180034af2  mov     rcx, rdi; this
0x180034af5  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180034afa  mov     rax, rsi
0x180034afd  mov     rcx, [rbp+57h+var_18]
0x180034b01  xor     rcx, rsp; StackCookie
0x180034b04  call    __security_check_cookie
0x180034b09  lea     r11, [rsp+0D0h+var_10]
0x180034b11  mov     rbx, [r11+30h]
0x180034b15  mov     rsi, [r11+38h]
0x180034b19  mov     rsp, r11
0x180034b1c  pop     r14
0x180034b1e  pop     rdi
0x180034b1f  pop     rbp
0x180034b20  retn
```
