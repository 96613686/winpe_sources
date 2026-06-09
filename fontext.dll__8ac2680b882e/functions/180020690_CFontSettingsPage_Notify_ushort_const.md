# CFontSettingsPage::Notify(ushort const *)

- ea: `0x180020690`
- end: `0x180020749`
- name: `?Notify@CFontSettingsPage@@UEAAJPEBG@Z`
- size: `185`
- prototype: `__int64 __fastcall(CFontSettingsPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callees

- `0x180020690`
- `0x18002ecb0`
- `0x180032010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadInt` at `0x1800206f7`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x1800206f7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800206aa`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800206aa`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800206d4`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800206d4`

## string_xrefs

- `0x1800206a3`: `ControlPanelNavLinkClicked`
- `0x1800206e8`: `ControlPanelNavLinkClicked`

## pseudocode

```c
__int64 __fastcall CFontSettingsPage::Notify(CFontSettingsPage *this, const unsigned __int16 *a2)
{
  IUnknown *v4; // rcx
  __int64 v5; // rcx
  INT value; // [rsp+40h] [rbp+18h] BYREF
  void *ppvOut; // [rsp+48h] [rbp+20h] BYREF

  if ( StrCmpICW(a2, L"ControlPanelNavLinkClicked") )
  {
    CControlPanelPage::Notify(this, a2);
  }
  else
  {
    v4 = (IUnknown *)*((_QWORD *)this - 1);
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v4,
           (const GUID *const)&SID_PerLayoutPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut) >= 0 )
    {
      value = 0;
      if ( PSPropertyBag_ReadInt((IPropertyBag *)ppvOut, L"ControlPanelNavLinkClicked", &value) >= 0 )
      {
        v5 = *(_QWORD *)(*((_QWORD *)this + 4) + 24LL);
        if ( v5 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 16LL))(v5, (unsigned int)value);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020690  mov     [rsp+arg_0], rbx
0x180020695  push    rdi
0x180020696  sub     rsp, 20h
0x18002069a  mov     rdi, rdx
0x18002069d  mov     rbx, rcx
0x1800206a0  mov     rcx, rdi; pszStr1
0x1800206a3  lea     rdx, pszStr2; "ControlPanelNavLinkClicked"
0x1800206aa  call    cs:__imp_StrCmpICW
0x1800206b0  test    eax, eax
0x1800206b2  jnz     short loc_180020731
0x1800206b4  mov     rcx, [rbx-8]; punk
0x1800206b8  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x1800206bd  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800206c4  mov     [rsp+28h+ppvOut], 0
0x1800206cd  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x1800206d4  call    cs:__imp_IUnknown_QueryService
0x1800206da  test    eax, eax
0x1800206dc  js      short loc_18002073C
0x1800206de  mov     rcx, [rsp+28h+ppvOut]; propBag
0x1800206e3  lea     r8, [rsp+28h+value]; value
0x1800206e8  lea     rdx, pszStr2; "ControlPanelNavLinkClicked"
0x1800206ef  mov     [rsp+28h+value], 0
0x1800206f7  call    cs:__imp_PSPropertyBag_ReadInt
0x1800206fd  test    eax, eax
0x1800206ff  js      short loc_18002071E
0x180020701  mov     rax, [rbx+20h]
0x180020705  mov     rcx, [rax+18h]
0x180020709  test    rcx, rcx
0x18002070c  jz      short loc_18002071E
0x18002070e  mov     rax, [rcx]
0x180020711  mov     edx, [rsp+28h+value]
0x180020715  mov     rax, [rax+10h]
0x180020719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002071e  mov     rcx, [rsp+28h+ppvOut]
0x180020723  mov     rax, [rcx]
0x180020726  mov     rax, [rax+10h]
0x18002072a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072f  jmp     short loc_18002073C
0x180020731  mov     rdx, rdi; unsigned __int16 *
0x180020734  mov     rcx, rbx; this
0x180020737  call    ?Notify@CControlPanelPage@@UEAAJPEBG@Z; CControlPanelPage::Notify(ushort const *)
0x18002073c  mov     rbx, [rsp+28h+arg_0]
0x180020741  xor     eax, eax
0x180020743  add     rsp, 20h
0x180020747  pop     rdi
0x180020748  retn
```
