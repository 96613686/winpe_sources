# Dfdll::CLock::`vector deleting destructor'(uint)

- ea: `0x180009270`
- end: `0x1800092d0`
- name: `??_ECLock@Dfdll@@UEAAPEAXI@Z`
- size: `96`
- prototype: `void *__fastcall(Dfdll::CLock *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180009270`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Dfdll::CLock *__fastcall Dfdll::CLock::`vector deleting destructor'(Dfdll::CLock *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &Dfdll::CLock::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
  }
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x18);
  return this;
}

```

## disassembly

```asm
0x180009270  mov     [rsp+arg_0], rbx
0x180009275  push    rdi
0x180009276  sub     rsp, 20h
0x18000927a  mov     edi, edx
0x18000927c  mov     rbx, rcx
0x18000927f  lea     rax, ??_7CLock@Dfdll@@6B@; const Dfdll::CLock::`vftable'
0x180009286  mov     [rcx], rax
0x180009289  cmp     byte ptr [rcx+10h], 0
0x18000928d  jz      short loc_1800092A5
0x18000928f  mov     rcx, [rcx+8]
0x180009293  test    rcx, rcx
0x180009296  jz      short loc_1800092A5
0x180009298  mov     rax, [rcx]
0x18000929b  mov     rax, [rax+30h]
0x18000929f  call    cs:__guard_dispatch_icall_fptr
0x1800092a5  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800092ac  mov     [rbx], rax
0x1800092af  test    dil, 1
0x1800092b3  jz      short loc_1800092C2
0x1800092b5  mov     edx, 18h; struct std::nothrow_t *
0x1800092ba  mov     rcx, rbx; void *
0x1800092bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800092c2  mov     rax, rbx
0x1800092c5  mov     rbx, [rsp+28h+arg_0]
0x1800092ca  add     rsp, 20h
0x1800092ce  pop     rdi
0x1800092cf  retn
```
