# ExtensionHost::Process(_IASATTRIBUTE_ARRAY_RPC,long *,long *,long *,_IASATTRIBUTE_ARRAY_RPC *)

- ea: `0x180012740`
- end: `0x180012979`
- name: `?Process@ExtensionHost@@UEAAJU_IASATTRIBUTE_ARRAY_RPC@@PEAJ11PEAU2@@Z`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800028e0`
- `0x1800030ac`
- `0x18000ae5c`
- `0x18000b24c`
- `0x18000b81c`
- `0x18000d604`
- `0x18000df68`
- `0x18000dfa4`
- `0x18001247c`
- `0x1800125a8`
- `0x18001261c`
- `0x180012700`
- `0x180012740`
- `0x180014f94`
- `0x18002b472`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012790`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012879`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ExtensionHost::Process(
        __int64 a1,
        unsigned int *a2,
        unsigned int *a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 a6)
{
  HRESULT Instance; // ebx
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // edx
  __int64 v15; // rsi
  __int64 i; // rbx
  int v17; // eax
  int v18; // edx
  __int64 AttributeCount; // rsi
  unsigned int v20; // ecx
  size_t v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  __int64 j; // rbx
  struct _IASATTRIBUTE *v26; // rax
  __int64 v27; // [rsp+38h] [rbp-280h] BYREF
  __int64 v28; // [rsp+40h] [rbp-278h]
  struct IRequest *ppv[3]; // [rsp+48h] [rbp-270h] BYREF
  _RADIUS_EXTENSION_CONTROL_BLOCK v30; // [rsp+60h] [rbp-258h] BYREF

  ATL::CComPtr<IRequest>::CComPtr<IRequest>(ppv);
  Instance = CoCreateInstance(
               &GUID_6bc096b1_0ce6_11d1_baae_00c04fc2e20d,
               0,
               1u,
               &GUID_6bc096a7_0ce6_11d1_baae_00c04fc2e20d,
               (LPVOID *)ppv);
  if ( Instance >= 0 )
  {
    IASTL::IASRequest::IASRequest((IASTL::IASRequest *)&v27, ppv[0]);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 32LL))(v27, *a3);
    if ( v11 < 0 )
      IASTL::issue_error((IASTL *)(unsigned int)v11, v12);
    IASTL::IASRequest::SetResponse(&v27, (unsigned int)*a4, (unsigned int)*a5);
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 88LL))(v28, *a2);
    if ( v13 < 0 )
      IASTL::issue_error((IASTL *)(unsigned int)v13, v14);
    v15 = *((_QWORD *)a2 + 1);
    for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 96LL))(v28, *(_QWORD *)(v15 + 8 * i));
      if ( v17 < 0 )
        IASTL::issue_error((IASTL *)(unsigned int)v17, v18);
    }
    ControlBlock::ControlBlock(
      (ControlBlock *)&v30,
      *(enum _RADIUS_EXTENSION_POINT *)(a1 + 96),
      (struct IASTL::IASRequest *)&v27);
    RadiusExtensionPoint::Process((RadiusExtensionPoint *)(a1 + 72), &v30);
    AttributeCount = IASTL::IASRequest::GetAttributeCount((IASTL::IASRequest *)&v27);
    v20 = 8 * AttributeCount;
    if ( (unsigned __int64)(8 * AttributeCount) > 0xFFFFFFFF )
    {
      ControlBlock::~ControlBlock((ControlBlock *)&v30);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      ATL::CComPtr<IRequest>::~CComPtr<IRequest>(ppv);
      return 2147942934LL;
    }
    v21 = v20;
    v22 = CoTaskMemAlloc(v20);
    v23 = v22;
    if ( !v22 )
    {
      ControlBlock::~ControlBlock((ControlBlock *)&v30);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      ATL::CComPtr<IRequest>::~CComPtr<IRequest>(ppv);
      return 2147942414LL;
    }
    memset_0(v22, 0, v21);
    for ( j = 0; (unsigned int)j < (unsigned int)AttributeCount; j = (unsigned int)(j + 1) )
    {
      v26 = IASTL::IASRequest::PeekAttribute((IASTL::IASRequest *)&v27, j);
      v23[j] = IASCloneAttribute((__int64)v26);
    }
    Instance = 0;
    *(_DWORD *)a6 = AttributeCount;
    *(_QWORD *)(a6 + 8) = v23;
    *a4 = IASTL::IASRequest::get_Response(&v27);
    *a5 = IASTL::IASRequest::get_Reason((IASTL::IASRequest *)&v27);
    ControlBlock::~ControlBlock((ControlBlock *)&v30);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  ATL::CComPtr<IRequest>::~CComPtr<IRequest>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180012740  push    rbx
0x180012742  push    rsi
0x180012743  push    rdi
0x180012744  push    r12
0x180012746  push    r13
0x180012748  push    r14
0x18001274a  push    r15
0x18001274c  sub     rsp, 280h
0x180012753  mov     r12, r9
0x180012756  mov     rsi, r8
0x180012759  mov     rdi, rdx
0x18001275c  mov     r15, rcx
0x18001275f  mov     r13, [rsp+2B8h+arg_28]
0x180012767  lea     rcx, [rsp+2B8h+var_270]; void *
0x18001276c  call    ??0?$CComPtr@UIRequest@@@ATL@@QEAA@XZ; ATL::CComPtr<IRequest>::CComPtr<IRequest>(void)
0x180012771  nop
0x180012772  lea     rax, [rsp+2B8h+var_270]
0x180012777  mov     [rsp+2B8h+ppv], rax; ppv
0x18001277c  lea     r9, _GUID_6bc096a7_0ce6_11d1_baae_00c04fc2e20d; riid
0x180012783  xor     edx, edx; pUnkOuter
0x180012785  lea     r8d, [rdx+1]; dwClsContext
0x180012789  lea     rcx, _GUID_6bc096b1_0ce6_11d1_baae_00c04fc2e20d; rclsid
0x180012790  call    cs:__imp_CoCreateInstance
0x180012796  mov     ebx, eax
0x180012798  test    eax, eax
0x18001279a  js      loc_18001295A
0x1800127a0  mov     rdx, [rsp+2B8h+var_270]; struct IRequest *
0x1800127a5  lea     rcx, [rsp+2B8h+var_280]; this
0x1800127aa  call    ??0IASRequest@IASTL@@QEAA@PEAUIRequest@@@Z; IASTL::IASRequest::IASRequest(IRequest *)
0x1800127af  nop
0x1800127b0  mov     rcx, [rsp+2B8h+var_280]
0x1800127b5  mov     rax, [rcx]
0x1800127b8  mov     edx, [rsi]
0x1800127ba  mov     rax, [rax+20h]
0x1800127be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127c3  test    eax, eax
0x1800127c5  jns     short loc_1800127CE
0x1800127c7  mov     ecx, eax; this
0x1800127c9  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x1800127ce  mov     r14, [rsp+2B8h+arg_20]
0x1800127d6  mov     r8d, [r14]
0x1800127d9  mov     edx, [r12]
0x1800127dd  lea     rcx, [rsp+2B8h+var_280]
0x1800127e2  call    ?SetResponse@IASRequest@IASTL@@QEAAXW4_IASRESPONSE@@K@Z; IASTL::IASRequest::SetResponse(_IASRESPONSE,ulong)
0x1800127e7  mov     rcx, [rsp+2B8h+var_278]
0x1800127ec  mov     rax, [rcx]
0x1800127ef  mov     edx, [rdi]
0x1800127f1  mov     rax, [rax+58h]
0x1800127f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127fa  test    eax, eax
0x1800127fc  jns     short loc_180012805
0x1800127fe  mov     ecx, eax; this
0x180012800  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x180012805  mov     rsi, [rdi+8]
0x180012809  xor     ebx, ebx
0x18001280b  cmp     ebx, [rdi]
0x18001280d  jnb     short loc_180012833
0x18001280f  mov     rcx, [rsp+2B8h+var_278]
0x180012814  mov     rax, [rcx]
0x180012817  mov     rdx, [rsi+rbx*8]
0x18001281b  mov     rax, [rax+60h]
0x18001281f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012824  test    eax, eax
0x180012826  jns     short loc_18001282F
0x180012828  mov     ecx, eax; this
0x18001282a  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18001282f  inc     ebx
0x180012831  jmp     short loc_18001280B
0x180012833  lea     r8, [rsp+2B8h+var_280]; struct IASTL::IASRequest *
0x180012838  mov     edx, [r15+60h]; enum _RADIUS_EXTENSION_POINT
0x18001283c  lea     rcx, [rsp+2B8h+var_258]; this
0x180012841  call    ??0ControlBlock@@QEAA@W4_RADIUS_EXTENSION_POINT@@AEAVIASRequest@IASTL@@@Z; ControlBlock::ControlBlock(_RADIUS_EXTENSION_POINT,IASTL::IASRequest &)
0x180012846  nop
0x180012847  lea     rcx, [r15+48h]; this
0x18001284b  lea     rdx, [rsp+2B8h+var_258]; struct _RADIUS_EXTENSION_CONTROL_BLOCK *
0x180012850  call    ?Process@RadiusExtensionPoint@@QEBAXPEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@@Z; RadiusExtensionPoint::Process(_RADIUS_EXTENSION_CONTROL_BLOCK *)
0x180012855  lea     rcx, [rsp+2B8h+var_280]; this
0x18001285a  call    ?GetAttributeCount@IASRequest@IASTL@@QEBAKXZ; IASTL::IASRequest::GetAttributeCount(void)
0x18001285f  mov     esi, eax
0x180012861  mov     ecx, esi
0x180012863  shl     rcx, 3
0x180012867  mov     eax, 0FFFFFFFFh
0x18001286c  cmp     rcx, rax
0x18001286f  ja      loc_180012926
0x180012875  mov     ebx, ecx
0x180012877  mov     ecx, ecx; cb
0x180012879  call    cs:__imp_CoTaskMemAlloc
0x18001287f  mov     rdi, rax
0x180012882  test    rax, rax
0x180012885  jnz     short loc_1800128B8
0x180012887  lea     rcx, [rsp+2B8h+var_258]; this
0x18001288c  call    ??1ControlBlock@@QEAA@XZ; ControlBlock::~ControlBlock(void)
0x180012891  nop
0x180012892  mov     rcx, [rsp+2B8h+var_278]
0x180012897  mov     rax, [rcx]
0x18001289a  mov     rax, [rax+10h]
0x18001289e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a3  nop
0x1800128a4  lea     rcx, [rsp+2B8h+var_270]
0x1800128a9  call    ??1?$CComPtr@UIRequest@@@ATL@@QEAA@XZ; ATL::CComPtr<IRequest>::~CComPtr<IRequest>(void)
0x1800128ae  mov     eax, 8007000Eh
0x1800128b3  jmp     loc_180012966
0x1800128b8  mov     r8, rbx; Size
0x1800128bb  xor     edx, edx; Val
0x1800128bd  mov     rcx, rdi; void *
0x1800128c0  call    memset_0
0x1800128c5  xor     ebx, ebx
0x1800128c7  lea     rcx, [rsp+2B8h+var_280]; this
0x1800128cc  cmp     ebx, esi
0x1800128ce  jnb     short loc_1800128E7
0x1800128d0  mov     edx, ebx; unsigned int
0x1800128d2  call    ?PeekAttribute@IASRequest@IASTL@@QEAAPEAU_IASATTRIBUTE@@K@Z; IASTL::IASRequest::PeekAttribute(ulong)
0x1800128d7  mov     rcx, rax
0x1800128da  call    IASCloneAttribute
0x1800128df  mov     [rdi+rbx*8], rax
0x1800128e3  inc     ebx
0x1800128e5  jmp     short loc_1800128C7
0x1800128e7  xor     ebx, ebx
0x1800128e9  mov     [r13+0], esi
0x1800128ed  mov     [r13+8], rdi
0x1800128f1  call    ?get_Response@IASRequest@IASTL@@QEBA?AW4_IASRESPONSE@@XZ; IASTL::IASRequest::get_Response(void)
0x1800128f6  mov     [r12], eax
0x1800128fa  lea     rcx, [rsp+2B8h+var_280]; this
0x1800128ff  call    ?get_Reason@IASRequest@IASTL@@QEBAKXZ; IASTL::IASRequest::get_Reason(void)
0x180012904  mov     [r14], eax
0x180012907  lea     rcx, [rsp+2B8h+var_258]; this
0x18001290c  call    ??1ControlBlock@@QEAA@XZ; ControlBlock::~ControlBlock(void)
0x180012911  nop
0x180012912  mov     rcx, [rsp+2B8h+var_278]
0x180012917  mov     rax, [rcx]
0x18001291a  mov     rax, [rax+10h]
0x18001291e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012923  nop
0x180012924  jmp     short loc_18001295A
0x180012926  lea     rcx, [rsp+2B8h+var_258]; this
0x18001292b  call    ??1ControlBlock@@QEAA@XZ; ControlBlock::~ControlBlock(void)
0x180012930  nop
0x180012931  mov     rcx, [rsp+2B8h+var_278]
0x180012936  mov     rax, [rcx]
0x180012939  mov     rax, [rax+10h]
0x18001293d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012942  nop
0x180012943  lea     rcx, [rsp+2B8h+var_270]
0x180012948  call    ??1?$CComPtr@UIRequest@@@ATL@@QEAA@XZ; ATL::CComPtr<IRequest>::~CComPtr<IRequest>(void)
0x18001294d  mov     eax, 80070216h
0x180012952  jmp     short loc_180012966
0x180012954  jmp     short $+2
0x180012956  mov     ebx, [rsp+2B8h+var_288]
0x18001295a  lea     rcx, [rsp+2B8h+var_270]
0x18001295f  call    ??1?$CComPtr@UIRequest@@@ATL@@QEAA@XZ; ATL::CComPtr<IRequest>::~CComPtr<IRequest>(void)
0x180012964  mov     eax, ebx
0x180012966  add     rsp, 280h
0x18001296d  pop     r15
0x18001296f  pop     r14
0x180012971  pop     r13
0x180012973  pop     r12
0x180012975  pop     rdi
0x180012976  pop     rsi
0x180012977  pop     rbx
0x180012978  retn
```
