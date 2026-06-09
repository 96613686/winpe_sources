# CHgCplCore::_GetParentWindow(void)

- ea: `0x18000b8ec`
- end: `0x18000b988`
- name: `?_GetParentWindow@CHgCplCore@@AEAAPEAUHWND__@@XZ`
- size: `156`
- prototype: `HWND __fastcall(CHgCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000b47c`

## callees

- `0x18000b8ec`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000b963`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000b963`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000b951`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000b951`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000b928`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000b928`

## pseudocode

```c
HWND __fastcall CHgCplCore::_GetParentWindow(CHgCplCore *this)
{
  HWND *v1; // rbx
  IUnknown **v2; // rdi
  IUnknown *v3; // rcx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (HWND *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
  {
    v2 = (IUnknown **)((char *)this + 16);
    if ( *((_QWORD *)this + 2)
      || IUnknown_GetSite(
           (IUnknown *)((*((_QWORD *)this + 3) + 208LL) & -(__int64)(*((_QWORD *)this + 3) != 0)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 2) >= 0 )
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
0x18000b8ec  mov     [rsp+arg_8], rbx
0x18000b8f1  push    rdi
0x18000b8f2  sub     rsp, 20h
0x18000b8f6  lea     rbx, [rcx+30h]
0x18000b8fa  cmp     qword ptr [rbx], 0
0x18000b8fe  jnz     short loc_18000B97A
0x18000b900  lea     rdi, [rcx+10h]
0x18000b904  cmp     qword ptr [rdi], 0
0x18000b908  jnz     short loc_18000B932
0x18000b90a  mov     rax, [rcx+18h]
0x18000b90e  mov     r8, rdi; ppv
0x18000b911  lea     rdx, [rax+0D0h]
0x18000b918  neg     rax
0x18000b91b  sbb     rcx, rcx
0x18000b91e  and     rcx, rdx; punk
0x18000b921  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000b928  call    cs:__imp_IUnknown_GetSite
0x18000b92e  test    eax, eax
0x18000b930  js      short loc_18000B97A
0x18000b932  mov     rcx, [rdi]; punk
0x18000b935  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18000b93a  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000b941  mov     [rsp+28h+ppvOut], 0
0x18000b94a  lea     rdx, SID_STopLevelBrowser; guidService
0x18000b951  call    cs:__imp_IUnknown_QueryService
0x18000b957  test    eax, eax
0x18000b959  js      short loc_18000B97A
0x18000b95b  mov     rcx, [rsp+28h+ppvOut]; punk
0x18000b960  mov     rdx, rbx; phwnd
0x18000b963  call    cs:__imp_IUnknown_GetWindow
0x18000b969  mov     rcx, [rsp+28h+ppvOut]
0x18000b96e  mov     rdx, [rcx]
0x18000b971  mov     rax, [rdx+10h]
0x18000b975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97a  mov     rax, [rbx]
0x18000b97d  mov     rbx, [rsp+28h+arg_8]
0x18000b982  add     rsp, 20h
0x18000b986  pop     rdi
0x18000b987  retn
```
