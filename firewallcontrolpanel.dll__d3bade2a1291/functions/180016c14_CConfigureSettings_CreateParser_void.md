# CConfigureSettings::CreateParser(void)

- ea: `0x180016c14`
- end: `0x180016d3b`
- name: `?CreateParser@CConfigureSettings@@AEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(struct DirectUI::DUIXmlParser **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016d44`

## callees

- `0x180009924`
- `0x18000994c`
- `0x180016c14`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180016cf1`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180016cf1`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180016c6d`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180016c6d`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180016ca9`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180016ca9`

## pseudocode

```c
__int64 __fastcall CConfigureSettings::CreateParser(struct DirectUI::DUIXmlParser **this)
{
  int v2; // eax
  unsigned int v3; // ebx
  CFwCplLua *v4; // rcx
  __int64 v5; // rdx

  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8f608efbb88938a26ba5ab864b6663b2_Traceguids);
  v2 = DirectUI::DUIXmlParser::Create(
         this + 6,
         0,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))ParserError_0,
         0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v2 = DirectUI::DUIXmlParser::SetXMLFromResource(this[6], 0xCEu, g_hinst, (HINSTANCE)&_ImageBase);
    v3 = v2;
    if ( v2 >= 0 )
    {
LABEL_15:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 13;
      goto LABEL_12;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 12;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_8f608efbb88938a26ba5ab864b6663b2_Traceguids, (unsigned int)v2);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( this[6] )
  {
    DirectUI::DUIXmlParser::Destroy(this[6]);
    this[6] = 0;
    goto LABEL_15;
  }
LABEL_16:
  if ( v4 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 14, WPP_8f608efbb88938a26ba5ab864b6663b2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180016c14  mov     [rsp+arg_0], rbx
0x180016c19  mov     [rsp+arg_8], rsi
0x180016c1e  push    rdi
0x180016c1f  sub     rsp, 30h
0x180016c23  mov     rdi, rcx
0x180016c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c2d  lea     rsi, WPP_GLOBAL_Control
0x180016c34  cmp     rcx, rsi
0x180016c37  jz      short loc_180016C54
0x180016c39  test    byte ptr [rcx+1Ch], 8
0x180016c3d  jz      short loc_180016C54
0x180016c3f  mov     rcx, [rcx+10h]
0x180016c43  lea     r8, WPP_8f608efbb88938a26ba5ab864b6663b2_Traceguids
0x180016c4a  mov     edx, 0Bh
0x180016c4f  call    WPP_SF_
0x180016c54  lea     r9, ParserError_0
0x180016c5b  mov     [rsp+38h+var_18], 0
0x180016c64  xor     r8d, r8d
0x180016c67  lea     rcx, [rdi+30h]
0x180016c6b  xor     edx, edx
0x180016c6d  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180016c73  mov     ebx, eax
0x180016c75  test    eax, eax
0x180016c77  jns     short loc_180016C92
0x180016c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c80  cmp     rcx, rsi
0x180016c83  jz      short loc_180016CE6
0x180016c85  test    byte ptr [rcx+1Ch], 1
0x180016c89  jz      short loc_180016CE6
0x180016c8b  mov     edx, 0Ch
0x180016c90  jmp     short loc_180016CCC
0x180016c92  mov     r8, cs:g_hinst
0x180016c99  lea     r9, __ImageBase
0x180016ca0  mov     rcx, [rdi+30h]
0x180016ca4  mov     edx, 0CEh
0x180016ca9  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180016caf  mov     ebx, eax
0x180016cb1  test    eax, eax
0x180016cb3  jns     short loc_180016CFF
0x180016cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cbc  cmp     rcx, rsi
0x180016cbf  jz      short loc_180016CE6
0x180016cc1  test    byte ptr [rcx+1Ch], 1
0x180016cc5  jz      short loc_180016CE6
0x180016cc7  mov     edx, 0Dh
0x180016ccc  mov     rcx, [rcx+10h]
0x180016cd0  lea     r8, WPP_8f608efbb88938a26ba5ab864b6663b2_Traceguids
0x180016cd7  mov     r9d, eax
0x180016cda  call    WPP_SF_d
0x180016cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ce6  cmp     qword ptr [rdi+30h], 0
0x180016ceb  jz      short loc_180016D06
0x180016ced  mov     rcx, [rdi+30h]
0x180016cf1  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180016cf7  mov     qword ptr [rdi+30h], 0
0x180016cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d06  cmp     rcx, rsi
0x180016d09  jz      short loc_180016D29
0x180016d0b  test    byte ptr [rcx+1Ch], 8
0x180016d0f  jz      short loc_180016D29
0x180016d11  mov     rcx, [rcx+10h]
0x180016d15  lea     r8, WPP_8f608efbb88938a26ba5ab864b6663b2_Traceguids
0x180016d1c  mov     edx, 0Eh
0x180016d21  mov     r9d, ebx
0x180016d24  call    WPP_SF_d
0x180016d29  mov     rsi, [rsp+38h+arg_8]
0x180016d2e  mov     eax, ebx
0x180016d30  mov     rbx, [rsp+38h+arg_0]
0x180016d35  add     rsp, 30h
0x180016d39  pop     rdi
0x180016d3a  retn
```
