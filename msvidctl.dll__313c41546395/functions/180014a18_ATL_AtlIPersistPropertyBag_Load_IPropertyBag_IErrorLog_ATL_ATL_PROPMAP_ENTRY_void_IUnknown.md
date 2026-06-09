# ATL::AtlIPersistPropertyBag_Load(IPropertyBag *,IErrorLog *,ATL::ATL_PROPMAP_ENTRY *,void *,IUnknown *)

- ea: `0x180014a18`
- end: `0x180014e15`
- name: `?AtlIPersistPropertyBag_Load@ATL@@YAJPEAUIPropertyBag@@PEAUIErrorLog@@PEAUATL_PROPMAP_ENTRY@1@PEAXPEAUIUnknown@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(struct IPropertyBag *, struct IErrorLog *, struct ATL::ATL_PROPMAP_ENTRY *, void *, struct IUnknown *)`
- caller_count: `32`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180014a18`
- `0x1800180e0`
- `0x18001b000`
- `0x18001c510`
- `0x18001e1a0`
- `0x18001f8c0`
- `0x180021180`
- `0x180022ae0`
- `0x180024230`
- `0x180025860`
- `0x180026d30`
- `0x180028140`
- `0x180029460`
- `0x18002e4e0`
- `0x18002e540`
- `0x18002e5a0`
- `0x18002e600`
- `0x18002e660`
- `0x180034de0`
- `0x180034e40`
- `0x180040290`
- `0x1800402f0`
- `0x180040350`
- `0x1800403b0`
- `0x180040410`
- `0x180040470`
- `0x1800404d0`
- `0x180040530`
- `0x180040590`
- `0x18004f790`
- `0x1800886f0`
- `0x1800ccdf0`

## callees

- `0x180006b08`
- `0x180006b38`
- `0x180014a18`
- `0x18001584c`
- `0x180016984`
- `0x1800186a4`
- `0x1800191f0`
- `0x1800f8010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180014c8e`
- `ole32!CLSIDFromString` at `0x180014c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c67`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c67`
- `OLEAUT32!__imp_VariantClear` at `0x180014d97`
- `OLEAUT32!__imp_VariantClear` at `0x180014dd3`
- `OLEAUT32!__imp_VariantClear` at `0x180014d97`
- `OLEAUT32!__imp_VariantClear` at `0x180014dd3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014c50`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014c50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::AtlIPersistPropertyBag_Load(
        struct IPropertyBag *a1,
        struct IErrorLog *a2,
        struct ATL::ATL_PROPMAP_ENTRY *a3,
        char *a4,
        struct IUnknown *a5)
{
  struct IErrorLog *v7; // r10
  struct IUnknown *v9; // r14
  _QWORD *v10; // r8
  int v11; // r13d
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(__int64); // rax
  _QWORD *v15; // r9
  __int64 v16; // r8
  struct ATL::ATL_PROPMAP_ENTRY *v17; // rax
  int v18; // ebx
  __int64 v19; // rbx
  __int64 v20; // rdx
  BSTR *v21; // rbx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  int (__fastcall ***llVal)(_QWORD, GUID *, BSTR *); // rcx
  GUID *v30; // rdx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  VARTYPE vt; // bx
  _QWORD *v39; // [rsp+30h] [rbp-30h]
  __int64 v40; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG lpsz; // [rsp+40h] [rbp-20h] BYREF
  struct IDispatch *v42; // [rsp+A0h] [rbp+40h] BYREF
  struct IErrorLog *v43; // [rsp+A8h] [rbp+48h]

