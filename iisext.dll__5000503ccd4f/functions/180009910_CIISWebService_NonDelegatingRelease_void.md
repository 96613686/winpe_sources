# CIISWebService::NonDelegatingRelease(void)

- ea: `0x180009910`
- end: `0x180009949`
- name: `?NonDelegatingRelease@CIISWebService@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CIISWebService *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001048`
- `0x1800085f0`
- `0x180009910`

## pseudocode

```c
__int64 __fastcall CIISWebService::NonDelegatingRelease(CIISWebService *this)
{
  unsigned int *v1; // rbx

  v1 = (unsigned int *)((char *)this - 32);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) != 1 )
    return v1[10];
  if ( this != (CIISWebService *)32 )
  {
    CIISWebService::~CIISWebService((CIISWebService *)((char *)this - 32));
    operator delete(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180009910  push    rbx
0x180009912  sub     rsp, 20h
0x180009916  lea     rbx, [rcx-20h]
0x18000991a  or      eax, 0FFFFFFFFh
0x18000991d  lock xadd [rcx+8], eax
0x180009922  cmp     eax, 1
0x180009925  jnz     short loc_180009940
0x180009927  test    rbx, rbx
0x18000992a  jz      short loc_18000993C
0x18000992c  mov     rcx, rbx; this
0x18000992f  call    ??1CIISWebService@@QEAA@XZ; CIISWebService::~CIISWebService(void)
0x180009934  mov     rcx, rbx; Block
0x180009937  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000993c  xor     eax, eax
0x18000993e  jmp     short loc_180009943
0x180009940  mov     eax, [rbx+28h]
0x180009943  add     rsp, 20h
0x180009947  pop     rbx
0x180009948  retn
```
