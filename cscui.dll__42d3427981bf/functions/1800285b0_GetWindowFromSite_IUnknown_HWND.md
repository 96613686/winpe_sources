# GetWindowFromSite(IUnknown *,HWND__ * *)

- ea: `0x1800285b0`
- end: `0x180028678`
- name: `?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(IUnknown *punk, HWND *phwnd)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180028d80`
- `0x18002a86c`

## callees

- `0x18000a048`
- `0x1800285b0`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18002864f`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18002864f`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800285f0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002863b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800285f0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002863b`

## pseudocode

```c
__int64 __fastcall GetWindowFromSite(IUnknown *punk, HWND *phwnd)
{
  HRESULT Service; // ebx
  IUnknown *punka; // [rsp+38h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  *phwnd = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         punk,
         &GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6,
         &GUID_00000114_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
  {
    punka = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punka);
    Service = IUnknown_QueryService(
                punk,
                (const GUID *const)&SID_STopLevelBrowser,
                &GUID_00000000_0000_0000_c000_000000000046,
                (void **)&punka);
    if ( Service >= 0 )
      Service = IUnknown_GetWindow(punka, phwnd);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punka);
  }
  else
  {
    Service = (*(__int64 (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, phwnd);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut);
  return (unsigned int)Service;
}

```

## disassembly

```asm
0x1800285b0  mov     [rsp+arg_0], rbx
0x1800285b5  push    rdi
0x1800285b6  sub     rsp, 20h
0x1800285ba  mov     rbx, rcx
0x1800285bd  mov     qword ptr [rdx], 0
0x1800285c4  lea     rcx, [rsp+28h+ppvOut]
0x1800285c9  mov     [rsp+28h+ppvOut], 0
0x1800285d2  mov     rdi, rdx
0x1800285d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800285da  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x1800285df  mov     rcx, rbx; punk
0x1800285e2  lea     r8, _GUID_00000114_0000_0000_c000_000000000046; riid
0x1800285e9  lea     rdx, _GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6; guidService
0x1800285f0  call    cs:__imp_IUnknown_QueryService
0x1800285f6  test    eax, eax
0x1800285f8  js      short loc_180028612
0x1800285fa  mov     rcx, [rsp+28h+ppvOut]
0x1800285ff  mov     rdx, rdi
0x180028602  mov     rax, [rcx]
0x180028605  mov     rax, [rax+18h]
0x180028609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002860e  mov     ebx, eax
0x180028610  jmp     short loc_180028661
0x180028612  lea     rcx, [rsp+28h+punk]
0x180028617  mov     [rsp+28h+punk], 0
0x180028620  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028625  lea     r9, [rsp+28h+punk]; ppvOut
0x18002862a  mov     rcx, rbx; punk
0x18002862d  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180028634  lea     rdx, SID_STopLevelBrowser; guidService
0x18002863b  call    cs:__imp_IUnknown_QueryService
0x180028641  mov     ebx, eax
0x180028643  test    eax, eax
0x180028645  js      short loc_180028657
0x180028647  mov     rcx, [rsp+28h+punk]; punk
0x18002864c  mov     rdx, rdi; phwnd
0x18002864f  call    cs:__imp_IUnknown_GetWindow
0x180028655  mov     ebx, eax
0x180028657  lea     rcx, [rsp+28h+punk]
0x18002865c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028661  lea     rcx, [rsp+28h+ppvOut]
0x180028666  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002866b  mov     eax, ebx
0x18002866d  mov     rbx, [rsp+28h+arg_0]
0x180028672  add     rsp, 20h
0x180028676  pop     rdi
0x180028677  retn
```
