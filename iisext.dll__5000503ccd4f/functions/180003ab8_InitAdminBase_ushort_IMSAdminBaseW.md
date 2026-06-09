# InitAdminBase(ushort *,IMSAdminBaseW * *)

- ea: `0x180003ab8`
- end: `0x180003bcf`
- name: `?InitAdminBase@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct IMSAdminBaseW **)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003bd8`
- `0x180003de8`
- `0x180007a80`
- `0x18000a2dc`

## callees

- `0x180003ab8`
- `0x180003efc`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003af8`
- `msvcrt!_wcsicmp` at `0x180003af8`
- `ole32!CoGetClassObject` at `0x180003b36`
- `ole32!CoGetClassObject` at `0x180003b36`

## pseudocode

```c
__int64 __fastcall InitAdminBase(unsigned __int16 *a1, struct IMSAdminBaseW **a2)
{
  HRESULT ClassObject; // ebx
  unsigned int v4; // edx
  __int128 pvReserved; // [rsp+30h] [rbp-20h] BYREF
  __int128 v7; // [rsp+40h] [rbp-10h]
  IUnknown *pProxy; // [rsp+70h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  struct IMSAdminBaseW *v10; // [rsp+88h] [rbp+38h] BYREF

  ppv = 0;
  v10 = 0;
  pProxy = 0;
  pvReserved = 0;
  v7 = 0;
  if ( !a1 || (*((_QWORD *)&pvReserved + 1) = a1, !_wcsicmp(a1, L"localhost")) )
    *((_QWORD *)&pvReserved + 1) = 0;
  *(_QWORD *)&v7 = 0;
  ClassObject = CoGetClassObject(&CLSID_MSAdminBase_W, 0x15u, &pvReserved, &IID_IClassFactory, &ppv);
  if ( ClassObject >= 0 )
  {
    ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, IUnknown **))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    0,
                    &IID_IMSAdminBase_W,
                    &pProxy);
    if ( ClassObject >= 0 )
    {
      ClassObject = SetProxyImpersonationLevel(pProxy, v4);
      if ( ClassObject >= 0 )
      {
        ClassObject = ((__int64 (__fastcall *)(IUnknown *, struct IMSAdminBaseW **))pProxy->lpVtbl[10].Release)(
                        pProxy,
                        &v10);
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        pProxy = 0;
        if ( ClassObject >= 0 )
          *a2 = v10;
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x180003ab8  push    rbp
0x180003aba  push    rbx
0x180003abb  push    rdi
0x180003abc  mov     rbp, rsp
0x180003abf  sub     rsp, 50h
0x180003ac3  mov     [rbp+arg_10], 0
0x180003acb  xorps   xmm0, xmm0
0x180003ace  mov     [rbp+arg_18], 0
0x180003ad6  mov     rdi, rdx
0x180003ad9  mov     [rbp+pProxy], 0
0x180003ae1  mov     rbx, rcx
0x180003ae4  movups  [rbp+pvReserved], xmm0
0x180003ae8  movups  [rbp+var_10], xmm0
0x180003aec  test    rcx, rcx
0x180003aef  jz      short loc_180003B06
0x180003af1  lea     rdx, aLocalhost; "localhost"
0x180003af8  call    cs:__imp__wcsicmp
0x180003afe  mov     qword ptr [rbp+pvReserved+8], rbx
0x180003b02  test    eax, eax
0x180003b04  jnz     short loc_180003B0E
0x180003b06  mov     qword ptr [rbp+pvReserved+8], 0
0x180003b0e  lea     rax, [rbp+arg_10]
0x180003b12  mov     qword ptr [rbp+var_10], 0
0x180003b1a  lea     r9, IID_IClassFactory; riid
0x180003b21  mov     [rsp+50h+ppv], rax; ppv
0x180003b26  lea     r8, [rbp+pvReserved]; pvReserved
0x180003b2a  mov     edx, 15h; dwClsContext
0x180003b2f  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x180003b36  call    cs:__imp_CoGetClassObject
0x180003b3c  mov     ebx, eax
0x180003b3e  test    eax, eax
0x180003b40  js      short loc_180003BB0
0x180003b42  mov     rcx, [rbp+arg_10]
0x180003b46  lea     r9, [rbp+pProxy]
0x180003b4a  lea     r8, IID_IMSAdminBase_W
0x180003b51  xor     edx, edx
0x180003b53  mov     rax, [rcx]
0x180003b56  mov     rax, [rax+18h]
0x180003b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5f  mov     ebx, eax
0x180003b61  test    eax, eax
0x180003b63  js      short loc_180003BB0
0x180003b65  mov     rcx, [rbp+pProxy]; pProxy
0x180003b69  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x180003b6e  mov     ebx, eax
0x180003b70  test    eax, eax
0x180003b72  js      short loc_180003BB0
0x180003b74  mov     rcx, [rbp+pProxy]
0x180003b78  lea     rdx, [rbp+arg_18]
0x180003b7c  mov     rax, [rcx]
0x180003b7f  mov     rax, [rax+100h]
0x180003b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8b  mov     rcx, [rbp+pProxy]
0x180003b8f  mov     ebx, eax
0x180003b91  mov     rax, [rcx]
0x180003b94  mov     rax, [rax+10h]
0x180003b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9d  mov     [rbp+pProxy], 0
0x180003ba5  test    ebx, ebx
0x180003ba7  js      short loc_180003BB0
0x180003ba9  mov     rax, [rbp+arg_18]
0x180003bad  mov     [rdi], rax
0x180003bb0  mov     rcx, [rbp+arg_10]
0x180003bb4  test    rcx, rcx
0x180003bb7  jz      short loc_180003BC5
0x180003bb9  mov     rax, [rcx]
0x180003bbc  mov     rax, [rax+10h]
0x180003bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc5  mov     eax, ebx
0x180003bc7  add     rsp, 50h
0x180003bcb  pop     rdi
0x180003bcc  pop     rbx
0x180003bcd  pop     rbp
0x180003bce  retn
```
