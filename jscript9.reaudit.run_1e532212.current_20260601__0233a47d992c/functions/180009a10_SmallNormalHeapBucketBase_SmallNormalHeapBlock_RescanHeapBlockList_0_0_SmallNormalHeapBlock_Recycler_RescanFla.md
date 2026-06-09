# SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(SmallNormalHeapBlock *,Recycler *,RescanFlags)

- ea: `0x180009a10`
- end: `0x180009cb4`
- name: `??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallNormalHeapBlock@@@@KA_KPEAVSmallNormalHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008e4c`

## callees

- `0x180009a10`
- `0x180009cc0`
- `0x180009d70`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x180009b2c`
- `KERNEL32!ResetWriteWatch` at `0x180009b2c`
- `KERNEL32!GetWriteWatch` at `0x180009aca`
- `KERNEL32!GetWriteWatch` at `0x180009aca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v3; // rbp
  __int64 v4; // rbx
  int v5; // r13d
  PVOID *v7; // rdi
  int v9; // eax
  unsigned int v10; // r15d
  char *v11; // r9
  __int64 v12; // r12
  unsigned int v13; // r14d
  __int64 v14; // r8
  unsigned int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // rcx
  char v20; // al
  int v21; // eax
  _QWORD *Chunk; // rax
  DWORD dwGranularity; // [rsp+30h] [rbp-68h] BYREF
  ULONG_PTR dwCount; // [rsp+38h] [rbp-60h] BYREF
  int v25; // [rsp+40h] [rbp-58h]
  PVOID Addresses[10]; // [rsp+48h] [rbp-50h] BYREF

  Addresses[1] = (PVOID)-2LL;
  v3 = 0;
  v4 = a1;
  if ( a1 )
  {
    v5 = a3 & 1;
    v25 = v5;
    do
    {
      if ( v5 )
      {
        *(_BYTE *)(v4 + 120) = 0;
      }
      else if ( *(_BYTE *)(v4 + 120) )
      {
        if ( (a3 & 2) != 0 )
          ResetWriteWatch(*(LPVOID *)(v4 + 8), 0x1000u);
        goto LABEL_10;
      }
      if ( *(_WORD *)(v4 + 80) )
      {
        if ( *(_BYTE *)(v4 + 25) )
        {
          if ( !*(_BYTE *)(a2 + 12888) )
          {
            *(_BYTE *)(v4 + 25) = 0;
            v7 = (PVOID *)(v4 + 8);
LABEL_17:
            *(_BYTE *)(v4 + 120) = 1;
            v9 = *(unsigned __int16 *)(v4 + 74);
            v10 = *(unsigned __int16 *)(v4 + 80);
            v11 = (char *)*v7;
            Addresses[0] = *v7;
            v12 = *(unsigned __int16 *)(v4 + 72);
            if ( v10 == v9 )
            {
              if ( !Recycler::AddMark((Recycler *)a2, v11, (unsigned int)(v12 * v9)) )
              {
                *(_BYTE *)(v4 + 25) = 1;
                *(_BYTE *)(a2 + 12888) = 1;
              }
LABEL_11:
              ++v3;
              goto LABEL_12;
            }
            v13 = 0;
            v14 = 0;
            dwGranularity = 0;
            v15 = 0;
            if ( !v10 )
              goto LABEL_11;
            while ( 2 )
            {
              v16 = *(_QWORD *)(v4 + 8 * ((unsigned __int64)v15 >> 6) + 88);
              if ( _bittest64(&v16, v15 & 0x3F) )
              {
                v17 = *(_QWORD *)(a2 + 12680);
                v18 = *(_QWORD **)(v17 + 16);
                v19 = v18 + 2;
                if ( (unsigned __int64)(v18 + 2) <= *(_QWORD *)(v17 + 24) )
                {
                  *(_QWORD *)(v17 + 16) = v19;
                  goto LABEL_22;
                }
                Chunk = *(_QWORD **)(a2 + 12688);
                if ( Chunk )
                {
                  *(_QWORD *)(a2 + 12688) = 0;
LABEL_33:
                  *Chunk = *(_QWORD *)(a2 + 12680);
                  Chunk[2] = Chunk + 6;
                  *(_QWORD *)(a2 + 12680) = Chunk;
                  v18 = Chunk + 4;
LABEL_22:
                  if ( v18 )
                  {
                    *v18 = &v11[(unsigned int)(v12 * v14)];
                    v18[1] = v12;
                    v20 = 1;
                    goto LABEL_24;
                  }
                }
                else
                {
                  Chunk = (_QWORD *)PageStackBase<Recycler::MarkCandidate>::CreateChunk(v19, a2 + 12712, v14);
                  if ( Chunk )
                  {
                    LODWORD(v14) = dwGranularity;
                    v11 = (char *)Addresses[0];
                    goto LABEL_33;
                  }
                }
                v20 = 0;
                LODWORD(v14) = dwGranularity;
                v11 = (char *)Addresses[0];
LABEL_24:
                if ( v20 )
                {
                  v21 = 1;
                }
                else
                {
                  *(_BYTE *)(v4 + 25) = 1;
                  *(_BYTE *)(a2 + 12888) = 1;
                  v21 = *(unsigned __int16 *)(v4 + 74) + 1;
                }
                v13 += v21;
              }
              v14 = (unsigned int)(v14 + 1);
              dwGranularity = v14;
              v15 += (unsigned int)v12 >> 5;
              if ( v13 >= v10 )
              {
                v5 = v25;
                goto LABEL_11;
              }
              continue;
            }
          }
        }
        else if ( !*(_BYTE *)(a2 + 12901) )
        {
          dwCount = 1;
          dwGranularity = 4096;
          Addresses[0] = 0;
          v7 = (PVOID *)(v4 + 8);
          if ( GetWriteWatch((a3 >> 1) & 1, *(PVOID *)(v4 + 8), 0x1000u, Addresses, &dwCount, &dwGranularity) || dwCount )
            goto LABEL_17;
        }
      }
LABEL_10:
      if ( *(_BYTE *)(v4 + 120) )
        goto LABEL_11;
LABEL_12:
      v4 = *(_QWORD *)(v4 + 32);
    }
    while ( v4 );
  }
  return v3;
}

