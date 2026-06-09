# UlpAllocateFastTracker

- ea: `0x1c00d4a8c`
- end: `0x1c00d4c7d`
- name: `UlpAllocateFastTracker`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00c0360`

## callees

- `0x1c0001118`
- `0x1c0017228`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c008f680`
- `0x1c00961a4`
- `0x1c00adc20`
- `0x1c00d4a8c`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c00d4b1e`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00d4b3c`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00d4b1e`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00d4b3c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00dd149`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00dd149`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00dd0d8`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00dd0d8`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d4b85`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d4b85`

## pseudocode

```c
PSLIST_ENTRY __fastcall UlpAllocateFastTracker(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 a5,
        int a6)
{
  SIZE_T v6; // r12
  unsigned int v8; // r14d
  PSLIST_ENTRY v9; // rbx
  unsigned int v10; // ebp
  int v11; // ecx
  unsigned int v12; // r14d
  __int64 v13; // rdi
  unsigned int v14; // r15d
  unsigned __int64 v15; // rcx
  struct _SLIST_ENTRY *PoolWithTagPriority; // rax
  struct _SLIST_ENTRY *Next; // rax
  __int64 v19; // rbx
  unsigned int v20; // r8d
  unsigned int v21; // eax
  __int64 v22; // rdi
  __int64 v23; // rcx
  unsigned int v24; // r8d
  unsigned int v25; // eax

  v6 = a4;
  v8 = a2;
  v9 = 0;
  v10 = 24 * a6;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qLLLlL(a1, a2, a1, (unsigned int)a2, a3, a4, a5, a6);
  v11 = UlVariableHeaderSize + v8;
  if ( (unsigned int)UlVariableHeaderSize + v8 >= (unsigned int)UlVariableHeaderSize && v11 + a3 >= a3 )
  {
    if ( !a5 || a3 > 0x800 || v8 > 0x200 || v10 > UlH3DefaultPairSize )
    {
      v12 = a3 + (v8 != 0 ? v11 : 0);
      v13 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, v12) + 7) & 0xFFFFFFF8;
      v14 = (MmSizeOfMdl((PVOID)0xFFF, v6) + 7) & 0xFFFFFFF8;
      v15 = v14 + 656LL + v12 + (unsigned __int64)v10 + 3 * v13;
      if ( v15 > 0xFFFFFFFF )
      {
        v9 = 0;
        goto LABEL_13;
      }
      PoolWithTagPriority = (struct _SLIST_ENTRY *)ExAllocatePoolWithTagPriority(
                                                     (POOL_TYPE)512,
                                                     (unsigned int)v15,
                                                     0x55466C55u,
                                                     LowPoolPriority);
      v9 = PoolWithTagPriority;
      if ( !PoolWithTagPriority )
        goto LABEL_13;
      memset(PoolWithTagPriority, 0, 0x290u);
      *((_DWORD *)&v9[5].Next + 2) = v12;
      UlInitializeFastTrackerPool((_DWORD)v9, v13, v14, a6, v10);
      goto LABEL_9;
    }
    if ( UxCompactMode )
    {
      v19 = qword_1C00741E0;
      v20 = KeGetCurrentNodeNumber() + 1;
      v21 = *(_DWORD *)v19 - 1;
      if ( v20 < *(_DWORD *)v19 )
        v21 = v20;
      v22 = *(_QWORD *)(*(_QWORD *)(v19 + 32) + 8LL * v21);
      if ( *(_BYTE *)(v22 + 112) )
        goto LABEL_30;
      v23 = v19;
    }
    else
    {
      v23 = qword_1C00741E0;
      v24 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v25 = *(_DWORD *)qword_1C00741E0 - 1;
      if ( v24 < *(_DWORD *)qword_1C00741E0 )
        v25 = v24;
      v22 = *(_QWORD *)(*(_QWORD *)(qword_1C00741E0 + 32) + 8LL * v25);
      if ( *(_BYTE *)(v22 + 112) )
        goto LABEL_30;
    }
    PplpLazyInitializeLookasideList(v23, v22);
