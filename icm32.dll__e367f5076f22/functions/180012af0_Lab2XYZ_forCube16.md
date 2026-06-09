# Lab2XYZ_forCube16

- ea: `0x180012af0`
- end: `0x180012c8a`
- name: `Lab2XYZ_forCube16`
- size: `410`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x18003cb08`

## callees

- `0x180012af0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012b11`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012b11`

## pseudocode

```c
ULONG __fastcall Lab2XYZ_forCube16(unsigned __int16 *a1, int a2)
{
  ULONG result; // eax
  int i; // esi
  unsigned __int64 v6; // r8
  int v7; // r9d
  int v8; // eax
  int v9; // edx
  int v10; // edi
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  int v14; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // ecx

  result = EventWrite(g_etwHandle, &CONVERT_LAB_TO_XYZ, 0, 0);
  for ( i = 0; i < a2; a1 += 3 )
  {
    v6 = *a1;
    v7 = ((19 * (unsigned int)a1[1] + 15) >> 5) + v6 - 19456;
    if ( v7 < 0 )
    {
      v10 = 0;
    }
    else
    {
      v8 = v7 >> 8;
      if ( v7 >> 8 >= 431 )
      {
        v10 = 131070;
      }
      else
      {
        v9 = word_18003F840[v8];
        v10 = (((unsigned __int8)(((19 * (unsigned int)a1[1] + 15) >> 5) + v6) * (word_18003F840[v8 + 1] - v9) + 63) >> 7)
            + 2 * v9;
      }
    }
    v11 = v6 - ((95 * (unsigned int)a1[2] + 31) >> 6) + 48640;
    if ( v11 < 0 )
    {
      v14 = 0;
    }
    else
    {
      v12 = v11 >> 8;
      if ( v11 >> 8 >= 431 )
      {
        v14 = 131070;
      }
      else
      {
        v13 = word_18003F840[v12];
        v14 = (((unsigned __int8)(v6 - ((95 * (unsigned int)a1[2] + 31) >> 6)) * (word_18003F840[v12 + 1] - v13) + 63) >> 7)
            + 2 * v13;
      }
    }
    v15 = word_18003F840[v6 >> 8];
    result = (31595 * v10 + 0x4000) >> 15;
    v16 = (((unsigned __int8)v6 * (word_18003F840[(v6 >> 8) + 1] - v15) + 63) >> 7) + 2 * v15;
    v17 = (13515 * v14 + 0x2000) >> 14;
    *a1 = result;
    if ( v17 > 0xFFFF )
      LOWORD(v17) = -1;
    a1[1] = v16;
    a1[2] = v17;
    ++i;
  }
  return result;
}

```

## disassembly

