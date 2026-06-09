# SC_DISK::InitializePartitionCache(void)

- ea: `0x1400050c0`
- end: `0x140005104`
- name: `?InitializePartitionCache@SC_DISK@@QEAAJXZ`
- size: `68`
- prototype: `__int64 __fastcall(SC_DISK *this, unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000df60`
- `0x140023da8`
- `0x140026640`

## callees

- `0x1400050c0`
- `0x14000510c`
- `0x14000a530`

## pseudocode

```c
__int64 __fastcall SC_DISK::InitializePartitionCache(SC_DISK *this, unsigned int a2, unsigned __int8 a3)
{
  void *v4; // rax

  v4 = SC_ENV::Allocate(1 << *((_DWORD *)this + 60), a2, a3, 1u);
  *((_QWORD *)this + 33) = v4;
  if ( v4 )
    return SC_DISK::ResetPartitionCache(this);
  else
    return 3221225626LL;
}

```

## disassembly

```asm
0x1400050c0  push    rbx
0x1400050c2  sub     rsp, 20h
0x1400050c6  mov     rbx, rcx
0x1400050c9  mov     r9d, 1; unsigned int
0x1400050cf  mov     ecx, [rcx+0F0h]
0x1400050d5  mov     eax, r9d
0x1400050d8  shl     eax, cl
0x1400050da  movsxd  rcx, eax; unsigned __int64
0x1400050dd  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400050e2  mov     [rbx+108h], rax
0x1400050e9  test    rax, rax
0x1400050ec  jnz     short loc_1400050F5
0x1400050ee  mov     eax, 0C000009Ah
0x1400050f3  jmp     short loc_1400050FD
0x1400050f5  mov     rcx, rbx; this
0x1400050f8  call    ?ResetPartitionCache@SC_DISK@@QEAAJXZ; SC_DISK::ResetPartitionCache(void)
0x1400050fd  add     rsp, 20h
0x140005101  pop     rbx
0x140005102  retn
```
