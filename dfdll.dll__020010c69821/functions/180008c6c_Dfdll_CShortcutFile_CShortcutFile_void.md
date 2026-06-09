# Dfdll::CShortcutFile::~CShortcutFile(void)

- ea: `0x180008c6c`
- end: `0x180008d31`
- name: `??1CShortcutFile@Dfdll@@UEAA@XZ`
- size: `197`
- prototype: `void __fastcall(Dfdll::CShortcutFile *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800092d0`
- `0x18000c954`
- `0x18001f31a`

## callees

- `0x180008c6c`
- `0x180012b30`

## pseudocode

```c
void __fastcall Dfdll::CShortcutFile::~CShortcutFile(Dfdll::CShortcutFile *this, const struct std::nothrow_t *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &Dfdll::CShortcutFile::`vftable';
  *((_QWORD *)this + 11) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 12) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v3 = (void *)*((_QWORD *)this + 13);
  if ( v3 )
    operator delete(v3, a2);
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 12) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 11) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 6) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 7) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
    operator delete(v4, a2);
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 7) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 6) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CString::`vftable';
  *((_QWORD *)this + 2) = &Dfdll::CBuffer<unsigned short>::`vftable';
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    operator delete(v5, a2);
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 2) = &Dfdll::CObject::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180008c6c  mov     [rsp+arg_0], rbx
0x180008c71  mov     [rsp+arg_8], rbp
0x180008c76  mov     [rsp+arg_10], rsi
0x180008c7b  push    r14
0x180008c7d  sub     rsp, 20h
0x180008c81  mov     rbx, rcx
0x180008c84  lea     rax, ??_7CShortcutFile@Dfdll@@6B@; const Dfdll::CShortcutFile::`vftable'
0x180008c8b  mov     [rcx], rax
0x180008c8e  lea     rbp, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180008c95  mov     [rcx+58h], rbp
0x180008c99  lea     r14, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180008ca0  mov     [rcx+60h], r14
0x180008ca4  mov     rcx, [rcx+68h]; void *
0x180008ca8  test    rcx, rcx
0x180008cab  jz      short loc_180008CB2
0x180008cad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008cb2  and     qword ptr [rbx+68h], 0
0x180008cb7  and     dword ptr [rbx+70h], 0
0x180008cbb  lea     rsi, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008cc2  mov     [rbx+60h], rsi
0x180008cc6  mov     [rbx+58h], rsi
0x180008cca  mov     [rbx+30h], rbp
0x180008cce  mov     [rbx+38h], r14
0x180008cd2  mov     rcx, [rbx+40h]; void *
0x180008cd6  test    rcx, rcx
0x180008cd9  jz      short loc_180008CE0
0x180008cdb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008ce0  and     qword ptr [rbx+40h], 0
0x180008ce5  and     dword ptr [rbx+48h], 0
0x180008ce9  mov     [rbx+38h], rsi
0x180008ced  mov     [rbx+30h], rsi
0x180008cf1  mov     [rbx+8], rbp
0x180008cf5  mov     [rbx+10h], r14
0x180008cf9  mov     rcx, [rbx+18h]; void *
0x180008cfd  test    rcx, rcx
0x180008d00  jz      short loc_180008D07
0x180008d02  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008d07  and     qword ptr [rbx+18h], 0
0x180008d0c  and     dword ptr [rbx+20h], 0
0x180008d10  mov     [rbx+10h], rsi
0x180008d14  mov     [rbx+8], rsi
0x180008d18  mov     [rbx], rsi
0x180008d1b  mov     rbx, [rsp+28h+arg_0]
0x180008d20  mov     rbp, [rsp+28h+arg_8]
0x180008d25  mov     rsi, [rsp+28h+arg_10]
0x180008d2a  add     rsp, 20h
0x180008d2e  pop     r14
0x180008d30  retn
```
