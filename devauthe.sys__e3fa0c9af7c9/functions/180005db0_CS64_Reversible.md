# CS64_Reversible

- ea: `0x180005db0`
- end: `0x180005f73`
- name: `CS64_Reversible`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f7c`

## callees

- `0x180005db0`

## pseudocode

```c
__int64 __fastcall CS64_Reversible(_DWORD *a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  int v5; // r11d
  int v6; // ebx
  int v7; // r9d
  int v8; // r8d
  unsigned int v10; // edi
  int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  int v14; // r9d
  unsigned int v15; // edx
  unsigned int v16; // r8d
  int v17; // ecx
  __int64 result; // rax
  unsigned int v19; // edx
  unsigned int v20; // edx
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // r8d
  int v24; // ecx

  v5 = *a3 | 1;
  v6 = a3[1] | 1;
  v7 = 0;
  v8 = 0;
  v10 = 8;
  do
  {
    v10 -= 2;
    v11 = v8 + *a1;
    a1 += 2;
    v12 = 2147025057 * ((unsigned int)(v5 * v11) >> 16) + 10551296 * v5 * v11;
    v13 = -892141568
        * (1338048512 * (849281024 * v12 - 275762529 * HIWORD(v12))
         - 2147266623 * ((849281024 * v12 - 275762529 * HIWORD(v12)) >> 16))
        - 1800680749
        * ((1338048512 * (849281024 * v12 - 275762529 * HIWORD(v12))
          - 2147266623 * ((849281024 * v12 - 275762529 * HIWORD(v12)) >> 16)) >> 16);
    v14 = v13 + v7;
    v15 = 858718208 * v6 * (v13 + *(a1 - 1)) + 313209647 * ((v6 * (v13 + *(a1 - 1))) >> 16);
    v16 = 180998117 * HIWORD(v15) - 807075840 * v15;
    v17 = 1971177561 * HIWORD(v16);
    result = 1072889856 * (933691392 * v16 - v17);
    v8 = 1787805709 * ((933691392 * v16 - v17) >> 16) - result;
    v7 = v8 + v14;
  }
  while ( v10 > 1 );
  if ( v10 == 1 )
  {
    v19 = 2147025057 * ((unsigned int)(v5 * (v8 + *a1)) >> 16) + 10551296 * v5 * (v8 + *a1);
    v20 = 1338048512 * (849281024 * v19 - 275762529 * HIWORD(v19))
        - 2147266623 * ((849281024 * v19 - 275762529 * HIWORD(v19)) >> 16);
    v21 = -892141568 * v20 - 1800680749 * HIWORD(v20);
    v22 = v21 + v7;
    v23 = 180998117 * ((858718208 * v6 * v21 + 313209647 * ((unsigned int)(v6 * v21) >> 16)) >> 16)
        - 807075840 * (858718208 * v6 * v21 + 313209647 * ((unsigned int)(v6 * v21) >> 16));
    v24 = 1971177561 * HIWORD(v23);
    result = 1072889856 * (933691392 * v23 - v24);
    v8 = 1787805709 * ((933691392 * v23 - v24) >> 16) - result;
    v7 = v8 + v22;
  }
  *a4 = v8;
  a4[1] = v7;
  return result;
}

