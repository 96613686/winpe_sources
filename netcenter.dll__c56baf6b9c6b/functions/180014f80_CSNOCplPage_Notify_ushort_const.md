# CSNOCplPage::Notify(ushort const *)

- ea: `0x180014f80`
- end: `0x18001503d`
- name: `?Notify@CSNOCplPage@@UEAAJPEBG@Z`
- size: `189`
- prototype: `__int64 __fastcall(CSNOCplPage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000de90`
- `0x180014f80`
- `0x18001cd68`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014fa8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014fa8`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180014fd3`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180014fd3`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180014ff6`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180014ff6`

## string_xrefs

- `0x180014f98`: `ControlPanelNavLinkClicked`
- `0x180014fe7`: `ControlPanelNavLinkClicked`

## pseudocode

```c
__int64 __fastcall CSNOCplPage::Notify(CSNOCplPage *this, const unsigned __int16 *a2)
{
  IUnknown *v4; // rcx
  LPARAM v5; // rcx
  INT value; // [rsp+50h] [rbp+18h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+20h] BYREF

  if ( CompareStringOrdinal(a2, -1, L"ControlPanelNavLinkClicked", -1, 1) == 2 )
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
        v5 = *((_QWORD *)this + 7);
        if ( v5 )
          CSNOCplCore::OnNavTaskLinkClicked(v5, value);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  else
  {
    CControlPanelPage::Notify(this, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x180014f80  mov     [rsp+arg_0], rbx
0x180014f85  push    rdi
0x180014f86  sub     rsp, 30h
0x180014f8a  mov     rdi, rdx
0x180014f8d  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180014f95  or      edx, 0FFFFFFFFh; cchCount1
0x180014f98  lea     r8, aControlpanelna_0; "ControlPanelNavLinkClicked"
0x180014f9f  mov     rbx, rcx
0x180014fa2  mov     r9d, edx; cchCount2
0x180014fa5  mov     rcx, rdi; lpString1
0x180014fa8  call    cs:__imp_CompareStringOrdinal
0x180014fae  cmp     eax, 2
0x180014fb1  jnz     short loc_180015025
0x180014fb3  mov     rcx, [rbx-8]; punk
0x180014fb7  lea     r9, [rsp+38h+ppvOut]; ppvOut
0x180014fbc  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180014fc3  mov     [rsp+38h+ppvOut], 0
0x180014fcc  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x180014fd3  call    cs:__imp_IUnknown_QueryService
0x180014fd9  test    eax, eax
0x180014fdb  js      short loc_180015030
0x180014fdd  mov     rcx, [rsp+38h+ppvOut]; propBag
0x180014fe2  lea     r8, [rsp+38h+value]; value
0x180014fe7  lea     rdx, aControlpanelna_0; "ControlPanelNavLinkClicked"
0x180014fee  mov     [rsp+38h+value], 0
0x180014ff6  call    cs:__imp_PSPropertyBag_ReadInt
0x180014ffc  test    eax, eax
0x180014ffe  js      short loc_180015012
0x180015000  mov     rcx, [rbx+38h]; lParam
0x180015004  test    rcx, rcx
0x180015007  jz      short loc_180015012
0x180015009  mov     edx, [rsp+38h+value]; int
0x18001500d  call    ?OnNavTaskLinkClicked@CSNOCplCore@@QEAAXH@Z; CSNOCplCore::OnNavTaskLinkClicked(int)
0x180015012  mov     rcx, [rsp+38h+ppvOut]
0x180015017  mov     rax, [rcx]
0x18001501a  mov     rax, [rax+10h]
0x18001501e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015023  jmp     short loc_180015030
0x180015025  mov     rdx, rdi; unsigned __int16 *
0x180015028  mov     rcx, rbx; this
0x18001502b  call    ?Notify@CControlPanelPage@@UEAAJPEBG@Z; CControlPanelPage::Notify(ushort const *)
0x180015030  mov     rbx, [rsp+38h+arg_0]
0x180015035  xor     eax, eax
0x180015037  add     rsp, 30h
0x18001503b  pop     rdi
0x18001503c  retn
```
