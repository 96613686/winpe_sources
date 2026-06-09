# Dfdll::CBuffer<uint>::`vector deleting destructor'(uint)

- ea: `0x1800090a0`
- end: `0x1800090fb`
- name: `??_E?$CBuffer@I@Dfdll@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800090a0`
- `0x180012b30`

## pseudocode

```c
_QWORD *__fastcall Dfdll::CBuffer<unsigned int>::`vector deleting destructor'(
        _QWORD *a1,
        const struct std::nothrow_t *a2)
{
  char v2; // di
  void *v4; // rcx

  v2 = (char)a2;
  *a1 = &Dfdll::CBuffer<unsigned int>::`vftable';
  v4 = (void *)a1[1];
  if ( v4 )
    operator delete(v4, a2);
  a1[1] = 0;
  *((_DWORD *)a1 + 4) = 0;
  *a1 = &Dfdll::CObject::`vftable';
  if ( (v2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x18);
  return a1;
}

```

## disassembly

```asm
0x1800090a0  mov     [rsp+arg_0], rbx
0x1800090a5  push    rdi
0x1800090a6  sub     rsp, 20h
0x1800090aa  mov     edi, edx
0x1800090ac  mov     rbx, rcx
0x1800090af  lea     rax, ??_7?$CBuffer@I@Dfdll@@6B@; const Dfdll::CBuffer<uint>::`vftable'
0x1800090b6  mov     [rcx], rax
0x1800090b9  mov     rcx, [rcx+8]; void *
0x1800090bd  test    rcx, rcx
0x1800090c0  jz      short loc_1800090C7
0x1800090c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800090c7  and     qword ptr [rbx+8], 0
0x1800090cc  and     dword ptr [rbx+10h], 0
0x1800090d0  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800090d7  mov     [rbx], rax
0x1800090da  test    dil, 1
0x1800090de  jz      short loc_1800090ED
0x1800090e0  mov     edx, 18h; struct std::nothrow_t *
0x1800090e5  mov     rcx, rbx; void *
0x1800090e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800090ed  mov     rax, rbx
0x1800090f0  mov     rbx, [rsp+28h+arg_0]
0x1800090f5  add     rsp, 20h
0x1800090f9  pop     rdi
0x1800090fa  retn
```
