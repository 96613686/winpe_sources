# CAdvancedPage::_OnUpdateSettings(CplUpdateAdvancedSettingsEvent *)

- ea: `0x18000a44c`
- end: `0x18000a4d7`
- name: `?_OnUpdateSettings@CAdvancedPage@@AEAAXPEAUCplUpdateAdvancedSettingsEvent@@@Z`
- size: `139`
- prototype: `void __fastcall(CAdvancedPage *__hidden this, struct CplUpdateAdvancedSettingsEvent *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180008250`

## callees

- `0x18000a44c`
- `0x18000a6f8`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a484`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a4a3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a484`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a4a3`
- `DUI70!StrToID` at `0x18000a478`
- `DUI70!StrToID` at `0x18000a497`
- `DUI70!StrToID` at `0x18000a478`
- `DUI70!StrToID` at `0x18000a497`

## pseudocode

```c
void __fastcall CAdvancedPage::_OnUpdateSettings(CAdvancedPage *this, struct CplUpdateAdvancedSettingsEvent *a2)
{
  __int64 i; // rdi
  DirectUI::Element *v5; // rbx
  __int64 v6; // rsi
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *v10; // rax

  for ( i = 0; i != 12; ++i )
  {
    v5 = (DirectUI::Element *)*((_QWORD *)this + 2);
    v6 = 4 * i;
    v7 = StrToID(qword_18001C260[4 * i + 1]);
    Descendent = DirectUI::Element::FindDescendent(v5, v7);
    if ( Descendent )
    {
      v9 = StrToID(qword_18001C260[v6 + 2]);
      v10 = DirectUI::Element::FindDescendent(Descendent, v9);
      if ( v10 )
        CAdvancedPage::_UpdateSetting((__int64)this, *((_QWORD *)a2 + 4), qword_18001C260[v6], v10);
    }
  }
}

```

## disassembly

```asm
0x18000a44c  push    rbx
0x18000a44e  push    rbp
0x18000a44f  push    rsi
0x18000a450  push    rdi
0x18000a451  push    r14
0x18000a453  push    r15
0x18000a455  sub     rsp, 28h
0x18000a459  mov     r14, rdx
0x18000a45c  lea     r15, qword_18001C260
0x18000a463  mov     rbp, rcx
0x18000a466  xor     edi, edi
0x18000a468  mov     rbx, [rbp+10h]
0x18000a46c  mov     rsi, rdi
0x18000a46f  shl     rsi, 5
0x18000a473  mov     rcx, [rsi+r15+8]
0x18000a478  call    cs:__imp_StrToID
0x18000a47e  movzx   edx, ax
0x18000a481  mov     rcx, rbx
0x18000a484  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a48a  mov     rbx, rax
0x18000a48d  test    rax, rax
0x18000a490  jz      short loc_18000A4C1
0x18000a492  mov     rcx, [rsi+r15+10h]
0x18000a497  call    cs:__imp_StrToID
0x18000a49d  movzx   edx, ax
0x18000a4a0  mov     rcx, rbx
0x18000a4a3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a4a9  test    rax, rax
0x18000a4ac  jz      short loc_18000A4C1
0x18000a4ae  mov     r8d, [rsi+r15]
0x18000a4b2  mov     r9, rax
0x18000a4b5  mov     rdx, [r14+20h]
0x18000a4b9  mov     rcx, rbp
0x18000a4bc  call    ?_UpdateSetting@CAdvancedPage@@AEAAXPEBUtagADVANCED_SETTING_READER_VALUE@@W4ADVANCED_SETTING@@PEAVElement@DirectUI@@@Z; CAdvancedPage::_UpdateSetting(tagADVANCED_SETTING_READER_VALUE const *,ADVANCED_SETTING,DirectUI::Element *)
0x18000a4c1  inc     rdi
0x18000a4c4  cmp     rdi, 0Ch
0x18000a4c8  jnz     short loc_18000A468
0x18000a4ca  add     rsp, 28h
0x18000a4ce  pop     r15
0x18000a4d0  pop     r14
0x18000a4d2  pop     rdi
0x18000a4d3  pop     rsi
0x18000a4d4  pop     rbp
0x18000a4d5  pop     rbx
0x18000a4d6  retn
```
