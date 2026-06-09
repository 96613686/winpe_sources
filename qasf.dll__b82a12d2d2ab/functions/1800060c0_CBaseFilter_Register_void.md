# CBaseFilter::Register(void)

- ea: `0x1800060c0`
- end: `0x180006159`
- name: `?Register@CBaseFilter@@UEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800060c0`
- `0x180006cb4`
- `0x18001f010`

## import_xrefs

- `ole32!CoUninitialize` at `0x18000614b`
- `ole32!CoUninitialize` at `0x18000614b`
- `ole32!CoFreeUnusedLibraries` at `0x180006145`
- `ole32!CoFreeUnusedLibraries` at `0x180006145`
- `ole32!CoCreateInstance` at `0x180006117`
- `ole32!CoCreateInstance` at `0x180006117`
- `ole32!CoInitializeEx` at `0x1800060ea`
- `ole32!CoInitializeEx` at `0x1800060ea`

## pseudocode

```c
__int64 __fastcall CBaseFilter::Register(CBaseFilter *this)
{
  __int64 v1; // rbx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 4) + 64LL))((char *)this - 32);
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
0x1800060c0  push    rbx
0x1800060c2  sub     rsp, 30h
0x1800060c6  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800060ca  mov     rax, [rcx]
0x1800060cd  mov     rax, [rax+40h]
0x1800060d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d6  mov     rbx, rax
0x1800060d9  test    rax, rax
0x1800060dc  jnz     short loc_1800060E3
0x1800060de  lea     eax, [rbx+1]
0x1800060e1  jmp     short loc_180006153
0x1800060e3  mov     edx, 2; dwCoInit
0x1800060e8  xor     ecx, ecx; pvReserved
0x1800060ea  call    cs:__imp_CoInitializeEx
0x1800060f0  xor     edx, edx; pUnkOuter
0x1800060f2  mov     [rsp+38h+arg_0], 0
0x1800060fb  lea     rax, [rsp+38h+arg_0]
0x180006100  lea     r9, IID_IFilterMapper; riid
0x180006107  mov     [rsp+38h+ppv], rax; ppv
0x18000610c  lea     rcx, CLSID_FilterMapper; rclsid
0x180006113  lea     r8d, [rdx+1]; dwClsContext
0x180006117  call    cs:__imp_CoCreateInstance
0x18000611d  test    eax, eax
0x18000611f  js      short loc_180006145
0x180006121  mov     rdx, [rsp+38h+arg_0]
0x180006126  mov     r8d, 1
0x18000612c  mov     rcx, rbx
0x18000612f  call    AMovieSetupRegisterFilter
0x180006134  mov     rcx, [rsp+38h+arg_0]
0x180006139  mov     rax, [rcx]
0x18000613c  mov     rax, [rax+10h]
0x180006140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006145  call    cs:__imp_CoFreeUnusedLibraries
0x18000614b  call    cs:__imp_CoUninitialize
0x180006151  xor     eax, eax
0x180006153  add     rsp, 30h
0x180006157  pop     rbx
0x180006158  retn
```
