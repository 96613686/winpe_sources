# CIISComputer::NonDelegatingRelease(void)

- ea: `0x180006eb0`
- end: `0x180006ee9`
- name: `?NonDelegatingRelease@CIISComputer@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CIISComputer *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x1800064a0`
- `0x180006eb0`

## pseudocode

```c
__int64 __fastcall CIISComputer::NonDelegatingRelease(CIISComputer *this)
{
  unsigned int *v1; // rbx

  v1 = (unsigned int *)((char *)this - 32);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) != 1 )
    return v1[10];
  if ( this != (CIISComputer *)32 )
  {
    CIISComputer::~CIISComputer((CIISComputer *)((char *)this - 32));
    operator delete(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180006eb0  push    rbx
0x180006eb2  sub     rsp, 20h
0x180006eb6  lea     rbx, [rcx-20h]
0x180006eba  or      eax, 0FFFFFFFFh
0x180006ebd  lock xadd [rcx+8], eax
0x180006ec2  cmp     eax, 1
0x180006ec5  jnz     short loc_180006EE0
0x180006ec7  test    rbx, rbx
0x180006eca  jz      short loc_180006EDC
0x180006ecc  mov     rcx, rbx; this
0x180006ecf  call    ??1CIISComputer@@QEAA@XZ; CIISComputer::~CIISComputer(void)
0x180006ed4  mov     rcx, rbx; Block
0x180006ed7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006edc  xor     eax, eax
0x180006ede  jmp     short loc_180006EE3
0x180006ee0  mov     eax, [rbx+28h]
0x180006ee3  add     rsp, 20h
0x180006ee7  pop     rbx
0x180006ee8  retn
```