  v43 = a2;
  v7 = a2;
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        v9 = a5;
        if ( a5 )
        {
          v42 = 0;
          v10 = 0;
          v39 = 0;
          v11 = 0;
          v12 = *(_QWORD *)GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4;
          v13 = *(_QWORD *)&GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1;
          while ( 1 )
          {
            v14 = (__int64 (__fastcall *)(__int64))*((_QWORD *)a3 + 6 * v11 + 2);
            if ( !v14 )
            {
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v42);
              return 0;
            }
            v15 = (_QWORD *)*((_QWORD *)a3 + 6 * v11 + 3);
            if ( v15 )
            {
              v16 = *v15 - v13;
              if ( *v15 == v13 )
                v16 = v15[1] - v12;
              if ( !v16 )
              {
                v17 = (struct ATL::ATL_PROPMAP_ENTRY *)v14(v12);
                if ( !v17 )
                  goto LABEL_76;
                v18 = ATL::AtlIPersistPropertyBag_Load(a1, v43, v17, &a4[*((_QWORD *)a3 + 6 * v11 + 4)], v9);
                if ( v18 < 0 )
                  goto LABEL_77;
                goto LABEL_71;
              }
              v10 = v39;
            }
            if ( !*((_QWORD *)a3 + 6 * v11) )
              goto LABEL_72;
            memset(&lpsz, 0, sizeof(lpsz));
            lpsz.vt = 0;
            if ( !*((_DWORD *)a3 + 12 * v11 + 10) )
            {
              if ( v15 != v10 )
              {
                ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
                  &v42,
                  v13);
                if ( ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IDispatch **))v9->lpVtbl->QueryInterface)(
                       v9,
                       *((_QWORD *)a3 + 6 * v11 + 3),
                       &v42) < 0 )
                  goto LABEL_73;
                v39 = (_QWORD *)*((_QWORD *)a3 + 6 * v11 + 3);
              }
              vt = *((_WORD *)a3 + 24 * v11 + 22);
              if ( !vt )
              {
                if ( (int)ATL::CComDispatchDriver::GetProperty(v42, *((_DWORD *)a3 + 12 * v11 + 2), &lpsz) < 0 )
                  goto LABEL_73;
                vt = lpsz.vt;
              }
              ATL::CComVariant::ClearToZero((ATL::CComVariant *)&lpsz);
              lpsz.vt = vt;
              if ( ((int (__fastcall *)(struct IPropertyBag *, _QWORD, VARIANTARG *, struct IErrorLog *))a1->lpVtbl->Read)(
                     a1,
                     *((_QWORD *)a3 + 6 * v11),
                     &lpsz,
                     v43) >= 0 )
              {
                if ( (int)ATL::CComDispatchDriver::PutProperty(v42, *((_DWORD *)a3 + 12 * v11 + 2), &lpsz) < 0 )
                {
LABEL_73:
                  if ( lpsz.vt == 4095 )
                    lpsz.vt = 8;
                  VariantClear(&lpsz);
LABEL_76:
                  v18 = -2147467259;
LABEL_77:
                  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v42);
                  return (unsigned int)v18;
                }
              }
              else
              {
                v40 = 0;
                ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v40);
              }
              if ( lpsz.vt != 4095 )
                goto LABEL_70;
LABEL_69:
              lpsz.vt = 8;
              goto LABEL_70;
            }
            v19 = *((_QWORD *)a3 + 6 * v11 + 4);
            lpsz.vt = *((_WORD *)a3 + 24 * v11 + 22);
            if ( ((int (__fastcall *)(struct IPropertyBag *, _QWORD, VARIANTARG *, struct IErrorLog *))a1->lpVtbl->Read)(
                   a1,
                   *((_QWORD *)a3 + 6 * v11),
                   &lpsz,
                   v7) >= 0 )
            {
              v21 = (BSTR *)&a4[v19];
              v22 = *((unsigned __int16 *)a3 + 24 * v11 + 22);
              if ( v22 <= 0x11 )
              {
                if ( v22 == 17 )
                  goto LABEL_27;
                v23 = v22 - 2;
                if ( !v23 )
                  goto LABEL_56;
                v24 = v23 - 1;
                if ( !v24 )
                  goto LABEL_55;
                v25 = v24 - 5;
                if ( v25 )
                {
                  v26 = v25 - 1;
                  if ( !v26 )
                  {
                    if ( *v21 )
                      (*(void (__fastcall **)(BSTR, __int64, _QWORD))(*(_QWORD *)*v21 + 16LL))(*v21, v20, 0);
                    llVal = (int (__fastcall ***)(_QWORD, GUID *, BSTR *))lpsz.llVal;
                    if ( lpsz.llVal )
                    {
                      v30 = &GUID_00020400_0000_0000_c000_000000000046;
LABEL_32:
                      if ( (**llVal)(llVal, v30, v21) >= 0 )
                        goto LABEL_57;
                    }
LABEL_33:
                    *v21 = 0;
                    goto LABEL_57;
                  }
                  v27 = v26 - 2;
                  if ( v27 )
                  {
                    v28 = v27 - 2;
                    if ( v28 )
                    {
                      if ( v28 != 3 )
                        goto LABEL_57;
LABEL_27:
                      *(_BYTE *)v21 = lpsz.bVal;
                      goto LABEL_57;
                    }
                    if ( *v21 )
                      (*(void (__fastcall **)(BSTR, __int64, _QWORD))(*(_QWORD *)*v21 + 16LL))(*v21, v20, 0);
                    llVal = (int (__fastcall ***)(_QWORD, GUID *, BSTR *))lpsz.llVal;
                    if ( lpsz.llVal )
                    {
                      v30 = (GUID *)*((_QWORD *)a3 + 6 * v11 + 3);
                      if ( v30 )
                        goto LABEL_32;
                    }
                    goto LABEL_33;
                  }
LABEL_56:
                  *(_WORD *)v21 = lpsz.iVal;
                  goto LABEL_57;
                }
LABEL_48:
                if ( *v21 )
                  SysFreeString(*v21);
                *v21 = lpsz.bstrVal;
                lpsz.llVal = 0;
                goto LABEL_57;
              }
              v31 = v22 - 18;
              if ( !v31 )
                goto LABEL_56;
              v32 = v31 - 1;
              if ( !v32 || (v33 = v32 - 3) == 0 || (v34 = v33 - 1) == 0 )
              {
LABEL_55:
                *(_DWORD *)v21 = lpsz.lVal;
                goto LABEL_57;
              }
              v35 = v34 - 49;
              if ( v35 )
              {
                v36 = v35 - 4023;
                if ( !v36 )
                  goto LABEL_48;
                if ( v36 == 4114 )
                {
                  if ( *v21 )
                    SafeArrayDestroy((SAFEARRAY *)*v21);
                  *v21 = lpsz.bstrVal;
                }
              }
              else if ( lpsz.vt != 8 || CLSIDFromString(lpsz.bstrVal, (LPCLSID)v21) < 0 )
              {
                *(_OWORD *)v21 = 0;
              }
            }
