# Conflict_GetCscService(IOfflineFilesService * *)

- ea: `0x18001c5d0`
- end: `0x18001c6ef`
- name: `?Conflict_GetCscService@@YAJPEAPEAUIOfflineFilesService@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct IOfflineFilesService **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c058`
- `0x18001c3d8`
- `0x18001dd30`
- `0x18001e58c`
- `0x18001eb48`

## callees

- `0x18001101c`
- `0x18001c5d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c64b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c64b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c60c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c60c`

## pseudocode

```c
__int64 __fastcall Conflict_GetCscService(IUnknown **a1)
{
  HRESULT Instance; // ebx
  IUnknown *v3; // rcx
  IUnknown *pProxy; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  pProxy = 0;
  Instance = CoCreateInstance(
               &CLSID_OfflineFilesService,
               0,
               0x4015u,
               &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
               (LPVOID *)&pProxy);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids,
        (unsigned int)Instance);
    }
  }
  else
  {
    Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 6u, 3u, 0, 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids,
          (unsigned int)Instance);
      }
    }
    else
    {
      v3 = pProxy;
      *a1 = pProxy;
      ((void (__fastcall *)(IUnknown *))v3->lpVtbl->AddRef)(v3);
    }
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001c5d0  mov     r11, rsp
0x18001c5d3  mov     [r11+10h], rbx
0x18001c5d7  push    rdi
0x18001c5d8  sub     rsp, 40h
0x18001c5dc  mov     rdi, rcx
0x18001c5df  mov     qword ptr [rcx], 0
0x18001c5e6  lea     rax, [r11+8]
0x18001c5ea  mov     qword ptr [r11+8], 0
0x18001c5f2  lea     rcx, CLSID_OfflineFilesService; rclsid
0x18001c5f9  mov     [r11-28h], rax
0x18001c5fd  lea     r9, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce; riid
0x18001c604  xor     edx, edx; pUnkOuter
0x18001c606  mov     r8d, 4015h; dwClsContext
0x18001c60c  call    cs:__imp_CoCreateInstance
0x18001c612  mov     ebx, eax
0x18001c614  test    eax, eax
0x18001c616  js      loc_18001C6B1
0x18001c61c  mov     rcx, [rsp+48h+pProxy]; pProxy
0x18001c621  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001c624  mov     [rsp+48h+dwCapabilities], 0; dwCapabilities
0x18001c62c  mov     r8d, edx; dwAuthzSvc
0x18001c62f  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001c638  xor     r9d, r9d; pServerPrincName
0x18001c63b  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18001c643  mov     [rsp+48h+dwAuthnLevel], 6; dwAuthnLevel
0x18001c64b  call    cs:__imp_CoSetProxyBlanket
0x18001c651  mov     ebx, eax
0x18001c653  test    eax, eax
0x18001c655  js      short loc_18001C66D
0x18001c657  mov     rcx, [rsp+48h+pProxy]
0x18001c65c  mov     [rdi], rcx
0x18001c65f  mov     rax, [rcx]
0x18001c662  mov     rax, [rax+8]
0x18001c666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c66b  jmp     short loc_18001C69E
0x18001c66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c674  lea     rax, WPP_GLOBAL_Control
0x18001c67b  cmp     rcx, rax
0x18001c67e  jz      short loc_18001C69E
0x18001c680  test    byte ptr [rcx+1Ch], 2
0x18001c684  jz      short loc_18001C69E
0x18001c686  mov     rcx, [rcx+10h]
0x18001c68a  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001c691  mov     edx, 44h ; 'D'
0x18001c696  mov     r9d, ebx
0x18001c699  call    WPP_SF_d
0x18001c69e  mov     rcx, [rsp+48h+pProxy]
0x18001c6a3  mov     rax, [rcx]
0x18001c6a6  mov     rax, [rax+10h]
0x18001c6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6af  jmp     short loc_18001C6E2
0x18001c6b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6b8  lea     rax, WPP_GLOBAL_Control
0x18001c6bf  cmp     rcx, rax
0x18001c6c2  jz      short loc_18001C6E2
0x18001c6c4  test    byte ptr [rcx+1Ch], 2
0x18001c6c8  jz      short loc_18001C6E2
0x18001c6ca  mov     rcx, [rcx+10h]
0x18001c6ce  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001c6d5  mov     edx, 45h ; 'E'
0x18001c6da  mov     r9d, ebx
0x18001c6dd  call    WPP_SF_d
0x18001c6e2  mov     eax, ebx
0x18001c6e4  mov     rbx, [rsp+48h+arg_8]
0x18001c6e9  add     rsp, 40h
0x18001c6ed  pop     rdi
0x18001c6ee  retn
```
