# EtwpGetNextEventOffsetType

- ea: `0x180012e48`
- end: `0x180012f78`
- name: `EtwpGetNextEventOffsetType`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000501c`
- `0x1800052b4`
- `0x180005cc8`
- `0x1800085d0`
- `0x1800110b0`

## callees

- `0x180012e48`

## pseudocode

```c
__int64 __fastcall EtwpGetNextEventOffsetType(unsigned int *a1, unsigned int a2, unsigned int *a3)
{
  __int64 v3; // rbx
  __int64 v4; // r11
  int v5; // edx
  unsigned int v6; // eax
  unsigned int v7; // r10d
  bool v8; // zf
  int v9; // eax
  unsigned int v11; // eax
  bool v12; // cf
  unsigned int v13; // eax

  *a3 = 0;
  v3 = *a1;
  v4 = a2;
  if ( !(_DWORD)v3 || a2 >= a1[12] || a2 < 0x48 || a2 >= (unsigned __int64)(v3 - 4) )
    return 0;
  v5 = *(unsigned int *)((char *)a1 + a2);
  v6 = *(unsigned int *)((char *)a1 + v4) & 0xFF000000;
  if ( v6 == -1879048192 )
  {
    v11 = (unsigned __int16)v5;
    v7 = 15;
    v12 = (unsigned __int16)v5 < 8u;
    goto LABEL_31;
  }
  if ( v6 != -1073741824 )
    return 0;
  v7 = BYTE2(v5);
  if ( BYTE2(v5) <= 0xDu )
  {
    if ( BYTE2(v5) != 13 )
    {
      if ( BYTE2(v5) == 1 || BYTE2(v5) == 2 )
      {
        if ( (unsigned int)v4 < (unsigned __int64)(v3 - 8) )
        {
          v11 = *(unsigned __int16 *)((char *)a1 + v4 + 4);
          v12 = v11 < 0x20;
          goto LABEL_31;
        }
      }
      else
      {
        if ( BYTE2(v5) != 3 && BYTE2(v5) != 4 )
        {
          v9 = BYTE2(v5) - 10;
          v8 = BYTE2(v5) == 10;
          goto LABEL_14;
        }
        if ( (unsigned int)v4 < (unsigned __int64)(v3 - 8) )
        {
          v11 = *(unsigned __int16 *)((char *)a1 + v4 + 4);
          v12 = v11 < 0x18;
          goto LABEL_31;
        }
      }
      return 0;
    }
    goto LABEL_27;
  }
  if ( BYTE2(v5) == 16 || BYTE2(v5) == 17 )
  {
    if ( (unsigned int)v4 < (unsigned __int64)(v3 - 8) )
    {
      v11 = *(unsigned __int16 *)((char *)a1 + v4 + 4);
      v12 = v11 < 0x10;
      goto LABEL_31;
    }
    return 0;
  }
  if ( BYTE2(v5) == 18 || BYTE2(v5) == 19 )
  {
LABEL_27:
    v11 = (unsigned __int16)v5;
    v12 = (unsigned __int16)v5 < 0x50u;
    goto LABEL_31;
  }
  v9 = BYTE2(v5) - 20;
  v8 = BYTE2(v5) == 20;
LABEL_14:
  if ( !v8 && v9 != 1 )
    return 0;
  v11 = (unsigned __int16)v5;
  v12 = (unsigned __int16)v5 < 0x30u;
LABEL_31:
  if ( v12 )
    return 0;
  v13 = (v11 + 7) & 0xFFFFFFF8;
  if ( v13 >= (unsigned int)v3 || v13 + (unsigned int)v4 > (unsigned int)v3 )
    return 0;
  *a3 = v13;
  return v7;
}

