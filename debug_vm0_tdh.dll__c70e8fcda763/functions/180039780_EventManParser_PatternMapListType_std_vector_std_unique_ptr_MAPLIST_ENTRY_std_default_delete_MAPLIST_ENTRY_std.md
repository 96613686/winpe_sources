# EventManParser::PatternMapListType(std::vector<std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>,std::allocator<std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>>> &)

- ea: `0x180039780`
- end: `0x180039871`
- name: `?PatternMapListType@EventManParser@@AEAAXAEAV?$vector@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@2@@std@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180038c30`

## callees

- `0x18001cb90`
- `0x18001df64`
- `0x18002e7b0`
- `0x180032c7c`
- `0x180035858`
- `0x180037e80`
- `0x180038cc4`
- `0x180039780`
- `0x180039878`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EventManParser::PatternMapListType(XmlReader *this, __int64 *a2)
{
  char i; // al
  __int64 *v5; // rax
  __int64 *v6; // rdx
  __int64 v7; // rcx
  _QWORD v8[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF
  __int128 v11; // [rsp+50h] [rbp-18h] BYREF
  MAPLIST_ENTRY *v12; // [rsp+78h] [rbp+10h] BYREF

  for ( i = XmlReader::FirstChildElement(this); i; i = XmlReader::NextChildElement((xp::XmlReader **)this) )
  {
    XmlReader::GetLocalName(this, &v9);
    v10 = v9;
    v11 = *(_OWORD *)&off_18004F7F0;
    v8[0] = L"patternMap";
    v8[1] = 10;
    if ( EventManParser::ElementMatches(this, v8, &v11, &v10) )
    {
      v5 = EventManParser::PatternMapType(this, (__int64 *)&v12);
      v6 = (__int64 *)a2[1];
      if ( v6 == (__int64 *)a2[2] )
      {
        std::vector<std::unique_ptr<MAPLIST_ENTRY>>::_Emplace_reallocate<std::unique_ptr<MAPLIST_ENTRY>>(
          a2,
          (__int64)v6,
          v5);
      }
      else
      {
        v7 = *v5;
        *v5 = 0;
        *v6 = v7;
        a2[1] += 8;
      }
      std::unique_ptr<MAPLIST_ENTRY>::~unique_ptr<MAPLIST_ENTRY>(&v12);
    }
  }
  if ( *a2 == a2[1] )
    EventManParser::ErrorWithFormatMessage(this, -1073221829, L"patternMap");
}

```

## disassembly

```asm
0x180039780  mov     [rsp+arg_0], rbx
0x180039785  mov     [rsp+arg_10], rsi
0x18003978a  push    rdi
0x18003978b  sub     rsp, 60h
0x18003978f  mov     rbx, rdx
0x180039792  mov     rdi, rcx
0x180039795  call    ?FirstChildElement@XmlReader@@QEAA_NXZ; XmlReader::FirstChildElement(void)
0x18003979a  lea     rsi, aPatternmap; "patternMap"
0x1800397a1  jmp     loc_18003983E
0x1800397a6  lea     rdx, [rsp+68h+var_38]
0x1800397ab  mov     rcx, rdi; this
0x1800397ae  call    ?GetLocalName@XmlReader@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; XmlReader::GetLocalName(void)
0x1800397b3  movups  xmm0, [rsp+68h+var_38]
0x1800397b8  movups  xmm1, xmmword ptr cs:off_18004F7F0; "http://schemas.microsoft.com/win/2004/0"...
0x1800397bf  movdqu  [rsp+68h+var_28], xmm0
0x1800397c5  movdqu  [rsp+68h+var_18], xmm1
0x1800397cb  mov     [rsp+68h+var_48], rsi
0x1800397d0  mov     [rsp+68h+var_40], 0Ah
0x1800397d9  lea     r9, [rsp+68h+var_28]
0x1800397de  lea     r8, [rsp+68h+var_18]
0x1800397e3  lea     rdx, [rsp+68h+var_48]
0x1800397e8  mov     rcx, rdi; this
0x1800397eb  call    ?ElementMatches@EventManParser@@AEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; EventManParser::ElementMatches(std::wstring_view,std::wstring_view,std::wstring_view)
0x1800397f0  test    al, al
0x1800397f2  jz      short loc_180039836
0x1800397f4  lea     rdx, [rsp+68h+arg_8]
0x1800397f9  mov     rcx, rdi; this
0x1800397fc  call    ?PatternMapType@EventManParser@@AEAA?AV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@XZ; EventManParser::PatternMapType(void)
0x180039801  nop
0x180039802  mov     rdx, [rbx+8]
0x180039806  cmp     rdx, [rbx+10h]
0x18003980a  jz      short loc_180039820
0x18003980c  mov     rcx, [rax]
0x18003980f  mov     qword ptr [rax], 0
0x180039816  mov     [rdx], rcx
0x180039819  add     qword ptr [rbx+8], 8
0x18003981e  jmp     short loc_18003982C
0x180039820  mov     r8, rax
0x180039823  mov     rcx, rbx
0x180039826  call    ??$_Emplace_reallocate@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<MAPLIST_ENTRY>>::_Emplace_reallocate<std::unique_ptr<MAPLIST_ENTRY>>(std::unique_ptr<MAPLIST_ENTRY> * const,std::unique_ptr<MAPLIST_ENTRY> &&)
0x18003982b  nop
0x18003982c  lea     rcx, [rsp+68h+arg_8]
0x180039831  call    ??1?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<MAPLIST_ENTRY>::~unique_ptr<MAPLIST_ENTRY>(void)
0x180039836  mov     rcx, rdi; this
0x180039839  call    ?NextChildElement@XmlReader@@QEAA_NXZ; XmlReader::NextChildElement(void)
0x18003983e  test    al, al
0x180039840  jnz     loc_1800397A6
0x180039846  mov     rax, [rbx+8]
0x18003984a  cmp     [rbx], rax
0x18003984d  jnz     short loc_18003985F
0x18003984f  mov     r8, rsi
0x180039852  mov     edx, 0C007EF3Bh; int
0x180039857  mov     rcx, rdi; this
0x18003985a  call    ?ErrorWithFormatMessage@EventManParser@@AEAAXJZZ; EventManParser::ErrorWithFormatMessage(long,...)
0x18003985f  lea     r11, [rsp+68h+var_8]
0x180039864  mov     rbx, [r11+10h]
0x180039868  mov     rsi, [r11+20h]
0x18003986c  mov     rsp, r11
0x18003986f  pop     rdi
0x180039870  retn
```
