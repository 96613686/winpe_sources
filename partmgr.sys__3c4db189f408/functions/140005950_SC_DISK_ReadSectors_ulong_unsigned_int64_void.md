# SC_DISK::ReadSectors(ulong,unsigned __int64,void *)

- ea: `0x140005950`
- end: `0x14000598c`
- name: `?ReadSectors@SC_DISK@@QEAAJK_KPEAX@Z`
- size: `60`
- prototype: `__int64 __fastcall(SC_DISK *this, int, __int64, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006384`
- `0x14000fc84`
- `0x14000ff58`
- `0x14000ffcc`
- `0x140026640`

## callees

- `0x140005950`
- `0x140010f60`

## pseudocode

```c
__int64 __fastcall SC_DISK::ReadSectors(SC_DISK *this, int a2, __int64 a3, void *a4)
{
  if ( !a4 )
    a4 = (void *)*((_QWORD *)this + 33);
  return (*(__int64 (__fastcall **)(SC_DISK *, __int64, _QWORD, void *))(*(_QWORD *)this + 64LL))(
           this,
           a3 << *((_DWORD *)this + 60),
           (unsigned int)(a2 << *((_DWORD *)this + 60)),
           a4);
}

```

## disassembly

```asm
0x140005950  sub     rsp, 38h
0x140005954  mov     r11, r8
0x140005957  mov     r10, rcx
0x14000595a  test    r9, r9
0x14000595d  jnz     short loc_140005966
0x14000595f  mov     r9, [rcx+108h]
0x140005966  mov     ecx, [rcx+0F0h]
0x14000596c  mov     rax, [r10]
0x14000596f  shl     edx, cl
0x140005971  shl     r11, cl
0x140005974  mov     r8d, edx
0x140005977  mov     rdx, r11
0x14000597a  mov     rcx, r10
0x14000597d  mov     rax, [rax+40h]
0x140005981  call    _guard_dispatch_icall
0x140005986  add     rsp, 38h
0x14000598a  retn
```
