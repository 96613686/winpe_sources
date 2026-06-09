# FillCalcParamCM

- ea: `0x18000e4fc`
- end: `0x18000e685`
- name: `FillCalcParamCM`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e724`
- `0x180020380`

## callees

- `0x18000e4fc`

## pseudocode

```c
__int64 __fastcall FillCalcParamCM(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v6; // edx
  __int64 result; // rax
  int v8; // r9d
  int v9; // eax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // edx
  __int64 v13; // rcx

  *(_DWORD *)(a1 + 24) = 16;
  *(_DWORD *)(a1 + 28) = 16;
  v6 = *(_DWORD *)(a2 + 48);
  switch ( v6 )
  {
    case 1:
      *(_DWORD *)a1 = 10;
      goto LABEL_5;
    case 3:
      *(_DWORD *)a1 = 16385;
      *(_QWORD *)(a1 + 40) = a3 + 2;
      *(_QWORD *)(a1 + 48) = a3 + 4;
      goto LABEL_5;
    case 4:
      *(_DWORD *)a1 = 16386;
      *(_QWORD *)(a1 + 40) = a3 + 2;
      *(_QWORD *)(a1 + 48) = a3 + 4;
      *(_QWORD *)(a1 + 56) = a3 + 6;
LABEL_5:
      *(_QWORD *)(a1 + 32) = a3;
      goto LABEL_6;
  }
  if ( v6 != 5 && v6 != 6 && (unsigned int)(v6 - 7) >= 2 )
    return 50;
  v9 = v6 + 12;
  v10 = 0;
  for ( *(_DWORD *)a1 = v9 | 0x2000; v10 < *(_DWORD *)(a2 + 48); *(_QWORD *)(a1 + 8 * v11 + 32) = v11 + a3 )
    v11 = v10++;
LABEL_6:
  switch ( *(_DWORD *)(a2 + 52) )
  {
    case 1:
      *(_DWORD *)(a1 + 4) = 10;
      goto LABEL_9;
    case 3:
      *(_DWORD *)(a1 + 4) = 16385;
      *(_QWORD *)(a1 + 104) = a3 + 2;
      *(_QWORD *)(a1 + 112) = a3 + 4;
LABEL_9:
      *(_QWORD *)(a1 + 96) = a3;
LABEL_10:
      result = 0;
      *(_DWORD *)(a1 + 8) = a4;
      v8 = 16 * a4;
      *(_DWORD *)(a1 + 16) = v8;
      *(_DWORD *)(a1 + 20) = v8;
      *(_DWORD *)(a1 + 12) = 1;
      return result;
    case 4:
      *(_DWORD *)(a1 + 4) = 16386;
      *(_QWORD *)(a1 + 104) = a3 + 2;
      *(_QWORD *)(a1 + 112) = a3 + 4;
      *(_QWORD *)(a1 + 120) = a3 + 6;
      goto LABEL_9;
  }
  if ( *(_DWORD *)(a2 + 52) == 5 || *(_DWORD *)(a2 + 52) == 6 || (unsigned int)(*(_DWORD *)(a2 + 52) - 7) <= 1 )
  {
    v12 = 0;
    for ( *(_DWORD *)(a1 + 4) = (*(_DWORD *)(a2 + 52) + 12) | 0x2000;
          v12 < *(_DWORD *)(a2 + 52);
          *(_QWORD *)(a1 + 8 * v13 + 96) = v13 + a3 )
    {
      v13 = v12++;
    }
    goto LABEL_10;
  }
  return 50;
}

