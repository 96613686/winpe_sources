# CNavigateButton::_Navigate(void)

- ea: `0x18001853c`
- end: `0x18001863e`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `258`
- prototype: `void(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180018020`

## callees

- `0x180017e00`
- `0x18001853c`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800185f3`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800185f3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018617`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018620`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018617`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018620`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018637`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001855f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180018593`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800185c7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001855f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180018593`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800185c7`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180018576`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800185aa`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800185de`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180018576`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800185aa`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800185de`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180018568`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001859c`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800185d0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180018568`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001859c`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800185d0`

## pseudocode

```c
void __fastcall CNavigateButton::_Navigate(struct IUnknown **this)
{
  bool v2; // bl
  DirectUI::Value *Value; // r14
  const unsigned __int16 *String; // rsi
  DirectUI::Value *v5; // r15
  const unsigned __int16 *v6; // rbp
  DirectUI::Value *v7; // r12
  const WCHAR *v8; // rax

  v2 = 1;
  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_1800291A8,
            1,
            0);
  if ( Value == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    String = 0;
  else
    String = DirectUI::Value::GetString(Value);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_1800291D8,
         1,
         0);
  if ( v5 == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = DirectUI::Value::GetString(v5);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180029208,
         1,
         0);
  if ( v7 == (DirectUI::Value *)DirectUI::Value::GetUnset()
    || (v8 = DirectUI::Value::GetString(v7)) == 0
    || StrCmpICW(v8, L"true") )
  {
    v2 = 0;
  }
  CNavigateButton::Navigate(String, v6, this[27], v2);
  DirectUI::Value::Release(Value);
  DirectUI::Value::Release(v5);
  DirectUI::Value::Release(v7);
}

```

## disassembly

```asm
0x18001853c  push    rbx
0x18001853e  push    rbp
0x18001853f  push    rsi
0x180018540  push    rdi
0x180018541  push    r12
0x180018543  push    r14
0x180018545  push    r15
0x180018547  sub     rsp, 20h
0x18001854b  xor     r9d, r9d
0x18001854e  lea     rdx, off_1800291A8; "navigationtargetroot"
0x180018555  mov     rdi, rcx
0x180018558  lea     ebx, [r9+1]
0x18001855c  mov     r8d, ebx
0x18001855f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180018565  mov     r14, rax
0x180018568  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001856e  cmp     r14, rax
0x180018571  jz      short loc_180018581
0x180018573  mov     rcx, r14
0x180018576  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18001857c  mov     rsi, rax
0x18001857f  jmp     short loc_180018583
0x180018581  xor     esi, esi
0x180018583  xor     r9d, r9d
0x180018586  lea     rdx, off_1800291D8; "navigationtargetrelative"
0x18001858d  mov     r8d, ebx
0x180018590  mov     rcx, rdi
0x180018593  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180018599  mov     r15, rax
0x18001859c  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800185a2  cmp     r15, rax
0x1800185a5  jz      short loc_1800185B5
0x1800185a7  mov     rcx, r15
0x1800185aa  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800185b0  mov     rbp, rax
0x1800185b3  jmp     short loc_1800185B7
0x1800185b5  xor     ebp, ebp
0x1800185b7  xor     r9d, r9d
0x1800185ba  lea     rdx, off_180029208; "nobackstack"
0x1800185c1  mov     r8d, ebx
0x1800185c4  mov     rcx, rdi
0x1800185c7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800185cd  mov     r12, rax
0x1800185d0  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800185d6  cmp     r12, rax
0x1800185d9  jz      short loc_1800185FD
0x1800185db  mov     rcx, r12
0x1800185de  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800185e4  test    rax, rax
0x1800185e7  jz      short loc_1800185FD
0x1800185e9  lea     rdx, aTrue; "true"
0x1800185f0  mov     rcx, rax; pszStr1
0x1800185f3  call    cs:__imp_StrCmpICW
0x1800185f9  test    eax, eax
0x1800185fb  jz      short loc_1800185FF
0x1800185fd  xor     bl, bl
0x1800185ff  mov     r8, [rdi+0D8h]; struct IUnknown *
0x180018606  mov     r9b, bl; bool
0x180018609  mov     rdx, rbp; unsigned __int16 *
0x18001860c  mov     rcx, rsi; unsigned __int16 *
0x18001860f  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x180018614  mov     rcx, r14
0x180018617  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001861d  mov     rcx, r15
0x180018620  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018626  mov     rcx, r12
0x180018629  add     rsp, 20h
0x18001862d  pop     r15
0x18001862f  pop     r14
0x180018631  pop     r12
0x180018633  pop     rdi
0x180018634  pop     rsi
0x180018635  pop     rbp
0x180018636  pop     rbx
0x180018637  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
