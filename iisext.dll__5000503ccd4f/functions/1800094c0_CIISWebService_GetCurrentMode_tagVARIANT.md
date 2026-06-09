# CIISWebService::GetCurrentMode(tagVARIANT *)

- ea: `0x1800094c0`
- end: `0x180009646`
- name: `?GetCurrentMode@CIISWebService@@UEAAJPEAUtagVARIANT@@@Z`
- size: `390`
- prototype: `int(CIISWebService *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003efc`
- `0x1800094c0`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000951a`
- `msvcrt!_wcsicmp` at `0x18000951a`
- `ole32!CoGetClassObject` at `0x18000955e`
- `ole32!CoGetClassObject` at `0x18000955e`
- `OLEAUT32!__imp_VariantInit` at `0x1800095ec`
- `OLEAUT32!__imp_VariantInit` at `0x1800095ec`

## pseudocode

```c
__int64 __fastcall CIISWebService::GetCurrentMode(CIISWebService *this, struct tagVARIANT *a2)
{
  int ClassObject; // ebx
  const wchar_t *v5; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-30h] BYREF
  __int128 pvReserved; // [rsp+38h] [rbp-28h] BYREF
  __int128 v9; // [rsp+48h] [rbp-18h]
  LONG v10; // [rsp+88h] [rbp+28h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp+30h] BYREF
  IUnknown *v12; // [rsp+98h] [rbp+38h] BYREF

  v10 = 0;
  ppv = 0;
  pProxy = 0;
  v12 = 0;
  if ( a2 )
  {
    v5 = (const wchar_t *)*((_QWORD *)this + 8);
    pvReserved = 0;
    v9 = 0;
    if ( v5 && _wcsicmp(v5, L"localhost") )
      *((_QWORD *)&pvReserved + 1) = *((_QWORD *)this + 8);
    else
      *((_QWORD *)&pvReserved + 1) = 0;
    *(_QWORD *)&v9 = 0;
    ClassObject = CoGetClassObject(&CLSID_WamAdmin, 0x15u, &pvReserved, &IID_IClassFactory, &ppv);
    if ( ClassObject >= 0 )
    {
      ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, IUnknown **))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      0,
                      &IID_IWamAdmin,
                      &pProxy);
      if ( ClassObject >= 0 )
      {
        ClassObject = SetProxyImpersonationLevel(pProxy);
        if ( ClassObject >= 0 )
        {
          ClassObject = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
                          pProxy,
                          &IID_IIISApplicationAdmin,
                          &v12);
          if ( ClassObject >= 0 )
          {
            ClassObject = SetProxyImpersonationLevel(v12);
            if ( ClassObject >= 0 )
            {
              ClassObject = ((__int64 (__fastcall *)(IUnknown *, LONG *))v12->lpVtbl[3].QueryInterface)(v12, &v10);
              if ( ClassObject >= 0 )
              {
                VariantInit(a2);
                a2->lVal = v10;
                a2->vt = 3;
              }
            }
          }
        }
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    if ( v12 )
      ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x1800094c0  push    rbp
