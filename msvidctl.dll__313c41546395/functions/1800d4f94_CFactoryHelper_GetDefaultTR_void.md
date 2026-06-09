# CFactoryHelper::GetDefaultTR(void)

- ea: `0x1800d4f94`
- end: `0x1800d5143`
- name: `?GetDefaultTR@CFactoryHelper@@SA?AVCComVariant@ATL@@XZ`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d514c`

## callees

- `0x180006b38`
- `0x18000eee4`
- `0x1800140b8`
- `0x1800d4f94`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800d4fd1`
- `ole32!CoCreateInstance` at `0x1800d4fd1`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5108`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5108`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
VARIANTARG *__fastcall CFactoryHelper::GetDefaultTR(VARIANTARG *a1)
{
  __int64 v3; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  __int64 v5; // [rsp+88h] [rbp+18h] BYREF
  __int64 v6; // [rsp+90h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+28h] BYREF

  v3 = 0;
  ppv = 0;
  CoCreateInstance(&CLSID_CreatePropBagOnRegKey, 0, 1u, &GUID_8a674b48_1f63_11d3_b64c_00c04f79498e, &ppv);
  if ( ppv
    && (*(int (__fastcall **)(LPVOID, __int64, const wchar_t *, _QWORD, int, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         -2147483647,
         L"Software\\Microsoft\\MSVidCtl",
         0,
         131097,
         &IID_IPropertyBag,
         &v3) >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v3 + 24LL))(
           v3,
           L"DefaultTuneRequest",
           &pvarg,
           0) < 0
      || ((pvarg.vt - 9) & 0xFFFB) != 0 )
    {
      *(_OWORD *)&a1->vt = 0;
      a1->pRecInfo = 0;
      a1->vt = 0;
    }
    else
    {
      v5 = 0;
      ATL::CComQIPtr<ITuneRequest,&__s_GUID const _GUID_07ddc146_fc3d_11d2_9d8c_00c04f72d980>::CComQIPtr<ITuneRequest,&__s_GUID const _GUID_07ddc146_fc3d_11d2_9d8c_00c04f72d980>(
        &v6,
        pvarg.llVal);
      if ( v6 && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 56LL))(v6, &v5) >= 0 && v5 )
      {
        a1->vt = 0;
        ATL::CComVariant::InternalCopy(a1, &pvarg);
      }
      else
      {
        *(_OWORD *)&a1->vt = 0;
        a1->pRecInfo = 0;
        a1->vt = 0;
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v6);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v5);
    }
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
  }
  else
  {
    *(_OWORD *)&a1->vt = 0;
    a1->pRecInfo = 0;
    a1->vt = 0;
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v3);
  return a1;
}

