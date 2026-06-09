# CDomNode::SetSource(IDomNode *)

- ea: `0x1800253a0`
- end: `0x18002547e`
- name: `?SetSource@CDomNode@@UEAAJPEAUIDomNode@@@Z`
- size: `222`
- prototype: `int(CDomNode *__hidden this, struct IDomNode *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800110bc`
- `0x180023b0c`
- `0x180024308`
- `0x1800253a0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025423`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025423`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDomNode::SetSource(CDomNode *this, struct IUnknown *a2)
{
  HRESULT v4; // ebx
  struct IUnknown **v5; // rdi
  LPVOID v6; // rcx
  LPVOID ppv; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  ppv = 0;
  v5 = (struct IUnknown **)((char *)this + 168);
  ATL::CComPtrBase<IDomNode>::Release((char *)this + 168);
  if ( *v5 != a2 )
    ATL::AtlComPtrAssign(v5, a2);
  if ( *v5 )
  {
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))(*v5)->lpVtbl[5].Release)(*v5, &ppv);
    if ( v4 >= 0 )
    {
      v6 = ppv;
      if ( ppv )
      {
LABEL_9:
        v4 = (*(__int64 (__fastcall **)(LPVOID, CDomNode *))(*(_QWORD *)v6 + 40LL))(v6, this);
        goto LABEL_10;
      }
      v4 = CoCreateInstance(
             &GUID_dab7ccb2_ec94_4c7e_ab52_826d6acd5249,
             0,
             1u,
             &GUID_dfcdb0e8_cb00_417b_82fb_1b6ac10a44a9,
             &ppv);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID))(*v5)->lpVtbl[5].AddRef)(*v5, ppv);
        if ( v4 >= 0 )
        {
          v6 = ppv;
          goto LABEL_9;
        }
      }
    }
  }
LABEL_10:
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800253a0  push    rbx
0x1800253a2  push    rbp
0x1800253a3  push    rsi
0x1800253a4  push    rdi
0x1800253a5  sub     rsp, 38h
0x1800253a9  mov     rsi, rdx
0x1800253ac  mov     rbp, rcx
0x1800253af  xor     ebx, ebx
0x1800253b1  mov     [rsp+58h+arg_0], rbx
0x1800253b6  lea     rdi, [rcx+0A8h]
0x1800253bd  mov     rcx, rdi
0x1800253c0  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x1800253c5  cmp     [rdi], rsi
0x1800253c8  jz      short loc_1800253D5
0x1800253ca  mov     rdx, rsi; struct IUnknown *
0x1800253cd  mov     rcx, rdi; struct IUnknown **
0x1800253d0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800253d5  mov     rcx, [rdi]
0x1800253d8  test    rcx, rcx
0x1800253db  jz      loc_180025468
0x1800253e1  mov     rax, [rcx]
0x1800253e4  lea     rdx, [rsp+58h+arg_0]
0x1800253e9  mov     rax, [rax+88h]
0x1800253f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253f5  mov     ebx, eax
0x1800253f7  test    eax, eax
0x1800253f9  js      short loc_180025468
0x1800253fb  mov     rcx, [rsp+58h+arg_0]
0x180025400  test    rcx, rcx
0x180025403  jnz     short loc_180025457
0x180025405  lea     rax, [rsp+58h+arg_0]
0x18002540a  mov     [rsp+58h+ppv], rax; ppv
0x18002540f  lea     r9, _GUID_dfcdb0e8_cb00_417b_82fb_1b6ac10a44a9; riid
0x180025416  xor     edx, edx; pUnkOuter
0x180025418  lea     r8d, [rcx+1]; dwClsContext
0x18002541c  lea     rcx, _GUID_dab7ccb2_ec94_4c7e_ab52_826d6acd5249; rclsid
0x180025423  call    cs:__imp_CoCreateInstance
0x18002542a  nop     dword ptr [rax+rax+00h]
0x18002542f  mov     ebx, eax
0x180025431  test    eax, eax
0x180025433  js      short loc_180025468
0x180025435  mov     rcx, [rdi]
0x180025438  mov     rax, [rcx]
0x18002543b  mov     rdx, [rsp+58h+arg_0]
0x180025440  mov     rax, [rax+80h]
0x180025447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002544c  mov     ebx, eax
0x18002544e  test    eax, eax
0x180025450  js      short loc_180025468
0x180025452  mov     rcx, [rsp+58h+arg_0]
0x180025457  mov     rax, [rcx]
0x18002545a  mov     rdx, rbp
0x18002545d  mov     rax, [rax+28h]
0x180025461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025466  mov     ebx, eax
0x180025468  lea     rcx, [rsp+58h+arg_0]
0x18002546d  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180025472  mov     eax, ebx
0x180025474  add     rsp, 38h
0x180025478  pop     rdi
0x180025479  pop     rsi
0x18002547a  pop     rbp
0x18002547b  pop     rbx
0x18002547c  retn
```