0x1800094c2  push    rbx
0x1800094c3  push    rdi
0x1800094c4  mov     rbp, rsp
0x1800094c7  sub     rsp, 60h
0x1800094cb  mov     [rbp+arg_8], 0
0x1800094d2  mov     rdi, rdx
0x1800094d5  mov     [rbp+var_30], 0
0x1800094dd  mov     rbx, rcx
0x1800094e0  mov     [rbp+pProxy], 0
0x1800094e8  mov     [rbp+arg_18], 0
0x1800094f0  test    rdx, rdx
0x1800094f3  jnz     short loc_1800094FF
0x1800094f5  mov     ebx, 80004003h
0x1800094fa  jmp     loc_18000963C
0x1800094ff  mov     rcx, [rcx+40h]; String1
0x180009503  xorps   xmm0, xmm0
0x180009506  movups  [rbp+pvReserved], xmm0
0x18000950a  movups  [rbp+var_18], xmm0
0x18000950e  test    rcx, rcx
0x180009511  jz      short loc_18000952E
0x180009513  lea     rdx, aLocalhost; "localhost"
0x18000951a  call    cs:__imp__wcsicmp
0x180009520  test    eax, eax
0x180009522  jz      short loc_18000952E
0x180009524  mov     rax, [rbx+40h]
0x180009528  mov     qword ptr [rbp+pvReserved+8], rax
0x18000952c  jmp     short loc_180009536
0x18000952e  mov     qword ptr [rbp+pvReserved+8], 0
0x180009536  lea     rax, [rbp+var_30]
0x18000953a  mov     qword ptr [rbp+var_18], 0
0x180009542  lea     r9, IID_IClassFactory; riid
0x180009549  mov     [rsp+60h+ppv], rax; ppv
0x18000954e  lea     r8, [rbp+pvReserved]; pvReserved
0x180009552  mov     edx, 15h; dwClsContext
0x180009557  lea     rcx, CLSID_WamAdmin; rclsid
0x18000955e  call    cs:__imp_CoGetClassObject
0x180009564  mov     ebx, eax
0x180009566  test    eax, eax
0x180009568  js      loc_1800095FD
0x18000956e  mov     rcx, [rbp+var_30]
0x180009572  lea     r9, [rbp+pProxy]
0x180009576  lea     r8, IID_IWamAdmin
0x18000957d  xor     edx, edx
0x18000957f  mov     rax, [rcx]
0x180009582  mov     rax, [rax+18h]
0x180009586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958b  mov     ebx, eax
0x18000958d  test    eax, eax
0x18000958f  js      short loc_1800095FD
0x180009591  mov     rcx, [rbp+pProxy]; pProxy
0x180009595  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x18000959a  mov     ebx, eax
0x18000959c  test    eax, eax
0x18000959e  js      short loc_1800095FD
0x1800095a0  mov     rcx, [rbp+pProxy]
0x1800095a4  lea     r8, [rbp+arg_18]
0x1800095a8  lea     rdx, IID_IIISApplicationAdmin
0x1800095af  mov     rax, [rcx]
0x1800095b2  mov     rax, [rax]
0x1800095b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ba  mov     ebx, eax
0x1800095bc  test    eax, eax
0x1800095be  js      short loc_1800095FD
0x1800095c0  mov     rcx, [rbp+arg_18]; pProxy
0x1800095c4  call    ?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z; SetProxyImpersonationLevel(IUnknown *,ulong)
0x1800095c9  mov     ebx, eax
0x1800095cb  test    eax, eax
0x1800095cd  js      short loc_1800095FD
0x1800095cf  mov     rcx, [rbp+arg_18]
0x1800095d3  lea     rdx, [rbp+arg_8]
0x1800095d7  mov     rax, [rcx]
0x1800095da  mov     rax, [rax+48h]
0x1800095de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e3  mov     ebx, eax
0x1800095e5  test    eax, eax
0x1800095e7  js      short loc_1800095FD
0x1800095e9  mov     rcx, rdi; pvarg
0x1800095ec  call    cs:__imp_VariantInit
0x1800095f2  mov     eax, [rbp+arg_8]
0x1800095f5  mov     [rdi+8], eax
0x1800095f8  mov     word ptr [rdi], 3
0x1800095fd  mov     rcx, [rbp+var_30]
0x180009601  test    rcx, rcx
0x180009604  jz      short loc_180009612
0x180009606  mov     rax, [rcx]
0x180009609  mov     rax, [rax+10h]
0x18000960d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009612  mov     rcx, [rbp+pProxy]
0x180009616  test    rcx, rcx
0x180009619  jz      short loc_180009627
0x18000961b  mov     rax, [rcx]
0x18000961e  mov     rax, [rax+10h]
0x180009622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009627  mov     rcx, [rbp+arg_18]
0x18000962b  test    rcx, rcx
0x18000962e  jz      short loc_18000963C
0x180009630  mov     rax, [rcx]
0x180009633  mov     rax, [rax+10h]
0x180009637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000963c  mov     eax, ebx
0x18000963e  add     rsp, 60h
0x180009642  pop     rdi
0x180009643  pop     rbx
0x180009644  pop     rbp
0x180009645  retn
```
