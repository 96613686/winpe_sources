# CDispatchInterfaceProxy::CreateObject(wchar_t const *,IDispatch * *)

- ea: `0x180004e84`
- end: `0x180004fbb`
- name: `?CreateObject@CDispatchInterfaceProxy@@AEAAJPEB_WPEAPEAUIDispatch@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(CDispatchInterfaceProxy *this, const wchar_t *, struct IDispatch **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004fc4`

## callees

- `0x180004e84`
- `0x18000f310`
- `0x18001e380`
- `0x180022010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004efa`
- `ole32!CoCreateInstance` at `0x180004efa`
- `ole32!CLSIDFromProgID` at `0x180004ecc`
- `ole32!CLSIDFromProgID` at `0x180004ecc`

## pseudocode

```c
__int64 __fastcall CDispatchInterfaceProxy::CreateObject(
        CDispatchInterfaceProxy *this,
        const wchar_t *a2,
        struct IDispatch **a3)
{
  HRESULT v4; // ebx
  unsigned __int16 v5; // r8
  LPVOID v7; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-30h] BYREF
  struct IDispatch *v9; // [rsp+38h] [rbp-28h] BYREF
  GUID clsid; // [rsp+40h] [rbp-20h] BYREF

  ppv = 0;
  v9 = 0;
  *a3 = 0;
  clsid = 0;
  v4 = CLSIDFromProgID(a2, &clsid);
  if ( v4 >= 0 )
  {
    v4 = CoCreateInstance(&clsid, 0, 0x15u, &IID_IUnknown, &ppv);
    if ( v4 >= 0 )
    {
      v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IDispatch **))ppv)(ppv, &IID_IDispatch, &v9);
      if ( v4 >= 0 )
      {
        v7 = ppv;
        *a3 = v9;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
        return 0;
      }
      v5 = 70;
    }
    else
    {
      v5 = 60;
    }
  }
  else
  {
    v5 = 50;
  }
  LogMsgHR(v4, (wchar_t *)L"trigobjs/idspprxy", v5);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v9 )
    ((void (__fastcall *)(struct IDispatch *))v9->lpVtbl->Release)(v9);
  LogMsgHR(v4, (wchar_t *)L"trigobjs/idspprxy", 0x50u);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004e84  mov     [rsp-8+arg_0], rbx
0x180004e89  mov     [rsp-8+arg_18], rdi
0x180004e8e  push    rbp
0x180004e8f  mov     rbp, rsp
0x180004e92  sub     rsp, 60h
0x180004e96  mov     rax, cs:__security_cookie
0x180004e9d  xor     rax, rsp
0x180004ea0  mov     [rbp+var_10], rax
0x180004ea4  mov     rcx, rdx; lpszProgID
0x180004ea7  mov     [rbp+var_30], 0
0x180004eaf  xorps   xmm0, xmm0
0x180004eb2  mov     [rbp+var_28], 0
0x180004eba  lea     rdx, [rbp+clsid]; lpclsid
0x180004ebe  mov     qword ptr [r8], 0
0x180004ec5  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180004ec9  mov     rdi, r8
0x180004ecc  call    cs:__imp_CLSIDFromProgID
0x180004ed2  mov     ebx, eax
0x180004ed4  test    eax, eax
0x180004ed6  jns     short loc_180004EE0
0x180004ed8  mov     r8d, 32h ; '2'
0x180004ede  jmp     short loc_180004F34
0x180004ee0  xor     edx, edx; pUnkOuter
0x180004ee2  lea     rax, [rbp+var_30]
0x180004ee6  lea     r9, IID_IUnknown; riid
0x180004eed  mov     [rsp+60h+ppv], rax; ppv
0x180004ef2  lea     rcx, [rbp+clsid]; rclsid
0x180004ef6  lea     r8d, [rdx+15h]; dwClsContext
0x180004efa  call    cs:__imp_CoCreateInstance
0x180004f00  mov     ebx, eax
0x180004f02  test    eax, eax
0x180004f04  jns     short loc_180004F0E
0x180004f06  mov     r8d, 3Ch ; '<'
0x180004f0c  jmp     short loc_180004F34
0x180004f0e  mov     rcx, [rbp+var_30]
0x180004f12  lea     r8, [rbp+var_28]
0x180004f16  lea     rdx, IID_IDispatch
0x180004f1d  mov     rax, [rcx]
0x180004f20  mov     rax, [rax]
0x180004f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f28  mov     ebx, eax
0x180004f2a  test    eax, eax
0x180004f2c  jns     short loc_180004F84
0x180004f2e  mov     r8d, 46h ; 'F'; unsigned __int16
0x180004f34  lea     rdx, aTrigobjsIdsppr; "trigobjs/idspprxy"
0x180004f3b  mov     ecx, ebx; int
0x180004f3d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180004f42  mov     rcx, [rbp+var_30]
0x180004f46  test    rcx, rcx
0x180004f49  jz      short loc_180004F57
0x180004f4b  mov     rax, [rcx]
0x180004f4e  mov     rax, [rax+10h]
0x180004f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f57  mov     rcx, [rbp+var_28]
0x180004f5b  test    rcx, rcx
0x180004f5e  jz      short loc_180004F6C
0x180004f60  mov     rax, [rcx]
0x180004f63  mov     rax, [rax+10h]
0x180004f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f6c  mov     r8d, 50h ; 'P'; unsigned __int16
0x180004f72  lea     rdx, aTrigobjsIdsppr; "trigobjs/idspprxy"
0x180004f79  mov     ecx, ebx; int
0x180004f7b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180004f80  mov     eax, ebx
0x180004f82  jmp     short loc_180004F9D
0x180004f84  mov     rax, [rbp+var_28]
0x180004f88  mov     rcx, [rbp+var_30]
0x180004f8c  mov     [rdi], rax
0x180004f8f  mov     rax, [rcx]
0x180004f92  mov     rax, [rax+10h]
0x180004f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9b  xor     eax, eax
0x180004f9d  mov     rcx, [rbp+var_10]
0x180004fa1  xor     rcx, rsp; StackCookie
0x180004fa4  call    __security_check_cookie
0x180004fa9  lea     r11, [rsp+60h+var_s0]
0x180004fae  mov     rbx, [r11+10h]
0x180004fb2  mov     rdi, [r11+28h]
0x180004fb6  mov     rsp, r11
0x180004fb9  pop     rbp
0x180004fba  retn
```
