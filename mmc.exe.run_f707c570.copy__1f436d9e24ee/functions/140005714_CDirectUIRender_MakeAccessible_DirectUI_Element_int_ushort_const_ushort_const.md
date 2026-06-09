# CDirectUIRender::MakeAccessible(DirectUI::Element *,int,ushort const *,ushort const *)

- ea: `0x140005714`
- end: `0x140005a21`
- name: `?MakeAccessible@CDirectUIRender@@AEAAJPEAVElement@DirectUI@@HPEBG1@Z`
- size: `781`
- prototype: `__int64 __fastcall(CDirectUIRender *__hidden this, struct DirectUI::Element *, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003350`
- `0x140004520`
- `0x1400301b8`
- `0x1400e8994`
- `0x1400e8c68`

## callees

- `0x140005040`
- `0x140005714`
- `0x1400598b4`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14000578c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140005a01`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14000578c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140005a01`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140005744`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140005772`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140005744`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140005772`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140005796`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x14000580e`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140005885`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400058fe`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400059b7`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400059f5`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140005796`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x14000580e`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140005885`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400058fe`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400059b7`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400059f5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140005804`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14000587b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400058f4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14000596d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400059ad`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140005804`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14000587b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400058f4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14000596d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400059ad`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140005781`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140005781`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140005756`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140005756`
- `DUI70!?AccNameProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400057cd`
- `DUI70!?AccNameProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400057cd`
- `DUI70!?AccDefActionProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140005849`
- `DUI70!?AccDefActionProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140005849`
- `DUI70!?AccRoleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400058b9`
- `DUI70!?AccRoleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400058b9`
- `DUI70!?ShortcutProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140005937`
- `DUI70!?ShortcutProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140005937`
- `DUI70!?AccessibleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140005977`
- `DUI70!?AccessibleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140005977`

## string_xrefs

- `0x14000574b`: `CDirectUIRender::MakeAccessible`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDirectUIRender::MakeAccessible(
        CDirectUIRender *this,
        struct DirectUI::Element *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  int v7; // edx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  const struct DirectUI::PropertyInfo *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  const unsigned __int16 *v14; // rsi
  const struct DirectUI::PropertyInfo *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // eax
  const struct DirectUI::PropertyInfo *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // eax
  const struct DirectUI::PropertyInfo *v21; // rax
  __int64 v22; // rcx
  unsigned int v23; // eax
  const struct DirectUI::PropertyInfo *v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // ebx
  _BYTE v29[24]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v30[24]; // [rsp+68h] [rbp-18h] BYREF
  CDirectUIRender *v31; // [rsp+A0h] [rbp+20h] BYREF
  unsigned int v32; // [rsp+B0h] [rbp+30h] BYREF

  v32 = a3;
  v31 = this;
  mmcerror::SC::SC((mmcerror::SC *)v29, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v29, L"CDirectUIRender::MakeAccessible");
  if ( !a2 || (v7 = 0, !a4) )
    v7 = -2147024809;
  mmcerror::SC::SC((mmcerror::SC *)v30, v7);
  mmcerror::SC::operator=(v29, v30);
  mmcerror::SC::~SC((mmcerror::SC *)v30);
  v8 = mmcerror::SC::ToHr((mmcerror::SC *)v29);
  if ( v8 >= 0 )
  {
    v11 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::AccNameProp();
    v13 = CDirectUIRender::SetLocalValue(v12, 2, v11, a2, 0, 0, a4, 0, 0);
    mmcerror::SC::operator=(v29, v13);
    v8 = mmcerror::SC::ToHr((mmcerror::SC *)v29);
    if ( v8 >= 0 )
    {
      v14 = a5;
      if ( a5
        && (v15 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::AccDefActionProp(),
            v17 = CDirectUIRender::SetLocalValue(v16, 2, v15, a2, 0, 0, v14, 0, 0),
            mmcerror::SC::operator=(v29, v17),
            v8 = mmcerror::SC::ToHr((mmcerror::SC *)v29),
            v8 < 0) )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v10 = 82;
          goto LABEL_25;
        }
      }
      else
      {
        v18 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::AccRoleProp();
        v20 = CDirectUIRender::SetLocalValue(v19, 1, v18, a2, 0, &v32, 0, 0, 0);
        mmcerror::SC::operator=(v29, v20);
        v8 = mmcerror::SC::ToHr((mmcerror::SC *)v29);
        if ( v8 >= 0 )
        {
          LODWORD(v31) = 32;
          v21 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ShortcutProp();
          v23 = CDirectUIRender::SetLocalValue(v22, 1, v21, a2, 0, (unsigned int *)&v31, 0, 0, 0);
          mmcerror::SC::operator=(v29, v23);
          LOBYTE(v31) = 1;
          v24 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::AccessibleProp();
          v26 = CDirectUIRender::SetLocalValue(v25, 0, v24, a2, (bool *)&v31, 0, 0, 0, 0);
          mmcerror::SC::operator=(v29, v26);
          v8 = mmcerror::SC::ToHr((mmcerror::SC *)v29);
          if ( v8 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              v10 = 84;
              goto LABEL_25;
            }
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v10 = 83;
            goto LABEL_25;
          }
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v10 = 81;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v10 = 80;
LABEL_25:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids, (unsigned int)v8);
    }
  }
  v27 = mmcerror::SC::ToHr((mmcerror::SC *)v29);
  mmcerror::SC::~SC((mmcerror::SC *)v29);
  return v27;
}

```

