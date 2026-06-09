# Dfdll::CBuffer<ushort>::`vector deleting destructor'(uint)

- ea: `0x180001be0`
- end: `0x180001c3b`
- name: `??_E?$CBuffer@G@Dfdll@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001be0`
- `0x180012b30`

## pseudocode

```c
_QWORD *__fastcall Dfdll::CBuffer<unsigned short>::`vector deleting destructor'(
        _QWORD *a1,
        const struct std::nothrow_t *a2)
{
  char v2; // di
  void *v4; // rcx

  v2 = (char)a2;
  *a1 = &Dfdll::CBuffer<unsigned short>::`vftable';
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
0x180001be0  mov     [rsp+arg_0], rbx
0x180001be5  push    rdi
0x180001be6  sub     rsp, 20h
0x180001bea  mov     edi, edx
0x180001bec  mov     rbx, rcx
0x180001bef  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180001bf6  mov     [rcx], rax
0x180001bf9  mov     rcx, [rcx+8]; void *
0x180001bfd  test    rcx, rcx
0x180001c00  jz      short loc_180001C07
0x180001c02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001c07  and     qword ptr [rbx+8], 0
0x180001c0c  and     dword ptr [rbx+10h], 0
0x180001c10  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001c17  mov     [rbx], rax
0x180001c1a  test    dil, 1
0x180001c1e  jz      short loc_180001C2D
0x180001c20  mov     edx, 18h; struct std::nothrow_t *
0x180001c25  mov     rcx, rbx; void *
0x180001c28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001c2d  mov     rax, rbx
0x180001c30  mov     rbx, [rsp+28h+arg_0]
0x180001c35  add     rsp, 20h
0x180001c39  pop     rdi
0x180001c3a  retn
```
