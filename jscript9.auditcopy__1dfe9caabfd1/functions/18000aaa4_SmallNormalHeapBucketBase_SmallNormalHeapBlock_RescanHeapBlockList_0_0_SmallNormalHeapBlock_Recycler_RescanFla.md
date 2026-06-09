# SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(SmallNormalHeapBlock *,Recycler *,RescanFlags)

- ea: `0x18000aaa4`
- end: `0x18000ad55`
- name: `??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallNormalHeapBlock@@@@KA_KPEAVSmallNormalHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a02c`

## callees

- `0x18000aaa4`
- `0x18000ad60`
- `0x18000ae10`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x18000abc7`
- `KERNEL32!ResetWriteWatch` at `0x18000abc7`
- `KERNEL32!GetWriteWatch` at `0x18000ab5e`
- `KERNEL32!GetWriteWatch` at `0x18000ab5e`

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
  DWORD v14; // r8d
  unsigned int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  char v20; // al
  int v21; // eax
  char *Chunk; // rax
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
                v19 = (__int64)(v18 + 2);
                if ( (unsigned __int64)(v18 + 2) <= *(_QWORD *)(v17 + 24) )
                {
                  *(_QWORD *)(v17 + 16) = v19;
                  goto LABEL_22;
                }
                Chunk = *(char **)(a2 + 12688);
                if ( Chunk )
                {
                  *(_QWORD *)(a2 + 12688) = 0;
LABEL_33:
                  *(_QWORD *)Chunk = *(_QWORD *)(a2 + 12680);
                  *((_QWORD *)Chunk + 2) = Chunk + 48;
                  *(_QWORD *)(a2 + 12680) = Chunk;
                  v18 = Chunk + 32;
LABEL_22:
                  if ( v18 )
                  {
                    *v18 = &v11[(unsigned int)v12 * v14];
                    v18[1] = v12;
                    v20 = 1;
                    goto LABEL_24;
                  }
                }
                else
                {
                  Chunk = PageStackBase<Recycler::MarkCandidate>::CreateChunk(v19, a2 + 12712);
                  if ( Chunk )
                  {
                    v14 = dwGranularity;
                    v11 = (char *)Addresses[0];
                    goto LABEL_33;
                  }
                }
                v20 = 0;
                v14 = dwGranularity;
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
              dwGranularity = ++v14;
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
0x18000aaa4  mov     rax, rsp
0x18000aaa7  mov     [rax+18h], r8d
0x18000aaab  mov     [rax+10h], rdx
0x18000aaaf  mov     [rax+8], rcx
0x18000aab3  push    rbp
0x18000aab4  push    rsi
0x18000aab5  push    rdi
0x18000aab6  push    r12
0x18000aab8  push    r13
0x18000aaba  push    r14
0x18000aabc  push    r15
0x18000aabe  sub     rsp, 60h
0x18000aac2  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000aaca  mov     [rax+20h], rbx
0x18000aace  xor     r10d, r10d
0x18000aad1  mov     ebp, r10d
0x18000aad4  mov     rbx, rcx
0x18000aad7  test    rcx, rcx
0x18000aada  jz      loc_18000AB8E
0x18000aae0  mov     r13d, r8d
0x18000aae3  and     r13d, 1
0x18000aae7  mov     [rsp+98h+var_58], r13d
0x18000aaec  mov     rsi, rdx
0x18000aaef  test    r13d, r13d
0x18000aaf2  jz      loc_18000ABAA
0x18000aaf8  mov     [rbx+78h], r10b
0x18000aafc  cmp     [rbx+50h], r10w
0x18000ab01  jz      short loc_18000AB78
0x18000ab03  cmp     [rbx+19h], r10b
0x18000ab07  jnz     loc_18000AC90
0x18000ab0d  cmp     [rsi+3265h], r10b
0x18000ab14  jnz     short loc_18000AB78
0x18000ab16  mov     [rsp+98h+dwCount], 1
0x18000ab1f  mov     [rsp+98h+dwGranularity], 1000h
0x18000ab27  mov     [rsp+98h+Addresses], r10
0x18000ab2c  lea     rdi, [rbx+8]
0x18000ab30  mov     ecx, [rsp+98h+arg_10]
0x18000ab37  shr     ecx, 1
0x18000ab39  and     ecx, 1; dwFlags
0x18000ab3c  lea     rax, [rsp+98h+dwGranularity]
0x18000ab41  mov     [rsp+98h+lpdwGranularity], rax; lpdwGranularity
0x18000ab46  lea     rax, [rsp+98h+dwCount]
0x18000ab4b  mov     [rsp+98h+lpdwCount], rax; lpdwCount
0x18000ab50  lea     r9, [rsp+98h+Addresses]; lpAddresses
0x18000ab55  mov     r8d, 1000h; dwRegionSize
0x18000ab5b  mov     rdx, [rdi]; lpBaseAddress
0x18000ab5e  call    cs:__imp_GetWriteWatch
0x18000ab65  nop     dword ptr [rax+rax+00h]
0x18000ab6a  xor     r10d, r10d
0x18000ab6d  test    eax, eax
0x18000ab6f  jnz     short loc_18000ABD8
0x18000ab71  cmp     [rsp+98h+dwCount], r10
0x18000ab76  jnz     short loc_18000ABD8
0x18000ab78  cmp     [rbx+78h], r10b
0x18000ab7c  jz      short loc_18000AB81
0x18000ab7e  inc     rbp
0x18000ab81  mov     rbx, [rbx+20h]
0x18000ab85  test    rbx, rbx
0x18000ab88  jnz     loc_18000AAEF
0x18000ab8e  mov     rax, rbp
0x18000ab91  mov     rbx, [rsp+98h+arg_18]
0x18000ab99  add     rsp, 60h
0x18000ab9d  pop     r15
0x18000ab9f  pop     r14
0x18000aba1  pop     r13
0x18000aba3  pop     r12
0x18000aba5  pop     rdi
0x18000aba6  pop     rsi
0x18000aba7  pop     rbp
0x18000aba8  retn
0x18000abaa  cmp     [rbx+78h], r10b
0x18000abae  jz      loc_18000AAFC
0x18000abb4  test    byte ptr [rsp+98h+arg_10], 2
0x18000abbc  jz      short loc_18000AB78
0x18000abbe  mov     edx, 1000h; dwRegionSize
0x18000abc3  mov     rcx, [rbx+8]; lpBaseAddress
0x18000abc7  call    cs:__imp_ResetWriteWatch
0x18000abce  nop     dword ptr [rax+rax+00h]
0x18000abd3  xor     r10d, r10d
0x18000abd6  jmp     short loc_18000AB78
0x18000abd8  mov     byte ptr [rbx+78h], 1
0x18000abdc  movzx   eax, word ptr [rbx+4Ah]
0x18000abe0  movzx   r15d, word ptr [rbx+50h]
0x18000abe5  mov     r9, [rdi]
0x18000abe8  mov     [rsp+98h+Addresses], r9
0x18000abed  movzx   r12d, word ptr [rbx+48h]
0x18000abf2  cmp     r15d, eax
0x18000abf5  jz      loc_18000ACFF
0x18000abfb  mov     eax, r12d
0x18000abfe  shr     eax, 5
0x18000ac01  mov     r14d, r10d
0x18000ac04  mov     r8d, r10d
0x18000ac07  mov     [rsp+98h+dwGranularity], r10d
0x18000ac0c  mov     edi, r10d
0x18000ac0f  test    r15d, r15d
0x18000ac12  jz      loc_18000AB7E
0x18000ac18  mov     r13d, eax
0x18000ac1b  mov     ecx, edi
0x18000ac1d  and     ecx, 3Fh
0x18000ac20  mov     eax, edi
0x18000ac22  shr     rax, 6
0x18000ac26  mov     rax, [rbx+rax*8+58h]
0x18000ac2b  bt      rax, rcx
0x18000ac2f  jnb     short loc_18000AC76
0x18000ac31  mov     rax, [rsi+3188h]
0x18000ac38  mov     rdx, [rax+10h]
0x18000ac3c  lea     rcx, [rdx+10h]
0x18000ac40  cmp     rcx, [rax+18h]
0x18000ac44  ja      short loc_18000ACAA
0x18000ac46  mov     [rax+10h], rcx
0x18000ac4a  test    rdx, rdx
0x18000ac4d  jz      loc_18000AD42
0x18000ac53  mov     ecx, r8d
0x18000ac56  imul    ecx, r12d
0x18000ac5a  add     rcx, r9
0x18000ac5d  mov     [rdx], rcx
0x18000ac60  mov     [rdx+8], r12
0x18000ac64  mov     al, 1
0x18000ac66  test    al, al
0x18000ac68  jz      loc_18000AD2C
0x18000ac6e  mov     eax, 1
0x18000ac73  add     r14d, eax
0x18000ac76  inc     r8d
0x18000ac79  mov     [rsp+98h+dwGranularity], r8d
0x18000ac7e  add     edi, r13d
0x18000ac81  cmp     r14d, r15d
0x18000ac84  jb      short loc_18000AC1B
0x18000ac86  mov     r13d, [rsp+98h+var_58]
0x18000ac8b  jmp     loc_18000AB7E
0x18000ac90  cmp     [rsi+3258h], r10b
0x18000ac97  jnz     loc_18000AB78
0x18000ac9d  mov     [rbx+19h], r10b
0x18000aca1  lea     rdi, [rbx+8]
0x18000aca5  jmp     loc_18000ABD8
0x18000acaa  mov     rax, [rsi+3190h]
0x18000acb1  test    rax, rax
0x18000acb4  jz      short loc_18000ACDF
0x18000acb6  mov     [rsi+3190h], r10
0x18000acbd  mov     rcx, [rsi+3188h]
0x18000acc4  mov     [rax], rcx
0x18000acc7  lea     rcx, [rax+30h]
0x18000accb  mov     [rax+10h], rcx
0x18000accf  mov     [rsi+3188h], rax
0x18000acd6  lea     rdx, [rax+20h]
0x18000acda  jmp     loc_18000AC4A
0x18000acdf  lea     rdx, [rsi+31A8h]
0x18000ace6  call    ?CreateChunk@?$PageStackBase@UMarkCandidate@Recycler@@@@QEAAPEAUChunk@1@PEAVPageAllocator@@@Z; PageStackBase<Recycler::MarkCandidate>::CreateChunk(PageAllocator *)
0x18000aceb  xor     r10d, r10d
0x18000acee  test    rax, rax
0x18000acf1  jz      short loc_18000AD42
0x18000acf3  mov     r8d, [rsp+98h+dwGranularity]
0x18000acf8  mov     r9, [rsp+98h+Addresses]
0x18000acfd  jmp     short loc_18000ACBD
0x18000acff  imul    eax, r12d
0x18000ad03  mov     r8d, eax; unsigned __int64
0x18000ad06  mov     rdx, r9; void *
0x18000ad09  mov     rcx, rsi; this
0x18000ad0c  call    ?AddMark@Recycler@@AEAA_NPEAX_K@Z; Recycler::AddMark(void *,unsigned __int64)
0x18000ad11  xor     r10d, r10d
0x18000ad14  test    al, al
0x18000ad16  jnz     loc_18000AB7E
0x18000ad1c  mov     byte ptr [rbx+19h], 1
0x18000ad20  mov     byte ptr [rsi+3258h], 1
0x18000ad27  jmp     loc_18000AB7E
0x18000ad2c  mov     byte ptr [rbx+19h], 1
0x18000ad30  mov     byte ptr [rsi+3258h], 1
0x18000ad37  movzx   eax, word ptr [rbx+4Ah]
0x18000ad3b  inc     eax
0x18000ad3d  jmp     loc_18000AC73
0x18000ad42  mov     al, r10b
0x18000ad45  mov     r8d, [rsp+98h+dwGranularity]
0x18000ad4a  mov     r9, [rsp+98h+Addresses]
0x18000ad4f  jmp     loc_18000AC66
```
