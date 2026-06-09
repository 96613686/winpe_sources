# std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>(void)

- ea: `0x18000d7ac`
- end: `0x18000d81a`
- name: `??1?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d718`
- `0x18000dab0`
- `0x18000fbec`
- `0x180011d30`

## callees

- `0x18000d7ac`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000d7ed`
- `msvcrt!free` at `0x18000d7ed`

## pseudocode

```c
void __fastcall std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(
        __int64 a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi

  v2 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_QWORD **)(a1 + 8);
    while ( v2 != v3 )
    {
      if ( *v2 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      ++v2;
    }
    free(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000d7ac  mov     [rsp+arg_0], rbx
0x18000d7b1  mov     [rsp+arg_8], rsi
0x18000d7b6  push    rdi
0x18000d7b7  sub     rsp, 20h
0x18000d7bb  mov     rbx, rcx
0x18000d7be  mov     rdi, [rcx]
0x18000d7c1  test    rdi, rdi
0x18000d7c4  jz      short loc_18000D80A
0x18000d7c6  mov     rsi, [rcx+8]
0x18000d7ca  jmp     short loc_18000D7E5
0x18000d7cc  mov     rcx, [rdi]
0x18000d7cf  test    rcx, rcx
0x18000d7d2  jz      short loc_18000D7E1
0x18000d7d4  mov     rax, [rcx]
0x18000d7d7  mov     rax, [rax+10h]
0x18000d7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e0  nop
0x18000d7e1  add     rdi, 8
0x18000d7e5  cmp     rdi, rsi
0x18000d7e8  jnz     short loc_18000D7CC
0x18000d7ea  mov     rcx, [rbx]; Block
0x18000d7ed  call    cs:__imp_free
0x18000d7f3  mov     qword ptr [rbx], 0
0x18000d7fa  mov     qword ptr [rbx+8], 0
0x18000d802  mov     qword ptr [rbx+10h], 0
0x18000d80a  mov     rbx, [rsp+28h+arg_0]
0x18000d80f  mov     rsi, [rsp+28h+arg_8]
0x18000d814  add     rsp, 20h
0x18000d818  pop     rdi
0x18000d819  retn
```
