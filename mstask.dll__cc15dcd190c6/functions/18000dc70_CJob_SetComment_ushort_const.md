# CJob::SetComment(ushort const *)

- ea: `0x18000dc70`
- end: `0x18000dd3a`
- name: `?SetComment@CJob@@UEAAJPEBG@Z`
- size: `202`
- prototype: `int(CJob *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001840`
- `0x180009ef8`
- `0x180009f38`
- `0x18000dc70`

## pseudocode

```c
__int64 __fastcall CJob::SetComment(CJob *this, unsigned __int16 *a2)
{
  void *v4; // rcx
  unsigned __int16 *v5; // r14
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  void *v10; // rcx

  if ( *a2 )
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = (unsigned __int16 *)operator new(saturated_mul(v7 + 1, 2u));
    v5 = v8;
    if ( !v8 )
      return 2147942414LL;
    *v8 = 0;
    do
      ++v6;
    while ( a2[v6] );
    StringCchCopyW(v8, v6 + 1, a2);
    v10 = (void *)*((_QWORD *)this + 18);
    if ( *((_QWORD *)this + 28) > (unsigned __int64)v10 || (unsigned __int64)v10 >= *((_QWORD *)this + 29) )
      operator delete(v10);
    *((_QWORD *)this + 18) = 0;
  }
  else
  {
    v4 = (void *)*((_QWORD *)this + 18);
    if ( *((_QWORD *)this + 28) > (unsigned __int64)v4 || (unsigned __int64)v4 >= *((_QWORD *)this + 29) )
      operator delete(v4);
    v5 = 0;
  }
  *((_QWORD *)this + 18) = v5;
  *((_DWORD *)this + 22) |= 0x40000000u;
  return 0;
}

```

## disassembly

```asm
0x18000dc70  push    rbx
0x18000dc72  push    rbp
0x18000dc73  push    rsi
0x18000dc74  push    rdi
0x18000dc75  push    r14
0x18000dc77  sub     rsp, 20h
0x18000dc7b  xor     ebp, ebp
0x18000dc7d  mov     rsi, rdx
0x18000dc80  mov     rbx, rcx
0x18000dc83  cmp     [rdx], bp
0x18000dc86  jnz     short loc_18000DCAB
0x18000dc88  mov     rcx, [rcx+90h]; Block
0x18000dc8f  cmp     [rbx+0E0h], rcx
0x18000dc96  ja      short loc_18000DCA1
0x18000dc98  cmp     rcx, [rbx+0E8h]
0x18000dc9f  jb      short loc_18000DCA6
0x18000dca1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dca6  mov     r14, rbp
0x18000dca9  jmp     short loc_18000DD21
0x18000dcab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dcaf  mov     rcx, rdi
0x18000dcb2  inc     rcx
0x18000dcb5  cmp     [rdx+rcx*2], bp
0x18000dcb9  jnz     short loc_18000DCB2
0x18000dcbb  inc     rcx
0x18000dcbe  mov     eax, 2
0x18000dcc3  mul     rcx
0x18000dcc6  cmovb   rax, rdi
0x18000dcca  mov     rcx, rax; Size
0x18000dccd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dcd2  mov     r14, rax
0x18000dcd5  test    rax, rax
0x18000dcd8  jnz     short loc_18000DCE1
0x18000dcda  mov     eax, 8007000Eh
0x18000dcdf  jmp     short loc_18000DD2F
0x18000dce1  mov     [rax], bp
0x18000dce4  inc     rdi
0x18000dce7  cmp     [rsi+rdi*2], bp
0x18000dceb  jnz     short loc_18000DCE4
0x18000dced  lea     rdx, [rdi+1]; unsigned __int64
0x18000dcf1  mov     r8, rsi; unsigned __int16 *
0x18000dcf4  mov     rcx, rax; unsigned __int16 *
0x18000dcf7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dcfc  mov     rcx, [rbx+90h]; Block
0x18000dd03  cmp     [rbx+0E0h], rcx
0x18000dd0a  ja      short loc_18000DD15
0x18000dd0c  cmp     rcx, [rbx+0E8h]
0x18000dd13  jb      short loc_18000DD1A
0x18000dd15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dd1a  mov     [rbx+90h], rbp
0x18000dd21  mov     [rbx+90h], r14
0x18000dd28  bts     dword ptr [rbx+58h], 1Eh
0x18000dd2d  xor     eax, eax
0x18000dd2f  add     rsp, 20h
0x18000dd33  pop     r14
0x18000dd35  pop     rdi
0x18000dd36  pop     rsi
0x18000dd37  pop     rbp
0x18000dd38  pop     rbx
0x18000dd39  retn
```
