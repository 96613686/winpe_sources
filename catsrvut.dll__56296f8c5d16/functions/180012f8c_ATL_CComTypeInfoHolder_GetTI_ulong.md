# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180012f8c`
- end: `0x18001314f`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `451`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180012e38`
- `0x180013160`

## callees

- `0x180010f64`
- `0x180011c14`
- `0x180012f8c`
- `0x180013644`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800130e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001313f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800130e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001313f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012fc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012fc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001309e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001309e`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180012ffa`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180012ffa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(struct IUnknown *this, LCID a2)
{
  HRESULT NameCache; // ebx
  ATL::CComTypeInfoHolder *v5; // rcx
  struct IUnknown *v6; // rcx
  struct IUnknown *v7; // rdi
  _QWORD *v8; // rax
  __int64 v9; // rdi
  ITypeLib *pptlib; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v11; // [rsp+60h] [rbp+20h] BYREF
  struct IUnknown *v12; // [rsp+70h] [rbp+30h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+38h] BYREF

  v11 = this;
  if ( qword_1800701C8 && qword_1800701D8 )
    return 0;
  NameCache = 0;
  EnterCriticalSection(&stru_1800732E8);
  if ( !qword_1800701C8 )
  {
    pptlib = 0;
    NameCache = LoadRegTypeLib(rguid, word_1800701C0, word_1800701C2, a2, &pptlib);
    if ( NameCache >= 0 )
    {
      v12 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, struct IUnknown **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    ATL::IDispatchImpl<IComponentRegistrarControl,&_GUID const IID_IComponentRegistrarControl,&_GUID const LIBID_CUSTREGLib,1,0,ATL::CComTypeInfoHolder>::_tih[0],
                    &v12);
      if ( NameCache >= 0 )
      {
        v6 = v12;
        v7 = v12;
        v11 = v12;
        if ( v12 )
        {
          ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->AddRef)(v12);
          v6 = v12;
        }
        v13 = 0;
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v6->lpVtbl->QueryInterface)(
               v6,
               &GUID_00020412_0000_0000_c000_000000000046,
               &v13) >= 0 )
        {
          ATL::AtlComPtrAssign(&v11, v13);
          v7 = v11;
        }
        v11 = 0;
        qword_1800701C8 = (struct ITypeInfo *)v7;
        v8 = CoTaskMemAlloc(0x18u);
        v9 = (__int64)v8;
        if ( v8 )
        {
          *v8 = ATL::CComTypeInfoHolder::Cleanup;
          v8[1] = ATL::IDispatchImpl<IComponentRegistrarControl,&_GUID const IID_IComponentRegistrarControl,&_GUID const LIBID_CUSTREGLib,1,0,ATL::CComTypeInfoHolder>::_tih;
          EnterCriticalSection(&stru_1800732E8);
          *(_QWORD *)(v9 + 16) = qword_180073398;
          qword_180073398 = v9;
          LeaveCriticalSection(&stru_1800732E8);
        }
        ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>((__int64 *)&v13);
        ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>((__int64 *)&v11);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>((__int64 *)&v12);
    }
  }
  if ( qword_1800701C8 )
  {
    if ( !qword_1800701D8 )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v5, qword_1800701C8);
  }
  LeaveCriticalSection(&stru_1800732E8);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180012f8c  mov     [rsp-18h+arg_0], rcx
0x180012f91  push    rbp
0x180012f92  push    rbx
0x180012f93  push    rdi
0x180012f94  mov     rbp, rsp
0x180012f97  sub     rsp, 40h
0x180012f9b  mov     edi, edx
0x180012f9d  cmp     cs:qword_1800701C8, 0
0x180012fa5  jz      short loc_180012FB8
0x180012fa7  cmp     cs:qword_1800701D8, 0
0x180012faf  jz      short loc_180012FB8
0x180012fb1  xor     eax, eax
0x180012fb3  jmp     loc_180013147
0x180012fb8  xor     ebx, ebx
0x180012fba  lea     rcx, stru_1800732E8; lpCriticalSection
0x180012fc1  call    cs:__imp_EnterCriticalSection
0x180012fc7  cmp     cs:qword_1800701C8, rbx
0x180012fce  jnz     loc_18001311B
0x180012fd4  mov     [rbp+var_10], rbx
0x180012fd8  lea     rax, [rbp+var_10]
0x180012fdc  mov     [rsp+40h+pptlib], rax; pptlib
0x180012fe1  mov     r9d, edi; lcid
0x180012fe4  movzx   r8d, cs:word_1800701C2; wVerMinor
0x180012fec  movzx   edx, cs:word_1800701C0; wVerMajor
0x180012ff3  mov     rcx, cs:rguid; rguid
0x180012ffa  call    cs:__imp_LoadRegTypeLib
0x180013000  mov     ebx, eax
0x180013002  test    eax, eax
0x180013004  js      loc_18001311B
0x18001300a  mov     [rbp+arg_10], 0
0x180013012  mov     rcx, [rbp+var_10]
0x180013016  mov     rax, [rcx]
0x180013019  lea     r8, [rbp+arg_10]
0x18001301d  mov     rdx, cs:?_tih@?$IDispatchImpl@UIComponentRegistrarControl@@$1?IID_IComponentRegistrarControl@@3U_GUID@@B$1?LIBID_CUSTREGLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IComponentRegistrarControl,&_GUID const IID_IComponentRegistrarControl,&_GUID const LIBID_CUSTREGLib,1,0,ATL::CComTypeInfoHolder>::_tih
0x180013024  mov     rax, [rax+30h]
0x180013028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302d  mov     ebx, eax
0x18001302f  test    eax, eax
0x180013031  js      loc_180013101
0x180013037  mov     rcx, [rbp+arg_10]
0x18001303b  mov     rdi, rcx
0x18001303e  mov     [rbp+arg_0], rcx
0x180013042  test    rcx, rcx
0x180013045  jz      short loc_180013057
0x180013047  mov     rax, [rcx]
0x18001304a  mov     rax, [rax+8]
0x18001304e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013053  mov     rcx, [rbp+arg_10]
0x180013057  mov     [rbp+arg_18], 0
0x18001305f  mov     rax, [rcx]
0x180013062  lea     r8, [rbp+arg_18]
0x180013066  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18001306d  mov     rax, [rax]
0x180013070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013075  test    eax, eax
0x180013077  js      short loc_18001308A
0x180013079  mov     rdx, [rbp+arg_18]; struct IUnknown *
0x18001307d  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180013081  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180013086  mov     rdi, [rbp+arg_0]
0x18001308a  mov     [rbp+arg_0], 0
0x180013092  mov     cs:qword_1800701C8, rdi
0x180013099  mov     ecx, 18h; cb
0x18001309e  call    cs:__imp_CoTaskMemAlloc
0x1800130a4  mov     rdi, rax
0x1800130a7  test    rax, rax
0x1800130aa  jz      short loc_1800130EE
0x1800130ac  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x1800130b3  mov     [rdi], rax
0x1800130b6  lea     rax, ?_tih@?$IDispatchImpl@UIComponentRegistrarControl@@$1?IID_IComponentRegistrarControl@@3U_GUID@@B$1?LIBID_CUSTREGLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IComponentRegistrarControl,&_GUID const IID_IComponentRegistrarControl,&_GUID const LIBID_CUSTREGLib,1,0,ATL::CComTypeInfoHolder>::_tih
0x1800130bd  mov     [rdi+8], rax
0x1800130c1  lea     rcx, stru_1800732E8; lpCriticalSection
0x1800130c8  call    cs:__imp_EnterCriticalSection
0x1800130ce  mov     rcx, cs:qword_180073398
0x1800130d5  mov     [rdi+10h], rcx
0x1800130d9  mov     cs:qword_180073398, rdi
0x1800130e0  lea     rcx, stru_1800732E8; lpCriticalSection
0x1800130e7  call    cs:__imp_LeaveCriticalSection
0x1800130ed  nop
0x1800130ee  lea     rcx, [rbp+arg_18]
0x1800130f2  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x1800130f7  nop
0x1800130f8  lea     rcx, [rbp+arg_0]
0x1800130fc  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x180013101  mov     rcx, [rbp+var_10]
0x180013105  mov     rax, [rcx]
0x180013108  mov     rax, [rax+10h]
0x18001310c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013111  nop
0x180013112  lea     rcx, [rbp+arg_10]
0x180013116  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x18001311b  mov     rdx, cs:qword_1800701C8; struct ITypeInfo *
0x180013122  test    rdx, rdx
0x180013125  jz      short loc_180013138
0x180013127  cmp     cs:qword_1800701D8, 0
0x18001312f  jnz     short loc_180013138
0x180013131  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180013136  mov     ebx, eax
0x180013138  lea     rcx, stru_1800732E8; lpCriticalSection
0x18001313f  call    cs:__imp_LeaveCriticalSection
0x180013145  mov     eax, ebx
0x180013147  add     rsp, 40h
0x18001314b  pop     rdi
0x18001314c  pop     rbx
0x18001314d  pop     rbp
0x18001314e  retn
```
