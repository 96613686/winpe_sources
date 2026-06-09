# CMSVidWebDVD::get_Bookmark(uchar * *,ulong *)

- ea: `0x1800b4700`
- end: `0x1800b4893`
- name: `?get_Bookmark@CMSVidWebDVD@@UEAAJPEAPEAEPEAK@Z`
- size: `403`
- prototype: `__int64 __fastcall(CMSVidWebDVD *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006b38`
- `0x1800acdc4`
- `0x1800acfe4`
- `0x1800b42fc`
- `0x1800b4700`
- `0x1800f8010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800b47d9`
- `ole32!CoTaskMemAlloc` at `0x1800b47d9`
- `ole32!CoTaskMemFree` at `0x1800b4826`
- `ole32!CoTaskMemFree` at `0x1800b4826`
- `KERNEL32!Sleep` at `0x1800b4778`
- `KERNEL32!Sleep` at `0x1800b4778`

## pseudocode

```c
__int64 __fastcall CMSVidWebDVD::get_Bookmark(CMSVidWebDVD *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v7; // edi
  CMSVidWebDVD *v8; // rcx
  int v9; // ebx
  CMSVidWebDVD *v10; // rcx
  int v11; // edx
  int v12; // eax
  LPVOID v13; // rax
  void *v14; // rbx
  int v15; // edi
  unsigned int v17; // eax
  CMSVidWebDVD *v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+38h] [rbp-8h] BYREF
  SIZE_T cb; // [rsp+68h] [rbp+28h] BYREF
  __int64 v21; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  CMSVidWebDVD::GetDVDInfo2((char *)this - 48, &v19);
  v5 = v19;
  if ( !v19 )
  {
    v6 = -2147418113;
LABEL_21:
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v19);
    return v6;
  }
  v21 = 0;
  v7 = 0;
  while ( 1 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 256LL))(v5, &v21);
    if ( v9 != -2147220836 )
      break;
    Sleep(1u);
    if ( ++v7 >= 50 )
      break;
    v5 = v19;
  }
  if ( v9 < 0 )
  {
    v6 = CMSVidWebDVD::HandleError(v8, v9);
LABEL_20:
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v21);
    goto LABEL_21;
  }
  ATL::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>(
    &v18,
    v21);
  v10 = v18;
  if ( !v18 )
  {
    v11 = v9;
LABEL_19:
    v6 = CMSVidWebDVD::HandleError(v10, v11);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v18);
    goto LABEL_20;
  }
  LODWORD(cb) = 0;
  v12 = (*(__int64 (__fastcall **)(CMSVidWebDVD *, SIZE_T *))(*(_QWORD *)v18 + 56LL))(v18, &cb);
  if ( v12 < 0 )
  {
    v11 = v12;
    goto LABEL_19;
  }
  v13 = CoTaskMemAlloc((unsigned int)cb);
  v14 = v13;
  if ( !v13 )
  {
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v18);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v21);
    v6 = -2147024882;
    goto LABEL_21;
  }
  v15 = (*(__int64 (__fastcall **)(CMSVidWebDVD *, LPVOID, __int64, _QWORD))(*(_QWORD *)v18 + 48LL))(
          v18,
          v13,
          1,
          (unsigned int)cb);
  if ( v15 < 0 )
  {
    CoTaskMemFree(v14);
    v11 = v15;
    goto LABEL_19;
  }
  v17 = cb;
  *a2 = (unsigned __int8 *)v14;
  *a3 = v17;
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v18);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v21);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v19);
  return 0;
}

```

## disassembly

