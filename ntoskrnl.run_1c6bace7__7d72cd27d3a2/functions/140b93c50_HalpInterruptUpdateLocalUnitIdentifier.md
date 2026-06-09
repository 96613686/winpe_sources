# HalpInterruptUpdateLocalUnitIdentifier

- ea: `0x140b93c50`
- end: `0x140b93eb8`
- name: `HalpInterruptUpdateLocalUnitIdentifier`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140b939a8`

## callees

- `0x1403a2480`
- `0x1403a8678`
- `0x1406eb0e0`
- `0x140b93c50`

## string_xrefs

- `0x140b93d22`: `minkernel\hals\lib\interrupts\common\replace.c`
- `0x140b93d90`: `minkernel\hals\lib\interrupts\common\replace.c`
- `0x140b93e85`: `minkernel\hals\lib\interrupts\common\replace.c`

## pseudocode

```c
__int64 __fastcall HalpInterruptUpdateLocalUnitIdentifier(int a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int i; // eax
  unsigned __int64 v9; // r9
  char v10; // al
  unsigned __int64 v11; // rdx
  ULONG ProcessorIndexFromNumber; // eax
  __int64 v13; // rcx
  __int64 v14; // r14
  int v15; // r8d
  unsigned int v16; // r8d
  __int64 v18; // rcx
  unsigned int j; // eax
  unsigned __int64 v20; // rcx
  int v21; // r9d
  const char *v22; // r11
  unsigned __int64 k; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned __int64 m; // rdx
  __int64 v27; // rax
  int v28; // [rsp+58h] [rbp+10h] BYREF

  v28 = a2;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)HalpInterruptProcessorCount )
    {
      HalpInterruptSetProblemEx(0, 21, 0, a1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\replace.c", 1020);
      return 3221226021LL;
    }
    v9 = (unsigned __int64)i << 6;
    if ( *(_DWORD *)(v9 + HalpInterruptProcessorState) == a1 )
      break;
  }
  v10 = *(_BYTE *)(v9 + HalpInterruptProcessorState + 13);
  v11 = v9 + HalpInterruptProcessorState + 16;
  *(_DWORD *)(v9 + HalpInterruptProcessorState) = a2;
  ProcessorIndexFromNumber = KeGetProcessorIndexFromNumber((PPROCESSOR_NUMBER)(v11 & -(__int64)(v10 != 0)));
  v13 = HalpInterruptTargets;
  v14 = ProcessorIndexFromNumber;
  *(_DWORD *)(HalpInterruptLocalIds + 4LL * ProcessorIndexFromNumber) = a2;
  *(_OWORD *)a3 = *(_OWORD *)(v13 + 24LL * ProcessorIndexFromNumber);
  *(_QWORD *)(a3 + 16) = *(_QWORD *)(v13 + 24LL * ProcessorIndexFromNumber + 16);
  if ( *(_DWORD *)(v13 + 24LL * ProcessorIndexFromNumber) == 4 )
    *(_DWORD *)(v13 + 24LL * ProcessorIndexFromNumber + 8) = v28;
  if ( *(_QWORD *)(HalpInterruptController + 144) )
  {
    v15 = guard_dispatch_icall_no_overrides(*(_QWORD *)(HalpInterruptController + 16), &v28, a4);
    if ( v15 < 0 )
    {
      HalpInterruptSetProblemEx(
        HalpInterruptController,
        9,
        v15,
        -1,
        (__int64)"minkernel\\hals\\lib\\interrupts\\common\\replace.c",
        1057);
      return v16;
    }
    v18 = HalpInterruptTargets;
    *(_OWORD *)(HalpInterruptTargets + 24 * v14) = *(_OWORD *)a4;
    *(_QWORD *)(v18 + 24 * v14 + 16) = *(_QWORD *)(a4 + 16);
  }
  for ( j = 0; j < HalpInterruptDynamicProcessorCount; ++j )
  {
    v20 = (unsigned __int64)j << 6;
    if ( *(_DWORD *)(v20 + HalpInterruptDynamicProcessorState) == a1 )
    {
      *(_DWORD *)(v20 + HalpInterruptDynamicProcessorState) = v28;
      break;
    }
  }
  v21 = -1;
  v22 = "minkernel\\hals\\lib\\interrupts\\common\\replace.c";
  if ( *(_DWORD *)a3 == 6 )
  {
    for ( k = HalpInterruptClusterData; ; k += 24LL )
    {
      if ( k >= HalpInterruptClusterDataEnd )
      {
        HalpInterruptSetProblemEx(0, 29, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\replace.c", 1112);
        goto LABEL_24;
      }
      if ( *(_DWORD *)k == *(_DWORD *)(a3 + 8) )
        break;
    }
    v24 = *(_QWORD *)(k + 8) & ~(1LL << (*((_BYTE *)qword_140F218A8 + 4 * v14) & 0x3F));
    *(_QWORD *)(k + 8) = v24;
    if ( !v24 )
      *(_DWORD *)k = -1;
  }
LABEL_24:
  v25 = HalpInterruptTargets;
  *(_OWORD *)a4 = *(_OWORD *)(HalpInterruptTargets + 24 * v14);
  *(_QWORD *)(a4 + 16) = *(_QWORD *)(v25 + 24 * v14 + 16);
  if ( *(_DWORD *)a4 == 6 )
  {
    for ( m = HalpInterruptClusterData; m < HalpInterruptClusterDataEnd; m += 24LL )
    {
      if ( *(_DWORD *)m == v21 || *(_DWORD *)m == *(_DWORD *)(a4 + 8) )
      {
        *(_DWORD *)m = *(_DWORD *)(a4 + 8);
        v27 = *(_QWORD *)(m + 8);
        _bittestandset64(&v27, *((_DWORD *)qword_140F218A8 + v14) & 0x3F);
        *(_QWORD *)(m + 8) = v27;
        return 0;
      }
    }
    HalpInterruptSetProblemEx(0, 29, 0, v21, (__int64)v22, 1147);
  }
  return 0;
}

