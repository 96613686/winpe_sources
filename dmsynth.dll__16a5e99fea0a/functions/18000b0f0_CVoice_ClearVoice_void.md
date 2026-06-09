# CVoice::ClearVoice(void)

- ea: `0x18000b0f0`
- end: `0x18000b1c3`
- name: `?ClearVoice@CVoice@@QEAAXXZ`
- size: `211`
- prototype: `void __fastcall(CVoice *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006030`
- `0x1800075f0`
- `0x18000c710`

## callees

- `0x180001514`
- `0x180007d50`
- `0x18000b0f0`
- `0x180015010`

## pseudocode

```c
void __fastcall CVoice::ClearVoice(CVoice *this)
{
  __int64 v2; // rbx
  bool v3; // zf
  void (__fastcall *v4)(__int64, _QWORD); // rax
  __int64 v5; // rbx
  void (__fastcall *v6)(__int64, _QWORD); // rax
  CWaveArt *v7; // rcx

  *((_DWORD *)this + 136) = 0;
  v2 = *((_QWORD *)this + 31);
  if ( v2 )
  {
    --*(_WORD *)(v2 + 46);
    v3 = (*(_WORD *)(v2 + 44))-- == 1;
    if ( v3 )
    {
      if ( *(_QWORD *)(v2 + 32) )
      {
        v4 = *(void (__fastcall **)(__int64, _QWORD))(v2 + 16);
        if ( v4 )
          v4(v2, *(_QWORD *)(v2 + 24));
      }
      operator delete((void *)v2);
    }
    v5 = *((_QWORD *)this + 31);
    v3 = (*(_WORD *)(v5 + 44))-- == 1;
    if ( v3 )
    {
      if ( *(_QWORD *)(v5 + 32) )
      {
        v6 = *(void (__fastcall **)(__int64, _QWORD))(v5 + 16);
        if ( v6 )
          v6(v5, *(_QWORD *)(v5 + 24));
      }
      operator delete((void *)v5);
    }
    *((_QWORD *)this + 31) = 0;
  }
  v7 = (CWaveArt *)*((_QWORD *)this + 51);
  if ( v7 )
  {
    v3 = (*((_WORD *)v7 + 36))-- == 1;
    if ( v3 )
      CWaveArt::`scalar deleting destructor'(v7);
    *((_QWORD *)this + 51) = 0;
  }
}

```

## disassembly

```asm
0x18000b0f0  mov     [rsp+arg_8], rbx
0x18000b0f5  mov     [rsp+arg_10], rbp
0x18000b0fa  push    rdi
0x18000b0fb  sub     rsp, 20h
0x18000b0ff  mov     dword ptr [rcx+220h], 0
0x18000b109  mov     rdi, rcx
0x18000b10c  mov     rbx, [rcx+0F8h]
0x18000b113  mov     ebp, 0FFFFh
0x18000b118  test    rbx, rbx
0x18000b11b  jz      short loc_18000B191
0x18000b11d  add     [rbx+2Eh], bp
0x18000b121  add     [rbx+2Ch], bp
0x18000b125  jnz     short loc_18000B150
0x18000b127  cmp     qword ptr [rbx+20h], 0
0x18000b12c  jz      short loc_18000B143
0x18000b12e  mov     rax, [rbx+10h]
0x18000b132  test    rax, rax
0x18000b135  jz      short loc_18000B143
0x18000b137  mov     rdx, [rbx+18h]
0x18000b13b  mov     rcx, rbx
0x18000b13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b143  mov     edx, 38h ; '8'; unsigned __int64
0x18000b148  mov     rcx, rbx; void *
0x18000b14b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b150  mov     rbx, [rdi+0F8h]
0x18000b157  add     [rbx+2Ch], bp
0x18000b15b  jnz     short loc_18000B186
0x18000b15d  cmp     qword ptr [rbx+20h], 0
0x18000b162  jz      short loc_18000B179
0x18000b164  mov     rax, [rbx+10h]
0x18000b168  test    rax, rax
0x18000b16b  jz      short loc_18000B179
0x18000b16d  mov     rdx, [rbx+18h]
0x18000b171  mov     rcx, rbx
0x18000b174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b179  mov     edx, 38h ; '8'; unsigned __int64
0x18000b17e  mov     rcx, rbx; void *
0x18000b181  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b186  mov     qword ptr [rdi+0F8h], 0
0x18000b191  mov     rcx, [rdi+198h]; this
0x18000b198  test    rcx, rcx
0x18000b19b  jz      short loc_18000B1B3
0x18000b19d  add     [rcx+48h], bp
0x18000b1a1  jnz     short loc_18000B1A8
0x18000b1a3  call    ??_GCWaveArt@@QEAAPEAXI@Z; CWaveArt::`scalar deleting destructor'(uint)
0x18000b1a8  mov     qword ptr [rdi+198h], 0
0x18000b1b3  mov     rbx, [rsp+28h+arg_8]
0x18000b1b8  mov     rbp, [rsp+28h+arg_10]
0x18000b1bd  add     rsp, 20h
0x18000b1c1  pop     rdi
0x18000b1c2  retn
```
