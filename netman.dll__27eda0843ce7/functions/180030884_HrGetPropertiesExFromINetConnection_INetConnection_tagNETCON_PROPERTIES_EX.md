# HrGetPropertiesExFromINetConnection(INetConnection *,tagNETCON_PROPERTIES_EX * *)

- ea: `0x180030884`
- end: `0x1800309b6`
- name: `?HrGetPropertiesExFromINetConnection@@YAJPEAUINetConnection@@PEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(struct INetConnection *, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a3d0`
- `0x18001a5d0`
- `0x18001a6d0`
- `0x18001fb68`
- `0x18001fd40`
- `0x18001fe84`

## callees

- `0x180002320`
- `0x180008168`
- `0x180030648`
- `0x180030714`
- `0x180030884`
- `0x180031d0c`
- `0x180031d44`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800308eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800308eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030998`

## pseudocode

```c
__int64 __fastcall HrGetPropertiesExFromINetConnection(struct INetConnection *a1, struct tagNETCON_PROPERTIES_EX **a2)
{
  int v4; // edi
  struct tagNETCON_PROPERTIES_EX *v5; // rax
  struct tagNETCON_PROPERTIES_EX *v6; // rbx
  IUnknown *pProxy; // [rsp+50h] [rbp+30h] BYREF
  struct tagNETCON_PROPERTIES *pv; // [rsp+58h] [rbp+38h] BYREF
  struct IPersistNetConnection *v10; // [rsp+60h] [rbp+40h] BYREF

  pProxy = 0;
  *a2 = 0;
  v4 = ((__int64 (__fastcall *)(struct INetConnection *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_INetConnection2,
         &pProxy);
  if ( v4 < 0 )
  {
    v5 = (struct tagNETCON_PROPERTIES_EX *)CoTaskMemAlloc(0x68u);
    v6 = v5;
    if ( v5 )
    {
      pv = 0;
      memset_0(v5, 0, 0x68u);
      v4 = ((__int64 (__fastcall *)(struct INetConnection *, struct tagNETCON_PROPERTIES **))a1->lpVtbl->GetProperties)(
             a1,
             &pv);
      if ( v4 < 0 )
        goto LABEL_11;
      v10 = 0;
      v4 = ((__int64 (__fastcall *)(struct INetConnection *, GUID *, struct IPersistNetConnection **))a1->lpVtbl->QueryInterface)(
             a1,
             &IID_IPersistNetConnection,
             &v10);
      if ( v4 >= 0 )
      {
        v4 = HrBuildPropertiesExFromProperties(pv, v6, v10);
        if ( v4 < 0 )
        {
          HrFreeNetConProperties2(v6);
          v6 = 0;
        }
        else
        {
          *a2 = v6;
        }
      }
      FreeNetconProperties(pv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
      if ( v4 < 0 )
      {
        if ( v6 )
LABEL_11:
          CoTaskMemFree(v6);
      }
    }
  }
  else
  {
    NcSetProxyBlanket(pProxy);
    v4 = ((__int64 (__fastcall *)(IUnknown *, struct tagNETCON_PROPERTIES_EX **))pProxy->lpVtbl[1].QueryInterface)(
           pProxy,
           a2);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pProxy);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030884  push    rbp
0x180030886  push    rbx
0x180030887  push    rsi
0x180030888  push    rdi
0x180030889  push    r14
0x18003088b  mov     rbp, rsp
0x18003088e  sub     rsp, 20h
0x180030892  mov     r14, rdx
0x180030895  mov     rsi, rcx
0x180030898  mov     [rbp+pProxy], 0
0x1800308a0  mov     qword ptr [rdx], 0
0x1800308a7  mov     rax, [rcx]
0x1800308aa  lea     r8, [rbp+pProxy]
0x1800308ae  lea     rdx, IID_INetConnection2
0x1800308b5  mov     rax, [rax]
0x1800308b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308bd  mov     edi, eax
0x1800308bf  test    eax, eax
0x1800308c1  js      short loc_1800308E6
0x1800308c3  mov     rcx, [rbp+pProxy]; pProxy
0x1800308c7  call    ?NcSetProxyBlanket@@YAXPEAUIUnknown@@@Z; NcSetProxyBlanket(IUnknown *)
0x1800308cc  mov     rcx, [rbp+pProxy]
0x1800308d0  mov     rax, [rcx]
0x1800308d3  mov     rdx, r14
0x1800308d6  mov     rax, [rax+18h]
0x1800308da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308df  mov     edi, eax
0x1800308e1  jmp     loc_18003099F
0x1800308e6  mov     ecx, 68h ; 'h'; cb
0x1800308eb  call    cs:__imp_CoTaskMemAlloc
0x1800308f1  mov     rbx, rax
0x1800308f4  test    rax, rax
0x1800308f7  jz      loc_18003099F
0x1800308fd  mov     [rbp+pv], 0
0x180030905  xor     edx, edx; Val
0x180030907  lea     r8d, [rdx+68h]; Size
0x18003090b  mov     rcx, rax; void *
0x18003090e  call    memset_0
0x180030913  mov     rcx, [rsi]
0x180030916  mov     rax, [rcx+38h]
0x18003091a  lea     rdx, [rbp+pv]
0x18003091e  mov     rcx, rsi
0x180030921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030926  mov     edi, eax
0x180030928  test    eax, eax
0x18003092a  js      short loc_180030995
0x18003092c  mov     [rbp+arg_10], 0
0x180030934  mov     rax, [rsi]
0x180030937  lea     r8, [rbp+arg_10]
0x18003093b  lea     rdx, IID_IPersistNetConnection
0x180030942  mov     rcx, rsi
0x180030945  mov     rax, [rax]
0x180030948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003094d  mov     edi, eax
0x18003094f  test    eax, eax
0x180030951  js      short loc_180030978
0x180030953  mov     r8, [rbp+arg_10]; struct IPersistNetConnection *
0x180030957  mov     rdx, rbx; struct tagNETCON_PROPERTIES_EX *
0x18003095a  mov     rcx, [rbp+pv]; struct tagNETCON_PROPERTIES *
0x18003095e  call    ?HrBuildPropertiesExFromProperties@@YAJPEAUtagNETCON_PROPERTIES@@PEAUtagNETCON_PROPERTIES_EX@@PEAUIPersistNetConnection@@@Z; HrBuildPropertiesExFromProperties(tagNETCON_PROPERTIES *,tagNETCON_PROPERTIES_EX *,IPersistNetConnection *)
0x180030963  mov     edi, eax
0x180030965  test    eax, eax
0x180030967  js      short loc_18003096E
0x180030969  mov     [r14], rbx
0x18003096c  jmp     short loc_180030978
0x18003096e  mov     rcx, rbx; pv
0x180030971  call    ?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z; HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)
0x180030976  xor     ebx, ebx
0x180030978  mov     rcx, [rbp+pv]; pv
0x18003097c  call    ?FreeNetconProperties@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetconProperties(tagNETCON_PROPERTIES *)
0x180030981  nop
0x180030982  lea     rcx, [rbp+arg_10]
0x180030986  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003098b  nop
0x18003098c  test    edi, edi
0x18003098e  jns     short loc_18003099F
0x180030990  test    rbx, rbx
0x180030993  jz      short loc_18003099F
0x180030995  mov     rcx, rbx; pv
0x180030998  call    cs:__imp_CoTaskMemFree
0x18003099e  nop
0x18003099f  lea     rcx, [rbp+pProxy]
0x1800309a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800309a8  nop
0x1800309a9  mov     eax, edi
0x1800309ab  add     rsp, 20h
0x1800309af  pop     r14
0x1800309b1  pop     rdi
0x1800309b2  pop     rsi
0x1800309b3  pop     rbx
0x1800309b4  pop     rbp
0x1800309b5  retn
```
