# DUI_SetElementStringProperty(DirectUI::Element *,DirectUI::PropertyInfo const * (*)(void),ushort const *,HINSTANCE__ *)

- ea: `0x180010488`
- end: `0x1800104f4`
- name: `?DUI_SetElementStringProperty@@YAJPEAVElement@DirectUI@@P6APEBUPropertyInfo@2@XZPEBGPEAUHINSTANCE__@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, const struct DirectUI::PropertyInfo *(*)(void), const unsigned __int16 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a6f8`

## callees

- `0x180010488`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800104dc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800104dc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800104d1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800104d1`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1800104ad`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1800104ad`

## pseudocode

```c
__int64 __fastcall DUI_SetElementStringProperty(
        struct DirectUI::Element *a1,
        const struct DirectUI::PropertyInfo *(*a2)(void),
        const unsigned __int16 *a3,
        unsigned __int64 a4)
{
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v7; // rdi
  unsigned int v8; // ebx

  String = DirectUI::Value::CreateString(a3, (HINSTANCE)(a4 & -(__int64)((unsigned __int64)a3 < 0x10000)));
  v7 = String;
  if ( String )
  {
    v8 = DirectUI::Element::SetValue(a1, a2, 1, String);
    DirectUI::Value::Release(v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180010488  mov     [rsp+arg_0], rbx
0x18001048d  mov     [rsp+arg_8], rsi
0x180010492  push    rdi
0x180010493  sub     rsp, 20h
0x180010497  mov     rbx, rdx
0x18001049a  cmp     r8, 10000h
0x1800104a1  mov     rsi, rcx
0x1800104a4  mov     rcx, r8
0x1800104a7  sbb     rdx, rdx
0x1800104aa  and     rdx, r9
0x1800104ad  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x1800104b3  mov     rdi, rax
0x1800104b6  test    rax, rax
0x1800104b9  jnz     short loc_1800104C2
0x1800104bb  mov     ebx, 8007000Eh
0x1800104c0  jmp     short loc_1800104E2
0x1800104c2  mov     r9, rdi
0x1800104c5  mov     r8d, 1
0x1800104cb  mov     rdx, rbx
0x1800104ce  mov     rcx, rsi
0x1800104d1  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800104d7  mov     rcx, rdi
0x1800104da  mov     ebx, eax
0x1800104dc  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800104e2  mov     rsi, [rsp+28h+arg_8]
0x1800104e7  mov     eax, ebx
0x1800104e9  mov     rbx, [rsp+28h+arg_0]
0x1800104ee  add     rsp, 20h
0x1800104f2  pop     rdi
0x1800104f3  retn
```
