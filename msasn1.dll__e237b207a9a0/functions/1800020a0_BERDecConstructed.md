# _BERDecConstructed

- ea: `0x1800020a0`
- end: `0x1800021f1`
- name: `_BERDecConstructed`
- size: `337`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001f80`
- `0x1800026b0`
- `0x180002c20`
- `0x180003270`
- `0x180003be0`
- `0x180004a60`
- `0x180005300`
- `0x180009c10`

## callees

- `0x1800020a0`
- `0x180004310`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002117`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002117`

## pseudocode

```c
__int64 __fastcall BERDecConstructed(__int64 a1, unsigned int a2, int a3, __int64 *a4, unsigned __int64 *a5)
{
  unsigned __int64 v6; // rbp
  __int64 v10; // r15
  char *v11; // rax
  unsigned __int64 *v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 v15; // r14
  unsigned int v16; // ecx

  *a4 = a1;
  v6 = *(_QWORD *)(a1 + 40);
  if ( a3 )
  {
    v15 = *(_QWORD *)(a1 + 16);
    if ( v6 < v15 || (v16 = *(_DWORD *)(a1 + 24), (int)v6 - (int)v15 > v16) )
    {
      ASN1DecSetError(a1, 0xFFFFFC17);
      return 0;
    }
    a2 = v16 + v15 - v6;
  }
  if ( a1 && *(_DWORD *)(a1 + 72) > (unsigned int)g_dwMaxRecursionLevel )
    return 0;
  if ( v6 && a2 > g_dwMaxDecodeBufferSize )
    return 0;
  v10 = *(_QWORD *)(a1 + 8);
  if ( !v10 )
    return 0;
  *a4 = 0;
  v11 = (char *)LocalAlloc(0x40u, 0x70u);
  if ( !v11 )
    return 0;
  v12 = (unsigned __int64 *)(v11 + 16);
  *(_OWORD *)v11 = 0;
  *((_OWORD *)v11 + 1) = 0;
  *((_OWORD *)v11 + 2) = 0;
  *((_OWORD *)v11 + 3) = 0;
  *((_OWORD *)v11 + 4) = 0;
  *((_OWORD *)v11 + 5) = 0;
  *((_OWORD *)v11 + 6) = 0;
  *(_DWORD *)v11 = 1145259332;
  *((_DWORD *)v11 + 13) = *(_DWORD *)(v10 + 8);
  *((_QWORD *)v11 + 1) = v10;
  *(_QWORD *)(a1 + 64) = v11;
  *((_QWORD *)v11 + 7) = a1;
  *((_DWORD *)v11 + 12) = *(_DWORD *)(a1 + 48);
  *((_DWORD *)v11 + 18) = *(_DWORD *)(a1 + 72) + 1;
  if ( v6 )
  {
    *((_DWORD *)v11 + 13) |= 8u;
    *((_QWORD *)v11 + 5) = v6;
    *v12 = v6;
    *((_DWORD *)v11 + 6) = a2;
  }
  *a4 = (__int64)v11;
  if ( a3 )
    v13 = 0;
  else
    v13 = *v12 + *((unsigned int *)v11 + 6);
  *a5 = v13;
  return 1;
}

