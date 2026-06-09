# CFirewallCplInitializer::_CreateElevatedObject(IMultiObjectElevationFactory * *)

- ea: `0x18000f438`
- end: `0x18000f533`
- name: `?_CreateElevatedObject@CFirewallCplInitializer@@IEAAJPEAPEAUIMultiObjectElevationFactory@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct IUnknown **this, struct IMultiObjectElevationFactory **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f130`

## callees

- `0x180008b30`
- `0x18000f0c8`
- `0x18000f438`
- `0x18002dd20`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f472`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f472`

## pseudocode

```c
__int64 __fastcall CFirewallCplInitializer::_CreateElevatedObject(
        struct IUnknown **this,
        struct IMultiObjectElevationFactory **a2)
{
  HRESULT Instance; // ebx
  int v5; // eax
  struct IMultiObjectElevationFactory *v6; // rax
  struct IMultiObjectElevationFactory *v8; // [rsp+60h] [rbp+18h] BYREF
  HWND hwndOwner; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  Instance = CoCreateInstance(
               &CLSID_MultiObjectElevationFactory,
               0,
               1u,
               &GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e,
               (LPVOID *)&v8);
  if ( Instance >= 0 )
  {
    hwndOwner = 0;
    Instance = GetHwndOfFrame(this[2], &hwndOwner);
    if ( Instance >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(struct IMultiObjectElevationFactory *, HWND, __int64 *))(*(_QWORD *)v8 + 24LL))(
             v8,
             hwndOwner,
             qword_1800373A0);
      Instance = v5;
      if ( v5 == -2147023636 )
      {
        TaskDialog(hwndOwner, g_hinst, (PCWSTR)1, 0, (PCWSTR)3, 0, (PCWSTR)0xFFFE, 0);
      }
      else if ( v5 >= 0 )
      {
        v6 = v8;
        v8 = 0;
        *a2 = v6;
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f438  mov     r11, rsp
0x18000f43b  mov     [r11+8], rbx
0x18000f43f  mov     [r11+10h], rsi
0x18000f443  push    rdi
0x18000f444  sub     rsp, 40h
0x18000f448  mov     rdi, rdx
0x18000f44b  mov     rsi, rcx
0x18000f44e  mov     qword ptr [r11+18h], 0
0x18000f456  lea     rax, [r11+18h]
0x18000f45a  mov     [r11-28h], rax
0x18000f45e  lea     r9, _GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e; riid
0x18000f465  xor     edx, edx; pUnkOuter
0x18000f467  lea     r8d, [rdx+1]; dwClsContext
0x18000f46b  lea     rcx, CLSID_MultiObjectElevationFactory; rclsid
0x18000f472  call    cs:__imp_CoCreateInstance
0x18000f478  mov     ebx, eax
0x18000f47a  test    eax, eax
0x18000f47c  js      loc_18000F517
0x18000f482  mov     [rsp+48h+hwndOwner], 0
0x18000f48b  lea     rdx, [rsp+48h+hwndOwner]; HWND *
0x18000f490  mov     rcx, [rsi+10h]; struct IUnknown *
0x18000f494  call    ?GetHwndOfFrame@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetHwndOfFrame(IUnknown *,HWND__ * *)
0x18000f499  mov     ebx, eax
0x18000f49b  test    eax, eax
0x18000f49d  js      short loc_18000F517
0x18000f49f  mov     rcx, [rsp+48h+arg_10]
0x18000f4a4  mov     rax, [rcx]
0x18000f4a7  lea     r8, qword_1800373A0
0x18000f4ae  mov     rdx, [rsp+48h+hwndOwner]
0x18000f4b3  mov     rax, [rax+18h]
0x18000f4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4bc  mov     ebx, eax
0x18000f4be  cmp     eax, 800704ECh
0x18000f4c3  jnz     short loc_18000F502
0x18000f4c5  mov     [rsp+48h+pnButton], 0; pnButton
0x18000f4ce  mov     [rsp+48h+pszIcon], 0FFFEh; pszIcon
0x18000f4d7  mov     [rsp+48h+dwCommonButtons], 0; dwCommonButtons
0x18000f4df  mov     [rsp+48h+pszContent], 3; pszContent
0x18000f4e8  xor     r9d, r9d; pszMainInstruction
0x18000f4eb  lea     r8d, [r9+1]; pszWindowTitle
0x18000f4ef  mov     rdx, cs:g_hinst; hInstance
0x18000f4f6  mov     rcx, [rsp+48h+hwndOwner]; hwndOwner
0x18000f4fb  call    TaskDialog
0x18000f500  jmp     short loc_18000F517
0x18000f502  test    eax, eax
0x18000f504  js      short loc_18000F517
0x18000f506  mov     rax, [rsp+48h+arg_10]
0x18000f50b  mov     [rsp+48h+arg_10], 0
0x18000f514  mov     [rdi], rax
0x18000f517  lea     rcx, [rsp+48h+arg_10]
0x18000f51c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f521  mov     eax, ebx
0x18000f523  mov     rbx, [rsp+48h+arg_0]
0x18000f528  mov     rsi, [rsp+48h+arg_8]
0x18000f52d  add     rsp, 40h
0x18000f531  pop     rdi
0x18000f532  retn
```
