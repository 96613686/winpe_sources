# CNavigateButton::_Execute(void)

- ea: `0x1800183e4`
- end: `0x180018535`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180018020`

## callees

- `0x180017dc8`
- `0x1800183e4`
- `0x180018a52`
- `0x18001a010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x1800184fc`
- `SHELL32!ShellExecuteExW` at `0x1800184fc`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180018444`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180018444`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018505`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001850e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180018505`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001850e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001852e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180018486`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800184ab`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180018486`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800184ab`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180018492`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800184b7`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180018492`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800184b7`

## pseudocode

```c
void __fastcall CNavigateButton::_Execute(IUnknown **this)
{
  const unsigned __int16 *ShellExecute; // rax
  const WCHAR *v3; // r15
  IUnknown *v4; // rcx
  DirectUI::Value *Value; // r14
  const WCHAR *String; // rdi
  DirectUI::Value *v7; // rsi
  const WCHAR *v8; // rbx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-39h] BYREF
  void *ppvOut; // [rsp+C8h] [rbp+6Fh] BYREF
  HWND v11; // [rsp+D0h] [rbp+77h] BYREF
  struct DirectUI::Value *v12; // [rsp+D8h] [rbp+7Fh] BYREF

  v12 = 0;
  ShellExecute = CNavigateButton::GetShellExecute((CNavigateButton *)this, &v12);
  v3 = ShellExecute;
  if ( ShellExecute && *ShellExecute )
  {
    v4 = this[27];
    v11 = 0;
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v4,
           (const GUID *const)&SID_STopLevelBrowser,
           &GUID_000214e2_0000_0000_c000_000000000046,
           &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v11);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    Value = DirectUI::Element::GetValue(
              (DirectUI::Element *)this,
              (const struct DirectUI::PropertyInfo *)&off_18001C1C0,
              2,
              0);
    String = DirectUI::Value::GetString(Value);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_18001C190,
           2,
           0);
    v8 = DirectUI::Value::GetString(v7);
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.hwnd = v11;
    pExecInfo.cbSize = 112;
    pExecInfo.nShow = 5;
    pExecInfo.lpFile = v3;
    pExecInfo.lpVerb = String;
    pExecInfo.lpParameters = v8;
    pExecInfo.fMask = 67109388;
    ShellExecuteExW(&pExecInfo);
    DirectUI::Value::Release(Value);
    DirectUI::Value::Release(v7);
  }
  DirectUI::Value::Release(v12);
}

```

## disassembly

```asm
0x1800183e4  mov     [rsp-8+arg_0], rbx
0x1800183e9  push    rbp
0x1800183ea  push    rsi
0x1800183eb  push    rdi
0x1800183ec  push    r14
0x1800183ee  push    r15
0x1800183f0  lea     rbp, [rsp-37h]
0x1800183f5  sub     rsp, 90h
0x1800183fc  xor     edi, edi
0x1800183fe  lea     rdx, [rbp+57h+arg_18]; struct DirectUI::Value **
0x180018402  mov     [rbp+57h+arg_18], rdi
0x180018406  mov     rbx, rcx
0x180018409  call    ?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; CNavigateButton::GetShellExecute(DirectUI::Value * *)
0x18001840e  mov     r15, rax
0x180018411  test    rax, rax
0x180018414  jz      loc_180018514
0x18001841a  cmp     [rax], di
0x18001841d  jz      loc_180018514
0x180018423  mov     rcx, [rbx+0D8h]; punk
0x18001842a  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18001842e  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180018435  mov     [rbp+57h+arg_10], rdi
0x180018439  lea     rdx, SID_STopLevelBrowser; guidService
0x180018440  mov     [rbp+57h+ppvOut], rdi
0x180018444  call    cs:__imp_IUnknown_QueryService
0x18001844a  test    eax, eax
0x18001844c  js      short loc_180018472
0x18001844e  mov     rcx, [rbp+57h+ppvOut]
0x180018452  lea     rdx, [rbp+57h+arg_10]
0x180018456  mov     rax, [rcx]
0x180018459  mov     rax, [rax+18h]
0x18001845d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018462  mov     rcx, [rbp+57h+ppvOut]
0x180018466  mov     rax, [rcx]
0x180018469  mov     rax, [rax+10h]
0x18001846d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018472  xor     r9d, r9d
0x180018475  lea     rdx, off_18001C1C0; "ShellExecuteVerb"
0x18001847c  mov     rcx, rbx
0x18001847f  lea     esi, [r9+2]
0x180018483  mov     r8d, esi
0x180018486  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001848c  mov     rcx, rax
0x18001848f  mov     r14, rax
0x180018492  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180018498  xor     r9d, r9d
0x18001849b  lea     rdx, off_18001C190; "ShellExecuteParams"
0x1800184a2  mov     r8d, esi
0x1800184a5  mov     rcx, rbx
0x1800184a8  mov     rdi, rax
0x1800184ab  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800184b1  mov     rcx, rax
0x1800184b4  mov     rsi, rax
0x1800184b7  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800184bd  xor     edx, edx; Val
0x1800184bf  lea     rcx, [rbp+57h+pExecInfo]; void *
0x1800184c3  mov     rbx, rax
0x1800184c6  lea     r8d, [rdx+70h]; Size
0x1800184ca  call    memset_0
0x1800184cf  mov     rcx, [rbp+57h+arg_10]
0x1800184d3  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x1800184d7  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x1800184db  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x1800184e2  mov     [rbp+57h+pExecInfo.nShow], 5
0x1800184e9  mov     [rbp+57h+pExecInfo.lpFile], r15
0x1800184ed  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x1800184f1  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x1800184f5  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x1800184fc  call    cs:__imp_ShellExecuteExW
0x180018502  mov     rcx, r14
0x180018505  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001850b  mov     rcx, rsi
0x18001850e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018514  mov     rcx, [rbp+57h+arg_18]
0x180018518  mov     rbx, [rsp+0B0h+arg_0]
0x180018520  add     rsp, 90h
0x180018527  pop     r15
0x180018529  pop     r14
0x18001852b  pop     rdi
0x18001852c  pop     rsi
0x18001852d  pop     rbp
0x18001852e  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
