# DiskContext::GetHardwareId(void)

- ea: `0x180003edc`
- end: `0x180003f23`
- name: `?GetHardwareId@DiskContext@@QEAAPEAGXZ`
- size: `71`
- prototype: `unsigned __int16 *__fastcall(DiskContext *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ed8`
- `0x1800037bc`
- `0x180006c74`
- `0x180007970`

## callees

- `0x180003edc`
- `0x18000462c`

## pseudocode

```c
unsigned __int16 *__fastcall DiskContext::GetHardwareId(DiskContext *this)
{
  char *v1; // rbx

  v1 = (char *)this + 560;
  if ( *((_BYTE *)this + 556) == 48 )
  {
    DiskContext::SetDiskProperty(this, (unsigned __int16 **)this + 70, (unsigned int *)this + 142, 1u);
    *((_BYTE *)this + 556) = 49;
  }
  return *(unsigned __int16 **)v1;
}

```

## disassembly

```asm
0x180003edc  mov     [rsp+arg_0], rbx
0x180003ee1  push    rdi
0x180003ee2  sub     rsp, 20h
0x180003ee6  cmp     byte ptr [rcx+22Ch], 30h ; '0'
0x180003eed  lea     rbx, [rcx+230h]
0x180003ef4  mov     rdi, rcx
0x180003ef7  jnz     short loc_180003F15
0x180003ef9  lea     r8, [rcx+238h]; unsigned int *
0x180003f00  mov     r9d, 1; unsigned int
0x180003f06  mov     rdx, rbx; unsigned __int16 **
0x180003f09  call    ?SetDiskProperty@DiskContext@@AEAAKPEAPEAGPEAKK@Z; DiskContext::SetDiskProperty(ushort * *,ulong *,ulong)
0x180003f0e  mov     byte ptr [rdi+22Ch], 31h ; '1'
0x180003f15  mov     rax, [rbx]
0x180003f18  mov     rbx, [rsp+28h+arg_0]
0x180003f1d  add     rsp, 20h
0x180003f21  pop     rdi
0x180003f22  retn
```
