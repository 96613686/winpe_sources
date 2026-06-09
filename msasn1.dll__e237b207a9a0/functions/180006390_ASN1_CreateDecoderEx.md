# ASN1_CreateDecoderEx

- ea: `0x180006390`
- end: `0x1800064d8`
- name: `ASN1_CreateDecoderEx`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006390`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064d0`

## pseudocode

```c
__int64 __fastcall ASN1_CreateDecoderEx(__int64 a1, _QWORD *a2, void *a3, unsigned int a4, __int64 a5, char a6)
{
  _OWORD *v6; // rbx
  _OWORD *v11; // rax

  v6 = (_OWORD *)a5;
  if ( a5 && *(_DWORD *)(a5 + 72) > (unsigned int)g_dwMaxRecursionLevel || a3 && a4 > g_dwMaxDecodeBufferSize )
    return 4294966292LL;
  if ( !a1 || !a2 )
    return 4294966287LL;
  *a2 = 0;
  v11 = LocalAlloc(0x40u, 0x70u);
  if ( v11 )
  {
    *v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
    v11[3] = 0;
    v11[4] = 0;
    v11[5] = 0;
    v11[6] = 0;
    *(_DWORD *)v11 = 1145259332;
    *((_DWORD *)v11 + 13) = *(_DWORD *)(a1 + 8);
    *((_QWORD *)v11 + 1) = a1;
    if ( a5 )
    {
      *(_QWORD *)(a5 + 64) = v11;
      *((_QWORD *)v11 + 7) = a5;
      *((_DWORD *)v11 + 12) = *(_DWORD *)(a5 + 48);
      *((_DWORD *)v11 + 18) = *(_DWORD *)(a5 + 72) + 1;
    }
    else
    {
      *((_QWORD *)v11 + 7) = v11;
      v6 = v11;
      *((_DWORD *)v11 + 12) = *(_DWORD *)(a1 + 4);
    }
    if ( a3 )
    {
      *((_DWORD *)v11 + 13) |= 8u;
      *((_QWORD *)v11 + 5) = a3;
      *((_QWORD *)v11 + 2) = a3;
      *((_DWORD *)v11 + 6) = a4;
      if ( (a6 & 0x10) != 0 && !*((_DWORD *)v6 + 19) )
        *((_DWORD *)v11 + 13) |= 0x10u;
    }
    *a2 = v11;
    return 0;
  }
  else
  {
    if ( (a6 & 0x10) != 0 && (!a5 || !*(_DWORD *)(a5 + 76)) )
      LocalFree(a3);
    return 4294966290LL;
  }
}

```

## disassembly

