# CBaseFilter::Register(void)

- ea: `0x18003f5f0`
- end: `0x18003f6a5`
- name: `?Register@CBaseFilter@@UEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18003f5f0`
- `0x18003fd30`
- `0x180045010`

## import_xrefs

- `ole32!CoUninitialize` at `0x18003f690`
- `ole32!CoUninitialize` at `0x18003f690`
- `ole32!CoFreeUnusedLibraries` at `0x18003f684`
- `ole32!CoFreeUnusedLibraries` at `0x18003f684`
- `ole32!CoInitializeEx` at `0x18003f61d`
- `ole32!CoInitializeEx` at `0x18003f61d`
- `ole32!CoCreateInstance` at `0x18003f650`
- `ole32!CoCreateInstance` at `0x18003f650`

## pseudocode

```c
__int64 __fastcall CBaseFilter::Register(CBaseFilter *this)
{
  __int64 v1; // rbx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = (*((__int64 (__fastcall **)(wchar_t **))this[-1].m_pName + 8))(&this[-1].m_pName);
  if ( !v1 )
    return 1;
  CoInitializeEx(0, 2u);
  ppv = 0;
  if ( CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &ppv) >= 0 )
  {
    AMovieSetupRegisterFilter(v1, ppv, 1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  CoFreeUnusedLibraries();
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18003f5f0  push    rbx
0x18003f5f2  sub     rsp, 30h
0x18003f5f6  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18003f5fa  mov     rax, [rcx]
0x18003f5fd  mov     rax, [rax+40h]
0x18003f601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f606  mov     rbx, rax
0x18003f609  test    rax, rax
0x18003f60c  jnz     short loc_18003F616
0x18003f60e  lea     eax, [rbx+1]
0x18003f611  jmp     loc_18003F69E
0x18003f616  mov     edx, 2; dwCoInit
0x18003f61b  xor     ecx, ecx; pvReserved
0x18003f61d  call    cs:__imp_CoInitializeEx
0x18003f624  nop     dword ptr [rax+rax+00h]
0x18003f629  xor     edx, edx; pUnkOuter
0x18003f62b  mov     [rsp+38h+arg_0], 0
0x18003f634  lea     rax, [rsp+38h+arg_0]
0x18003f639  lea     r9, IID_IFilterMapper; riid
0x18003f640  mov     [rsp+38h+ppv], rax; ppv
0x18003f645  lea     rcx, CLSID_FilterMapper; rclsid
0x18003f64c  lea     r8d, [rdx+1]; dwClsContext
0x18003f650  call    cs:__imp_CoCreateInstance
0x18003f657  nop     dword ptr [rax+rax+00h]
0x18003f65c  test    eax, eax
0x18003f65e  js      short loc_18003F684
0x18003f660  mov     rdx, [rsp+38h+arg_0]
0x18003f665  mov     r8d, 1
0x18003f66b  mov     rcx, rbx
0x18003f66e  call    AMovieSetupRegisterFilter
0x18003f673  mov     rcx, [rsp+38h+arg_0]
0x18003f678  mov     rax, [rcx]
0x18003f67b  mov     rax, [rax+10h]
0x18003f67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f684  call    cs:__imp_CoFreeUnusedLibraries
0x18003f68b  nop     dword ptr [rax+rax+00h]
0x18003f690  call    cs:__imp_CoUninitialize
0x18003f697  nop     dword ptr [rax+rax+00h]
0x18003f69c  xor     eax, eax
0x18003f69e  add     rsp, 30h
0x18003f6a2  pop     rbx
0x18003f6a3  retn
```
