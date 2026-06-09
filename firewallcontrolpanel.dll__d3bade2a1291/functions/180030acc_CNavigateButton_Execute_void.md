# CNavigateButton::_Execute(void)

- ea: `0x180030acc`
- end: `0x180030c1d`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(IUnknown **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180030700`

## callees

- `0x1800304a8`
- `0x180030acc`
- `0x180030e6e`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180030b2c`
- `SHCORE!IUnknown_QueryService` at `0x180030b2c`
- `SHELL32!ShellExecuteExW` at `0x180030be4`
- `SHELL32!ShellExecuteExW` at `0x180030be4`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030b7a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030b9f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030b7a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030b9f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030b6e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030b93`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030b6e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030b93`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030bed`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030bf6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030bed`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030bf6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180030c16`

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
              (const struct DirectUI::PropertyInfo *)&off_180035100,
              2,
              0);
    String = DirectUI::Value::GetString(Value);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_1800350D0,
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
0x180030acc  mov     [rsp-8+arg_0], rbx
0x180030ad1  push    rbp
0x180030ad2  push    rsi
0x180030ad3  push    rdi
0x180030ad4  push    r14
0x180030ad6  push    r15
0x180030ad8  lea     rbp, [rsp-37h]
0x180030add  sub     rsp, 90h
0x180030ae4  xor     edi, edi
0x180030ae6  lea     rdx, [rbp+57h+arg_18]; struct DirectUI::Value **
0x180030aea  mov     [rbp+57h+arg_18], rdi
0x180030aee  mov     rbx, rcx
0x180030af1  call    ?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; CNavigateButton::GetShellExecute(DirectUI::Value * *)
0x180030af6  mov     r15, rax
0x180030af9  test    rax, rax
0x180030afc  jz      loc_180030BFC
0x180030b02  cmp     [rax], di
0x180030b05  jz      loc_180030BFC
0x180030b0b  mov     rcx, [rbx+0D8h]; punk
0x180030b12  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180030b16  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180030b1d  mov     [rbp+57h+arg_10], rdi
0x180030b21  lea     rdx, SID_STopLevelBrowser; guidService
0x180030b28  mov     [rbp+57h+ppvOut], rdi
0x180030b2c  call    cs:__imp_IUnknown_QueryService
0x180030b32  test    eax, eax
0x180030b34  js      short loc_180030B5A
0x180030b36  mov     rcx, [rbp+57h+ppvOut]
0x180030b3a  lea     rdx, [rbp+57h+arg_10]
0x180030b3e  mov     rax, [rcx]
0x180030b41  mov     rax, [rax+18h]
0x180030b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b4a  mov     rcx, [rbp+57h+ppvOut]
0x180030b4e  mov     rax, [rcx]
0x180030b51  mov     rax, [rax+10h]
0x180030b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b5a  xor     r9d, r9d
0x180030b5d  lea     rdx, off_180035100; "ShellExecuteVerb"
0x180030b64  mov     rcx, rbx
0x180030b67  lea     esi, [r9+2]
0x180030b6b  mov     r8d, esi
0x180030b6e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030b74  mov     rcx, rax
0x180030b77  mov     r14, rax
0x180030b7a  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030b80  xor     r9d, r9d
0x180030b83  lea     rdx, off_1800350D0; "ShellExecuteParams"
0x180030b8a  mov     r8d, esi
0x180030b8d  mov     rcx, rbx
0x180030b90  mov     rdi, rax
0x180030b93  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030b99  mov     rcx, rax
0x180030b9c  mov     rsi, rax
0x180030b9f  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030ba5  xor     edx, edx; Val
0x180030ba7  lea     rcx, [rbp+57h+pExecInfo]; void *
0x180030bab  mov     rbx, rax
0x180030bae  lea     r8d, [rdx+70h]; Size
0x180030bb2  call    memset_0
0x180030bb7  mov     rcx, [rbp+57h+arg_10]
0x180030bbb  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x180030bbf  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180030bc3  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180030bca  mov     [rbp+57h+pExecInfo.nShow], 5
0x180030bd1  mov     [rbp+57h+pExecInfo.lpFile], r15
0x180030bd5  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x180030bd9  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x180030bdd  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x180030be4  call    cs:__imp_ShellExecuteExW
0x180030bea  mov     rcx, r14
0x180030bed  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180030bf3  mov     rcx, rsi
0x180030bf6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180030bfc  mov     rcx, [rbp+57h+arg_18]
0x180030c00  mov     rbx, [rsp+0B0h+arg_0]
0x180030c08  add     rsp, 90h
0x180030c0f  pop     r15
0x180030c11  pop     r14
0x180030c13  pop     rdi
0x180030c14  pop     rsi
0x180030c15  pop     rbp
0x180030c16  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
