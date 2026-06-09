# RdpLocationHandler::CreateLocationOverrideManager(ILocationOverride * *)

- ea: `0x140029204`
- end: `0x1400293a4`
- name: `?CreateLocationOverrideManager@RdpLocationHandler@@AEAAJPEAPEAUILocationOverride@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(RdpLocationHandler *__hidden this, struct ILocationOverride **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002a6dc`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x140029204`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002923d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002923d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1400292b9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1400292b9`

## string_xrefs

- `0x14002927e`: `CoCreateInstance(CLSID_LocationManager, IID_ILocationManager) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RdpLocationHandler::CreateLocationOverrideManager(
        RdpLocationHandler *this,
        struct ILocationOverride **a2)
{
  HRESULT Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  IUnknown *v7; // rcx
  __int64 dwImpLevel; // [rsp+28h] [rbp-20h]
  IUnknown *pProxy; // [rsp+50h] [rbp+8h] BYREF

  pProxy = 0;
  Instance = CoCreateInstance(
               &GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd,
               0,
               0x100004u,
               &GUID_3d0423b1_bbd4_4c4a_8f20_da15228e0f3d,
               (LPVOID *)&pProxy);
  if ( Instance >= 0 )
  {
    Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct ILocationOverride **))pProxy->lpVtbl->QueryInterface)(
                   pProxy,
                   &GUID_36205546_1ab7_4714_a3e9_e874233670db,
                   a2);
      if ( Instance < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 70;
        v6 = "QueryInterface(IID_ILocationOverride) failed!";
        goto LABEL_16;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 69;
      v6 = "CoSetProxyBlanket failed!";
      goto LABEL_16;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 68;
    v6 = "CoCreateInstance(CLSID_LocationManager, IID_ILocationManager) failed!";
LABEL_16:
    LODWORD(dwImpLevel) = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)&WPP_b9c789bf6143327f63d9bfd65da02f41_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6,
      dwImpLevel);
  }
  v7 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140029204  mov     r11, rsp
0x140029207  mov     [r11+10h], rbx
0x14002920b  mov     [r11+8], rcx
0x14002920f  push    rdi
0x140029210  sub     rsp, 40h
0x140029214  mov     rdi, rdx
0x140029217  mov     qword ptr [r11+8], 0
0x14002921f  lea     rax, [r11+8]
0x140029223  mov     [r11-28h], rax
0x140029227  lea     r9, _GUID_3d0423b1_bbd4_4c4a_8f20_da15228e0f3d; riid
0x14002922e  xor     edx, edx; pUnkOuter
0x140029230  mov     r8d, 100004h; dwClsContext
0x140029236  lea     rcx, _GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd; rclsid
0x14002923d  call    cs:__imp_CoCreateInstance
0x140029243  mov     ebx, eax
0x140029245  test    eax, eax
0x140029247  jns     short loc_14002928A
0x140029249  lea     rcx, WPP_GLOBAL_Control
0x140029250  mov     rax, cs:WPP_GLOBAL_Control
0x140029257  cmp     rax, rcx
0x14002925a  jz      loc_140029377
0x140029260  test    byte ptr [rax+1Ch], 8
0x140029264  jz      loc_140029377
0x14002926a  cmp     byte ptr [rax+19h], 2
0x14002926e  jb      loc_140029377
0x140029274  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029279  mov     edx, 44h ; 'D'
0x14002927e  lea     rcx, aCocreateinstan_1; "CoCreateInstance(CLSID_LocationManager,"...
0x140029285  jmp     loc_140029353
0x14002928a  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x140029292  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x14002929b  mov     dword ptr [rsp+48h+dwImpLevel], 3; dwImpLevel
0x1400292a3  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x1400292ab  xor     r9d, r9d; pServerPrincName
0x1400292ae  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1400292b1  mov     r8d, edx; dwAuthzSvc
0x1400292b4  mov     rcx, [rsp+48h+pProxy]; pProxy
0x1400292b9  call    cs:__imp_CoSetProxyBlanket
0x1400292bf  mov     ebx, eax
0x1400292c1  test    eax, eax
0x1400292c3  jns     short loc_140029303
0x1400292c5  lea     rcx, WPP_GLOBAL_Control
0x1400292cc  mov     rax, cs:WPP_GLOBAL_Control
0x1400292d3  cmp     rax, rcx
0x1400292d6  jz      loc_140029377
0x1400292dc  test    byte ptr [rax+1Ch], 8
0x1400292e0  jz      loc_140029377
0x1400292e6  cmp     byte ptr [rax+19h], 2
0x1400292ea  jb      loc_140029377
0x1400292f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400292f5  mov     edx, 45h ; 'E'
0x1400292fa  lea     rcx, aCosetproxyblan; "CoSetProxyBlanket failed!"
0x140029301  jmp     short loc_140029353
0x140029303  mov     rcx, [rsp+48h+pProxy]
0x140029308  mov     rax, [rcx]
0x14002930b  mov     r8, rdi
0x14002930e  lea     rdx, _GUID_36205546_1ab7_4714_a3e9_e874233670db
0x140029315  mov     rax, [rax]
0x140029318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002931d  mov     ebx, eax
0x14002931f  test    eax, eax
0x140029321  jns     short loc_140029377
0x140029323  lea     rcx, WPP_GLOBAL_Control
0x14002932a  mov     rax, cs:WPP_GLOBAL_Control
0x140029331  cmp     rax, rcx
0x140029334  jz      short loc_140029377
0x140029336  test    byte ptr [rax+1Ch], 8
0x14002933a  jz      short loc_140029377
0x14002933c  cmp     byte ptr [rax+19h], 2
0x140029340  jb      short loc_140029377
0x140029342  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029347  mov     edx, 46h ; 'F'
0x14002934c  lea     rcx, aQueryinterface_3; "QueryInterface(IID_ILocationOverride) f"...
0x140029353  mov     dword ptr [rsp+48h+dwImpLevel], ebx
0x140029357  mov     qword ptr [rsp+48h+dwAuthnLevel], rcx
0x14002935c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029363  mov     r9d, eax
0x140029366  lea     r8, WPP_b9c789bf6143327f63d9bfd65da02f41_Traceguids
0x14002936d  mov     rcx, [rcx+10h]
0x140029371  call    WPP_SF_DsD
0x140029376  nop
0x140029377  mov     rcx, [rsp+48h+pProxy]
0x14002937c  test    rcx, rcx
0x14002937f  jz      short loc_140029397
0x140029381  mov     [rsp+48h+pProxy], 0
0x14002938a  mov     rax, [rcx]
0x14002938d  mov     rax, [rax+10h]
0x140029391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029396  nop
0x140029397  mov     eax, ebx
0x140029399  mov     rbx, [rsp+48h+arg_8]
0x14002939e  add     rsp, 40h
0x1400293a2  pop     rdi
0x1400293a3  retn
```
