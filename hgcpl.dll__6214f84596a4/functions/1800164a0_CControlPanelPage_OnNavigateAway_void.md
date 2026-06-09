# CControlPanelPage::OnNavigateAway(void)

- ea: `0x1800164a0`
- end: `0x1800164c9`
- name: `?OnNavigateAway@CControlPanelPage@@UEAAJXZ`
- size: `41`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800164a0`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x1800164bc`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x1800164bc`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::OnNavigateAway(CControlPanelPage *this)
{
  if ( *((_DWORD *)this + 2) )
    IUnknown_ProfferService(*((_QWORD *)this - 1), &IID_IShellSearchTargetServices, 0, (char *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x1800164a0  sub     rsp, 28h
0x1800164a4  lea     r9, [rcx+8]
0x1800164a8  cmp     dword ptr [r9], 0
0x1800164ac  jz      short loc_1800164C2
0x1800164ae  mov     rcx, [rcx-8]
0x1800164b2  lea     rdx, IID_IShellSearchTargetServices
0x1800164b9  xor     r8d, r8d
0x1800164bc  call    cs:__imp_IUnknown_ProfferService
0x1800164c2  xor     eax, eax
0x1800164c4  add     rsp, 28h
0x1800164c8  retn
```
