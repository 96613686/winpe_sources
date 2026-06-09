# CNavigateButton::_Execute(void)

- ea: `0x180030684`
- end: `0x1800307d5`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800302c0`

## callees

- `0x180030078`
- `0x180030684`
- `0x18003104a`
- `0x180032010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18003079c`
- `SHELL32!ShellExecuteExW` at `0x18003079c`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800306e4`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800306e4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800307a5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800307ae`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800307a5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800307ae`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800307ce`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030726`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18003074b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180030726`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18003074b`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030732`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030757`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030732`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180030757`

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
              (const struct DirectUI::PropertyInfo *)&off_1800351A0,
              2,
              0);
    String = DirectUI::Value::GetString(Value);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_180035170,
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
0x180030684  mov     [rsp-8+arg_0], rbx
0x180030689  push    rbp
0x18003068a  push    rsi
0x18003068b  push    rdi
0x18003068c  push    r14
0x18003068e  push    r15
0x180030690  lea     rbp, [rsp-37h]
0x180030695  sub     rsp, 90h
0x18003069c  xor     edi, edi
0x18003069e  lea     rdx, [rbp+57h+arg_18]; struct DirectUI::Value **
0x1800306a2  mov     [rbp+57h+arg_18], rdi
0x1800306a6  mov     rbx, rcx
0x1800306a9  call    ?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; CNavigateButton::GetShellExecute(DirectUI::Value * *)
0x1800306ae  mov     r15, rax
0x1800306b1  test    rax, rax
0x1800306b4  jz      loc_1800307B4
0x1800306ba  cmp     [rax], di
0x1800306bd  jz      loc_1800307B4
0x1800306c3  mov     rcx, [rbx+0D8h]; punk
0x1800306ca  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800306ce  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x1800306d5  mov     [rbp+57h+arg_10], rdi
0x1800306d9  lea     rdx, SID_STopLevelBrowser; guidService
0x1800306e0  mov     [rbp+57h+ppvOut], rdi
0x1800306e4  call    cs:__imp_IUnknown_QueryService
0x1800306ea  test    eax, eax
0x1800306ec  js      short loc_180030712
0x1800306ee  mov     rcx, [rbp+57h+ppvOut]
0x1800306f2  lea     rdx, [rbp+57h+arg_10]
0x1800306f6  mov     rax, [rcx]
0x1800306f9  mov     rax, [rax+18h]
0x1800306fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030702  mov     rcx, [rbp+57h+ppvOut]
0x180030706  mov     rax, [rcx]
0x180030709  mov     rax, [rax+10h]
0x18003070d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030712  xor     r9d, r9d
0x180030715  lea     rdx, off_1800351A0; "ShellExecuteVerb"
0x18003071c  mov     rcx, rbx
0x18003071f  lea     esi, [r9+2]
0x180030723  mov     r8d, esi
0x180030726  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18003072c  mov     rcx, rax
0x18003072f  mov     r14, rax
0x180030732  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180030738  xor     r9d, r9d
0x18003073b  lea     rdx, off_180035170; "ShellExecuteParams"
0x180030742  mov     r8d, esi
0x180030745  mov     rcx, rbx
0x180030748  mov     rdi, rax
0x18003074b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030751  mov     rcx, rax
0x180030754  mov     rsi, rax
0x180030757  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18003075d  xor     edx, edx; Val
0x18003075f  lea     rcx, [rbp+57h+pExecInfo]; void *
0x180030763  mov     rbx, rax
0x180030766  lea     r8d, [rdx+70h]; Size
0x18003076a  call    memset_0
0x18003076f  mov     rcx, [rbp+57h+arg_10]
0x180030773  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x180030777  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18003077b  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180030782  mov     [rbp+57h+pExecInfo.nShow], 5
0x180030789  mov     [rbp+57h+pExecInfo.lpFile], r15
0x18003078d  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x180030791  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x180030795  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x18003079c  call    cs:__imp_ShellExecuteExW
0x1800307a2  mov     rcx, r14
0x1800307a5  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800307ab  mov     rcx, rsi
0x1800307ae  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800307b4  mov     rcx, [rbp+57h+arg_18]
0x1800307b8  mov     rbx, [rsp+0B0h+arg_0]
0x1800307c0  add     rsp, 90h
0x1800307c7  pop     r15
0x1800307c9  pop     r14
0x1800307cb  pop     rdi
0x1800307cc  pop     rsi
0x1800307cd  pop     rbp
0x1800307ce  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
