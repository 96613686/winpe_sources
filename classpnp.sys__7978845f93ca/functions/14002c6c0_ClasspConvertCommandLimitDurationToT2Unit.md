# ClasspConvertCommandLimitDurationToT2Unit

- ea: `0x14002c6c0`
- end: `0x14002c853`
- name: `ClasspConvertCommandLimitDurationToT2Unit`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002cb0c`

## callees

- `0x14002c674`
- `0x14002c6c0`

## pseudocode

```c
__int64 __fastcall ClasspConvertCommandLimitDurationToT2Unit(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _BYTE *a4,
        _WORD *a5,
        _WORD *a6,
        _WORD *a7)
{
  _WORD *v9; // rax
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r9
  _WORD *v14; // rax
  unsigned __int8 v15; // r8
  char v16; // si
  char v17; // r8
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // r11
  unsigned __int64 v20; // rbp
  _WORD *v21; // rax
  __int16 v22; // [rsp+60h] [rbp+8h]
  char v23; // [rsp+62h] [rbp+Ah]

  if ( !a1 && !a2 && !a3 )
  {
    v9 = a5;
    *a4 = 0;
    *v9 = 0;
    *a6 = 0;
LABEL_5:
    *a7 = a1;
    return 0;
  }
  v11 = a1 / 0x186A0;
  v12 = a1 % 0x186A0;
  if ( a1 / 0x186A0 <= 0xFFFF )
  {
    v13 = a2 / 0x186A0;
    a1 = 100000 * (a2 / 0x186A0);
    if ( a2 / 0x186A0 <= 0xFFFF )
    {
      a1 = a3 / 0x186A0;
      if ( a3 / 0x186A0 <= 0xFFFF && !v12 && !(a2 % 0x186A0) && !(a3 % 0x186A0) )
      {
        v14 = a5;
        *a4 = 10;
        *v14 = v11;
LABEL_13:
        *a6 = v13;
        goto LABEL_5;
      }
    }
  }
  v22 = 2568;
  v15 = 0;
  v23 = 14;
  while ( v15 < 3u )
  {
    v16 = *((_BYTE *)&v22 + v15);
    LOBYTE(a1) = v16;
    a1 = ClasspConvertCommandLimitDurationTo100ns(a1, 1);
    v20 = v19 / a1;
    if ( v19 / a1 <= 0xFFFF )
    {
      v13 = v18 / a1;
      if ( v18 / a1 <= 0xFFFF )
      {
        a1 = a3 / a1;
        if ( a1 <= 0xFFFF )
        {
          v21 = a5;
          *a4 = v16;
          *v21 = v20;
          goto LABEL_13;
        }
      }
    }
    v15 = v17 + 1;
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x14002c6c0  push    rbx
0x14002c6c2  push    rbp
0x14002c6c3  push    rsi
0x14002c6c4  push    rdi
0x14002c6c5  push    r14
0x14002c6c7  push    r15
0x14002c6c9  sub     rsp, 28h
0x14002c6cd  mov     rdi, r9
0x14002c6d0  mov     rbx, r8
0x14002c6d3  mov     r10, rdx
0x14002c6d6  mov     r11, rcx
0x14002c6d9  test    rcx, rcx
0x14002c6dc  jnz     short loc_14002C713
0x14002c6de  test    rdx, rdx
0x14002c6e1  jnz     short loc_14002C713
0x14002c6e3  test    rbx, rbx
0x14002c6e6  jnz     short loc_14002C713
0x14002c6e8  mov     rax, [rsp+58h+arg_20]
0x14002c6f0  mov     [r9], cl
0x14002c6f3  mov     [rax], cx
0x14002c6f6  mov     rax, [rsp+58h+arg_28]
0x14002c6fe  mov     [rax], cx
0x14002c701  mov     rax, [rsp+58h+arg_30]
0x14002c709  mov     [rax], cx
0x14002c70c  xor     eax, eax
0x14002c70e  jmp     loc_14002C845
0x14002c713  mov     r15, 4F8B588E368F0847h
0x14002c71d  mov     r8, r11
0x14002c720  mov     rax, r15
0x14002c723  mov     rsi, r11
0x14002c726  mul     r11
0x14002c729  mov     r14d, 0FFFFh
0x14002c72f  sub     r8, rdx
0x14002c732  shr     r8, 1
0x14002c735  add     r8, rdx
0x14002c738  shr     r8, 10h
0x14002c73c  imul    rax, r8, 186A0h
0x14002c743  sub     rsi, rax
0x14002c746  cmp     r8, r14
0x14002c749  ja      short loc_14002C7CA
0x14002c74b  mov     rax, r15
0x14002c74e  mov     r9, r10
0x14002c751  mul     r10
0x14002c754  mov     rbp, r10
0x14002c757  sub     r9, rdx
0x14002c75a  shr     r9, 1
0x14002c75d  add     r9, rdx
0x14002c760  shr     r9, 10h
0x14002c764  imul    rcx, r9, 186A0h
0x14002c76b  sub     rbp, rcx
0x14002c76e  cmp     r9, r14
0x14002c771  ja      short loc_14002C7CA
0x14002c773  mov     rax, r15
0x14002c776  mov     rcx, rbx
0x14002c779  mul     rbx
0x14002c77c  sub     rcx, rdx
0x14002c77f  shr     rcx, 1
0x14002c782  add     rcx, rdx
0x14002c785  mov     rdx, rbx
0x14002c788  shr     rcx, 10h
0x14002c78c  imul    rax, rcx, 186A0h
0x14002c793  sub     rdx, rax
0x14002c796  cmp     rcx, r14
0x14002c799  ja      short loc_14002C7CA
0x14002c79b  test    rsi, rsi
0x14002c79e  jnz     short loc_14002C7CA
0x14002c7a0  test    rbp, rbp
0x14002c7a3  jnz     short loc_14002C7CA
0x14002c7a5  test    rdx, rdx
0x14002c7a8  jnz     short loc_14002C7CA
0x14002c7aa  mov     rax, [rsp+58h+arg_20]
0x14002c7b2  mov     byte ptr [rdi], 0Ah
0x14002c7b5  mov     [rax], r8w
0x14002c7b9  mov     rax, [rsp+58h+arg_28]
0x14002c7c1  mov     [rax], r9w
0x14002c7c5  jmp     loc_14002C701
0x14002c7ca  mov     [rsp+58h+arg_0], 0A08h
0x14002c7d1  xor     r8b, r8b
0x14002c7d4  mov     [rsp+58h+arg_2], 0Eh
0x14002c7d9  cmp     r8b, 3
0x14002c7dd  jnb     short loc_14002C840
0x14002c7df  movzx   eax, r8b
0x14002c7e3  mov     edx, 1
0x14002c7e8  mov     sil, byte ptr [rsp+rax+58h+arg_0]
0x14002c7ed  mov     cl, sil
0x14002c7f0  call    ClasspConvertCommandLimitDurationTo100ns
0x14002c7f5  mov     rcx, rax
0x14002c7f8  xor     edx, edx
0x14002c7fa  mov     rax, r11
0x14002c7fd  div     rcx
0x14002c800  mov     rbp, rax
0x14002c803  cmp     rax, r14
0x14002c806  ja      short loc_14002C828
0x14002c808  xor     edx, edx
0x14002c80a  mov     rax, r10
0x14002c80d  div     rcx
0x14002c810  mov     r9, rax
0x14002c813  cmp     rax, r14
0x14002c816  ja      short loc_14002C828
0x14002c818  xor     edx, edx
0x14002c81a  mov     rax, rbx
0x14002c81d  div     rcx
0x14002c820  mov     rcx, rax
0x14002c823  cmp     rax, r14
0x14002c826  jbe     short loc_14002C82D
0x14002c828  inc     r8b
0x14002c82b  jmp     short loc_14002C7D9
0x14002c82d  mov     rax, [rsp+58h+arg_20]
0x14002c835  mov     [rdi], sil
0x14002c838  mov     [rax], bp
0x14002c83b  jmp     loc_14002C7B9
0x14002c840  mov     eax, 0C00000BBh
0x14002c845  add     rsp, 28h
0x14002c849  pop     r15
0x14002c84b  pop     r14
0x14002c84d  pop     rdi
0x14002c84e  pop     rsi
0x14002c84f  pop     rbp
0x14002c850  pop     rbx
0x14002c851  retn
```
