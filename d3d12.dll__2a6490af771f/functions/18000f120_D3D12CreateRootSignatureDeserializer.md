# D3D12CreateRootSignatureDeserializer

- ea: `0x18000f120`
- end: `0x18000f18a`
- name: `D3D12CreateRootSignatureDeserializer`
- size: `106`
- prototype: `HRESULT __stdcall(LPCVOID pSrcData, SIZE_T SrcDataSizeInBytes, const IID *const pRootSignatureDeserializerInterface, void **ppRootSignatureDeserializer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006110`
- `0x180009084`
- `0x18000affc`
- `0x18000f120`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall D3D12CreateRootSignatureDeserializer(
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
  v9 = (*(__int64 (__fastcall **)(LPCVOID, SIZE_T, const IID *const, void **))(CoreExports + 16))(
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
0x18000f120  push    rbx
0x18000f122  push    rbp
0x18000f123  push    rsi
0x18000f124  push    rdi
0x18000f125  sub     rsp, 48h
0x18000f129  mov     rsi, rdx
0x18000f12c  mov     rbp, rcx
0x18000f12f  lea     rdx, qword_18001E7F8
0x18000f136  mov     rbx, r9
0x18000f139  lea     rcx, [rsp+68h+var_38]
0x18000f13e  mov     rdi, r8
0x18000f141  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18000f146  lea     rdx, [rsp+68h+var_38]
0x18000f14b  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x18000f152  call    ?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z; CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)
0x18000f157  mov     r9, rbx
0x18000f15a  mov     r8, rdi
0x18000f15d  mov     rdx, rsi
0x18000f160  mov     rcx, rbp
0x18000f163  mov     rax, [rax+10h]
0x18000f167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f16c  cmp     [rsp+68h+var_30], 0
0x18000f171  mov     ebx, eax
0x18000f173  jz      short loc_18000F17F
0x18000f175  mov     rcx, [rsp+68h+var_38]; _Smtx_t *
0x18000f17a  call    _Smtx_unlock_shared
0x18000f17f  mov     eax, ebx
0x18000f181  add     rsp, 48h
0x18000f185  pop     rdi
0x18000f186  pop     rsi
0x18000f187  pop     rbp
0x18000f188  pop     rbx
0x18000f189  retn
```
