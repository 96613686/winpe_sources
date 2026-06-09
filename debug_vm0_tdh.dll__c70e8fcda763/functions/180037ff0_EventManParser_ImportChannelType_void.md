# EventManParser::ImportChannelType(void)

- ea: `0x180037ff0`
- end: `0x1800380e5`
- name: `?ImportChannelType@EventManParser@@AEAA?AV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@XZ`
- size: `245`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180034cbc`

## callees

- `0x18001df64`
- `0x18001e284`
- `0x18001e4d8`
- `0x18001e550`
- `0x18001e8f0`
- `0x18001e930`
- `0x18003110c`
- `0x180037670`
- `0x180037ff0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EventManParser::ImportChannelType(XmlReader *this, __int64 *a2)
{
  bool i; // al
  char AttributeId; // al
  _QWORD *Value; // rax
  __int64 v7; // rcx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  __int64 v10; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h] BYREF
  __int64 v12; // [rsp+60h] [rbp-28h] BYREF
  __int64 v13[3]; // [rsp+70h] [rbp-18h] BYREF
  char v14; // [rsp+A0h] [rbp+18h] BYREF

  v14 = 1;
  std::make_unique<CHANNEL_ENTRY,bool,0>(a2, &v14);
  for ( i = XmlReader::FirstAttribute(this); i; i = XmlReader::NextAttribute(this) )
  {
    v9 = *(_OWORD *)XmlReader::GetQualifiedName(this, &v10);
    AttributeId = GetAttributeId(&v9);
    switch ( AttributeId )
    {
      case 3:
        Value = XmlReader::GetValue(this, v13);
        v7 = *a2 + 64;
        break;
      case 25:
        Value = XmlReader::GetValue(this, &v12);
        v7 = *a2;
        break;
      case 34:
        Value = XmlReader::GetValue(this, &v11);
        v7 = *a2 + 32;
        break;
      default:
        continue;
    }
    std::wstring::_Assign<wchar_t>(v7, *Value);
  }
  if ( !*(_QWORD *)(*a2 + 16) )
    EventManParser::ErrorWithFormatMessage(this, -1073221826, L"name");
  return a2;
}

```

## disassembly

```asm
0x180037ff0  mov     rax, rsp
0x180037ff3  mov     [rax+8], rbx
0x180037ff7  mov     [rax+10h], rdx
0x180037ffb  push    rdi
0x180037ffc  sub     rsp, 80h
0x180038003  mov     rbx, rdx
0x180038006  mov     rdi, rcx
0x180038009  mov     dword ptr [rax-68h], 0
0x180038010  mov     byte ptr [rax+18h], 1
0x180038014  lea     rdx, [rax+18h]
0x180038018  mov     rcx, rbx
0x18003801b  call    ??$make_unique@VCHANNEL_ENTRY@@_N$0A@@std@@YA?AV?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@0@$$QEA_N@Z; std::make_unique<CHANNEL_ENTRY,bool,0>(bool &&)
0x180038020  mov     [rsp+88h+var_68], 1
0x180038028  mov     rcx, rdi; this
0x18003802b  call    ?FirstAttribute@XmlReader@@QEAA_NXZ; XmlReader::FirstAttribute(void)
0x180038030  jmp     short loc_1800380AE
0x180038032  lea     rdx, [rsp+88h+var_48]
0x180038037  mov     rcx, rdi; this
0x18003803a  call    ?GetQualifiedName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetQualifiedName(void)
0x18003803f  movups  xmm0, xmmword ptr [rax]
0x180038042  movdqu  [rsp+88h+var_58], xmm0
0x180038048  lea     rcx, [rsp+88h+var_58]
0x18003804d  call    GetAttributeId
0x180038052  cmp     al, 3
0x180038054  jz      short loc_180038086
0x180038056  cmp     al, 19h
0x180038058  jz      short loc_180038074
0x18003805a  cmp     al, 22h ; '"'
0x18003805c  jnz     short loc_1800380A6
0x18003805e  lea     rdx, [rsp+88h+var_38]
0x180038063  mov     rcx, rdi; this
0x180038066  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x18003806b  mov     rcx, [rbx]
0x18003806e  add     rcx, 20h ; ' '
0x180038072  jmp     short loc_18003809A
0x180038074  lea     rdx, [rsp+88h+var_28]
0x180038079  mov     rcx, rdi; this
0x18003807c  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038081  mov     rcx, [rbx]
0x180038084  jmp     short loc_18003809A
0x180038086  lea     rdx, [rsp+88h+var_18]
0x18003808b  mov     rcx, rdi; this
0x18003808e  call    ?GetValue@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetValue(void)
0x180038093  mov     rcx, [rbx]
0x180038096  add     rcx, 40h ; '@'
0x18003809a  mov     r8, [rax+8]
0x18003809e  mov     rdx, [rax]
0x1800380a1  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800380a6  mov     rcx, rdi; this
0x1800380a9  call    ?NextAttribute@XmlReader@@QEAA_NXZ; XmlReader::NextAttribute(void)
0x1800380ae  test    al, al
0x1800380b0  jnz     short loc_180038032
0x1800380b2  mov     rax, [rbx]
0x1800380b5  cmp     qword ptr [rax+10h], 0
0x1800380ba  jnz     short loc_1800380D0
0x1800380bc  lea     r8, aName_0; "name"
0x1800380c3  mov     edx, 0C007EF3Eh; int
0x1800380c8  mov     rcx, rdi; this
0x1800380cb  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x1800380d0  mov     rax, rbx
0x1800380d3  mov     rbx, [rsp+88h+arg_0]
0x1800380db  add     rsp, 80h
0x1800380e2  pop     rdi
0x1800380e3  retn
```
