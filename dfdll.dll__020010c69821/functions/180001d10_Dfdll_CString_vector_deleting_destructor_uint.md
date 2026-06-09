# Dfdll::CString::`vector deleting destructor'(uint)

- ea: `0x180001d10`
- end: `0x180001d7a`
- name: `??_ECString@Dfdll@@UEAAPEAXI@Z`
- size: `106`
- prototype: `void *__fastcall(Dfdll::CString *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001d10`
- `0x180012b30`

## pseudocode

```c
Dfdll::CString *__fastcall Dfdll::CString::`vector deleting destructor'(
        Dfdll::CString *this,
        const struct std::nothrow_t *a2)
{
  char v2; // di
  void *v4; // rcx

  v2 = (char)a2;
  *(_QWORD *)this = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
    operator delete(v4, a2);
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
  if ( (v2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x28);
  return this;
}

```

## disassembly

```asm
0x180001d10  mov     [rsp+arg_0], rbx
0x180001d15  push    rdi
0x180001d16  sub     rsp, 20h
0x180001d1a  mov     edi, edx
0x180001d1c  mov     rbx, rcx
0x180001d1f  lea     rax, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180001d26  mov     [rcx], rax
0x180001d29  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180001d30  mov     [rcx+8], rax
0x180001d34  mov     rcx, [rcx+10h]; void *
0x180001d38  test    rcx, rcx
0x180001d3b  jz      short loc_180001D42
0x180001d3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001d42  and     qword ptr [rbx+10h], 0
0x180001d47  and     dword ptr [rbx+18h], 0
0x180001d4b  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001d52  mov     [rbx+8], rax
0x180001d56  mov     [rbx], rax
0x180001d59  test    dil, 1
0x180001d5d  jz      short loc_180001D6C
0x180001d5f  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180001d64  mov     rcx, rbx; void *
0x180001d67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001d6c  mov     rax, rbx
0x180001d6f  mov     rbx, [rsp+28h+arg_0]
0x180001d74  add     rsp, 20h
0x180001d78  pop     rdi
0x180001d79  retn
```
