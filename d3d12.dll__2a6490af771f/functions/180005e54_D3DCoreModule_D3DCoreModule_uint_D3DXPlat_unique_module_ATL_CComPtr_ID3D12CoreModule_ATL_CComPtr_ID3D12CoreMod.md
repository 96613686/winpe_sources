# D3DCoreModule::D3DCoreModule(uint,D3DXPlat::unique_module,ATL::CComPtr<ID3D12CoreModule>,ATL::CComPtr<ID3D12CoreModule1>,ATL::CComPtr<ID3D12CoreModule2>)

- ea: `0x180005e54`
- end: `0x180005fca`
- name: `??0D3DCoreModule@@QEAA@IVunique_module@D3DXPlat@@V?$CComPtr@UID3D12CoreModule@@@ATL@@V?$CComPtr@UID3D12CoreModule1@@@4@V?$CComPtr@UID3D12CoreModule2@@@4@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006228`

## callees

- `0x180002988`
- `0x180005e54`
- `0x180005fd0`
- `0x1800071a0`
- `0x1800071bc`
- `0x18000be78`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005f93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005f93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall D3DCoreModule::D3DCoreModule(
        __int64 a1,
        unsigned int a2,
        HMODULE *a3,
        __int64 *a4,
        unsigned __int64 a5,
        _QWORD *a6)
{
  HMODULE v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // r14
  __int64 v13; // rcx
  _QWORD *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // rcx
  const char **v17; // r8
  __int64 v18; // rcx
  CD3D12TelemetryHelper *v19; // rcx

  v10 = *a3;
  *a3 = 0;
  *(_QWORD *)a1 = v10;
  v11 = *a4;
  *(_QWORD *)(a1 + 8) = *a4;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = a5;
  v13 = *(_QWORD *)a5;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)a5;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  v14 = a6;
  v15 = *a6;
  *(_QWORD *)(a1 + 24) = *a6;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  memset_0((void *)(a1 + 32), 0, 0x90u);
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  std::_Tree<std::_Tmap_traits<_LUID,IUnknown *,std::less<_LUID>,std::allocator<std::pair<_LUID const,IUnknown *>>,0>>::_Alloc_sentinel_and_proxy();
  v16 = *(_QWORD *)(a1 + 24);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 88LL))(v16, a1 + 32);
  }
  else
  {
    v18 = *(_QWORD *)(a1 + 16);
    if ( v18 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 80LL))(v18, a1 + 32);
    else
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 8) + 64LL))(*(_QWORD *)(a1 + 8), a1 + 32);
  }
  a6 = 0;
  a5 = 0;
  DxgAppCompat::GetAppCompatStringPointerImpl((DxgAppCompat *)&a6, &a5, v17);
  (*(void (__fastcall **)(_QWORD *, unsigned __int64))(a1 + 88))(a6, a5);
  CD3D12TelemetryHelper::LogD3D12CoreLoaded(v19, a2);
  if ( *a3 )
    FreeLibrary(*a3);
  *a3 = 0;
  ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(a4);
  ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(v12);
  ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(v14);
  return a1;
}

