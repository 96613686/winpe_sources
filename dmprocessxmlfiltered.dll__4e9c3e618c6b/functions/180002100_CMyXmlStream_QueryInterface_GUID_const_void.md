# CMyXmlStream::QueryInterface(_GUID const &,void * *)

- ea: `0x180002100`
- end: `0x18000216c`
- name: `?QueryInterface@CMyXmlStream@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(CMyXmlStream *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002100`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall CMyXmlStream::QueryInterface(CMyXmlStream *this, const struct _GUID *a2, void **a3)
{
  if ( (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4)
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_0000000c_0000_0000_c000_000000000046.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_0000000c_0000_0000_c000_000000000046.Data4)
    && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d.Data4) )
  {
    return 2147500034LL;
  }
  *a3 = this;
  (*(void (__fastcall **)(CMyXmlStream *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x180002100  sub     rsp, 28h
0x180002104  mov     rax, [rdx]
0x180002107  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x18000210e  jnz     short loc_18000211D
0x180002110  mov     rax, [rdx+8]
0x180002114  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000211b  jz      short loc_18000214F
0x18000211d  mov     rax, [rdx]
0x180002120  cmp     rax, qword ptr cs:_GUID_0000000c_0000_0000_c000_000000000046.Data1
0x180002127  jnz     short loc_180002136
0x180002129  mov     rax, [rdx+8]
0x18000212d  cmp     rax, qword ptr cs:_GUID_0000000c_0000_0000_c000_000000000046.Data4
0x180002134  jz      short loc_18000214F
0x180002136  mov     rax, [rdx]
0x180002139  cmp     rax, qword ptr cs:_GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d.Data1
0x180002140  jnz     short loc_180002162
0x180002142  mov     rax, [rdx+8]
0x180002146  cmp     rax, qword ptr cs:_GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d.Data4
0x18000214d  jnz     short loc_180002162
0x18000214f  mov     [r8], rcx
0x180002152  mov     rax, [rcx]
0x180002155  mov     rax, [rax+8]
0x180002159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000215e  xor     eax, eax
0x180002160  jmp     short loc_180002167
0x180002162  mov     eax, 80004002h
0x180002167  add     rsp, 28h
0x18000216b  retn
```
