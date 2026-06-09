# D3D12CreateAdditionalDeviceImpl(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)

- ea: `0x18000ac30`
- end: `0x18000aceb`
- name: `?D3D12CreateAdditionalDeviceImpl@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z`
- size: `187`
- prototype: `__int64 __fastcall(struct IUnknown *, enum D3D_FEATURE_LEVEL, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006110`
- `0x180009084`
- `0x18000ac30`
- `0x18000affc`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall D3D12CreateAdditionalDeviceImpl(
        struct IUnknown *a1,
        unsigned int a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rbx
  __int64 (__fastcall **CoreExports)(); // rax
  unsigned int v10; // edi
  _Smtx_t *v12; // [rsp+40h] [rbp-48h] BYREF
  char v13; // [rsp+48h] [rbp-40h]

  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&v12, &qword_18001E7F8);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_BYTE *)(v8 + 16) = 1;
  CoreExports = CModule::GetCoreExports((CModule *)&g_Module, (__int64)&v12);
  *(_QWORD *)(v8 + 8) = qword_18001E870;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, __int64 *, __int64, const struct _GUID *, void **))*CoreExports)(
          a1,
          a2,
          0,
          &qword_180016258,
          1,
          a3,
          a4);
  *(_BYTE *)(v8 + 16) = 0;
  if ( v13 )
    Smtx_unlock_shared(v12);
  return v10;
}

```

## disassembly

```asm
0x18000ac30  push    rbx
0x18000ac32  push    rbp
0x18000ac33  push    rsi
0x18000ac34  push    rdi
0x18000ac35  push    r14
0x18000ac37  push    r15
0x18000ac39  sub     rsp, 58h
0x18000ac3d  mov     rdi, r9
0x18000ac40  mov     rsi, r8
0x18000ac43  mov     ebp, edx
0x18000ac45  mov     r14, rcx
0x18000ac48  lea     rdx, qword_18001E7F8
0x18000ac4f  lea     rcx, [rsp+88h+var_48]
0x18000ac54  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18000ac59  nop
0x18000ac5a  mov     r10d, cs:_tls_index
0x18000ac61  mov     rax, gs:58h
0x18000ac6a  mov     rbx, [rax+r10*8]
0x18000ac6e  mov     r15d, 10h
0x18000ac74  mov     byte ptr [r15+rbx], 1
0x18000ac79  lea     rdx, [rsp+88h+var_48]
0x18000ac7e  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x18000ac85  call    ?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z; CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)
0x18000ac8a  mov     edx, 8
0x18000ac8f  mov     rcx, cs:qword_18001E870
0x18000ac96  mov     [rdx+rbx], rcx
0x18000ac9a  mov     [rsp+88h+var_58], rdi
0x18000ac9f  mov     [rsp+88h+var_60], rsi
0x18000aca4  mov     [rsp+88h+var_68], 1
0x18000acad  lea     r9, qword_180016258
0x18000acb4  xor     r8d, r8d
0x18000acb7  mov     edx, ebp
0x18000acb9  mov     rcx, r14
0x18000acbc  mov     rax, [rax]
0x18000acbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc4  mov     edi, eax
0x18000acc6  mov     byte ptr [r15+rbx], 0
0x18000accb  cmp     [rsp+88h+var_40], 0
0x18000acd0  jz      short loc_18000ACDC
0x18000acd2  mov     rcx, [rsp+88h+var_48]; _Smtx_t *
0x18000acd7  call    _Smtx_unlock_shared
0x18000acdc  mov     eax, edi
0x18000acde  add     rsp, 58h
0x18000ace2  pop     r15
0x18000ace4  pop     r14
0x18000ace6  pop     rdi
0x18000ace7  pop     rsi
0x18000ace8  pop     rbp
0x18000ace9  pop     rbx
0x18000acea  retn
```
