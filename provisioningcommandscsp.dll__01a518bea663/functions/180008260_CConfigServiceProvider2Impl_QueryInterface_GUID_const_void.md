# CConfigServiceProvider2Impl::QueryInterface(_GUID const &,void * *)

- ea: `0x180008260`
- end: `0x1800082c6`
- name: `?QueryInterface@CConfigServiceProvider2Impl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800062c0`

## callees

- `0x180008260`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::QueryInterface(
        CConfigServiceProvider2Impl *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data4 == *(_QWORD *)a2->Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CConfigServiceProvider2Impl *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180008260  sub     rsp, 28h
0x180008264  test    r8, r8
0x180008267  jnz     short loc_180008270
0x180008269  mov     eax, 80070057h
0x18000826e  jmp     short loc_1800082C1
0x180008270  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180008277  cmp     rax, [rdx]
0x18000827a  jnz     short loc_180008289
0x18000827c  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180008283  cmp     rax, [rdx+8]
0x180008287  jz      short loc_1800082A2
0x180008289  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data1
0x180008290  cmp     rax, [rdx]
0x180008293  jnz     short loc_1800082B5
0x180008295  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data4
0x18000829c  cmp     rax, [rdx+8]
0x1800082a0  jnz     short loc_1800082B5
0x1800082a2  mov     [r8], rcx
0x1800082a5  mov     rax, [rcx]
0x1800082a8  mov     rax, [rax+8]
0x1800082ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b1  xor     eax, eax
0x1800082b3  jmp     short loc_1800082C1
0x1800082b5  mov     qword ptr [r8], 0
0x1800082bc  mov     eax, 80004002h
0x1800082c1  add     rsp, 28h
0x1800082c5  retn
```
