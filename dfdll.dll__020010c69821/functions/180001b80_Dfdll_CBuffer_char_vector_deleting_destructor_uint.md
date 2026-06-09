# Dfdll::CBuffer<char>::`vector deleting destructor'(uint)

- ea: `0x180001b80`
- end: `0x180001bdb`
- name: `??_E?$CBuffer@D@Dfdll@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001b80`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Dfdll::CBuffer<char>::`vector deleting destructor'(_QWORD *a1, const struct std::nothrow_t *a2)
{
  char v2; // di
  void *v4; // rcx

  v2 = (char)a2;
  *a1 = &Dfdll::CBuffer<unsigned char>::`vftable';
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
0x180001b80  mov     [rsp+arg_0], rbx
0x180001b85  push    rdi
0x180001b86  sub     rsp, 20h
0x180001b8a  mov     edi, edx
0x180001b8c  mov     rbx, rcx
0x180001b8f  lea     rax, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x180001b96  mov     [rcx], rax
0x180001b99  mov     rcx, [rcx+8]; void *
0x180001b9d  test    rcx, rcx
0x180001ba0  jz      short loc_180001BA7
0x180001ba2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001ba7  and     qword ptr [rbx+8], 0
0x180001bac  and     dword ptr [rbx+10h], 0
0x180001bb0  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001bb7  mov     [rbx], rax
0x180001bba  test    dil, 1
0x180001bbe  jz      short loc_180001BCD
0x180001bc0  mov     edx, 18h; struct std::nothrow_t *
0x180001bc5  mov     rcx, rbx; void *
0x180001bc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001bcd  mov     rax, rbx
0x180001bd0  mov     rbx, [rsp+28h+arg_0]
0x180001bd5  add     rsp, 20h
0x180001bd9  pop     rdi
0x180001bda  retn
```
