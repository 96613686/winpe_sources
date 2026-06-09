# SetSrbScsiData

- ea: `0x1400034f0`
- end: `0x1400035af`
- name: `SetSrbScsiData`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140004ca0`

## callees

- `0x1400034f0`

## pseudocode

```c
__int64 __fastcall SetSrbScsiData(__int64 a1, char a2, int a3, __int64 a4, __int64 a5, unsigned __int8 a6)
{
  unsigned int v8; // r10d
  __int64 v9; // r9
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // r11
  __int64 v13; // rbx
  int v14; // edx
  int v15; // edx
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 2) != 40 )
    return result;
  if ( *(_DWORD *)(a1 + 20) )
    return result;
  v8 = *(_DWORD *)(a1 + 56);
  v9 = 0;
  if ( !v8 )
    return result;
  while ( 1 )
  {
    v10 = *(unsigned int *)(a1 + 4 * v9 + 120);
    if ( (unsigned int)v10 < 0x80 )
      goto LABEL_16;
    v11 = *(unsigned int *)(a1 + 16);
    if ( (unsigned int)v10 > (unsigned int)v11 )
      goto LABEL_16;
    v12 = v10 + a1;
    v13 = (unsigned int)v10;
    v14 = *(_DWORD *)(v10 + a1) - 64;
    if ( !v14 )
      break;
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 == 1 && v13 + 40 <= v11 )
      {
        *(_QWORD *)(v12 + 24) = a5;
        *(_DWORD *)(v12 + 12) = a3;
        goto LABEL_13;
      }
    }
    else if ( v13 + 56 <= v11 )
    {
      goto LABEL_12;
    }
LABEL_16:
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= v8 )
      return result;
  }
  if ( v13 + 40 > v11 )
    goto LABEL_16;
LABEL_12:
  *(_QWORD *)(v12 + 16) = a5;
  *(_BYTE *)(v12 + 10) = a2;
LABEL_13:
  result = a6;
  *(_BYTE *)(v12 + 9) = a6;
  *(_BYTE *)(v12 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x1400034f0  mov     [rsp+arg_8], rsi
0x1400034f5  push    rdi
0x1400034f6  cmp     byte ptr [rcx+2], 28h ; '('
0x1400034fa  mov     edi, r8d
0x1400034fd  movzx   esi, dl
0x140003500  jnz     loc_140003590
0x140003506  cmp     dword ptr [rcx+14h], 0
0x14000350a  jnz     loc_140003590
0x140003510  mov     r10d, [rcx+38h]
0x140003514  xor     r9d, r9d
0x140003517  test    r10d, r10d
0x14000351a  jz      short loc_140003590
0x14000351c  mov     [rsp+8+arg_0], rbx
0x140003521  mov     edx, [rcx+r9*4+78h]
0x140003526  cmp     edx, 80h
0x14000352c  jb      short loc_1400035A1
0x14000352e  mov     r8d, [rcx+10h]
0x140003532  cmp     edx, r8d
0x140003535  ja      short loc_1400035A1
0x140003537  lea     r11, [rdx+rcx]
0x14000353b  mov     ebx, edx
0x14000353d  mov     edx, [r11]
0x140003540  sub     edx, 40h ; '@'
0x140003543  jz      short loc_140003598
0x140003545  sub     edx, 1
0x140003548  jz      short loc_140003567
0x14000354a  cmp     edx, 1
0x14000354d  jnz     short loc_1400035A1
0x14000354f  lea     rdx, [rbx+28h]
0x140003553  cmp     rdx, r8
0x140003556  ja      short loc_1400035A1
0x140003558  mov     rax, [rsp+8+arg_20]
0x14000355d  mov     [r11+18h], rax
0x140003561  mov     [r11+0Ch], edi
0x140003565  jmp     short loc_14000357D
0x140003567  lea     rdx, [rbx+38h]
0x14000356b  cmp     rdx, r8
0x14000356e  ja      short loc_1400035A1
0x140003570  mov     rax, [rsp+8+arg_20]
0x140003575  mov     [r11+10h], rax
0x140003579  mov     [r11+0Ah], sil
0x14000357d  movzx   eax, [rsp+8+arg_28]
0x140003582  mov     [r11+9], al
0x140003586  mov     byte ptr [r11+8], 0
0x14000358b  mov     rbx, [rsp+8+arg_0]
0x140003590  mov     rsi, [rsp+8+arg_8]
0x140003595  pop     rdi
0x140003596  retn
0x140003598  lea     rdx, [rbx+28h]
0x14000359c  cmp     rdx, r8
0x14000359f  jbe     short loc_140003570
0x1400035a1  inc     r9d
0x1400035a4  cmp     r9d, r10d
0x1400035a7  jb      loc_140003521
0x1400035ad  jmp     short loc_14000358B
```
