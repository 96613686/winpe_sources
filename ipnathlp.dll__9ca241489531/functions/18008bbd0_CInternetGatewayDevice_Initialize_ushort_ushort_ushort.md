# CInternetGatewayDevice::Initialize(ushort *,ushort *,ushort *)

- ea: `0x18008bbd0`
- end: `0x18008bcac`
- name: `?Initialize@CInternetGatewayDevice@@UEAAJPEAG00@Z`
- size: `220`
- prototype: `__int64 __fastcall(CInternetGatewayDevice *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180037c3c`
- `0x18008bbd0`
- `0x180090010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008bc3e`
- `OLEAUT32!__imp_SysAllocString` at `0x18008bc3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008bc7a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008bc83`
- `OLEAUT32!__imp_SysFreeString` at `0x18008bc7a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008bc83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008bc18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008bc18`

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
0x18008bbd0  mov     [rsp+arg_0], rbx
0x18008bbd5  mov     [rsp+arg_8], rsi
0x18008bbda  push    rdi
0x18008bbdb  sub     rsp, 40h
0x18008bbdf  mov     rsi, r8
0x18008bbe2  test    r8, r8
0x18008bbe5  jnz     short loc_18008BBF1
0x18008bbe7  mov     eax, 80070057h
0x18008bbec  jmp     loc_18008BC9C
0x18008bbf1  xor     edx, edx; pUnkOuter
0x18008bbf3  mov     [rsp+48h+arg_10], 0
0x18008bbfc  lea     rax, [rsp+48h+arg_10]
0x18008bc01  lea     r9, IID_IUPnPRegistrar; riid
0x18008bc08  mov     [rsp+48h+ppv], rax; ppv
0x18008bc0d  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x18008bc14  lea     r8d, [rdx+15h]; dwClsContext
0x18008bc18  call    cs:__imp_CoCreateInstance
0x18008bc1e  mov     ebx, eax
0x18008bc20  test    eax, eax
0x18008bc22  js      short loc_18008BC9A
0x18008bc24  mov     rcx, [rsp+48h+arg_10]; struct IUnknown *
0x18008bc29  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x18008bc2e  lea     rcx, aDummyudn; "DummyUDN"
0x18008bc35  mov     [rsp+48h+bstrString], 0
0x18008bc3e  call    cs:__imp_SysAllocString
0x18008bc44  mov     rdi, rax
0x18008bc47  test    rax, rax
0x18008bc4a  jnz     short loc_18008BC53
0x18008bc4c  mov     ebx, 8007000Eh
0x18008bc51  jmp     short loc_18008BC89
0x18008bc53  mov     rcx, [rsp+48h+arg_10]
0x18008bc58  lea     r9, [rsp+48h+bstrString]
0x18008bc5d  mov     r8, rdi
0x18008bc60  mov     rdx, rsi
0x18008bc63  mov     rax, [rcx]
0x18008bc66  mov     rax, [rax+30h]
0x18008bc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc6f  mov     ebx, eax
0x18008bc71  test    eax, eax
0x18008bc73  js      short loc_18008BC80
0x18008bc75  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18008bc7a  call    cs:__imp_SysFreeString
0x18008bc80  mov     rcx, rdi; bstrString
0x18008bc83  call    cs:__imp_SysFreeString
0x18008bc89  mov     rcx, [rsp+48h+arg_10]
0x18008bc8e  mov     rax, [rcx]
0x18008bc91  mov     rax, [rax+10h]
0x18008bc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc9a  mov     eax, ebx
0x18008bc9c  mov     rbx, [rsp+48h+arg_0]
0x18008bca1  mov     rsi, [rsp+48h+arg_8]
0x18008bca6  add     rsp, 40h
0x18008bcaa  pop     rdi
0x18008bcab  retn
```
