# MupFsctlGetUncCacheInfo

- ea: `0x140019944`
- end: `0x140019cae`
- name: `MupFsctlGetUncCacheInfo`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140019cc0`

## callees

- `0x1400056c0`
- `0x140019944`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001da7c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140019c82`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019c82`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400199fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400199fb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140019a10`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140019a10`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140019ab0`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140019ab0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019c8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019c8e`

## pseudocode

```c
__int64 __fastcall MupFsctlGetUncCacheInfo(_QWORD *a1)
{
  _DWORD *v1; // rbx
  _QWORD *v2; // r13
  unsigned int ContainerContextFromSilo; // esi
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 SiloFromFileObject; // rax
  unsigned int v7; // ebp
  unsigned int v8; // r12d
  unsigned int *v9; // rbx
  int v10; // edi
  __int64 v11; // r15
  __int64 v12; // r13
  unsigned int *v13; // r14
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // eax
  int v17; // ecx
  __int64 v18; // rdi
  int v19; // ebx
  unsigned int v20; // ecx
  unsigned __int64 v21; // rbx
  unsigned int v22; // ecx
  char *v23; // rdi
  unsigned __int64 v24; // rbx
  __int64 v25; // rdx
  unsigned int v26; // edx
  unsigned __int64 v27; // rbx
  __int64 v28; // kr18_8
  __int64 v29; // rax
  unsigned int *v31; // [rsp+20h] [rbp-58h]
  _DWORD *v32; // [rsp+28h] [rbp-50h]
  int v34; // [rsp+88h] [rbp+10h]
  __int64 UncCachePrefixTable; // [rsp+90h] [rbp+18h]
  unsigned int v36; // [rsp+90h] [rbp+18h]
  __int64 v37; // [rsp+98h] [rbp+20h] BYREF

  v1 = (_DWORD *)a1[3];
  v2 = a1;
  v37 = 0;
  v32 = v1;
  if ( v1 )
  {
    v4 = a1[23];
    v5 = *(_DWORD *)(v4 + 8);
    if ( v5 < 4 )
    {
      ContainerContextFromSilo = -1073741789;
      v2[7] = 0;
      return ContainerContextFromSilo;
    }
    SiloFromFileObject = MupGetSiloFromFileObject(*(_QWORD *)(v4 + 48));
    ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v37);
    if ( ContainerContextFromSilo )
      return ContainerContextFromSilo;
    UncCachePrefixTable = MupGetUncCachePrefixTable(v37);
    v7 = 16;
    v8 = v5 - 16;
    if ( v5 <= 0x10 )
      v8 = 0;
    v9 = v1 + 4;
    v10 = 0;
    v31 = v9;
    v34 = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&Resource, 1u);
    v11 = qword_14000A9E0;
    if ( (__int64 *)qword_14000A9E0 != &qword_14000A9E0 )
    {
      v12 = UncCachePrefixTable;
      v13 = v9;
      do
      {
        if ( *(_QWORD *)(v11 - 48) == v12 )
        {
          v14 = *(_QWORD *)(v11 - 8);
          if ( v14 )
            v15 = *(unsigned __int16 *)(*(_QWORD *)(v11 - 16) + 24LL)
                + **(unsigned __int16 **)(v11 - 56)
                + 36
                + *(unsigned __int16 *)(v14 + 40);
          else
            v15 = *(unsigned __int16 *)(*(_QWORD *)(v11 - 16) + 24LL) + **(unsigned __int16 **)(v11 - 56) + 36;
          v16 = (v15 + 3) & 0xFFFFFFFC;
          v36 = v16;
          if ( v8 < v16 )
          {
            v8 = 0;
            ContainerContextFromSilo = -2147483643;
          }
          else
          {
            *v13 = v16;
            v13[7] = *(_DWORD *)(*(_QWORD *)(v11 - 16) + 60LL);
            v17 = 0;
            v18 = *(_QWORD *)(v11 - 24);
            v19 = MEMORY[0xFFFFF78000000320];
            if ( v18 > MEMORY[0xFFFFF78000000320] )
              v17 = 100 * (v18 - v19) * KeQueryTimeIncrement();
            v13[8] = v17 / 1000000000;
            v20 = **(unsigned __int16 **)(v11 - 56);
            *((_WORD *)v13 + 4) = v20;
            v21 = v20;
            v13[1] = 0;
            memmove(v13 + 9, *(const void **)(*(_QWORD *)(v11 - 56) + 8LL), v20);
            v22 = *(unsigned __int16 *)(*(_QWORD *)(v11 - 16) + 24LL);
            *((_WORD *)v13 + 8) = v22;
            v23 = (char *)v13 + 2 * (v21 >> 1) + 36;
            v24 = v22;
            v13[3] = (_DWORD)v23 - (_DWORD)v13 - 36;
            memmove(v23, *(const void **)(*(_QWORD *)(v11 - 16) + 32LL), v22);
            v25 = *(_QWORD *)(v11 - 8);
            if ( v25 )
            {
              v26 = *(unsigned __int16 *)(v25 + 40);
              *((_WORD *)v13 + 12) = v26;
              v27 = v24 >> 1;
              v13[5] = (_DWORD)v23 + 2 * v27 - (_DWORD)v13 - 36;
              memmove(&v23[2 * v27], *(const void **)(*(_QWORD *)(v11 - 8) + 48LL), v26);
            }
            else
            {
              v13[5] = 0;
              *((_WORD *)v13 + 12) = 0;
            }
            *((_WORD *)v13 + 13) = 0;
            if ( *(_BYTE *)(v11 + 20) )
              *((_WORD *)v13 + 13) = 1;
            v10 = v34;
            v13 = (unsigned int *)((char *)v13 + *v13);
            v16 = v36;
            v8 -= v36;
          }
          v7 += v16;
          v34 = ++v10;
        }
        v11 = *(_QWORD *)v11;
      }
      while ( (__int64 *)v11 != &qword_14000A9E0 );
      v2 = a1;
      if ( v10 )
        goto LABEL_30;
      v9 = v31;
    }
    v7 += 40;
    if ( v8 < 0x28 )
    {
      ContainerContextFromSilo = -2147483643;
      goto LABEL_33;
    }
    *(_OWORD *)v9 = 0;
    *((_OWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *v9 = 40;
LABEL_30:
    if ( !ContainerContextFromSilo )
    {
      *v32 = dword_14000A9F8;
      v32[1] = dword_14000A9FC;
      v28 = qword_14000A9F0;
      v32[3] = v10;
      v29 = v7;
      v32[2] = v28 / 10000000;
LABEL_34:
      v2[7] = v29;
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      return ContainerContextFromSilo;
    }
LABEL_33:
    *(_DWORD *)v2[3] = v7;
    v29 = 4;
    goto LABEL_34;
  }
  ContainerContextFromSilo = -1073741811;
  a1[7] = 0;
  return ContainerContextFromSilo;
}

