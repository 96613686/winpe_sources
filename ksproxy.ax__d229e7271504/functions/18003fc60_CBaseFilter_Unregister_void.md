# CBaseFilter::Unregister(void)

- ea: `0x18003fc60`
- end: `0x18003fd2a`
- name: `?Unregister@CBaseFilter@@UEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18003fc60`
- `0x18003fd30`
- `0x180045010`

## import_xrefs

- `ole32!CoUninitialize` at `0x18003fd05`
- `ole32!CoUninitialize` at `0x18003fd05`
- `ole32!CoFreeUnusedLibraries` at `0x18003fcf9`
- `ole32!CoFreeUnusedLibraries` at `0x18003fcf9`
- `ole32!CoInitializeEx` at `0x18003fc91`
- `ole32!CoInitializeEx` at `0x18003fc91`
- `ole32!CoCreateInstance` at `0x18003fcc4`
- `ole32!CoCreateInstance` at `0x18003fcc4`

## pseudocode

```c
__int64 __fastcall CBaseFilter::Unregister(CBaseFilter *this)
{
  __int64 v1; // rdi
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = (*((__int64 (__fastcall **)(wchar_t **))this[-1].m_pName + 8))(&this[-1].m_pName);
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
0x18003fc60  mov     [rsp+arg_8], rbx
0x18003fc65  push    rdi
0x18003fc66  sub     rsp, 30h
0x18003fc6a  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18003fc6e  mov     rax, [rcx]
0x18003fc71  mov     rax, [rax+40h]
0x18003fc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc7a  mov     rdi, rax
0x18003fc7d  test    rax, rax
0x18003fc80  jnz     short loc_18003FC8A
0x18003fc82  lea     eax, [rdi+1]
0x18003fc85  jmp     loc_18003FD1E
0x18003fc8a  mov     edx, 2; dwCoInit
0x18003fc8f  xor     ecx, ecx; pvReserved
0x18003fc91  call    cs:__imp_CoInitializeEx
0x18003fc98  nop     dword ptr [rax+rax+00h]
0x18003fc9d  xor     edx, edx; pUnkOuter
0x18003fc9f  mov     [rsp+38h+arg_0], 0
0x18003fca8  lea     rax, [rsp+38h+arg_0]
0x18003fcad  lea     r9, IID_IFilterMapper; riid
0x18003fcb4  mov     [rsp+38h+ppv], rax; ppv
0x18003fcb9  lea     rcx, CLSID_FilterMapper; rclsid
0x18003fcc0  lea     r8d, [rdx+1]; dwClsContext
0x18003fcc4  call    cs:__imp_CoCreateInstance
0x18003fccb  nop     dword ptr [rax+rax+00h]
0x18003fcd0  mov     ebx, eax
0x18003fcd2  test    eax, eax
0x18003fcd4  js      short loc_18003FCF9
0x18003fcd6  mov     rdx, [rsp+38h+arg_0]
0x18003fcdb  xor     r8d, r8d
0x18003fcde  mov     rcx, rdi
0x18003fce1  call    AMovieSetupRegisterFilter
0x18003fce6  mov     rcx, [rsp+38h+arg_0]
0x18003fceb  mov     ebx, eax
0x18003fced  mov     rax, [rcx]
0x18003fcf0  mov     rax, [rax+10h]
0x18003fcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcf9  call    cs:__imp_CoFreeUnusedLibraries
0x18003fd00  nop     dword ptr [rax+rax+00h]
0x18003fd05  call    cs:__imp_CoUninitialize
0x18003fd0c  nop     dword ptr [rax+rax+00h]
0x18003fd11  xor     eax, eax
0x18003fd13  cmp     ebx, 80070002h
0x18003fd19  cmovz   ebx, eax
0x18003fd1c  mov     eax, ebx
0x18003fd1e  mov     rbx, [rsp+38h+arg_8]
0x18003fd23  add     rsp, 30h
0x18003fd27  pop     rdi
0x18003fd28  retn
```
