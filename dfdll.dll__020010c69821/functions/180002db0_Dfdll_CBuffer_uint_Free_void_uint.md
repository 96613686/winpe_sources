# Dfdll::CBuffer<uint>::Free(void * &,uint &)

- ea: `0x180002db0`
- end: `0x180002ddf`
- name: `?Free@?$CBuffer@I@Dfdll@@MEAAXAEAPEAXAEAI@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180002db0`
- `0x180012b30`

## pseudocode

```c
void __fastcall Dfdll::CBuffer<unsigned int>::Free(__int64 a1, void **a2, _DWORD *a3)
{
  if ( *a2 )
  {
    operator delete(*a2, (const struct std::nothrow_t *)a2);
    *a2 = 0;
  }
  *a3 = 0;
}

```

## disassembly

```asm
0x180002db0  mov     [rsp+arg_0], rbx
0x180002db5  push    rdi
0x180002db6  sub     rsp, 20h
0x180002dba  mov     rcx, [rdx]; void *
0x180002dbd  mov     rdi, r8
0x180002dc0  mov     rbx, rdx
0x180002dc3  test    rcx, rcx
0x180002dc6  jz      short loc_180002DD1
0x180002dc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002dcd  and     qword ptr [rbx], 0
0x180002dd1  and     dword ptr [rdi], 0
0x180002dd4  mov     rbx, [rsp+28h+arg_0]
0x180002dd9  add     rsp, 20h
0x180002ddd  pop     rdi
0x180002dde  retn
```
