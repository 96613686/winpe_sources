# CreateMultiObjectElevationFactory(HWND__ *,IMultiObjectElevationFactory * *)

- ea: `0x1800150a4`
- end: `0x180015138`
- name: `?CreateMultiObjectElevationFactory@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(HWND, struct IMultiObjectElevationFactory **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013e3c`

## callees

- `0x180008b30`
- `0x1800150a4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800150de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800150de`

## pseudocode

```c
__int64 __fastcall CreateMultiObjectElevationFactory(HWND a1, struct IMultiObjectElevationFactory **a2)
{
  HRESULT Instance; // ebx
  struct IMultiObjectElevationFactory *v5; // rax
  struct IMultiObjectElevationFactory *v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  Instance = CoCreateInstance(
               &CLSID_MultiObjectElevationFactory,
               0,
               1u,
               &GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e,
               (LPVOID *)&v7);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(struct IMultiObjectElevationFactory *, HWND, __int64 *))(*(_QWORD *)v7 + 24LL))(
                 v7,
                 a1,
                 qword_180037840);
    if ( Instance >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800150a4  mov     r11, rsp
0x1800150a7  mov     [r11+8], rbx
0x1800150ab  mov     [r11+10h], rsi
0x1800150af  push    rdi
0x1800150b0  sub     rsp, 30h
0x1800150b4  mov     rdi, rdx
0x1800150b7  mov     rsi, rcx
0x1800150ba  mov     qword ptr [r11+18h], 0
0x1800150c2  lea     rax, [r11+18h]
0x1800150c6  mov     [r11-18h], rax
0x1800150ca  lea     r9, _GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e; riid
0x1800150d1  xor     edx, edx; pUnkOuter
0x1800150d3  lea     r8d, [rdx+1]; dwClsContext
0x1800150d7  lea     rcx, CLSID_MultiObjectElevationFactory; rclsid
0x1800150de  call    cs:__imp_CoCreateInstance
0x1800150e4  mov     ebx, eax
0x1800150e6  test    eax, eax
0x1800150e8  js      short loc_18001511C
0x1800150ea  mov     rcx, [rsp+38h+arg_10]
0x1800150ef  mov     rax, [rcx]
0x1800150f2  lea     r8, qword_180037840
0x1800150f9  mov     rdx, rsi
0x1800150fc  mov     rax, [rax+18h]
0x180015100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015105  mov     ebx, eax
0x180015107  test    eax, eax
0x180015109  js      short loc_18001511C
0x18001510b  mov     rax, [rsp+38h+arg_10]
0x180015110  mov     [rsp+38h+arg_10], 0
0x180015119  mov     [rdi], rax
0x18001511c  lea     rcx, [rsp+38h+arg_10]
0x180015121  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015126  mov     eax, ebx
0x180015128  mov     rbx, [rsp+38h+arg_0]
0x18001512d  mov     rsi, [rsp+38h+arg_8]
0x180015132  add     rsp, 30h
0x180015136  pop     rdi
0x180015137  retn
```
