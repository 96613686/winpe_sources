# DName::operator+(DName const &)

- ea: `0x18000ebe8`
- end: `0x18000eceb`
- name: `??HDName@@QEBA?AV0@AEBV0@@Z`
- size: `259`
- prototype: ``
- caller_count: `25`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ea20`
- `0x18000f43c`
- `0x180010420`
- `0x18001074c`
- `0x180010c90`
- `0x180011434`
- `0x18001152c`
- `0x18001181c`
- `0x180011a80`
- `0x180011bf0`
- `0x180011d00`
- `0x180011eec`
- `0x180011fb4`
- `0x1800125f8`
- `0x180012fc4`
- `0x180013188`
- `0x180013490`
- `0x180013810`
- `0x180013920`
- `0x180013c5c`
- `0x180013ec0`
- `0x180014230`
- `0x18001446c`
- `0x180014938`
- `0x180014bb0`

## callees

- `0x18000e880`
- `0x18000ebe8`
- `0x18000ef94`
- `0x18000f1b0`

## pseudocode

```c
__int64 __fastcall DName::operator+(__int64 *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  int v7; // r8d
  int v8; // eax
  int v9; // ecx
  int v10; // edx
  __int64 v11; // r8
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx

  v6 = *((_DWORD *)a1 + 2) ^ (*(_DWORD *)(a2 + 8) ^ *((_DWORD *)a1 + 2)) & 0xFFFFFFF0;
  *(_DWORD *)(a2 + 8) = v6;
  v7 = v6 ^ (*((_DWORD *)a1 + 2) ^ v6) & 0x10;
  *(_DWORD *)(a2 + 8) = v7;
  v8 = v7 ^ (*((_DWORD *)a1 + 2) ^ v7) & 0x20;
  *(_DWORD *)(a2 + 8) = v8;
  v9 = v8 ^ (*((_DWORD *)a1 + 2) ^ v8) & 0x40;
  *(_DWORD *)(a2 + 8) = v9;
  v10 = v9 ^ (*((_DWORD *)a1 + 2) ^ v9) & 0x80;
  *(_DWORD *)(a2 + 8) = v10;
  v11 = *a1;
  *(_QWORD *)a2 = *a1;
  v12 = v10 ^ (*((_DWORD *)a1 + 2) ^ v10) & 0x100;
  *(_DWORD *)(a2 + 8) = v12;
  v13 = v12 ^ (*((_DWORD *)a1 + 2) ^ v12) & 0x200;
  *(_DWORD *)(a2 + 8) = v13;
  v14 = v13 ^ (*((_DWORD *)a1 + 2) ^ v13) & 0x400;
  *(_DWORD *)(a2 + 8) = v14;
  v15 = v14 ^ (*((_DWORD *)a1 + 2) ^ v14) & 0x800;
  *(_DWORD *)(a2 + 8) = v15;
  if ( !v11 || ((v15 << 28 >> 28) & 0xFFFFFFFD) != 0 )
  {
    DName::operator=(a2, a3);
  }
  else if ( !*(_QWORD *)a3 || (((int)(*(_DWORD *)(a3 + 8) << 28) >> 28) & 0xFFFFFFFD) != 0 )
  {
    DName::operator+=(a2, (unsigned int)((int)(*(_DWORD *)(a3 + 8) << 28) >> 28));
  }
  else
  {
    DName::operator+=(a2, a3);
  }
  return a2;
}

```

## disassembly

```asm
0x18000ebe8  push    rbx
0x18000ebea  sub     rsp, 20h
0x18000ebee  mov     eax, [rcx+8]
0x18000ebf1  mov     r9, rcx
0x18000ebf4  xor     eax, [rdx+8]
0x18000ebf7  mov     rbx, rdx
0x18000ebfa  and     eax, 0FFFFFFF0h
0x18000ebfd  mov     r10, r8
0x18000ec00  xor     eax, [rcx+8]
0x18000ec03  mov     [rdx+8], eax
0x18000ec06  mov     r8d, eax
0x18000ec09  xor     r8d, [rcx+8]
0x18000ec0d  and     r8d, 10h
0x18000ec11  xor     r8d, eax
0x18000ec14  mov     [rdx+8], r8d
0x18000ec18  mov     eax, r8d
0x18000ec1b  xor     eax, [rcx+8]
0x18000ec1e  and     eax, 20h
0x18000ec21  xor     eax, r8d
0x18000ec24  mov     [rdx+8], eax
0x18000ec27  mov     ecx, eax
0x18000ec29  xor     ecx, [r9+8]
0x18000ec2d  and     ecx, 40h
0x18000ec30  xor     ecx, eax
0x18000ec32  mov     [rdx+8], ecx
0x18000ec35  mov     edx, ecx
0x18000ec37  xor     edx, [r9+8]
0x18000ec3b  and     edx, 80h
0x18000ec41  xor     edx, ecx
0x18000ec43  mov     [rbx+8], edx
0x18000ec46  mov     eax, edx
0x18000ec48  mov     r8, [r9]
0x18000ec4b  mov     [rbx], r8
0x18000ec4e  xor     eax, [r9+8]
0x18000ec52  and     eax, 100h
0x18000ec57  xor     eax, edx
0x18000ec59  mov     [rbx+8], eax
0x18000ec5c  mov     ecx, eax
0x18000ec5e  xor     ecx, [r9+8]
0x18000ec62  and     ecx, 200h
0x18000ec68  xor     ecx, eax
0x18000ec6a  mov     [rbx+8], ecx
0x18000ec6d  mov     eax, ecx
0x18000ec6f  xor     eax, [r9+8]
0x18000ec73  and     eax, 400h
0x18000ec78  xor     eax, ecx
0x18000ec7a  mov     [rbx+8], eax
0x18000ec7d  mov     ecx, eax
0x18000ec7f  xor     ecx, [r9+8]
0x18000ec83  and     ecx, 800h
0x18000ec89  xor     ecx, eax
0x18000ec8b  mov     [rbx+8], ecx
0x18000ec8e  test    r8, r8
0x18000ec91  jz      short loc_18000ECD7
0x18000ec93  shl     ecx, 1Ch
0x18000ec96  mov     edx, 0FFFFFFFDh
0x18000ec9b  sar     ecx, 1Ch
0x18000ec9e  test    edx, ecx
0x18000eca0  jnz     short loc_18000ECD7
0x18000eca2  cmp     qword ptr [r10], 0
0x18000eca6  jz      short loc_18000ECC3
0x18000eca8  mov     eax, [r10+8]
0x18000ecac  shl     eax, 1Ch
0x18000ecaf  sar     eax, 1Ch
0x18000ecb2  test    edx, eax
0x18000ecb4  jnz     short loc_18000ECC3
0x18000ecb6  mov     rdx, r10
0x18000ecb9  mov     rcx, rbx
0x18000ecbc  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18000ecc1  jmp     short loc_18000ECE2
0x18000ecc3  mov     edx, [r10+8]
0x18000ecc7  mov     rcx, rbx
0x18000ecca  shl     edx, 1Ch
0x18000eccd  sar     edx, 1Ch
0x18000ecd0  call    ??YDName@@QEAAAEAV0@W4DNameStatus@@@Z; DName::operator+=(DNameStatus)
0x18000ecd5  jmp     short loc_18000ECE2
0x18000ecd7  mov     rdx, r10
0x18000ecda  mov     rcx, rbx
0x18000ecdd  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x18000ece2  mov     rax, rbx
0x18000ece5  add     rsp, 20h
0x18000ece9  pop     rbx
0x18000ecea  retn
```