## disassembly

```asm
0x140005714  mov     rax, rsp
0x140005717  mov     [rax+10h], rbx
0x14000571b  mov     [rax+20h], rsi
0x14000571f  mov     [rax+18h], r8d
0x140005723  mov     [rax+8], rcx
0x140005727  push    rbp
0x140005728  push    rdi
0x140005729  push    r14
0x14000572b  mov     rbp, rsp
0x14000572e  sub     rsp, 80h
0x140005735  mov     rbx, r9
0x140005738  mov     rdi, rdx
0x14000573b  xor     r14d, r14d
0x14000573e  xor     edx, edx
0x140005740  lea     rcx, [rbp+var_30]
0x140005744  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14000574a  nop
0x14000574b  lea     rdx, aCdirectuirende_9; "CDirectUIRender::MakeAccessible"
0x140005752  lea     rcx, [rbp+var_30]
0x140005756  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14000575c  test    rdi, rdi
0x14000575f  jz      short loc_140005769
0x140005761  test    rbx, rbx
0x140005764  mov     edx, r14d
0x140005767  jnz     short loc_14000576E
0x140005769  mov     edx, 80070057h
0x14000576e  lea     rcx, [rbp+var_18]
0x140005772  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140005778  nop
0x140005779  lea     rdx, [rbp+var_18]
0x14000577d  lea     rcx, [rbp+var_30]
0x140005781  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140005787  nop
0x140005788  lea     rcx, [rbp+var_18]
0x14000578c  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140005792  lea     rcx, [rbp+var_30]
0x140005796  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x14000579c  test    eax, eax
0x14000579e  jns     short loc_1400057CD
0x1400057a0  lea     rdx, WPP_GLOBAL_Control
0x1400057a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057ae  cmp     rcx, rdx
0x1400057b1  jz      loc_1400059F1
0x1400057b7  mov     ebx, 2
0x1400057bc  cmp     [rcx+19h], bl
0x1400057bf  jb      loc_1400059F1
0x1400057c5  lea     edx, [rbx+4Eh]
0x1400057c8  jmp     loc_1400059DE
0x1400057cd  call    cs:__imp_?AccNameProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccNameProp(void)
0x1400057d3  mov     r8, rax
0x1400057d6  mov     [rsp+80h+var_40], r14
0x1400057db  mov     [rsp+80h+var_48], r14
0x1400057e0  mov     [rsp+80h+var_50], rbx
0x1400057e5  mov     [rsp+80h+var_58], r14
0x1400057ea  mov     [rsp+80h+var_60], r14
0x1400057ef  mov     r9, rdi
0x1400057f2  mov     ebx, 2
0x1400057f7  mov     edx, ebx
0x1400057f9  call    ?SetLocalValue@CDirectUIRender@@AEAAJW4eDUIValueType@1@PEBUPropertyInfo@DirectUI@@PEAVElement@4@PEA_NPEAHPEBGPEAUHICON__@@PEAK@Z; CDirectUIRender::SetLocalValue(CDirectUIRender::eDUIValueType,DirectUI::PropertyInfo const *,DirectUI::Element *,bool *,int *,ushort const *,HICON__ *,ulong *)
0x1400057fe  mov     edx, eax
0x140005800  lea     rcx, [rbp+var_30]
0x140005804  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14000580a  lea     rcx, [rbp+var_30]
0x14000580e  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140005814  test    eax, eax
0x140005816  jns     short loc_140005840
0x140005818  lea     rdx, WPP_GLOBAL_Control
0x14000581f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005826  cmp     rcx, rdx
0x140005829  jz      loc_1400059F1
0x14000582f  cmp     [rcx+19h], bl
0x140005832  jb      loc_1400059F1
0x140005838  lea     edx, [rbx+4Fh]
0x14000583b  jmp     loc_1400059DE
0x140005840  mov     rsi, [rbp+arg_20]
0x140005844  test    rsi, rsi
0x140005847  jz      short loc_1400058B9
0x140005849  call    cs:__imp_?AccDefActionProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccDefActionProp(void)
0x14000584f  mov     r8, rax
0x140005852  mov     [rsp+80h+var_40], r14
0x140005857  mov     [rsp+80h+var_48], r14
0x14000585c  mov     [rsp+80h+var_50], rsi
0x140005861  mov     [rsp+80h+var_58], r14
0x140005866  mov     [rsp+80h+var_60], r14
0x14000586b  mov     r9, rdi
0x14000586e  mov     edx, ebx
0x140005870  call    ?SetLocalValue@CDirectUIRender@@AEAAJW4eDUIValueType@1@PEBUPropertyInfo@DirectUI@@PEAVElement@4@PEA_NPEAHPEBGPEAUHICON__@@PEAK@Z; CDirectUIRender::SetLocalValue(CDirectUIRender::eDUIValueType,DirectUI::PropertyInfo const *,DirectUI::Element *,bool *,int *,ushort const *,HICON__ *,ulong *)
0x140005875  mov     edx, eax
0x140005877  lea     rcx, [rbp+var_30]
0x14000587b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140005881  lea     rcx, [rbp+var_30]
0x140005885  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x14000588b  test    eax, eax
0x14000588d  jns     short loc_1400058B9
0x14000588f  lea     rdx, WPP_GLOBAL_Control
0x140005896  mov     rcx, cs:WPP_GLOBAL_Control
0x14000589d  cmp     rcx, rdx
0x1400058a0  jz      loc_1400059F1
0x1400058a6  cmp     [rcx+19h], bl
0x1400058a9  jb      loc_1400059F1
0x1400058af  mov     edx, 52h ; 'R'
0x1400058b4  jmp     loc_1400059DE
0x1400058b9  call    cs:__imp_?AccRoleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccRoleProp(void)
0x1400058bf  mov     r8, rax
0x1400058c2  mov     [rsp+80h+var_40], r14
0x1400058c7  mov     [rsp+80h+var_48], r14
0x1400058cc  mov     [rsp+80h+var_50], r14
0x1400058d1  lea     rax, [rbp+arg_10]
0x1400058d5  mov     [rsp+80h+var_58], rax
0x1400058da  mov     [rsp+80h+var_60], r14
0x1400058df  mov     r9, rdi
0x1400058e2  mov     esi, 1
0x1400058e7  mov     edx, esi
0x1400058e9  call    ?SetLocalValue@CDirectUIRender@@AEAAJW4eDUIValueType@1@PEBUPropertyInfo@DirectUI@@PEAVElement@4@PEA_NPEAHPEBGPEAUHICON__@@PEAK@Z; CDirectUIRender::SetLocalValue(CDirectUIRender::eDUIValueType,DirectUI::PropertyInfo const *,DirectUI::Element *,bool *,int *,ushort const *,HICON__ *,ulong *)
0x1400058ee  mov     edx, eax
0x1400058f0  lea     rcx, [rbp+var_30]
0x1400058f4  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400058fa  lea     rcx, [rbp+var_30]
0x1400058fe  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140005904  test    eax, eax
0x140005906  jns     short loc_140005930
0x140005908  lea     rdx, WPP_GLOBAL_Control
0x14000590f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005916  cmp     rcx, rdx
0x140005919  jz      loc_1400059F1
0x14000591f  cmp     [rcx+19h], bl
0x140005922  jb      loc_1400059F1
0x140005928  lea     edx, [rsi+52h]
0x14000592b  jmp     loc_1400059DE
0x140005930  mov     dword ptr [rbp+arg_0], 20h ; ' '
0x140005937  call    cs:__imp_?ShortcutProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ShortcutProp(void)
0x14000593d  mov     r8, rax
0x140005940  mov     [rsp+80h+var_40], r14
0x140005945  mov     [rsp+80h+var_48], r14
0x14000594a  mov     [rsp+80h+var_50], r14
0x14000594f  lea     rax, [rbp+arg_0]
0x140005953  mov     [rsp+80h+var_58], rax
0x140005958  mov     [rsp+80h+var_60], r14
0x14000595d  mov     r9, rdi
0x140005960  mov     edx, esi
0x140005962  call    ?SetLocalValue@CDirectUIRender@@AEAAJW4eDUIValueType@1@PEBUPropertyInfo@DirectUI@@PEAVElement@4@PEA_NPEAHPEBGPEAUHICON__@@PEAK@Z; CDirectUIRender::SetLocalValue(CDirectUIRender::eDUIValueType,DirectUI::PropertyInfo const *,DirectUI::Element *,bool *,int *,ushort const *,HICON__ *,ulong *)
0x140005967  mov     edx, eax
0x140005969  lea     rcx, [rbp+var_30]
0x14000596d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140005973  mov     byte ptr [rbp+arg_0], sil
0x140005977  call    cs:__imp_?AccessibleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccessibleProp(void)
0x14000597d  mov     r8, rax
0x140005980  mov     [rsp+80h+var_40], r14
0x140005985  mov     [rsp+80h+var_48], r14
0x14000598a  mov     [rsp+80h+var_50], r14
0x14000598f  mov     [rsp+80h+var_58], r14
0x140005994  lea     rax, [rbp+arg_0]
0x140005998  mov     [rsp+80h+var_60], rax
0x14000599d  mov     r9, rdi
0x1400059a0  xor     edx, edx
0x1400059a2  call    ?SetLocalValue@CDirectUIRender@@AEAAJW4eDUIValueType@1@PEBUPropertyInfo@DirectUI@@PEAVElement@4@PEA_NPEAHPEBGPEAUHICON__@@PEAK@Z; CDirectUIRender::SetLocalValue(CDirectUIRender::eDUIValueType,DirectUI::PropertyInfo const *,DirectUI::Element *,bool *,int *,ushort const *,HICON__ *,ulong *)
0x1400059a7  mov     edx, eax
0x1400059a9  lea     rcx, [rbp+var_30]
0x1400059ad  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400059b3  lea     rcx, [rbp+var_30]
0x1400059b7  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400059bd  test    eax, eax
0x1400059bf  jns     short loc_1400059F1
0x1400059c1  lea     rdx, WPP_GLOBAL_Control
0x1400059c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059cf  cmp     rcx, rdx
0x1400059d2  jz      short loc_1400059F1
0x1400059d4  cmp     [rcx+19h], bl
0x1400059d7  jb      short loc_1400059F1
0x1400059d9  mov     edx, 54h ; 'T'
0x1400059de  mov     r9d, eax
0x1400059e1  lea     r8, WPP_af702272411f32d5bae2e4aec0f6e859_Traceguids
0x1400059e8  mov     rcx, [rcx+10h]
0x1400059ec  call    WPP_SF_d
0x1400059f1  lea     rcx, [rbp+var_30]
0x1400059f5  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400059fb  mov     ebx, eax
0x1400059fd  lea     rcx, [rbp+var_30]
0x140005a01  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140005a07  mov     eax, ebx
0x140005a09  lea     r11, [rsp+80h+var_s0]
0x140005a11  mov     rbx, [r11+28h]
0x140005a15  mov     rsi, [r11+38h]
0x140005a19  mov     rsp, r11
0x140005a1c  pop     r14
0x140005a1e  pop     rdi
0x140005a1f  pop     rbp
0x140005a20  retn
```
