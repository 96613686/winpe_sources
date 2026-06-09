# SetIconOnElement(DirectUI::Element *,ushort const *,uint,uint,uint)

- ea: `0x180021164`
- end: `0x180021230`
- name: `?SetIconOnElement@@YAJPEAVElement@DirectUI@@PEBGIII@Z`
- size: `204`
- prototype: `int(struct DirectUI::Element *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180021000`

## callees

- `0x1800156a0`
- `0x18001ae20`
- `0x180021164`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002121d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002121d`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGGGPEAUHINSTANCE__@@_N2@Z` at `0x1800211dc`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGGGPEAUHINSTANCE__@@_N2@Z` at `0x1800211dc`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800211f1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180021204`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180021204`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002120f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002120f`

## pseudocode

```c
__int64 __fastcall SetIconOnElement(struct DirectUI::Element *a1, const unsigned __int16 *a2, unsigned __int16 a3)
{
  unsigned int v5; // ebx
  HINSTANCE v6; // rsi
  HMODULE v7; // rdi
  HINSTANCE LibraryFromSystemDir; // rax
  unsigned __int16 v9; // bx
  int v10; // edx
  unsigned __int16 v11; // ax
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v13; // rsi

  if ( a1 )
  {
    if ( a2 )
    {
      LibraryFromSystemDir = LoadLibraryFromSystemDir(a2);
      v7 = LibraryFromSystemDir;
      if ( !LibraryFromSystemDir )
        return (unsigned int)-2147467259;
      v6 = LibraryFromSystemDir;
    }
    else
    {
      v6 = g_hinst;
      v7 = 0;
    }
    v9 = DirectUI::RelPixToPixel((DirectUI *)0x18, (int)a2);
    v11 = DirectUI::RelPixToPixel((DirectUI *)0x18, v10);
    Graphic = DirectUI::Value::CreateGraphic((const unsigned __int16 *)a3, v9, v11, v6, 0, 0);
    v13 = Graphic;
    if ( Graphic )
    {
      v5 = DirectUI::Element::SetValue(
             a1,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
             1,
             Graphic);
      DirectUI::Value::Release(v13);
    }
    else
    {
      v5 = -2147024882;
    }
    if ( v7 )
      FreeLibrary(v7);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180021164  push    rbx
0x180021166  push    rbp
0x180021167  push    rsi
0x180021168  push    rdi
0x180021169  push    r14
0x18002116b  sub     rsp, 30h
0x18002116f  mov     r14d, r8d
0x180021172  mov     rbp, rcx
0x180021175  test    rcx, rcx
0x180021178  jnz     short loc_180021184
0x18002117a  mov     ebx, 80070057h
0x18002117f  jmp     loc_180021223
0x180021184  test    rdx, rdx
0x180021187  jnz     short loc_180021194
0x180021189  mov     rsi, cs:g_hinst
0x180021190  xor     edi, edi
0x180021192  jmp     short loc_1800211AE
0x180021194  mov     rcx, rdx; unsigned __int16 *
0x180021197  call    ?LoadLibraryFromSystemDir@@YAPEAUHINSTANCE__@@PEBGK@Z; LoadLibraryFromSystemDir(ushort const *,ulong)
0x18002119c  mov     rdi, rax
0x18002119f  test    rax, rax
0x1800211a2  jnz     short loc_1800211AB
0x1800211a4  mov     ebx, 80004005h
0x1800211a9  jmp     short loc_180021223
0x1800211ab  mov     rsi, rax
0x1800211ae  mov     ecx, 18h; this
0x1800211b3  call    ?RelPixToPixel@DirectUI@@YAHH@Z; DirectUI::RelPixToPixel(int)
0x1800211b8  mov     ecx, 18h; this
0x1800211bd  mov     ebx, eax
0x1800211bf  call    ?RelPixToPixel@DirectUI@@YAHH@Z; DirectUI::RelPixToPixel(int)
0x1800211c4  movzx   r8d, ax
0x1800211c8  movzx   ecx, r14w
0x1800211cc  movzx   edx, bx
0x1800211cf  mov     [rsp+58h+var_30], 0
0x1800211d4  mov     r9, rsi
0x1800211d7  mov     [rsp+58h+var_38], 0
0x1800211dc  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGGGPEAUHINSTANCE__@@_N2@Z; DirectUI::Value::CreateGraphic(ushort const *,ushort,ushort,HINSTANCE__ *,bool,bool)
0x1800211e2  mov     rsi, rax
0x1800211e5  test    rax, rax
0x1800211e8  jnz     short loc_1800211F1
0x1800211ea  mov     ebx, 8007000Eh
0x1800211ef  jmp     short loc_180021215
0x1800211f1  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800211f8  mov     r9, rsi
0x1800211fb  mov     r8d, 1
0x180021201  mov     rcx, rbp
0x180021204  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18002120a  mov     rcx, rsi
0x18002120d  mov     ebx, eax
0x18002120f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180021215  test    rdi, rdi
0x180021218  jz      short loc_180021223
0x18002121a  mov     rcx, rdi; hLibModule
0x18002121d  call    cs:__imp_FreeLibrary
0x180021223  mov     eax, ebx
0x180021225  add     rsp, 30h
0x180021229  pop     r14
0x18002122b  pop     rdi
0x18002122c  pop     rsi
0x18002122d  pop     rbp
0x18002122e  pop     rbx
0x18002122f  retn
```
