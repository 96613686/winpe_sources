# D3D12EnableExperimentalFeatures

- ea: `0x18000f280`
- end: `0x18000f2e8`
- name: `D3D12EnableExperimentalFeatures`
- size: `104`
- prototype: `HRESULT __stdcall(UINT NumFeatures, const IID *pIIDs, void *pConfigurationStructs, UINT *pConfigurationStructSizes)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006110`
- `0x180009084`
- `0x18000affc`
- `0x18000f280`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall D3D12EnableExperimentalFeatures(
        UINT NumFeatures,
        const IID *pIIDs,
        void *pConfigurationStructs,
        UINT *pConfigurationStructSizes)
{
  __int64 (__fastcall **CoreExports)(); // rax
  HRESULT v9; // ebx
  _Smtx_t *v11; // [rsp+30h] [rbp-38h] BYREF
  char v12; // [rsp+38h] [rbp-30h]

  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&v11, &qword_18001E7F8);
  CoreExports = CModule::GetCoreExports((CModule *)&g_Module, (__int64)&v11);
  v9 = ((__int64 (__fastcall *)(_QWORD, const IID *, void *, UINT *))CoreExports[5])(
         NumFeatures,
         pIIDs,
         pConfigurationStructs,
         pConfigurationStructSizes);
  if ( v12 )
    Smtx_unlock_shared(v11);
  return v9;
}

```

## disassembly

```asm
0x18000f280  push    rbx
0x18000f282  push    rbp
0x18000f283  push    rsi
0x18000f284  push    rdi
0x18000f285  sub     rsp, 48h
0x18000f289  mov     rsi, rdx
0x18000f28c  mov     ebp, ecx
0x18000f28e  lea     rdx, qword_18001E7F8
0x18000f295  mov     rbx, r9
0x18000f298  lea     rcx, [rsp+68h+var_38]
0x18000f29d  mov     rdi, r8
0x18000f2a0  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18000f2a5  lea     rdx, [rsp+68h+var_38]
0x18000f2aa  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x18000f2b1  call    ?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z; CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)
0x18000f2b6  mov     r9, rbx
0x18000f2b9  mov     r8, rdi
0x18000f2bc  mov     rdx, rsi
0x18000f2bf  mov     ecx, ebp
0x18000f2c1  mov     rax, [rax+28h]
0x18000f2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2ca  cmp     [rsp+68h+var_30], 0
0x18000f2cf  mov     ebx, eax
0x18000f2d1  jz      short loc_18000F2DD
0x18000f2d3  mov     rcx, [rsp+68h+var_38]; _Smtx_t *
0x18000f2d8  call    _Smtx_unlock_shared
0x18000f2dd  mov     eax, ebx
0x18000f2df  add     rsp, 48h
0x18000f2e3  pop     rdi
0x18000f2e4  pop     rsi
0x18000f2e5  pop     rbp
0x18000f2e6  pop     rbx
0x18000f2e7  retn
```
