# ASN1_CreateDecoder

- ea: `0x1800064e0`
- end: `0x1800065f5`
- name: `ASN1_CreateDecoder`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800064e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006545`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006545`

## pseudocode

```c
__int64 __fastcall ASN1_CreateDecoder(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4, __int64 a5)
{
  _OWORD *v9; // rax

  if ( a5 && *(_DWORD *)(a5 + 72) > (unsigned int)g_dwMaxRecursionLevel || a3 && a4 > g_dwMaxDecodeBufferSize )
    return 4294966292LL;
  if ( !a1 || !a2 )
    return 4294966287LL;
  *a2 = 0;
  v9 = LocalAlloc(0x40u, 0x70u);
  if ( !v9 )
    return 4294966290LL;
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  v9[3] = 0;
  v9[4] = 0;
  v9[5] = 0;
  v9[6] = 0;
  *(_DWORD *)v9 = 1145259332;
  *((_DWORD *)v9 + 13) = *(_DWORD *)(a1 + 8);
  *((_QWORD *)v9 + 1) = a1;
  if ( a5 )
  {
    *(_QWORD *)(a5 + 64) = v9;
    *((_QWORD *)v9 + 7) = a5;
    *((_DWORD *)v9 + 12) = *(_DWORD *)(a5 + 48);
    *((_DWORD *)v9 + 18) = *(_DWORD *)(a5 + 72) + 1;
  }
  else
  {
    *((_QWORD *)v9 + 7) = v9;
    *((_DWORD *)v9 + 12) = *(_DWORD *)(a1 + 4);
  }
  if ( a3 )
  {
    *((_DWORD *)v9 + 13) |= 8u;
    *((_QWORD *)v9 + 5) = a3;
    *((_QWORD *)v9 + 2) = a3;
    *((_DWORD *)v9 + 6) = a4;
  }
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x1800064e0  push    rbx
0x1800064e2  push    rbp
0x1800064e3  push    rsi
0x1800064e4  push    rdi
0x1800064e5  push    r14
0x1800064e7  sub     rsp, 20h
0x1800064eb  mov     rbx, [rsp+48h+arg_20]
0x1800064f0  mov     r14d, r9d
0x1800064f3  mov     rdi, r8
0x1800064f6  mov     rsi, rdx
0x1800064f9  mov     rbp, rcx
0x1800064fc  test    rbx, rbx
0x1800064ff  jz      short loc_180006510
0x180006501  mov     eax, cs:g_dwMaxRecursionLevel
0x180006507  cmp     [rbx+48h], eax
0x18000650a  ja      loc_1800065C2
0x180006510  test    rdi, rdi
0x180006513  jz      short loc_180006522
0x180006515  cmp     r14d, cs:g_dwMaxDecodeBufferSize
0x18000651c  ja      loc_1800065C2
0x180006522  test    rbp, rbp
0x180006525  jz      loc_1800065D2
0x18000652b  test    rsi, rsi
0x18000652e  jz      loc_1800065D2
0x180006534  mov     qword ptr [rdx], 0
0x18000653b  mov     ecx, 40h ; '@'; uFlags
0x180006540  mov     edx, 70h ; 'p'; uBytes
0x180006545  call    cs:__imp_LocalAlloc
0x18000654b  test    rax, rax
0x18000654e  jz      loc_1800065D9
0x180006554  xorps   xmm0, xmm0
0x180006557  movups  xmmword ptr [rax], xmm0
0x18000655a  movups  xmmword ptr [rax+10h], xmm0
0x18000655e  movups  xmmword ptr [rax+20h], xmm0
0x180006562  movups  xmmword ptr [rax+30h], xmm0
0x180006566  movups  xmmword ptr [rax+40h], xmm0
0x18000656a  movups  xmmword ptr [rax+50h], xmm0
0x18000656e  movups  xmmword ptr [rax+60h], xmm0
0x180006572  mov     dword ptr [rax], 44434544h
0x180006578  mov     ecx, [rbp+8]
0x18000657b  mov     [rax+34h], ecx
0x18000657e  mov     [rax+8], rbp
0x180006582  test    rbx, rbx
0x180006585  jz      short loc_1800065E9
0x180006587  mov     [rbx+40h], rax
0x18000658b  mov     [rax+38h], rbx
0x18000658f  mov     ecx, [rbx+30h]
0x180006592  mov     [rax+30h], ecx
0x180006595  mov     ecx, [rbx+48h]
0x180006598  inc     ecx
0x18000659a  mov     [rax+48h], ecx
0x18000659d  test    rdi, rdi
0x1800065a0  jz      short loc_1800065B2
0x1800065a2  or      dword ptr [rax+34h], 8
0x1800065a6  mov     [rax+28h], rdi
0x1800065aa  mov     [rax+10h], rdi
0x1800065ae  mov     [rax+18h], r14d
0x1800065b2  mov     [rsi], rax
0x1800065b5  xor     eax, eax
0x1800065b7  add     rsp, 20h
0x1800065bb  pop     r14
0x1800065bd  pop     rdi
0x1800065be  pop     rsi
0x1800065bf  pop     rbp
0x1800065c0  pop     rbx
0x1800065c1  retn
0x1800065c2  mov     eax, 0FFFFFC14h
0x1800065c7  add     rsp, 20h
0x1800065cb  pop     r14
0x1800065cd  pop     rdi
0x1800065ce  pop     rsi
0x1800065cf  pop     rbp
0x1800065d0  pop     rbx
0x1800065d1  retn
0x1800065d2  mov     eax, 0FFFFFC0Fh
0x1800065d7  jmp     short loc_1800065B7
0x1800065d9  mov     eax, 0FFFFFC12h
0x1800065de  add     rsp, 20h
0x1800065e2  pop     r14
0x1800065e4  pop     rdi
0x1800065e5  pop     rsi
0x1800065e6  pop     rbp
0x1800065e7  pop     rbx
0x1800065e8  retn
0x1800065e9  mov     [rax+38h], rax
0x1800065ed  mov     ecx, [rbp+4]
0x1800065f0  mov     [rax+30h], ecx
0x1800065f3  jmp     short loc_18000659D
```