```

## disassembly

```asm
0x140b93c50  mov     [rsp+arg_0], rbx
0x140b93c55  mov     [rsp+arg_10], rbp
0x140b93c5a  mov     [rsp+arg_8], edx
0x140b93c5e  push    rsi
0x140b93c5f  push    rdi
0x140b93c60  push    r14
0x140b93c62  sub     rsp, 30h
0x140b93c66  mov     rbx, r9
0x140b93c69  mov     rbp, r8
0x140b93c6c  mov     edi, edx
0x140b93c6e  mov     esi, ecx
0x140b93c70  xor     eax, eax
0x140b93c72  cmp     eax, cs:HalpInterruptProcessorCount
0x140b93c78  jnb     loc_140B93E7A
0x140b93c7e  mov     r8, cs:HalpInterruptProcessorState
0x140b93c85  mov     r9d, eax
0x140b93c88  shl     r9, 6
0x140b93c8c  cmp     [r9+r8], esi
0x140b93c90  jz      short loc_140B93C96
0x140b93c92  inc     eax
0x140b93c94  jmp     short loc_140B93C72
0x140b93c96  mov     al, [r9+r8+0Dh]
0x140b93c9b  lea     rdx, [r8+10h]
0x140b93c9f  add     rdx, r9
0x140b93ca2  mov     [r9+r8], edi
0x140b93ca6  neg     al
0x140b93ca8  sbb     rcx, rcx
0x140b93cab  and     rcx, rdx; ProcNumber
0x140b93cae  call    KeGetProcessorIndexFromNumber
0x140b93cb3  mov     rcx, cs:HalpInterruptTargets
0x140b93cba  mov     r14d, eax
0x140b93cbd  mov     rax, cs:HalpInterruptLocalIds
0x140b93cc4  mov     [rax+r14*4], edi
0x140b93cc8  lea     rdi, [r14+r14*2]
0x140b93ccc  movups  xmm0, xmmword ptr [rcx+rdi*8]
0x140b93cd0  movups  xmmword ptr [rbp+0], xmm0
0x140b93cd4  movsd   xmm1, qword ptr [rcx+rdi*8+10h]
0x140b93cda  movsd   qword ptr [rbp+10h], xmm1
0x140b93cdf  cmp     dword ptr [rcx+rdi*8], 4
0x140b93ce3  jnz     short loc_140B93CED
0x140b93ce5  mov     eax, [rsp+48h+arg_8]
0x140b93ce9  mov     [rcx+rdi*8+8], eax
0x140b93ced  mov     rcx, cs:HalpInterruptController
0x140b93cf4  mov     rax, [rcx+90h]
0x140b93cfb  test    rax, rax
0x140b93cfe  jz      short loc_140B93D65
0x140b93d00  mov     rcx, [rcx+10h]
0x140b93d04  lea     rdx, [rsp+48h+arg_8]
0x140b93d09  mov     r9b, 1
0x140b93d0c  mov     r8, rbx
0x140b93d0f  call    _guard_dispatch_icall_no_overrides
0x140b93d14  mov     r8d, eax
0x140b93d17  test    eax, eax
0x140b93d19  jns     short loc_140B93D4C
0x140b93d1b  mov     rcx, cs:HalpInterruptController
0x140b93d22  lea     r11, aMinkernelHalsL_2; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140b93d29  mov     [rsp+48h+var_20], 421h
0x140b93d31  or      r9d, 0FFFFFFFFh
0x140b93d35  mov     edx, 9
0x140b93d3a  mov     [rsp+48h+var_28], r11
0x140b93d3f  call    HalpInterruptSetProblemEx
0x140b93d44  mov     eax, r8d
0x140b93d47  jmp     loc_140B93EA4
0x140b93d4c  mov     rcx, cs:HalpInterruptTargets
0x140b93d53  movups  xmm0, xmmword ptr [rbx]
0x140b93d56  movups  xmmword ptr [rcx+rdi*8], xmm0
0x140b93d5a  movsd   xmm1, qword ptr [rbx+10h]
0x140b93d5f  movsd   qword ptr [rcx+rdi*8+10h], xmm1
0x140b93d65  xor     eax, eax
0x140b93d67  cmp     eax, cs:HalpInterruptDynamicProcessorCount
0x140b93d6d  jnb     short loc_140B93D8C
0x140b93d6f  mov     rdx, cs:HalpInterruptDynamicProcessorState
0x140b93d76  mov     ecx, eax
0x140b93d78  shl     rcx, 6
0x140b93d7c  cmp     [rcx+rdx], esi
0x140b93d7f  jz      short loc_140B93D85
0x140b93d81  inc     eax
0x140b93d83  jmp     short loc_140B93D67
0x140b93d85  mov     eax, [rsp+48h+arg_8]
0x140b93d89  mov     [rcx+rdx], eax
0x140b93d8c  or      r9d, 0FFFFFFFFh
0x140b93d90  lea     r11, aMinkernelHalsL_2; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140b93d97  cmp     dword ptr [rbp+0], 6
0x140b93d9b  mov     esi, 1Dh
0x140b93da0  jnz     short loc_140B93DFC
0x140b93da2  mov     rdx, cs:HalpInterruptClusterData
0x140b93da9  cmp     rdx, cs:HalpInterruptClusterDataEnd
0x140b93db0  jnb     short loc_140B93DE3
0x140b93db2  mov     eax, [rbp+8]
0x140b93db5  cmp     [rdx], eax
0x140b93db7  jz      short loc_140B93DBF
0x140b93db9  add     rdx, 18h
0x140b93dbd  jmp     short loc_140B93DA9
0x140b93dbf  mov     rax, cs:qword_140F218A8
0x140b93dc6  mov     ecx, [rax+r14*4]
0x140b93dca  mov     rax, [rdx+8]
0x140b93dce  and     ecx, 3Fh
0x140b93dd1  btr     rax, rcx
0x140b93dd5  mov     [rdx+8], rax
0x140b93dd9  test    rax, rax
0x140b93ddc  jnz     short loc_140B93DFC
0x140b93dde  mov     [rdx], r9d
0x140b93de1  jmp     short loc_140B93DFC
0x140b93de3  mov     [rsp+48h+var_20], 458h
0x140b93deb  xor     r8d, r8d
0x140b93dee  mov     edx, esi
0x140b93df0  mov     [rsp+48h+var_28], r11
0x140b93df5  xor     ecx, ecx
0x140b93df7  call    HalpInterruptSetProblemEx
0x140b93dfc  mov     rax, cs:HalpInterruptTargets
0x140b93e03  movups  xmm0, xmmword ptr [rax+rdi*8]
0x140b93e07  movups  xmmword ptr [rbx], xmm0
0x140b93e0a  movsd   xmm1, qword ptr [rax+rdi*8+10h]
0x140b93e10  movsd   qword ptr [rbx+10h], xmm1
0x140b93e15  cmp     dword ptr [rbx], 6
0x140b93e18  jnz     short loc_140B93E76
0x140b93e1a  mov     rdx, cs:HalpInterruptClusterData
0x140b93e21  cmp     rdx, cs:HalpInterruptClusterDataEnd
0x140b93e28  jnb     short loc_140B93E5D
0x140b93e2a  mov     eax, [rdx]
0x140b93e2c  cmp     eax, r9d
0x140b93e2f  jz      short loc_140B93E3C
0x140b93e31  cmp     eax, [rbx+8]
0x140b93e34  jz      short loc_140B93E3C
0x140b93e36  add     rdx, 18h
0x140b93e3a  jmp     short loc_140B93E21
0x140b93e3c  mov     eax, [rbx+8]
0x140b93e3f  mov     [rdx], eax
0x140b93e41  mov     rax, cs:qword_140F218A8
0x140b93e48  mov     ecx, [rax+r14*4]
0x140b93e4c  mov     rax, [rdx+8]
0x140b93e50  and     ecx, 3Fh
0x140b93e53  bts     rax, rcx
0x140b93e57  mov     [rdx+8], rax
0x140b93e5b  jmp     short loc_140B93E76
0x140b93e5d  mov     [rsp+48h+var_20], 47Bh
0x140b93e65  xor     r8d, r8d
0x140b93e68  mov     edx, esi
0x140b93e6a  mov     [rsp+48h+var_28], r11
0x140b93e6f  xor     ecx, ecx
0x140b93e71  call    HalpInterruptSetProblemEx
0x140b93e76  xor     eax, eax
0x140b93e78  jmp     short loc_140B93EA4
0x140b93e7a  xor     r8d, r8d
0x140b93e7d  mov     [rsp+48h+var_20], 3FCh
0x140b93e85  lea     r11, aMinkernelHalsL_2; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140b93e8c  mov     r9d, esi
0x140b93e8f  xor     ecx, ecx
0x140b93e91  mov     [rsp+48h+var_28], r11
0x140b93e96  lea     edx, [r8+15h]
0x140b93e9a  call    HalpInterruptSetProblemEx
0x140b93e9f  mov     eax, 0C0000225h
0x140b93ea4  mov     rbx, [rsp+48h+arg_0]
0x140b93ea9  mov     rbp, [rsp+48h+arg_10]
0x140b93eae  add     rsp, 30h
0x140b93eb2  pop     r14
0x140b93eb4  pop     rdi
0x140b93eb5  pop     rsi
0x140b93eb6  retn
```