```

## disassembly

```asm
0x1800020a0  mov     [rsp+arg_8], rbx
0x1800020a5  mov     [rsp+arg_10], rbp
0x1800020aa  push    rsi
0x1800020ab  push    rdi
0x1800020ac  push    r14
0x1800020ae  sub     rsp, 20h
0x1800020b2  mov     [r9], rcx
0x1800020b5  mov     rdi, r9
0x1800020b8  mov     rbp, [rcx+28h]
0x1800020bc  mov     esi, r8d
0x1800020bf  mov     rbx, rcx
0x1800020c2  test    r8d, r8d
0x1800020c5  jnz     loc_1800021BC
0x1800020cb  mov     r14d, edx
0x1800020ce  mov     [rsp+38h+arg_0], r15
0x1800020d3  test    rbx, rbx
0x1800020d6  jz      short loc_1800020E7
0x1800020d8  mov     eax, cs:g_dwMaxRecursionLevel
0x1800020de  cmp     [rbx+48h], eax
0x1800020e1  ja      loc_1800021B8
0x1800020e7  test    rbp, rbp
0x1800020ea  jz      short loc_1800020F9
0x1800020ec  cmp     r14d, cs:g_dwMaxDecodeBufferSize
0x1800020f3  ja      loc_1800021B8
0x1800020f9  mov     r15, [rbx+8]
0x1800020fd  test    r15, r15
0x180002100  jz      loc_1800021B8
0x180002106  mov     edx, 70h ; 'p'; uBytes
0x18000210b  mov     qword ptr [r9], 0
0x180002112  mov     ecx, 40h ; '@'; uFlags
0x180002117  call    cs:__imp_LocalAlloc
0x18000211d  mov     rcx, rax
0x180002120  test    rax, rax
0x180002123  jz      loc_1800021B8
0x180002129  xorps   xmm0, xmm0
0x18000212c  lea     rdx, [rcx+10h]
0x180002130  movups  xmmword ptr [rax], xmm0
0x180002133  movups  xmmword ptr [rax+10h], xmm0
0x180002137  movups  xmmword ptr [rax+20h], xmm0
0x18000213b  movups  xmmword ptr [rax+30h], xmm0
0x18000213f  movups  xmmword ptr [rax+40h], xmm0
0x180002143  movups  xmmword ptr [rax+50h], xmm0
0x180002147  movups  xmmword ptr [rax+60h], xmm0
0x18000214b  mov     dword ptr [rax], 44434544h
0x180002151  mov     eax, [r15+8]
0x180002155  mov     [rcx+34h], eax
0x180002158  mov     [rcx+8], r15
0x18000215c  mov     [rbx+40h], rcx
0x180002160  mov     [rcx+38h], rbx
0x180002164  mov     eax, [rbx+30h]
0x180002167  mov     [rcx+30h], eax
0x18000216a  mov     eax, [rbx+48h]
0x18000216d  inc     eax
0x18000216f  mov     [rcx+48h], eax
0x180002172  test    rbp, rbp
0x180002175  jz      short loc_180002186
0x180002177  or      dword ptr [rcx+34h], 8
0x18000217b  mov     [rcx+28h], rbp
0x18000217f  mov     [rdx], rbp
0x180002182  mov     [rcx+18h], r14d
0x180002186  mov     [rdi], rcx
0x180002189  test    esi, esi
0x18000218b  jnz     short loc_1800021DC
0x18000218d  mov     ecx, [rcx+18h]
0x180002190  add     rcx, [rdx]
0x180002193  mov     rax, [rsp+38h+arg_20]
0x180002198  mov     [rax], rcx
0x18000219b  mov     eax, 1
0x1800021a0  mov     r15, [rsp+38h+arg_0]
0x1800021a5  mov     rbx, [rsp+38h+arg_8]
0x1800021aa  mov     rbp, [rsp+38h+arg_10]
0x1800021af  add     rsp, 20h
0x1800021b3  pop     r14
0x1800021b5  pop     rdi
0x1800021b6  pop     rsi
0x1800021b7  retn
0x1800021b8  xor     eax, eax
0x1800021ba  jmp     short loc_1800021A0
0x1800021bc  mov     r14, [rcx+10h]
0x1800021c0  cmp     rbp, r14
0x1800021c3  jb      short loc_1800021E0
0x1800021c5  mov     ecx, [rcx+18h]
0x1800021c8  mov     eax, ebp
0x1800021ca  sub     eax, r14d
0x1800021cd  cmp     eax, ecx
0x1800021cf  ja      short loc_1800021E0
0x1800021d1  sub     r14d, ebp
0x1800021d4  add     r14d, ecx
0x1800021d7  jmp     loc_1800020CE
0x1800021dc  xor     ecx, ecx
0x1800021de  jmp     short loc_180002193
0x1800021e0  mov     edx, 0FFFFFC17h
0x1800021e5  mov     rcx, rbx
0x1800021e8  call    ASN1DecSetError
0x1800021ed  xor     eax, eax
0x1800021ef  jmp     short loc_1800021A5
```
