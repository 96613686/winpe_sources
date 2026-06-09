# CBaseFilter::Register(void)

- ea: `0x10030c70`
- end: `0x10030cf0`
- name: `?Register@CBaseFilter@@UAGJXZ`
- size: `128`
- prototype: `int __stdcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1002d510`
- `0x10030c70`
- `0x1003341a`

## import_xrefs

- `ole32!CoUninitialize` at `0x10030ce2`
- `ole32!CoUninitialize` at `0x10030ce2`
- `ole32!CoFreeUnusedLibraries` at `0x10030cdc`
- `ole32!CoFreeUnusedLibraries` at `0x10030cdc`
- `ole32!CoInitializeEx` at `0x10030c9b`
- `ole32!CoInitializeEx` at `0x10030c9b`
- `ole32!CoCreateInstance` at `0x10030cb3`
- `ole32!CoCreateInstance` at `0x10030cb3`

## pseudocode

```c
int __stdcall CBaseFilter::Register(CBaseFilter *this)
{
  LPVOID ppv; // [esp+8h] [ebp-4h] BYREF

  if ( !((int (__thiscall *)(IFilterGraph **))this[-1].m_pGraph[8].__vftable)(&this[-1].m_pGraph) )
    return 1;
  CoInitializeEx(0, 2u);
  if ( CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &ppv) >= 0 )
  {
    AMovieSetupRegisterFilter(1);
    (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)ppv + 8))(*(_DWORD *)(*(_DWORD *)ppv + 8), ppv);
  }
  CoFreeUnusedLibraries();
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x10030c70  mov     edi, edi
0x10030c72  push    ebp
0x10030c73  mov     ebp, esp
0x10030c75  push    ecx
0x10030c76  push    esi
0x10030c77  push    edi
0x10030c78  mov     edi, [ebp+this]
0x10030c7b  mov     eax, [edi-10h]
0x10030c7e  mov     esi, [eax+20h]
0x10030c81  mov     ecx, esi; this
0x10030c83  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10030c89  lea     ecx, [edi-10h]
0x10030c8c  call    esi
0x10030c8e  mov     esi, eax
0x10030c90  test    esi, esi
0x10030c92  jnz     short loc_10030C97
0x10030c94  inc     eax
0x10030c95  jmp     short loc_10030CEA
0x10030c97  push    2; dwCoInit
0x10030c99  push    0; pvReserved
0x10030c9b  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10030ca1  lea     eax, [ebp+ppv]
0x10030ca4  push    eax; ppv
0x10030ca5  push    offset _IID_IFilterMapper; riid
0x10030caa  push    1; dwClsContext
0x10030cac  push    0; pUnkOuter
0x10030cae  push    offset _CLSID_FilterMapper; rclsid
0x10030cb3  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10030cb9  test    eax, eax
0x10030cbb  js      short loc_10030CDC
0x10030cbd  mov     edx, [ebp+ppv]
0x10030cc0  mov     ecx, esi
0x10030cc2  push    1
0x10030cc4  call    _AMovieSetupRegisterFilter@12; AMovieSetupRegisterFilter(x,x,x)
0x10030cc9  mov     eax, [ebp+ppv]
0x10030ccc  push    eax
0x10030ccd  mov     ecx, [eax]
0x10030ccf  mov     esi, [ecx+8]
0x10030cd2  mov     ecx, esi; this
0x10030cd4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10030cda  call    esi
0x10030cdc  call    ds:__imp__CoFreeUnusedLibraries@0; CoFreeUnusedLibraries()
0x10030ce2  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10030ce8  xor     eax, eax
0x10030cea  pop     edi
0x10030ceb  pop     esi
0x10030cec  leave
0x10030ced  retn    4
```
