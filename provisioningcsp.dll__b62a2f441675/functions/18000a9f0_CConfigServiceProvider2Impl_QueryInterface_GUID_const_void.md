# CConfigServiceProvider2Impl::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a9f0`
- end: `0x18000aa57`
- name: `?QueryInterface@CConfigServiceProvider2Impl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180006590`

## callees

- `0x18000a9f0`
- `0x180038010`

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
0x18000a9f0  sub     rsp, 28h
0x18000a9f4  test    r8, r8
0x18000a9f7  jnz     short loc_18000AA00
0x18000a9f9  mov     eax, 80070057h
0x18000a9fe  jmp     short loc_18000AA51
0x18000aa00  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18000aa07  cmp     rax, [rdx]
0x18000aa0a  jnz     short loc_18000AA19
0x18000aa0c  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18000aa13  cmp     rax, [rdx+8]
0x18000aa17  jz      short loc_18000AA32
0x18000aa19  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data1
0x18000aa20  cmp     rax, [rdx]
0x18000aa23  jnz     short loc_18000AA45
0x18000aa25  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data4
0x18000aa2c  cmp     rax, [rdx+8]
0x18000aa30  jnz     short loc_18000AA45
0x18000aa32  mov     [r8], rcx
0x18000aa35  mov     rax, [rcx]
0x18000aa38  mov     rax, [rax+8]
0x18000aa3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa41  xor     eax, eax
0x18000aa43  jmp     short loc_18000AA51
0x18000aa45  mov     qword ptr [r8], 0
0x18000aa4c  mov     eax, 80004002h
0x18000aa51  add     rsp, 28h
0x18000aa55  retn
```
