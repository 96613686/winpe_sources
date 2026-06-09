# ProxyWindow::PromoteWindowHelper(HWND__ *)

- ea: `0x1800a7528`
- end: `0x1800a7646`
- name: `?PromoteWindowHelper@ProxyWindow@@AEAAJPEAUHWND__@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(ProxyWindow *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180061ab4`

## callees

- `0x180014750`
- `0x1800a7528`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a761a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a761a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a7599`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a7599`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a7559`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a756c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a7559`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a756c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProxyWindow::PromoteWindowHelper(ProxyWindow *this, HWND a2)
{
  HRESULT v3; // ebx
  __int64 v4; // rcx
  LPVOID v5; // rcx
  __int64 v7; // [rsp+40h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+20h] BYREF

  ppv = 0;
  v7 = 0;
  v3 = CoInitializeEx(0, 2u);
  if ( v3 == -2147417850 )
    v3 = CoInitializeEx(0, 0);
  if ( v3 >= 0 )
  {
    v3 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &ppv);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             &GUID_bdd61328_14f8_4dff_8b7b_92be622ae360,
             &GUID_bdd61328_14f8_4dff_8b7b_92be622ae360,
             &v7);
      if ( v3 >= 0 )
        v3 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v7 + 24LL))(v7, a2);
    }
    v4 = v7;
    if ( v7 )
    {
      v7 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    v5 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    }
    CoUninitialize();
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800a7528  mov     [rsp-8+arg_8], rbx
0x1800a752d  mov     [rsp-8+arg_18], rdi
0x1800a7532  mov     [rsp-8+arg_0], rcx
0x1800a7537  push    rbp
0x1800a7538  mov     rbp, rsp
0x1800a753b  sub     rsp, 30h
0x1800a753f  mov     rdi, rdx
0x1800a7542  mov     [rbp+arg_10], 0
0x1800a754a  mov     [rbp+arg_0], 0
0x1800a7552  mov     edx, 2; dwCoInit
0x1800a7557  xor     ecx, ecx; pvReserved
0x1800a7559  call    cs:__imp_CoInitializeEx
0x1800a755f  mov     ebx, eax
0x1800a7561  cmp     eax, 80010106h
0x1800a7566  jnz     short loc_1800A7574
0x1800a7568  xor     edx, edx; dwCoInit
0x1800a756a  xor     ecx, ecx; pvReserved
0x1800a756c  call    cs:__imp_CoInitializeEx
0x1800a7572  mov     ebx, eax
0x1800a7574  test    ebx, ebx
0x1800a7576  js      loc_1800A7621
0x1800a757c  lea     rax, [rbp+arg_10]
0x1800a7580  mov     [rsp+30h+ppv], rax; ppv
0x1800a7585  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x1800a758c  xor     edx, edx; pUnkOuter
0x1800a758e  lea     r8d, [rdx+4]; dwClsContext
0x1800a7592  lea     rcx, CLSID_ImmersiveShell; rclsid
0x1800a7599  call    cs:__imp_CoCreateInstance
0x1800a759f  mov     ebx, eax
0x1800a75a1  test    eax, eax
0x1800a75a3  js      short loc_1800A75DE
0x1800a75a5  mov     rcx, [rbp+arg_10]
0x1800a75a9  mov     rax, [rcx]
0x1800a75ac  lea     r9, [rbp+arg_0]
0x1800a75b0  lea     rdx, _GUID_bdd61328_14f8_4dff_8b7b_92be622ae360
0x1800a75b7  mov     r8, rdx
0x1800a75ba  mov     rax, [rax+18h]
0x1800a75be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75c3  mov     ebx, eax
0x1800a75c5  test    eax, eax
0x1800a75c7  js      short loc_1800A75DE
0x1800a75c9  mov     rcx, [rbp+arg_0]
0x1800a75cd  mov     rax, [rcx]
0x1800a75d0  mov     rdx, rdi
0x1800a75d3  mov     rax, [rax+18h]
0x1800a75d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75dc  mov     ebx, eax
0x1800a75de  mov     rcx, [rbp+arg_0]
0x1800a75e2  test    rcx, rcx
0x1800a75e5  jz      short loc_1800A75FC
0x1800a75e7  mov     [rbp+arg_0], 0
0x1800a75ef  mov     rax, [rcx]
0x1800a75f2  mov     rax, [rax+10h]
0x1800a75f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75fb  nop
0x1800a75fc  mov     rcx, [rbp+arg_10]
0x1800a7600  test    rcx, rcx
0x1800a7603  jz      short loc_1800A761A
0x1800a7605  mov     [rbp+arg_10], 0
0x1800a760d  mov     rax, [rcx]
0x1800a7610  mov     rax, [rax+10h]
0x1800a7614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7619  nop
0x1800a761a  call    cs:__imp_CoUninitialize
0x1800a7620  nop
0x1800a7621  lea     rcx, [rbp+arg_0]
0x1800a7625  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a762a  nop
0x1800a762b  lea     rcx, [rbp+arg_10]
0x1800a762f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a7634  mov     eax, ebx
0x1800a7636  mov     rbx, [rsp+30h+arg_8]
0x1800a763b  mov     rdi, [rsp+30h+arg_18]
0x1800a7640  add     rsp, 30h
0x1800a7644  pop     rbp
0x1800a7645  retn
```
