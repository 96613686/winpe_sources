# CompressRdp8<4>::Reset(void)

- ea: `0x1800271c0`
- end: `0x180027210`
- name: `?Reset@?$CompressRdp8@$03@@UEAAXXZ`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024100`
- `0x180026ec0`
- `0x180027280`

## callees

- `0x180004154`
- `0x180026e10`
- `0x1800271c0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CompressRdp8<4>::Reset(_QWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  memset_0(a1 + 20, 0, 0x80000u);
  result = RingBuffer::Initialize((RingBuffer *)(a1 + 8), 0);
  v3 = a1[7];
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 24LL))(v3, a1 + 8);
  return result;
}

```

## disassembly

```asm
0x1800271c0  mov     [rsp+arg_0], rbx
0x1800271c5  push    rdi
0x1800271c6  sub     rsp, 20h
0x1800271ca  mov     rbx, rcx
0x1800271cd  xor     edx, edx; Val
0x1800271cf  add     rcx, 0A0h; void *
0x1800271d6  mov     r8d, 80000h; Size
0x1800271dc  call    memset_0
0x1800271e1  xor     edx, edx; unsigned int
0x1800271e3  lea     rcx, [rbx+40h]; this
0x1800271e7  call    ?Initialize@RingBuffer@@QEAAJI@Z; RingBuffer::Initialize(uint)
0x1800271ec  mov     rcx, [rbx+38h]
0x1800271f0  test    rcx, rcx
0x1800271f3  jz      short loc_180027205
0x1800271f5  mov     rax, [rcx]
0x1800271f8  lea     rdx, [rbx+40h]
0x1800271fc  mov     rax, [rax+18h]
0x180027200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027205  mov     rbx, [rsp+28h+arg_0]
0x18002720a  add     rsp, 20h
0x18002720e  pop     rdi
0x18002720f  retn
```
