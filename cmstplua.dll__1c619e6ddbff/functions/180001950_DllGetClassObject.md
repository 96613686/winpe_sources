# DllGetClassObject

- ea: `0x180001950`
- end: `0x180001a23`
- name: `DllGetClassObject`
- size: `211`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001950`
- `0x180003010`

## import_xrefs

- `cmutil!CmMalloc` at `0x1800019bb`
- `cmutil!CmMalloc` at `0x1800019bb`
- `RPCRT4!NdrDllGetClassObject` at `0x180001993`
- `RPCRT4!NdrDllGetClassObject` at `0x180001993`

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
  if ( *(_QWORD *)&CLSID_CmstpLua.Data1 != *(_QWORD *)&rclsid->Data1
    || *(_QWORD *)CLSID_CmstpLua.Data4 != *(_QWORD *)rclsid->Data4 )
  {
    return -2147221231;
  }
  v7 = CmMalloc(0x10u);
  v8 = v7;
  if ( !v7 )
    return -2147024882;
  v7[2] = 1;
  *(_QWORD *)v7 = &CClassFactory::`vftable';
  _InterlockedIncrement(&dword_180006640);
  v9 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180001950  push    rbx
0x180001952  push    rbp
0x180001953  push    rsi
0x180001954  push    rdi
0x180001955  sub     rsp, 38h
0x180001959  mov     rax, cs:aProxyFileList
0x180001960  mov     rsi, r8
0x180001963  mov     rbp, rdx
0x180001966  mov     rbx, rcx
0x180001969  mov     r9, [rax+8]
0x18000196d  mov     rax, [r9]
0x180001970  test    rax, rax
0x180001973  jz      short loc_180001978
0x180001975  mov     rax, [rax]
0x180001978  lea     rcx, gPFactory
0x18000197f  mov     [rsp+58h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180001984  lea     r9, aProxyFileList; pProxyFileList
0x18000198b  mov     rcx, rbx; rclsid
0x18000198e  mov     [rsp+58h+pclsid], rax; pclsid
0x180001993  call    cs:__imp_NdrDllGetClassObject
0x180001999  test    eax, eax
0x18000199b  jns     short loc_180001A18
0x18000199d  mov     rax, qword ptr cs:CLSID_CmstpLua.Data1
0x1800019a4  cmp     rax, [rbx]
0x1800019a7  jnz     short loc_180001A0F
0x1800019a9  mov     rax, qword ptr cs:CLSID_CmstpLua.Data4
0x1800019b0  cmp     rax, [rbx+8]
0x1800019b4  jnz     short loc_180001A0F
0x1800019b6  mov     ecx, 10h
0x1800019bb  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x1800019c1  mov     rdi, rax
0x1800019c4  test    rax, rax
0x1800019c7  jz      short loc_180001A08
0x1800019c9  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800019d0  mov     dword ptr [rdi+8], 1
0x1800019d7  mov     [rdi], rax
0x1800019da  lock inc cs:dword_180006640
0x1800019e1  mov     rcx, [rdi]
0x1800019e4  mov     r8, rsi
0x1800019e7  mov     rdx, rbp
0x1800019ea  mov     rax, [rcx]
0x1800019ed  mov     rcx, rdi
0x1800019f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019f5  mov     rcx, [rdi]
0x1800019f8  mov     ebx, eax
0x1800019fa  mov     rax, [rcx+10h]
0x1800019fe  mov     rcx, rdi
0x180001a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a06  jmp     short loc_180001A14
0x180001a08  mov     ebx, 8007000Eh
0x180001a0d  jmp     short loc_180001A14
0x180001a0f  mov     ebx, 80040111h
0x180001a14  mov     eax, ebx
0x180001a16  jmp     short loc_180001A1A
0x180001a18  xor     eax, eax
0x180001a1a  add     rsp, 38h
0x180001a1e  pop     rdi
0x180001a1f  pop     rsi
0x180001a20  pop     rbp
0x180001a21  pop     rbx
0x180001a22  retn
```