```

## disassembly

```asm
0x180012e48  mov     [rsp+arg_0], rbx
0x180012e4d  mov     [rsp+arg_8], rdi
0x180012e52  mov     dword ptr [r8], 0
0x180012e59  mov     r9, rcx
0x180012e5c  mov     ebx, [rcx]
0x180012e5e  mov     r11d, edx
0x180012e61  test    ebx, ebx
0x180012e63  jz      short loc_180012ECC
0x180012e65  cmp     r11d, [rcx+30h]
0x180012e69  jnb     short loc_180012ECC
0x180012e6b  cmp     r11d, 48h ; 'H'
0x180012e6f  jb      short loc_180012ECC
0x180012e71  lea     rax, [rbx-4]
0x180012e75  mov     ecx, r11d
0x180012e78  cmp     r11, rax
0x180012e7b  jnb     short loc_180012ECC
0x180012e7d  mov     edx, [r11+r9]
0x180012e81  mov     eax, edx
0x180012e83  and     eax, 0FF000000h
0x180012e88  cmp     eax, 90000000h
0x180012e8d  jz      loc_180012F41
0x180012e93  cmp     eax, 0C0000000h
0x180012e98  jnz     short loc_180012ECC
0x180012e9a  mov     eax, edx
0x180012e9c  shr     eax, 10h
0x180012e9f  movzx   r10d, al
0x180012ea3  cmp     r10d, 0Dh
0x180012ea7  ja      short loc_180012F01
0x180012ea9  jz      short loc_180012F25
0x180012eab  mov     eax, r10d
0x180012eae  sub     eax, 1
0x180012eb1  jz      short loc_180012EED
0x180012eb3  sub     eax, 1
0x180012eb6  jz      short loc_180012EED
0x180012eb8  sub     eax, 1
0x180012ebb  jz      short loc_180012ED9
0x180012ebd  sub     eax, 1
0x180012ec0  jz      short loc_180012ED9
0x180012ec2  sub     eax, 6
0x180012ec5  jz      short loc_180012F1D
0x180012ec7  cmp     eax, 1
0x180012eca  jz      short loc_180012F1D
0x180012ecc  xor     eax, eax
0x180012ece  mov     rbx, [rsp+arg_0]
0x180012ed3  mov     rdi, [rsp+arg_8]
0x180012ed8  retn
0x180012ed9  lea     rax, [rbx-8]
0x180012edd  cmp     rcx, rax
0x180012ee0  jnb     short loc_180012ECC
0x180012ee2  movzx   eax, word ptr [r11+r9+4]
0x180012ee8  cmp     eax, 18h
0x180012eeb  jmp     short loc_180012F4D
0x180012eed  lea     rax, [rbx-8]
0x180012ef1  cmp     rcx, rax
0x180012ef4  jnb     short loc_180012ECC
0x180012ef6  movzx   eax, word ptr [r11+r9+4]
0x180012efc  cmp     eax, 20h ; ' '
0x180012eff  jmp     short loc_180012F4D
0x180012f01  mov     eax, r10d
0x180012f04  sub     eax, 10h
0x180012f07  jz      short loc_180012F2D
0x180012f09  sub     eax, 1
0x180012f0c  jz      short loc_180012F2D
0x180012f0e  sub     eax, 1
0x180012f11  jz      short loc_180012F25
0x180012f13  sub     eax, 1
0x180012f16  jz      short loc_180012F25
0x180012f18  sub     eax, 1
0x180012f1b  jmp     short loc_180012EC5
0x180012f1d  movzx   eax, dx
0x180012f20  cmp     eax, 30h ; '0'
0x180012f23  jmp     short loc_180012F4D
0x180012f25  movzx   eax, dx
0x180012f28  cmp     eax, 50h ; 'P'
0x180012f2b  jmp     short loc_180012F4D
0x180012f2d  lea     rax, [rbx-8]
0x180012f31  cmp     rcx, rax
0x180012f34  jnb     short loc_180012ECC
0x180012f36  movzx   eax, word ptr [r11+r9+4]
0x180012f3c  cmp     eax, 10h
0x180012f3f  jmp     short loc_180012F4D
0x180012f41  movzx   eax, dx
0x180012f44  mov     r10d, 0Fh
0x180012f4a  cmp     eax, 8
0x180012f4d  jb      loc_180012ECC
0x180012f53  add     eax, 7
0x180012f56  and     eax, 0FFFFFFF8h
0x180012f59  cmp     eax, ebx
0x180012f5b  jnb     loc_180012ECC
0x180012f61  lea     ecx, [rax+r11]
0x180012f65  cmp     ecx, ebx
0x180012f67  ja      loc_180012ECC
0x180012f6d  mov     [r8], eax
0x180012f70  mov     eax, r10d
0x180012f73  jmp     loc_180012ECE
```
