# COfflinePropSheetExt::_GetCscService(IOfflineFilesService * *)

- ea: `0x1800151d0`
- end: `0x180015289`
- name: `?_GetCscService@COfflinePropSheetExt@@AEAAJPEAPEAUIOfflineFilesService@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(COfflinePropSheetExt *this, IUnknown **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016bd0`
- `0x180021398`

## callees

- `0x1800151d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001524b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001524b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015210`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015210`

## pseudocode

```c
__int64 __fastcall COfflinePropSheetExt::_GetCscService(COfflinePropSheetExt *this, IUnknown **a2)
{
  HRESULT Instance; // ebx
  IUnknown *v4; // rcx
  IUnknown *pProxy; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  pProxy = 0;
  Instance = CoCreateInstance(
               &CLSID_OfflineFilesService,
               0,
               0x4015u,
               &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
               (LPVOID *)&pProxy);
  if ( Instance >= 0 )
  {
    Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 3u, 0, 0);
    if ( Instance >= 0 )
    {
      v4 = pProxy;
      *a2 = pProxy;
      ((void (__fastcall *)(IUnknown *))v4->lpVtbl->AddRef)(v4);
    }
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800151d0  mov     r11, rsp
0x1800151d3  mov     [r11+10h], rbx
0x1800151d7  mov     [r11+8], rcx
0x1800151db  push    rdi
0x1800151dc  sub     rsp, 40h
0x1800151e0  mov     rdi, rdx
0x1800151e3  mov     qword ptr [rdx], 0
0x1800151ea  lea     rax, [r11+8]
0x1800151ee  mov     qword ptr [r11+8], 0
0x1800151f6  xor     edx, edx; pUnkOuter
0x1800151f8  mov     [r11-28h], rax
0x1800151fc  lea     r9, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce; riid
0x180015203  mov     r8d, 4015h; dwClsContext
0x180015209  lea     rcx, CLSID_OfflineFilesService; rclsid
0x180015210  call    cs:__imp_CoCreateInstance
0x180015216  mov     ebx, eax
0x180015218  test    eax, eax
0x18001521a  js      short loc_18001527C
0x18001521c  mov     rcx, [rsp+48h+pProxy]; pProxy
0x180015221  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180015224  mov     [rsp+48h+dwCapabilities], 0; dwCapabilities
0x18001522c  mov     r8d, edx; dwAuthzSvc
0x18001522f  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180015238  xor     r9d, r9d; pServerPrincName
0x18001523b  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180015243  mov     [rsp+48h+dwAuthnLevel], 6; dwAuthnLevel
0x18001524b  call    cs:__imp_CoSetProxyBlanket
0x180015251  mov     ebx, eax
0x180015253  test    eax, eax
0x180015255  js      short loc_18001526B
0x180015257  mov     rcx, [rsp+48h+pProxy]
0x18001525c  mov     [rdi], rcx
0x18001525f  mov     rax, [rcx]
0x180015262  mov     rax, [rax+8]
0x180015266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001526b  mov     rcx, [rsp+48h+pProxy]
0x180015270  mov     rax, [rcx]
0x180015273  mov     rax, [rax+10h]
0x180015277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001527c  mov     eax, ebx
0x18001527e  mov     rbx, [rsp+48h+arg_8]
0x180015283  add     rsp, 40h
0x180015287  pop     rdi
0x180015288  retn
```
