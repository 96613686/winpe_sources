# CNavigateButton::_Execute(void)

- ea: `0x18001e16c`
- end: `0x18001e2bd`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18001dda0`

## callees

- `0x180002c2c`
- `0x18001db48`
- `0x18001e16c`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001e1cc`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001e1cc`
- `SHELL32!ShellExecuteExW` at `0x18001e284`
- `SHELL32!ShellExecuteExW` at `0x18001e284`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e28d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e296`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e28d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e296`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001e2b6`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e21a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e23f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e21a`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001e23f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e20e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e233`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e20e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001e233`

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
              (const struct DirectUI::PropertyInfo *)&off_180025950,
              2,
              0);
    String = DirectUI::Value::GetString(Value);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_180025920,
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
0x18001e16c  mov     [rsp-8+arg_0], rbx
0x18001e171  push    rbp
0x18001e172  push    rsi
0x18001e173  push    rdi
0x18001e174  push    r14
0x18001e176  push    r15
0x18001e178  lea     rbp, [rsp-37h]
0x18001e17d  sub     rsp, 90h
0x18001e184  xor     edi, edi
0x18001e186  lea     rdx, [rbp+57h+arg_18]; struct DirectUI::Value **
0x18001e18a  mov     [rbp+57h+arg_18], rdi
0x18001e18e  mov     rbx, rcx
0x18001e191  call    ?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; CNavigateButton::GetShellExecute(DirectUI::Value * *)
0x18001e196  mov     r15, rax
0x18001e199  test    rax, rax
0x18001e19c  jz      loc_18001E29C
0x18001e1a2  cmp     [rax], di
0x18001e1a5  jz      loc_18001E29C
0x18001e1ab  mov     rcx, [rbx+0D8h]; punk
0x18001e1b2  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18001e1b6  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18001e1bd  mov     [rbp+57h+arg_10], rdi
0x18001e1c1  lea     rdx, SID_STopLevelBrowser; guidService
0x18001e1c8  mov     [rbp+57h+ppvOut], rdi
0x18001e1cc  call    cs:__imp_IUnknown_QueryService
0x18001e1d2  test    eax, eax
0x18001e1d4  js      short loc_18001E1FA
0x18001e1d6  mov     rcx, [rbp+57h+ppvOut]
0x18001e1da  lea     rdx, [rbp+57h+arg_10]
0x18001e1de  mov     rax, [rcx]
0x18001e1e1  mov     rax, [rax+18h]
0x18001e1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ea  mov     rcx, [rbp+57h+ppvOut]
0x18001e1ee  mov     rax, [rcx]
0x18001e1f1  mov     rax, [rax+10h]
0x18001e1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1fa  xor     r9d, r9d
0x18001e1fd  lea     rdx, off_180025950; "ShellExecuteVerb"
0x18001e204  mov     rcx, rbx
0x18001e207  lea     esi, [r9+2]
0x18001e20b  mov     r8d, esi
0x18001e20e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001e214  mov     rcx, rax
0x18001e217  mov     r14, rax
0x18001e21a  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18001e220  xor     r9d, r9d
0x18001e223  lea     rdx, off_180025920; "ShellExecuteParams"
0x18001e22a  mov     r8d, esi
0x18001e22d  mov     rcx, rbx
0x18001e230  mov     rdi, rax
0x18001e233  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001e239  mov     rcx, rax
0x18001e23c  mov     rsi, rax
0x18001e23f  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18001e245  xor     edx, edx; Val
0x18001e247  lea     rcx, [rbp+57h+pExecInfo]; void *
0x18001e24b  mov     rbx, rax
0x18001e24e  lea     r8d, [rdx+70h]; Size
0x18001e252  call    memset_0
0x18001e257  mov     rcx, [rbp+57h+arg_10]
0x18001e25b  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x18001e25f  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18001e263  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18001e26a  mov     [rbp+57h+pExecInfo.nShow], 5
0x18001e271  mov     [rbp+57h+pExecInfo.lpFile], r15
0x18001e275  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x18001e279  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x18001e27d  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x18001e284  call    cs:__imp_ShellExecuteExW
0x18001e28a  mov     rcx, r14
0x18001e28d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001e293  mov     rcx, rsi
0x18001e296  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001e29c  mov     rcx, [rbp+57h+arg_18]
0x18001e2a0  mov     rbx, [rsp+0B0h+arg_0]
0x18001e2a8  add     rsp, 90h
0x18001e2af  pop     r15
0x18001e2b1  pop     r14
0x18001e2b3  pop     rdi
0x18001e2b4  pop     rsi
0x18001e2b5  pop     rbp
0x18001e2b6  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