```

## disassembly

```asm
0x1800d4f94  mov     [rsp-8+arg_0], rbx
0x1800d4f99  push    rbp
0x1800d4f9a  mov     rbp, rsp
0x1800d4f9d  sub     rsp, 70h
0x1800d4fa1  mov     rbx, rcx
0x1800d4fa4  mov     [rbp+var_28], 0
0x1800d4fac  mov     [rbp+arg_18], 0
0x1800d4fb4  lea     rax, [rbp+arg_18]
0x1800d4fb8  mov     [rsp+70h+ppv], rax; ppv
0x1800d4fbd  lea     r9, _GUID_8a674b48_1f63_11d3_b64c_00c04f79498e; riid
0x1800d4fc4  xor     edx, edx; pUnkOuter
0x1800d4fc6  lea     r8d, [rdx+1]; dwClsContext
0x1800d4fca  lea     rcx, CLSID_CreatePropBagOnRegKey; rclsid
0x1800d4fd1  call    cs:__imp_CoCreateInstance
0x1800d4fd7  nop
0x1800d4fd8  mov     rcx, [rbp+arg_18]
0x1800d4fdc  test    rcx, rcx
0x1800d4fdf  jz      loc_1800D5110
0x1800d4fe5  mov     rax, [rcx]
0x1800d4fe8  lea     rdx, [rbp+var_28]
0x1800d4fec  mov     [rsp+70h+var_40], rdx
0x1800d4ff1  lea     rdx, IID_IPropertyBag
0x1800d4ff8  mov     [rsp+70h+var_48], rdx
0x1800d4ffd  mov     dword ptr [rsp+70h+ppv], 20019h
0x1800d5005  xor     r9d, r9d
0x1800d5008  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\MSVidCtl"
0x1800d500f  mov     rdx, 0FFFFFFFF80000001h
0x1800d5016  mov     rax, [rax+18h]
0x1800d501a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d501f  test    eax, eax
0x1800d5021  js      loc_1800D5110
0x1800d5027  xorps   xmm0, xmm0
0x1800d502a  xor     eax, eax
0x1800d502c  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800d5030  mov     qword ptr [rbp+pvarg+10h], rax
0x1800d5034  mov     word ptr [rbp+pvarg], ax
0x1800d5038  mov     rcx, [rbp+var_28]
0x1800d503c  mov     rax, [rcx]
0x1800d503f  xor     r9d, r9d
0x1800d5042  lea     r8, [rbp+pvarg]
0x1800d5046  lea     rdx, aDefaulttunereq; "DefaultTuneRequest"
0x1800d504d  mov     rax, [rax+18h]
0x1800d5051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5056  test    eax, eax
0x1800d5058  js      loc_1800D50E1
0x1800d505e  movzx   eax, word ptr [rbp+pvarg]
0x1800d5062  sub     ax, 9
0x1800d5066  mov     ecx, 0FFFBh
0x1800d506b  test    cx, ax
0x1800d506e  jnz     short loc_1800D50E1
0x1800d5070  mov     [rbp+arg_8], 0
0x1800d5078  mov     rdx, qword ptr [rbp+pvarg+8]
0x1800d507c  lea     rcx, [rbp+arg_10]
0x1800d5080  call    ??0?$CComQIPtr@UITuneRequest@@$1?_GUID_07ddc146_fc3d_11d2_9d8c_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ITuneRequest,&__s_GUID const _GUID_07ddc146_fc3d_11d2_9d8c_00c04f72d980>::CComQIPtr<ITuneRequest,&__s_GUID const _GUID_07ddc146_fc3d_11d2_9d8c_00c04f72d980>(IUnknown *)
0x1800d5085  nop
0x1800d5086  mov     rcx, [rbp+arg_10]
0x1800d508a  test    rcx, rcx
0x1800d508d  jnz     short loc_1800D50B3
0x1800d508f  xorps   xmm0, xmm0
0x1800d5092  xor     eax, eax
0x1800d5094  movups  xmmword ptr [rbx], xmm0
0x1800d5097  mov     [rbx+10h], rax
0x1800d509b  mov     [rbx], ax
0x1800d509e  lea     rcx, [rbp+arg_10]
0x1800d50a2  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d50a7  nop
0x1800d50a8  lea     rcx, [rbp+arg_8]
0x1800d50ac  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d50b1  jmp     short loc_1800D50F0
0x1800d50b3  mov     rax, [rcx]
0x1800d50b6  lea     rdx, [rbp+arg_8]
0x1800d50ba  mov     rax, [rax+38h]
0x1800d50be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d50c3  test    eax, eax
0x1800d50c5  js      short loc_1800D508F
0x1800d50c7  cmp     [rbp+arg_8], 0
0x1800d50cc  jz      short loc_1800D508F
0x1800d50ce  xor     eax, eax
0x1800d50d0  mov     [rbx], ax
0x1800d50d3  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x1800d50d7  mov     rcx, rbx; this
0x1800d50da  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800d50df  jmp     short loc_1800D509E
0x1800d50e1  xorps   xmm0, xmm0
0x1800d50e4  xor     eax, eax
0x1800d50e6  movups  xmmword ptr [rbx], xmm0
0x1800d50e9  mov     [rbx+10h], rax
0x1800d50ed  mov     [rbx], ax
0x1800d50f0  mov     eax, 0FFFh
0x1800d50f5  cmp     word ptr [rbp+pvarg], ax
0x1800d50f9  jnz     short loc_1800D5104
0x1800d50fb  mov     eax, 8
0x1800d5100  mov     word ptr [rbp+pvarg], ax
0x1800d5104  lea     rcx, [rbp+pvarg]; pvarg
0x1800d5108  call    cs:__imp_VariantClear
0x1800d510e  jmp     short loc_1800D511F
0x1800d5110  xorps   xmm0, xmm0
0x1800d5113  xor     eax, eax
0x1800d5115  movups  xmmword ptr [rbx], xmm0
0x1800d5118  mov     [rbx+10h], rax
0x1800d511c  mov     [rbx], ax
0x1800d511f  lea     rcx, [rbp+arg_18]
0x1800d5123  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d5128  nop
0x1800d5129  lea     rcx, [rbp+var_28]
0x1800d512d  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d5132  mov     rax, rbx
0x1800d5135  mov     rbx, [rsp+70h+arg_0]
0x1800d513d  add     rsp, 70h
0x1800d5141  pop     rbp
0x1800d5142  retn
```