```

## disassembly

```asm
0x18000e4fc  mov     eax, 10h
0x18000e501  mov     r10, rcx
0x18000e504  mov     [rcx+18h], eax
0x18000e507  mov     r11, rdx
0x18000e50a  mov     [rcx+1Ch], eax
0x18000e50d  mov     edx, [rdx+30h]
0x18000e510  mov     ecx, edx
0x18000e512  sub     ecx, 1
0x18000e515  jz      loc_18000E59F
0x18000e51b  sub     ecx, 2
0x18000e51e  jz      loc_18000E5A8
0x18000e524  sub     ecx, 1
0x18000e527  jnz     loc_18000E5C1
0x18000e52d  mov     dword ptr [r10], 4002h
0x18000e534  lea     rax, [r8+2]
0x18000e538  mov     [r10+28h], rax
0x18000e53c  lea     rax, [r8+4]
0x18000e540  mov     [r10+30h], rax
0x18000e544  lea     rax, [r8+6]
0x18000e548  mov     [r10+38h], rax
0x18000e54c  mov     [r10+20h], r8
0x18000e550  mov     edx, [r11+34h]
0x18000e554  mov     ecx, edx
0x18000e556  sub     ecx, 1
0x18000e559  jz      loc_18000E678
0x18000e55f  sub     ecx, 2
0x18000e562  jnz     loc_18000E60A
0x18000e568  lea     rax, [r8+2]
0x18000e56c  mov     dword ptr [r10+4], 4001h
0x18000e574  mov     [r10+68h], rax
0x18000e578  lea     rax, [r8+4]
0x18000e57c  mov     [r10+70h], rax
0x18000e580  mov     [r10+60h], r8
0x18000e584  xor     eax, eax
0x18000e586  mov     [r10+8], r9d
0x18000e58a  shl     r9d, 4
0x18000e58e  mov     [r10+10h], r9d
0x18000e592  mov     [r10+14h], r9d
0x18000e596  mov     dword ptr [r10+0Ch], 1
0x18000e59e  retn
0x18000e59f  mov     dword ptr [r10], 0Ah
0x18000e5a6  jmp     short loc_18000E54C
0x18000e5a8  lea     rax, [r8+2]
0x18000e5ac  mov     dword ptr [r10], 4001h
0x18000e5b3  mov     [r10+28h], rax
0x18000e5b7  lea     rax, [r8+4]
0x18000e5bb  mov     [r10+30h], rax
0x18000e5bf  jmp     short loc_18000E54C
0x18000e5c1  sub     ecx, 1
0x18000e5c4  jz      short loc_18000E5DB
0x18000e5c6  sub     ecx, 1
0x18000e5c9  jz      short loc_18000E5DB
0x18000e5cb  sub     ecx, 1
0x18000e5ce  jz      short loc_18000E5DB
0x18000e5d0  cmp     ecx, 1
0x18000e5d3  jz      short loc_18000E5DB
0x18000e5d5  mov     eax, 32h ; '2'
0x18000e5da  retn
0x18000e5db  lea     eax, [rdx+0Ch]
0x18000e5de  xor     edx, edx
0x18000e5e0  bts     eax, 0Dh
0x18000e5e4  mov     [r10], eax
0x18000e5e7  cmp     [r11+30h], edx
0x18000e5eb  jle     loc_18000E550
0x18000e5f1  movsxd  rcx, edx
0x18000e5f4  inc     edx
0x18000e5f6  lea     rax, [rcx+r8]
0x18000e5fa  mov     [r10+rcx*8+20h], rax
0x18000e5ff  cmp     edx, [r11+30h]
0x18000e603  jl      short loc_18000E5F1
0x18000e605  jmp     loc_18000E550
0x18000e60a  sub     ecx, 1
0x18000e60d  jz      short loc_18000E653
0x18000e60f  sub     ecx, 1
0x18000e612  jz      short loc_18000E623
0x18000e614  sub     ecx, 1
0x18000e617  jz      short loc_18000E623
0x18000e619  sub     ecx, 1
0x18000e61c  jz      short loc_18000E623
0x18000e61e  cmp     ecx, 1
0x18000e621  jnz     short loc_18000E5D5
0x18000e623  lea     eax, [rdx+0Ch]
0x18000e626  xor     edx, edx
0x18000e628  bts     eax, 0Dh
0x18000e62c  mov     [r10+4], eax
0x18000e630  cmp     [r11+34h], edx
0x18000e634  jle     loc_18000E584
0x18000e63a  movsxd  rcx, edx
0x18000e63d  inc     edx
0x18000e63f  lea     rax, [rcx+r8]
0x18000e643  mov     [r10+rcx*8+60h], rax
0x18000e648  cmp     edx, [r11+34h]
0x18000e64c  jl      short loc_18000E63A
0x18000e64e  jmp     loc_18000E584
0x18000e653  mov     dword ptr [r10+4], 4002h
0x18000e65b  lea     rax, [r8+2]
0x18000e65f  mov     [r10+68h], rax
0x18000e663  lea     rax, [r8+4]
0x18000e667  mov     [r10+70h], rax
0x18000e66b  lea     rax, [r8+6]
0x18000e66f  mov     [r10+78h], rax
0x18000e673  jmp     loc_18000E580
0x18000e678  mov     dword ptr [r10+4], 0Ah
0x18000e680  jmp     loc_18000E580
```
