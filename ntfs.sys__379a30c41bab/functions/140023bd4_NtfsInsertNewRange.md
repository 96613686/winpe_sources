# NtfsInsertNewRange

- ea: `0x140023bd4`
- end: `0x140023fde`
- name: `NtfsInsertNewRange`
- size: `1034`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140023740`
- `0x140031410`
- `0x14004b1b0`

## callees

- `0x140015164`
- `0x140023bd4`
- `0x140038b74`
- `0x140059440`

## import_xrefs

- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140023ec1`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140023f49`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140023ec1`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140023f49`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140023f09`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140023f09`
- `ntoskrnl!FsRtlTruncateBaseMcb` at `0x140023f85`
- `ntoskrnl!FsRtlTruncateBaseMcb` at `0x140023f85`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140023fac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005ad83`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140023fac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005ad83`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140023d8c`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140023d8c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140023d43`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140023d43`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140023e38`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140023e38`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140023dc1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140023dc1`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x140023e97`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x140023e97`

## pseudocode

```c
BOOLEAN __fastcall NtfsInsertNewRange(__int64 a1, __int64 a2, unsigned int a3, char a4)
{
  __int64 v4; // r13
  BOOLEAN result; // al
  BOOLEAN v7; // r15
  unsigned int v8; // ecx
  unsigned int v9; // esi
  _QWORD *v10; // r14
  unsigned int v11; // r12d
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r12
  char v16; // r13
  struct _LOOKASIDE_LIST_EX *v17; // rcx
  char *v18; // rax
  char *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  ULONG v22; // r12d
  struct _LOOKASIDE_LIST_EX *v23; // rcx
  ULONG Index; // [rsp+44h] [rbp-74h] BYREF
  __int64 Lbn; // [rsp+48h] [rbp-70h] BYREF
  __int64 SectorCountFromLbn; // [rsp+50h] [rbp-68h] BYREF
  ULONG v27; // [rsp+58h] [rbp-60h]
  __int64 v28; // [rsp+60h] [rbp-58h]
  char *v29; // [rsp+68h] [rbp-50h]
  __int64 v30; // [rsp+70h] [rbp-48h]
  __int64 Vbn; // [rsp+78h] [rbp-40h] BYREF
  __int64 v32; // [rsp+80h] [rbp-38h]

  v4 = a3;
  if ( *(_DWORD *)(a1 + 12) < *(_DWORD *)(a1 + 16) || (result = NtfsGrowMcbArray()) != 0 )
  {
    v7 = 1;
    v8 = *(_DWORD *)(a1 + 12);
    v9 = v4 + 2;
    v10 = (_QWORD *)(a1 + 24);
    v11 = v4 + 1;
    if ( (int)v4 + 2 <= v8 )
    {
      memmove((void *)(*v10 + 32LL * v9), (const void *)(*v10 + 32LL * v11), 32LL * (v8 + ~(_DWORD)v4));
      while ( 1 )
      {
        v8 = *(_DWORD *)(a1 + 12);
        if ( v9 >= v8 + 1 )
          break;
        v12 = *v10 + 32LL * v9;
        v13 = *(_QWORD *)(v12 + 16);
        if ( v13 )
          *(_QWORD *)(v13 + 32) = v12;
        ++v9;
      }
    }
    *(_DWORD *)(a1 + 12) = v8 + 1;
    v14 = 32LL * v11;
    v30 = v14;
    *(_QWORD *)(v14 + *v10) = a2;
    v15 = 32 * v4;
    v32 = 32 * v4;
    *(_QWORD *)(v14 + *v10 + 8) = *(_QWORD *)(32 * v4 + *v10 + 8);
    *(_QWORD *)(*v10 + v14 + 16) = 0;
    *(_QWORD *)(*v10 + 32 * v4 + 8) = a2 - 1;
    if ( !a4 )
    {
      v28 = *(_QWORD *)(*v10 + v15 + 16);
      if ( v28 )
      {
        v29 = 0;
        Vbn = 0;
        Lbn = -1;
        SectorCountFromLbn = 0;
        Index = 0;
        v16 = 0;
        v17 = &NtfsPagedMcbEntryLookasideList;
        if ( *(_WORD *)(a1 + 10) != 1 )
          v17 = &NtfsNonPagedMcbEntryLookasideList;
        v18 = (char *)ExAllocateFromLookasideListEx(v17);
        v19 = v18;
        v29 = v18;
        if ( v18 )
        {
          v16 = 1;
          *((_QWORD *)v18 + 3) = a1;
          *((_QWORD *)v18 + 4) = *v10 + v30;
          v7 = FsRtlInitializeBaseMcbEx((PBASE_MCB)(v18 + 40), (POOL_TYPE)*(unsigned __int16 *)(a1 + 10), 0);
          if ( v7 )
          {
            if ( PoolType == PagedPool )
            {
              KeAcquireGuardedMutex(&NtfsMcbMutex);
              NtfsEnchainNewMcbs(v20);
              if ( *(_WORD *)(a1 + 10) != 1 || (*(_DWORD *)(*(_QWORD *)a1 + 512LL) & 0x400000) != 0 )
              {
                *((_QWORD *)v19 + 1) = 0;
              }
              else
              {
                *((_QWORD *)v19 + 2) = MEMORY[0xFFFFF78000000320];
                v21 = qword_140094F28;
                *(_QWORD *)qword_140094F28 = v19;
                *((_QWORD *)v19 + 1) = v21;
                *(_QWORD *)v19 = &NtfsMcbLruQueue;
                qword_140094F28 = (__int64)v19;
                ++NtfsMcbCurrentLevel;
              }
              KeReleaseGuardedMutex(&NtfsMcbMutex);
            }
            *(_QWORD *)(*v10 + v30 + 16) = v19;
            v16 = 0;
            if ( FsRtlLookupBaseMcbEntry(
                   (PBASE_MCB)(v28 + 40),
                   a2 - *(_QWORD *)(*v10 + v15),
                   &Lbn,
                   &SectorCountFromLbn,
                   0,
                   0,
                   &Index) )
            {
              if ( Lbn == -1 || (v7 = FsRtlAddBaseMcbEntry((PBASE_MCB)(v19 + 40), 0, Lbn, SectorCountFromLbn)) != 0 )
              {
                v22 = Index;
                while ( 1 )
                {
                  v27 = ++v22;
                  if ( !FsRtlGetNextBaseMcbEntry((PBASE_MCB)(v28 + 40), v22, &Vbn, &Lbn, &SectorCountFromLbn) )
                    break;
                  if ( Lbn != -1 )
                  {
                    v7 = FsRtlAddBaseMcbEntry(
                           (PBASE_MCB)(v19 + 40),
                           Vbn + *(_QWORD *)(*v10 + v32) - a2,
                           Lbn,
                           SectorCountFromLbn);
                    if ( !v7 )
                      goto LABEL_31;
                  }
                }
                FsRtlTruncateBaseMcb((PBASE_MCB)(v28 + 40), a2 - *(_QWORD *)(*v10 + v32));
              }
            }
          }
        }
        else
        {
          v7 = 0;
        }
LABEL_31:
        if ( v16 )
        {
          if ( *(_WORD *)(a1 + 10) == 1 )
            v23 = &NtfsPagedMcbEntryLookasideList;
          else
            v23 = &NtfsNonPagedMcbEntryLookasideList;
          ExFreeToLookasideListEx(v23, v19);
        }
      }
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140023bd4  mov     rax, rsp
0x140023bd7  mov     [rax+18h], rsi
0x140023bdb  mov     [rax+20h], r9b
0x140023bdf  mov     [rax+10h], rdx
0x140023be3  mov     [rax+8], rcx
0x140023be7  push    rdi
0x140023be8  push    r12
0x140023bea  push    r13
0x140023bec  push    r14
0x140023bee  push    r15
0x140023bf0  sub     rsp, 90h
0x140023bf7  mov     r13d, r8d
0x140023bfa  mov     rdi, rcx
0x140023bfd  mov     eax, [rcx+10h]
0x140023c00  cmp     [rcx+0Ch], eax
0x140023c03  jb      short loc_140023C12
0x140023c05  call    NtfsGrowMcbArray
0x140023c0a  test    al, al
0x140023c0c  jz      loc_140023FBB
0x140023c12  mov     r9d, 1
0x140023c18  mov     r15b, r9b
0x140023c1b  mov     ecx, [rdi+0Ch]
0x140023c1e  lea     esi, [r13+2]
0x140023c22  lea     r14, [rdi+18h]
0x140023c26  lea     r12d, [r13+1]
0x140023c2a  cmp     esi, ecx
0x140023c2c  ja      short loc_140023C81
0x140023c2e  mov     r9, [r14]
0x140023c31  mov     r8d, r13d
0x140023c34  not     r8d
0x140023c37  add     r8d, ecx
0x140023c3a  shl     r8, 5; Size
0x140023c3e  mov     edx, r12d
0x140023c41  shl     rdx, 5
0x140023c45  add     rdx, r9; Src
0x140023c48  mov     ecx, esi
0x140023c4a  shl     rcx, 5
0x140023c4e  add     rcx, r9; void *
0x140023c51  call    memmove
0x140023c56  mov     r9d, 1
0x140023c5c  mov     ecx, [rdi+0Ch]
0x140023c5f  lea     eax, [rcx+1]
0x140023c62  cmp     esi, eax
0x140023c64  jnb     short loc_140023C81
0x140023c66  mov     edx, esi
0x140023c68  shl     rdx, 5
0x140023c6c  add     rdx, [r14]
0x140023c6f  mov     rax, [rdx+10h]
0x140023c73  test    rax, rax
0x140023c76  jz      short loc_140023C7C
0x140023c78  mov     [rax+20h], rdx
0x140023c7c  add     esi, r9d
0x140023c7f  jmp     short loc_140023C5C
0x140023c81  lea     eax, [rcx+1]
0x140023c84  mov     [rdi+0Ch], eax
0x140023c87  mov     edx, r12d
0x140023c8a  shl     rdx, 5
0x140023c8e  mov     [rsp+0B8h+var_48], rdx
0x140023c93  mov     rax, [r14]
0x140023c96  mov     r8, [rsp+0B8h+arg_8]
0x140023c9e  mov     [rdx+rax], r8
0x140023ca2  mov     r12, r13
0x140023ca5  shl     r12, 5
0x140023ca9  mov     [rsp+0B8h+var_38], r12
0x140023cb1  mov     rcx, [r14]
0x140023cb4  mov     rax, [r12+rcx+8]
0x140023cb9  mov     [rdx+rcx+8], rax
0x140023cbe  mov     rax, [r14]
0x140023cc1  mov     qword ptr [rax+rdx+10h], 0
0x140023cca  lea     rcx, [r8-1]
0x140023cce  mov     rax, [r14]
0x140023cd1  mov     [rax+r12+8], rcx
0x140023cd6  cmp     [rsp+0B8h+arg_18], 0
0x140023cde  jnz     loc_140023FB8
0x140023ce4  mov     rax, [r14]
0x140023ce7  mov     rax, [rax+r12+10h]
0x140023cec  mov     [rsp+0B8h+var_58], rax
0x140023cf1  test    rax, rax
0x140023cf4  jz      loc_140023FB8
0x140023cfa  mov     [rsp+0B8h+var_50], 0
0x140023d03  mov     [rsp+0B8h+Vbn], 0
0x140023d0c  mov     [rsp+0B8h+Lbn], 0FFFFFFFFFFFFFFFFh
0x140023d15  mov     [rsp+0B8h+SectorCountFromLbn], 0
0x140023d1e  mov     [rsp+0B8h+var_74], 0
0x140023d26  xor     r13b, r13b
0x140023d29  mov     [rsp+0B8h+var_77], r13b
0x140023d2e  cmp     [rdi+0Ah], r9w
0x140023d33  lea     rcx, NtfsPagedMcbEntryLookasideList
0x140023d3a  jz      short loc_140023D43
0x140023d3c  lea     rcx, NtfsNonPagedMcbEntryLookasideList; Lookaside
0x140023d43  call    cs:__imp_ExAllocateFromLookasideListEx
0x140023d4a  nop     dword ptr [rax+rax+00h]
0x140023d4f  mov     rsi, rax
0x140023d52  mov     [rsp+0B8h+var_50], rax
0x140023d57  test    rax, rax
0x140023d5a  jnz     short loc_140023D69
0x140023d5c  xor     r15b, r15b
0x140023d5f  mov     [rsp+0B8h+var_78], r15b
0x140023d64  jmp     loc_140023F92
0x140023d69  mov     r13b, 1
0x140023d6c  mov     [rsp+0B8h+var_77], r13b
0x140023d71  mov     [rsi+18h], rdi
0x140023d75  mov     rcx, [rsp+0B8h+var_48]
0x140023d7a  add     rcx, [r14]
0x140023d7d  mov     [rsi+20h], rcx
0x140023d81  lea     rcx, [rsi+28h]; Mcb
0x140023d85  xor     r8d, r8d; Flags
0x140023d88  movzx   edx, word ptr [rdi+0Ah]; PoolType
0x140023d8c  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x140023d93  nop     dword ptr [rax+rax+00h]
0x140023d98  mov     r15b, al
0x140023d9b  mov     [rsp+0B8h+var_78], al
0x140023d9f  test    al, al
0x140023da1  jz      loc_140023F92
0x140023da7  mov     r13d, 1
0x140023dad  cmp     cs:PoolType, r13d
0x140023db4  jnz     loc_140023E44
0x140023dba  lea     rcx, NtfsMcbMutex; Mutex
0x140023dc1  call    cs:__imp_KeAcquireGuardedMutex
0x140023dc8  nop     dword ptr [rax+rax+00h]
0x140023dcd  call    NtfsEnchainNewMcbs
0x140023dd2  cmp     [rdi+0Ah], r13w
0x140023dd7  jnz     short loc_140023E29
0x140023dd9  mov     rax, [rdi]
0x140023ddc  test    dword ptr [rax+200h], 400000h
0x140023de6  jnz     short loc_140023E29
0x140023de8  mov     rax, 0FFFFF78000000320h
0x140023df2  mov     rax, [rax]
0x140023df5  mov     [rsi+10h], rax
0x140023df9  mov     rax, cs:qword_140094F28
0x140023e00  mov     [rax], rsi
0x140023e03  mov     [rsi+8], rax
0x140023e07  lea     rax, NtfsMcbLruQueue
0x140023e0e  mov     [rsi], rax
0x140023e11  mov     cs:qword_140094F28, rsi
0x140023e18  mov     eax, cs:NtfsMcbCurrentLevel
0x140023e1e  add     eax, r13d
0x140023e21  mov     cs:NtfsMcbCurrentLevel, eax
0x140023e27  jmp     short loc_140023E31
0x140023e29  mov     qword ptr [rsi+8], 0
0x140023e31  lea     rcx, NtfsMcbMutex; Mutex
0x140023e38  call    cs:__imp_KeReleaseGuardedMutex
0x140023e3f  nop     dword ptr [rax+rax+00h]
0x140023e44  mov     rax, [r14]
0x140023e47  mov     rcx, [rsp+0B8h+var_48]
0x140023e4c  mov     [rax+rcx+10h], rsi
0x140023e51  xor     r13b, r13b
0x140023e54  mov     [rsp+0B8h+var_77], r13b
0x140023e59  mov     rcx, [rsp+0B8h+var_58]
0x140023e5e  add     rcx, 28h ; '('; Mcb
0x140023e62  mov     rax, [r14]
0x140023e65  mov     rdx, [rsp+0B8h+arg_8]
0x140023e6d  sub     rdx, [rax+r12]; Vbn
0x140023e71  lea     rax, [rsp+0B8h+var_74]
0x140023e76  mov     [rsp+0B8h+Index], rax; Index
0x140023e7b  mov     [rsp+0B8h+SectorCountFromStartingLbn], 0; SectorCountFromStartingLbn
0x140023e84  mov     [rsp+0B8h+StartingLbn], 0; StartingLbn
0x140023e8d  lea     r9, [rsp+0B8h+SectorCountFromLbn]; SectorCountFromLbn
0x140023e92  lea     r8, [rsp+0B8h+Lbn]; Lbn
0x140023e97  call    cs:__imp_FsRtlLookupBaseMcbEntry
0x140023e9e  nop     dword ptr [rax+rax+00h]
0x140023ea3  test    al, al
0x140023ea5  jz      loc_140023F92
0x140023eab  mov     r8, [rsp+0B8h+Lbn]; Lbn
0x140023eb0  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140023eb4  jz      short loc_140023EDC
0x140023eb6  mov     r9, [rsp+0B8h+SectorCountFromLbn]; SectorCount
0x140023ebb  xor     edx, edx; Vbn
0x140023ebd  lea     rcx, [rsi+28h]; Mcb
0x140023ec1  call    cs:__imp_FsRtlAddBaseMcbEntry
0x140023ec8  nop     dword ptr [rax+rax+00h]
0x140023ecd  mov     r15b, al
0x140023ed0  mov     [rsp+0B8h+var_78], al
0x140023ed4  test    al, al
0x140023ed6  jz      loc_140023F92
0x140023edc  mov     r12d, [rsp+0B8h+var_74]
0x140023ee1  inc     r12d
0x140023ee4  mov     [rsp+0B8h+var_60], r12d
0x140023ee9  lea     rax, [rsp+0B8h+SectorCountFromLbn]
0x140023eee  mov     [rsp+0B8h+StartingLbn], rax; SectorCount
0x140023ef3  lea     r9, [rsp+0B8h+Lbn]; Lbn
0x140023ef8  lea     r8, [rsp+0B8h+Vbn]; Vbn
0x140023efd  mov     edx, r12d; RunIndex
0x140023f00  mov     rcx, [rsp+0B8h+var_58]
0x140023f05  add     rcx, 28h ; '('; Mcb
0x140023f09  call    cs:__imp_FsRtlGetNextBaseMcbEntry
0x140023f10  nop     dword ptr [rax+rax+00h]
0x140023f15  test    al, al
0x140023f17  jz      short loc_140023F65
0x140023f19  mov     r8, [rsp+0B8h+Lbn]; Lbn
0x140023f1e  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140023f22  jz      short loc_140023F60
0x140023f24  mov     rax, [r14]
0x140023f27  mov     rcx, [rsp+0B8h+var_38]
0x140023f2f  mov     rdx, [rax+rcx]
0x140023f33  sub     rdx, [rsp+0B8h+arg_8]
0x140023f3b  add     rdx, [rsp+0B8h+Vbn]; Vbn
0x140023f40  mov     r9, [rsp+0B8h+SectorCountFromLbn]; SectorCount
0x140023f45  lea     rcx, [rsi+28h]; Mcb
0x140023f49  call    cs:__imp_FsRtlAddBaseMcbEntry
0x140023f50  nop     dword ptr [rax+rax+00h]
0x140023f55  mov     r15b, al
0x140023f58  mov     [rsp+0B8h+var_78], al
0x140023f5c  test    al, al
0x140023f5e  jz      short loc_140023F92
0x140023f60  jmp     loc_140023EE1
0x140023f65  mov     rax, [r14]
0x140023f68  mov     rcx, [rsp+0B8h+var_38]
0x140023f70  mov     rdx, [rsp+0B8h+arg_8]
0x140023f78  sub     rdx, [rax+rcx]; Vbn
0x140023f7c  mov     rcx, [rsp+0B8h+var_58]
0x140023f81  add     rcx, 28h ; '('; Mcb
0x140023f85  call    cs:__imp_FsRtlTruncateBaseMcb
0x140023f8c  nop     dword ptr [rax+rax+00h]
0x140023f91  nop
0x140023f92  test    r13b, r13b
0x140023f95  jz      short loc_140023FB8
0x140023f97  mov     eax, 1
0x140023f9c  mov     rdx, rsi; Entry
0x140023f9f  cmp     [rdi+0Ah], ax
0x140023fa3  jnz     short loc_140023FD5
0x140023fa5  lea     rcx, NtfsPagedMcbEntryLookasideList; Lookaside
0x140023fac  call    cs:__imp_ExFreeToLookasideListEx
0x140023fb3  nop     dword ptr [rax+rax+00h]
0x140023fb8  mov     al, r15b
0x140023fbb  mov     rsi, [rsp+0B8h+arg_10]
0x140023fc3  add     rsp, 90h
0x140023fca  pop     r15
0x140023fcc  pop     r14
0x140023fce  pop     r13
0x140023fd0  pop     r12
0x140023fd2  pop     rdi
0x140023fd3  retn
0x140023fd5  lea     rcx, NtfsNonPagedMcbEntryLookasideList
0x140023fdc  jmp     short loc_140023FAC
0x14005ad47  push    rbp
0x14005ad49  sub     rsp, 40h
0x14005ad4d  mov     rbp, rdx
0x14005ad50  movzx   eax, cl
0x14005ad53  test    cl, cl
0x14005ad55  jz      short loc_14005AD5D
0x14005ad57  mov     al, cs:NtfsStatusDebugFlags
0x14005ad5d  cmp     byte ptr [rbp+41h], 0
0x14005ad61  jz      short loc_14005AD90
0x14005ad63  mov     rax, [rbp+0C0h]
0x14005ad6a  mov     rdx, [rbp+68h]; Entry
0x14005ad6e  cmp     word ptr [rax+0Ah], 1
0x14005ad73  lea     rcx, NtfsPagedMcbEntryLookasideList
0x14005ad7a  jz      short loc_14005AD83
0x14005ad7c  lea     rcx, NtfsNonPagedMcbEntryLookasideList; Lookaside
0x14005ad83  call    cs:__imp_ExFreeToLookasideListEx
0x14005ad8a  nop     dword ptr [rax+rax+00h]
0x14005ad8f  nop
0x14005ad90  add     rsp, 40h
0x14005ad94  pop     rbp
0x14005ad95  retn
```
