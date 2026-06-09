# D3D12CreateDeviceImpl(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)

- ea: `0x180006060`
- end: `0x18000610a`
- name: `?D3D12CreateDeviceImpl@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct IUnknown *, enum D3D_FEATURE_LEVEL, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006060`
- `0x180006110`
- `0x18000afdc`
- `0x18000affc`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall D3D12CreateDeviceImpl(struct IUnknown *a1, unsigned int a2, const struct _GUID *a3, void **a4)
{
  __int64 (__fastcall **CoreExports)(); // rax
  __int64 v9; // r8
  unsigned int v10; // ebx
  _Smtx_t *v12; // [rsp+40h] [rbp-38h] BYREF
  char v13; // [rsp+48h] [rbp-30h]

  v12 = &qword_18001E7F8;
  v13 = 1;
  Smtx_lock_shared(&qword_18001E7F8);
  CoreExports = CModule::GetCoreExports((CModule *)&g_Module, (__int64)&v12);
  *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) = qword_18001E870;
  LOBYTE(v9) = 1;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, __int64 *, __int64, const struct _GUID *, void **))*CoreExports)(
          a1,
          a2,
          v9,
          &qword_180016258,
          1,
          a3,
          a4);
  if ( v13 )
    Smtx_unlock_shared(v12);
  return v10;
}

```

## disassembly

```asm
0x180006060  push    rbx
0x180006062  push    rbp
0x180006063  push    rsi
0x180006064  push    rdi
0x180006065  sub     rsp, 58h
0x180006069  mov     rbx, r9
0x18000606c  mov     rdi, r8
0x18000606f  mov     esi, edx
0x180006071  mov     rbp, rcx
0x180006074  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000607b  mov     [rsp+78h+var_38], rcx
0x180006080  mov     [rsp+78h+var_30], 1
0x180006085  call    _Smtx_lock_shared
0x18000608a  nop
0x18000608b  lea     rdx, [rsp+78h+var_38]
0x180006090  lea     rcx, ?g_Module@@3VCModule@@A; CModule g_Module
0x180006097  call    ?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z; CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)
0x18000609c  mov     edx, cs:_tls_index
0x1800060a2  mov     rcx, gs:58h
0x1800060ab  mov     r9d, 8
0x1800060b1  mov     rdx, [rcx+rdx*8]
0x1800060b5  mov     rcx, cs:qword_18001E870
0x1800060bc  mov     [r9+rdx], rcx
0x1800060c0  mov     [rsp+78h+var_48], rbx
0x1800060c5  mov     [rsp+78h+var_50], rdi
0x1800060ca  mov     [rsp+78h+var_58], 1
0x1800060d3  lea     r9, qword_180016258
0x1800060da  mov     r8b, 1
0x1800060dd  mov     edx, esi
0x1800060df  mov     rcx, rbp
0x1800060e2  mov     rax, [rax]
0x1800060e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ea  mov     ebx, eax
0x1800060ec  cmp     [rsp+78h+var_30], 0
0x1800060f1  jnz     short loc_1800060FE
0x1800060f3  mov     eax, ebx
0x1800060f5  add     rsp, 58h
0x1800060f9  pop     rdi
0x1800060fa  pop     rsi
0x1800060fb  pop     rbp
0x1800060fc  pop     rbx
0x1800060fd  retn
0x1800060fe  mov     rcx, [rsp+78h+var_38]; _Smtx_t *
0x180006103  call    _Smtx_unlock_shared
0x180006108  jmp     short loc_1800060F3
```
