# CWaveArt::`scalar deleting destructor'(uint)

- ea: `0x180007d50`
- end: `0x180007df1`
- name: `??_GCWaveArt@@QEAAPEAXI@Z`
- size: `161`
- prototype: `void *__fastcall(CWaveArt *__hidden this, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003210`
- `0x180004c90`
- `0x1800076e0`
- `0x180007a00`
- `0x180009290`
- `0x180009b30`
- `0x18000b070`
- `0x18000b0f0`
- `0x18000ddf0`

## callees

- `0x180001514`
- `0x180007d50`
- `0x180015010`

## pseudocode

```c
CWaveArt *__fastcall CWaveArt::`scalar deleting destructor'(CWaveArt *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rbx
  void (__fastcall *v5)(__int64, _QWORD); // rax

  while ( 1 )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 7);
    if ( !v2 )
      break;
    *((_QWORD *)this + 7) = *v2;
    *v2 = 0;
    v3 = v2[1];
    if ( v3 )
    {
      if ( (*(_WORD *)(v3 + 44))-- == 1 )
      {
        if ( *(_QWORD *)(v3 + 32) )
        {
          v5 = *(void (__fastcall **)(__int64, _QWORD))(v3 + 16);
          if ( v5 )
            v5(v3, *(_QWORD *)(v3 + 24));
        }
        operator delete((void *)v3);
      }
      v2[1] = 0;
    }
    operator delete(v2);
  }
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007d50  mov     [rsp+arg_10], rbp
0x180007d55  push    rsi
0x180007d56  push    rdi
0x180007d57  push    r14
0x180007d59  sub     rsp, 20h
0x180007d5d  mov     rsi, rcx
0x180007d60  mov     [rsp+38h+arg_0], rbx
0x180007d65  xor     ebp, ebp
0x180007d67  mov     r14d, 0FFFFh
0x180007d6d  nop     dword ptr [rax]
0x180007d70  mov     rdi, [rsi+38h]
0x180007d74  test    rdi, rdi
0x180007d77  jz      short loc_180007DCE
0x180007d79  mov     rax, [rdi]
0x180007d7c  mov     [rsi+38h], rax
0x180007d80  mov     [rdi], rbp
0x180007d83  mov     rbx, [rdi+8]
0x180007d87  test    rbx, rbx
0x180007d8a  jz      short loc_180007DBF
0x180007d8c  add     [rbx+2Ch], r14w
0x180007d91  jnz     short loc_180007DBB
0x180007d93  cmp     [rbx+20h], rbp
0x180007d97  jz      short loc_180007DAE
0x180007d99  mov     rax, [rbx+10h]
0x180007d9d  test    rax, rax
0x180007da0  jz      short loc_180007DAE
0x180007da2  mov     rdx, [rbx+18h]
0x180007da6  mov     rcx, rbx
0x180007da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dae  mov     edx, 38h ; '8'; unsigned __int64
0x180007db3  mov     rcx, rbx; void *
0x180007db6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007dbb  mov     [rdi+8], rbp
0x180007dbf  mov     edx, 18h; unsigned __int64
0x180007dc4  mov     rcx, rdi; void *
0x180007dc7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007dcc  jmp     short loc_180007D70
0x180007dce  mov     edx, 50h ; 'P'; unsigned __int64
0x180007dd3  mov     rcx, rsi; void *
0x180007dd6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007ddb  mov     rbx, [rsp+38h+arg_0]
0x180007de0  mov     rax, rsi
0x180007de3  mov     rbp, [rsp+38h+arg_10]
0x180007de8  add     rsp, 20h
0x180007dec  pop     r14
0x180007dee  pop     rdi
0x180007def  pop     rsi
0x180007df0  retn
```
