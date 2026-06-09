# CNavigateButton::_Navigate(void)

- ea: `0x180030c24`
- end: `0x180030d26`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `258`
- prototype: `void __fastcall(struct IUnknown **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180030700`

## callees

- `0x1800304e0`
- `0x180030c24`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180030cdb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180030cdb`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030c50`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030c84`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030cb8`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030c50`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030c84`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180030cb8`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030c5e`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030c92`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030cc6`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030c5e`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030c92`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030cc6`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030c47`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030c7b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030caf`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030c47`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030c7b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030caf`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030cff`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030d08`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030cff`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030d08`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030d1f`

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
            (const struct DirectUI::PropertyInfo *)&off_1800451C8,
            1,
            0);
  if ( Value == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    String = 0;
  else
    String = DirectUI::Value::GetString(Value);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_1800451F8,
         1,
         0);
  if ( v5 == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = DirectUI::Value::GetString(v5);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180045228,
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
0x180030c24  push    rbx
0x180030c26  push    rbp
0x180030c27  push    rsi
0x180030c28  push    rdi
0x180030c29  push    r12
0x180030c2b  push    r14
0x180030c2d  push    r15
0x180030c2f  sub     rsp, 20h
0x180030c33  xor     r9d, r9d
0x180030c36  lea     rdx, off_1800451C8; "navigationtargetroot"
0x180030c3d  mov     rdi, rcx
0x180030c40  lea     ebx, [r9+1]
0x180030c44  mov     r8d, ebx
0x180030c47  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030c4d  mov     r14, rax
0x180030c50  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x180030c56  cmp     r14, rax
0x180030c59  jz      short loc_180030C69
0x180030c5b  mov     rcx, r14
0x180030c5e  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030c64  mov     rsi, rax
0x180030c67  jmp     short loc_180030C6B
0x180030c69  xor     esi, esi
0x180030c6b  xor     r9d, r9d
0x180030c6e  lea     rdx, off_1800451F8; "navigationtargetrelative"
0x180030c75  mov     r8d, ebx
0x180030c78  mov     rcx, rdi
0x180030c7b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030c81  mov     r15, rax
0x180030c84  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x180030c8a  cmp     r15, rax
0x180030c8d  jz      short loc_180030C9D
0x180030c8f  mov     rcx, r15
0x180030c92  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030c98  mov     rbp, rax
0x180030c9b  jmp     short loc_180030C9F
0x180030c9d  xor     ebp, ebp
0x180030c9f  xor     r9d, r9d
0x180030ca2  lea     rdx, off_180045228; "nobackstack"
0x180030ca9  mov     r8d, ebx
0x180030cac  mov     rcx, rdi
0x180030caf  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030cb5  mov     r12, rax
0x180030cb8  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x180030cbe  cmp     r12, rax
0x180030cc1  jz      short loc_180030CE5
0x180030cc3  mov     rcx, r12
0x180030cc6  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030ccc  test    rax, rax
0x180030ccf  jz      short loc_180030CE5
0x180030cd1  lea     rdx, aTrue; "true"
0x180030cd8  mov     rcx, rax; pszStr1
0x180030cdb  call    cs:__imp_StrCmpICW
0x180030ce1  test    eax, eax
0x180030ce3  jz      short loc_180030CE7
0x180030ce5  xor     bl, bl
0x180030ce7  mov     r8, [rdi+0D8h]; struct IUnknown *
0x180030cee  mov     r9b, bl; bool
0x180030cf1  mov     rdx, rbp; unsigned __int16 *
0x180030cf4  mov     rcx, rsi; unsigned __int16 *
0x180030cf7  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x180030cfc  mov     rcx, r14
0x180030cff  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180030d05  mov     rcx, r15
0x180030d08  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180030d0e  mov     rcx, r12
0x180030d11  add     rsp, 20h
0x180030d15  pop     r15
0x180030d17  pop     r14
0x180030d19  pop     r12
0x180030d1b  pop     rdi
0x180030d1c  pop     rsi
0x180030d1d  pop     rbp
0x180030d1e  pop     rbx
0x180030d1f  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
