# Dfdll::CArray<Dfdll::CBuffer<uint>,uint>::~CArray<Dfdll::CBuffer<uint>,uint>(void)

- ea: `0x180008b00`
- end: `0x180008b49`
- name: `??1?$CArray@V?$CBuffer@I@Dfdll@@I@Dfdll@@UEAA@XZ`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f42e`

## callees

- `0x180008b00`
- `0x180012b30`

## pseudocode

```c
void **__fastcall Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::~CArray<Dfdll::CBuffer<unsigned int>,unsigned int>(
        __int64 a1,
        const struct std::nothrow_t *a2)
{
  void *v3; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::`vftable';
  *(_QWORD *)(a1 + 24) = &Dfdll::CBuffer<unsigned int>::`vftable';
  v3 = *(void **)(a1 + 32);
  if ( v3 )
    operator delete(v3, a2);
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  result = &Dfdll::CObject::`vftable';
  *(_QWORD *)(a1 + 24) = &Dfdll::CObject::`vftable';
  *(_QWORD *)a1 = &Dfdll::CObject::`vftable';
  return result;
}

```

## disassembly

```asm
0x180008b00  push    rbx
0x180008b02  sub     rsp, 20h
0x180008b06  mov     rbx, rcx
0x180008b09  lea     rax, ??_7?$CArray@V?$CBuffer@I@Dfdll@@I@Dfdll@@6B@; const Dfdll::CArray<Dfdll::CBuffer<uint>,uint>::`vftable'
0x180008b10  mov     [rcx], rax
0x180008b13  lea     rax, ??_7?$CBuffer@I@Dfdll@@6B@; const Dfdll::CBuffer<uint>::`vftable'
0x180008b1a  mov     [rcx+18h], rax
0x180008b1e  mov     rcx, [rcx+20h]; void *
0x180008b22  test    rcx, rcx
0x180008b25  jz      short loc_180008B2C
0x180008b27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008b2c  and     qword ptr [rbx+20h], 0
0x180008b31  and     dword ptr [rbx+28h], 0
0x180008b35  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008b3c  mov     [rbx+18h], rax
0x180008b40  mov     [rbx], rax
0x180008b43  add     rsp, 20h
0x180008b47  pop     rbx
0x180008b48  retn
```
