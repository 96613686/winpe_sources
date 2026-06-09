# Dfdll::CString::~CString(void)

- ea: `0x180001a64`
- end: `0x180001aad`
- name: `??1CString@Dfdll@@UEAA@XZ`
- size: `73`
- prototype: `void __fastcall(Dfdll::CString *__hidden this)`
- caller_count: `23`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180005400`
- `0x180006180`
- `0x180007a7c`
- `0x18000dadc`
- `0x18001f0b6`
- `0x18001f0e6`
- `0x18001f0f2`
- `0x18001f122`
- `0x18001f12e`
- `0x18001f13a`
- `0x18001f146`
- `0x18001f15e`
- `0x18001f16a`
- `0x18001f18e`
- `0x18001f1a6`
- `0x18001f1b2`
- `0x18001f22a`
- `0x18001f236`
- `0x18001f24e`
- `0x18001f33e`
- `0x18001f3aa`
- `0x18001f3ce`
- `0x18001f40a`

## callees

- `0x180001a64`
- `0x180012b30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dfdll::CString::~CString(Dfdll::CString *this, const struct std::nothrow_t *a2)
{
  void *v3; // rcx

  *(_QWORD *)this = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    operator delete(v3, a2);
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180001a64  push    rbx
0x180001a66  sub     rsp, 20h
0x180001a6a  mov     rbx, rcx
0x180001a6d  lea     rax, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180001a74  mov     [rcx], rax
0x180001a77  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180001a7e  mov     [rcx+8], rax
0x180001a82  mov     rcx, [rcx+10h]; void *
0x180001a86  test    rcx, rcx
0x180001a89  jz      short loc_180001A90
0x180001a8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001a90  and     qword ptr [rbx+10h], 0
0x180001a95  and     dword ptr [rbx+18h], 0
0x180001a99  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001aa0  mov     [rbx+8], rax
0x180001aa4  mov     [rbx], rax
0x180001aa7  add     rsp, 20h
0x180001aab  pop     rbx
0x180001aac  retn
```
