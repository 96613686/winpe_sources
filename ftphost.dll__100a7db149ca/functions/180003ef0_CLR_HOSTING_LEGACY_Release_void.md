# CLR_HOSTING_LEGACY::Release(void)

- ea: `0x180003ef0`
- end: `0x180003f1f`
- name: `?Release@CLR_HOSTING_LEGACY@@UEAAXXZ`
- size: `47`
- prototype: `void __fastcall(CLR_HOSTING_LEGACY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003ef0`
- `0x180005010`

## pseudocode

```c
void __fastcall CLR_HOSTING_LEGACY::Release(CLR_HOSTING_LEGACY *this)
{
  char *v1; // rcx

  v1 = (char *)this - 32;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( v1 )
      (**(void (__fastcall ***)(char *, __int64))v1)(v1, 1);
  }
}

```

## disassembly

```asm
0x180003ef0  sub     rsp, 28h
0x180003ef4  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180003ef8  or      eax, 0FFFFFFFFh
0x180003efb  lock xadd [rcx+8], eax
0x180003f00  cmp     eax, 1
0x180003f03  jnz     short loc_180003F1A
0x180003f05  test    rcx, rcx
0x180003f08  jz      short loc_180003F1A
0x180003f0a  mov     rax, [rcx]
0x180003f0d  mov     edx, 1
0x180003f12  mov     rax, [rax]
0x180003f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1a  add     rsp, 28h
0x180003f1e  retn
```