```

## disassembly

```asm
0x140019944  mov     rax, rsp
0x140019947  mov     [rax+8], rcx
0x14001994b  push    rbx
0x14001994c  push    rbp
0x14001994d  push    rsi
0x14001994e  push    rdi
0x14001994f  push    r12
0x140019951  push    r13
0x140019953  push    r14
0x140019955  push    r15
0x140019957  sub     rsp, 38h
0x14001995b  mov     rbx, [rcx+18h]
0x14001995f  mov     r13, rcx
0x140019962  mov     qword ptr [rax+20h], 0
0x14001996a  mov     [rsp+78h+var_50], rbx
0x14001996f  test    rbx, rbx
0x140019972  jnz     short loc_140019982
0x140019974  mov     esi, 0C000000Dh
0x140019979  mov     [rcx+38h], rbx
0x14001997d  jmp     loc_140019C9A
0x140019982  mov     rcx, [rcx+0B8h]
0x140019989  mov     edi, [rcx+8]
0x14001998c  cmp     edi, 4
0x14001998f  jnb     short loc_1400199A3
0x140019991  mov     esi, 0C0000023h
0x140019996  mov     qword ptr [r13+38h], 0
0x14001999e  jmp     loc_140019C9A
0x1400199a3  mov     rcx, [rcx+30h]
0x1400199a7  call    MupGetSiloFromFileObject
0x1400199ac  mov     rcx, rax
0x1400199af  lea     rdx, [rsp+78h+arg_18]
0x1400199b7  call    MupGetContainerContextFromSilo
0x1400199bc  mov     esi, eax
0x1400199be  test    eax, eax
0x1400199c0  jnz     loc_140019C9A
0x1400199c6  mov     rcx, [rsp+78h+arg_18]
0x1400199ce  call    MupGetUncCachePrefixTable
0x1400199d3  xor     ecx, ecx
0x1400199d5  mov     [rsp+78h+arg_10], rax
0x1400199dd  lea     ebp, [rsi+10h]
0x1400199e0  cmp     edi, ebp
0x1400199e2  lea     r12d, [rdi-10h]
0x1400199e6  cmovbe  r12d, ecx
0x1400199ea  add     rbx, rbp
0x1400199ed  xor     edi, edi
0x1400199ef  mov     [rsp+78h+var_58], rbx
0x1400199f4  mov     [rsp+78h+arg_8], edi
0x1400199fb  call    cs:__imp_KeEnterCriticalRegion
0x140019a02  nop     dword ptr [rax+rax+00h]
0x140019a07  mov     dl, 1; Wait
0x140019a09  lea     rcx, Resource; Resource
0x140019a10  call    cs:__imp_ExAcquireResourceSharedLite
0x140019a17  nop     dword ptr [rax+rax+00h]
0x140019a1c  mov     r15, cs:qword_14000A9E0
0x140019a23  lea     r9, qword_14000A9E0
0x140019a2a  cmp     r15, r9
0x140019a2d  jz      loc_140019BFA
0x140019a33  mov     r13, [rsp+78h+arg_10]
0x140019a3b  mov     r14, rbx
0x140019a3e  cmp     [r15-30h], r13
0x140019a42  jnz     loc_140019BDB
0x140019a48  mov     rax, [r15-10h]
0x140019a4c  movzx   edx, word ptr [rax+18h]
0x140019a50  mov     rax, [r15-38h]
0x140019a54  movzx   r8d, word ptr [rax]
0x140019a58  mov     rax, [r15-8]
0x140019a5c  add     r8d, 24h ; '$'
0x140019a60  add     r8d, edx
0x140019a63  test    rax, rax
0x140019a66  jz      short loc_140019A71
0x140019a68  movzx   eax, word ptr [rax+28h]
0x140019a6c  add     eax, r8d
0x140019a6f  jmp     short loc_140019A74
0x140019a71  mov     eax, r8d
0x140019a74  add     eax, 3
0x140019a77  and     eax, 0FFFFFFFCh
0x140019a7a  mov     dword ptr [rsp+78h+arg_10], eax
0x140019a81  cmp     r12d, eax
0x140019a84  jb      loc_140019BC8
0x140019a8a  mov     [r14], eax
0x140019a8d  mov     rbx, 0FFFFF78000000320h
0x140019a97  mov     rax, [r15-10h]
0x140019a9b  mov     ecx, [rax+3Ch]
0x140019a9e  mov     [r14+1Ch], ecx
0x140019aa2  xor     ecx, ecx
0x140019aa4  mov     rdi, [r15-18h]
0x140019aa8  mov     rbx, [rbx]
0x140019aab  cmp     rdi, rbx
0x140019aae  jle     short loc_140019AC9
0x140019ab0  call    cs:__imp_KeQueryTimeIncrement
0x140019ab7  nop     dword ptr [rax+rax+00h]
0x140019abc  sub     rdi, rbx
0x140019abf  mov     eax, eax
0x140019ac1  imul    rax, rdi
0x140019ac5  imul    rcx, rax, 64h ; 'd'
0x140019ac9  lea     rdi, [r14+24h]
0x140019acd  mov     rax, 112E0BE826D694B3h
0x140019ad7  imul    rcx
0x140019ada  sar     rdx, 1Ah
0x140019ade  mov     rax, rdx
0x140019ae1  shr     rax, 3Fh
0x140019ae5  add     rdx, rax
0x140019ae8  mov     [r14+20h], edx
0x140019aec  mov     rax, [r15-38h]
0x140019af0  movzx   ecx, word ptr [rax]
0x140019af3  mov     eax, edi
0x140019af5  mov     [r14+8], cx
0x140019afa  sub     eax, r14d
0x140019afd  sub     eax, 24h ; '$'
0x140019b00  mov     ebx, ecx
0x140019b02  mov     [r14+4], eax
0x140019b06  mov     r8d, ecx; Size
0x140019b09  mov     rdx, [r15-38h]
0x140019b0d  mov     rcx, rdi; void *
0x140019b10  mov     rdx, [rdx+8]; Src
0x140019b14  call    memmove
0x140019b19  mov     rax, [r15-10h]
0x140019b1d  shr     rbx, 1
0x140019b20  movzx   ecx, word ptr [rax+18h]
0x140019b24  mov     [r14+10h], cx
0x140019b29  lea     rdi, [rdi+rbx*2]
0x140019b2d  mov     eax, edi
0x140019b2f  mov     ebx, ecx
0x140019b31  sub     eax, r14d
0x140019b34  mov     r8d, ecx; Size
0x140019b37  sub     eax, 24h ; '$'
0x140019b3a  mov     rcx, rdi; void *
0x140019b3d  mov     [r14+0Ch], eax
0x140019b41  mov     rdx, [r15-10h]
0x140019b45  mov     rdx, [rdx+20h]; Src
0x140019b49  call    memmove
0x140019b4e  mov     rdx, [r15-8]
0x140019b52  test    rdx, rdx
0x140019b55  jz      short loc_140019B85
0x140019b57  movzx   edx, word ptr [rdx+28h]
0x140019b5b  mov     [r14+18h], dx
0x140019b60  mov     r8d, edx; Size
0x140019b63  shr     rbx, 1
0x140019b66  lea     rcx, [rdi+rbx*2]; void *
0x140019b6a  mov     eax, ecx
0x140019b6c  sub     eax, r14d
0x140019b6f  sub     eax, 24h ; '$'
0x140019b72  mov     [r14+14h], eax
0x140019b76  mov     rdx, [r15-8]
0x140019b7a  mov     rdx, [rdx+30h]; Src
0x140019b7e  call    memmove
0x140019b83  jmp     short loc_140019B94
0x140019b85  xor     eax, eax
0x140019b87  mov     dword ptr [r14+14h], 0
0x140019b8f  mov     [r14+18h], ax
0x140019b94  xor     eax, eax
0x140019b96  mov     [r14+1Ah], ax
0x140019b9b  cmp     [r15+14h], al
0x140019b9f  jz      short loc_140019BA8
0x140019ba1  mov     word ptr [r14+1Ah], 1
0x140019ba8  mov     eax, [r14]
0x140019bab  lea     r9, qword_14000A9E0
0x140019bb2  mov     edi, [rsp+78h+arg_8]
0x140019bb9  add     r14, rax
0x140019bbc  mov     eax, dword ptr [rsp+78h+arg_10]
0x140019bc3  sub     r12d, eax
0x140019bc6  jmp     short loc_140019BD0
0x140019bc8  xor     r12d, r12d
0x140019bcb  mov     esi, 80000005h
0x140019bd0  add     ebp, eax
0x140019bd2  inc     edi
0x140019bd4  mov     [rsp+78h+arg_8], edi
0x140019bdb  mov     r15, [r15]
0x140019bde  mov     eax, edi
0x140019be0  cmp     r15, r9
0x140019be3  jnz     loc_140019A3E
0x140019be9  mov     r13, [rsp+78h+arg_0]
0x140019bf1  test    eax, eax
0x140019bf3  jnz     short loc_140019C19
0x140019bf5  mov     rbx, [rsp+78h+var_58]
0x140019bfa  add     ebp, 28h ; '('
0x140019bfd  cmp     r12d, 28h ; '('
0x140019c01  jb      short loc_140019C67
0x140019c03  xorps   xmm0, xmm0
0x140019c06  xor     eax, eax
0x140019c08  movups  xmmword ptr [rbx], xmm0
0x140019c0b  movups  xmmword ptr [rbx+10h], xmm0
0x140019c0f  mov     [rbx+20h], rax
0x140019c13  mov     dword ptr [rbx], 28h ; '('
0x140019c19  test    esi, esi
0x140019c1b  jnz     short loc_140019C6C
0x140019c1d  mov     eax, cs:dword_14000A9F8
0x140019c23  mov     r8, [rsp+78h+var_50]
0x140019c28  mov     [r8], eax
0x140019c2b  mov     eax, cs:dword_14000A9FC
0x140019c31  mov     [r8+4], eax
0x140019c35  mov     rax, 0D6BF94D5E57A42BDh
0x140019c3f  imul    cs:qword_14000A9F0
0x140019c46  add     rdx, cs:qword_14000A9F0
0x140019c4d  sar     rdx, 17h
0x140019c51  mov     rax, rdx
0x140019c54  mov     [r8+0Ch], edi
0x140019c58  shr     rax, 3Fh
0x140019c5c  add     rdx, rax
0x140019c5f  mov     eax, ebp
0x140019c61  mov     [r8+8], edx
0x140019c65  jmp     short loc_140019C77
0x140019c67  mov     esi, 80000005h
0x140019c6c  mov     rax, [r13+18h]
0x140019c70  mov     [rax], ebp
0x140019c72  mov     eax, 4
0x140019c77  lea     rcx, Resource; Resource
0x140019c7e  mov     [r13+38h], rax
0x140019c82  call    cs:__imp_ExReleaseResourceLite
0x140019c89  nop     dword ptr [rax+rax+00h]
0x140019c8e  call    cs:__imp_KeLeaveCriticalRegion
0x140019c95  nop     dword ptr [rax+rax+00h]
0x140019c9a  mov     eax, esi
0x140019c9c  add     rsp, 38h
0x140019ca0  pop     r15
0x140019ca2  pop     r14
0x140019ca4  pop     r13
0x140019ca6  pop     r12
0x140019ca8  pop     rdi
0x140019ca9  pop     rsi
0x140019caa  pop     rbp
0x140019cab  pop     rbx
0x140019cac  retn
```
