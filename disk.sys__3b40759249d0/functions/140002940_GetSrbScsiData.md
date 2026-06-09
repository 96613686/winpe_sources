# GetSrbScsiData

- ea: `0x140002940`
- end: `0x140002ab9`
- name: `GetSrbScsiData`
- size: `377`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001ec0`
- `0x140004ca0`

## callees

- `0x140002940`

## pseudocode

```c
__int64 __fastcall GetSrbScsiData(__int64 a1, _BYTE *a2, _DWORD *a3, _BYTE *a4, _QWORD *a5, _BYTE *a6)
{
  __int64 v6; // r10
  unsigned int v9; // r9d
  __int64 v10; // r11
  __int64 v11; // rdx
  unsigned __int64 v12; // rbp
  __int64 v13; // rsi
  __int64 v14; // r14
  int v15; // edx
  int v16; // edx
  _QWORD *v17; // rcx
  __int64 v18; // rax

  v6 = 0;
  if ( *(_BYTE *)(a1 + 2) != 40 || *(_DWORD *)(a1 + 20) )
  {
    if ( a2 )
      *a2 = 0;
    if ( a3 )
      *a3 = 0;
    if ( a4 )
      *a4 = 0;
    if ( a5 )
      *a5 = 0;
    if ( a6 )
      *a6 = 0;
    return v6;
  }
  v9 = *(_DWORD *)(a1 + 56);
  v10 = 0;
  if ( !v9 )
    return v6;
  while ( 1 )
  {
    v11 = *(unsigned int *)(a1 + 4 * v10 + 120);
    if ( (unsigned int)v11 < 0x80 )
      goto LABEL_31;
    v12 = *(unsigned int *)(a1 + 16);
    if ( (unsigned int)v11 > (unsigned int)v12 )
      goto LABEL_31;
    v13 = v11 + a1;
    v14 = (unsigned int)v11;
    v15 = *(_DWORD *)(v11 + a1) - 64;
    if ( v15 )
      break;
    if ( v14 + 40 <= v12 )
    {
      if ( a2 )
        *a2 = *(_BYTE *)(v13 + 10);
      v6 = v13 + 24;
      if ( !*(_BYTE *)(v13 + 10) )
        v6 = 0;
      if ( a4 )
        goto LABEL_27;
      goto LABEL_28;
    }
LABEL_31:
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= v9 )
      return v6;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    if ( v16 == 1 && v14 + 40 <= v12 )
    {
      if ( a3 )
        *a3 = *(_DWORD *)(v13 + 12);
      v6 = v13 + 32;
      if ( !*(_DWORD *)(v13 + 12) )
        v6 = 0;
      if ( a4 )
        *a4 = *(_BYTE *)(v13 + 8);
      v17 = a5;
      if ( a5 )
      {
        v18 = *(_QWORD *)(v13 + 24);
LABEL_18:
        *v17 = v18;
        goto LABEL_19;
      }
      goto LABEL_19;
    }
    goto LABEL_31;
  }
  if ( v14 + 56 > v12 )
    goto LABEL_31;
  if ( a2 )
    *a2 = *(_BYTE *)(v13 + 10);
  v6 = v13 + 24;
  if ( !*(_BYTE *)(v13 + 10) )
    v6 = 0;
  if ( a4 )
LABEL_27:
    *a4 = *(_BYTE *)(v13 + 8);
LABEL_28:
  v17 = a5;
  if ( a5 )
  {
    v18 = *(_QWORD *)(v13 + 16);
    goto LABEL_18;
  }
LABEL_19:
  if ( a6 )
    *a6 = *(_BYTE *)(v13 + 9);
  return v6;
}

