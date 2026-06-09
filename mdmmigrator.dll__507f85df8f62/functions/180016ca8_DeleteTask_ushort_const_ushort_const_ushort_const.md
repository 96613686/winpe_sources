# DeleteTask(ushort const *,ushort const *,ushort const *)

- ea: `0x180016ca8`
- end: `0x1800170ee`
- name: `?DeleteTask@@YAJPEBG00@Z`
- size: `1094`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000c214`

## callees

- `0x1800026b0`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x180011d5c`
- `0x180012a70`
- `0x180016ca8`
- `0x18001ce54`
- `0x180020010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016d4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016d4c`
- `OLEAUT32!__imp_VariantInit` at `0x180016eac`
- `OLEAUT32!__imp_VariantInit` at `0x180016ec1`
- `OLEAUT32!__imp_VariantInit` at `0x180016ed6`
- `OLEAUT32!__imp_VariantInit` at `0x180016eea`
- `OLEAUT32!__imp_VariantInit` at `0x180016eac`
- `OLEAUT32!__imp_VariantInit` at `0x180016ec1`
- `OLEAUT32!__imp_VariantInit` at `0x180016ed6`
- `OLEAUT32!__imp_VariantInit` at `0x180016eea`
- `OLEAUT32!__imp_VariantClear` at `0x180016f4e`
- `OLEAUT32!__imp_VariantClear` at `0x180016f58`
- `OLEAUT32!__imp_VariantClear` at `0x180016f62`
- `OLEAUT32!__imp_VariantClear` at `0x180016f6c`
- `OLEAUT32!__imp_VariantClear` at `0x180016f4e`
- `OLEAUT32!__imp_VariantClear` at `0x180016f58`
- `OLEAUT32!__imp_VariantClear` at `0x180016f62`
- `OLEAUT32!__imp_VariantClear` at `0x180016f6c`

## string_xrefs

- `0x180016cf0`: `DeleteTask`

## pseudocode

