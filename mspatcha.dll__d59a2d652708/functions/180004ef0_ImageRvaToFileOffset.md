# ImageRvaToFileOffset

- ea: `0x180004ef0`
- end: `0x180004f85`
- name: `ImageRvaToFileOffset`
- size: `149`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180004db8`
- `0x180004e48`
- `0x1800050bc`
- `0x180005338`
- `0x180005754`
- `0x180005934`
- `0x180005c60`
- `0x180005d5c`
- `0x180005f64`
- `0x1800061e4`
- `0x180006b98`

## callees

- `0x180004ef0`
- `0x180005400`

## pseudocode

```c
__int64 __fastcall ImageRvaToFileOffset(__int64 a1, __int64 a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v6; // r10
  unsigned int v7; // edi
  __int64 v8; // rsi
  unsigned __int64 v9; // r11
  __int64 v10; // rcx
  unsigned int *v11; // r8
  unsigned __int64 v12; // rax

  if ( (unsigned int)a2 < *(_DWORD *)(a1 + 84) )
    return (unsigned int)a2;
  v6 = 0;
  v7 = *(unsigned __int16 *)(a1 + 6);
  v8 = a1 + *(unsigned __int16 *)(a1 + 20) + 24LL;
  v9 = a3 + (unsigned int)a4;
  if ( !*(_WORD *)(a1 + 6) )
    return 0;
  while ( 1 )
  {
    v10 = 5 * v6;
    v11 = (unsigned int *)(v8 + 40 * v6);
    if ( (unsigned __int64)v11 < a3
      || (v6 = (unsigned int)(v6 + 1), v10 = 5 * v6, v12 = v8 + 40 * v6, (unsigned __int64)v11 > v12)
      || v12 > v9 )
    {
      ThrowPeFmtException(v10, a2, v11, a4);
      JUMPOUT(0x180004F84LL);
    }
    a4 = v11[3];
    if ( (unsigned int)a2 >= (unsigned int)a4 && (unsigned int)a2 < (unsigned int)a4 + v11[4] )
      break;
    if ( (unsigned int)v6 >= v7 )
      return 0;
  }
  return (unsigned int)a2 + v11[5] - (_DWORD)a4;
}

```

## disassembly

```asm
0x180004ef0  mov     [rsp+arg_0], rbx
0x180004ef5  mov     [rsp+arg_8], rsi
0x180004efa  push    rdi
0x180004efb  sub     rsp, 20h
0x180004eff  mov     rbx, r8
0x180004f02  cmp     edx, [rcx+54h]
0x180004f05  jnb     short loc_180004F0B
0x180004f07  mov     eax, edx
0x180004f09  jmp     short loc_180004F64
0x180004f0b  movzx   esi, word ptr [rcx+14h]
0x180004f0f  xor     r10d, r10d
0x180004f12  movzx   edi, word ptr [rcx+6]
0x180004f16  add     rsi, 18h
0x180004f1a  mov     r11d, r9d
0x180004f1d  add     rsi, rcx
0x180004f20  add     r11, rbx
0x180004f23  test    edi, edi
0x180004f25  jz      short loc_180004F62
0x180004f27  lea     rcx, [r10+r10*4]
0x180004f2b  lea     r8, [rsi+rcx*8]
0x180004f2f  cmp     r8, rbx
0x180004f32  jb      short loc_180004F7F
0x180004f34  inc     r10d
0x180004f37  lea     rcx, [r10+r10*4]
0x180004f3b  lea     rax, [rsi+rcx*8]
0x180004f3f  cmp     r8, rax
0x180004f42  ja      short loc_180004F7F
0x180004f44  cmp     rax, r11
0x180004f47  ja      short loc_180004F7F
0x180004f49  mov     r9d, [r8+0Ch]
0x180004f4d  cmp     edx, r9d
0x180004f50  jb      short loc_180004F5D
0x180004f52  mov     ecx, [r8+10h]
0x180004f56  add     ecx, r9d
0x180004f59  cmp     edx, ecx
0x180004f5b  jb      short loc_180004F74
0x180004f5d  cmp     r10d, edi
0x180004f60  jb      short loc_180004F27
0x180004f62  xor     eax, eax
0x180004f64  mov     rbx, [rsp+28h+arg_0]
0x180004f69  mov     rsi, [rsp+28h+arg_8]
0x180004f6e  add     rsp, 20h
0x180004f72  pop     rdi
0x180004f73  retn
0x180004f74  mov     eax, [r8+14h]
0x180004f78  sub     eax, r9d
0x180004f7b  add     eax, edx
0x180004f7d  jmp     short loc_180004F64
0x180004f7f  call    ThrowPeFmtException
```
