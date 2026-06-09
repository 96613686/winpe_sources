# CS64ComputeMAC

- ea: `0x1800058b8`
- end: `0x18000597b`
- name: `CS64ComputeMAC`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005984`
- `0x180005f7c`

## callees

- `0x1800058b8`

## pseudocode

```c
__int64 __fastcall CS64ComputeMAC(_DWORD *a1, unsigned int a2, __int64 a3, int *a4)
{
  int v4; // edi
  int v6; // esi
  unsigned int v7; // r11d
  int v8; // ebp
  int v9; // r14d
  __int64 result; // rax
  int v11; // edx
  _DWORD *v12; // r10
  unsigned int v13; // ebx
  int v14; // ecx
  int v15; // edx
  int v16; // r8d
  int v17; // ecx
  int v18; // ecx

  v4 = *(_DWORD *)a3;
  sCSKey = v4;
  v6 = *(_DWORD *)(a3 + 4);
  v7 = 1;
  dword_18000C824 = v6;
  v8 = *(_DWORD *)(a3 + 8);
  dword_18000C828 = v8;
  v9 = *(_DWORD *)(a3 + 12);
  dword_18000C82C = v9;
  dword_18000C830 = *(_DWORD *)(a3 + 16);
  qword_18000C834 = *(_QWORD *)(a3 + 20);
  result = *(unsigned int *)(a3 + 28);
  dword_18000C83C = *(_DWORD *)(a3 + 28);
  v11 = a1[1];
  v12 = a1 + 2;
  v13 = a2 >> 1;
  v14 = v6 + v4 * *a1 * dword_18000C830;
  v15 = v9 + v8 * (v14 + v11);
  v16 = v14 + v15;
  if ( v13 > 1 )
  {
    do
    {
      ++v7;
      v17 = dword_18000C830 * *v12;
      v12 += 2;
      v18 = v6 + v4 * (v15 + v17);
      v15 = v9 + v8 * (v18 + *(v12 - 1));
      v16 += v15 + v18;
    }
    while ( v7 < v13 );
  }
  *a4 = v16;
  a4[1] = v15;
  return result;
}

```

## disassembly

```asm
0x1800058b8  push    rbx
0x1800058ba  push    rbp
0x1800058bb  push    rsi
0x1800058bc  push    rdi
0x1800058bd  push    r14
0x1800058bf  push    r15
0x1800058c1  mov     edi, [r8]
0x1800058c4  mov     r10, rcx
0x1800058c7  mov     cs:sCSKey, edi
0x1800058cd  mov     ebx, edx
0x1800058cf  mov     esi, [r8+4]
0x1800058d3  mov     r11d, 1
0x1800058d9  mov     cs:dword_18000C824, esi
0x1800058df  mov     ebp, [r8+8]
0x1800058e3  mov     cs:dword_18000C828, ebp
0x1800058e9  mov     r14d, [r8+0Ch]
0x1800058ed  mov     cs:dword_18000C82C, r14d
0x1800058f4  mov     r15d, [r8+10h]
0x1800058f8  mov     ecx, r15d
0x1800058fb  mov     cs:dword_18000C830, r15d
0x180005902  movsd   xmm0, qword ptr [r8+14h]
0x180005908  movsd   cs:qword_18000C834, xmm0
0x180005910  mov     eax, [r8+1Ch]
0x180005914  mov     cs:dword_18000C83C, eax
0x18000591a  imul    ecx, [r10]
0x18000591e  mov     edx, [r10+4]
0x180005922  add     r10, 8
0x180005926  shr     ebx, 1
0x180005928  imul    ecx, edi
0x18000592b  add     ecx, esi
0x18000592d  add     edx, ecx
0x18000592f  imul    edx, ebp
0x180005932  add     edx, r14d
0x180005935  lea     r8d, [rcx+rdx]
0x180005939  cmp     ebx, r11d
0x18000593c  jbe     short loc_18000596A
0x18000593e  mov     ecx, [r10]
0x180005941  inc     r11d
0x180005944  imul    ecx, r15d
0x180005948  lea     r10, [r10+8]
0x18000594c  add     ecx, edx
0x18000594e  mov     edx, [r10-4]
0x180005952  imul    ecx, edi
0x180005955  add     ecx, esi
0x180005957  add     edx, ecx
0x180005959  add     r8d, ecx
0x18000595c  imul    edx, ebp
0x18000595f  add     edx, r14d
0x180005962  add     r8d, edx
0x180005965  cmp     r11d, ebx
0x180005968  jb      short loc_18000593E
0x18000596a  mov     [r9], r8d
0x18000596d  mov     [r9+4], edx
0x180005971  pop     r15
0x180005973  pop     r14
0x180005975  pop     rdi
0x180005976  pop     rsi
0x180005977  pop     rbp
0x180005978  pop     rbx
0x180005979  retn
```
