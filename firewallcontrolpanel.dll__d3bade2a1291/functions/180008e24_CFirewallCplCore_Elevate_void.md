# CFirewallCplCore::Elevate(void)

- ea: `0x180008e24`
- end: `0x180008f52`
- name: `?Elevate@CFirewallCplCore@@QEAAJXZ`
- size: `302`
- prototype: `__int64 __fastcall(CFirewallCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008f80`
- `0x180019c84`

## callees

- `0x180008b30`
- `0x180008e24`
- `0x1800094ac`
- `0x1800098bc`
- `0x18000994c`
- `0x18002dd20`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008e6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008e6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFirewallCplCore::Elevate(CFirewallCplCore *this)
{
  HRESULT v2; // ebx
  HWND ParentWindow; // rsi
  int v4; // eax
  LPVOID v5; // rax
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  ppv = 0;
  v2 = 0;
  if ( !CFirewallCplCore::IsElevated(this) )
  {
    v2 = CoCreateInstance(&CLSID_MultiObjectElevationFactory, 0, 1u, &GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e, &ppv);
    if ( v2 >= 0 )
    {
      ParentWindow = CFirewallCplCore::_GetParentWindow(this);
      v4 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             ParentWindow,
             qword_180036E78);
      v2 = v4;
      if ( v4 == -2147023636 )
      {
        TaskDialog(ParentWindow, g_hinst, (PCWSTR)1, 0, (PCWSTR)3, 0, (PCWSTR)0xFFFE, 0);
      }
      else if ( v4 >= 0 )
      {
        v5 = ppv;
        ppv = 0;
        *((_QWORD *)this + 9) = v5;
      }
    }
    else if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_d2517ed6f73e376c3e61f10cf36dc817_Traceguids,
        (unsigned int)v2);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180008e24  mov     [rsp+arg_0], rbx
0x180008e29  mov     [rsp+arg_10], rsi
0x180008e2e  push    rdi
0x180008e2f  sub     rsp, 40h
0x180008e33  mov     rdi, rcx
0x180008e36  mov     [rsp+48h+arg_8], 0
0x180008e3f  xor     ebx, ebx
0x180008e41  call    ?IsElevated@CFirewallCplCore@@QEAA_NXZ; CFirewallCplCore::IsElevated(void)
0x180008e46  test    al, al
0x180008e48  jnz     loc_180008F36
0x180008e4e  lea     rax, [rsp+48h+arg_8]
0x180008e53  mov     [rsp+48h+ppv], rax; ppv
0x180008e58  lea     r9, _GUID_6fabda16_031e_47e3_b2a2_2339c05ccb9e; riid
0x180008e5f  xor     edx, edx; pUnkOuter
0x180008e61  lea     r8d, [rbx+1]; dwClsContext
0x180008e65  lea     rcx, CLSID_MultiObjectElevationFactory; rclsid
0x180008e6c  call    cs:__imp_CoCreateInstance
0x180008e72  mov     ebx, eax
0x180008e74  test    eax, eax
0x180008e76  jns     short loc_180008EB6
0x180008e78  lea     rax, WPP_GLOBAL_Control
0x180008e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e86  cmp     rcx, rax
0x180008e89  jz      loc_180008F36
0x180008e8f  test    byte ptr [rcx+1Ch], 1
0x180008e93  jz      loc_180008F36
0x180008e99  mov     edx, 0Eh
0x180008e9e  mov     r9d, ebx
0x180008ea1  lea     r8, WPP_d2517ed6f73e376c3e61f10cf36dc817_Traceguids
0x180008ea8  mov     rcx, [rcx+10h]
0x180008eac  call    WPP_SF_d
0x180008eb1  jmp     loc_180008F36
0x180008eb6  mov     rcx, rdi; this
0x180008eb9  call    ?_GetParentWindow@CFirewallCplCore@@AEAAPEAUHWND__@@XZ; CFirewallCplCore::_GetParentWindow(void)
0x180008ebe  mov     rsi, rax
0x180008ec1  mov     rcx, [rsp+48h+arg_8]
0x180008ec6  mov     rdx, [rcx]
0x180008ec9  mov     rax, [rdx+18h]
0x180008ecd  lea     r8, qword_180036E78
0x180008ed4  mov     rdx, rsi
0x180008ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008edc  mov     ebx, eax
0x180008ede  cmp     eax, 800704ECh
0x180008ee3  jnz     short loc_180008F20
0x180008ee5  mov     [rsp+48h+pnButton], 0; pnButton
0x180008eee  mov     [rsp+48h+pszIcon], 0FFFEh; pszIcon
0x180008ef7  mov     [rsp+48h+dwCommonButtons], 0; dwCommonButtons
0x180008eff  mov     [rsp+48h+ppv], 3; pszContent
0x180008f08  xor     r9d, r9d; pszMainInstruction
0x180008f0b  lea     r8d, [r9+1]; pszWindowTitle
0x180008f0f  mov     rdx, cs:g_hinst; hInstance
0x180008f16  mov     rcx, rsi; hwndOwner
0x180008f19  call    TaskDialog
0x180008f1e  jmp     short loc_180008F36
0x180008f20  test    eax, eax
0x180008f22  js      short loc_180008F36
0x180008f24  mov     rax, [rsp+48h+arg_8]
0x180008f29  mov     [rsp+48h+arg_8], 0
0x180008f32  mov     [rdi+48h], rax
0x180008f36  lea     rcx, [rsp+48h+arg_8]
0x180008f3b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008f40  mov     eax, ebx
0x180008f42  mov     rbx, [rsp+48h+arg_0]
0x180008f47  mov     rsi, [rsp+48h+arg_10]
0x180008f4c  add     rsp, 40h
0x180008f50  pop     rdi
0x180008f51  retn
```