LABEL_57:
            if ( lpsz.vt == 4095 )
              goto LABEL_69;
LABEL_70:
            VariantClear(&lpsz);
LABEL_71:
            v7 = v43;
            v13 = *(_QWORD *)&GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1;
            v12 = *(_QWORD *)GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4;
LABEL_72:
            ++v11;
            v10 = v39;
          }
        }
      }
    }
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180014a18  mov     [rsp-38h+arg_10], rbx
0x180014a1d  mov     [rsp-38h+arg_8], rdx
0x180014a22  push    rbp
0x180014a23  push    rsi
0x180014a24  push    rdi
0x180014a25  push    r12
0x180014a27  push    r13
0x180014a29  push    r14
0x180014a2b  push    r15
0x180014a2d  mov     rbp, rsp
0x180014a30  sub     rsp, 60h
0x180014a34  mov     r12, r9
0x180014a37  mov     rsi, r8
0x180014a3a  mov     r10, rdx
0x180014a3d  mov     r15, rcx
0x180014a40  xor     ebx, ebx
0x180014a42  test    rcx, rcx
0x180014a45  jz      loc_180014DF8
0x180014a4b  test    r8, r8
0x180014a4e  jz      loc_180014DF8
0x180014a54  test    r9, r9
0x180014a57  jz      loc_180014DF8
0x180014a5d  mov     r14, [rbp+arg_20]
0x180014a61  test    r14, r14
0x180014a64  jz      loc_180014DF8
0x180014a6a  mov     [rbp+arg_0], rbx
0x180014a6e  mov     r8d, ebx
0x180014a71  mov     [rbp+var_30], rbx
0x180014a75  mov     r13d, ebx
0x180014a78  mov     rcx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4
0x180014a7f  mov     rdx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1
0x180014a86  movsxd  rax, r13d
0x180014a89  lea     rdi, [rax+rax*2]
0x180014a8d  add     rdi, rdi
0x180014a90  mov     rax, [rsi+rdi*8+10h]
0x180014a95  test    rax, rax
0x180014a98  jz      loc_180014DEB
0x180014a9e  mov     r9, [rsi+rdi*8+18h]
0x180014aa3  test    r9, r9
0x180014aa6  jz      short loc_180014AFB
0x180014aa8  mov     r8, [r9]
0x180014aab  sub     r8, rdx
0x180014aae  jnz     short loc_180014AB7
0x180014ab0  mov     r8, [r9+8]
0x180014ab4  sub     r8, rcx
0x180014ab7  test    r8, r8
0x180014aba  jnz     short loc_180014AF7
0x180014abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac1  test    rax, rax
0x180014ac4  jz      loc_180014DD9
0x180014aca  mov     r9, [rsi+rdi*8+20h]
0x180014acf  add     r9, r12; void *
0x180014ad2  mov     [rsp+60h+var_40], r14; struct IUnknown *
0x180014ad7  mov     r8, rax; struct ATL::ATL_PROPMAP_ENTRY *
0x180014ada  mov     rdx, [rbp+arg_8]; struct IErrorLog *
0x180014ade  mov     rcx, r15; struct IPropertyBag *
0x180014ae1  call    ?AtlIPersistPropertyBag_Load@ATL@@YAJPEAUIPropertyBag@@PEAUIErrorLog@@PEAUATL_PROPMAP_ENTRY@1@PEAXPEAUIUnknown@@@Z; ATL::AtlIPersistPropertyBag_Load(IPropertyBag *,IErrorLog *,ATL::ATL_PROPMAP_ENTRY *,void *,IUnknown *)
0x180014ae6  mov     ebx, eax
0x180014ae8  test    eax, eax
0x180014aea  js      loc_180014DDE
0x180014af0  xor     ebx, ebx
0x180014af2  jmp     loc_180014D9D
0x180014af7  mov     r8, [rbp+var_30]
0x180014afb  cmp     [rsi+rdi*8], rbx
0x180014aff  jz      loc_180014DAF
0x180014b05  xorps   xmm0, xmm0
0x180014b08  xor     eax, eax
0x180014b0a  movups  xmmword ptr [rbp+lpsz], xmm0
0x180014b0e  mov     [rbp+var_10], rax
0x180014b12  mov     word ptr [rbp+lpsz], bx
0x180014b16  cmp     [rsi+rdi*8+28h], ebx
0x180014b1a  jz      loc_180014CD0
0x180014b20  mov     rbx, [rsi+rdi*8+20h]
0x180014b25  movzx   eax, word ptr [rsi+rdi*8+2Ch]
0x180014b2a  mov     word ptr [rbp+lpsz], ax
0x180014b2e  mov     rax, [r15]
0x180014b31  mov     r9, r10
0x180014b34  lea     r8, [rbp+lpsz]
0x180014b38  mov     rdx, [rsi+rdi*8]
0x180014b3c  mov     rcx, r15
0x180014b3f  mov     rax, [rax+18h]
0x180014b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b48  xor     r8d, r8d
0x180014b4b  test    eax, eax
0x180014b4d  js      loc_180014CB5
0x180014b53  add     rbx, r12
0x180014b56  movzx   ecx, word ptr [rsi+rdi*8+2Ch]
0x180014b5b  cmp     ecx, 11h
0x180014b5e  ja      loc_180014C1B
0x180014b64  jz      short loc_180014B9D
0x180014b66  sub     ecx, 2
0x180014b69  jz      loc_180014CAE
0x180014b6f  sub     ecx, 1
0x180014b72  jz      loc_180014CA7
0x180014b78  sub     ecx, 5
0x180014b7b  jz      loc_180014C5F
0x180014b81  sub     ecx, 1
0x180014b84  jz      short loc_180014BF2
0x180014b86  sub     ecx, 2
0x180014b89  jz      loc_180014CAE
0x180014b8f  sub     ecx, 2
0x180014b92  jz      short loc_180014BA7
0x180014b94  cmp     ecx, 3
0x180014b97  jnz     loc_180014CB5
0x180014b9d  mov     al, byte ptr [rbp+lpsz+8]
0x180014ba0  mov     [rbx], al
0x180014ba2  jmp     loc_180014CB5
0x180014ba7  mov     rcx, [rbx]
0x180014baa  test    rcx, rcx
0x180014bad  jz      short loc_180014BBE
0x180014baf  mov     rax, [rcx]
0x180014bb2  mov     rax, [rax+10h]
0x180014bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bbb  xor     r8d, r8d
0x180014bbe  mov     rcx, [rbp+lpsz+8]
0x180014bc2  test    rcx, rcx
0x180014bc5  jz      short loc_180014BEA
0x180014bc7  mov     rdx, [rsi+rdi*8+18h]
0x180014bcc  test    rdx, rdx
0x180014bcf  jz      short loc_180014BEA
0x180014bd1  mov     rax, [rcx]
0x180014bd4  mov     r8, rbx
0x180014bd7  mov     rax, [rax]
0x180014bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bdf  xor     r8d, r8d
0x180014be2  test    eax, eax
0x180014be4  jns     loc_180014CB5
0x180014bea  mov     [rbx], r8
0x180014bed  jmp     loc_180014CB5
0x180014bf2  mov     rcx, [rbx]
0x180014bf5  test    rcx, rcx
0x180014bf8  jz      short loc_180014C09
0x180014bfa  mov     rax, [rcx]
0x180014bfd  mov     rax, [rax+10h]
0x180014c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c06  xor     r8d, r8d
0x180014c09  mov     rcx, [rbp+lpsz+8]
0x180014c0d  test    rcx, rcx
0x180014c10  jz      short loc_180014BEA
0x180014c12  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180014c19  jmp     short loc_180014BD1
0x180014c1b  sub     ecx, 12h
0x180014c1e  jz      loc_180014CAE
0x180014c24  sub     ecx, 1
0x180014c27  jz      short loc_180014CA7
0x180014c29  sub     ecx, 3
0x180014c2c  jz      short loc_180014CA7
0x180014c2e  sub     ecx, 1
0x180014c31  jz      short loc_180014CA7
0x180014c33  sub     ecx, 31h ; '1'
0x180014c36  jz      short loc_180014C7C
0x180014c38  sub     ecx, 0FB7h
0x180014c3e  jz      short loc_180014C5F
0x180014c40  cmp     ecx, 1012h
0x180014c46  jnz     short loc_180014CB5
0x180014c48  mov     rcx, [rbx]; psa
0x180014c4b  test    rcx, rcx
0x180014c4e  jz      short loc_180014C56
0x180014c50  call    cs:__imp_SafeArrayDestroy
0x180014c56  mov     rax, [rbp+lpsz+8]
0x180014c5a  mov     [rbx], rax
0x180014c5d  jmp     short loc_180014CB5
0x180014c5f  mov     rcx, [rbx]; bstrString
0x180014c62  test    rcx, rcx
0x180014c65  jz      short loc_180014C6D
0x180014c67  call    cs:__imp_SysFreeString
0x180014c6d  mov     rax, [rbp+lpsz+8]
0x180014c71  mov     [rbx], rax
0x180014c74  xor     ebx, ebx
0x180014c76  mov     [rbp+lpsz+8], rbx
0x180014c7a  jmp     short loc_180014CB7
0x180014c7c  mov     eax, 8
0x180014c81  cmp     word ptr [rbp+lpsz], ax
0x180014c85  jnz     short loc_180014C9D
0x180014c87  mov     rdx, rbx; pclsid
0x180014c8a  mov     rcx, [rbp+lpsz+8]; lpsz
0x180014c8e  call    cs:__imp_CLSIDFromString
0x180014c94  test    eax, eax
0x180014c96  mov     eax, 8
0x180014c9b  jns     short loc_180014CA3
0x180014c9d  xorps   xmm0, xmm0
0x180014ca0  movups  xmmword ptr [rbx], xmm0
0x180014ca3  xor     ebx, ebx
0x180014ca5  jmp     short loc_180014CBC
0x180014ca7  mov     eax, dword ptr [rbp+lpsz+8]
0x180014caa  mov     [rbx], eax
0x180014cac  jmp     short loc_180014CB5
0x180014cae  movzx   eax, word ptr [rbp+lpsz+8]
0x180014cb2  mov     [rbx], ax
0x180014cb5  xor     ebx, ebx
0x180014cb7  mov     eax, 8
0x180014cbc  mov     ecx, 0FFFh
0x180014cc1  cmp     word ptr [rbp+lpsz], cx
0x180014cc5  jnz     loc_180014D93
0x180014ccb  jmp     loc_180014D8F
0x180014cd0  cmp     r9, r8
0x180014cd3  jz      short loc_180014D06
0x180014cd5  lea     rcx, [rbp+arg_0]
0x180014cd9  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x180014cde  mov     rax, [r14]
0x180014ce1  lea     r8, [rbp+arg_0]
0x180014ce5  mov     rdx, [rsi+rdi*8+18h]
0x180014cea  mov     rcx, r14
0x180014ced  mov     rax, [rax]
0x180014cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf5  test    eax, eax
0x180014cf7  js      loc_180014DBB
0x180014cfd  mov     rax, [rsi+rdi*8+18h]
0x180014d02  mov     [rbp+var_30], rax
0x180014d06  movzx   ebx, word ptr [rsi+rdi*8+2Ch]
0x180014d0b  test    bx, bx
0x180014d0e  jnz     short loc_180014D2D
0x180014d10  lea     r8, [rbp+lpsz]; struct tagVARIANT *
0x180014d14  mov     edx, [rsi+rdi*8+8]; int
0x180014d18  mov     rcx, [rbp+arg_0]; struct IDispatch *
0x180014d1c  call    ?GetProperty@CComDispatchDriver@ATL@@SAJPEAUIDispatch@@JPEAUtagVARIANT@@@Z; ATL::CComDispatchDriver::GetProperty(IDispatch *,long,tagVARIANT *)
0x180014d21  test    eax, eax
0x180014d23  js      loc_180014DBB
0x180014d29  movzx   ebx, word ptr [rbp+lpsz]
0x180014d2d  lea     rcx, [rbp+lpsz]; this
0x180014d31  call    ?ClearToZero@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::ClearToZero(void)
0x180014d36  mov     word ptr [rbp+lpsz], bx
0x180014d3a  mov     rax, [r15]
0x180014d3d  mov     r9, [rbp+arg_8]
0x180014d41  lea     r8, [rbp+lpsz]
0x180014d45  mov     rdx, [rsi+rdi*8]
0x180014d49  mov     rcx, r15
0x180014d4c  mov     rax, [rax+18h]
0x180014d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d55  xor     ebx, ebx
0x180014d57  test    eax, eax
0x180014d59  jns     short loc_180014D6A
0x180014d5b  mov     [rbp+var_28], rbx
0x180014d5f  lea     rcx, [rbp+var_28]
0x180014d63  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180014d68  jmp     short loc_180014D7F
0x180014d6a  lea     r8, [rbp+lpsz]; struct tagVARIANT *
0x180014d6e  mov     edx, [rsi+rdi*8+8]; int
0x180014d72  mov     rcx, [rbp+arg_0]; struct IDispatch *
0x180014d76  call    ?PutProperty@CComDispatchDriver@ATL@@SAJPEAUIDispatch@@JPEAUtagVARIANT@@@Z; ATL::CComDispatchDriver::PutProperty(IDispatch *,long,tagVARIANT *)
0x180014d7b  test    eax, eax
0x180014d7d  js      short loc_180014DBB
0x180014d7f  mov     eax, 0FFFh
0x180014d84  cmp     word ptr [rbp+lpsz], ax
0x180014d88  jnz     short loc_180014D93
0x180014d8a  mov     eax, 8
0x180014d8f  mov     word ptr [rbp+lpsz], ax
0x180014d93  lea     rcx, [rbp+lpsz]; pvarg
0x180014d97  call    cs:__imp_VariantClear
0x180014d9d  mov     r10, [rbp+arg_8]
0x180014da1  mov     rdx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data1
0x180014da8  mov     rcx, qword ptr cs:_GUID_2a6e293d_2595_11d3_b64c_00c04f79498e.Data4
0x180014daf  inc     r13d
0x180014db2  mov     r8, [rbp+var_30]
0x180014db6  jmp     loc_180014A86
0x180014dbb  mov     eax, 0FFFh
0x180014dc0  cmp     word ptr [rbp+lpsz], ax
0x180014dc4  jnz     short loc_180014DCF
0x180014dc6  mov     eax, 8
0x180014dcb  mov     word ptr [rbp+lpsz], ax
0x180014dcf  lea     rcx, [rbp+lpsz]; pvarg
0x180014dd3  call    cs:__imp_VariantClear
0x180014dd9  mov     ebx, 80004005h
0x180014dde  lea     rcx, [rbp+arg_0]
0x180014de2  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180014de7  mov     eax, ebx
0x180014de9  jmp     short loc_180014DFD
0x180014deb  lea     rcx, [rbp+arg_0]
0x180014def  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180014df4  xor     eax, eax
0x180014df6  jmp     short loc_180014DFD
0x180014df8  mov     eax, 80004003h
0x180014dfd  mov     rbx, [rsp+60h+arg_10]
0x180014e05  add     rsp, 60h
0x180014e09  pop     r15
0x180014e0b  pop     r14
0x180014e0d  pop     r13
0x180014e0f  pop     r12
0x180014e11  pop     rdi
0x180014e12  pop     rsi
0x180014e13  pop     rbp
0x180014e14  retn
```
