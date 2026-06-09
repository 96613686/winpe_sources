# DuiTaskDlg::_SetGraphicContent(DirectUI::Element *,ushort const *,ushort *)

- ea: `0x180002838`
- end: `0x180002912`
- name: `?_SetGraphicContent@DuiTaskDlg@@IEAAJPEAVElement@DirectUI@@PEBGPEAG@Z`
- size: `218`
- prototype: `int(DuiTaskDlg *__hidden this, struct DirectUI::Element *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800036a0`

## callees

- `0x180002838`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002901`
- `OLEAUT32!__imp_SysFreeString` at `0x180002901`
- `USER32!LoadBitmapW` at `0x18000287c`
- `USER32!LoadBitmapW` at `0x18000287c`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800028d3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800028ef`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800028ef`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z` at `0x1800028c5`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z` at `0x1800028c5`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18000289d`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18000289d`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800028e6`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800028e6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000285d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000285d`
- `DUI70!StrToID` at `0x180002851`
- `DUI70!StrToID` at `0x180002851`

## pseudocode

```c
__int64 __fastcall DuiTaskDlg::_SetGraphicContent(
        HINSTANCE *this,
        struct DirectUI::Element *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbp
  HBITMAP BitmapW; // rax
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v11; // rbx
  unsigned int v12; // ebx

  v7 = StrToID(L"ItemImage", a2, a3);
  Descendent = DirectUI::Element::FindDescendent(a2, v7);
  if ( !Descendent )
  {
    v12 = -2147467259;
    goto LABEL_10;
  }
  if ( *a4 != 35 )
  {
    Graphic = DirectUI::Value::CreateGraphic(a4, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0);
LABEL_6:
    v11 = Graphic;
    if ( Graphic )
    {
      DirectUI::Element::SetValue(
        Descendent,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
        1,
        Graphic);
      DirectUI::Value::Release(v11);
    }
    goto LABEL_8;
  }
  BitmapW = LoadBitmapW(this[2], a4);
  if ( BitmapW )
  {
    Graphic = DirectUI::Value::CreateGraphic(BitmapW, 3u, 0xFFFFFFFF, 0, 0, 0);
    goto LABEL_6;
  }
LABEL_8:
  v12 = 0;
LABEL_10:
  SysFreeString(a4);
  return v12;
}

```

## disassembly

```asm
0x180002838  push    rbx
0x18000283a  push    rbp
0x18000283b  push    rsi
0x18000283c  push    rdi
0x18000283d  sub     rsp, 48h
0x180002841  mov     rsi, rcx
0x180002844  mov     rdi, r9
0x180002847  lea     rcx, aItemimage; "ItemImage"
0x18000284e  mov     rbx, rdx
0x180002851  call    cs:__imp_StrToID
0x180002857  movzx   edx, ax
0x18000285a  mov     rcx, rbx
0x18000285d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180002863  mov     rbp, rax
0x180002866  test    rax, rax
0x180002869  jz      loc_1800028F9
0x18000286f  cmp     word ptr [rdi], 23h ; '#'
0x180002873  jnz     short loc_1800028A5
0x180002875  mov     rcx, [rsi+10h]; hInstance
0x180002879  mov     rdx, rdi; lpBitmapName
0x18000287c  call    cs:__imp_LoadBitmapW
0x180002882  test    rax, rax
0x180002885  jz      short loc_1800028F5
0x180002887  mov     byte ptr [rsp+68h+var_40], 0
0x18000288c  xor     r9d, r9d
0x18000288f  or      r8d, 0FFFFFFFFh
0x180002893  mov     byte ptr [rsp+68h+var_48], 0
0x180002898  mov     dl, 3
0x18000289a  mov     rcx, rax
0x18000289d  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800028a3  jmp     short loc_1800028CB
0x1800028a5  xor     eax, eax
0x1800028a7  xor     r9d, r9d
0x1800028aa  mov     [rsp+68h+var_30], al
0x1800028ae  or      r8d, 0FFFFFFFFh
0x1800028b2  mov     [rsp+68h+var_38], al
0x1800028b6  mov     dl, 3
0x1800028b8  mov     [rsp+68h+var_40], rax
0x1800028bd  mov     rcx, rdi
0x1800028c0  mov     [rsp+68h+var_48], ax
0x1800028c5  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z; DirectUI::Value::CreateGraphic(ushort const *,uchar,uint,ushort,ushort,HINSTANCE__ *,bool,bool)
0x1800028cb  mov     rbx, rax
0x1800028ce  test    rax, rax
0x1800028d1  jz      short loc_1800028F5
0x1800028d3  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800028da  mov     r9, rax
0x1800028dd  mov     r8d, 1
0x1800028e3  mov     rcx, rbp
0x1800028e6  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800028ec  mov     rcx, rbx
0x1800028ef  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800028f5  xor     ebx, ebx
0x1800028f7  jmp     short loc_1800028FE
0x1800028f9  mov     ebx, 80004005h
0x1800028fe  mov     rcx, rdi; bstrString
0x180002901  call    cs:__imp_SysFreeString
0x180002907  mov     eax, ebx
0x180002909  add     rsp, 48h
0x18000290d  pop     rdi
0x18000290e  pop     rsi
0x18000290f  pop     rbp
0x180002910  pop     rbx
0x180002911  retn
```
