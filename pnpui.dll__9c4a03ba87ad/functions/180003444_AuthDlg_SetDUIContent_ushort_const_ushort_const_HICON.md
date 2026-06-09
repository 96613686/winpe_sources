# AuthDlg::SetDUIContent(ushort const *,ushort const *,HICON__ *)

- ea: `0x180003444`
- end: `0x180003549`
- name: `?SetDUIContent@AuthDlg@@QEAAJPEBG0PEAUHICON__@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(AuthDlg *__hidden this, OLECHAR *psz, OLECHAR *, HICON)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003110`

## callees

- `0x180003444`
- `0x1800036a0`

## import_xrefs

- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800034ef`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180003472`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180003472`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000350b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000350b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x1800034e1`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x1800034e1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180003502`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180003502`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180003538`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180003538`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800034c3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800034c3`
- `DUI70!StrToID` at `0x1800034b7`
- `DUI70!StrToID` at `0x1800034b7`

## pseudocode

```c
__int64 __fastcall AuthDlg::SetDUIContent(AuthDlg *this, OLECHAR *psz, OLECHAR *a3, HICON a4)
{
  struct DirectUI::Element *v8; // rdx
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // r8
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  DirectUI::Element *Descendent; // rdi
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v16; // rbx
  DirectUI::Element *v18; // [rsp+30h] [rbp-38h]
  unsigned int v19[12]; // [rsp+38h] [rbp-30h] BYREF

  v19[0] = 0;
  v18 = (DirectUI::Element *)*((_QWORD *)this + 24);
  DirectUI::Element::StartDefer(v18, v19);
  v8 = (struct DirectUI::Element *)*((_QWORD *)this + 24);
  if ( a4 == (HICON)-1LL )
  {
    v10 = AuthDlg::_ManualSetData(this, v8, psz, a3, 103);
  }
  else
  {
    v10 = AuthDlg::_ManualSetData(this, v8, psz, a3, -1);
    if ( v10 >= 0 )
    {
      v12 = (DirectUI::Element *)*((_QWORD *)this + 24);
      v13 = StrToID(L"ItemImage", v9, v11);
      Descendent = DirectUI::Element::FindDescendent(v12, v13);
      if ( Descendent )
      {
        if ( a4 )
        {
          Graphic = DirectUI::Value::CreateGraphic(a4, 0, 0, 0);
          v16 = Graphic;
          if ( Graphic )
          {
            DirectUI::Element::SetValue(
              Descendent,
              (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
              1,
              Graphic);
            DirectUI::Value::Release(v16);
          }
        }
        v10 = 0;
      }
      else
      {
        v10 = -2147467259;
      }
    }
  }
  if ( v19[0] )
    DirectUI::Element::EndDefer(v18, v19[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003444  push    rbx
0x180003446  push    rbp
0x180003447  push    rsi
0x180003448  push    rdi
0x180003449  sub     rsp, 48h
0x18000344d  mov     rdi, rcx
0x180003450  mov     [rsp+68h+var_30], 0
0x180003458  mov     rcx, [rcx+0C0h]
0x18000345f  mov     rbp, rdx
0x180003462  lea     rdx, [rsp+68h+var_30]
0x180003467  mov     [rsp+68h+var_38], rcx
0x18000346c  mov     rsi, r9
0x18000346f  mov     rbx, r8
0x180003472  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180003478  mov     rdx, [rdi+0C0h]; struct DirectUI::Element *
0x18000347f  mov     r9, rbx; OLECHAR *
0x180003482  mov     r8, rbp; psz
0x180003485  mov     rcx, rdi; this
0x180003488  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000348c  jz      loc_18000351C
0x180003492  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x18000349a  call    ?_ManualSetData@AuthDlg@@IEAAJPEAVElement@DirectUI@@PEBG1H@Z; AuthDlg::_ManualSetData(DirectUI::Element *,ushort const *,ushort const *,int)
0x18000349f  mov     ebx, eax
0x1800034a1  test    eax, eax
0x1800034a3  js      loc_18000352B
0x1800034a9  mov     rbx, [rdi+0C0h]
0x1800034b0  lea     rcx, aItemimage; "ItemImage"
0x1800034b7  call    cs:__imp_StrToID
0x1800034bd  movzx   edx, ax
0x1800034c0  mov     rcx, rbx
0x1800034c3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800034c9  mov     rdi, rax
0x1800034cc  test    rax, rax
0x1800034cf  jz      short loc_180003515
0x1800034d1  test    rsi, rsi
0x1800034d4  jz      short loc_180003511
0x1800034d6  xor     r9d, r9d
0x1800034d9  xor     r8d, r8d
0x1800034dc  xor     edx, edx
0x1800034de  mov     rcx, rsi
0x1800034e1  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x1800034e7  mov     rbx, rax
0x1800034ea  test    rax, rax
0x1800034ed  jz      short loc_180003511
0x1800034ef  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800034f6  mov     r9, rax
0x1800034f9  mov     r8d, 1
0x1800034ff  mov     rcx, rdi
0x180003502  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180003508  mov     rcx, rbx
0x18000350b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180003511  xor     ebx, ebx
0x180003513  jmp     short loc_18000352B
0x180003515  mov     ebx, 80004005h
0x18000351a  jmp     short loc_18000352B
0x18000351c  mov     [rsp+68h+var_48], 67h ; 'g'; int
0x180003524  call    ?_ManualSetData@AuthDlg@@IEAAJPEAVElement@DirectUI@@PEBG1H@Z; AuthDlg::_ManualSetData(DirectUI::Element *,ushort const *,ushort const *,int)
0x180003529  mov     ebx, eax
0x18000352b  mov     edx, [rsp+68h+var_30]
0x18000352f  test    edx, edx
0x180003531  jz      short loc_18000353E
0x180003533  mov     rcx, [rsp+68h+var_38]
0x180003538  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18000353e  mov     eax, ebx
0x180003540  add     rsp, 48h
0x180003544  pop     rdi
0x180003545  pop     rsi
0x180003546  pop     rbp
0x180003547  pop     rbx
0x180003548  retn
```