```c
__int64 __fastcall DeleteTask(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // ebx
  void (*v8)(void); // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v11; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v13; // xmm8
  IRecordInfo *v14; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD *, __int64 *); // rdi
  _QWORD *v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  __int64 v21; // rbx
  void (__fastcall *v22)(__int64, _QWORD *, _QWORD); // rdi
  _QWORD *v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  unsigned __int16 *v26[2]; // [rsp+38h] [rbp-D0h] BYREF
  _WORD v27[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-B0h] BYREF
  const char *v29; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v30; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h]
  VARIANTARG v32; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v33; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v35; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v36; // [rsp+E8h] [rbp-20h]
  __int128 v37; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v38; // [rsp+108h] [rbp+0h]
  __int128 v39; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v40; // [rsp+128h] [rbp+20h]
  __int128 v41; // [rsp+138h] [rbp+30h] BYREF
  __int64 v42; // [rsp+148h] [rbp+40h]
  __int64 v43; // [rsp+1E0h] [rbp+D8h] BYREF
  int v44; // [rsp+1E8h] [rbp+E0h] BYREF
  int v45; // [rsp+1ECh] [rbp+E4h]
  __int64 v46; // [rsp+1F0h] [rbp+E8h] BYREF

  v45 = HIDWORD(a3);
  v44 = 0;
  v29 = "DeleteTask";
  *(_QWORD *)&v30.vt = &v44;
  v43 = 0;
  v46 = 0;
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  if ( a2 && (unsigned int)_o__wcsicmp(a2, L"S-1-5-18") )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v26,
                             a2) )
    {
      if ( v26[0] != v27 )
        operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_14:
      ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v46);
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v7 = -2147024882;
      goto LABEL_39;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v26,
                             L"\\EnterpriseMgmt") )
    {
      if ( v26[0] != v27 )
        operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_14;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v26,
                                L"\\Microsoft\\Windows\\EnterpriseMgmt") )
  {
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_14;
  }
  v7 = CoCreateTaskScheduler(v6, v5, &v43);
  v44 = v7;
  if ( v7 < 0 )
  {
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_20:
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v46);
    if ( !v43 )
      goto LABEL_39;
    v8 = *(void (**)(void))(*(_QWORD *)v43 + 16LL);
LABEL_38:
    v8();
    goto LABEL_39;
  }
  v9 = v43;
  v10 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v43 + 80LL);
  VariantInit(&pvarg);
  v11 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v33);
  v13 = *(_OWORD *)&v33.vt;
  v14 = v33.pRecInfo;
  VariantInit(&v32);
  v15 = *(_OWORD *)&v32.vt;
  v16 = v32.pRecInfo;
  VariantInit((VARIANTARG *)&v30.decVal.8);
  v35 = v11;
  v36 = pRecInfo;
  v37 = v13;
  v38 = v14;
  v39 = v15;
  v40 = v16;
  v41 = *(_OWORD *)&v30.decVal.Lo32;
  v42 = v31;
  v44 = v10(v9, &v41, &v39, &v37, &v35);
  VariantClear((VARIANTARG *)&v30.decVal.8);
  VariantClear(&v32);
  VariantClear(&v33);
  VariantClear(&pvarg);
  v7 = v44;
  if ( v44 < 0 )
  {
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_20;
  }
  v17 = v43;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v43 + 56LL);
  v19 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v28, v26[0]);
  if ( v19 )
    v19 = (_QWORD *)*v19;
  v44 = v18(v17, v19, &v46);
  _bstr_t::~_bstr_t((_bstr_t *)&v28, v20);
  v7 = v44;
  if ( v44 < 0 )
  {
    if ( v26[0] != v27 )
      operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_20;
  }
  v21 = v46;
  v22 = *(void (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v46 + 120LL);
  v23 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v28, a1);
  if ( v23 )
    v23 = (_QWORD *)*v23;
  v22(v21, v23, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&v28, v24);
  v7 = v44;
  if ( v26[0] != v27 )
    operator delete(v26[0], (const struct std::nothrow_t *)&std::nothrow);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v46);
  if ( v43 )
  {
    v8 = *(void (**)(void))(*(_QWORD *)v43 + 16LL);
    goto LABEL_38;
  }
LABEL_39:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v29);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016ca8  mov     rax, rsp
0x180016cab  mov     [rax+8], rbx
0x180016caf  mov     [rax+18h], r8
0x180016cb3  push    rbp
0x180016cb4  push    rsi
0x180016cb5  push    rdi
0x180016cb6  lea     rbp, [rax-0C8h]
0x180016cbd  sub     rsp, 1B0h
0x180016cc4  movaps  xmmword ptr [rax-28h], xmm6
0x180016cc8  movaps  xmmword ptr [rax-38h], xmm7
0x180016ccc  movaps  xmmword ptr [rax-48h], xmm8
0x180016cd1  movaps  xmmword ptr [rax-58h], xmm9
0x180016cd6  movaps  xmmword ptr [rax-68h], xmm10
0x180016cdb  movaps  xmmword ptr [rax-78h], xmm11
0x180016ce0  mov     rbx, rdx
0x180016ce3  mov     rsi, rcx
0x180016ce6  mov     [rbp+0C0h+arg_10], 0
0x180016cf0  lea     rax, aDeletetask; "DeleteTask"
0x180016cf7  mov     [rsp+1C0h+var_168], rax
0x180016cfc  lea     rax, [rbp+0C0h+arg_10]
0x180016d03  mov     qword ptr [rsp+1C0h+var_160], rax
0x180016d08  mov     [rbp+0C0h+arg_8], 0
0x180016d13  mov     [rbp+0C0h+arg_18], 0
0x180016d1e  lea     rax, [rsp+1C0h+var_180]
0x180016d23  mov     [rsp+1C0h+var_190], rax
0x180016d28  lea     rax, [rsp+1C0h+var_180]
0x180016d2d  mov     qword ptr [rsp+1C0h+var_188], rax
0x180016d32  xor     eax, eax
0x180016d34  mov     [rsp+1C0h+var_180], ax
0x180016d39  test    rdx, rdx
0x180016d3c  jz      loc_180016DDD
0x180016d42  lea     rdx, psz; "S-1-5-18"
0x180016d49  mov     rcx, rbx
0x180016d4c  call    cs:__imp__o__wcsicmp
0x180016d52  test    eax, eax
0x180016d54  jz      loc_180016DDD
0x180016d5a  mov     rdx, rbx
0x180016d5d  lea     rcx, [rsp+1C0h+var_190]
0x180016d62  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180016d67  test    al, al
0x180016d69  jnz     short loc_180016D99
0x180016d6b  lea     rax, [rsp+1C0h+var_180]
0x180016d70  mov     rcx, [rsp+1C0h+var_190]; void *
0x180016d75  cmp     rcx, rax
0x180016d78  jz      short loc_180016D87
0x180016d7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016d81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016d86  nop
0x180016d87  lea     rcx, [rbp+0C0h+arg_18]
0x180016d8e  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016d93  nop
0x180016d94  jmp     loc_180016E1B
0x180016d99  lea     rdx, aEnterprisemgmt; "\\EnterpriseMgmt"
0x180016da0  lea     rcx, [rsp+1C0h+var_190]
0x180016da5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180016daa  test    al, al
0x180016dac  jnz     loc_180016E3D
0x180016db2  lea     rax, [rsp+1C0h+var_180]
0x180016db7  mov     rcx, [rsp+1C0h+var_190]; void *
0x180016dbc  cmp     rcx, rax
0x180016dbf  jz      short loc_180016DCE
0x180016dc1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016dc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016dcd  nop
0x180016dce  lea     rcx, [rbp+0C0h+arg_18]
0x180016dd5  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016dda  nop
0x180016ddb  jmp     short loc_180016E1B
0x180016ddd  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180016de4  lea     rcx, [rsp+1C0h+var_190]
0x180016de9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180016dee  test    al, al
0x180016df0  jnz     short loc_180016E3D
0x180016df2  lea     rax, [rsp+1C0h+var_180]
0x180016df7  mov     rcx, [rsp+1C0h+var_190]; void *
0x180016dfc  cmp     rcx, rax
0x180016dff  jz      short loc_180016E0E
0x180016e01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016e08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016e0d  nop
0x180016e0e  lea     rcx, [rbp+0C0h+arg_18]
0x180016e15  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016e1a  nop
0x180016e1b  mov     rcx, [rbp+0C0h+arg_8]
0x180016e22  test    rcx, rcx
0x180016e25  jz      short loc_180016E33
0x180016e27  mov     rax, [rcx]
0x180016e2a  mov     rax, [rax+10h]
0x180016e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e33  mov     ebx, 8007000Eh
0x180016e38  jmp     loc_1800170B1
0x180016e3d  lea     r8, [rbp+0C0h+arg_8]
0x180016e44  call    CoCreateTaskScheduler
0x180016e49  mov     ebx, eax
0x180016e4b  mov     [rbp+0C0h+arg_10], eax
0x180016e51  test    eax, eax
0x180016e53  jns     short loc_180016E9A
0x180016e55  lea     rax, [rsp+1C0h+var_180]
0x180016e5a  mov     rcx, [rsp+1C0h+var_190]; void *
0x180016e5f  cmp     rcx, rax
0x180016e62  jz      short loc_180016E71
0x180016e64  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016e6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016e70  nop
0x180016e71  lea     rcx, [rbp+0C0h+arg_18]
0x180016e78  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016e7d  nop
0x180016e7e  mov     rcx, [rbp+0C0h+arg_8]
0x180016e85  test    rcx, rcx
0x180016e88  jz      loc_1800170B1
0x180016e8e  mov     rax, [rcx]
0x180016e91  mov     rax, [rax+10h]
0x180016e95  jmp     loc_1800170AC
0x180016e9a  mov     rdi, [rbp+0C0h+arg_8]
0x180016ea1  mov     rax, [rdi]
0x180016ea4  mov     rbx, [rax+50h]
0x180016ea8  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x180016eac  call    cs:__imp_VariantInit
0x180016eb2  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x180016eb7  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x180016ebd  lea     rcx, [rbp+0C0h+var_128]; pvarg
0x180016ec1  call    cs:__imp_VariantInit
0x180016ec7  movups  xmm8, xmmword ptr [rbp+0C0h+var_128]
0x180016ecc  movsd   xmm9, qword ptr [rbp+0C0h+var_128+10h]
0x180016ed2  lea     rcx, [rbp+0C0h+var_140]; pvarg
0x180016ed6  call    cs:__imp_VariantInit
0x180016edc  movups  xmm6, xmmword ptr [rbp+0C0h+var_140]
0x180016ee0  movsd   xmm7, qword ptr [rbp+0C0h+var_140+10h]
0x180016ee5  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x180016eea  call    cs:__imp_VariantInit
0x180016ef0  movups  xmm0, xmmword ptr [rsp+1C0h+var_160+8]
0x180016ef5  movsd   xmm1, [rsp+1C0h+var_148]
0x180016efb  movaps  [rbp+0C0h+var_F0], xmm10
0x180016f00  movsd   [rbp+0C0h+var_E0], xmm11
0x180016f06  movaps  [rbp+0C0h+var_D0], xmm8
0x180016f0b  movsd   [rbp+0C0h+var_C0], xmm9
0x180016f11  movaps  [rbp+0C0h+var_B0], xmm6
0x180016f15  movsd   [rbp+0C0h+var_A0], xmm7
0x180016f1a  movaps  [rbp+0C0h+var_90], xmm0
0x180016f1e  movsd   [rbp+0C0h+var_80], xmm1
0x180016f23  lea     rax, [rbp+0C0h+var_F0]
0x180016f27  mov     [rsp+1C0h+var_1A0], rax
0x180016f2c  lea     r9, [rbp+0C0h+var_D0]
0x180016f30  lea     r8, [rbp+0C0h+var_B0]
0x180016f34  lea     rdx, [rbp+0C0h+var_90]
0x180016f38  mov     rcx, rdi
0x180016f3b  mov     rax, rbx
0x180016f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f43  mov     [rbp+0C0h+arg_10], eax
0x180016f49  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x180016f4e  call    cs:__imp_VariantClear
0x180016f54  lea     rcx, [rbp+0C0h+var_140]; pvarg
0x180016f58  call    cs:__imp_VariantClear
0x180016f5e  lea     rcx, [rbp+0C0h+var_128]; pvarg
0x180016f62  call    cs:__imp_VariantClear
0x180016f68  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x180016f6c  call    cs:__imp_VariantClear
0x180016f72  mov     ebx, [rbp+0C0h+arg_10]
0x180016f78  test    ebx, ebx
0x180016f7a  jns     short loc_180016FAA
0x180016f7c  lea     rax, [rsp+1C0h+var_180]
0x180016f81  mov     rcx, [rsp+1C0h+var_190]; void *
0x180016f86  cmp     rcx, rax
0x180016f89  jz      short loc_180016F98
0x180016f8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016f92  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016f97  nop
0x180016f98  lea     rcx, [rbp+0C0h+arg_18]
0x180016f9f  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016fa4  nop
0x180016fa5  jmp     loc_180016E7E
0x180016faa  mov     rbx, [rbp+0C0h+arg_8]
0x180016fb1  mov     rax, [rbx]
0x180016fb4  mov     rdi, [rax+38h]
0x180016fb8  mov     rdx, [rsp+1C0h+var_190]; unsigned __int16 *
0x180016fbd  lea     rcx, [rsp+1C0h+var_170]; this
0x180016fc2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180016fc7  mov     rdx, [rax]
0x180016fca  test    rdx, rdx
0x180016fcd  jz      short loc_180016FD2
0x180016fcf  mov     rdx, [rdx]
0x180016fd2  lea     r8, [rbp+0C0h+arg_18]
0x180016fd9  mov     rcx, rbx
0x180016fdc  mov     rax, rdi
0x180016fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe4  mov     [rbp+0C0h+arg_10], eax
0x180016fea  lea     rcx, [rsp+1C0h+var_170]; this
0x180016fef  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180016ff4  mov     ebx, [rbp+0C0h+arg_10]
0x180016ffa  test    ebx, ebx
0x180016ffc  jns     short loc_18001702C
0x180016ffe  lea     rax, [rsp+1C0h+var_180]
0x180017003  mov     rcx, [rsp+1C0h+var_190]; void *
0x180017008  cmp     rcx, rax
0x18001700b  jz      short loc_18001701A
0x18001700d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017014  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017019  nop
0x18001701a  lea     rcx, [rbp+0C0h+arg_18]
0x180017021  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180017026  nop
0x180017027  jmp     loc_180016E7E
0x18001702c  mov     rbx, [rbp+0C0h+arg_18]
0x180017033  mov     rax, [rbx]
0x180017036  mov     rdi, [rax+78h]
0x18001703a  mov     rdx, rsi; unsigned __int16 *
0x18001703d  lea     rcx, [rsp+1C0h+var_170]; this
0x180017042  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180017047  mov     rdx, [rax]
0x18001704a  test    rdx, rdx
0x18001704d  jz      short loc_180017052
0x18001704f  mov     rdx, [rdx]
0x180017052  xor     r8d, r8d
0x180017055  mov     rcx, rbx
0x180017058  mov     rax, rdi
0x18001705b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017060  lea     rcx, [rsp+1C0h+var_170]; this
0x180017065  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001706a  mov     ebx, [rbp+0C0h+arg_10]
0x180017070  lea     rax, [rsp+1C0h+var_180]
0x180017075  mov     rcx, [rsp+1C0h+var_190]; void *
0x18001707a  cmp     rcx, rax
0x18001707d  jz      short loc_18001708C
0x18001707f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017086  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001708b  nop
0x18001708c  lea     rcx, [rbp+0C0h+arg_18]
0x180017093  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180017098  nop
0x180017099  mov     rcx, [rbp+0C0h+arg_8]
0x1800170a0  test    rcx, rcx
0x1800170a3  jz      short loc_1800170B1
0x1800170a5  mov     rdx, [rcx]
0x1800170a8  mov     rax, [rdx+10h]
0x1800170ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b1  lea     rcx, [rsp+1C0h+var_168]; this
0x1800170b6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800170bb  mov     eax, ebx
0x1800170bd  lea     r11, [rsp+1C0h+var_10]
0x1800170c5  mov     rbx, [r11+20h]
0x1800170c9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800170ce  movaps  xmm7, xmmword ptr [r11-20h]
0x1800170d3  movaps  xmm8, xmmword ptr [r11-30h]
0x1800170d8  movaps  xmm9, xmmword ptr [r11-40h]
0x1800170dd  movaps  xmm10, xmmword ptr [r11-50h]
0x1800170e2  movaps  xmm11, xmmword ptr [r11-60h]
0x1800170e7  mov     rsp, r11
0x1800170ea  pop     rdi
0x1800170eb  pop     rsi
0x1800170ec  pop     rbp
0x1800170ed  retn
```