```

## disassembly

```asm
0x180005e54  push    rbx
0x180005e56  push    rbp
0x180005e57  push    rsi
0x180005e58  push    rdi
0x180005e59  push    r12
0x180005e5b  push    r14
0x180005e5d  push    r15
0x180005e5f  sub     rsp, 20h
0x180005e63  mov     rbp, r9
0x180005e66  mov     rdi, r8
0x180005e69  mov     r12d, edx
0x180005e6c  mov     rbx, rcx
0x180005e6f  mov     rax, [r8]
0x180005e72  mov     qword ptr [r8], 0
0x180005e79  mov     [rcx], rax
0x180005e7c  mov     rcx, [r9]
0x180005e7f  mov     [rbx+8], rcx
0x180005e83  test    rcx, rcx
0x180005e86  jz      short loc_180005E95
0x180005e88  mov     rax, [rcx]
0x180005e8b  mov     rax, [rax+8]
0x180005e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e94  nop
0x180005e95  mov     r14, [rsp+58h+arg_20]
0x180005e9d  mov     rcx, [r14]
0x180005ea0  mov     [rbx+10h], rcx
0x180005ea4  test    rcx, rcx
0x180005ea7  jz      short loc_180005EB6
0x180005ea9  mov     rax, [rcx]
0x180005eac  mov     rax, [rax+8]
0x180005eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb5  nop
0x180005eb6  mov     r15, [rsp+58h+arg_28]
0x180005ebe  mov     rcx, [r15]
0x180005ec1  mov     [rbx+18h], rcx
0x180005ec5  test    rcx, rcx
0x180005ec8  jz      short loc_180005ED7
0x180005eca  mov     rax, [rcx]
0x180005ecd  mov     rax, [rax+8]
0x180005ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed6  nop
0x180005ed7  lea     rsi, [rbx+20h]
0x180005edb  xor     edx, edx; Val
0x180005edd  mov     r8d, 90h; Size
0x180005ee3  mov     rcx, rsi; void *
0x180005ee6  call    memset_0
0x180005eeb  lea     rcx, [rbx+0B0h]
0x180005ef2  mov     qword ptr [rcx], 0
0x180005ef9  mov     qword ptr [rcx+8], 0
0x180005f01  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_LUID@@PEAUIUnknown@@U?$less@U_LUID@@@std@@V?$allocator@U?$pair@$$CBU_LUID@@PEAUIUnknown@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_LUID,IUnknown *,std::less<_LUID>,std::allocator<std::pair<_LUID const,IUnknown *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180005f06  mov     rcx, [rbx+18h]
0x180005f0a  test    rcx, rcx
0x180005f0d  jz      short loc_180005F18
0x180005f0f  mov     rax, [rcx]
0x180005f12  mov     rax, [rax+58h]
0x180005f16  jmp     short loc_180005F35
0x180005f18  mov     rcx, [rbx+10h]
0x180005f1c  test    rcx, rcx
0x180005f1f  jz      short loc_180005F2A
0x180005f21  mov     rax, [rcx]
0x180005f24  mov     rax, [rax+50h]
0x180005f28  jmp     short loc_180005F35
0x180005f2a  mov     rcx, [rbx+8]
0x180005f2e  mov     rax, [rcx]
0x180005f31  mov     rax, [rax+40h]
0x180005f35  mov     rdx, rsi
0x180005f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3d  mov     [rsp+58h+arg_28], 0
0x180005f49  mov     [rsp+58h+arg_20], 0
0x180005f55  lea     rdx, [rsp+58h+arg_20]; unsigned __int64 *
0x180005f5d  lea     rcx, [rsp+58h+arg_28]; this
0x180005f65  call    ?GetAppCompatStringPointerImpl@DxgAppCompat@@YAXPEA_KPEAPEBD@Z; DxgAppCompat::GetAppCompatStringPointerImpl(unsigned __int64 *,char const * *)
0x180005f6a  mov     rdx, [rsp+58h+arg_20]
0x180005f72  mov     rcx, [rsp+58h+arg_28]
0x180005f7a  mov     rax, [rbx+58h]
0x180005f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f83  mov     edx, r12d; unsigned int
0x180005f86  call    ?LogD3D12CoreLoaded@CD3D12TelemetryHelper@@QEAAXI@Z; CD3D12TelemetryHelper::LogD3D12CoreLoaded(uint)
0x180005f8b  mov     rcx, [rdi]; hLibModule
0x180005f8e  test    rcx, rcx
0x180005f91  jz      short loc_180005F99
0x180005f93  call    cs:__imp_FreeLibrary
0x180005f99  mov     qword ptr [rdi], 0
0x180005fa0  mov     rcx, rbp
0x180005fa3  call    ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
0x180005fa8  mov     rcx, r14
0x180005fab  call    ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
0x180005fb0  mov     rcx, r15
0x180005fb3  call    ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
0x180005fb8  mov     rax, rbx
0x180005fbb  add     rsp, 20h
0x180005fbf  pop     r15
0x180005fc1  pop     r14
0x180005fc3  pop     r12
0x180005fc5  pop     rdi
0x180005fc6  pop     rsi
0x180005fc7  pop     rbp
0x180005fc8  pop     rbx
0x180005fc9  retn
```
