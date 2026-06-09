# Dfdll::CBuffer<char>::~CBuffer<char>(void)

- ea: `0x180001874`
- end: `0x1800018ae`
- name: `??1?$CBuffer@D@Dfdll@@UEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f06e`
- `0x18001f0aa`
- `0x18001f422`

## callees

- `0x180001874`
- `0x180012b30`

## pseudocode

```c
void **__fastcall Dfdll::CBuffer<char>::~CBuffer<char>(__int64 a1, const struct std::nothrow_t *a2)
{
  void *v3; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &Dfdll::CBuffer<unsigned char>::`vftable';
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3, a2);
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  result = &Dfdll::CObject::`vftable';
  *(_QWORD *)a1 = &Dfdll::CObject::`vftable';
  return result;
}

```

## disassembly

```asm
0x180001874  push    rbx
0x180001876  sub     rsp, 20h
0x18000187a  mov     rbx, rcx
0x18000187d  lea     rax, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x180001884  mov     [rcx], rax
0x180001887  mov     rcx, [rcx+8]; void *
0x18000188b  test    rcx, rcx
0x18000188e  jz      short loc_180001895
0x180001890  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001895  and     qword ptr [rbx+8], 0
0x18000189a  and     dword ptr [rbx+10h], 0
0x18000189e  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800018a5  mov     [rbx], rax
0x1800018a8  add     rsp, 20h
0x1800018ac  pop     rbx
0x1800018ad  retn
```
