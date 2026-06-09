# ATL::CComControlBase::DoVerbProperties(tagRECT const *,HWND__ *)

- ea: `0x1800c87ac`
- end: `0x1800c89ad`
- name: `?DoVerbProperties@CComControlBase@ATL@@QEAAJPEBUtagRECT@@PEAUHWND__@@@Z`
- size: `513`
- prototype: `int(ATL::CComControlBase *__hidden this, const struct tagRECT *, HWND)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c8510`
- `0x1800c86dc`

## callees

- `0x180006b38`
- `0x1800149b0`
- `0x180016984`
- `0x1800c1918`
- `0x1800c87ac`
- `0x1800f8010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c8958`
- `ole32!CoTaskMemFree` at `0x1800c8969`
- `ole32!CoTaskMemFree` at `0x1800c8958`
- `ole32!CoTaskMemFree` at `0x1800c8969`
- `OLEAUT32!__imp_VariantClear` at `0x1800c88f8`
- `OLEAUT32!__imp_VariantClear` at `0x1800c88f8`
- `OLEAUT32!__imp_OleCreatePropertyFrame` at `0x1800c894c`
- `OLEAUT32!__imp_OleCreatePropertyFrame` at `0x1800c894c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComControlBase::DoVerbProperties(ATL::CComControlBase *this, IUnknown *a2, HWND a3)
{
  HRESULT v5; // ebx
  VARTYPE vt; // ax
  int Property; // esi
  struct IDispatch *v8; // rcx
  LCID lcid; // ebx
  LPCOLESTR lpszCaption; // [rsp+60h] [rbp-9h] BYREF
  __int64 v12; // [rsp+68h] [rbp-1h] BYREF
  ULONG cPages[4]; // [rsp+70h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp+17h] BYREF
  struct IUnknown *v15; // [rsp+D0h] [rbp+67h] BYREF
  LPUNKNOWN ppUnk; // [rsp+D8h] [rbp+6Fh] BYREF
  struct IUnknown *v17; // [rsp+E8h] [rbp+7Fh] BYREF

  ppUnk = a2;
  v17 = 0;
  v15 = 0;
  ATL::CComQIPtr<IOleControlSite,&_GUID const IID_IOleControlSite>::CComQIPtr<IOleControlSite,&_GUID const IID_IOleControlSite>(
    &v12,
    *((_QWORD *)this + 4));
  if ( !v12 || (v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12), v5 < 0) )
  {
    ppUnk = 0;
    (*(void (__fastcall **)(ATL::CComControlBase *, GUID *, LPUNKNOWN *))(*(_QWORD *)this + 8LL))(
      this,
      &IID_IUnknown,
      &ppUnk);
    *(_OWORD *)cPages = 0;
    ATL::AtlComQIPtrAssign(&v17, ppUnk, &IID_ISpecifyPropertyPages);
    if ( v17 )
    {
      v5 = ((__int64 (__fastcall *)(struct IUnknown *, ULONG *))v17->lpVtbl[1].QueryInterface)(v17, cPages);
      if ( v5 >= 0 )
      {
        ATL::AtlComQIPtrAssign(&v15, ppUnk, &IID_IOleObject);
        if ( v15 )
        {
          lpszCaption = 0;
          ((void (__fastcall *)(struct IUnknown *, __int64, LPCOLESTR *))v15->lpVtbl[5].AddRef)(v15, 2, &lpszCaption);
          vt = 0;
          memset(&pvarg, 0, sizeof(pvarg));
          pvarg.vt = 0;
          Property = -2147467259;
          v8 = (struct IDispatch *)*((_QWORD *)this + 6);
          if ( v8 )
          {
            Property = ATL::CComDispatchDriver::GetProperty(v8, -705, &pvarg);
            vt = pvarg.vt;
          }
          lcid = pvarg.cyVal.Lo;
          if ( vt == 4095 )
            pvarg.vt = 8;
          VariantClear(&pvarg);
          if ( Property < 0 )
            lcid = 1024;
          v5 = OleCreatePropertyFrame(
                 a3,
                 *((_DWORD *)this + 19),
                 *((_DWORD *)this + 18),
                 lpszCaption,
                 1u,
                 &ppUnk,
                 cPages[0],
                 *(LPCLSID *)&cPages[2],
                 lcid,
                 0,
                 0);
          CoTaskMemFree((LPVOID)lpszCaption);
        }
        else
        {
          v5 = 262529;
        }
        CoTaskMemFree(*(LPVOID *)&cPages[2]);
      }
    }
    else
    {
      v5 = 262529;
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppUnk);
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v12);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v15);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c87ac  mov     [rsp-8+arg_8], rdx
0x1800c87b1  push    rbp
0x1800c87b2  push    rbx
0x1800c87b3  push    rsi
0x1800c87b4  push    rdi
0x1800c87b5  push    r14
0x1800c87b7  lea     rbp, [rsp-37h]
0x1800c87bc  sub     rsp, 0A0h
0x1800c87c3  mov     r14, r8
0x1800c87c6  mov     rdi, rcx
0x1800c87c9  mov     [rbp+57h+arg_18], 0
0x1800c87d1  mov     [rbp+57h+arg_0], 0
0x1800c87d9  mov     rdx, [rcx+20h]
0x1800c87dd  lea     rcx, [rbp+57h+var_58]
0x1800c87e1  call    ??0?$CComQIPtr@UIOleControlSite@@$1?IID_IOleControlSite@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IOleControlSite,&_GUID const IID_IOleControlSite>::CComQIPtr<IOleControlSite,&_GUID const IID_IOleControlSite>(IUnknown *)
0x1800c87e6  nop
0x1800c87e7  mov     rcx, [rbp+57h+var_58]
0x1800c87eb  test    rcx, rcx
0x1800c87ee  jz      short loc_1800C8806
0x1800c87f0  mov     rax, [rcx]
0x1800c87f3  mov     rax, [rax+48h]
0x1800c87f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c87fc  mov     ebx, eax
0x1800c87fe  test    eax, eax
0x1800c8800  jns     loc_1800C8980
0x1800c8806  mov     [rbp+57h+arg_8], 0
0x1800c880e  mov     rax, [rdi]
0x1800c8811  lea     r8, [rbp+57h+arg_8]
0x1800c8815  lea     rdx, IID_IUnknown
0x1800c881c  mov     rcx, rdi
0x1800c881f  mov     rax, [rax+8]
0x1800c8823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8828  xorps   xmm0, xmm0
0x1800c882b  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800c882f  lea     r8, IID_ISpecifyPropertyPages; struct _GUID *
0x1800c8836  mov     rdx, [rbp+57h+arg_8]; struct IUnknown *
0x1800c883a  lea     rcx, [rbp+57h+arg_18]; struct IUnknown **
0x1800c883e  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x1800c8843  mov     rcx, [rbp+57h+arg_18]
0x1800c8847  test    rcx, rcx
0x1800c884a  jz      loc_1800C8971
0x1800c8850  mov     rax, [rcx]
0x1800c8853  lea     rdx, [rbp+57h+var_50]
0x1800c8857  mov     rax, [rax+18h]
0x1800c885b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8860  mov     ebx, eax
0x1800c8862  test    eax, eax
0x1800c8864  js      loc_1800C8976
0x1800c886a  lea     r8, IID_IOleObject; struct _GUID *
0x1800c8871  mov     rdx, [rbp+57h+arg_8]; struct IUnknown *
0x1800c8875  lea     rcx, [rbp+57h+arg_0]; struct IUnknown **
0x1800c8879  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x1800c887e  mov     rcx, [rbp+57h+arg_0]
0x1800c8882  test    rcx, rcx
0x1800c8885  jz      loc_1800C8960
0x1800c888b  mov     [rbp+57h+lpszCaption], 0
0x1800c8893  mov     rax, [rcx]
0x1800c8896  lea     r8, [rbp+57h+lpszCaption]
0x1800c889a  mov     edx, 2
0x1800c889f  mov     rax, [rax+80h]
0x1800c88a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c88ab  xorps   xmm0, xmm0
0x1800c88ae  xor     eax, eax
0x1800c88b0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800c88b4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800c88b8  mov     word ptr [rbp+57h+pvarg], ax
0x1800c88bc  mov     esi, 80004005h
0x1800c88c1  mov     rcx, [rdi+30h]; struct IDispatch *
0x1800c88c5  test    rcx, rcx
0x1800c88c8  jz      short loc_1800C88DE
0x1800c88ca  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x1800c88ce  mov     edx, 0FFFFFD3Fh; int
0x1800c88d3  call    ?GetProperty@CComDispatchDriver@ATL@@SAJPEAUIDispatch@@JPEAUtagVARIANT@@@Z; ATL::CComDispatchDriver::GetProperty(IDispatch *,long,tagVARIANT *)
0x1800c88d8  mov     esi, eax
0x1800c88da  movzx   eax, word ptr [rbp+57h+pvarg]
0x1800c88de  mov     ebx, dword ptr [rbp+57h+pvarg+8]
0x1800c88e1  mov     ecx, 0FFFh
0x1800c88e6  cmp     ax, cx
0x1800c88e9  jnz     short loc_1800C88F4
0x1800c88eb  mov     eax, 8
0x1800c88f0  mov     word ptr [rbp+57h+pvarg], ax
0x1800c88f4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800c88f8  call    cs:__imp_VariantClear
0x1800c88fe  mov     eax, 400h
0x1800c8903  test    esi, esi
0x1800c8905  cmovs   ebx, eax
0x1800c8908  mov     [rsp+0C0h+pvReserved], 0; pvReserved
0x1800c8911  mov     [rsp+0C0h+dwReserved], 0; dwReserved
0x1800c8919  mov     [rsp+0C0h+lcid], ebx; lcid
0x1800c891d  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1800c8921  mov     [rsp+0C0h+pPageClsID], rax; pPageClsID
0x1800c8926  mov     eax, [rbp+57h+var_50]
0x1800c8929  mov     [rsp+0C0h+cPages], eax; cPages
0x1800c892d  lea     rax, [rbp+57h+arg_8]
0x1800c8931  mov     [rsp+0C0h+ppUnk], rax; ppUnk
0x1800c8936  mov     [rsp+0C0h+cObjects], 1; cObjects
0x1800c893e  mov     r9, [rbp+57h+lpszCaption]; lpszCaption
0x1800c8942  mov     r8d, [rdi+48h]; y
0x1800c8946  mov     edx, [rdi+4Ch]; x
0x1800c8949  mov     rcx, r14; hwndOwner
0x1800c894c  call    cs:__imp_OleCreatePropertyFrame
0x1800c8952  mov     ebx, eax
0x1800c8954  mov     rcx, [rbp+57h+lpszCaption]; pv
0x1800c8958  call    cs:__imp_CoTaskMemFree
0x1800c895e  jmp     short loc_1800C8965
0x1800c8960  mov     ebx, 40181h
0x1800c8965  mov     rcx, qword ptr [rbp+57h+var_50+8]; pv
0x1800c8969  call    cs:__imp_CoTaskMemFree
0x1800c896f  jmp     short loc_1800C8976
0x1800c8971  mov     ebx, 40181h
0x1800c8976  lea     rcx, [rbp+57h+arg_8]
0x1800c897a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c897f  nop
0x1800c8980  lea     rcx, [rbp+57h+var_58]
0x1800c8984  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c8989  nop
0x1800c898a  lea     rcx, [rbp+57h+arg_0]
0x1800c898e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c8993  nop
0x1800c8994  lea     rcx, [rbp+57h+arg_18]
0x1800c8998  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800c899d  mov     eax, ebx
0x1800c899f  add     rsp, 0A0h
0x1800c89a6  pop     r14
0x1800c89a8  pop     rdi
0x1800c89a9  pop     rsi
0x1800c89aa  pop     rbx
0x1800c89ab  pop     rbp
0x1800c89ac  retn
```