```asm
0x1800b4700  mov     [rsp-18h+arg_0], rbx
0x1800b4705  mov     [rsp-18h+arg_10], rsi
0x1800b470a  push    rbp
0x1800b470b  push    rdi
0x1800b470c  push    r14
0x1800b470e  mov     rbp, rsp
0x1800b4711  sub     rsp, 40h
0x1800b4715  mov     rsi, r8
0x1800b4718  mov     r14, rdx
0x1800b471b  test    rdx, rdx
0x1800b471e  jz      loc_1800B487B
0x1800b4724  test    r8, r8
0x1800b4727  jz      loc_1800B487B
0x1800b472d  add     rcx, 0FFFFFFFFFFFFFFD0h
0x1800b4731  lea     rdx, [rbp+var_8]
0x1800b4735  call    ?GetDVDInfo2@CMSVidWebDVD@@QEAA?AV?$CComQIPtr@UIDvdInfo2@@$1?IID_IDvdInfo2@@3U_GUID@@B@ATL@@XZ; CMSVidWebDVD::GetDVDInfo2(void)
0x1800b473a  mov     rcx, [rbp+var_8]
0x1800b473e  test    rcx, rcx
0x1800b4741  jnz     short loc_1800B474D
0x1800b4743  mov     ebx, 8000FFFFh
0x1800b4748  jmp     loc_1800B4847
0x1800b474d  mov     [rbp+arg_18], 0
0x1800b4755  xor     edi, edi
0x1800b4757  mov     rax, [rcx]
0x1800b475a  lea     rdx, [rbp+arg_18]
0x1800b475e  mov     rax, [rax+100h]
0x1800b4765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b476a  mov     ebx, eax
0x1800b476c  cmp     eax, 8004029Ch
0x1800b4771  jnz     short loc_1800B478B
0x1800b4773  mov     ecx, 1; dwMilliseconds
0x1800b4778  call    cs:__imp_Sleep
0x1800b477e  inc     edi
0x1800b4780  cmp     edi, 32h ; '2'
0x1800b4783  jge     short loc_1800B478B
0x1800b4785  mov     rcx, [rbp+var_8]
0x1800b4789  jmp     short loc_1800B4757
0x1800b478b  test    ebx, ebx
0x1800b478d  jns     short loc_1800B479D
0x1800b478f  mov     edx, ebx; int
0x1800b4791  call    ?HandleError@CMSVidWebDVD@@AEAAJJ@Z; CMSVidWebDVD::HandleError(long)
0x1800b4796  mov     ebx, eax
0x1800b4798  jmp     loc_1800B483E
0x1800b479d  mov     rdx, [rbp+arg_18]
0x1800b47a1  lea     rcx, [rbp+var_10]
0x1800b47a5  call    ??0?$CComQIPtr@UIPersistMemory@@$1?_GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>::CComQIPtr<IPersistMemory,&__s_GUID const _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000>(IUnknown *)
0x1800b47aa  mov     rcx, [rbp+var_10]
0x1800b47ae  test    rcx, rcx
0x1800b47b1  jnz     short loc_1800B47B7
0x1800b47b3  mov     edx, ebx
0x1800b47b5  jmp     short loc_1800B482E
0x1800b47b7  mov     dword ptr [rbp+cb], 0
0x1800b47be  lea     rdx, [rbp+cb]
0x1800b47c2  mov     rax, [rcx]
0x1800b47c5  mov     rax, [rax+38h]
0x1800b47c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47ce  test    eax, eax
0x1800b47d0  jns     short loc_1800B47D6
0x1800b47d2  mov     edx, eax
0x1800b47d4  jmp     short loc_1800B482E
0x1800b47d6  mov     ecx, dword ptr [rbp+cb]; cb
0x1800b47d9  call    cs:__imp_CoTaskMemAlloc
0x1800b47df  mov     rbx, rax
0x1800b47e2  test    rax, rax
0x1800b47e5  jnz     short loc_1800B4800
0x1800b47e7  lea     rcx, [rbp+var_10]
0x1800b47eb  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b47f0  lea     rcx, [rbp+arg_18]
0x1800b47f4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b47f9  mov     ebx, 8007000Eh
0x1800b47fe  jmp     short loc_1800B4847
0x1800b4800  mov     rcx, [rbp+var_10]
0x1800b4804  mov     r8d, 1
0x1800b480a  mov     r9d, dword ptr [rbp+cb]
0x1800b480e  mov     rdx, rbx
0x1800b4811  mov     rax, [rcx]
0x1800b4814  mov     rax, [rax+30h]
0x1800b4818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b481d  mov     edi, eax
0x1800b481f  test    eax, eax
0x1800b4821  jns     short loc_1800B4854
0x1800b4823  mov     rcx, rbx; pv
0x1800b4826  call    cs:__imp_CoTaskMemFree
0x1800b482c  mov     edx, edi; int
0x1800b482e  call    ?HandleError@CMSVidWebDVD@@AEAAJJ@Z; CMSVidWebDVD::HandleError(long)
0x1800b4833  lea     rcx, [rbp+var_10]
0x1800b4837  mov     ebx, eax
0x1800b4839  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b483e  lea     rcx, [rbp+arg_18]
0x1800b4842  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b4847  lea     rcx, [rbp+var_8]
0x1800b484b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b4850  mov     eax, ebx
0x1800b4852  jmp     short loc_1800B4880
0x1800b4854  mov     eax, dword ptr [rbp+cb]
0x1800b4857  lea     rcx, [rbp+var_10]
0x1800b485b  mov     [r14], rbx
0x1800b485e  mov     [rsi], eax
0x1800b4860  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b4865  lea     rcx, [rbp+arg_18]
0x1800b4869  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b486e  lea     rcx, [rbp+var_8]
0x1800b4872  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800b4877  xor     eax, eax
0x1800b4879  jmp     short loc_1800B4880
0x1800b487b  mov     eax, 80004003h
0x1800b4880  mov     rbx, [rsp+40h+arg_0]
0x1800b4885  mov     rsi, [rsp+40h+arg_10]
0x1800b488a  add     rsp, 40h
0x1800b488e  pop     r14
0x1800b4890  pop     rdi
0x1800b4891  pop     rbp
0x1800b4892  retn
```
