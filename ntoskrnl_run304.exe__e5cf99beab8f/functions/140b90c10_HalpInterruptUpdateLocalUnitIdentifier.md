# HalpInterruptUpdateLocalUnitIdentifier

- ea: `0x140b90c10`
- end: `0x140b90e78`
- name: `HalpInterruptUpdateLocalUnitIdentifier`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140b90968`

## callees

- `0x14023f970`
- `0x140245868`
- `0x1406e8590`
- `0x140b90c10`

## string_xrefs

- `0x140b90ce2`: `minkernel\hals\lib\interrupts\common\replace.c`
- `0x140b90d50`: `minkernel\hals\lib\interrupts\common\replace.c`
- `0x140b90e45`: `minkernel\hals\lib\interrupts\common\replace.c`

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
    v24 = *(_QWORD *)(k + 8)
        & ~(1LL << (*(_BYTE *)(&KiSystemAvailableCpusSubscriptionLock.SchedulingGroup->Policy.Value + v14) & 0x3F));
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
        _bittestandset64(&v27, *(&KiSystemAvailableCpusSubscriptionLock.SchedulingGroup->Policy.Value + v14) & 0x3F);
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
0x140b90c10  mov     [rsp+arg_0], rbx
0x140b90c15  mov     [rsp+arg_10], rbp
0x140b90c1a  mov     [rsp+arg_8], edx
0x140b90c1e  push    rsi
0x140b90c1f  push    rdi
0x140b90c20  push    r14
0x140b90c22  sub     rsp, 30h
0x140b90c26  mov     rbx, r9
0x140b90c29  mov     rbp, r8
0x140b90c2c  mov     edi, edx
0x140b90c2e  mov     esi, ecx
0x140b90c30  xor     eax, eax
0x140b90c32  cmp     eax, cs:HalpInterruptProcessorCount
0x140b90c38  jnb     loc_140B90E3A
0x140b90c3e  mov     r8, cs:HalpInterruptProcessorState
0x140b90c45  mov     r9d, eax
0x140b90c48  shl     r9, 6
0x140b90c4c  cmp     [r9+r8], esi
0x140b90c50  jz      short loc_140B90C56
0x140b90c52  inc     eax
0x140b90c54  jmp     short loc_140B90C32
0x140b90c56  mov     al, [r9+r8+0Dh]
0x140b90c5b  lea     rdx, [r8+10h]
0x140b90c5f  add     rdx, r9
0x140b90c62  mov     [r9+r8], edi
0x140b90c66  neg     al
0x140b90c68  sbb     rcx, rcx
0x140b90c6b  and     rcx, rdx; ProcNumber
0x140b90c6e  call    KeGetProcessorIndexFromNumber
0x140b90c73  mov     rcx, cs:HalpInterruptTargets
0x140b90c7a  mov     r14d, eax
0x140b90c7d  mov     rax, cs:HalpInterruptLocalIds
0x140b90c84  mov     [rax+r14*4], edi
0x140b90c88  lea     rdi, [r14+r14*2]
0x140b90c8c  movups  xmm0, xmmword ptr [rcx+rdi*8]
0x140b90c90  movups  xmmword ptr [rbp+0], xmm0
0x140b90c94  movsd   xmm1, qword ptr [rcx+rdi*8+10h]
0x140b90c9a  movsd   qword ptr [rbp+10h], xmm1
0x140b90c9f  cmp     dword ptr [rcx+rdi*8], 4
0x140b90ca3  jnz     short loc_140B90CAD
0x140b90ca5  mov     eax, [rsp+48h+arg_8]
0x140b90ca9  mov     [rcx+rdi*8+8], eax
0x140b90cad  mov     rcx, cs:HalpInterruptController
0x140b90cb4  mov     rax, [rcx+90h]
0x140b90cbb  test    rax, rax
0x140b90cbe  jz      short loc_140B90D25
0x140b90cc0  mov     rcx, [rcx+10h]
0x140b90cc4  lea     rdx, [rsp+48h+arg_8]
0x140b90cc9  mov     r9b, 1
0x140b90ccc  mov     r8, rbx
0x140b90ccf  call    _guard_dispatch_icall_no_overrides
0x140b90cd4  mov     r8d, eax
0x140b90cd7  test    eax, eax
0x140b90cd9  jns     short loc_140B90D0C
0x140b90cdb  mov     rcx, cs:HalpInterruptController
0x140b90ce2  lea     r11, aMinkernelHalsL_2; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140b90ce9  mov     [rsp+48h+var_20], 421h
0x140b90cf1  or      r9d, 0FFFFFFFFh
0x140b90cf5  mov     edx, 9
0x140b90cfa  mov     [rsp+48h+var_28], r11
0x140b90cff  call    HalpInterruptSetProblemEx
0x140b90d04  mov     eax, r8d
0x140b90d07  jmp     loc_140B90E64
0x140b90d0c  mov     rcx, cs:HalpInterruptTargets
0x140b90d13  movups  xmm0, xmmword ptr [rbx]
0x140b90d16  movups  xmmword ptr [rcx+rdi*8], xmm0
0x140b90d1a  movsd   xmm1, qword ptr [rbx+10h]
0x140b90d1f  movsd   qword ptr [rcx+rdi*8+10h], xmm1
0x140b90d25  xor     eax, eax
0x140b90d27  cmp     eax, cs:HalpInterruptDynamicProcessorCount
0x140b90d2d  jnb     short loc_140B90D4C
0x140b90d2f  mov     rdx, cs:HalpInterruptDynamicProcessorState
0x140b90d36  mov     ecx, eax
0x140b90d38  shl     rcx, 6
0x140b90d3c  cmp     [rcx+rdx], esi
0x140b90d3f  jz      short loc_140B90D45
0x140b90d41  inc     eax
0x140b90d43  jmp     short loc_140B90D27
0x140b90d45  mov     eax, [rsp+48h+arg_8]
0x140b90d49  mov     [rcx+rdx], eax
0x140b90d4c  or      r9d, 0FFFFFFFFh
0x140b90d50  lea     r11, aMinkernelHalsL_2; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140b90d57  cmp     dword ptr [rbp+0], 6
0x140b90d5b  mov     esi, 1Dh
0x140b90d60  jnz     short loc_140B90DBC
0x140b90d62  mov     rdx, cs:HalpInterruptClusterData
0x140b90d69  cmp     rdx, cs:HalpInterruptClusterDataEnd
0x140b90d70  jnb     short loc_140B90DA3
0x140b90d72  mov     eax, [rbp+8]
0x140b90d75  cmp     [rdx], eax
0x140b90d77  jz      short loc_140B90D7F
0x140b90d79  add     rdx, 18h
0x140b90d7d  jmp     short loc_140B90D69
0x140b90d7f  mov     rax, cs:KiSystemAvailableCpusSubscriptionLock.SchedulingGroup
0x140b90d86  mov     ecx, [rax+r14*4]
0x140b90d8a  mov     rax, [rdx+8]
0x140b90d8e  and     ecx, 3Fh
0x140b90d91  btr     rax, rcx
0x140b90d95  mov     [rdx+8], rax
0x140b90d99  test    rax, rax
0x140b90d9c  jnz     short loc_140B90DBC
0x140b90d9e  mov     [rdx], r9d
0x140b90da1  jmp     short loc_140B90DBC
0x140b90da3  mov     [rsp+48h+var_20], 458h
0x140b90dab  xor     r8d, r8d
0x140b90dae  mov     edx, esi
0x140b90db0  mov     [rsp+48h+var_28], r11
0x140b90db5  xor     ecx, ecx
0x140b90db7  call    HalpInterruptSetProblemEx
0x140b90dbc  mov     rax, cs:HalpInterruptTargets
0x140b90dc3  movups  xmm0, xmmword ptr [rax+rdi*8]
0x140b90dc7  movups  xmmword ptr [rbx], xmm0
0x140b90dca  movsd   xmm1, qword ptr [rax+rdi*8+10h]
0x140b90dd0  movsd   qword ptr [rbx+10h], xmm1
0x140b90dd5  cmp     dword ptr [rbx], 6
0x140b90dd8  jnz     short loc_140B90E36
0x140b90dda  mov     rdx, cs:HalpInterruptClusterData
0x140b90de1  cmp     rdx, cs:HalpInterruptClusterDataEnd
0x140b90de8  jnb     short loc_140B90E1D
0x140b90dea  mov     eax, [rdx]
0x140b90dec  cmp     eax, r9d
0x140b90def  jz      short loc_140B90DFC
0x140b90df1  cmp     eax, [rbx+8]
0x140b90df4  jz      short loc_140B90DFC
0x140b90df6  add     rdx, 18h
0x140b90dfa  jmp     short loc_140B90DE1
0x140b90dfc  mov     eax, [rbx+8]
0x140b90dff  mov     [rdx], eax
0x140b90e01  mov     rax, cs:KiSystemAvailableCpusSubscriptionLock.SchedulingGroup
0x140b90e08  mov     ecx, [rax+r14*4]
0x140b90e0c  mov     rax, [rdx+8]
0x140b90e10  and     ecx, 3Fh
0x140b90e13  bts     rax, rcx
0x140b90e17  mov     [rdx+8], rax
0x140b90e1b  jmp     short loc_140B90E36
0x140b90e1d  mov     [rsp+48h+var_20], 47Bh
0x140b90e25  xor     r8d, r8d
0x140b90e28  mov     edx, esi
0x140b90e2a  mov     [rsp+48h+var_28], r11
0x140b90e2f  xor     ecx, ecx
0x140b90e31  call    HalpInterruptSetProblemEx
0x140b90e36  xor     eax, eax
0x140b90e38  jmp     short loc_140B90E64
0x140b90e3a  xor     r8d, r8d
0x140b90e3d  mov     [rsp+48h+var_20], 3FCh
0x140b90e45  lea     r11, aMinkernelHalsL_2; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140b90e4c  mov     r9d, esi
0x140b90e4f  xor     ecx, ecx
0x140b90e51  mov     [rsp+48h+var_28], r11
0x140b90e56  lea     edx, [r8+15h]
0x140b90e5a  call    HalpInterruptSetProblemEx
0x140b90e5f  mov     eax, 0C0000225h
0x140b90e64  mov     rbx, [rsp+48h+arg_0]
0x140b90e69  mov     rbp, [rsp+48h+arg_10]
0x140b90e6e  add     rsp, 30h
0x140b90e72  pop     r14
0x140b90e74  pop     rdi
0x140b90e75  pop     rsi
0x140b90e76  retn
```
