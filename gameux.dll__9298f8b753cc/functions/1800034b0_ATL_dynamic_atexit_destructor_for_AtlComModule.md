# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x1800034b0`
- end: `0x180003540`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001250`
- `0x1800034b0`
- `0x180004010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000351b`
- `KERNEL32!DeleteCriticalSection` at `0x18000351b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rbx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = off_1800070B8;
    for ( i = off_1800070B0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v0; ++i )
    {
      v2 = *i;
      if ( *i )
      {
        v3 = *((_QWORD *)v2 + 4);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *((_QWORD *)v2 + 4) = 0;
        v0 = off_1800070B8;
      }
    }
    DeleteCriticalSection(&stru_1800070C0);
    ATL::_AtlComModule = 0;
  }
}

```

## disassembly

```asm
0x1800034b0  sub     rsp, 28h
0x1800034b4  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800034bb  jz      short loc_180003530
0x1800034bd  mov     rax, cs:off_1800070B8
0x1800034c4  mov     [rsp+28h+arg_0], rbx
0x1800034c9  mov     rbx, cs:off_1800070B0
0x1800034d0  cmp     rbx, rax
0x1800034d3  jnb     short loc_180003514
0x1800034d5  mov     [rsp+28h+var_8], rdi
0x1800034da  mov     rdi, [rbx]
0x1800034dd  test    rdi, rdi
0x1800034e0  jz      short loc_180003506
0x1800034e2  mov     rcx, [rdi+20h]
0x1800034e6  test    rcx, rcx
0x1800034e9  jz      short loc_1800034F7
0x1800034eb  mov     rax, [rcx]
0x1800034ee  mov     rax, [rax+10h]
0x1800034f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f7  mov     qword ptr [rdi+20h], 0
0x1800034ff  mov     rax, cs:off_1800070B8
0x180003506  add     rbx, 8
0x18000350a  cmp     rbx, rax
0x18000350d  jb      short loc_1800034DA
0x18000350f  mov     rdi, [rsp+28h+var_8]
0x180003514  lea     rcx, stru_1800070C0; lpCriticalSection
0x18000351b  call    cs:__imp_DeleteCriticalSection
0x180003521  mov     rbx, [rsp+28h+arg_0]
0x180003526  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180003530  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180003537  add     rsp, 28h
0x18000353b  jmp     _guard_check_icall_nop
```