```

## disassembly

```asm
0x180005db0  push    rbx
0x180005db2  push    rsi
0x180005db3  push    rdi
0x180005db4  mov     r11d, [r8]
0x180005db7  mov     r10, r9
0x180005dba  mov     ebx, [r8+4]
0x180005dbe  or      r11d, 1
0x180005dc2  or      ebx, 1
0x180005dc5  xor     r9d, r9d
0x180005dc8  xor     r8d, r8d
0x180005dcb  mov     rsi, rcx
0x180005dce  mov     edi, 8
0x180005dd3  mov     edx, [rsi]
0x180005dd5  add     edi, 0FFFFFFFEh
0x180005dd8  add     edx, r8d
0x180005ddb  lea     rsi, [rsi+8]
0x180005ddf  mov     eax, edx
0x180005de1  imul    edx, r11d
0x180005de5  imul    eax, r11d
0x180005de9  imul    edx, 0A10000h
0x180005def  shr     eax, 10h
0x180005df2  imul    ecx, eax, 7FF900A1h
0x180005df8  add     edx, ecx
0x180005dfa  imul    r8d, edx, 329F0000h
0x180005e01  mov     eax, edx
0x180005e03  shr     eax, 10h
0x180005e06  imul    ecx, eax, 106FCD61h
0x180005e0c  sub     r8d, ecx
0x180005e0f  imul    edx, r8d, 4FC10000h
0x180005e16  mov     eax, r8d
0x180005e19  mov     r8d, [rsi-4]
0x180005e1d  shr     eax, 10h
0x180005e20  imul    ecx, eax, 7FFCB03Fh
0x180005e26  sub     edx, ecx
0x180005e28  mov     eax, edx
0x180005e2a  imul    edx, 0CAD30000h
0x180005e30  shr     eax, 10h
0x180005e33  imul    ecx, eax, 6B54352Dh
0x180005e39  sub     edx, ecx
0x180005e3b  add     r8d, edx
0x180005e3e  add     r9d, edx
0x180005e41  mov     eax, r8d
0x180005e44  imul    r8d, ebx
0x180005e48  imul    eax, ebx
0x180005e4b  shr     eax, 10h
0x180005e4e  imul    edx, eax, 12AB332Fh
0x180005e54  imul    eax, r8d, 332F0000h
0x180005e5b  add     edx, eax
0x180005e5d  mov     eax, edx
0x180005e5f  shr     eax, 10h
0x180005e62  imul    r8d, eax, 0AC9CFE5h
0x180005e69  imul    eax, edx, 301B0000h
0x180005e6f  sub     r8d, eax
0x180005e72  imul    edx, r8d, 37A70000h
0x180005e79  mov     eax, r8d
0x180005e7c  shr     eax, 10h
0x180005e7f  imul    ecx, eax, 757DC859h
0x180005e85  sub     edx, ecx
0x180005e87  mov     eax, edx
0x180005e89  shr     eax, 10h
0x180005e8c  imul    r8d, eax, 6A8FC00Dh
0x180005e93  imul    eax, edx, 3FF30000h
0x180005e99  sub     r8d, eax
0x180005e9c  add     r9d, r8d
0x180005e9f  cmp     edi, 1
0x180005ea2  ja      loc_180005DD3
0x180005ea8  jnz     loc_180005F67
0x180005eae  mov     edx, [rsi]
0x180005eb0  add     edx, r8d
0x180005eb3  imul    edx, r11d
0x180005eb7  mov     eax, edx
0x180005eb9  imul    edx, 0A10000h
0x180005ebf  shr     eax, 10h
0x180005ec2  imul    ecx, eax, 7FF900A1h
0x180005ec8  add     edx, ecx
0x180005eca  imul    r8d, edx, 329F0000h
0x180005ed1  mov     eax, edx
0x180005ed3  shr     eax, 10h
0x180005ed6  imul    ecx, eax, 106FCD61h
0x180005edc  sub     r8d, ecx
0x180005edf  imul    edx, r8d, 4FC10000h
0x180005ee6  mov     eax, r8d
0x180005ee9  shr     eax, 10h
0x180005eec  imul    ecx, eax, 7FFCB03Fh
0x180005ef2  sub     edx, ecx
0x180005ef4  imul    r8d, edx, 0CAD30000h
0x180005efb  mov     eax, edx
0x180005efd  shr     eax, 10h
0x180005f00  imul    ecx, eax, 6B54352Dh
0x180005f06  sub     r8d, ecx
0x180005f09  add     r9d, r8d
0x180005f0c  imul    r8d, ebx
0x180005f10  mov     eax, r8d
0x180005f13  shr     eax, 10h
0x180005f16  imul    edx, eax, 12AB332Fh
0x180005f1c  imul    eax, r8d, 332F0000h
0x180005f23  add     edx, eax
0x180005f25  mov     eax, edx
0x180005f27  shr     eax, 10h
0x180005f2a  imul    r8d, eax, 0AC9CFE5h
0x180005f31  imul    eax, edx, 301B0000h
0x180005f37  sub     r8d, eax
0x180005f3a  imul    edx, r8d, 37A70000h
0x180005f41  mov     eax, r8d
0x180005f44  shr     eax, 10h
0x180005f47  imul    ecx, eax, 757DC859h
0x180005f4d  sub     edx, ecx
0x180005f4f  mov     eax, edx
0x180005f51  shr     eax, 10h
0x180005f54  imul    r8d, eax, 6A8FC00Dh
0x180005f5b  imul    eax, edx, 3FF30000h
0x180005f61  sub     r8d, eax
0x180005f64  add     r9d, r8d
0x180005f67  mov     [r10], r8d
0x180005f6a  mov     [r10+4], r9d
0x180005f6e  pop     rdi
0x180005f6f  pop     rsi
0x180005f70  pop     rbx
0x180005f71  retn
```
