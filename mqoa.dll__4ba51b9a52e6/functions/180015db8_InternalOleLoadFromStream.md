# InternalOleLoadFromStream

- ea: `0x180015db8`
- end: `0x180015eee`
- name: `InternalOleLoadFromStream`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800158dc`

## callees

- `0x180015db8`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `ole32!ReadClassStm` at `0x180015df6`
- `ole32!ReadClassStm` at `0x180015df6`
- `ole32!CoCreateInstance` at `0x180015e20`
- `ole32!CoCreateInstance` at `0x180015e20`

## pseudocode

```c
__int64 __fastcall InternalOleLoadFromStream(IStream *a1, __int64 a2, __int64 a3)
{
  HRESULT v5; // ebx
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  CLSID pclsid; // [rsp+40h] [rbp-20h] BYREF

  ppv = 0;
  v7 = 0;
  pclsid = 0;
  v5 = ReadClassStm(a1, &pclsid);
  if ( v5 >= 0 )
  {
    v5 = CoCreateInstance(&pclsid, 0, 0x15u, &IID_IUnknown, &ppv);
    if ( v5 >= 0 )
    {
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistStream, &v7) >= 0
        || (v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistStreamInit, &v7), v5 >= 0) )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, IStream *))(*(_QWORD *)v7 + 40LL))(v7, a1);
        if ( v5 >= 0 )
          v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(ppv, &IID_IUnknown, a3);
      }
    }
  }
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015db8  mov     [rsp-18h+arg_8], rbx
0x180015dbd  push    rbp
0x180015dbe  push    rsi
0x180015dbf  push    rdi
0x180015dc0  mov     rbp, rsp
0x180015dc3  sub     rsp, 60h
0x180015dc7  mov     rax, cs:__security_cookie
0x180015dce  xor     rax, rsp
0x180015dd1  mov     [rbp+var_10], rax
0x180015dd5  xorps   xmm0, xmm0
0x180015dd8  mov     [rbp+var_28], 0
0x180015de0  lea     rdx, [rbp+pclsid]; pclsid
0x180015de4  mov     [rbp+var_30], 0
0x180015dec  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180015df0  mov     rsi, r8
0x180015df3  mov     rdi, rcx
0x180015df6  call    cs:__imp_ReadClassStm
0x180015dfc  mov     ebx, eax
0x180015dfe  test    eax, eax
0x180015e00  js      loc_180015E9E
0x180015e06  xor     edx, edx; pUnkOuter
0x180015e08  lea     rax, [rbp+var_28]
0x180015e0c  lea     r9, IID_IUnknown; riid
0x180015e13  mov     [rsp+60h+ppv], rax; ppv
0x180015e18  lea     rcx, [rbp+pclsid]; rclsid
0x180015e1c  lea     r8d, [rdx+15h]; dwClsContext
0x180015e20  call    cs:__imp_CoCreateInstance
0x180015e26  mov     ebx, eax
0x180015e28  test    eax, eax
0x180015e2a  js      short loc_180015E9E
0x180015e2c  mov     rcx, [rbp+var_28]
0x180015e30  lea     r8, [rbp+var_30]
0x180015e34  lea     rdx, IID_IPersistStream
0x180015e3b  mov     rax, [rcx]
0x180015e3e  mov     rax, [rax]
0x180015e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e46  test    eax, eax
0x180015e48  jns     short loc_180015E6A
0x180015e4a  mov     rcx, [rbp+var_28]
0x180015e4e  lea     r8, [rbp+var_30]
0x180015e52  lea     rdx, IID_IPersistStreamInit
0x180015e59  mov     rax, [rcx]
0x180015e5c  mov     rax, [rax]
0x180015e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e64  mov     ebx, eax
0x180015e66  test    eax, eax
0x180015e68  js      short loc_180015E9E
0x180015e6a  mov     rcx, [rbp+var_30]
0x180015e6e  mov     rdx, rdi
0x180015e71  mov     rax, [rcx]
0x180015e74  mov     rax, [rax+28h]
0x180015e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7d  mov     ebx, eax
0x180015e7f  test    eax, eax
0x180015e81  js      short loc_180015E9E
0x180015e83  mov     rcx, [rbp+var_28]
0x180015e87  lea     rdx, IID_IUnknown
0x180015e8e  mov     r8, rsi
0x180015e91  mov     rax, [rcx]
0x180015e94  mov     rax, [rax]
0x180015e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e9c  mov     ebx, eax
0x180015e9e  mov     rcx, [rbp+var_30]
0x180015ea2  test    rcx, rcx
0x180015ea5  jz      short loc_180015EBB
0x180015ea7  mov     rax, [rcx]
0x180015eaa  mov     rax, [rax+10h]
0x180015eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb3  mov     [rbp+var_30], 0
0x180015ebb  mov     rcx, [rbp+var_28]
0x180015ebf  test    rcx, rcx
0x180015ec2  jz      short loc_180015ED0
0x180015ec4  mov     rax, [rcx]
0x180015ec7  mov     rax, [rax+10h]
0x180015ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed0  mov     eax, ebx
0x180015ed2  mov     rcx, [rbp+var_10]
0x180015ed6  xor     rcx, rsp; StackCookie
0x180015ed9  call    __security_check_cookie
0x180015ede  mov     rbx, [rsp+60h+arg_8]
0x180015ee6  add     rsp, 60h
0x180015eea  pop     rdi
0x180015eeb  pop     rsi
0x180015eec  pop     rbp
0x180015eed  retn
```
