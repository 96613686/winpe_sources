# APPLICATION::DereferenceApplication(void)

- ea: `0x180005030`
- end: `0x180005061`
- name: `?DereferenceApplication@APPLICATION@@QEAAXXZ`
- size: `49`
- prototype: `void __fastcall(APPLICATION *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005010`
- `0x180005294`
- `0x180005f4c`
- `0x180007180`
- `0x18000794c`
- `0x180008164`
- `0x1800086bc`
- `0x18000bac0`
- `0x18000bea0`

## callees

- `0x180001048`
- `0x1800047ec`
- `0x180005030`

## pseudocode

```c
void __fastcall APPLICATION::DereferenceApplication(APPLICATION *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 39, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      APPLICATION::~APPLICATION(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180005030  push    rbx
0x180005032  sub     rsp, 20h
0x180005036  mov     rbx, rcx
0x180005039  or      eax, 0FFFFFFFFh
0x18000503c  lock xadd [rcx+9Ch], eax
0x180005044  cmp     eax, 1
0x180005047  jnz     short loc_18000505B
0x180005049  test    rcx, rcx
0x18000504c  jz      short loc_18000505B
0x18000504e  call    ??1APPLICATION@@AEAA@XZ; APPLICATION::~APPLICATION(void)
0x180005053  mov     rcx, rbx; Block
0x180005056  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000505b  add     rsp, 20h
0x18000505f  pop     rbx
0x180005060  retn
```
