# CSNOCplCore::GetParentWindow(void)

- ea: `0x18000ae44`
- end: `0x18000aef7`
- name: `?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ`
- size: `179`
- prototype: `HWND __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800099fc`
- `0x180009aec`
- `0x18000d2e4`
- `0x18000db9c`
- `0x18000dd74`
- `0x18000e564`

## callees

- `0x18000ae44`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000aed2`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000aed2`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000aebb`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000aebb`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000ae8d`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000ae8d`

## pseudocode

```c
HWND __fastcall CSNOCplCore::GetParentWindow(CSNOCplCore *this)
{
  HWND *v1; // rbx
  IUnknown **v2; // rdi
  IUnknown *v3; // rcx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (HWND *)((char *)this + 336);
  if ( !*((_QWORD *)this + 42) )
  {
    v2 = (IUnknown **)((char *)this + 344);
    if ( *((_QWORD *)this + 43)
      || IUnknown_GetSite(
           (IUnknown *)((*((_QWORD *)this + 41) + 208LL) & -(__int64)(*((_QWORD *)this + 41) != 0)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 43) >= 0 )
    {
      v3 = *v2;
      if ( *v2 )
      {
        ppvOut = 0;
        if ( IUnknown_QueryService(
               v3,
               (const GUID *const)&SID_STopLevelBrowser,
               &GUID_00000000_0000_0000_c000_000000000046,
               &ppvOut) >= 0 )
        {
          if ( ppvOut )
          {
            IUnknown_GetWindow((IUnknown *)ppvOut, v1);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          }
        }
      }
    }
  }
  return *v1;
}

```

## disassembly

```asm
0x18000ae44  mov     [rsp+arg_8], rbx
0x18000ae49  push    rdi
0x18000ae4a  sub     rsp, 20h
0x18000ae4e  lea     rbx, [rcx+150h]
0x18000ae55  cmp     qword ptr [rbx], 0
0x18000ae59  jnz     loc_18000AEE9
0x18000ae5f  lea     rdi, [rcx+158h]
0x18000ae66  cmp     qword ptr [rdi], 0
0x18000ae6a  jnz     short loc_18000AE97
0x18000ae6c  mov     rax, [rcx+148h]
0x18000ae73  mov     r8, rdi; ppv
0x18000ae76  lea     rdx, [rax+0D0h]
0x18000ae7d  neg     rax
0x18000ae80  sbb     rcx, rcx
0x18000ae83  and     rcx, rdx; punk
0x18000ae86  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000ae8d  call    cs:__imp_IUnknown_GetSite
0x18000ae93  test    eax, eax
0x18000ae95  js      short loc_18000AEE9
0x18000ae97  mov     rcx, [rdi]; punk
0x18000ae9a  test    rcx, rcx
0x18000ae9d  jz      short loc_18000AEE9
0x18000ae9f  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18000aea4  mov     [rsp+28h+ppvOut], 0
0x18000aead  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000aeb4  lea     rdx, SID_STopLevelBrowser; guidService
0x18000aebb  call    cs:__imp_IUnknown_QueryService
0x18000aec1  test    eax, eax
0x18000aec3  js      short loc_18000AEE9
0x18000aec5  mov     rcx, [rsp+28h+ppvOut]; punk
0x18000aeca  test    rcx, rcx
0x18000aecd  jz      short loc_18000AEE9
0x18000aecf  mov     rdx, rbx; phwnd
0x18000aed2  call    cs:__imp_IUnknown_GetWindow
0x18000aed8  mov     rcx, [rsp+28h+ppvOut]
0x18000aedd  mov     rdx, [rcx]
0x18000aee0  mov     rax, [rdx+10h]
0x18000aee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee9  mov     rax, [rbx]
0x18000aeec  mov     rbx, [rsp+28h+arg_8]
0x18000aef1  add     rsp, 20h
0x18000aef5  pop     rdi
0x18000aef6  retn
```
