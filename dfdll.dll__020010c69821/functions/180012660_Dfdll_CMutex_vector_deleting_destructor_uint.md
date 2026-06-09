# Dfdll::CMutex::`vector deleting destructor'(uint)

- ea: `0x180012660`
- end: `0x180012694`
- name: `??_ECMutex@Dfdll@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Dfdll::CMutex *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x1800125ec`
- `0x180012660`
- `0x180012b30`

## pseudocode

```c
Dfdll::CMutex *__fastcall Dfdll::CMutex::`vector deleting destructor'(Dfdll::CMutex *this, char a2)
{
  Dfdll::CMutex::~CMutex(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x180012660  mov     [rsp+arg_0], rbx
0x180012665  push    rdi
0x180012666  sub     rsp, 20h
0x18001266a  mov     ebx, edx
0x18001266c  mov     rdi, rcx
0x18001266f  call    ??1CMutex@Dfdll@@UEAA@XZ; Dfdll::CMutex::~CMutex(void)
0x180012674  test    bl, 1
0x180012677  jz      short loc_180012686
0x180012679  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18001267e  mov     rcx, rdi; void *
0x180012681  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012686  mov     rbx, [rsp+28h+arg_0]
0x18001268b  mov     rax, rdi
0x18001268e  add     rsp, 20h
0x180012692  pop     rdi
0x180012693  retn
```
