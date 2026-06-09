# D3D12CreateVersionedRootSignatureDeserializerFromSubobjectInLibrary

- ea: `0x18000f200`
- end: `0x18000f27a`
- name: `D3D12CreateVersionedRootSignatureDeserializerFromSubobjectInLibrary`
- size: `122`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006110`
- `0x180009084`
- `0x18000affc`
- `0x18000f200`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall D3D12CreateVersionedRootSignatureDeserializerFromSubobjectInLibrary(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 CoreExports; // rax
  unsigned int v10; // ebx
  _Smtx_t *v12; // [rsp+30h] [rbp-38h] BYREF
  char v13; // [rsp+38h] [rbp-30h]

  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&v12, &qword_18001E7F8);
  CoreExports = CModule::GetCoreExports((CModule *)&g_Module);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int64))(CoreExports + 136))(a1, a2, a3, a4, a5);
  if ( v13 )
    Smtx_unlock_shared(v12);
  return v10;
}

```

## disassembly

```asm
0x18000f200  push    rbx
0x18000f202  push    rbp
0x18000f203  push    rsi
0x18000f204  push    rdi
0x18000f205  sub     rsp, 48h
0x18000f209  mov     rsi, rdx
0x18000f20c  mov     rbp, rcx
0x18000f20f  lea     rdx, qword_18001E7F8
0x18000f216  mov     rbx, r9
0x18000f219  lea     rcx, [rsp+68h+var_38]
0x18000f21e  mov     rdi, r8
0x18000f221  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18000f226  lea     rdx, [rsp+68h+var_38]
0x18000f22b  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x18000f232  call    ?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z; CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)
0x18000f237  mov     r10, [rsp+68h+arg_20]
0x18000f23f  mov     r9, rbx
0x18000f242  mov     r8, rdi
0x18000f245  mov     [rsp+68h+var_48], r10
0x18000f24a  mov     rdx, rsi
0x18000f24d  mov     rcx, rbp
0x18000f250  mov     rax, [rax+88h]
0x18000f257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f25c  cmp     [rsp+68h+var_30], 0
0x18000f261  mov     ebx, eax
0x18000f263  jz      short loc_18000F26F
0x18000f265  mov     rcx, [rsp+68h+var_38]; _Smtx_t *
0x18000f26a  call    _Smtx_unlock_shared
0x18000f26f  mov     eax, ebx
0x18000f271  add     rsp, 48h
0x18000f275  pop     rdi
0x18000f276  pop     rsi
0x18000f277  pop     rbp
0x18000f278  pop     rbx
0x18000f279  retn
```
