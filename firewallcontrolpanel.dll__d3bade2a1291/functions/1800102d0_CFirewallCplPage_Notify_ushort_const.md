# CFirewallCplPage::Notify(ushort const *)

- ea: `0x1800102d0`
- end: `0x180010393`
- name: `?Notify@CFirewallCplPage@@UEAAJPEBG@Z`
- size: `195`
- prototype: `__int64 __fastcall(CFirewallCplPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800102d0`
- `0x18002fd30`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800102fb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800102fb`
- `SHCORE!IUnknown_QueryService` at `0x18001031c`
- `SHCORE!IUnknown_QueryService` at `0x18001031c`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180010339`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180010339`

## string_xrefs

- `0x1800102f4`: `ControlPanelNavLinkClicked`
- `0x180010332`: `ControlPanelNavLinkClicked`

## pseudocode

```c
__int64 __fastcall CFirewallCplPage::Notify(CFirewallCplPage *this, const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rcx
  INT value; // [rsp+40h] [rbp+18h] BYREF
  void *ppvOut; // [rsp+48h] [rbp+20h] BYREF

  value = 0;
  ppvOut = 0;
  if ( StrCmpICW(a2, L"ControlPanelNavLinkClicked") )
  {
    return (unsigned int)CControlPanelPage::Notify(this, a2);
  }
  else
  {
    v4 = IUnknown_QueryService(
           *((IUnknown **)this - 1),
           (const GUID *const)&SID_PerLayoutPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut);
    if ( v4 >= 0 )
    {
      v4 = PSPropertyBag_ReadInt((IPropertyBag *)ppvOut, L"ControlPanelNavLinkClicked", &value);
      if ( v4 >= 0 )
      {
        v4 = 0;
        v5 = *(_QWORD *)(*((_QWORD *)this + 7) + 32LL);
        if ( v5 )
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, (unsigned int)value);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800102d0  mov     [rsp+arg_0], rbx
0x1800102d5  push    rdi
0x1800102d6  sub     rsp, 20h
0x1800102da  mov     rbx, rdx
0x1800102dd  mov     [rsp+28h+value], 0
0x1800102e5  mov     rdi, rcx
0x1800102e8  mov     [rsp+28h+ppvOut], 0
0x1800102f1  mov     rcx, rbx; pszStr1
0x1800102f4  lea     rdx, pszStr2; "ControlPanelNavLinkClicked"
0x1800102fb  call    cs:__imp_StrCmpICW
0x180010301  test    eax, eax
0x180010303  jnz     short loc_180010379
0x180010305  mov     rcx, [rdi-8]; punk
0x180010309  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18001030e  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180010315  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x18001031c  call    cs:__imp_IUnknown_QueryService
0x180010322  mov     ebx, eax
0x180010324  test    eax, eax
0x180010326  js      short loc_180010386
0x180010328  mov     rcx, [rsp+28h+ppvOut]; propBag
0x18001032d  lea     r8, [rsp+28h+value]; value
0x180010332  lea     rdx, pszStr2; "ControlPanelNavLinkClicked"
0x180010339  call    cs:__imp_PSPropertyBag_ReadInt
0x18001033f  mov     ebx, eax
0x180010341  test    eax, eax
0x180010343  js      short loc_180010366
0x180010345  mov     rax, [rdi+38h]
0x180010349  xor     ebx, ebx
0x18001034b  mov     rcx, [rax+20h]
0x18001034f  test    rcx, rcx
0x180010352  jz      short loc_180010366
0x180010354  mov     rax, [rcx]
0x180010357  mov     edx, [rsp+28h+value]
0x18001035b  mov     rax, [rax+18h]
0x18001035f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010364  mov     ebx, eax
0x180010366  mov     rcx, [rsp+28h+ppvOut]
0x18001036b  mov     rax, [rcx]
0x18001036e  mov     rax, [rax+10h]
0x180010372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010377  jmp     short loc_180010386
0x180010379  mov     rdx, rbx; unsigned __int16 *
0x18001037c  mov     rcx, rdi; this
0x18001037f  call    ?Notify@CControlPanelPage@@UEAAJPEBG@Z; CControlPanelPage::Notify(ushort const *)
0x180010384  mov     ebx, eax
0x180010386  mov     eax, ebx
0x180010388  mov     rbx, [rsp+28h+arg_0]
0x18001038d  add     rsp, 20h
0x180010391  pop     rdi
0x180010392  retn
```
