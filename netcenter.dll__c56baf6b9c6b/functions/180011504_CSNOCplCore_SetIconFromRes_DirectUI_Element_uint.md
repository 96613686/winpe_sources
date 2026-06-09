# CSNOCplCore::SetIconFromRes(DirectUI::Element *,uint)

- ea: `0x180011504`
- end: `0x1800115b8`
- name: `?SetIconFromRes@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@I@Z`
- size: `180`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Element *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012a84`
- `0x18001305c`

## callees

- `0x180010e9c`
- `0x180011504`

## import_xrefs

- `USER32!LoadImageW` at `0x180011550`
- `USER32!LoadImageW` at `0x180011550`
- `USER32!GetSystemMetrics` at `0x18001151e`
- `USER32!GetSystemMetrics` at `0x18001152b`
- `USER32!GetSystemMetrics` at `0x18001151e`
- `USER32!GetSystemMetrics` at `0x18001152b`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180011579`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18001158c`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18001158c`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x18001156b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x18001156b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180011597`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180011597`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::SetIconFromRes(CSNOCplCore *this, struct DirectUI::Element *a2, unsigned __int16 a3)
{
  int cy; // ebx
  int SystemMetrics; // eax
  HICON ImageW; // rax
  unsigned int v8; // ebx
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v10; // rdi

  cy = GetSystemMetrics(50);
  SystemMetrics = GetSystemMetrics(49);
  ImageW = (HICON)LoadImageW(g_hinst, (LPCWSTR)a3, 1u, SystemMetrics, cy, 0);
  if ( ImageW )
  {
    v8 = -2147467259;
    Graphic = DirectUI::Value::CreateGraphic(ImageW, 0, 0, 0);
    v10 = Graphic;
    if ( Graphic )
    {
      v8 = DirectUI::Element::SetValue(
             a2,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
             1,
             Graphic);
      DirectUI::Value::Release(v10);
    }
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return v8;
}

```

## disassembly

```asm
0x180011504  mov     [rsp+arg_0], rbx
0x180011509  mov     [rsp+arg_8], rsi
0x18001150e  push    rdi
0x18001150f  sub     rsp, 30h
0x180011513  mov     ecx, 32h ; '2'; nIndex
0x180011518  mov     edi, r8d
0x18001151b  mov     rsi, rdx
0x18001151e  call    cs:__imp_GetSystemMetrics
0x180011524  mov     ecx, 31h ; '1'; nIndex
0x180011529  mov     ebx, eax
0x18001152b  call    cs:__imp_GetSystemMetrics
0x180011531  mov     rcx, cs:g_hinst; hInst
0x180011538  mov     r8d, 1; type
0x18001153e  mov     r9d, eax; cx
0x180011541  movzx   edx, di; name
0x180011544  mov     [rsp+38h+fuLoad], 0; fuLoad
0x18001154c  mov     [rsp+38h+cy], ebx; cy
0x180011550  call    cs:__imp_LoadImageW
0x180011556  test    rax, rax
0x180011559  jz      short loc_18001159F
0x18001155b  xor     r9d, r9d
0x18001155e  xor     r8d, r8d
0x180011561  xor     edx, edx
0x180011563  mov     rcx, rax
0x180011566  mov     ebx, 80004005h
0x18001156b  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x180011571  mov     rdi, rax
0x180011574  test    rax, rax
0x180011577  jz      short loc_1800115A6
0x180011579  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180011580  mov     r9, rax
0x180011583  mov     r8d, 1
0x180011589  mov     rcx, rsi
0x18001158c  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180011592  mov     rcx, rdi
0x180011595  mov     ebx, eax
0x180011597  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001159d  jmp     short loc_1800115A6
0x18001159f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800115a4  mov     ebx, eax
0x1800115a6  mov     rsi, [rsp+38h+arg_8]
0x1800115ab  mov     eax, ebx
0x1800115ad  mov     rbx, [rsp+38h+arg_0]
0x1800115b2  add     rsp, 30h
0x1800115b6  pop     rdi
0x1800115b7  retn
```