LABEL_30:
    ++*(_DWORD *)(v22 + 20);
    v9 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v22);
    if ( !v9 )
    {
      ++*(_DWORD *)(v22 + 24);
      v9 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v22 + 48))(
                           *(unsigned int *)(v22 + 36),
                           *(unsigned int *)(v22 + 44),
                           *(unsigned int *)(v22 + 40),
                           v22);
    }
LABEL_9:
    if ( v9 )
    {
      LODWORD(v9[1].Next) = 1430678613;
      v9[9].Next = 0;
      *((_QWORD *)&v9[9].Next + 1) = 0;
      v9[11].Next = 0;
      *((_QWORD *)&v9[10].Next + 1) = 0;
      v9[10].Next = 0;
      v9[5].Next = 0;
      BYTE5(v9[1].Next) = 0;
      *((_DWORD *)&v9[16].Next + 2) = 0;
      v9[17] = 0;
      memset(&v9[11].Next + 1, 0, 0x50u);
      UxDuoInitializeCollection(&v9[20]);
      if ( a6 )
        Next = v9[7].Next;
      else
        Next = (struct _SLIST_ENTRY *)*((_QWORD *)&v9[6].Next + 1);
      *((_QWORD *)&v9[7].Next + 1) = Next;
      *((_DWORD *)&v9[18].Next + 2) = 0;
    }
  }
