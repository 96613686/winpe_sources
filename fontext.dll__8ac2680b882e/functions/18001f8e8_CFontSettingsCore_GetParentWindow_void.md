# CFontSettingsCore::_GetParentWindow(void)

- ea: `0x18001f8e8`
- end: `0x18001f984`
- name: `?_GetParentWindow@CFontSettingsCore@@AEAAPEAUHWND__@@XZ`
- size: `156`
- prototype: `HWND __fastcall(CFontSettingsCore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18001f744`

## callees

- `0x18001f8e8`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18001f95f`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18001f95f`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001f94d`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001f94d`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18001f924`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18001f924`

## pseudocode

```c
HWND __fastcall CFontSettingsCore::_GetParentWindow(CFontSettingsCore *this)
{
  HWND *v1; // rbx
  IUnknown **v2; // rdi
  IUnknown *v3; // rcx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (HWND *)((char *)this + 32);
  if ( !*((_QWORD *)this + 4) )
  {
    v2 = (IUnknown **)((char *)this + 8);
    if ( !*((_QWORD *)this + 1)
      && IUnknown_GetSite(
           (IUnknown *)((*((_QWORD *)this + 2) + 208LL) & -(__int64)(*((_QWORD *)this + 2) != 0)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 1) >= 0 )
    {
      v3 = *v2;
      ppvOut = 0;
      if ( IUnknown_QueryService(
             v3,
             (const GUID *const)&SID_STopLevelBrowser,
             &GUID_00000000_0000_0000_c000_000000000046,
             &ppvOut) >= 0 )
      {
        IUnknown_GetWindow((IUnknown *)ppvOut, v1);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
  }
  return *v1;
}

```

## disassembly

```asm
0x18001f8e8  mov     [rsp+arg_8], rbx
0x18001f8ed  push    rdi
0x18001f8ee  sub     rsp, 20h
0x18001f8f2  lea     rbx, [rcx+20h]
0x18001f8f6  cmp     qword ptr [rbx], 0
0x18001f8fa  jnz     short loc_18001F976
0x18001f8fc  lea     rdi, [rcx+8]
0x18001f900  cmp     qword ptr [rdi], 0
0x18001f904  jnz     short loc_18001F976
0x18001f906  mov     rax, [rcx+10h]
0x18001f90a  mov     r8, rdi; ppv
0x18001f90d  lea     rdx, [rax+0D0h]
0x18001f914  neg     rax
0x18001f917  sbb     rcx, rcx
0x18001f91a  and     rcx, rdx; punk
0x18001f91d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001f924  call    cs:__imp_IUnknown_GetSite
0x18001f92a  test    eax, eax
0x18001f92c  js      short loc_18001F976
0x18001f92e  mov     rcx, [rdi]; punk
0x18001f931  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18001f936  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001f93d  mov     [rsp+28h+ppvOut], 0
0x18001f946  lea     rdx, SID_STopLevelBrowser; guidService
0x18001f94d  call    cs:__imp_IUnknown_QueryService
0x18001f953  test    eax, eax
0x18001f955  js      short loc_18001F976
0x18001f957  mov     rcx, [rsp+28h+ppvOut]; punk
0x18001f95c  mov     rdx, rbx; phwnd
0x18001f95f  call    cs:__imp_IUnknown_GetWindow
0x18001f965  mov     rcx, [rsp+28h+ppvOut]
0x18001f96a  mov     rdx, [rcx]
0x18001f96d  mov     rax, [rdx+10h]
0x18001f971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f976  mov     rax, [rbx]
0x18001f979  mov     rbx, [rsp+28h+arg_8]
0x18001f97e  add     rsp, 20h
0x18001f982  pop     rdi
0x18001f983  retn
```
