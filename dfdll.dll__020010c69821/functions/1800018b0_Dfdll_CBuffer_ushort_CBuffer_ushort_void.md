# Dfdll::CBuffer<ushort>::~CBuffer<ushort>(void)

- ea: `0x1800018b0`
- end: `0x1800018ea`
- name: `??1?$CBuffer@G@Dfdll@@UEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f04a`
- `0x18001f07a`
- `0x18001f0c2`
- `0x18001f1fa`
- `0x18001f206`

## callees

- `0x1800018b0`
- `0x180012b30`

## pseudocode

```c
void **__fastcall Dfdll::CBuffer<unsigned short>::~CBuffer<unsigned short>(__int64 a1, const struct std::nothrow_t *a2)
{
  void *v3; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &Dfdll::CBuffer<unsigned short>::`vftable';
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
0x1800018b0  push    rbx
0x1800018b2  sub     rsp, 20h
0x1800018b6  mov     rbx, rcx
0x1800018b9  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800018c0  mov     [rcx], rax
0x1800018c3  mov     rcx, [rcx+8]; void *
0x1800018c7  test    rcx, rcx
0x1800018ca  jz      short loc_1800018D1
0x1800018cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800018d1  and     qword ptr [rbx+8], 0
0x1800018d6  and     dword ptr [rbx+10h], 0
0x1800018da  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800018e1  mov     [rbx], rax
0x1800018e4  add     rsp, 20h
0x1800018e8  pop     rbx
0x1800018e9  retn
```
