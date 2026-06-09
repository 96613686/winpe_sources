# CDirectUIRender::LoadParser(void)

- ea: `0x1400306e4`
- end: `0x140030886`
- name: `?LoadParser@CDirectUIRender@@AEAAPEAVDUIXmlParser@DirectUI@@XZ`
- size: `418`
- prototype: `struct DirectUI::DUIXmlParser *__fastcall(CDirectUIRender *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400301b8`
- `0x14004fce0`

## callees

- `0x14000c1d0`
- `0x1400306e4`
- `0x1400598b4`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400307a4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140030872`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400307a4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140030872`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400306fa`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400306fa`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140030749`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400307ae`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x14003080a`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x14003082f`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140030749`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400307ae`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x14003080a`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x14003082f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14003073f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140030800`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140030825`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14003073f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140030800`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140030825`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140030799`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140030799`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003070c`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003070c`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x140030733`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x140030733`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1400307f4`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1400307f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct DirectUI::DUIXmlParser *__fastcall CDirectUIRender::LoadParser(HINSTANCE *this)
{
  unsigned int v2; // eax
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  unsigned int v7; // eax
  struct DirectUI::DUIXmlParser *v8; // rbx
  _BYTE v10[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v11[24]; // [rsp+48h] [rbp-18h] BYREF
  struct DirectUI::DUIXmlParser *v12; // [rsp+78h] [rbp+18h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v10, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v10, L"CDirectUIRender::LoadParser");
  v12 = 0;
  v2 = DirectUI::DUIXmlParser::Create(
         &v12,
         0,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))CDirectUIRender::ParserError,
         0);
  mmcerror::SC::operator=(v10, v2);
  v3 = mmcerror::SC::ToHr((mmcerror::SC *)v10);
  if ( v3 >= 0 )
  {
    v6 = ScCheckPointers(v11, v12, 2147549183LL);
    mmcerror::SC::operator=(v10, v6);
    mmcerror::SC::~SC((mmcerror::SC *)v11);
    v3 = mmcerror::SC::ToHr((mmcerror::SC *)v10);
    if ( v3 >= 0 )
    {
      v7 = DirectUI::DUIXmlParser::SetXMLFromResource(v12, 0x1770u, this[3], &_ImageBase);
      mmcerror::SC::operator=(v10, v7);
      if ( (int)mmcerror::SC::ToHr((mmcerror::SC *)v10) < 0 )
      {
        v12 = 0;
        mmcerror::SC::operator=(v10, 2147549183LL);
        v3 = mmcerror::SC::ToHr((mmcerror::SC *)v10);
        if ( v3 < 0 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v5 = 79;
            goto LABEL_14;
          }
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v5 = 78;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v5 = 77;
LABEL_14:
      WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids, (unsigned int)v3);
    }
  }
  v8 = v12;
  mmcerror::SC::~SC((mmcerror::SC *)v10);
  return v8;
}

```

## disassembly

```asm
0x1400306e4  mov     [rsp-8+arg_0], rbx
0x1400306e9  push    rbp
0x1400306ea  mov     rbp, rsp
0x1400306ed  sub     rsp, 60h
0x1400306f1  mov     rbx, rcx
0x1400306f4  xor     edx, edx
0x1400306f6  lea     rcx, [rbp+var_30]
0x1400306fa  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140030700  nop
0x140030701  lea     rdx, aCdirectuirende_1; "CDirectUIRender::LoadParser"
0x140030708  lea     rcx, [rbp+var_30]
0x14003070c  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140030712  mov     [rbp+arg_8], 0
0x14003071a  mov     [rsp+60h+var_40], 0
0x140030723  lea     r9, ?ParserError@CDirectUIRender@@CAXPEBG0HPEAX@Z; CDirectUIRender::ParserError(ushort const *,ushort const *,int,void *)
0x14003072a  xor     r8d, r8d
0x14003072d  xor     edx, edx
0x14003072f  lea     rcx, [rbp+arg_8]
0x140030733  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x140030739  mov     edx, eax
0x14003073b  lea     rcx, [rbp+var_30]
0x14003073f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140030745  lea     rcx, [rbp+var_30]
0x140030749  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x14003074f  test    eax, eax
0x140030751  jns     short loc_14003077E
0x140030753  lea     rdx, WPP_GLOBAL_Control
0x14003075a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030761  cmp     rcx, rdx
0x140030764  jz      loc_14003086A
0x14003076a  cmp     byte ptr [rcx+19h], 2
0x14003076e  jb      loc_14003086A
0x140030774  mov     edx, 4Dh ; 'M'
0x140030779  jmp     loc_140030857
0x14003077e  mov     r8d, 8000FFFFh
0x140030784  mov     rdx, [rbp+arg_8]
0x140030788  lea     rcx, [rbp+var_18]
0x14003078c  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140030791  nop
0x140030792  mov     rdx, rax
0x140030795  lea     rcx, [rbp+var_30]
0x140030799  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14003079f  nop
0x1400307a0  lea     rcx, [rbp+var_18]
0x1400307a4  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400307aa  lea     rcx, [rbp+var_30]
0x1400307ae  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400307b4  test    eax, eax
0x1400307b6  jns     short loc_1400307E0
0x1400307b8  lea     rdx, WPP_GLOBAL_Control
0x1400307bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307c6  cmp     rcx, rdx
0x1400307c9  jz      loc_14003086A
0x1400307cf  cmp     byte ptr [rcx+19h], 2
0x1400307d3  jb      loc_14003086A
0x1400307d9  mov     edx, 4Eh ; 'N'
0x1400307de  jmp     short loc_140030857
0x1400307e0  lea     r9, __ImageBase
0x1400307e7  mov     r8, [rbx+18h]
0x1400307eb  mov     edx, 1770h
0x1400307f0  mov     rcx, [rbp+arg_8]
0x1400307f4  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1400307fa  mov     edx, eax
0x1400307fc  lea     rcx, [rbp+var_30]
0x140030800  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140030806  lea     rcx, [rbp+var_30]
0x14003080a  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140030810  test    eax, eax
0x140030812  jns     short loc_14003086A
0x140030814  mov     [rbp+arg_8], 0
0x14003081c  mov     edx, 8000FFFFh
0x140030821  lea     rcx, [rbp+var_30]
0x140030825  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14003082b  lea     rcx, [rbp+var_30]
0x14003082f  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140030835  test    eax, eax
0x140030837  jns     short loc_14003086A
0x140030839  lea     rdx, WPP_GLOBAL_Control
0x140030840  mov     rcx, cs:WPP_GLOBAL_Control
0x140030847  cmp     rcx, rdx
0x14003084a  jz      short loc_14003086A
0x14003084c  cmp     byte ptr [rcx+19h], 2
0x140030850  jb      short loc_14003086A
0x140030852  mov     edx, 4Fh ; 'O'
0x140030857  mov     r9d, eax
0x14003085a  lea     r8, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids
0x140030861  mov     rcx, [rcx+10h]
0x140030865  call    WPP_SF_d
0x14003086a  mov     rbx, [rbp+arg_8]
0x14003086e  lea     rcx, [rbp+var_30]
0x140030872  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140030878  mov     rax, rbx
0x14003087b  mov     rbx, [rsp+60h+arg_0]
0x140030880  add     rsp, 60h
0x140030884  pop     rbp
0x140030885  retn
```