```asm
0x180006390  push    rbx
0x180006392  push    rbp
0x180006393  push    rsi
0x180006394  push    rdi
0x180006395  push    r14
0x180006397  sub     rsp, 20h
0x18000639b  mov     rbx, [rsp+48h+arg_20]
0x1800063a0  mov     r14d, r9d
0x1800063a3  mov     rdi, r8
0x1800063a6  mov     rsi, rdx
0x1800063a9  mov     rbp, rcx
0x1800063ac  test    rbx, rbx
0x1800063af  jz      short loc_1800063C0
0x1800063b1  mov     eax, cs:g_dwMaxRecursionLevel
0x1800063b7  cmp     [rbx+48h], eax
0x1800063ba  ja      loc_180006479
0x1800063c0  test    rdi, rdi
0x1800063c3  jz      short loc_1800063D2
0x1800063c5  cmp     r14d, cs:g_dwMaxDecodeBufferSize
0x1800063cc  ja      loc_180006479
0x1800063d2  test    rbp, rbp
0x1800063d5  jz      loc_180006489
0x1800063db  test    rsi, rsi
0x1800063de  jz      loc_180006489
0x1800063e4  mov     qword ptr [rdx], 0
0x1800063eb  mov     ecx, 40h ; '@'; uFlags
0x1800063f0  mov     edx, 70h ; 'p'; uBytes
0x1800063f5  call    cs:__imp_LocalAlloc
0x1800063fb  test    rax, rax
0x1800063fe  jz      loc_180006490
0x180006404  xorps   xmm0, xmm0
0x180006407  movups  xmmword ptr [rax], xmm0
0x18000640a  movups  xmmword ptr [rax+10h], xmm0
0x18000640e  movups  xmmword ptr [rax+20h], xmm0
0x180006412  movups  xmmword ptr [rax+30h], xmm0
0x180006416  movups  xmmword ptr [rax+40h], xmm0
0x18000641a  movups  xmmword ptr [rax+50h], xmm0
0x18000641e  movups  xmmword ptr [rax+60h], xmm0
0x180006422  mov     dword ptr [rax], 44434544h
0x180006428  mov     ecx, [rbp+8]
0x18000642b  mov     [rax+34h], ecx
0x18000642e  mov     [rax+8], rbp
0x180006432  test    rbx, rbx
0x180006435  jz      short loc_1800064A7
0x180006437  mov     [rbx+40h], rax
0x18000643b  mov     [rax+38h], rbx
0x18000643f  mov     ecx, [rbx+30h]
0x180006442  mov     [rax+30h], ecx
0x180006445  mov     ecx, [rbx+48h]
0x180006448  inc     ecx
0x18000644a  mov     [rax+48h], ecx
0x18000644d  test    rdi, rdi
0x180006450  jz      short loc_180006469
0x180006452  or      dword ptr [rax+34h], 8
0x180006456  test    [rsp+48h+arg_28], 10h
0x18000645b  mov     [rax+28h], rdi
0x18000645f  mov     [rax+10h], rdi
0x180006463  mov     [rax+18h], r14d
0x180006467  jnz     short loc_1800064B6
0x180006469  mov     [rsi], rax
0x18000646c  xor     eax, eax
0x18000646e  add     rsp, 20h
0x180006472  pop     r14
0x180006474  pop     rdi
0x180006475  pop     rsi
0x180006476  pop     rbp
0x180006477  pop     rbx
0x180006478  retn
0x180006479  mov     eax, 0FFFFFC14h
0x18000647e  add     rsp, 20h
0x180006482  pop     r14
0x180006484  pop     rdi
0x180006485  pop     rsi
0x180006486  pop     rbp
0x180006487  pop     rbx
0x180006488  retn
0x180006489  mov     eax, 0FFFFFC0Fh
0x18000648e  jmp     short loc_18000646E
0x180006490  test    [rsp+48h+arg_28], 10h
0x180006495  jnz     short loc_1800064C2
0x180006497  mov     eax, 0FFFFFC12h
0x18000649c  add     rsp, 20h
0x1800064a0  pop     r14
0x1800064a2  pop     rdi
0x1800064a3  pop     rsi
0x1800064a4  pop     rbp
0x1800064a5  pop     rbx
0x1800064a6  retn
0x1800064a7  mov     [rax+38h], rax
0x1800064ab  mov     rbx, rax
0x1800064ae  mov     ecx, [rbp+4]
0x1800064b1  mov     [rax+30h], ecx
0x1800064b4  jmp     short loc_18000644D
0x1800064b6  cmp     dword ptr [rbx+4Ch], 0
0x1800064ba  jnz     short loc_180006469
0x1800064bc  or      dword ptr [rax+34h], 10h
0x1800064c0  jmp     short loc_180006469
0x1800064c2  test    rbx, rbx
0x1800064c5  jz      short loc_1800064CD
0x1800064c7  cmp     dword ptr [rbx+4Ch], 0
0x1800064cb  jnz     short loc_180006497
0x1800064cd  mov     rcx, rdi; hMem
0x1800064d0  call    cs:__imp_LocalFree
0x1800064d6  jmp     short loc_180006497
```
