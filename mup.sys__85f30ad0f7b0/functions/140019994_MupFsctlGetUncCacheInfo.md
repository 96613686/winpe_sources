# MupFsctlGetUncCacheInfo

- ea: `0x140019994`
- end: `0x140019cfe`
- name: `MupFsctlGetUncCacheInfo`
- size: `874`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140019d10`

## callees

- `0x1400056c0`
- `0x140019994`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001dacc`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140019cd2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019cd2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019a4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140019a4b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140019a60`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140019a60`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140019b00`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140019b00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019cde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019cde`

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
0x140019994  mov     rax, rsp
0x140019997  mov     [rax+8], rcx
0x14001999b  push    rbx
0x14001999c  push    rbp
0x14001999d  push    rsi
0x14001999e  push    rdi
0x14001999f  push    r12
0x1400199a1  push    r13
0x1400199a3  push    r14
0x1400199a5  push    r15
0x1400199a7  sub     rsp, 38h
0x1400199ab  mov     rbx, [rcx+18h]
0x1400199af  mov     r13, rcx
0x1400199b2  mov     qword ptr [rax+20h], 0
0x1400199ba  mov     [rsp+78h+var_50], rbx
0x1400199bf  test    rbx, rbx
0x1400199c2  jnz     short loc_1400199D2
0x1400199c4  mov     esi, 0C000000Dh
0x1400199c9  mov     [rcx+38h], rbx
0x1400199cd  jmp     loc_140019CEA
0x1400199d2  mov     rcx, [rcx+0B8h]
0x1400199d9  mov     edi, [rcx+8]
0x1400199dc  cmp     edi, 4
0x1400199df  jnb     short loc_1400199F3
0x1400199e1  mov     esi, 0C0000023h
0x1400199e6  mov     qword ptr [r13+38h], 0
0x1400199ee  jmp     loc_140019CEA
0x1400199f3  mov     rcx, [rcx+30h]
0x1400199f7  call    MupGetSiloFromFileObject
0x1400199fc  mov     rcx, rax
0x1400199ff  lea     rdx, [rsp+78h+arg_18]
0x140019a07  call    MupGetContainerContextFromSilo
0x140019a0c  mov     esi, eax
0x140019a0e  test    eax, eax
0x140019a10  jnz     loc_140019CEA
0x140019a16  mov     rcx, [rsp+78h+arg_18]
0x140019a1e  call    MupGetUncCachePrefixTable
0x140019a23  xor     ecx, ecx
0x140019a25  mov     [rsp+78h+arg_10], rax
0x140019a2d  lea     ebp, [rsi+10h]
0x140019a30  cmp     edi, ebp
0x140019a32  lea     r12d, [rdi-10h]
0x140019a36  cmovbe  r12d, ecx
0x140019a3a  add     rbx, rbp
0x140019a3d  xor     edi, edi
0x140019a3f  mov     [rsp+78h+var_58], rbx
0x140019a44  mov     [rsp+78h+arg_8], edi
0x140019a4b  call    cs:__imp_KeEnterCriticalRegion
0x140019a52  nop     dword ptr [rax+rax+00h]
0x140019a57  mov     dl, 1; Wait
0x140019a59  lea     rcx, Resource; Resource
0x140019a60  call    cs:__imp_ExAcquireResourceSharedLite
0x140019a67  nop     dword ptr [rax+rax+00h]
0x140019a6c  mov     r15, cs:qword_14000A9E0
0x140019a73  lea     r9, qword_14000A9E0
0x140019a7a  cmp     r15, r9
0x140019a7d  jz      loc_140019C4A
0x140019a83  mov     r13, [rsp+78h+arg_10]
0x140019a8b  mov     r14, rbx
0x140019a8e  cmp     [r15-30h], r13
0x140019a92  jnz     loc_140019C2B
0x140019a98  mov     rax, [r15-10h]
0x140019a9c  movzx   edx, word ptr [rax+18h]
0x140019aa0  mov     rax, [r15-38h]
0x140019aa4  movzx   r8d, word ptr [rax]
0x140019aa8  mov     rax, [r15-8]
0x140019aac  add     r8d, 24h ; '$'
0x140019ab0  add     r8d, edx
0x140019ab3  test    rax, rax
0x140019ab6  jz      short loc_140019AC1
0x140019ab8  movzx   eax, word ptr [rax+28h]
0x140019abc  add     eax, r8d
0x140019abf  jmp     short loc_140019AC4
0x140019ac1  mov     eax, r8d
0x140019ac4  add     eax, 3
0x140019ac7  and     eax, 0FFFFFFFCh
0x140019aca  mov     dword ptr [rsp+78h+arg_10], eax
0x140019ad1  cmp     r12d, eax
0x140019ad4  jb      loc_140019C18
0x140019ada  mov     [r14], eax
0x140019add  mov     rbx, 0FFFFF78000000320h
0x140019ae7  mov     rax, [r15-10h]
0x140019aeb  mov     ecx, [rax+3Ch]
0x140019aee  mov     [r14+1Ch], ecx
0x140019af2  xor     ecx, ecx
0x140019af4  mov     rdi, [r15-18h]
0x140019af8  mov     rbx, [rbx]
0x140019afb  cmp     rdi, rbx
0x140019afe  jle     short loc_140019B19
0x140019b00  call    cs:__imp_KeQueryTimeIncrement
0x140019b07  nop     dword ptr [rax+rax+00h]
0x140019b0c  sub     rdi, rbx
0x140019b0f  mov     eax, eax
0x140019b11  imul    rax, rdi
0x140019b15  imul    rcx, rax, 64h ; 'd'
0x140019b19  lea     rdi, [r14+24h]
0x140019b1d  mov     rax, 112E0BE826D694B3h
0x140019b27  imul    rcx
0x140019b2a  sar     rdx, 1Ah
0x140019b2e  mov     rax, rdx
0x140019b31  shr     rax, 3Fh
0x140019b35  add     rdx, rax
0x140019b38  mov     [r14+20h], edx
0x140019b3c  mov     rax, [r15-38h]
0x140019b40  movzx   ecx, word ptr [rax]
0x140019b43  mov     eax, edi
0x140019b45  mov     [r14+8], cx
0x140019b4a  sub     eax, r14d
0x140019b4d  sub     eax, 24h ; '$'
0x140019b50  mov     ebx, ecx
0x140019b52  mov     [r14+4], eax
0x140019b56  mov     r8d, ecx; Size
0x140019b59  mov     rdx, [r15-38h]
0x140019b5d  mov     rcx, rdi; void *
0x140019b60  mov     rdx, [rdx+8]; Src
0x140019b64  call    memmove
0x140019b69  mov     rax, [r15-10h]
0x140019b6d  shr     rbx, 1
0x140019b70  movzx   ecx, word ptr [rax+18h]
0x140019b74  mov     [r14+10h], cx
0x140019b79  lea     rdi, [rdi+rbx*2]
0x140019b7d  mov     eax, edi
0x140019b7f  mov     ebx, ecx
0x140019b81  sub     eax, r14d
0x140019b84  mov     r8d, ecx; Size
0x140019b87  sub     eax, 24h ; '$'
0x140019b8a  mov     rcx, rdi; void *
0x140019b8d  mov     [r14+0Ch], eax
0x140019b91  mov     rdx, [r15-10h]
0x140019b95  mov     rdx, [rdx+20h]; Src
0x140019b99  call    memmove
0x140019b9e  mov     rdx, [r15-8]
0x140019ba2  test    rdx, rdx
0x140019ba5  jz      short loc_140019BD5
0x140019ba7  movzx   edx, word ptr [rdx+28h]
0x140019bab  mov     [r14+18h], dx
0x140019bb0  mov     r8d, edx; Size
0x140019bb3  shr     rbx, 1
0x140019bb6  lea     rcx, [rdi+rbx*2]; void *
0x140019bba  mov     eax, ecx
0x140019bbc  sub     eax, r14d
0x140019bbf  sub     eax, 24h ; '$'
0x140019bc2  mov     [r14+14h], eax
0x140019bc6  mov     rdx, [r15-8]
0x140019bca  mov     rdx, [rdx+30h]; Src
0x140019bce  call    memmove
0x140019bd3  jmp     short loc_140019BE4
0x140019bd5  xor     eax, eax
0x140019bd7  mov     dword ptr [r14+14h], 0
0x140019bdf  mov     [r14+18h], ax
0x140019be4  xor     eax, eax
0x140019be6  mov     [r14+1Ah], ax
0x140019beb  cmp     [r15+14h], al
0x140019bef  jz      short loc_140019BF8
0x140019bf1  mov     word ptr [r14+1Ah], 1
0x140019bf8  mov     eax, [r14]
0x140019bfb  lea     r9, qword_14000A9E0
0x140019c02  mov     edi, [rsp+78h+arg_8]
0x140019c09  add     r14, rax
0x140019c0c  mov     eax, dword ptr [rsp+78h+arg_10]
0x140019c13  sub     r12d, eax
0x140019c16  jmp     short loc_140019C20
0x140019c18  xor     r12d, r12d
0x140019c1b  mov     esi, 80000005h
0x140019c20  add     ebp, eax
0x140019c22  inc     edi
0x140019c24  mov     [rsp+78h+arg_8], edi
0x140019c2b  mov     r15, [r15]
0x140019c2e  mov     eax, edi
0x140019c30  cmp     r15, r9
0x140019c33  jnz     loc_140019A8E
0x140019c39  mov     r13, [rsp+78h+arg_0]
0x140019c41  test    eax, eax
0x140019c43  jnz     short loc_140019C69
0x140019c45  mov     rbx, [rsp+78h+var_58]
0x140019c4a  add     ebp, 28h ; '('
0x140019c4d  cmp     r12d, 28h ; '('
0x140019c51  jb      short loc_140019CB7
0x140019c53  xorps   xmm0, xmm0
0x140019c56  xor     eax, eax
0x140019c58  movups  xmmword ptr [rbx], xmm0
0x140019c5b  movups  xmmword ptr [rbx+10h], xmm0
0x140019c5f  mov     [rbx+20h], rax
0x140019c63  mov     dword ptr [rbx], 28h ; '('
0x140019c69  test    esi, esi
0x140019c6b  jnz     short loc_140019CBC
0x140019c6d  mov     eax, cs:dword_14000A9F8
0x140019c73  mov     r8, [rsp+78h+var_50]
0x140019c78  mov     [r8], eax
0x140019c7b  mov     eax, cs:dword_14000A9FC
0x140019c81  mov     [r8+4], eax
0x140019c85  mov     rax, 0D6BF94D5E57A42BDh
0x140019c8f  imul    cs:qword_14000A9F0
0x140019c96  add     rdx, cs:qword_14000A9F0
0x140019c9d  sar     rdx, 17h
0x140019ca1  mov     rax, rdx
0x140019ca4  mov     [r8+0Ch], edi
0x140019ca8  shr     rax, 3Fh
0x140019cac  add     rdx, rax
0x140019caf  mov     eax, ebp
0x140019cb1  mov     [r8+8], edx
0x140019cb5  jmp     short loc_140019CC7
0x140019cb7  mov     esi, 80000005h
0x140019cbc  mov     rax, [r13+18h]
0x140019cc0  mov     [rax], ebp
0x140019cc2  mov     eax, 4
0x140019cc7  lea     rcx, Resource; Resource
0x140019cce  mov     [r13+38h], rax
0x140019cd2  call    cs:__imp_ExReleaseResourceLite
0x140019cd9  nop     dword ptr [rax+rax+00h]
0x140019cde  call    cs:__imp_KeLeaveCriticalRegion
0x140019ce5  nop     dword ptr [rax+rax+00h]
0x140019cea  mov     eax, esi
0x140019cec  add     rsp, 38h
0x140019cf0  pop     r15
0x140019cf2  pop     r14
0x140019cf4  pop     r13
0x140019cf6  pop     r12
0x140019cf8  pop     rdi
0x140019cf9  pop     rsi
0x140019cfa  pop     rbp
0x140019cfb  pop     rbx
0x140019cfc  retn
```