```

## disassembly

```asm
0x180009a10  mov     rax, rsp
0x180009a13  mov     [rax+18h], r8d
0x180009a17  mov     [rax+10h], rdx
0x180009a1b  mov     [rax+8], rcx
0x180009a1f  push    rbp
0x180009a20  push    rsi
0x180009a21  push    rdi
0x180009a22  push    r12
0x180009a24  push    r13
0x180009a26  push    r14
0x180009a28  push    r15
0x180009a2a  sub     rsp, 60h
0x180009a2e  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180009a36  mov     [rax+20h], rbx
0x180009a3a  xor     r10d, r10d
0x180009a3d  mov     ebp, r10d
0x180009a40  mov     rbx, rcx
0x180009a43  test    rcx, rcx
0x180009a46  jz      loc_180009AF4
0x180009a4c  mov     r13d, r8d
0x180009a4f  and     r13d, 1
0x180009a53  mov     [rsp+98h+var_58], r13d
0x180009a58  mov     rsi, rdx
0x180009a5b  test    r13d, r13d
0x180009a5e  jz      loc_180009B0F
0x180009a64  mov     [rbx+78h], r10b
0x180009a68  cmp     [rbx+50h], r10w
0x180009a6d  jz      short loc_180009ADE
0x180009a6f  cmp     [rbx+19h], r10b
0x180009a73  jnz     loc_180009BEF
0x180009a79  cmp     [rsi+3265h], r10b
0x180009a80  jnz     short loc_180009ADE
0x180009a82  mov     [rsp+98h+dwCount], 1
0x180009a8b  mov     [rsp+98h+dwGranularity], 1000h
0x180009a93  mov     [rsp+98h+Addresses], r10
0x180009a98  lea     rdi, [rbx+8]
0x180009a9c  mov     ecx, [rsp+98h+arg_10]
0x180009aa3  shr     ecx, 1
0x180009aa5  and     ecx, 1; dwFlags
0x180009aa8  lea     rax, [rsp+98h+dwGranularity]
0x180009aad  mov     [rsp+98h+lpdwGranularity], rax; lpdwGranularity
0x180009ab2  lea     rax, [rsp+98h+dwCount]
0x180009ab7  mov     [rsp+98h+lpdwCount], rax; lpdwCount
0x180009abc  lea     r9, [rsp+98h+Addresses]; lpAddresses
0x180009ac1  mov     r8d, 1000h; dwRegionSize
0x180009ac7  mov     rdx, [rdi]; lpBaseAddress
0x180009aca  call    cs:__imp_GetWriteWatch
0x180009ad0  xor     r10d, r10d
0x180009ad3  test    eax, eax
0x180009ad5  jnz     short loc_180009B37
0x180009ad7  cmp     [rsp+98h+dwCount], r10
0x180009adc  jnz     short loc_180009B37
0x180009ade  cmp     [rbx+78h], r10b
0x180009ae2  jz      short loc_180009AE7
0x180009ae4  inc     rbp
0x180009ae7  mov     rbx, [rbx+20h]
0x180009aeb  test    rbx, rbx
0x180009aee  jnz     loc_180009A5B
0x180009af4  mov     rax, rbp
0x180009af7  mov     rbx, [rsp+98h+arg_18]
0x180009aff  add     rsp, 60h
0x180009b03  pop     r15
0x180009b05  pop     r14
0x180009b07  pop     r13
0x180009b09  pop     r12
0x180009b0b  pop     rdi
0x180009b0c  pop     rsi
0x180009b0d  pop     rbp
0x180009b0e  retn
0x180009b0f  cmp     [rbx+78h], r10b
0x180009b13  jz      loc_180009A68
0x180009b19  test    byte ptr [rsp+98h+arg_10], 2
0x180009b21  jz      short loc_180009ADE
0x180009b23  mov     edx, 1000h; dwRegionSize
0x180009b28  mov     rcx, [rbx+8]; lpBaseAddress
0x180009b2c  call    cs:__imp_ResetWriteWatch
0x180009b32  xor     r10d, r10d
0x180009b35  jmp     short loc_180009ADE
0x180009b37  mov     byte ptr [rbx+78h], 1
0x180009b3b  movzx   eax, word ptr [rbx+4Ah]
0x180009b3f  movzx   r15d, word ptr [rbx+50h]
0x180009b44  mov     r9, [rdi]
0x180009b47  mov     [rsp+98h+Addresses], r9
0x180009b4c  movzx   r12d, word ptr [rbx+48h]
0x180009b51  cmp     r15d, eax
0x180009b54  jz      loc_180009C5E
0x180009b5a  mov     eax, r12d
0x180009b5d  shr     eax, 5
0x180009b60  mov     r14d, r10d
0x180009b63  mov     r8d, r10d
0x180009b66  mov     [rsp+98h+dwGranularity], r10d
0x180009b6b  mov     edi, r10d
0x180009b6e  test    r15d, r15d
0x180009b71  jz      loc_180009AE4
0x180009b77  mov     r13d, eax
0x180009b7a  mov     ecx, edi
0x180009b7c  and     ecx, 3Fh
0x180009b7f  mov     eax, edi
0x180009b81  shr     rax, 6
0x180009b85  mov     rax, [rbx+rax*8+58h]
0x180009b8a  bt      rax, rcx
0x180009b8e  jnb     short loc_180009BD5
0x180009b90  mov     rax, [rsi+3188h]
0x180009b97  mov     rdx, [rax+10h]
0x180009b9b  lea     rcx, [rdx+10h]
0x180009b9f  cmp     rcx, [rax+18h]
0x180009ba3  ja      short loc_180009C09
0x180009ba5  mov     [rax+10h], rcx
0x180009ba9  test    rdx, rdx
0x180009bac  jz      loc_180009CA1
0x180009bb2  mov     ecx, r8d
0x180009bb5  imul    ecx, r12d
0x180009bb9  add     rcx, r9
0x180009bbc  mov     [rdx], rcx
0x180009bbf  mov     [rdx+8], r12
0x180009bc3  mov     al, 1
0x180009bc5  test    al, al
0x180009bc7  jz      loc_180009C8B
0x180009bcd  mov     eax, 1
0x180009bd2  add     r14d, eax
0x180009bd5  inc     r8d
0x180009bd8  mov     [rsp+98h+dwGranularity], r8d
0x180009bdd  add     edi, r13d
0x180009be0  cmp     r14d, r15d
0x180009be3  jb      short loc_180009B7A
0x180009be5  mov     r13d, [rsp+98h+var_58]
0x180009bea  jmp     loc_180009AE4
0x180009bef  cmp     [rsi+3258h], r10b
0x180009bf6  jnz     loc_180009ADE
0x180009bfc  mov     [rbx+19h], r10b
0x180009c00  lea     rdi, [rbx+8]
0x180009c04  jmp     loc_180009B37
0x180009c09  mov     rax, [rsi+3190h]
0x180009c10  test    rax, rax
0x180009c13  jz      short loc_180009C3E
0x180009c15  mov     [rsi+3190h], r10
0x180009c1c  mov     rcx, [rsi+3188h]
0x180009c23  mov     [rax], rcx
0x180009c26  lea     rcx, [rax+30h]
0x180009c2a  mov     [rax+10h], rcx
0x180009c2e  mov     [rsi+3188h], rax
0x180009c35  lea     rdx, [rax+20h]
0x180009c39  jmp     loc_180009BA9
0x180009c3e  lea     rdx, [rsi+31A8h]
0x180009c45  call    ?CreateChunk@?$PageStackBase@UMarkCandidate@Recycler@@@@QEAAPEAUChunk@1@PEAVPageAllocator@@@Z; PageStackBase<Recycler::MarkCandidate>::CreateChunk(PageAllocator *)
0x180009c4a  xor     r10d, r10d
0x180009c4d  test    rax, rax
0x180009c50  jz      short loc_180009CA1
0x180009c52  mov     r8d, [rsp+98h+dwGranularity]
0x180009c57  mov     r9, [rsp+98h+Addresses]
0x180009c5c  jmp     short loc_180009C1C
0x180009c5e  imul    eax, r12d
0x180009c62  mov     r8d, eax; unsigned __int64
0x180009c65  mov     rdx, r9; void *
0x180009c68  mov     rcx, rsi; this
0x180009c6b  call    ?AddMark@Recycler@@AEAA_NPEAX_K@Z; Recycler::AddMark(void *,unsigned __int64)
0x180009c70  xor     r10d, r10d
0x180009c73  test    al, al
0x180009c75  jnz     loc_180009AE4
0x180009c7b  mov     byte ptr [rbx+19h], 1
0x180009c7f  mov     byte ptr [rsi+3258h], 1
0x180009c86  jmp     loc_180009AE4
0x180009c8b  mov     byte ptr [rbx+19h], 1
0x180009c8f  mov     byte ptr [rsi+3258h], 1
0x180009c96  movzx   eax, word ptr [rbx+4Ah]
0x180009c9a  inc     eax
0x180009c9c  jmp     loc_180009BD2
0x180009ca1  mov     al, r10b
0x180009ca4  mov     r8d, [rsp+98h+dwGranularity]
0x180009ca9  mov     r9, [rsp+98h+Addresses]
0x180009cae  jmp     loc_180009BC5
```
