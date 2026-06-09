# CDirectUIRender::AddSectionDescription(DirectUI::Element *,ushort const *)

- ea: `0x1400e8994`
- end: `0x1400e8c61`
- name: `?AddSectionDescription@CDirectUIRender@@QEAAPEAVElement@DirectUI@@PEAV23@PEBG@Z`
- size: `717`
- prototype: `struct DirectUI::Element *__fastcall(CDirectUIRender *this, struct DirectUI::Element *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140003840`

## callees

- `0x140005040`
- `0x140005714`
- `0x14002c9c0`
- `0x1400598b4`
- `0x1400e8994`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400e8a2d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400e8c48`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400e8a2d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400e8c48`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400e89b8`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400e89b8`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8a37`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8ab8`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8b62`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8bc4`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8c11`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8a37`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8ab8`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8b62`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8bc4`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400e8c11`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e89f4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8aae`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8b58`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8bba`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8c07`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e89f4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8aae`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8b58`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8bba`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e8c07`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400e8a22`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400e8a22`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400e89ca`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400e89ca`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1400e8aa2`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1400e8aa2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1400e89dd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1400e8b01`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1400e89dd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1400e8b01`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400e8b13`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400e8b13`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1400e8bfb`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1400e8bfb`

## pseudocode

```c
struct DirectUI::Element *__fastcall CDirectUIRender::AddSectionDescription(
        CDirectUIRender *this,
        struct DirectUI::Element *a2,
        const unsigned __int16 *a3)
{
  struct DirectUI::Element *v6; // rdi
  struct DirectUI::Element *Descendent; // r14
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  int v14; // eax
  struct DirectUI::Element *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // eax
  int v19; // eax
  CDirectUIRender *v20; // rcx
  unsigned int Accessible; // eax
  int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  _BYTE v26[24]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v27[72]; // [rsp+68h] [rbp+Fh] BYREF
  struct DirectUI::Element *v28; // [rsp+C0h] [rbp+67h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v26, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v26, L"CDirectUIRender::AddSectionDescription");
  v6 = 0;
  v28 = 0;
  Descendent = DirectUI::Element::FindDescendent(a2, *((_WORD *)this + 44));
  if ( !Descendent )
    goto LABEL_2;
  v8 = ScCheckPointers(v27, a2, *((_QWORD *)this + 5), a3, -2147024809);
  mmcerror::SC::operator=(v26, v8);
  mmcerror::SC::~SC((mmcerror::SC *)v27);
  v9 = mmcerror::SC::ToHr((mmcerror::SC *)v26);
  v10 = (unsigned int)v9;
  if ( v9 >= 0 )
  {
    v13 = DirectUI::DUIXmlParser::CreateElement(
            *((DirectUI::DUIXmlParser **)this + 5),
            L"descsection",
            0,
            Descendent,
            0,
            &v28);
    mmcerror::SC::operator=(v26, v13);
    v14 = mmcerror::SC::ToHr((mmcerror::SC *)v26);
    v10 = (unsigned int)v14;
    if ( v14 >= 0 )
    {
      if ( !v28 || (v15 = DirectUI::Element::FindDescendent(v28, *((_WORD *)this + 46))) == 0 )
      {
LABEL_2:
        mmcerror::SC::operator=(v26, 2147549183LL);
        goto LABEL_27;
      }
      v16 = DirectUI::Element::ContentProp();
      v18 = CDirectUIRender::SetLocalValue(v17, 2, v16, v15, 0, 0, a3, 0, 0);
      mmcerror::SC::operator=(v26, v18);
      v19 = mmcerror::SC::ToHr((mmcerror::SC *)v26);
      v10 = (unsigned int)v19;
      if ( v19 >= 0 )
      {
        Accessible = CDirectUIRender::MakeAccessible(v20, v15, 41, a3, 0);
        mmcerror::SC::operator=(v26, Accessible);
        v22 = mmcerror::SC::ToHr((mmcerror::SC *)v26);
        v10 = (unsigned int)v22;
        if ( v22 >= 0 )
        {
          v23 = DirectUI::Element::Add(Descendent, v28);
          mmcerror::SC::operator=(v26, v23);
          v24 = mmcerror::SC::ToHr((mmcerror::SC *)v26);
          v10 = (unsigned int)v24;
          if ( v24 >= 0 )
          {
            v6 = v15;
            goto LABEL_27;
          }
          v11 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v12 = 46;
            goto LABEL_7;
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v12 = 45;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v12 = 44;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v12 = 43;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v12 = 42;
LABEL_7:
      WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids, v10);
    }
  }
LABEL_27:
  mmcerror::SC::~SC((mmcerror::SC *)v26);
  return v6;
}

```

## disassembly

```asm
0x1400e8994  push    rbp
0x1400e8996  push    rbx
0x1400e8997  push    rsi
0x1400e8998  push    rdi
0x1400e8999  push    r14
0x1400e899b  push    r15
0x1400e899d  lea     rbp, [rsp-2Fh]
0x1400e89a2  sub     rsp, 88h
0x1400e89a9  mov     rsi, r8
0x1400e89ac  mov     r15, rdx
0x1400e89af  mov     rbx, rcx
0x1400e89b2  xor     edx, edx
0x1400e89b4  lea     rcx, [rbp+57h+var_60]
0x1400e89b8  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400e89be  nop
0x1400e89bf  lea     rdx, aCdirectuirende_2; "CDirectUIRender::AddSectionDescription"
0x1400e89c6  lea     rcx, [rbp+57h+var_60]
0x1400e89ca  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400e89d0  xor     edi, edi
0x1400e89d2  mov     [rbp+57h+arg_0], rdi
0x1400e89d6  movzx   edx, word ptr [rbx+58h]
0x1400e89da  mov     rcx, r15
0x1400e89dd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1400e89e3  mov     r14, rax
0x1400e89e6  test    rax, rax
0x1400e89e9  jnz     short loc_1400E89FF
0x1400e89eb  mov     edx, 8000FFFFh
0x1400e89f0  lea     rcx, [rbp+57h+var_60]
0x1400e89f4  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e89fa  jmp     loc_1400E8C44
0x1400e89ff  mov     dword ptr [rsp+0B0h+var_90], 80070057h
0x1400e8a07  mov     r9, rsi
0x1400e8a0a  mov     r8, [rbx+28h]
0x1400e8a0e  mov     rdx, r15
0x1400e8a11  lea     rcx, [rbp+57h+var_48]
0x1400e8a15  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBX00J@Z; ScCheckPointers(void const *,void const *,void const *,long)
0x1400e8a1a  nop
0x1400e8a1b  mov     rdx, rax
0x1400e8a1e  lea     rcx, [rbp+57h+var_60]
0x1400e8a22  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400e8a28  nop
0x1400e8a29  lea     rcx, [rbp+57h+var_48]
0x1400e8a2d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400e8a33  lea     rcx, [rbp+57h+var_60]
0x1400e8a37  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400e8a3d  mov     r9d, eax
0x1400e8a40  test    eax, eax
0x1400e8a42  jns     short loc_1400E8A7F
0x1400e8a44  lea     rax, WPP_GLOBAL_Control
0x1400e8a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8a52  cmp     rcx, rax
0x1400e8a55  jz      loc_1400E8C44
0x1400e8a5b  cmp     byte ptr [rcx+19h], 2
0x1400e8a5f  jb      loc_1400E8C44
0x1400e8a65  mov     edx, 2Ah ; '*'
0x1400e8a6a  lea     r8, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids
0x1400e8a71  mov     rcx, [rcx+10h]
0x1400e8a75  call    WPP_SF_d
0x1400e8a7a  jmp     loc_1400E8C44
0x1400e8a7f  lea     rax, [rbp+57h+arg_0]
0x1400e8a83  mov     [rsp+0B0h+var_88], rax
0x1400e8a88  mov     [rsp+0B0h+var_90], 0
0x1400e8a91  mov     r9, r14
0x1400e8a94  xor     r8d, r8d
0x1400e8a97  lea     rdx, aDescsection; "descsection"
0x1400e8a9e  mov     rcx, [rbx+28h]
0x1400e8aa2  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1400e8aa8  mov     edx, eax
0x1400e8aaa  lea     rcx, [rbp+57h+var_60]
0x1400e8aae  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e8ab4  lea     rcx, [rbp+57h+var_60]
0x1400e8ab8  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400e8abe  mov     r9d, eax
0x1400e8ac1  test    eax, eax
0x1400e8ac3  jns     short loc_1400E8AF0
0x1400e8ac5  lea     rax, WPP_GLOBAL_Control
0x1400e8acc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8ad3  cmp     rcx, rax
0x1400e8ad6  jz      loc_1400E8C44
0x1400e8adc  cmp     byte ptr [rcx+19h], 2
0x1400e8ae0  jb      loc_1400E8C44
0x1400e8ae6  mov     edx, 2Bh ; '+'
0x1400e8aeb  jmp     loc_1400E8A6A
0x1400e8af0  mov     rcx, [rbp+57h+arg_0]
0x1400e8af4  test    rcx, rcx
0x1400e8af7  jz      loc_1400E89EB
0x1400e8afd  movzx   edx, word ptr [rbx+5Ch]
0x1400e8b01  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1400e8b07  mov     rbx, rax
0x1400e8b0a  test    rax, rax
0x1400e8b0d  jz      loc_1400E89EB
0x1400e8b13  call    cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1400e8b19  mov     r8, rax
0x1400e8b1c  mov     [rsp+0B0h+var_70], 0
0x1400e8b25  mov     [rsp+0B0h+var_78], 0
0x1400e8b2e  mov     [rsp+0B0h+var_80], rsi
0x1400e8b33  mov     [rsp+0B0h+var_88], 0
0x1400e8b3c  mov     [rsp+0B0h+var_90], 0
0x1400e8b45  mov     r9, rbx
0x1400e8b48  mov     edx, 2
0x1400e8b4d  call    ?SetLocalValue@CDirectUIRender@@AEAAJW4eDUIValueType@1@PEBUPropertyInfo@DirectUI@@PEAVElement@4@PEA_NPEAHPEBGPEAUHICON__@@PEAK@Z; CDirectUIRender::SetLocalValue(CDirectUIRender::eDUIValueType,DirectUI::PropertyInfo const *,DirectUI::Element *,bool *,int *,ushort const *,HICON__ *,ulong *)
0x1400e8b52  mov     edx, eax
0x1400e8b54  lea     rcx, [rbp+57h+var_60]
0x1400e8b58  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e8b5e  lea     rcx, [rbp+57h+var_60]
0x1400e8b62  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400e8b68  mov     r9d, eax
0x1400e8b6b  test    eax, eax
0x1400e8b6d  jns     short loc_1400E8B9A
0x1400e8b6f  lea     rax, WPP_GLOBAL_Control
0x1400e8b76  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8b7d  cmp     rcx, rax
0x1400e8b80  jz      loc_1400E8C44
0x1400e8b86  cmp     byte ptr [rcx+19h], 2
0x1400e8b8a  jb      loc_1400E8C44
0x1400e8b90  mov     edx, 2Ch ; ','
0x1400e8b95  jmp     loc_1400E8A6A
0x1400e8b9a  mov     [rsp+0B0h+var_90], 0; unsigned __int16 *
0x1400e8ba3  mov     r9, rsi; unsigned __int16 *
0x1400e8ba6  mov     r8d, 29h ; ')'; int
0x1400e8bac  mov     rdx, rbx; struct DirectUI::Element *
0x1400e8baf  call    ?MakeAccessible@CDirectUIRender@@AEAAJPEAVElement@DirectUI@@HPEBG1@Z; CDirectUIRender::MakeAccessible(DirectUI::Element *,int,ushort const *,ushort const *)
0x1400e8bb4  mov     edx, eax
0x1400e8bb6  lea     rcx, [rbp+57h+var_60]
0x1400e8bba  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e8bc0  lea     rcx, [rbp+57h+var_60]
0x1400e8bc4  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400e8bca  mov     r9d, eax
0x1400e8bcd  test    eax, eax
0x1400e8bcf  jns     short loc_1400E8BF4
0x1400e8bd1  lea     rax, WPP_GLOBAL_Control
0x1400e8bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8bdf  cmp     rcx, rax
0x1400e8be2  jz      short loc_1400E8C44
0x1400e8be4  cmp     byte ptr [rcx+19h], 2
0x1400e8be8  jb      short loc_1400E8C44
0x1400e8bea  mov     edx, 2Dh ; '-'
0x1400e8bef  jmp     loc_1400E8A6A
0x1400e8bf4  mov     rdx, [rbp+57h+arg_0]
0x1400e8bf8  mov     rcx, r14
0x1400e8bfb  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x1400e8c01  mov     edx, eax
0x1400e8c03  lea     rcx, [rbp+57h+var_60]
0x1400e8c07  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e8c0d  lea     rcx, [rbp+57h+var_60]
0x1400e8c11  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400e8c17  mov     r9d, eax
0x1400e8c1a  test    eax, eax
0x1400e8c1c  jns     short loc_1400E8C41
0x1400e8c1e  lea     rax, WPP_GLOBAL_Control
0x1400e8c25  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8c2c  cmp     rcx, rax
0x1400e8c2f  jz      short loc_1400E8C44
0x1400e8c31  cmp     byte ptr [rcx+19h], 2
0x1400e8c35  jb      short loc_1400E8C44
0x1400e8c37  mov     edx, 2Eh ; '.'
0x1400e8c3c  jmp     loc_1400E8A6A
0x1400e8c41  mov     rdi, rbx
0x1400e8c44  lea     rcx, [rbp+57h+var_60]
0x1400e8c48  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400e8c4e  mov     rax, rdi
0x1400e8c51  add     rsp, 88h
0x1400e8c58  pop     r15
0x1400e8c5a  pop     r14
0x1400e8c5c  pop     rdi
0x1400e8c5d  pop     rsi
0x1400e8c5e  pop     rbx
0x1400e8c5f  pop     rbp
0x1400e8c60  retn
```
