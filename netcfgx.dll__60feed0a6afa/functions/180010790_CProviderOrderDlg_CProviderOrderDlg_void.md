# CProviderOrderDlg::~CProviderOrderDlg(void)

- ea: `0x180010790`
- end: `0x1800107d7`
- name: `??1CProviderOrderDlg@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CProviderOrderDlg *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000da34`
- `0x180010810`
- `0x18001276d`

## callees

- `0x180010724`
- `0x180010790`
- `0x180011e0c`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800107ac`
- `GDI32!DeleteObject` at `0x1800107bb`
- `GDI32!DeleteObject` at `0x1800107ac`
- `GDI32!DeleteObject` at `0x1800107bb`

## pseudocode

```c
void __fastcall CProviderOrderDlg::~CProviderOrderDlg(CProviderOrderDlg *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CProviderOrderDlg::`vftable';
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    DeleteObject(v2);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
    DeleteObject(v3);
  std::list<ProviderOrder>::~list<ProviderOrder>((char *)this + 56);
  CPropSheetPage::~CPropSheetPage(this);
}

```

## disassembly

```asm
0x180010790  push    rbx
0x180010792  sub     rsp, 20h
0x180010796  lea     rax, ??_7CProviderOrderDlg@@6B@; const CProviderOrderDlg::`vftable'
0x18001079d  mov     rbx, rcx
0x1800107a0  mov     [rcx], rax
0x1800107a3  mov     rcx, [rcx+20h]; ho
0x1800107a7  test    rcx, rcx
0x1800107aa  jz      short loc_1800107B2
0x1800107ac  call    cs:__imp_DeleteObject
0x1800107b2  mov     rcx, [rbx+28h]; ho
0x1800107b6  test    rcx, rcx
0x1800107b9  jz      short loc_1800107C1
0x1800107bb  call    cs:__imp_DeleteObject
0x1800107c1  lea     rcx, [rbx+38h]
0x1800107c5  call    ??1?$list@UProviderOrder@@V?$allocator@UProviderOrder@@@std@@@std@@QEAA@XZ; std::list<ProviderOrder>::~list<ProviderOrder>(void)
0x1800107ca  mov     rcx, rbx; this
0x1800107cd  add     rsp, 20h
0x1800107d1  pop     rbx
0x1800107d2  jmp     ??1CPropSheetPage@@UEAA@XZ; CPropSheetPage::~CPropSheetPage(void)
```
