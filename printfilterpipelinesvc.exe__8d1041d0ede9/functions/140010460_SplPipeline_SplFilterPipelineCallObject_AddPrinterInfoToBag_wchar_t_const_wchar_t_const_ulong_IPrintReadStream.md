# SplPipeline::SplFilterPipelineCallObject::AddPrinterInfoToBag(wchar_t const *,wchar_t const *,ulong,IPrintReadStreamFactory *,wchar_t const *)

- ea: `0x140010460`
- end: `0x1400105f7`
- name: `?AddPrinterInfoToBag@SplFilterPipelineCallObject@SplPipeline@@AEAAXPEB_W0KPEAUIPrintReadStreamFactory@@0@Z`
- size: `407`
- prototype: `void(SplPipeline::SplFilterPipelineCallObject *__hidden this, const wchar_t *, const wchar_t *, unsigned int, struct IPrintReadStreamFactory *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012404`

## callees

- `0x14000fdf8`
- `0x140010460`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1400104ed`
- `OLEAUT32!__imp_VariantInit` at `0x140010537`
- `OLEAUT32!__imp_VariantInit` at `0x1400104ed`
- `OLEAUT32!__imp_VariantInit` at `0x140010537`
- `OLEAUT32!__imp_VariantClear` at `0x14001059e`
- `OLEAUT32!__imp_VariantClear` at `0x1400105db`
- `OLEAUT32!__imp_VariantClear` at `0x1400105e6`
- `OLEAUT32!__imp_VariantClear` at `0x14001059e`
- `OLEAUT32!__imp_VariantClear` at `0x1400105db`
- `OLEAUT32!__imp_VariantClear` at `0x1400105e6`

## string_xrefs

- `0x140010523`: `UserSecurityToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SplPipeline::SplFilterPipelineCallObject::AddPrinterInfoToBag(
        SplPipeline::SplFilterPipelineCallObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        LONG a4,
        struct IPrintReadStreamFactory *a5,
        wchar_t *a6)
{
  LONGLONG v10; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG v12; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v13; // [rsp+50h] [rbp-20h] BYREF

  *(_QWORD *)&pvarg.vt = 13;
  *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)a5;
  (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL) + 48LL))(
    *((_QWORD *)this + 15) + 16LL,
    L"PerUserPrintTicket",
    &pvarg);
  PrnExcept::TBstrVT::TBstrVT((PrnExcept::TBstrVT *)&v13, a2);
  (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL) + 48LL))(
    *((_QWORD *)this + 15) + 16LL,
    L"PrinterName",
    &v13);
  VariantInit(&pvarg);
  pvarg.vt = 0x4000;
  v10 = *((_QWORD *)this + 10);
  if ( v10 == -1 )
    v10 = 0;
  pvarg.llVal = v10;
  (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL) + 48LL))(
    *((_QWORD *)this + 15) + 16LL,
    L"UserSecurityToken",
    &pvarg);
  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = a4;
  (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL) + 48LL))(
    *((_QWORD *)this + 15) + 16LL,
    L"PrintJobId",
    &pvarg);
  if ( a3 )
  {
    PrnExcept::TBstrVT::TBstrVT((PrnExcept::TBstrVT *)&v12, a3);
    (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL) + 48LL))(
      *((_QWORD *)this + 15) + 16LL,
      L"PrintOutputFileName",
      &v12);
    VariantClear(&v12);
  }
  if ( a6 )
  {
    PrnExcept::TBstrVT::TBstrVT((PrnExcept::TBstrVT *)&v12, a6);
    (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)(*((_QWORD *)this + 15) + 16LL) + 48LL))(
      *((_QWORD *)this + 15) + 16LL,
      L"DriverMultiContentType",
      &v12);
    VariantClear(&v12);
  }
  VariantClear(&v13);
}

