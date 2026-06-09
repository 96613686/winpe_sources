# EventManParser::PatternMapValueType(void)

- ea: `0x180039a80`
- end: `0x180039b8f`
- name: `?PatternMapValueType@EventManParser@@AEAA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@std@@XZ`
- size: `271`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180039878`

## callees

- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x180031310`
- `0x180037670`
- `0x180039a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EventManParser::PatternMapValueType(XmlReader *this, __int64 a2)
{
  char v4; // si
  bool i; // al
  char AttributeId; // al
  _QWORD *v7; // rax
  _QWORD *Value; // rax
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+60h] [rbp-18h] BYREF
  int v14; // [rsp+90h] [rbp+18h] BYREF

  v14 = 4;
  std::make_unique<MAP_ENTRY,enum _MAP_FLAGS,0>(a2, &v14);
  v4 = 0;
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v10 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v11);
    AttributeId = GetAttributeId(&v10);
    if ( AttributeId == 25 )
    {
      Value = XmlReader::GetValue(this, &v13);
      std::wstring::_Assign<wchar_t>(*(_QWORD *)a2 + 104LL, *Value);
    }
    else if ( AttributeId == 40 )
    {
      v7 = XmlReader::GetValue(this, &v12);
      std::wstring::_Assign<wchar_t>(*(_QWORD *)a2 + 72LL, *v7);
      v4 = 1;
    }
  }
  if ( !*(_QWORD *)(*(_QWORD *)a2 + 120LL) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  if ( !v4 )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"value");
  return a2;
}

```

## disassembly

```asm
0x180039a80  mov     rax, rsp
0x180039a83  mov     [rax+8], rbx
0x180039a87  mov     [rax+20h], rsi
0x180039a8b  mov     [rax+10h], rdx
0x180039a8f  push    rdi
0x180039a90  sub     rsp, 70h
0x180039a94  mov     rdi, rdx
0x180039a97  mov     rbx, rcx
0x180039a9a  mov     dword ptr [rax-58h], 0
0x180039aa1  mov     dword ptr [rax+18h], 4
0x180039aa8  lea     rdx, [rax+18h]
0x180039aac  mov     rcx, rdi
0x180039aaf  call    ??$make_unique@VMAP_ENTRY@@W4_MAP_FLAGS@@$0A@@std@@YA?AV?$unique_ptr@VMAP_ENTRY@@U?$default_delete@VMAP_ENTRY@@@std@@@0@$$QEAW4_MAP_FLAGS@@@Z; std::make_unique<MAP_ENTRY,_MAP_FLAGS,0>(_MAP_FLAGS &&)
0x180039ab4  mov     [rsp+78h+var_58], 1
0x180039abc  xor     sil, sil
0x180039abf  mov     rcx, rbx; this
0x180039ac2  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180039ac7  jmp     short loc_180039B3E
0x180039ac9  lea     rdx, [rsp+78h+var_38]
0x180039ace  mov     rcx, rbx; this
0x180039ad1  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x180039ad6  movups  xmm0, xmmword ptr [rax]
0x180039ad9  movdqu  [rsp+78h+var_48], xmm0
0x180039adf  lea     rcx, [rsp+78h+var_48]
0x180039ae4  call    GetAttributeId
0x180039ae9  cmp     al, 19h
0x180039aeb  jz      short loc_180039B16
0x180039aed  cmp     al, 28h ; '('
0x180039aef  jnz     short loc_180039B36
0x180039af1  lea     rdx, [rsp+78h+var_28]
0x180039af6  mov     rcx, rbx; this
0x180039af9  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039afe  mov     rcx, [rdi]
0x180039b01  add     rcx, 48h ; 'H'
0x180039b05  mov     r8, [rax+8]
0x180039b09  mov     rdx, [rax]
0x180039b0c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180039b11  mov     sil, 1
0x180039b14  jmp     short loc_180039B36
0x180039b16  lea     rdx, [rsp+78h+var_18]
0x180039b1b  mov     rcx, rbx; this
0x180039b1e  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180039b23  mov     rcx, [rdi]
0x180039b26  add     rcx, 68h ; 'h'
0x180039b2a  mov     r8, [rax+8]
0x180039b2e  mov     rdx, [rax]
0x180039b31  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180039b36  mov     rcx, rbx; this
0x180039b39  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x180039b3e  test    al, al
0x180039b40  jnz     short loc_180039AC9
0x180039b42  mov     rax, [rdi]
0x180039b45  cmp     qword ptr [rax+78h], 0
0x180039b4a  jnz     short loc_180039B60
0x180039b4c  lea     r8, aName_0; "name"
0x180039b53  mov     edx, 0C007EF3Eh; int
0x180039b58  mov     rcx, rbx; this
0x180039b5b  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180039b60  test    sil, sil
0x180039b63  jnz     short loc_180039B79
0x180039b65  lea     r8, aValue; "value"
0x180039b6c  mov     edx, 0C007EF3Eh; int
0x180039b71  mov     rcx, rbx; this
0x180039b74  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x180039b79  mov     rax, rdi
0x180039b7c  lea     r11, [rsp+78h+var_8]
0x180039b81  mov     rbx, [r11+10h]
0x180039b85  mov     rsi, [r11+28h]
0x180039b89  mov     rsp, r11
0x180039b8c  pop     rdi
0x180039b8d  retn
```
