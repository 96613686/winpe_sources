# D3D12CreateVersionedRootSignatureDeserializer

- ea: `0x18000f190`
- end: `0x18000f1fa`
- name: `D3D12CreateVersionedRootSignatureDeserializer`
- size: `106`
- prototype: `HRESULT __stdcall(LPCVOID pSrcData, SIZE_T SrcDataSizeInBytes, const IID *const pRootSignatureDeserializerInterface, void **ppRootSignatureDeserializer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006110`
- `0x180009084`
- `0x18000affc`
- `0x18000f190`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall D3D12CreateVersionedRootSignatureDeserializer(
        LPCVOID pSrcData,
        SIZE_T SrcDataSizeInBytes,
        const IID *const pRootSignatureDeserializerInterface,
        void **ppRootSignatureDeserializer)
{
  __int64 CoreExports; // rax
  HRESULT v9; // ebx
  _Smtx_t *v11; // [rsp+30h] [rbp-38h] BYREF
  char v12; // [rsp+38h] [rbp-30h]

  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&v11, &qword_18001E7F8);
  CoreExports = CModule::GetCoreExports((CModule *)&g_Module);
  v9 = (*(__int64 (__fastcall **)(LPCVOID, SIZE_T, const IID *const, void **))(CoreExports + 32))(
         pSrcData,
         SrcDataSizeInBytes,
         pRootSignatureDeserializerInterface,
         ppRootSignatureDeserializer);
  if ( v12 )
    Smtx_unlock_shared(v11);
  return v9;
}

```

## disassembly

```asm
0x18000f190  push    rbx
0x18000f192  push    rbp
0x18000f193  push    rsi
0x18000f194  push    rdi
0x18000f195  sub     rsp, 48h
0x18000f199  mov     rsi, rdx
0x18000f19c  mov     rbp, rcx
0x18000f19f  lea     rdx, qword_18001E7F8
0x18000f1a6  mov     rbx, r9
0x18000f1a9  lea     rcx, [rsp+68h+var_38]
0x18000f1ae  mov     rdi, r8
0x18000f1b1  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18000f1b6  lea     rdx, [rsp+68h+var_38]
0x18000f1bb  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x18000f1c2  call    ?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z; CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)
0x18000f1c7  mov     r9, rbx
0x18000f1ca  mov     r8, rdi
0x18000f1cd  mov     rdx, rsi
0x18000f1d0  mov     rcx, rbp
0x18000f1d3  mov     rax, [rax+20h]
0x18000f1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1dc  cmp     [rsp+68h+var_30], 0
0x18000f1e1  mov     ebx, eax
0x18000f1e3  jz      short loc_18000F1EF
0x18000f1e5  mov     rcx, [rsp+68h+var_38]; _Smtx_t *
0x18000f1ea  call    _Smtx_unlock_shared
0x18000f1ef  mov     eax, ebx
0x18000f1f1  add     rsp, 48h
0x18000f1f5  pop     rdi
0x18000f1f6  pop     rsi
0x18000f1f7  pop     rbp
0x18000f1f8  pop     rbx
0x18000f1f9  retn
```
