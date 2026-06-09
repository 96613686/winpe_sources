# Dfdll::CBSTR::`scalar deleting destructor'(uint)

- ea: `0x180001c40`
- end: `0x180001c92`
- name: `??_GCBSTR@Dfdll@@UEAAPEAXI@Z`
- size: `82`
- prototype: `void *__fastcall(Dfdll::CBSTR *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001c40`
- `0x180012b30`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001c5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180001c5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall Dfdll::CBSTR::`scalar deleting destructor'(BSTR *this, char a2)
{
  *this = (BSTR)&Dfdll::CBSTR::`vftable';
  SysFreeString(this[1]);
  this[1] = 0;
  *this = (BSTR)&Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x10);
  return this;
}

```

## disassembly

```asm
0x180001c40  mov     [rsp+arg_0], rbx
0x180001c45  push    rdi
0x180001c46  sub     rsp, 20h
0x180001c4a  mov     ebx, edx
0x180001c4c  mov     rdi, rcx
0x180001c4f  lea     rax, ??_7CBSTR@Dfdll@@6B@; const Dfdll::CBSTR::`vftable'
0x180001c56  mov     [rcx], rax
0x180001c59  mov     rcx, [rcx+8]; bstrString
0x180001c5d  call    cs:__imp_SysFreeString
0x180001c63  and     qword ptr [rdi+8], 0
0x180001c68  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001c6f  mov     [rdi], rax
0x180001c72  test    bl, 1
0x180001c75  jz      short loc_180001C84
0x180001c77  mov     edx, 10h; struct std::nothrow_t *
0x180001c7c  mov     rcx, rdi; void *
0x180001c7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001c84  mov     rax, rdi
0x180001c87  mov     rbx, [rsp+28h+arg_0]
0x180001c8c  add     rsp, 20h
0x180001c90  pop     rdi
0x180001c91  retn
```
