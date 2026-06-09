# ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>::EnumConnectionPoints(IEnumConnectionPoints * *)

- ea: `0x180032900`
- end: `0x180032ae7`
- name: `?EnumConnectionPoints@?$IConnectionPointContainerImpl@VCMsftWriteEngine2@@@ATL@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000c760`
- `0x18000ea20`
- `0x18000fc4c`
- `0x18000fd58`
- `0x18000fdd4`
- `0x180011024`
- `0x1800167e4`
- `0x18001709c`
- `0x18002135c`
- `0x180032900`
- `0x180049880`
- `0x180049940`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>::EnumConnectionPoints(__int64 a1, _QWORD *a2)
{
  void *v5; // rax
  struct IUnknown *v6; // rax
  struct IUnknown *v7; // rbx
  unsigned __int64 v8; // rdx
  ATL::_ATL_SAFE_ALLOCA_IMPL *v9; // rdi
  __int64 v10; // rax
  void *v11; // rsp
  struct IUnknown **v12; // rsi
  __int64 (__fastcall **v13)(_QWORD); // rdx
  __int64 (__fastcall *v14)(_QWORD); // rcx
  int v15; // r15d
  __int64 v16; // rax
  int v17; // edi
  unsigned int v18; // ebx
  struct IUnknown *v19; // [rsp+30h] [rbp+0h] BYREF
  int v20; // [rsp+38h] [rbp+8h] BYREF
  __int64 v21; // [rsp+40h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v19 = 0;
  v5 = operator new(0x90u);
  if ( !v5 )
    goto LABEL_25;
  v6 = (struct IUnknown *)ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>(v5);
  if ( !v6 )
    goto LABEL_25;
  ATL::AtlComPtrAssign(&v19, v6);
  v7 = v19;
  if ( !v19 )
    goto LABEL_25;
  v20 = 0;
  CMsftWriteEngine2::GetConnMap(&v20);
  v21 = 0;
  if ( v20 < 0 || (unsigned __int64)v20 > 0xFFFFFFF )
    goto LABEL_24;
  v9 = (ATL::_ATL_SAFE_ALLOCA_IMPL *)(8LL * v20);
  if ( (unsigned __int64)v9 <= 0x400 && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(v9, v8) )
  {
    v10 = (__int64)v9 + 15;
    if ( (ATL::_ATL_SAFE_ALLOCA_IMPL *)((char *)v9 + 15) < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    v12 = &v19;
  }
  else
  {
    v12 = (struct IUnknown **)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::Allocate(
                                &v21,
                                v9);
  }
  if ( !v12 )
  {
LABEL_24:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
LABEL_25:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
    return 2147942414LL;
  }
  v13 = (__int64 (__fastcall **)(_QWORD))ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>::pConnMap;
  v14 = *(__int64 (__fastcall **)(_QWORD))ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>::pConnMap;
  if ( *(_QWORD *)ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>::pConnMap != -1 )
  {
    v15 = 0;
    do
    {
      ++v13;
      if ( v14 == (__int64 (__fastcall *)(_QWORD))-2LL )
      {
        v13 = (__int64 (__fastcall **)(_QWORD))(*v13)(0);
      }
      else
      {
        v16 = v15++;
        v12[v16] = (struct IUnknown *)((char *)v14 + a1);
      }
      v14 = *v13;
    }
    while ( *v13 != (__int64 (__fastcall *)(_QWORD))-1LL );
  }
  v17 = ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(
          v7,
          v12,
          (char *)v12 + (_QWORD)v9,
          a1,
          3);
  if ( v17 >= 0 )
  {
    v18 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))v7->lpVtbl->QueryInterface)(
            v7,
            &GUID_b196b285_bab4_101a_b69c_00aa00341d07,
            a2);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
    return v18;
  }
  else
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x180032900  push    rbp
0x180032902  push    rbx
0x180032903  push    rsi
0x180032904  push    rdi
0x180032905  push    r12
0x180032907  push    r14
0x180032909  push    r15
0x18003290b  sub     rsp, 50h
0x18003290f  lea     rbp, [rsp+30h]
0x180032914  mov     rax, cs:__security_cookie
0x18003291b  xor     rax, rbp
0x18003291e  mov     [rbp+50h+var_38], rax
0x180032922  mov     r14, rdx
0x180032925  mov     r12, rcx
0x180032928  test    rdx, rdx
0x18003292b  jnz     short loc_180032937
0x18003292d  mov     eax, 80004003h
0x180032932  jmp     loc_180032ACC
0x180032937  mov     ecx, 90h; Size
0x18003293c  mov     qword ptr [rdx], 0
0x180032943  mov     [rbp+50h+var_50], 0
0x18003294b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032950  test    rax, rax
0x180032953  jz      loc_180032ABE
0x180032959  mov     rcx, rax
0x18003295c  call    ??0?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>(void *)
0x180032961  test    rax, rax
0x180032964  jz      loc_180032ABE
0x18003296a  mov     rdx, rax; struct IUnknown *
0x18003296d  lea     rcx, [rbp+50h+var_50]; struct IUnknown **
0x180032971  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180032976  mov     rbx, [rbp+50h+var_50]
0x18003297a  test    rbx, rbx
0x18003297d  jz      loc_180032ABE
0x180032983  lea     rcx, [rbp+50h+var_48]; int *
0x180032987  mov     [rbp+50h+var_48], 0
0x18003298e  call    ?GetConnMap@CMsftWriteEngine2@@SAPEBU_ATL_CONNMAP_ENTRY@ATL@@PEAH@Z; CMsftWriteEngine2::GetConnMap(int *)
0x180032993  movsxd  rax, [rbp+50h+var_48]
0x180032997  mov     [rbp+50h+var_40], 0
0x18003299f  test    eax, eax
0x1800329a1  js      loc_180032AB5
0x1800329a7  mov     rdi, rax
0x1800329aa  cmp     rax, 0FFFFFFFh
0x1800329b0  ja      loc_180032AB5
0x1800329b6  shl     rdi, 3
0x1800329ba  cmp     rdi, 400h
0x1800329c1  ja      short loc_1800329F5
0x1800329c3  mov     rcx, rdi; this
0x1800329c6  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800329cb  test    al, al
0x1800329cd  jz      short loc_1800329F5
0x1800329cf  lea     rax, [rdi+0Fh]
0x1800329d3  cmp     rax, rdi
0x1800329d6  ja      short loc_1800329E2
0x1800329d8  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800329e2  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800329e6  call    _alloca_probe
0x1800329eb  sub     rsp, rax
0x1800329ee  lea     rsi, [rsp+80h+var_50]
0x1800329f3  jmp     short loc_180032A04
0x1800329f5  mov     rdx, rdi
0x1800329f8  lea     rcx, [rbp+50h+var_40]
0x1800329fc  call    ?Allocate@?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180032a01  mov     rsi, rax
0x180032a04  test    rsi, rsi
0x180032a07  jz      loc_180032AB5
0x180032a0d  mov     rdx, cs:?pConnMap@?$IConnectionPointContainerImpl@VCMsftWriteEngine2@@@ATL@@0PEBU_ATL_CONNMAP_ENTRY@2@EB; ATL::_ATL_CONNMAP_ENTRY const * const ATL::IConnectionPointContainerImpl<CMsftWriteEngine2>::pConnMap
0x180032a14  mov     rcx, [rdx]
0x180032a17  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180032a1b  jz      short loc_180032A4F
0x180032a1d  xor     r15d, r15d
0x180032a20  add     rdx, 8
0x180032a24  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x180032a28  jnz     short loc_180032A39
0x180032a2a  mov     rax, [rdx]
0x180032a2d  xor     ecx, ecx
0x180032a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a34  mov     rdx, rax
0x180032a37  jmp     short loc_180032A46
0x180032a39  movsxd  rax, r15d
0x180032a3c  add     rcx, r12
0x180032a3f  inc     r15d
0x180032a42  mov     [rsi+rax*8], rcx
0x180032a46  mov     rcx, [rdx]
0x180032a49  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180032a4d  jnz     short loc_180032A20
0x180032a4f  lea     r8, [rdi+rsi]
0x180032a53  mov     [rsp+80h+var_60], 3
0x180032a5b  mov     r9, r12
0x180032a5e  mov     rdx, rsi
0x180032a61  mov     rcx, rbx
0x180032a64  call    ?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)
0x180032a69  mov     edi, eax
0x180032a6b  test    eax, eax
0x180032a6d  jns     short loc_180032A85
0x180032a6f  lea     rcx, [rbp+50h+var_40]
0x180032a73  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180032a78  lea     rcx, [rbp+50h+var_50]
0x180032a7c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032a81  mov     eax, edi
0x180032a83  jmp     short loc_180032ACC
0x180032a85  mov     rax, [rbx]
0x180032a88  lea     rdx, _GUID_b196b285_bab4_101a_b69c_00aa00341d07
0x180032a8f  mov     r8, r14
0x180032a92  mov     rcx, rbx
0x180032a95  mov     rax, [rax]
0x180032a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a9d  lea     rcx, [rbp+50h+var_40]
0x180032aa1  mov     ebx, eax
0x180032aa3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180032aa8  lea     rcx, [rbp+50h+var_50]
0x180032aac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032ab1  mov     eax, ebx
0x180032ab3  jmp     short loc_180032ACC
0x180032ab5  lea     rcx, [rbp+50h+var_40]
0x180032ab9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180032abe  lea     rcx, [rbp+50h+var_50]
0x180032ac2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032ac7  mov     eax, 8007000Eh
0x180032acc  mov     rcx, [rbp+50h+var_38]
0x180032ad0  xor     rcx, rbp; StackCookie
0x180032ad3  call    __security_check_cookie
0x180032ad8  lea     rsp, [rbp+20h]
0x180032adc  pop     r15
0x180032ade  pop     r14
0x180032ae0  pop     r12
0x180032ae2  pop     rdi
0x180032ae3  pop     rsi
0x180032ae4  pop     rbx
0x180032ae5  pop     rbp
0x180032ae6  retn
```
