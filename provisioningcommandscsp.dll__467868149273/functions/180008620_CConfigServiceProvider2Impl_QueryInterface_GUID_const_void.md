# CConfigServiceProvider2Impl::QueryInterface(_GUID const &,void * *)

- ea: `0x180008620`
- end: `0x180008687`
- name: `?QueryInterface@CConfigServiceProvider2Impl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800065c0`

## callees

- `0x180008620`
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
0x180008620  sub     rsp, 28h
0x180008624  test    r8, r8
0x180008627  jnz     short loc_180008630
0x180008629  mov     eax, 80070057h
0x18000862e  jmp     short loc_180008681
0x180008630  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180008637  cmp     rax, [rdx]
0x18000863a  jnz     short loc_180008649
0x18000863c  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180008643  cmp     rax, [rdx+8]
0x180008647  jz      short loc_180008662
0x180008649  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data1
0x180008650  cmp     rax, [rdx]
0x180008653  jnz     short loc_180008675
0x180008655  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data4
0x18000865c  cmp     rax, [rdx+8]
0x180008660  jnz     short loc_180008675
0x180008662  mov     [r8], rcx
0x180008665  mov     rax, [rcx]
0x180008668  mov     rax, [rax+8]
0x18000866c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008671  xor     eax, eax
0x180008673  jmp     short loc_180008681
0x180008675  mov     qword ptr [r8], 0
0x18000867c  mov     eax, 80004002h
0x180008681  add     rsp, 28h
0x180008685  retn
```
