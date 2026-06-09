# HrGetPropertiesExFromINetConnection(INetConnection *,tagNETCON_PROPERTIES_EX * *)

- ea: `0x180061524`
- end: `0x180061656`
- name: `?HrGetPropertiesExFromINetConnection@@YAJPEAUINetConnection@@PEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(struct INetConnection *, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a730`

## callees

- `0x180009930`
- `0x1800157f0`
- `0x18001644c`
- `0x18001eb7c`
- `0x180034c18`
- `0x1800613b4`
- `0x180061524`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180061638`
- `ole32!CoTaskMemFree` at `0x180061638`
- `ole32!CoTaskMemAlloc` at `0x18006158b`
- `ole32!CoTaskMemAlloc` at `0x18006158b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HrGetPropertiesExFromINetConnection(struct INetConnection *a1, struct tagNETCON_PROPERTIES_EX **a2)
{
  int v4; // edi
  struct tagNETCON_PROPERTIES_EX *v5; // rax
  struct tagNETCON_PROPERTIES_EX *v6; // rbx
  IUnknown *pProxy; // [rsp+50h] [rbp+30h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+58h] [rbp+38h] BYREF
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
      pProps = 0;
      memset_0(v5, 0, 0x68u);
      v4 = ((__int64 (__fastcall *)(struct INetConnection *, NETCON_PROPERTIES **))a1->lpVtbl->GetProperties)(
             a1,
             &pProps);
      if ( v4 < 0 )
        goto LABEL_11;
      v10 = 0;
      v4 = ((__int64 (__fastcall *)(struct INetConnection *, GUID *, struct IPersistNetConnection **))a1->lpVtbl->QueryInterface)(
             a1,
             &IID_IPersistNetConnection,
             &v10);
      if ( v4 >= 0 )
      {
        v4 = HrBuildPropertiesExFromProperties(pProps, v6, v10);
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
      NcFreeNetconProperties(pProps);
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&v10);
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
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&pProxy);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180061524  push    rbp
0x180061526  push    rbx
0x180061527  push    rsi
0x180061528  push    rdi
0x180061529  push    r14
0x18006152b  mov     rbp, rsp
0x18006152e  sub     rsp, 20h
0x180061532  mov     r14, rdx
0x180061535  mov     rsi, rcx
0x180061538  mov     [rbp+pProxy], 0
0x180061540  mov     qword ptr [rdx], 0
0x180061547  mov     rax, [rcx]
0x18006154a  lea     r8, [rbp+pProxy]
0x18006154e  lea     rdx, IID_INetConnection2
0x180061555  mov     rax, [rax]
0x180061558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006155d  mov     edi, eax
0x18006155f  test    eax, eax
0x180061561  js      short loc_180061586
0x180061563  mov     rcx, [rbp+pProxy]; pProxy
0x180061567  call    ?NcSetProxyBlanket@@YAXPEAUIUnknown@@@Z; NcSetProxyBlanket(IUnknown *)
0x18006156c  mov     rcx, [rbp+pProxy]
0x180061570  mov     rax, [rcx]
0x180061573  mov     rdx, r14
0x180061576  mov     rax, [rax+18h]
0x18006157a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006157f  mov     edi, eax
0x180061581  jmp     loc_18006163F
0x180061586  mov     ecx, 68h ; 'h'; cb
0x18006158b  call    cs:__imp_CoTaskMemAlloc
0x180061591  mov     rbx, rax
0x180061594  test    rax, rax
0x180061597  jz      loc_18006163F
0x18006159d  mov     [rbp+pProps], 0
0x1800615a5  xor     edx, edx; Val
0x1800615a7  lea     r8d, [rdx+68h]; Size
0x1800615ab  mov     rcx, rax; void *
0x1800615ae  call    memset_0
0x1800615b3  mov     rcx, [rsi]
0x1800615b6  mov     rax, [rcx+38h]
0x1800615ba  lea     rdx, [rbp+pProps]
0x1800615be  mov     rcx, rsi
0x1800615c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615c6  mov     edi, eax
0x1800615c8  test    eax, eax
0x1800615ca  js      short loc_180061635
0x1800615cc  mov     [rbp+arg_10], 0
0x1800615d4  mov     rax, [rsi]
0x1800615d7  lea     r8, [rbp+arg_10]
0x1800615db  lea     rdx, IID_IPersistNetConnection
0x1800615e2  mov     rcx, rsi
0x1800615e5  mov     rax, [rax]
0x1800615e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615ed  mov     edi, eax
0x1800615ef  test    eax, eax
0x1800615f1  js      short loc_180061618
0x1800615f3  mov     r8, [rbp+arg_10]; struct IPersistNetConnection *
0x1800615f7  mov     rdx, rbx; struct tagNETCON_PROPERTIES_EX *
0x1800615fa  mov     rcx, [rbp+pProps]; struct tagNETCON_PROPERTIES *
0x1800615fe  call    ?HrBuildPropertiesExFromProperties@@YAJPEAUtagNETCON_PROPERTIES@@PEAUtagNETCON_PROPERTIES_EX@@PEAUIPersistNetConnection@@@Z; HrBuildPropertiesExFromProperties(tagNETCON_PROPERTIES *,tagNETCON_PROPERTIES_EX *,IPersistNetConnection *)
0x180061603  mov     edi, eax
0x180061605  test    eax, eax
0x180061607  js      short loc_18006160E
0x180061609  mov     [r14], rbx
0x18006160c  jmp     short loc_180061618
0x18006160e  mov     rcx, rbx; pv
0x180061611  call    ?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z; HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)
0x180061616  xor     ebx, ebx
0x180061618  mov     rcx, [rbp+pProps]; pProps
0x18006161c  call    NcFreeNetconProperties
0x180061621  nop
0x180061622  lea     rcx, [rbp+arg_10]
0x180061626  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18006162b  nop
0x18006162c  test    edi, edi
0x18006162e  jns     short loc_18006163F
0x180061630  test    rbx, rbx
0x180061633  jz      short loc_18006163F
0x180061635  mov     rcx, rbx; pv
0x180061638  call    cs:__imp_CoTaskMemFree
0x18006163e  nop
0x18006163f  lea     rcx, [rbp+pProxy]
0x180061643  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180061648  nop
0x180061649  mov     eax, edi
0x18006164b  add     rsp, 20h
0x18006164f  pop     r14
0x180061651  pop     rdi
0x180061652  pop     rsi
0x180061653  pop     rbx
0x180061654  pop     rbp
0x180061655  retn
```
