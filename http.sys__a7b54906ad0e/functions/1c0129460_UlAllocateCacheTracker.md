# UlAllocateCacheTracker

- ea: `0x1c0129460`
- end: `0x1c01297a4`
- name: `UlAllocateCacheTracker`
- size: `836`
- prototype: `__int64 __fastcall(SIZE_T Length, SIZE_T)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1c0046388`
- `0x1c012422c`
- `0x1c0124ec0`

## callees

- `0x1c0001118`
- `0x1c000b280`
- `0x1c001b610`
- `0x1c008f680`
- `0x1c009a2bc`
- `0x1c00adc20`
- `0x1c0129460`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c01295e5`
- `ntoskrnl!MmSizeOfMdl` at `0x1c01295fa`
- `ntoskrnl!MmSizeOfMdl` at `0x1c01295e5`
- `ntoskrnl!MmSizeOfMdl` at `0x1c01295fa`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c012975b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c012975b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0129550`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0129550`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c01294df`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c01294df`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0129661`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0129661`

## pseudocode

```c
PSLIST_ENTRY __fastcall UlAllocateCacheTracker(SIZE_T Length, __int64 a2, unsigned __int8 a3, unsigned int a4)
{
  SIZE_T v6; // rsi
  SIZE_T v7; // rbx
  __int64 v8; // rbx
  unsigned int v9; // r8d
  unsigned int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // eax
  PSLIST_ENTRY v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(__int64, __int64, __int64, __int64); // rax
  SIZE_T v20; // rbx
  __int64 v21; // rsi
  __int64 v22; // r14
  unsigned __int64 v23; // rax
  char *PoolWithTagPriority; // rax
  __int64 v25; // rdx
  struct _SLIST_ENTRY *v26; // rcx
  char *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r10
  struct _SLIST_ENTRY *Next; // r9
  unsigned __int64 v31; // rdx
  __int64 v32; // r8

  v6 = (unsigned int)a2;
  v7 = (unsigned int)Length;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_LLlL(Length, a2, (unsigned int)Length, (unsigned int)a2, a3);
  if ( a4 )
    a4 += UlH3ExtraHeaderCount;
  if ( (unsigned int)v7 <= 0x200 && (unsigned int)v6 <= 0x40000 && a4 <= 0x14 )
  {
    if ( UxCompactMode )
    {
      v8 = qword_1C00741B0;
      v9 = KeGetCurrentNodeNumber() + 1;
      v10 = *(_DWORD *)v8 - 1;
      if ( v9 < *(_DWORD *)v8 )
        v10 = v9;
      v11 = *(_QWORD *)(*(_QWORD *)(v8 + 32) + 8LL * v10);
      if ( *(_BYTE *)(v11 + 112) )
        goto LABEL_17;
      v12 = v8;
    }
    else
    {
      v12 = qword_1C00741B0;
      v13 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v14 = *(_DWORD *)qword_1C00741B0 - 1;
      if ( v13 < *(_DWORD *)qword_1C00741B0 )
        v14 = v13;
      v11 = *(_QWORD *)(*(_QWORD *)(qword_1C00741B0 + 32) + 8LL * v14);
      if ( *(_BYTE *)(v11 + 112) )
        goto LABEL_17;
    }
    PplpLazyInitializeLookasideList(v12, v11);
LABEL_17:
    ++*(_DWORD *)(v11 + 20);
    v15 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v11);
    if ( !v15 )
    {
      v16 = *(unsigned int *)(v11 + 40);
      v17 = *(unsigned int *)(v11 + 44);
      v18 = *(unsigned int *)(v11 + 36);
      v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v11 + 48);
      ++*(_DWORD *)(v11 + 24);
      v15 = (PSLIST_ENTRY)v19(v18, v17, v16, v11);
    }
    if ( v15 )
    {
      LODWORD(v15[1].Next) = 1094937685;
      *((_QWORD *)&v15[8].Next + 1) = 0;
      v15[9].Next = 0;
      BYTE5(v15[1].Next) = a3;
      LODWORD(v15[11].Next) = 0;
      BYTE4(v15[1].Next) = 1;
      LODWORD(v15[12].Next) = 0;
      *((_DWORD *)&v15[12].Next + 3) = 0;
      v15[2].Next = 0;
      v15[3].Next = 0;
      v15[4].Next = 0;
      UxDuoInitializeCollection(&v15[13].Next + 1);
    }
    goto LABEL_25;
  }
  v20 = MmSizeOfMdl((PVOID)0xFFF, v7);
  v21 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, v6) + 7) & 0xFFFFFFF8;
  v22 = (v20 + 7) & 0xFFFFFFF8;
  v23 = v21 + (unsigned int)UlVariableHeaderSize + 640LL + v22 + (unsigned int)UlVariableHeadersMdlLength + 24LL * a4;
  if ( v23 <= 0xFFFFFFFF )
  {
    PoolWithTagPriority = (char *)ExAllocatePoolWithTagPriority(
                                    (POOL_TYPE)512,
                                    (unsigned int)v23,
                                    0x41436C55u,
                                    LowPoolPriority);
    v15 = (PSLIST_ENTRY)PoolWithTagPriority;
    if ( PoolWithTagPriority )
    {
      strcpy(PoolWithTagPriority + 16, "UlCA");
      *((_QWORD *)PoolWithTagPriority + 17) = 0;
      *((_QWORD *)PoolWithTagPriority + 18) = 0;
      PoolWithTagPriority[21] = a3;
      *((_DWORD *)PoolWithTagPriority + 44) = 0;
      *((_DWORD *)PoolWithTagPriority + 48) = 0;
      *((_DWORD *)PoolWithTagPriority + 51) = 0;
      *((_QWORD *)PoolWithTagPriority + 4) = 0;
      *((_QWORD *)PoolWithTagPriority + 6) = 0;
      *((_QWORD *)PoolWithTagPriority + 8) = 0;
      UxDuoInitializeCollection(PoolWithTagPriority + 216);
      v25 = (unsigned int)UlVariableHeadersMdlLength;
      v26 = (PSLIST_ENTRY)((char *)v15 + v22 + 640);
      *((_QWORD *)&v15[6].Next + 1) = v15 + 40;
      v27 = (char *)v26 + v25;
      v15[7].Next = v26;
      v28 = (unsigned int)UlVariableHeaderSize;
      *((_QWORD *)&v15[7].Next + 1) = v27;
      *((_DWORD *)&v15[5].Next + 2) = v28;
      v15[6].Next = (struct _SLIST_ENTRY *)&v27[v21];
      UlInitializeParsedHeaders(&v15[11].Next + 1, &v27[v21 + v28], a4);
      v29 = *((unsigned int *)&v15[5].Next + 2);
      Next = v15[7].Next;
      v31 = (unsigned __int64)v15[6].Next & 0xFFFFFFFFFFFFF000uLL;
      v32 = (__int64)v15[6].Next & 0xFFF;
      Next->Next = 0;
      *((_WORD *)&Next->Next + 4) = 8 * (((unsigned __int64)(v29 + v32 + 4095) >> 12) + 6);
      *((_WORD *)&Next->Next + 5) = 0;
      Next[2].Next = (struct _SLIST_ENTRY *)v31;
      *((_DWORD *)&Next[2].Next + 3) = v32;
      *((_DWORD *)&Next[2].Next + 2) = v29;
      MmBuildMdlForNonPagedPool((PMDL)v15[7].Next);
    }
  }
  else
  {
    v15 = 0;
  }