```asm
0x180012af0  push    rbx
0x180012af2  push    rbp
0x180012af3  push    rsi
0x180012af4  sub     rsp, 20h
0x180012af8  mov     ebp, edx
0x180012afa  mov     rbx, rcx
0x180012afd  mov     rcx, cs:g_etwHandle; RegHandle
0x180012b04  lea     rdx, CONVERT_LAB_TO_XYZ; EventDescriptor
0x180012b0b  xor     r9d, r9d; UserData
0x180012b0e  xor     r8d, r8d; UserDataCount
0x180012b11  call    cs:__imp_EventWrite
0x180012b17  xor     esi, esi
0x180012b19  test    ebp, ebp
0x180012b1b  jle     loc_180012C5E
0x180012b21  mov     [rsp+38h+arg_0], rdi
0x180012b26  mov     [rsp+38h+arg_8], r14
0x180012b2b  lea     r14, word_18003F840
0x180012b32  mov     [rsp+38h+arg_10], r15
0x180012b37  mov     r15d, 0FFFFh
0x180012b3d  nop     dword ptr [rax]
0x180012b40  movzx   eax, word ptr [rbx+2]
0x180012b44  movzx   r8d, word ptr [rbx]
0x180012b48  movzx   r11d, word ptr [rbx+4]
0x180012b4d  imul    ecx, eax, 13h
0x180012b50  lea     r9d, [r8-4C00h]
0x180012b57  add     ecx, 0Fh
0x180012b5a  shr     ecx, 5
0x180012b5d  add     r9d, ecx
0x180012b60  js      loc_180012C6E
0x180012b66  mov     eax, r9d
0x180012b69  sar     eax, 8
0x180012b6c  cmp     eax, 1AFh
0x180012b71  jge     loc_180012C80
0x180012b77  cdqe
0x180012b79  movzx   edx, word ptr [r14+rax*2]
0x180012b7e  movzx   ecx, word ptr [r14+rax*2+2]
0x180012b84  sub     ecx, edx
0x180012b86  movzx   eax, r9b
0x180012b8a  imul    ecx, eax
0x180012b8d  add     ecx, 3Fh ; '?'
0x180012b90  sar     ecx, 7
0x180012b93  lea     edi, [rcx+rdx*2]
0x180012b96  imul    ecx, r11d, 5Fh ; '_'
0x180012b9a  mov     r9d, r8d
0x180012b9d  add     ecx, 1Fh
0x180012ba0  shr     ecx, 6
0x180012ba3  sub     r9d, ecx
0x180012ba6  add     r9d, 0BE00h
0x180012bad  js      loc_180012C66
0x180012bb3  mov     eax, r9d
0x180012bb6  sar     eax, 8
0x180012bb9  cmp     eax, 1AFh
0x180012bbe  jge     loc_180012C75
0x180012bc4  cdqe
0x180012bc6  movzx   edx, word ptr [r14+rax*2]
0x180012bcb  movzx   ecx, word ptr [r14+rax*2+2]
0x180012bd1  sub     ecx, edx
0x180012bd3  movzx   eax, r9b
0x180012bd7  imul    ecx, eax
0x180012bda  add     ecx, 3Fh ; '?'
0x180012bdd  sar     ecx, 7
0x180012be0  lea     r9d, [rcx+rdx*2]
0x180012be4  mov     rax, r8
0x180012be7  shr     rax, 8
0x180012beb  movzx   edx, word ptr [r14+rax*2]
0x180012bf0  movzx   ecx, word ptr [r14+rax*2+2]
0x180012bf6  sub     ecx, edx
0x180012bf8  movzx   eax, r8b
0x180012bfc  imul    ecx, eax
0x180012bff  imul    eax, edi, 7B6Bh
0x180012c05  add     ecx, 3Fh ; '?'
0x180012c08  sar     ecx, 7
0x180012c0b  add     eax, 4000h
0x180012c10  sar     eax, 0Fh
0x180012c13  lea     r8d, [rcx+rdx*2]
0x180012c17  imul    ecx, r9d, 34CBh
0x180012c1e  add     ecx, 2000h
0x180012c24  sar     ecx, 0Eh
0x180012c27  cmp     eax, r15d
0x180012c2a  cmovg   eax, r15d
0x180012c2e  cmp     ecx, r15d
0x180012c31  mov     [rbx], ax
0x180012c34  cmovg   ecx, r15d
0x180012c38  mov     [rbx+2], r8w
0x180012c3d  mov     [rbx+4], cx
0x180012c41  inc     esi
0x180012c43  add     rbx, 6
0x180012c47  cmp     esi, ebp
0x180012c49  jl      loc_180012B40
0x180012c4f  mov     r15, [rsp+38h+arg_10]
0x180012c54  mov     r14, [rsp+38h+arg_8]
0x180012c59  mov     rdi, [rsp+38h+arg_0]
0x180012c5e  add     rsp, 20h
0x180012c62  pop     rsi
0x180012c63  pop     rbp
0x180012c64  pop     rbx
0x180012c65  retn
0x180012c66  xor     r9d, r9d
0x180012c69  jmp     loc_180012BE4
0x180012c6e  xor     edi, edi
0x180012c70  jmp     loc_180012B96
0x180012c75  mov     r9d, 1FFFEh
0x180012c7b  jmp     loc_180012BE4
0x180012c80  mov     edi, 1FFFEh
0x180012c85  jmp     loc_180012B96
```
