# CNavigateButton::_Navigate(void)

- ea: `0x18001e2c4`
- end: `0x18001e3c6`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `258`
- prototype: `void(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001dda0`

## callees

- `0x18001db80`
- `0x18001e2c4`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18001e37b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001e37b`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001e2f0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001e324`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001e358`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001e2f0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001e324`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001e358`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e39f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e3a8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e39f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e3a8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e3bf`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e2fe`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e332`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e366`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e2fe`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e332`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e366`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e2e7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e31b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e34f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e2e7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e31b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e34f`

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
            (const struct DirectUI::PropertyInfo *)&off_180032118,
            1,
            0);
  if ( Value == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    String = 0;
  else
    String = DirectUI::Value::GetString(Value);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180032148,
         1,
         0);
  if ( v5 == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = DirectUI::Value::GetString(v5);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180032178,
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
0x18001e2c4  push    rbx
0x18001e2c6  push    rbp
0x18001e2c7  push    rsi
0x18001e2c8  push    rdi
0x18001e2c9  push    r12
0x18001e2cb  push    r14
0x18001e2cd  push    r15
0x18001e2cf  sub     rsp, 20h
0x18001e2d3  xor     r9d, r9d
0x18001e2d6  lea     rdx, off_180032118; "navigationtargetroot"
0x18001e2dd  mov     rdi, rcx
0x18001e2e0  lea     ebx, [r9+1]
0x18001e2e4  mov     r8d, ebx
0x18001e2e7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001e2ed  mov     r14, rax
0x18001e2f0  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001e2f6  cmp     r14, rax
0x18001e2f9  jz      short loc_18001E309
0x18001e2fb  mov     rcx, r14
0x18001e2fe  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18001e304  mov     rsi, rax
0x18001e307  jmp     short loc_18001E30B
0x18001e309  xor     esi, esi
0x18001e30b  xor     r9d, r9d
0x18001e30e  lea     rdx, off_180032148; "navigationtargetrelative"
0x18001e315  mov     r8d, ebx
0x18001e318  mov     rcx, rdi
0x18001e31b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001e321  mov     r15, rax
0x18001e324  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001e32a  cmp     r15, rax
0x18001e32d  jz      short loc_18001E33D
0x18001e32f  mov     rcx, r15
0x18001e332  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18001e338  mov     rbp, rax
0x18001e33b  jmp     short loc_18001E33F
0x18001e33d  xor     ebp, ebp
0x18001e33f  xor     r9d, r9d
0x18001e342  lea     rdx, off_180032178; "nobackstack"
0x18001e349  mov     r8d, ebx
0x18001e34c  mov     rcx, rdi
0x18001e34f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001e355  mov     r12, rax
0x18001e358  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001e35e  cmp     r12, rax
0x18001e361  jz      short loc_18001E385
0x18001e363  mov     rcx, r12
0x18001e366  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18001e36c  test    rax, rax
0x18001e36f  jz      short loc_18001E385
0x18001e371  lea     rdx, aTrue; "true"
0x18001e378  mov     rcx, rax; pszStr1
0x18001e37b  call    cs:__imp_StrCmpICW
0x18001e381  test    eax, eax
0x18001e383  jz      short loc_18001E387
0x18001e385  xor     bl, bl
0x18001e387  mov     r8, [rdi+0D8h]; struct IUnknown *
0x18001e38e  mov     r9b, bl; bool
0x18001e391  mov     rdx, rbp; unsigned __int16 *
0x18001e394  mov     rcx, rsi; unsigned __int16 *
0x18001e397  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x18001e39c  mov     rcx, r14
0x18001e39f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001e3a5  mov     rcx, r15
0x18001e3a8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001e3ae  mov     rcx, r12
0x18001e3b1  add     rsp, 20h
0x18001e3b5  pop     r15
0x18001e3b7  pop     r14
0x18001e3b9  pop     r12
0x18001e3bb  pop     rdi
0x18001e3bc  pop     rsi
0x18001e3bd  pop     rbp
0x18001e3be  pop     rbx
0x18001e3bf  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
