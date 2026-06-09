# CBaseFilter::Unregister(void)

- ea: `0x10030d00`
- end: `0x10030d8f`
- name: `?Unregister@CBaseFilter@@UAGJXZ`
- size: `143`
- prototype: `HRESULT __stdcall(CBaseFilter *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1002d510`
- `0x10030d00`
- `0x1003341a`

## import_xrefs

- `ole32!CoUninitialize` at `0x10030d76`
- `ole32!CoUninitialize` at `0x10030d76`
- `ole32!CoFreeUnusedLibraries` at `0x10030d70`
- `ole32!CoFreeUnusedLibraries` at `0x10030d70`
- `ole32!CoInitializeEx` at `0x10030d2b`
- `ole32!CoInitializeEx` at `0x10030d2b`
- `ole32!CoCreateInstance` at `0x10030d43`
- `ole32!CoCreateInstance` at `0x10030d43`

## pseudocode

```c
HRESULT __stdcall CBaseFilter::Unregister(CBaseFilter *this)
{
  HRESULT v2; // edi
  LPVOID ppv; // [esp+8h] [ebp-4h] BYREF

  if ( !((int (__thiscall *)(IFilterGraph **))this[-1].m_pGraph[8].__vftable)(&this[-1].m_pGraph) )
    return 1;
  CoInitializeEx(0, 2u);
  v2 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &ppv);
  if ( v2 >= 0 )
  {
    v2 = AMovieSetupRegisterFilter(0);
    (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)ppv + 8))(*(_DWORD *)(*(_DWORD *)ppv + 8), ppv);
  }
  CoFreeUnusedLibraries();
  CoUninitialize();
  if ( v2 == -2147024894 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x10030d00  mov     edi, edi
0x10030d02  push    ebp
0x10030d03  mov     ebp, esp
0x10030d05  push    ecx
0x10030d06  push    esi
0x10030d07  push    edi
0x10030d08  mov     edi, [ebp+this]
0x10030d0b  mov     eax, [edi-10h]
0x10030d0e  mov     esi, [eax+20h]
0x10030d11  mov     ecx, esi; this
0x10030d13  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10030d19  lea     ecx, [edi-10h]
0x10030d1c  call    esi
0x10030d1e  mov     esi, eax
0x10030d20  test    esi, esi
0x10030d22  jnz     short loc_10030D27
0x10030d24  inc     eax
0x10030d25  jmp     short loc_10030D89
0x10030d27  push    2; dwCoInit
0x10030d29  push    0; pvReserved
0x10030d2b  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10030d31  lea     eax, [ebp+ppv]
0x10030d34  push    eax; ppv
0x10030d35  push    offset _IID_IFilterMapper; riid
0x10030d3a  push    1; dwClsContext
0x10030d3c  push    0; pUnkOuter
0x10030d3e  push    offset _CLSID_FilterMapper; rclsid
0x10030d43  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10030d49  mov     edi, eax
0x10030d4b  test    edi, edi
0x10030d4d  js      short loc_10030D70
0x10030d4f  mov     edx, [ebp+ppv]
0x10030d52  mov     ecx, esi
0x10030d54  push    0
0x10030d56  call    _AMovieSetupRegisterFilter@12; AMovieSetupRegisterFilter(x,x,x)
0x10030d5b  mov     edi, eax
0x10030d5d  mov     eax, [ebp+ppv]
0x10030d60  push    eax
0x10030d61  mov     ecx, [eax]
0x10030d63  mov     esi, [ecx+8]
0x10030d66  mov     ecx, esi; this
0x10030d68  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10030d6e  call    esi
0x10030d70  call    ds:__imp__CoFreeUnusedLibraries@0; CoFreeUnusedLibraries()
0x10030d76  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10030d7c  xor     eax, eax
0x10030d7e  cmp     edi, 80070002h
0x10030d84  cmovz   edi, eax
0x10030d87  mov     eax, edi
0x10030d89  pop     edi
0x10030d8a  pop     esi
0x10030d8b  leave
0x10030d8c  retn    4
```
