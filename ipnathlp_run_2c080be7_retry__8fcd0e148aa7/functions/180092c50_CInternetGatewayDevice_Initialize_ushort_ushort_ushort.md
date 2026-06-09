# CInternetGatewayDevice::Initialize(ushort *,ushort *,ushort *)

- ea: `0x180092c50`
- end: `0x180092d49`
- name: `?Initialize@CInternetGatewayDevice@@UEAAJPEAG00@Z`
- size: `249`
- prototype: `__int64 __fastcall(CInternetGatewayDevice *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003a9c0`
- `0x180092c50`
- `0x180097010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180092cc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180092cc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d19`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180092c98`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180092c98`

## pseudocode

```c
__int64 __fastcall CInternetGatewayDevice::Initialize(
        CInternetGatewayDevice *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HRESULT Instance; // ebx
  BSTR v7; // rax
  OLECHAR *v8; // rdi
  BSTR bstrString[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IUnknown *ppv; // [rsp+60h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x15u, &IID_IUPnPRegistrar, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    SetProxyBlanket(ppv);
    bstrString[0] = 0;
    v7 = SysAllocString(L"DummyUDN");
    v8 = v7;
    if ( v7 )
    {
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, BSTR, BSTR *))ppv->lpVtbl[2].QueryInterface)(
                   ppv,
                   a3,
                   v7,
                   bstrString);
      if ( Instance >= 0 )
        SysFreeString(bstrString[0]);
      SysFreeString(v8);
    }
    else
    {
      Instance = -2147024882;
    }
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180092c50  mov     [rsp+arg_0], rbx
0x180092c55  mov     [rsp+arg_8], rsi
0x180092c5a  push    rdi
0x180092c5b  sub     rsp, 40h
0x180092c5f  mov     rsi, r8
0x180092c62  test    r8, r8
0x180092c65  jnz     short loc_180092C71
0x180092c67  mov     eax, 80070057h
0x180092c6c  jmp     loc_180092D38
0x180092c71  xor     edx, edx; pUnkOuter
0x180092c73  mov     [rsp+48h+arg_10], 0
0x180092c7c  lea     rax, [rsp+48h+arg_10]
0x180092c81  lea     r9, IID_IUPnPRegistrar; riid
0x180092c88  mov     [rsp+48h+ppv], rax; ppv
0x180092c8d  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180092c94  lea     r8d, [rdx+15h]; dwClsContext
0x180092c98  call    cs:__imp_CoCreateInstance
0x180092c9f  nop     dword ptr [rax+rax+00h]
0x180092ca4  mov     ebx, eax
0x180092ca6  test    eax, eax
0x180092ca8  js      loc_180092D36
0x180092cae  mov     rcx, [rsp+48h+arg_10]; struct IUnknown *
0x180092cb3  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180092cb8  lea     rcx, aDummyudn; "DummyUDN"
0x180092cbf  mov     [rsp+48h+bstrString], 0
0x180092cc8  call    cs:__imp_SysAllocString
0x180092ccf  nop     dword ptr [rax+rax+00h]
0x180092cd4  mov     rdi, rax
0x180092cd7  test    rax, rax
0x180092cda  jnz     short loc_180092CE3
0x180092cdc  mov     ebx, 8007000Eh
0x180092ce1  jmp     short loc_180092D25
0x180092ce3  mov     rcx, [rsp+48h+arg_10]
0x180092ce8  lea     r9, [rsp+48h+bstrString]
0x180092ced  mov     r8, rdi
0x180092cf0  mov     rdx, rsi
0x180092cf3  mov     rax, [rcx]
0x180092cf6  mov     rax, [rax+30h]
0x180092cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092cff  mov     ebx, eax
0x180092d01  test    eax, eax
0x180092d03  js      short loc_180092D16
0x180092d05  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180092d0a  call    cs:__imp_SysFreeString
0x180092d11  nop     dword ptr [rax+rax+00h]
0x180092d16  mov     rcx, rdi; bstrString
0x180092d19  call    cs:__imp_SysFreeString
0x180092d20  nop     dword ptr [rax+rax+00h]
0x180092d25  mov     rcx, [rsp+48h+arg_10]
0x180092d2a  mov     rax, [rcx]
0x180092d2d  mov     rax, [rax+10h]
0x180092d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d36  mov     eax, ebx
0x180092d38  mov     rbx, [rsp+48h+arg_0]
0x180092d3d  mov     rsi, [rsp+48h+arg_8]
0x180092d42  add     rsp, 40h
0x180092d46  pop     rdi
0x180092d47  retn
```
