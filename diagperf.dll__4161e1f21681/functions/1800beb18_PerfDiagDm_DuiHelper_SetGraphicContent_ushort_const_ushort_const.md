# PerfDiagDm::DuiHelper::SetGraphicContent(ushort const *,ushort const *)

- ea: `0x1800beb18`
- end: `0x1800bec11`
- name: `?SetGraphicContent@DuiHelper@PerfDiagDm@@QEAAJPEBG0@Z`
- size: `249`
- prototype: `int(PerfDiagDm::DuiHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800bec18`

## callees

- `0x1800beb18`

## import_xrefs

- `USER32!LoadBitmapW` at `0x1800beb70`
- `USER32!LoadBitmapW` at `0x1800beb70`
- `GDI32!DeleteObject` at `0x1800bebeb`
- `GDI32!DeleteObject` at `0x1800bebeb`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800bebb4`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800bebb4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800bebde`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800bebde`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800beb4a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800beb4a`
- `DUI70!StrToID` at `0x1800beb3e`
- `DUI70!StrToID` at `0x1800beb3e`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800bebff`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800bebff`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800beb97`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800beb97`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800bebcb`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800bebd5`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800bebd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PerfDiagDm::DuiHelper::SetGraphicContent(
        DirectUI::Element **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  DirectUI::Element *v4; // rsi
  unsigned int v6; // ebx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbp
  HBITMAP BitmapW; // rdi
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v11; // rsi
  unsigned int v12[12]; // [rsp+38h] [rbp-30h] BYREF

  v4 = *this;
  if ( !*this )
    return 2147500037LL;
  v6 = -2147467259;
  v7 = StrToID(a2);
  Descendent = DirectUI::Element::FindDescendent(v4, v7);
  if ( Descendent )
  {
    if ( *a3 == 35 )
    {
      BitmapW = LoadBitmapW(hInstance, a3);
      if ( BitmapW )
      {
        v12[0] = 0;
        DirectUI::Element::StartDefer(Descendent, v12);
        Graphic = DirectUI::Value::CreateGraphic(BitmapW, 3u, 0xFFFFFFFF, 0, 0, 0);
        v11 = Graphic;
        if ( Graphic )
        {
          DirectUI::Element::SetValue(
            Descendent,
            (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
            1,
            Graphic);
          DirectUI::Value::Release(v11);
          v6 = 0;
        }
        else
        {
          DeleteObject(BitmapW);
        }
        if ( v12[0] )
          DirectUI::Element::EndDefer(Descendent, v12[0]);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800beb18  push    rbx
0x1800beb1a  push    rbp
0x1800beb1b  push    rsi
0x1800beb1c  push    rdi
0x1800beb1d  sub     rsp, 48h
0x1800beb21  mov     rdi, r8
0x1800beb24  mov     rsi, [rcx]
0x1800beb27  test    rsi, rsi
0x1800beb2a  jnz     short loc_1800BEB36
0x1800beb2c  mov     eax, 80004005h
0x1800beb31  jmp     loc_1800BEC08
0x1800beb36  mov     ebx, 80004005h
0x1800beb3b  mov     rcx, rdx
0x1800beb3e  call    cs:__imp_StrToID
0x1800beb44  movzx   edx, ax
0x1800beb47  mov     rcx, rsi
0x1800beb4a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800beb50  mov     rbp, rax
0x1800beb53  test    rax, rax
0x1800beb56  jz      loc_1800BEC06
0x1800beb5c  cmp     word ptr [rdi], 23h ; '#'
0x1800beb60  jnz     loc_1800BEC06
0x1800beb66  mov     rdx, rdi; lpBitmapName
0x1800beb69  mov     rcx, cs:hInstance; hInstance
0x1800beb70  call    cs:__imp_LoadBitmapW
0x1800beb76  mov     rdi, rax
0x1800beb79  test    rax, rax
0x1800beb7c  jz      loc_1800BEC06
0x1800beb82  mov     [rsp+68h+var_38], rbp
0x1800beb87  mov     [rsp+68h+var_30], 0
0x1800beb8f  lea     rdx, [rsp+68h+var_30]
0x1800beb94  mov     rcx, rbp
0x1800beb97  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1800beb9d  nop
0x1800beb9e  mov     [rsp+68h+var_40], 0
0x1800beba3  mov     [rsp+68h+var_48], 0
0x1800beba8  xor     r9d, r9d
0x1800bebab  or      r8d, 0FFFFFFFFh
0x1800bebaf  mov     dl, 3
0x1800bebb1  mov     rcx, rdi
0x1800bebb4  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800bebba  mov     rsi, rax
0x1800bebbd  test    rax, rax
0x1800bebc0  jz      short loc_1800BEBE8
0x1800bebc2  mov     r9, rax
0x1800bebc5  mov     r8d, 1
0x1800bebcb  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800bebd2  mov     rcx, rbp
0x1800bebd5  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800bebdb  mov     rcx, rsi
0x1800bebde  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800bebe4  xor     ebx, ebx
0x1800bebe6  jmp     short loc_1800BEBF2
0x1800bebe8  mov     rcx, rdi; ho
0x1800bebeb  call    cs:__imp_DeleteObject
0x1800bebf1  nop
0x1800bebf2  mov     edx, [rsp+68h+var_30]
0x1800bebf6  test    edx, edx
0x1800bebf8  jz      short loc_1800BEC06
0x1800bebfa  mov     rcx, [rsp+68h+var_38]
0x1800bebff  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x1800bec05  nop
0x1800bec06  mov     eax, ebx
0x1800bec08  add     rsp, 48h
0x1800bec0c  pop     rdi
0x1800bec0d  pop     rsi
0x1800bec0e  pop     rbp
0x1800bec0f  pop     rbx
0x1800bec10  retn
```