LABEL_25:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_q(108, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x1c0129460  mov     rax, rsp
0x1c0129463  mov     [rax+8], rbx
0x1c0129467  mov     [rax+10h], rbp
0x1c012946b  mov     [rax+18h], rsi
0x1c012946f  push    rdi
0x1c0129470  push    r14
0x1c0129472  push    r15
0x1c0129474  sub     rsp, 30h
0x1c0129478  mov     edi, r9d
0x1c012947b  movzx   ebp, r8b
0x1c012947f  mov     esi, edx
0x1c0129481  mov     ebx, ecx
0x1c0129483  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c012948d  jz      short loc_1C01294A1
0x1c012948f  mov     [rax-20h], r9d
0x1c0129493  mov     r8d, ebx
0x1c0129496  mov     r9d, esi
0x1c0129499  mov     [rax-28h], ebp
0x1c012949c  call    WPP_SF_LLlL
0x1c01294a1  xor     r15d, r15d
0x1c01294a4  test    edi, edi
0x1c01294a6  jz      short loc_1C01294AE
0x1c01294a8  add     edi, cs:UlH3ExtraHeaderCount
0x1c01294ae  cmp     ebx, 200h
0x1c01294b4  ja      loc_1C01295D9
0x1c01294ba  cmp     esi, 40000h
0x1c01294c0  ja      loc_1C01295D9
0x1c01294c6  cmp     edi, 14h
0x1c01294c9  ja      loc_1C01295D9
0x1c01294cf  cmp     cs:UxCompactMode, r15b
0x1c01294d6  jz      short loc_1C0129513
0x1c01294d8  mov     rbx, cs:qword_1C00741B0
0x1c01294df  call    cs:__imp_KeGetCurrentNodeNumber
0x1c01294e6  nop     dword ptr [rax+rax+00h]
0x1c01294eb  mov     edx, [rbx]
0x1c01294ed  movzx   r8d, ax
0x1c01294f1  inc     r8d
0x1c01294f4  cmp     r8d, edx
0x1c01294f7  lea     eax, [rdx-1]
0x1c01294fa  cmovb   eax, r8d
0x1c01294fe  mov     edx, eax
0x1c0129500  mov     rax, [rbx+20h]
0x1c0129504  mov     rdi, [rax+rdx*8]
0x1c0129508  cmp     [rdi+70h], r15b
0x1c012950c  jnz     short loc_1C012954A
0x1c012950e  mov     rcx, rbx
0x1c0129511  jmp     short loc_1C0129542
0x1c0129513  mov     eax, gs:1A4h
0x1c012951b  mov     rcx, cs:qword_1C00741B0
0x1c0129522  lea     r8d, [rax+1]
0x1c0129526  mov     edx, [rcx]
0x1c0129528  cmp     r8d, edx
0x1c012952b  lea     eax, [rdx-1]
0x1c012952e  cmovb   eax, r8d
0x1c0129532  mov     edx, eax
0x1c0129534  mov     rax, [rcx+20h]
0x1c0129538  mov     rdi, [rax+rdx*8]
0x1c012953c  cmp     [rdi+70h], r15b
0x1c0129540  jnz     short loc_1C012954A
0x1c0129542  mov     rdx, rdi
0x1c0129545  call    PplpLazyInitializeLookasideList
0x1c012954a  inc     dword ptr [rdi+14h]
0x1c012954d  mov     rcx, rdi; ListHead
0x1c0129550  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0129557  nop     dword ptr [rax+rax+00h]
0x1c012955c  mov     rbx, rax
0x1c012955f  test    rax, rax
0x1c0129562  jnz     short loc_1C0129581
0x1c0129564  mov     r8d, [rdi+28h]
0x1c0129568  mov     r9, rdi
0x1c012956b  mov     edx, [rdi+2Ch]
0x1c012956e  mov     ecx, [rdi+24h]
0x1c0129571  mov     rax, [rdi+30h]
0x1c0129575  inc     dword ptr [rdi+18h]
0x1c0129578  call    cs:__guard_dispatch_icall_fptr
0x1c012957e  mov     rbx, rax
0x1c0129581  test    rbx, rbx
0x1c0129584  jz      loc_1C0129767
0x1c012958a  mov     dword ptr [rbx+10h], 41436C55h
0x1c0129591  lea     rcx, [rbx+0D8h]
0x1c0129598  mov     [rbx+88h], r15
0x1c012959f  mov     [rbx+90h], r15
0x1c01295a6  mov     [rbx+15h], bpl
0x1c01295aa  mov     [rbx+0B0h], r15d
0x1c01295b1  mov     byte ptr [rbx+14h], 1
0x1c01295b5  mov     [rbx+0C0h], r15d
0x1c01295bc  mov     [rbx+0CCh], r15d
0x1c01295c3  mov     [rbx+20h], r15
0x1c01295c7  mov     [rbx+30h], r15
0x1c01295cb  mov     [rbx+40h], r15
0x1c01295cf  call    UxDuoInitializeCollection
0x1c01295d4  jmp     loc_1C0129767
0x1c01295d9  mov     r14d, 0FFFh
0x1c01295df  mov     rdx, rbx; Length
0x1c01295e2  mov     ecx, r14d; Base
0x1c01295e5  call    cs:__imp_MmSizeOfMdl
0x1c01295ec  nop     dword ptr [rax+rax+00h]
0x1c01295f1  mov     rdx, rsi; Length
0x1c01295f4  mov     ecx, r14d; Base
0x1c01295f7  mov     rbx, rax
0x1c01295fa  call    cs:__imp_MmSizeOfMdl
0x1c0129601  nop     dword ptr [rax+rax+00h]
0x1c0129606  mov     ecx, cs:UlVariableHeaderSize
0x1c012960c  lea     r14, [rbx+7]
0x1c0129610  add     rcx, 280h
0x1c0129617  lea     rsi, [rax+7]
0x1c012961b  mov     eax, 0FFFFFFF8h
0x1c0129620  and     rsi, rax
0x1c0129623  and     r14, rax
0x1c0129626  mov     eax, edi
0x1c0129628  lea     rdx, [rax+rax*2]
0x1c012962c  mov     eax, cs:UlVariableHeadersMdlLength
0x1c0129632  add     rax, r14
0x1c0129635  lea     rax, [rax+rdx*8]
0x1c0129639  add     rax, rcx
0x1c012963c  mov     ecx, 0FFFFFFFFh
0x1c0129641  add     rax, rsi
0x1c0129644  cmp     rax, rcx
0x1c0129647  jbe     short loc_1C0129651
0x1c0129649  mov     rbx, r15
0x1c012964c  jmp     loc_1C0129767
0x1c0129651  mov     edx, eax; NumberOfBytes
0x1c0129653  xor     r9d, r9d; Priority
0x1c0129656  mov     ecx, 200h; PoolType
0x1c012965b  mov     r8d, 41436C55h; Tag
0x1c0129661  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0129668  nop     dword ptr [rax+rax+00h]
0x1c012966d  mov     rbx, rax
0x1c0129670  test    rax, rax
0x1c0129673  jz      loc_1C0129767
0x1c0129679  mov     dword ptr [rax+10h], 41436C55h
0x1c0129680  lea     rcx, [rax+0D8h]
0x1c0129687  mov     [rax+88h], r15
0x1c012968e  mov     [rax+90h], r15
0x1c0129695  mov     [rax+15h], bpl
0x1c0129699  mov     [rax+0B0h], r15d
0x1c01296a0  mov     [rax+14h], r15b
0x1c01296a4  mov     [rax+0C0h], r15d
0x1c01296ab  mov     [rax+0CCh], r15d
0x1c01296b2  mov     [rax+20h], r15
0x1c01296b6  mov     [rax+30h], r15
0x1c01296ba  mov     [rax+40h], r15
0x1c01296be  call    UxDuoInitializeCollection
0x1c01296c3  mov     edx, cs:UlVariableHeadersMdlLength
0x1c01296c9  lea     rax, [rbx+280h]
0x1c01296d0  lea     rcx, [rax+r14]
0x1c01296d4  mov     [rbx+68h], rax
0x1c01296d8  add     rdx, rcx
0x1c01296db  mov     [rbx+70h], rcx
0x1c01296df  mov     ecx, cs:UlVariableHeaderSize
0x1c01296e5  mov     r8d, edi
0x1c01296e8  mov     [rbx+78h], rdx
0x1c01296ec  mov     [rbx+58h], ecx
0x1c01296ef  lea     rax, [rsi+rdx]
0x1c01296f3  lea     rdx, [rax+rcx]
0x1c01296f7  mov     [rbx+60h], rax
0x1c01296fb  lea     rcx, [rbx+0B8h]
0x1c0129702  call    UlInitializeParsedHeaders
0x1c0129707  mov     rdx, [rbx+60h]
0x1c012970b  mov     r11d, 0FFFh
0x1c0129711  mov     r10d, [rbx+58h]
0x1c0129715  mov     r8d, edx
0x1c0129718  mov     r9, [rbx+70h]
0x1c012971c  mov     ecx, r8d
0x1c012971f  and     rcx, r11
0x1c0129722  and     rdx, 0FFFFFFFFFFFFF000h
0x1c0129729  add     rcx, r11
0x1c012972c  and     r8d, r11d
0x1c012972f  add     rcx, r10
0x1c0129732  shr     rcx, 0Ch
0x1c0129736  add     cx, 6
0x1c012973a  mov     [r9], r15
0x1c012973d  shl     cx, 3
0x1c0129741  mov     [r9+8], cx
0x1c0129746  mov     [r9+0Ah], r15w
0x1c012974b  mov     [r9+20h], rdx
0x1c012974f  mov     [r9+2Ch], r8d
0x1c0129753  mov     [r9+28h], r10d
0x1c0129757  mov     rcx, [rbx+70h]; MemoryDescriptorList
0x1c012975b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1c0129762  nop     dword ptr [rax+rax+00h]
0x1c0129767  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c0129771  jz      short loc_1C0129787
0x1c0129773  mov     ecx, 6Ch ; 'l'
0x1c0129778  lea     rdx, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids
0x1c012977f  mov     r8, rbx
0x1c0129782  call    WPP_SF_q
0x1c0129787  mov     rbp, [rsp+48h+arg_8]
0x1c012978c  mov     rax, rbx
0x1c012978f  mov     rbx, [rsp+48h+arg_0]
0x1c0129794  mov     rsi, [rsp+48h+arg_10]
0x1c0129799  add     rsp, 30h
0x1c012979d  pop     r15
0x1c012979f  pop     r14
0x1c01297a1  pop     rdi
0x1c01297a2  retn
```