```

## disassembly

```asm
0x140002940  push    rbx
0x140002942  push    rbp
0x140002943  push    rsi
0x140002944  push    rdi
0x140002945  push    r14
0x140002947  xor     r10d, r10d
0x14000294a  mov     rbx, r9
0x14000294d  cmp     byte ptr [rcx+2], 28h ; '('
0x140002951  mov     rdi, rdx
0x140002954  jnz     loc_140002A7C
0x14000295a  cmp     [rcx+14h], r10d
0x14000295e  jnz     loc_140002A7C
0x140002964  mov     r9d, [rcx+38h]
0x140002968  xor     r11d, r11d
0x14000296b  test    r9d, r9d
0x14000296e  jz      loc_140002AAE
0x140002974  mov     edx, [rcx+r11*4+78h]
0x140002979  cmp     edx, 80h
0x14000297f  jb      loc_140002A4F
0x140002985  mov     ebp, [rcx+10h]
0x140002988  cmp     edx, ebp
0x14000298a  ja      loc_140002A4F
0x140002990  lea     rsi, [rdx+rcx]
0x140002994  mov     r14d, edx
0x140002997  mov     edx, [rsi]
0x140002999  sub     edx, 40h ; '@'
0x14000299c  jz      loc_140002A46
0x1400029a2  sub     edx, 1
0x1400029a5  jz      short loc_140002A0A
0x1400029a7  cmp     edx, 1
0x1400029aa  jnz     loc_140002A4F
0x1400029b0  lea     rdx, [r14+28h]
0x1400029b4  cmp     rdx, rbp
0x1400029b7  ja      loc_140002A4F
0x1400029bd  test    r8, r8
0x1400029c0  jz      short loc_1400029C8
0x1400029c2  mov     eax, [rsi+0Ch]
0x1400029c5  mov     [r8], eax
0x1400029c8  xor     eax, eax
0x1400029ca  lea     r10, [rsi+20h]
0x1400029ce  cmp     [rsi+0Ch], eax
0x1400029d1  cmovz   r10, rax
0x1400029d5  test    rbx, rbx
0x1400029d8  jz      short loc_1400029E0
0x1400029da  movzx   eax, byte ptr [rsi+8]
0x1400029de  mov     [rbx], al
0x1400029e0  mov     rcx, [rsp+28h+arg_20]
0x1400029e5  test    rcx, rcx
0x1400029e8  jz      short loc_1400029F1
0x1400029ea  mov     rax, [rsi+18h]
0x1400029ee  mov     [rcx], rax
0x1400029f1  mov     rcx, [rsp+28h+arg_28]
0x1400029f6  test    rcx, rcx
0x1400029f9  jz      loc_140002AAE
0x1400029ff  movzx   eax, byte ptr [rsi+9]
0x140002a03  mov     [rcx], al
0x140002a05  jmp     loc_140002AAE
0x140002a0a  lea     rdx, [r14+38h]
0x140002a0e  cmp     rdx, rbp
0x140002a11  ja      short loc_140002A4F
0x140002a13  test    rdi, rdi
0x140002a16  jz      short loc_140002A1E
0x140002a18  movzx   eax, byte ptr [rsi+0Ah]
0x140002a1c  mov     [rdi], al
0x140002a1e  xor     eax, eax
0x140002a20  lea     r10, [rsi+18h]
0x140002a24  cmp     [rsi+0Ah], al
0x140002a27  cmovz   r10, rax
0x140002a2b  test    rbx, rbx
0x140002a2e  jz      short loc_140002A36
0x140002a30  movzx   eax, byte ptr [rsi+8]
0x140002a34  mov     [rbx], al
0x140002a36  mov     rcx, [rsp+28h+arg_20]
0x140002a3b  test    rcx, rcx
0x140002a3e  jz      short loc_1400029F1
0x140002a40  mov     rax, [rsi+10h]
0x140002a44  jmp     short loc_1400029EE
0x140002a46  lea     rdx, [r14+28h]
0x140002a4a  cmp     rdx, rbp
0x140002a4d  jbe     short loc_140002A5D
0x140002a4f  inc     r11d
0x140002a52  cmp     r11d, r9d
0x140002a55  jb      loc_140002974
0x140002a5b  jmp     short loc_140002AAE
0x140002a5d  test    rdi, rdi
0x140002a60  jz      short loc_140002A68
0x140002a62  movzx   eax, byte ptr [rsi+0Ah]
0x140002a66  mov     [rdi], al
0x140002a68  xor     eax, eax
0x140002a6a  lea     r10, [rsi+18h]
0x140002a6e  cmp     [rsi+0Ah], al
0x140002a71  cmovz   r10, rax
0x140002a75  test    rbx, rbx
0x140002a78  jz      short loc_140002A36
0x140002a7a  jmp     short loc_140002A30
0x140002a7c  test    rdi, rdi
0x140002a7f  jz      short loc_140002A84
0x140002a81  mov     [rdx], r10b
0x140002a84  test    r8, r8
0x140002a87  jz      short loc_140002A8C
0x140002a89  mov     [r8], r10d
0x140002a8c  test    rbx, rbx
0x140002a8f  jz      short loc_140002A94
0x140002a91  mov     [r9], r10b
0x140002a94  mov     rax, [rsp+28h+arg_20]
0x140002a99  test    rax, rax
0x140002a9c  jz      short loc_140002AA1
0x140002a9e  mov     [rax], r10
0x140002aa1  mov     rax, [rsp+28h+arg_28]
0x140002aa6  test    rax, rax
0x140002aa9  jz      short loc_140002AAE
0x140002aab  mov     [rax], r10b
0x140002aae  mov     rax, r10
0x140002ab1  pop     r14
0x140002ab3  pop     rdi
0x140002ab4  pop     rsi
0x140002ab5  pop     rbp
0x140002ab6  pop     rbx
0x140002ab7  retn
```
