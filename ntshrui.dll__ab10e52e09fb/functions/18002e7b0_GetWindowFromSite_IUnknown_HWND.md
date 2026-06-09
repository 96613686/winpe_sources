# GetWindowFromSite(IUnknown *,HWND__ * *)

- ea: `0x18002e7b0`
- end: `0x18002e879`
- name: `?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(IUnknown *punk, HWND *phwnd)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ed20`
- `0x180044690`
- `0x180047af0`
- `0x1800484e0`
- `0x180049228`

## callees

- `0x180008900`
- `0x18002e7b0`
- `0x180078010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18002e7f0`
- `SHCORE!IUnknown_QueryService` at `0x18002e83b`
- `SHCORE!IUnknown_QueryService` at `0x18002e7f0`
- `SHCORE!IUnknown_QueryService` at `0x18002e83b`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18002e84f`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18002e84f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetWindowFromSite(IUnknown *punk, HWND *phwnd)
{
  HRESULT Service; // ebx
  IUnknown *punka; // [rsp+38h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  *phwnd = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         punk,
         &GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6,
         &GUID_00000114_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
  {
    punka = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&punka);
    Service = IUnknown_QueryService(
                punk,
                (const GUID *const)&SID_STopLevelBrowser,
                &GUID_00000000_0000_0000_c000_000000000046,
                (void **)&punka);
    if ( Service >= 0 )
      Service = IUnknown_GetWindow(punka, phwnd);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&punka);
  }
  else
  {
    Service = (*(__int64 (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, phwnd);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  return (unsigned int)Service;
}

```

## disassembly

```asm
0x18002e7b0  mov     [rsp+arg_0], rbx
0x18002e7b5  push    rdi
0x18002e7b6  sub     rsp, 20h
0x18002e7ba  mov     rdi, rdx
0x18002e7bd  mov     rbx, rcx
0x18002e7c0  mov     qword ptr [rdx], 0
0x18002e7c7  mov     [rsp+28h+ppvOut], 0
0x18002e7d0  lea     rcx, [rsp+28h+ppvOut]
0x18002e7d5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002e7da  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18002e7df  lea     r8, _GUID_00000114_0000_0000_c000_000000000046; riid
0x18002e7e6  lea     rdx, _GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6; guidService
0x18002e7ed  mov     rcx, rbx; punk
0x18002e7f0  call    cs:__imp_IUnknown_QueryService
0x18002e7f6  test    eax, eax
0x18002e7f8  js      short loc_18002E812
0x18002e7fa  mov     rcx, [rsp+28h+ppvOut]
0x18002e7ff  mov     rax, [rcx]
0x18002e802  mov     rdx, rdi
0x18002e805  mov     rax, [rax+18h]
0x18002e809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e80e  mov     ebx, eax
0x18002e810  jmp     short loc_18002E862
0x18002e812  mov     [rsp+28h+punk], 0
0x18002e81b  lea     rcx, [rsp+28h+punk]
0x18002e820  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002e825  lea     r9, [rsp+28h+punk]; ppvOut
0x18002e82a  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002e831  lea     rdx, SID_STopLevelBrowser; guidService
0x18002e838  mov     rcx, rbx; punk
0x18002e83b  call    cs:__imp_IUnknown_QueryService
0x18002e841  mov     ebx, eax
0x18002e843  test    eax, eax
0x18002e845  js      short loc_18002E857
0x18002e847  mov     rdx, rdi; phwnd
0x18002e84a  mov     rcx, [rsp+28h+punk]; punk
0x18002e84f  call    cs:__imp_IUnknown_GetWindow
0x18002e855  mov     ebx, eax
0x18002e857  lea     rcx, [rsp+28h+punk]
0x18002e85c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002e861  nop
0x18002e862  lea     rcx, [rsp+28h+ppvOut]
0x18002e867  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002e86c  mov     eax, ebx
0x18002e86e  mov     rbx, [rsp+28h+arg_0]
0x18002e873  add     rsp, 20h
0x18002e877  pop     rdi
0x18002e878  retn
```
