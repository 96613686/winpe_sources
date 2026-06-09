# DllGetClassObject

- ea: `0x180001a80`
- end: `0x180001b53`
- name: `DllGetClassObject`
- size: `211`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001a80`
- `0x180006010`

## import_xrefs

- `cmutil!CmMalloc` at `0x180001aeb`
- `cmutil!CmMalloc` at `0x180001aeb`
- `RPCRT4!NdrDllGetClassObject` at `0x180001ac3`
- `RPCRT4!NdrDllGetClassObject` at `0x180001ac3`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  HRESULT v9; // ebx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  if ( NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory) >= 0 )
    return 0;
  if ( *(_QWORD *)&CLSID_CMLuaUtil.Data1 != *(_QWORD *)&rclsid->Data1
    || *(_QWORD *)CLSID_CMLuaUtil.Data4 != *(_QWORD *)rclsid->Data4 )
  {
    return -2147221231;
  }
  v7 = CmMalloc(0x10u);
  v8 = v7;
  if ( !v7 )
    return -2147024882;
  v7[2] = 1;
  *(_QWORD *)v7 = &CClassFactory::`vftable';
  _InterlockedIncrement(&dword_18000C6C0);
  v9 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180001a80  push    rbx
0x180001a82  push    rbp
0x180001a83  push    rsi
0x180001a84  push    rdi
0x180001a85  sub     rsp, 38h
0x180001a89  mov     rax, cs:aProxyFileList
0x180001a90  mov     rsi, r8
0x180001a93  mov     rbp, rdx
0x180001a96  mov     rbx, rcx
0x180001a99  mov     r9, [rax+8]
0x180001a9d  mov     rax, [r9]
0x180001aa0  test    rax, rax
0x180001aa3  jz      short loc_180001AA8
0x180001aa5  mov     rax, [rax]
0x180001aa8  lea     rcx, gPFactory
0x180001aaf  mov     [rsp+58h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180001ab4  lea     r9, aProxyFileList; pProxyFileList
0x180001abb  mov     rcx, rbx; rclsid
0x180001abe  mov     [rsp+58h+pclsid], rax; pclsid
0x180001ac3  call    cs:__imp_NdrDllGetClassObject
0x180001ac9  test    eax, eax
0x180001acb  jns     short loc_180001B48
0x180001acd  mov     rax, qword ptr cs:CLSID_CMLuaUtil.Data1
0x180001ad4  cmp     rax, [rbx]
0x180001ad7  jnz     short loc_180001B3F
0x180001ad9  mov     rax, qword ptr cs:CLSID_CMLuaUtil.Data4
0x180001ae0  cmp     rax, [rbx+8]
0x180001ae4  jnz     short loc_180001B3F
0x180001ae6  mov     ecx, 10h
0x180001aeb  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180001af1  mov     rdi, rax
0x180001af4  test    rax, rax
0x180001af7  jz      short loc_180001B38
0x180001af9  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180001b00  mov     dword ptr [rdi+8], 1
0x180001b07  mov     [rdi], rax
0x180001b0a  lock inc cs:dword_18000C6C0
0x180001b11  mov     rcx, [rdi]
0x180001b14  mov     r8, rsi
0x180001b17  mov     rdx, rbp
0x180001b1a  mov     rax, [rcx]
0x180001b1d  mov     rcx, rdi
0x180001b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b25  mov     rcx, [rdi]
0x180001b28  mov     ebx, eax
0x180001b2a  mov     rax, [rcx+10h]
0x180001b2e  mov     rcx, rdi
0x180001b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b36  jmp     short loc_180001B44
0x180001b38  mov     ebx, 8007000Eh
0x180001b3d  jmp     short loc_180001B44
0x180001b3f  mov     ebx, 80040111h
0x180001b44  mov     eax, ebx
0x180001b46  jmp     short loc_180001B4A
0x180001b48  xor     eax, eax
0x180001b4a  add     rsp, 38h
0x180001b4e  pop     rdi
0x180001b4f  pop     rsi
0x180001b50  pop     rbp
0x180001b51  pop     rbx
0x180001b52  retn
```
