# CBaseFilter::Unregister(void)

- ea: `0x180006c00`
- end: `0x180006cae`
- name: `?Unregister@CBaseFilter@@UEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180006c00`
- `0x180006cb4`
- `0x18001f010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180006c90`
- `ole32!CoUninitialize` at `0x180006c90`
- `ole32!CoFreeUnusedLibraries` at `0x180006c8a`
- `ole32!CoFreeUnusedLibraries` at `0x180006c8a`
- `ole32!CoCreateInstance` at `0x180006c5b`
- `ole32!CoCreateInstance` at `0x180006c5b`
- `ole32!CoInitializeEx` at `0x180006c2e`
- `ole32!CoInitializeEx` at `0x180006c2e`

## pseudocode

```c
__int64 __fastcall CBaseFilter::Unregister(CBaseFilter *this)
{
  __int64 v1; // rdi
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 4) + 64LL))((char *)this - 32);
  if ( !v1 )
    return 1;
  CoInitializeEx(0, 2u);
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &ppv);
  if ( v3 >= 0 )
  {
    v3 = AMovieSetupRegisterFilter(v1, ppv, 0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  CoFreeUnusedLibraries();
  CoUninitialize();
  if ( v3 == -2147024894 )
    return 0;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006c00  mov     [rsp+arg_8], rbx
0x180006c05  push    rdi
0x180006c06  sub     rsp, 30h
0x180006c0a  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180006c0e  mov     rax, [rcx]
0x180006c11  mov     rax, [rax+40h]
0x180006c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c1a  mov     rdi, rax
0x180006c1d  test    rax, rax
0x180006c20  jnz     short loc_180006C27
0x180006c22  lea     eax, [rdi+1]
0x180006c25  jmp     short loc_180006CA3
0x180006c27  mov     edx, 2; dwCoInit
0x180006c2c  xor     ecx, ecx; pvReserved
0x180006c2e  call    cs:__imp_CoInitializeEx
0x180006c34  xor     edx, edx; pUnkOuter
0x180006c36  mov     [rsp+38h+arg_0], 0
0x180006c3f  lea     rax, [rsp+38h+arg_0]
0x180006c44  lea     r9, IID_IFilterMapper; riid
0x180006c4b  mov     [rsp+38h+ppv], rax; ppv
0x180006c50  lea     rcx, CLSID_FilterMapper; rclsid
0x180006c57  lea     r8d, [rdx+1]; dwClsContext
0x180006c5b  call    cs:__imp_CoCreateInstance
0x180006c61  mov     ebx, eax
0x180006c63  test    eax, eax
0x180006c65  js      short loc_180006C8A
0x180006c67  mov     rdx, [rsp+38h+arg_0]
0x180006c6c  xor     r8d, r8d
0x180006c6f  mov     rcx, rdi
0x180006c72  call    AMovieSetupRegisterFilter
0x180006c77  mov     rcx, [rsp+38h+arg_0]
0x180006c7c  mov     ebx, eax
0x180006c7e  mov     rax, [rcx]
0x180006c81  mov     rax, [rax+10h]
0x180006c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8a  call    cs:__imp_CoFreeUnusedLibraries
0x180006c90  call    cs:__imp_CoUninitialize
0x180006c96  xor     eax, eax
0x180006c98  cmp     ebx, 80070002h
0x180006c9e  cmovz   ebx, eax
0x180006ca1  mov     eax, ebx
0x180006ca3  mov     rbx, [rsp+38h+arg_8]
0x180006ca8  add     rsp, 30h
0x180006cac  pop     rdi
0x180006cad  retn
```
