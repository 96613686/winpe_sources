# SSI_VECTOR_BUFFER::AddFileChunkToVector(ulong,ulong,void *)

- ea: `0x1800054e4`
- end: `0x180005540`
- name: `?AddFileChunkToVector@SSI_VECTOR_BUFFER@@QEAAJKKPEAX@Z`
- size: `92`
- prototype: `__int64 __fastcall(SSI_VECTOR_BUFFER *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042fc`
- `0x180004afc`

## callees

- `0x1800054e4`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SSI_VECTOR_BUFFER::AddFileChunkToVector(
        SSI_VECTOR_BUFFER *this,
        unsigned int a2,
        unsigned int a3,
        void *a4)
{
  __int64 v5; // rcx
  _DWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+30h] [rbp-18h]
  void *v9; // [rsp+38h] [rbp-10h]

  v6[1] = 0;
  if ( !a3 )
    return 0;
  *((_DWORD *)this + 70) += a3;
  v5 = *((_QWORD *)this + 37);
  v7 = a2;
  v8 = a3;
  v6[0] = 1;
  v9 = a4;
  return (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v5 + 160LL))(v5, v6, 0xFFFFFFFFLL);
}

```

## disassembly

```asm
0x1800054e4  sub     rsp, 48h
0x1800054e8  mov     [rsp+48h+var_24], 0
0x1800054f0  test    r8d, r8d
0x1800054f3  jnz     short loc_1800054F9
0x1800054f5  xor     eax, eax
0x1800054f7  jmp     short loc_18000553B
0x1800054f9  add     [rcx+118h], r8d
0x180005500  mov     rcx, [rcx+128h]
0x180005507  mov     eax, edx
0x180005509  lea     rdx, [rsp+48h+var_28]
0x18000550e  mov     [rsp+48h+var_20], rax
0x180005513  mov     eax, r8d
0x180005516  or      r8d, 0FFFFFFFFh
0x18000551a  mov     [rsp+48h+var_18], rax
0x18000551f  mov     [rsp+48h+var_28], 1
0x180005527  mov     [rsp+48h+var_10], r9
0x18000552c  mov     rax, [rcx]
0x18000552f  mov     rax, [rax+0A0h]
0x180005536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000553b  add     rsp, 48h
0x18000553f  retn
```
