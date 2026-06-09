# SC_DISK::WriteSectors(ulong,unsigned __int64,void *)

- ea: `0x14000f264`
- end: `0x14000f2a0`
- name: `?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z`
- size: `60`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this, unsigned int, unsigned __int64, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fc84`
- `0x140010380`
- `0x140010a30`

## callees

- `0x14000f264`
- `0x140010f60`

## pseudocode

```c
__int64 __fastcall SC_DISK::WriteSectors(SC_DISK *this, int a2, __int64 a3, void *a4)
{
  if ( !a4 )
    a4 = (void *)*((_QWORD *)this + 33);
  return (*(__int64 (__fastcall **)(SC_DISK *, __int64, _QWORD, void *))(*(_QWORD *)this + 72LL))(
           this,
           a3 << *((_DWORD *)this + 60),
           (unsigned int)(a2 << *((_DWORD *)this + 60)),
           a4);
}

```

## disassembly

```asm
0x14000f264  sub     rsp, 38h
0x14000f268  mov     r11, r8
0x14000f26b  mov     r10, rcx
0x14000f26e  test    r9, r9
0x14000f271  jnz     short loc_14000F27A
0x14000f273  mov     r9, [rcx+108h]
0x14000f27a  mov     ecx, [rcx+0F0h]
0x14000f280  mov     rax, [r10]
0x14000f283  shl     edx, cl
0x14000f285  shl     r11, cl
0x14000f288  mov     r8d, edx
0x14000f28b  mov     rdx, r11
0x14000f28e  mov     rcx, r10
0x14000f291  mov     rax, [rax+48h]
0x14000f295  call    _guard_dispatch_icall
0x14000f29a  add     rsp, 38h
0x14000f29e  retn
```
