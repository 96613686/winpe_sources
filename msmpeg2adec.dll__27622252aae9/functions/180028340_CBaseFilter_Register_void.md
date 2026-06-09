# CBaseFilter::Register(void)

- ea: `0x180028340`
- end: `0x1800283f7`
- name: `?Register@CBaseFilter@@UEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180028340`
- `0x180028934`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800283a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800283a1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002836e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002836e`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800283d6`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800283d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800283e2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800283e2`

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
0x180028340  push    rbx
0x180028342  sub     rsp, 30h
0x180028346  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18002834a  mov     rax, [rcx]
0x18002834d  mov     rax, [rax+40h]
0x180028351  call    cs:__guard_dispatch_icall_fptr
0x180028357  mov     rbx, rax
0x18002835a  test    rax, rax
0x18002835d  jnz     short loc_180028367
0x18002835f  lea     eax, [rbx+1]
0x180028362  jmp     loc_1800283F0
0x180028367  mov     edx, 2; dwCoInit
0x18002836c  xor     ecx, ecx; pvReserved
0x18002836e  call    cs:__imp_CoInitializeEx
0x180028375  nop     dword ptr [rax+rax+00h]
0x18002837a  xor     edx, edx; pUnkOuter
0x18002837c  mov     [rsp+38h+arg_0], 0
0x180028385  lea     rax, [rsp+38h+arg_0]
0x18002838a  lea     r9, IID_IFilterMapper; riid
0x180028391  mov     [rsp+38h+ppv], rax; ppv
0x180028396  lea     rcx, CLSID_FilterMapper; rclsid
0x18002839d  lea     r8d, [rdx+1]; dwClsContext
0x1800283a1  call    cs:__imp_CoCreateInstance
0x1800283a8  nop     dword ptr [rax+rax+00h]
0x1800283ad  test    eax, eax
0x1800283af  js      short loc_1800283D6
0x1800283b1  mov     rdx, [rsp+38h+arg_0]
0x1800283b6  mov     r8d, 1
0x1800283bc  mov     rcx, rbx
0x1800283bf  call    AMovieSetupRegisterFilter
0x1800283c4  mov     rcx, [rsp+38h+arg_0]
0x1800283c9  mov     rax, [rcx]
0x1800283cc  mov     rax, [rax+10h]
0x1800283d0  call    cs:__guard_dispatch_icall_fptr
0x1800283d6  call    cs:__imp_CoFreeUnusedLibraries
0x1800283dd  nop     dword ptr [rax+rax+00h]
0x1800283e2  call    cs:__imp_CoUninitialize
0x1800283e9  nop     dword ptr [rax+rax+00h]
0x1800283ee  xor     eax, eax
0x1800283f0  add     rsp, 30h
0x1800283f4  pop     rbx
0x1800283f5  retn
```
