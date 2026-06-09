# CNavigateButton::_Navigate(void)

- ea: `0x1800307dc`
- end: `0x1800308de`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `258`
- prototype: `void(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800302c0`

## callees

- `0x1800300b0`
- `0x1800307dc`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180030893`
- `SHLWAPI!__imp_StrCmpICW` at `0x180030893`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800308b7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800308c0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800308b7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800308c0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800308d7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800307ff`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030833`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030867`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800307ff`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030833`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030867`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030816`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18003084a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18003087e`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030816`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18003084a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18003087e`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030808`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18003083c`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030870`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030808`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18003083c`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030870`

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
            (const struct DirectUI::PropertyInfo *)&off_1800463B0,
            1,
            0);
  if ( Value == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    String = 0;
  else
    String = DirectUI::Value::GetString(Value);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_1800463E0,
         1,
         0);
  if ( v5 == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = DirectUI::Value::GetString(v5);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180046410,
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
0x1800307dc  push    rbx
0x1800307de  push    rbp
0x1800307df  push    rsi
0x1800307e0  push    rdi
0x1800307e1  push    r12
0x1800307e3  push    r14
0x1800307e5  push    r15
0x1800307e7  sub     rsp, 20h
0x1800307eb  xor     r9d, r9d
0x1800307ee  lea     rdx, off_1800463B0; "navigationtargetroot"
0x1800307f5  mov     rdi, rcx
0x1800307f8  lea     ebx, [r9+1]
0x1800307fc  mov     r8d, ebx
0x1800307ff  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030805  mov     r14, rax
0x180030808  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18003080e  cmp     r14, rax
0x180030811  jz      short loc_180030821
0x180030813  mov     rcx, r14
0x180030816  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18003081c  mov     rsi, rax
0x18003081f  jmp     short loc_180030823
0x180030821  xor     esi, esi
0x180030823  xor     r9d, r9d
0x180030826  lea     rdx, off_1800463E0; "navigationtargetrelative"
0x18003082d  mov     r8d, ebx
0x180030830  mov     rcx, rdi
0x180030833  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030839  mov     r15, rax
0x18003083c  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x180030842  cmp     r15, rax
0x180030845  jz      short loc_180030855
0x180030847  mov     rcx, r15
0x18003084a  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030850  mov     rbp, rax
0x180030853  jmp     short loc_180030857
0x180030855  xor     ebp, ebp
0x180030857  xor     r9d, r9d
0x18003085a  lea     rdx, off_180046410; "nobackstack"
0x180030861  mov     r8d, ebx
0x180030864  mov     rcx, rdi
0x180030867  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18003086d  mov     r12, rax
0x180030870  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x180030876  cmp     r12, rax
0x180030879  jz      short loc_18003089D
0x18003087b  mov     rcx, r12
0x18003087e  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030884  test    rax, rax
0x180030887  jz      short loc_18003089D
0x180030889  lea     rdx, aTrue; "true"
0x180030890  mov     rcx, rax; pszStr1
0x180030893  call    cs:__imp_StrCmpICW
0x180030899  test    eax, eax
0x18003089b  jz      short loc_18003089F
0x18003089d  xor     bl, bl
0x18003089f  mov     r8, [rdi+0D8h]; struct IUnknown *
0x1800308a6  mov     r9b, bl; bool
0x1800308a9  mov     rdx, rbp; unsigned __int16 *
0x1800308ac  mov     rcx, rsi; unsigned __int16 *
0x1800308af  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x1800308b4  mov     rcx, r14
0x1800308b7  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800308bd  mov     rcx, r15
0x1800308c0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800308c6  mov     rcx, r12
0x1800308c9  add     rsp, 20h
0x1800308cd  pop     r15
0x1800308cf  pop     r14
0x1800308d1  pop     r12
0x1800308d3  pop     rdi
0x1800308d4  pop     rsi
0x1800308d5  pop     rbp
0x1800308d6  pop     rbx
0x1800308d7  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