```

## disassembly

```asm
0x140010460  push    rbp
0x140010462  push    rbx
0x140010463  push    rsi
0x140010464  push    rdi
0x140010465  push    r14
0x140010467  mov     rbp, rsp
0x14001046a  sub     rsp, 70h
0x14001046e  mov     edi, r9d
0x140010471  mov     r14, r8
0x140010474  mov     rbx, rdx
0x140010477  mov     rsi, rcx
0x14001047a  xorps   xmm0, xmm0
0x14001047d  xor     eax, eax
0x14001047f  movups  xmmword ptr [rbp+pvarg], xmm0
0x140010483  mov     qword ptr [rbp+pvarg+10h], rax
0x140010487  mov     rax, [rbp+arg_20]
0x14001048b  mov     dword ptr [rbp+pvarg+8], eax
0x14001048e  sar     rax, 20h
0x140010492  mov     dword ptr [rbp+pvarg+0Ch], eax
0x140010495  mov     eax, 0Dh
0x14001049a  mov     word ptr [rbp+pvarg], ax
0x14001049e  mov     rcx, [rcx+78h]
0x1400104a2  add     rcx, 10h
0x1400104a6  mov     rax, [rcx]
0x1400104a9  lea     r8, [rbp+pvarg]
0x1400104ad  lea     rdx, aPeruserprintti; "PerUserPrintTicket"
0x1400104b4  mov     rax, [rax+30h]
0x1400104b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104bd  mov     rdx, rbx; wchar_t *
0x1400104c0  lea     rcx, [rbp+var_20]; this
0x1400104c4  call    ??0TBstrVT@PrnExcept@@QEAA@PEB_W@Z; PrnExcept::TBstrVT::TBstrVT(wchar_t const *)
0x1400104c9  nop
0x1400104ca  mov     rcx, [rsi+78h]
0x1400104ce  add     rcx, 10h
0x1400104d2  mov     rax, [rcx]
0x1400104d5  lea     r8, [rbp+var_20]
0x1400104d9  lea     rdx, aPrintername; "PrinterName"
0x1400104e0  mov     rax, [rax+30h]
0x1400104e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104e9  lea     rcx, [rbp+pvarg]; pvarg
0x1400104ed  call    cs:__imp_VariantInit
0x1400104f3  mov     eax, 4000h
0x1400104f8  mov     word ptr [rbp+pvarg], ax
0x1400104fc  mov     rcx, [rsi+50h]
0x140010500  xor     eax, eax
0x140010502  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140010506  cmovz   rcx, rax
0x14001050a  mov     dword ptr [rbp+pvarg+8], ecx
0x14001050d  sar     rcx, 20h
0x140010511  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x140010514  mov     rcx, [rsi+78h]
0x140010518  add     rcx, 10h
0x14001051c  mov     rax, [rcx]
0x14001051f  lea     r8, [rbp+pvarg]
0x140010523  lea     rdx, aUsersecurityto; "UserSecurityToken"
0x14001052a  mov     rax, [rax+30h]
0x14001052e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010533  lea     rcx, [rbp+pvarg]; pvarg
0x140010537  call    cs:__imp_VariantInit
0x14001053d  mov     eax, 13h
0x140010542  mov     word ptr [rbp+pvarg], ax
0x140010546  mov     dword ptr [rbp+pvarg+8], edi
0x140010549  mov     rcx, [rsi+78h]
0x14001054d  add     rcx, 10h
0x140010551  mov     rax, [rcx]
0x140010554  lea     r8, [rbp+pvarg]
0x140010558  lea     rdx, aPrintjobid; "PrintJobId"
0x14001055f  mov     rax, [rax+30h]
0x140010563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010568  test    r14, r14
0x14001056b  jz      short loc_1400105A4
0x14001056d  mov     rdx, r14; wchar_t *
0x140010570  lea     rcx, [rbp+var_38]; this
0x140010574  call    ??0TBstrVT@PrnExcept@@QEAA@PEB_W@Z; PrnExcept::TBstrVT::TBstrVT(wchar_t const *)
0x140010579  nop
0x14001057a  mov     rcx, [rsi+78h]
0x14001057e  add     rcx, 10h
0x140010582  mov     rax, [rcx]
0x140010585  lea     r8, [rbp+var_38]
0x140010589  lea     rdx, aPrintoutputfil; "PrintOutputFileName"
0x140010590  mov     rax, [rax+30h]
0x140010594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010599  nop
0x14001059a  lea     rcx, [rbp+var_38]; pvarg
0x14001059e  call    cs:__imp_VariantClear
0x1400105a4  mov     rdx, [rbp+arg_28]; wchar_t *
0x1400105a8  test    rdx, rdx
0x1400105ab  jz      short loc_1400105E2
0x1400105ad  lea     rcx, [rbp+var_38]; this
0x1400105b1  call    ??0TBstrVT@PrnExcept@@QEAA@PEB_W@Z; PrnExcept::TBstrVT::TBstrVT(wchar_t const *)
0x1400105b6  nop
0x1400105b7  mov     rcx, [rsi+78h]
0x1400105bb  add     rcx, 10h
0x1400105bf  mov     rax, [rcx]
0x1400105c2  lea     r8, [rbp+var_38]
0x1400105c6  lea     rdx, aDrivermulticon; "DriverMultiContentType"
0x1400105cd  mov     rax, [rax+30h]
0x1400105d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105d6  nop
0x1400105d7  lea     rcx, [rbp+var_38]; pvarg
0x1400105db  call    cs:__imp_VariantClear
0x1400105e1  nop
0x1400105e2  lea     rcx, [rbp+var_20]; pvarg
0x1400105e6  call    cs:__imp_VariantClear
0x1400105ec  add     rsp, 70h
0x1400105f0  pop     r14
0x1400105f2  pop     rdi
0x1400105f3  pop     rsi
0x1400105f4  pop     rbx
0x1400105f5  pop     rbp
0x1400105f6  retn
```
