# CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)

- ea: `0x140006290`
- end: `0x14000636e`
- name: `?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z`
- size: `222`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400058b4`
- `0x140005a88`
- `0x140008d58`
- `0x14000ff10`
- `0x140014140`

## callees

- `0x140006290`

## pseudocode

```c
__int64 __fastcall CompareStrsCaseInsensitive(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  const unsigned __int16 *v3; // r10
  const unsigned __int16 *v4; // r9
  unsigned __int64 v5; // rax
  unsigned __int16 v6; // cx
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // r11
  __int64 result; // rax

  v3 = a2;
  v4 = a1;
  if ( a3 == -1 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a1[v5] );
    }
    else
    {
      v5 = 0;
    }
    if ( a2 )
    {
      a3 = -1;
      do
        ++a3;
      while ( a2[a3] );
    }
    else
    {
      a3 = 0;
    }
    if ( v5 > a3 )
      a3 = v5;
  }
  while ( 1 )
  {
    if ( !a3 )
      return 0;
    v6 = *v4;
    v7 = *v3;
    if ( *v4 != *v3 )
      break;
    if ( !v6 )
      return 0;
LABEL_27:
    --a3;
    ++v4;
    ++v3;
  }
  if ( !v6 )
    return 0xFFFFFFFFLL;
  if ( !v7 )
    return 1;
  v8 = *v4;
  if ( (unsigned __int16)(v6 - 65) <= 0x19u )
    v8 = v6 + 32;
  v9 = *v3;
  if ( (unsigned __int16)(v7 - 65) <= 0x19u )
    v9 = v7 + 32;
  if ( v8 == v9 )
    goto LABEL_27;
  result = 1;
  if ( v6 <= v7 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x140006290  push    rdi
0x140006292  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140006299  mov     r10, rdx
0x14000629c  mov     r9, rcx
0x14000629f  cmp     r8, rdi
0x1400062a2  jnz     short loc_1400062E7
0x1400062a4  test    rcx, rcx
0x1400062a7  jz      short loc_1400062BC
0x1400062a9  mov     rax, rdi
0x1400062ac  nop     dword ptr [rax+00h]
0x1400062b0  inc     rax
0x1400062b3  cmp     word ptr [rcx+rax*2], 0
0x1400062b8  jnz     short loc_1400062B0
0x1400062ba  jmp     short loc_1400062BE
0x1400062bc  xor     eax, eax
0x1400062be  test    rdx, rdx
0x1400062c1  jz      short loc_1400062DD
0x1400062c3  mov     r8, rdi
0x1400062c6  nop     word ptr [rax+rax+00000000h]
0x1400062d0  inc     r8
0x1400062d3  cmp     word ptr [rdx+r8*2], 0
0x1400062d9  jnz     short loc_1400062D0
0x1400062db  jmp     short loc_1400062E0
0x1400062dd  xor     r8d, r8d
0x1400062e0  cmp     rax, r8
0x1400062e3  cmova   r8, rax
0x1400062e7  mov     [rsp+8+arg_0], rbx
0x1400062ec  cmp     r8, 1
0x1400062f0  jb      short loc_140006365
0x1400062f2  movzx   ecx, word ptr [r9]
0x1400062f6  xor     eax, eax
0x1400062f8  movzx   edx, word ptr [r10]
0x1400062fc  cmp     cx, dx
0x1400062ff  jz      short loc_140006343
0x140006301  cmp     ax, cx
0x140006304  jz      short loc_140006361
0x140006306  cmp     ax, dx
0x140006309  jz      short loc_140006355
0x14000630b  lea     eax, [rcx-41h]
0x14000630e  movzx   ebx, cx
0x140006311  cmp     ax, 19h
0x140006315  ja      short loc_14000631A
0x140006317  lea     ebx, [rcx+20h]
0x14000631a  lea     eax, [rdx-41h]
0x14000631d  movzx   r11d, dx
0x140006321  cmp     ax, 19h
0x140006325  ja      short loc_14000632B
0x140006327  lea     r11d, [rdx+20h]
0x14000632b  cmp     bx, r11w
0x14000632f  jz      short loc_140006348
0x140006331  cmp     cx, dx
0x140006334  mov     eax, 1
0x140006339  cmovbe  eax, edi
0x14000633c  mov     rbx, [rsp+8+arg_0]
0x140006341  pop     rdi
0x140006342  retn
0x140006343  cmp     ax, cx
0x140006346  jz      short loc_140006365
0x140006348  dec     r8
0x14000634b  add     r9, 2
0x14000634f  add     r10, 2
0x140006353  jmp     short loc_1400062EC
0x140006355  mov     eax, 1
0x14000635a  mov     rbx, [rsp+8+arg_0]
0x14000635f  pop     rdi
0x140006360  retn
0x140006361  mov     eax, edi
0x140006363  jmp     short loc_140006367
0x140006365  xor     eax, eax
0x140006367  mov     rbx, [rsp+8+arg_0]
0x14000636c  pop     rdi
0x14000636d  retn
```