LABEL_13:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_q(52, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1c00d4a8c  mov     [rsp+arg_0], rbx
0x1c00d4a91  mov     [rsp+arg_8], rbp
0x1c00d4a96  mov     [rsp+arg_10], rsi
0x1c00d4a9b  push    rdi
0x1c00d4a9c  push    r12
0x1c00d4a9e  push    r13
0x1c00d4aa0  push    r14
0x1c00d4aa2  push    r15
0x1c00d4aa4  sub     rsp, 40h
0x1c00d4aa8  mov     esi, [rsp+68h+arg_28]
0x1c00d4aaf  xor     r13d, r13d
0x1c00d4ab2  mov     r12d, r9d
0x1c00d4ab5  mov     edi, r8d
0x1c00d4ab8  mov     r14d, edx
0x1c00d4abb  mov     ebx, r13d
0x1c00d4abe  lea     ebp, [rsi+rsi*2]
0x1c00d4ac1  shl     ebp, 3
0x1c00d4ac4  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00d4ace  movzx   r15d, [rsp+68h+arg_20]
0x1c00d4ad7  jnz     loc_1C00DD080
0x1c00d4add  mov     eax, cs:UlVariableHeaderSize
0x1c00d4ae3  lea     ecx, [rax+r14]
0x1c00d4ae7  cmp     ecx, eax
0x1c00d4ae9  jb      loc_1C00D4C41
0x1c00d4aef  lea     eax, [rcx+rdi]
0x1c00d4af2  cmp     eax, edi
0x1c00d4af4  jb      loc_1C00D4C41
0x1c00d4afa  test    r15b, r15b
0x1c00d4afd  jnz     loc_1C00DD0A3
0x1c00d4b03  neg     r14d
0x1c00d4b06  mov     r15d, 0FFFh
0x1c00d4b0c  sbb     r14d, r14d
0x1c00d4b0f  and     r14d, ecx
0x1c00d4b12  mov     ecx, r15d; Base
0x1c00d4b15  add     r14d, edi
0x1c00d4b18  mov     edx, r14d; Length
0x1c00d4b1b  mov     ebx, r14d
0x1c00d4b1e  call    cs:__imp_MmSizeOfMdl
0x1c00d4b25  nop     dword ptr [rax+rax+00h]
0x1c00d4b2a  mov     r13d, 0FFFFFFF8h
0x1c00d4b30  mov     rdx, r12; Length
0x1c00d4b33  mov     ecx, r15d; Base
0x1c00d4b36  lea     edi, [rax+7]
0x1c00d4b39  and     edi, r13d
0x1c00d4b3c  call    cs:__imp_MmSizeOfMdl
0x1c00d4b43  nop     dword ptr [rax+rax+00h]
0x1c00d4b48  mov     edx, ebp
0x1c00d4b4a  lea     rcx, [rdi+rdi*2]
0x1c00d4b4e  add     rdx, rbx
0x1c00d4b51  add     rcx, rdx
0x1c00d4b54  lea     r15d, [rax+7]
0x1c00d4b58  and     r15d, r13d
0x1c00d4b5b  mov     eax, r15d
0x1c00d4b5e  add     rax, 290h
0x1c00d4b64  add     rcx, rax
0x1c00d4b67  mov     eax, 0FFFFFFFFh
0x1c00d4b6c  cmp     rcx, rax
0x1c00d4b6f  ja      loc_1C00D4C73
0x1c00d4b75  mov     edx, ecx; NumberOfBytes
0x1c00d4b77  xor     r9d, r9d; Priority
0x1c00d4b7a  mov     ecx, 200h; PoolType
0x1c00d4b7f  mov     r8d, 55466C55h; Tag
0x1c00d4b85  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d4b8c  nop     dword ptr [rax+rax+00h]
0x1c00d4b91  xor     r13d, r13d
0x1c00d4b94  mov     rbx, rax
0x1c00d4b97  test    rax, rax
0x1c00d4b9a  jz      loc_1C00D4C41
0x1c00d4ba0  xor     edx, edx; Val
0x1c00d4ba2  mov     r8d, 290h; Size
0x1c00d4ba8  mov     rcx, rax; void *
0x1c00d4bab  call    memset
0x1c00d4bb0  mov     r9d, esi
0x1c00d4bb3  mov     [rbx+58h], r14d
0x1c00d4bb7  mov     r8d, r15d
0x1c00d4bba  mov     [rsp+68h+var_48], ebp
0x1c00d4bbe  mov     edx, edi
0x1c00d4bc0  mov     rcx, rbx
0x1c00d4bc3  call    UlInitializeFastTrackerPool
0x1c00d4bc8  test    rbx, rbx
0x1c00d4bcb  jz      short loc_1C00D4C41
0x1c00d4bcd  xor     edx, edx; Val
0x1c00d4bcf  mov     dword ptr [rbx+10h], 55466C55h
0x1c00d4bd6  xorps   xmm0, xmm0
0x1c00d4bd9  mov     [rbx+90h], r13
0x1c00d4be0  mov     [rbx+98h], r13
0x1c00d4be7  lea     rcx, [rbx+0B8h]; void *
0x1c00d4bee  mov     [rbx+0B0h], r13
0x1c00d4bf5  mov     [rbx+0A8h], r13
0x1c00d4bfc  lea     r8d, [rdx+50h]; Size
0x1c00d4c00  mov     [rbx+0A0h], r13
0x1c00d4c07  mov     [rbx+50h], r13
0x1c00d4c0b  mov     [rbx+15h], r13b
0x1c00d4c0f  mov     [rbx+108h], r13d
0x1c00d4c16  movups  xmmword ptr [rbx+110h], xmm0
0x1c00d4c1d  call    memset
0x1c00d4c22  lea     rcx, [rbx+140h]
0x1c00d4c29  call    UxDuoInitializeCollection
0x1c00d4c2e  test    esi, esi
0x1c00d4c30  jnz     short loc_1C00D4C77
0x1c00d4c32  mov     rax, [rbx+68h]
0x1c00d4c36  mov     [rbx+78h], rax
0x1c00d4c3a  mov     [rbx+128h], r13d
0x1c00d4c41  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00d4c4b  jnz     loc_1C00DD183
0x1c00d4c51  lea     r11, [rsp+68h+var_28]
0x1c00d4c56  mov     rax, rbx
0x1c00d4c59  mov     rbx, [r11+30h]
0x1c00d4c5d  mov     rbp, [r11+38h]
0x1c00d4c61  mov     rsi, [r11+40h]
0x1c00d4c65  mov     rsp, r11
0x1c00d4c68  pop     r15
0x1c00d4c6a  pop     r14
0x1c00d4c6c  pop     r13
0x1c00d4c6e  pop     r12
0x1c00d4c70  pop     rdi
0x1c00d4c71  retn
0x1c00d4c73  xor     ebx, ebx
0x1c00d4c75  jmp     short loc_1C00D4C41
0x1c00d4c77  mov     rax, [rbx+70h]
0x1c00d4c7b  jmp     short loc_1C00D4C36
0x1c00dd080  mov     [rsp+68h+var_30], esi
0x1c00dd084  mov     r9d, r14d
0x1c00dd087  mov     [rsp+68h+var_38], r15d
0x1c00dd08c  mov     r8, rcx
0x1c00dd08f  mov     [rsp+68h+var_40], r12d
0x1c00dd094  mov     [rsp+68h+var_48], edi
0x1c00dd098  call    WPP_SF_qLLLlL
0x1c00dd09d  nop
0x1c00dd09e  jmp     loc_1C00D4ADD
0x1c00dd0a3  cmp     edi, 800h
0x1c00dd0a9  ja      loc_1C00D4B03
0x1c00dd0af  cmp     r14d, 200h
0x1c00dd0b6  ja      loc_1C00D4B03
0x1c00dd0bc  cmp     ebp, cs:UlH3DefaultPairSize
0x1c00dd0c2  ja      loc_1C00D4B03
0x1c00dd0c8  cmp     cs:UxCompactMode, r13b
0x1c00dd0cf  jz      short loc_1C00DD10C
0x1c00dd0d1  mov     rbx, cs:qword_1C00741E0
0x1c00dd0d8  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00dd0df  nop     dword ptr [rax+rax+00h]
0x1c00dd0e4  mov     edx, [rbx]
0x1c00dd0e6  movzx   r8d, ax
0x1c00dd0ea  inc     r8d
0x1c00dd0ed  cmp     r8d, edx
0x1c00dd0f0  lea     eax, [rdx-1]
0x1c00dd0f3  cmovb   eax, r8d
0x1c00dd0f7  mov     edx, eax
0x1c00dd0f9  mov     rax, [rbx+20h]
0x1c00dd0fd  mov     rdi, [rax+rdx*8]
0x1c00dd101  cmp     [rdi+70h], r13b
0x1c00dd105  jnz     short loc_1C00DD143
0x1c00dd107  mov     rcx, rbx
0x1c00dd10a  jmp     short loc_1C00DD13B
0x1c00dd10c  mov     eax, gs:1A4h
0x1c00dd114  mov     rcx, cs:qword_1C00741E0
0x1c00dd11b  lea     r8d, [rax+1]
0x1c00dd11f  mov     edx, [rcx]
0x1c00dd121  cmp     r8d, edx
0x1c00dd124  lea     eax, [rdx-1]
0x1c00dd127  cmovb   eax, r8d
0x1c00dd12b  mov     edx, eax
0x1c00dd12d  mov     rax, [rcx+20h]
0x1c00dd131  mov     rdi, [rax+rdx*8]
0x1c00dd135  cmp     [rdi+70h], r13b
0x1c00dd139  jnz     short loc_1C00DD143
0x1c00dd13b  mov     rdx, rdi
0x1c00dd13e  call    PplpLazyInitializeLookasideList
0x1c00dd143  inc     dword ptr [rdi+14h]
0x1c00dd146  mov     rcx, rdi; ListHead
0x1c00dd149  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00dd150  nop     dword ptr [rax+rax+00h]
0x1c00dd155  mov     rbx, rax
0x1c00dd158  test    rax, rax
0x1c00dd15b  jnz     loc_1C00D4BC8
0x1c00dd161  inc     dword ptr [rdi+18h]
0x1c00dd164  mov     r9, rdi
0x1c00dd167  mov     edx, [rdi+2Ch]
0x1c00dd16a  mov     rax, [rdi+30h]
0x1c00dd16e  mov     r8d, [rdi+28h]
0x1c00dd172  mov     ecx, [rdi+24h]
0x1c00dd175  call    cs:__guard_dispatch_icall_fptr
0x1c00dd17b  mov     rbx, rax
0x1c00dd17e  jmp     loc_1C00D4BC8
0x1c00dd183  mov     ecx, 34h ; '4'
0x1c00dd188  lea     rdx, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids
0x1c00dd18f  mov     r8, rbx
0x1c00dd192  call    WPP_SF_q
0x1c00dd197  nop
0x1c00dd198  jmp     loc_1C00D4C51
```
