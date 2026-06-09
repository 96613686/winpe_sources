# VDS::ReadVds(EXTENTAD)

- ea: `0x18006a43c`
- end: `0x18006a7ce`
- name: `?ReadVds@VDS@@AEAAEUEXTENTAD@@@Z`
- size: `914`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18006a3c0`
- `0x18006a43c`

## callees

- `0x180001670`
- `0x180005040`
- `0x1800515ec`
- `0x18005fae0`
- `0x18006a43c`
- `0x18006c50c`
- `0x18006c6d0`
- `0x18006cda0`
- `0x18006cfc0`
- `0x18006f3a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006a630`
- `ntdll!RtlFreeHeap` at `0x18006a679`
- `ntdll!RtlFreeHeap` at `0x18006a6f7`
- `ntdll!RtlFreeHeap` at `0x18006a7ae`
- `ntdll!RtlFreeHeap` at `0x18006a630`
- `ntdll!RtlFreeHeap` at `0x18006a679`
- `ntdll!RtlFreeHeap` at `0x18006a6f7`
- `ntdll!RtlFreeHeap` at `0x18006a7ae`

## pseudocode

```c
char __fastcall VDS::ReadVds(__int64 a1, unsigned __int64 a2)
{
  UDF_SA *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // r14
  unsigned int SectorSize; // eax
  unsigned __int64 v7; // r15
  unsigned int i; // esi
  struct UDF_SA *v9; // rdx
  unsigned __int8 *v10; // rbx
  __int64 v12; // rdx
  UNALLOCATED_SPACE_DESCRIPTOR *v13; // rax
  UNALLOCATED_SPACE_DESCRIPTOR *v14; // rbx
  const struct CLASS_DESCRIPTOR *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned __int8 v18; // r8
  _DWORD *v19; // r8
  _DWORD *v20; // r8
  char v21; // dl
  unsigned __int64 v22; // rcx
  _DWORD *v23; // r8
  _DWORD *v24; // r8
  _QWORD v25[2]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v26; // [rsp+40h] [rbp-10h]
  __int16 v27; // [rsp+48h] [rbp-8h]
  bool v28; // [rsp+4Ah] [rbp-6h]
  int v29; // [rsp+4Ch] [rbp-4h]
  unsigned int v30; // [rsp+80h] [rbp+30h] BYREF

  v25[0] = &DESCRIPTOR::`vftable';
  v3 = *(UDF_SA **)(a1 + 16);
  v4 = a2;
  v25[1] = DESCRIPTOR_cd;
  v29 = 0;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  v5 = HIDWORD(a2);
  SectorSize = UDF_SA::QuerySectorSize(v3);
  v30 = 0;
  v7 = (SectorSize + (unsigned __int64)v4 - 1) / SectorSize;
  if ( !(unsigned __int8)NUMBER_SET::Add(*(_QWORD *)(a1 + 80), v5, (unsigned int)v7) )
    goto LABEL_43;
  for ( i = 0; ; i += v30 )
  {
    while ( 1 )
    {
      if ( i >= (unsigned int)v7 )
      {
LABEL_14:
        DESCRIPTOR::~DESCRIPTOR((DESCRIPTOR *)v25);
        return 1;
      }
      DESCRIPTOR::Destroy((DESCRIPTOR *)v25);
      v9 = *(struct UDF_SA **)(a1 + 16);
      v29 = i + v5;
      v27 = 0;
      if ( DESCRIPTOR::Read((DESCRIPTOR *)v25, v9, &v30, 1u) )
        break;
      ++i;
    }
    if ( !DESCRIPTOR::Verify((DESCRIPTOR *)v25) )
      continue;
    v10 = v26;
    if ( *(_WORD *)v26 == 1 )
    {
      v24 = *(_DWORD **)(a1 + 40);
      if ( v24 )
      {
        v28 = v28;
        if ( v24[4] >= *((_DWORD *)v26 + 4) )
          continue;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
        *(_QWORD *)(a1 + 40) = v26;
      }
      else
      {
        *(_QWORD *)(a1 + 40) = v26;
      }
      goto LABEL_48;
    }
    if ( *(_WORD *)v26 == 3 )
    {
      v28 = v28;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_9d30ce6518fc32679771b1918a9f0ec4_Traceguids,
          *((unsigned int *)v26 + 6),
          *((_DWORD *)v26 + 5));
      if ( !(unsigned __int8)VDS::ReadVds(a1, *(_QWORD *)(v10 + 20)) )
        goto LABEL_43;
      continue;
    }
    if ( *(_WORD *)v26 != 4 )
      break;
    if ( v28 )
    {
      v28 = 1;
      v21 = 1;
    }
    else
    {
      v28 = 0;
      v21 = 0;
    }
    v22 = *(_QWORD *)(v26 + 21) - (_QWORD)UdfLVInfoIdentifierArray;
    if ( !v22 )
      v22 = *(unsigned int *)(v26 + 29) - (unsigned __int64)(unsigned int)dword_1800B55A0;
    if ( !v22 )
    {
      v23 = *(_DWORD **)(a1 + 72);
      if ( v23 )
      {
        v28 = v21 != 0;
        if ( v23[4] >= *((_DWORD *)v26 + 4) )
          continue;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
        *(_QWORD *)(a1 + 72) = v26;
      }
      else
      {
        *(_QWORD *)(a1 + 72) = v26;
      }
      goto LABEL_48;
    }
LABEL_49:
    ;
  }
  if ( *(_WORD *)v26 == 5 )
  {
    v20 = *(_DWORD **)(a1 + 48);
    if ( v20 )
    {
      v28 = v28;
      if ( v20[4] >= *((_DWORD *)v26 + 4) )
        goto LABEL_49;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      *(_QWORD *)(a1 + 48) = v26;
    }
    else
    {
      *(_QWORD *)(a1 + 48) = v26;
    }
    goto LABEL_48;
  }
  if ( *(_WORD *)v26 == 6 )
  {
    v19 = *(_DWORD **)(a1 + 56);
    if ( v19 )
    {
      v28 = v28;
      if ( v19[4] >= *((_DWORD *)v26 + 4) )
        goto LABEL_49;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
      *(_QWORD *)(a1 + 56) = v26;
    }
    else
    {
      *(_QWORD *)(a1 + 56) = v26;
    }
LABEL_48:
    v28 = 0;
    goto LABEL_49;
  }
  if ( *(_WORD *)v26 != 7 )
  {
    if ( *(_WORD *)v26 == 8 )
      goto LABEL_14;
    goto LABEL_49;
  }
  v12 = *(_QWORD *)(a1 + 64);
  if ( v12 )
  {
    *(_BYTE *)(v12 + 26) = *(_BYTE *)(v12 + 26) != 0;
    v16 = *(_QWORD *)(v12 + 16);
    v28 = v28;
    if ( *(_DWORD *)(v16 + 16) >= *((_DWORD *)v26 + 4) )
      goto LABEL_49;
    v14 = *(UNALLOCATED_SPACE_DESCRIPTOR **)(a1 + 64);
    goto LABEL_20;
  }
  v13 = (UNALLOCATED_SPACE_DESCRIPTOR *)operator new(0x28u);
  v14 = v13;
  if ( v13 )
  {
    v15 = UNALLOCATED_SPACE_DESCRIPTOR_cd;
    *((_DWORD *)v13 + 7) = 0;
    *((_WORD *)v13 + 12) = 0;
    *((_QWORD *)v13 + 2) = 0;
    *((_BYTE *)v13 + 26) = 0;
    *(_QWORD *)v13 = &UNALLOCATED_SPACE_DESCRIPTOR::`vftable';
    *((_QWORD *)v13 + 1) = v15;
    *((_QWORD *)v13 + 4) = 0;
    *(_QWORD *)(a1 + 64) = v13;
LABEL_20:
    v17 = UDF_SA::QuerySectorSize(*(UDF_SA **)(a1 + 16));
    v28 = 0;
    UNALLOCATED_SPACE_DESCRIPTOR::Initialize(v14, v26, v18, v17);
    goto LABEL_49;
  }
  *(_QWORD *)(a1 + 64) = 0;
LABEL_43:
  DESCRIPTOR::~DESCRIPTOR((DESCRIPTOR *)v25);
  return 0;
}

```

## disassembly

```asm
0x18006a43c  mov     [rsp-28h+arg_8], rbx
0x18006a441  mov     [rsp-28h+arg_10], rsi
0x18006a446  push    rbp
0x18006a447  push    rdi
0x18006a448  push    r12
0x18006a44a  push    r14
0x18006a44c  push    r15
0x18006a44e  mov     rbp, rsp
0x18006a451  sub     rsp, 50h
0x18006a455  xor     r12d, r12d
0x18006a458  lea     rax, ??_7DESCRIPTOR@@6B@; const DESCRIPTOR::`vftable'
0x18006a45f  mov     [rbp+var_20], rax
0x18006a463  mov     rdi, rcx
0x18006a466  mov     rax, cs:?DESCRIPTOR_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const DESCRIPTOR_cd
0x18006a46d  mov     r14, rdx
0x18006a470  mov     rcx, [rcx+10h]; this
0x18006a474  mov     rbx, rdx
0x18006a477  mov     [rbp+var_18], rax
0x18006a47b  mov     [rbp+var_4], r12d
0x18006a47f  mov     [rbp+var_8], r12w
0x18006a484  mov     [rbp+var_10], r12
0x18006a488  mov     [rbp+var_6], r12b
0x18006a48c  shr     r14, 20h
0x18006a490  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006a495  mov     ecx, eax
0x18006a497  xor     edx, edx
0x18006a499  mov     eax, ebx
0x18006a49b  dec     rax
0x18006a49e  mov     [rbp+arg_0], r12d
0x18006a4a2  add     rax, rcx
0x18006a4a5  div     rcx
0x18006a4a8  mov     rcx, [rdi+50h]
0x18006a4ac  mov     rdx, r14
0x18006a4af  mov     r8d, eax
0x18006a4b2  mov     r15, rax
0x18006a4b5  call    ?Add@NUMBER_SET@@QEAAEVBIG_INT@@0@Z; NUMBER_SET::Add(BIG_INT,BIG_INT)
0x18006a4ba  test    al, al
0x18006a4bc  jz      loc_18006A75B
0x18006a4c2  mov     esi, r12d
0x18006a4c5  cmp     esi, r15d
0x18006a4c8  jnb     loc_18006A552
0x18006a4ce  lea     rcx, [rbp+var_20]; this
0x18006a4d2  call    ?Destroy@DESCRIPTOR@@AEAAXXZ; DESCRIPTOR::Destroy(void)
0x18006a4d7  mov     rdx, [rdi+10h]; struct UDF_SA *
0x18006a4db  lea     eax, [rsi+r14]
0x18006a4df  mov     r9b, 1; unsigned __int8
0x18006a4e2  mov     [rbp+var_4], eax
0x18006a4e5  lea     r8, [rbp+arg_0]; unsigned int *
0x18006a4e9  mov     [rbp+var_8], r12w
0x18006a4ee  lea     rcx, [rbp+var_20]; this
0x18006a4f2  call    ?Read@DESCRIPTOR@@QEAAEPEAVUDF_SA@@PEAIE@Z; DESCRIPTOR::Read(UDF_SA *,uint *,uchar)
0x18006a4f7  test    al, al
0x18006a4f9  jnz     short loc_18006A4FF
0x18006a4fb  inc     esi
0x18006a4fd  jmp     short loc_18006A4C5
0x18006a4ff  lea     rcx, [rbp+var_20]; this
0x18006a503  call    ?Verify@DESCRIPTOR@@QEAAEXZ; DESCRIPTOR::Verify(void)
0x18006a508  test    al, al
0x18006a50a  jz      loc_18006A7C0
0x18006a510  mov     rbx, [rbp+var_10]
0x18006a514  movzx   ecx, word ptr [rbx]
0x18006a517  sub     ecx, 1
0x18006a51a  jz      loc_18006A77F
0x18006a520  sub     ecx, 2
0x18006a523  jz      loc_18006A70A
0x18006a529  sub     ecx, 1
0x18006a52c  jz      loc_18006A68C
0x18006a532  sub     ecx, 1
0x18006a535  jz      loc_18006A643
0x18006a53b  sub     ecx, 1
0x18006a53e  jz      loc_18006A5FA
0x18006a544  sub     ecx, 1
0x18006a547  jz      short loc_18006A562
0x18006a549  cmp     ecx, 1
0x18006a54c  jnz     loc_18006A7C0
0x18006a552  lea     rcx, [rbp+var_20]; this
0x18006a556  call    ??1DESCRIPTOR@@UEAA@XZ; DESCRIPTOR::~DESCRIPTOR(void)
0x18006a55b  mov     al, 1
0x18006a55d  jmp     loc_18006A766
0x18006a562  mov     rdx, [rdi+40h]
0x18006a566  test    rdx, rdx
0x18006a569  jnz     short loc_18006A5AF
0x18006a56b  lea     ecx, [rdx+28h]; unsigned __int64
0x18006a56e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a573  mov     rbx, rax
0x18006a576  test    rax, rax
0x18006a579  jz      loc_18006A7C8
0x18006a57f  mov     rcx, cs:?UNALLOCATED_SPACE_DESCRIPTOR_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const UNALLOCATED_SPACE_DESCRIPTOR_cd
0x18006a586  mov     [rax+1Ch], r12d
0x18006a58a  mov     [rax+18h], r12w
0x18006a58f  mov     [rax+10h], r12
0x18006a593  mov     [rax+1Ah], r12b
0x18006a597  lea     rax, ??_7UNALLOCATED_SPACE_DESCRIPTOR@@6B@; const UNALLOCATED_SPACE_DESCRIPTOR::`vftable'
0x18006a59e  mov     [rbx], rax
0x18006a5a1  mov     [rbx+8], rcx
0x18006a5a5  mov     [rbx+20h], r12
0x18006a5a9  mov     [rdi+40h], rbx
0x18006a5ad  jmp     short loc_18006A5D9
0x18006a5af  cmp     [rdx+1Ah], r12b
0x18006a5b3  setnz   al
0x18006a5b6  mov     [rdx+1Ah], al
0x18006a5b9  mov     rdx, [rdx+10h]
0x18006a5bd  cmp     [rbp+var_6], r12b
0x18006a5c1  mov     rax, [rbp+var_10]
0x18006a5c5  setnz   [rbp+var_6]
0x18006a5c9  mov     ecx, [rax+10h]
0x18006a5cc  cmp     [rdx+10h], ecx
0x18006a5cf  jnb     loc_18006A7C0
0x18006a5d5  mov     rbx, [rdi+40h]
0x18006a5d9  mov     rcx, [rdi+10h]; this
0x18006a5dd  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006a5e2  mov     rdx, [rbp+var_10]; unsigned __int8 *
0x18006a5e6  mov     r9d, eax; unsigned int
0x18006a5e9  mov     rcx, rbx; this
0x18006a5ec  mov     [rbp+var_6], r12b
0x18006a5f0  call    ?Initialize@UNALLOCATED_SPACE_DESCRIPTOR@@QEAAEPEAEEK@Z; UNALLOCATED_SPACE_DESCRIPTOR::Initialize(uchar *,uchar,ulong)
0x18006a5f5  jmp     loc_18006A7C0
0x18006a5fa  mov     r8, [rdi+38h]; P
0x18006a5fe  test    r8, r8
0x18006a601  jnz     short loc_18006A60C
0x18006a603  mov     [rdi+38h], rbx
0x18006a607  jmp     loc_18006A7BC
0x18006a60c  cmp     [rbp+var_6], r12b
0x18006a610  setnz   [rbp+var_6]
0x18006a614  mov     eax, [rbx+10h]
0x18006a617  cmp     [r8+10h], eax
0x18006a61b  jnb     loc_18006A7C0
0x18006a621  mov     rcx, gs:60h
0x18006a62a  xor     edx, edx; Flags
0x18006a62c  mov     rcx, [rcx+30h]; HeapHandle
0x18006a630  call    cs:__imp_RtlFreeHeap
0x18006a636  mov     rax, [rbp+var_10]
0x18006a63a  mov     [rdi+38h], rax
0x18006a63e  jmp     loc_18006A7BC
0x18006a643  mov     r8, [rdi+30h]; P
0x18006a647  test    r8, r8
0x18006a64a  jnz     short loc_18006A655
0x18006a64c  mov     [rdi+30h], rbx
0x18006a650  jmp     loc_18006A7BC
0x18006a655  cmp     [rbp+var_6], r12b
0x18006a659  setnz   [rbp+var_6]
0x18006a65d  mov     eax, [rbx+10h]
0x18006a660  cmp     [r8+10h], eax
0x18006a664  jnb     loc_18006A7C0
0x18006a66a  mov     rcx, gs:60h
0x18006a673  xor     edx, edx; Flags
0x18006a675  mov     rcx, [rcx+30h]; HeapHandle
0x18006a679  call    cs:__imp_RtlFreeHeap
0x18006a67f  mov     rax, [rbp+var_10]
0x18006a683  mov     [rdi+30h], rax
0x18006a687  jmp     loc_18006A7BC
0x18006a68c  cmp     [rbp+var_6], r12b
0x18006a690  jz      short loc_18006A69A
0x18006a692  mov     [rbp+var_6], 1
0x18006a696  mov     dl, 1
0x18006a698  jmp     short loc_18006A6A1
0x18006a69a  mov     [rbp+var_6], r12b
0x18006a69e  mov     dl, r12b
0x18006a6a1  mov     rcx, [rbx+15h]
0x18006a6a5  sub     rcx, cs:?UdfLVInfoIdentifierArray@@3PADA; char near * UdfLVInfoIdentifierArray
0x18006a6ac  jnz     short loc_18006A6BA
0x18006a6ae  mov     ecx, [rbx+1Dh]
0x18006a6b1  mov     eax, cs:dword_1800B55A0
0x18006a6b7  sub     rcx, rax
0x18006a6ba  test    rcx, rcx
0x18006a6bd  jnz     loc_18006A7C0
0x18006a6c3  mov     r8, [rdi+48h]; P
0x18006a6c7  test    r8, r8
0x18006a6ca  jnz     short loc_18006A6D5
0x18006a6cc  mov     [rdi+48h], rbx
0x18006a6d0  jmp     loc_18006A7BC
0x18006a6d5  test    dl, dl
0x18006a6d7  setnz   [rbp+var_6]
0x18006a6db  mov     eax, [rbx+10h]
0x18006a6de  cmp     [r8+10h], eax
0x18006a6e2  jnb     loc_18006A7C0
0x18006a6e8  mov     rcx, gs:60h
0x18006a6f1  xor     edx, edx; Flags
0x18006a6f3  mov     rcx, [rcx+30h]; HeapHandle
0x18006a6f7  call    cs:__imp_RtlFreeHeap
0x18006a6fd  mov     rax, [rbp+var_10]
0x18006a701  mov     [rdi+48h], rax
0x18006a705  jmp     loc_18006A7BC
0x18006a70a  cmp     [rbp+var_6], r12b
0x18006a70e  setnz   [rbp+var_6]
0x18006a712  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a719  lea     rax, WPP_GLOBAL_Control
0x18006a720  cmp     rcx, rax
0x18006a723  jz      short loc_18006A74B
0x18006a725  test    byte ptr [rcx+1Ch], 1
0x18006a729  jz      short loc_18006A74B
0x18006a72b  mov     eax, [rbx+14h]
0x18006a72e  lea     r8, WPP_9d30ce6518fc32679771b1918a9f0ec4_Traceguids
0x18006a735  mov     r9d, [rbx+18h]
0x18006a739  mov     edx, 0Bh
0x18006a73e  mov     rcx, [rcx+10h]
0x18006a742  mov     [rsp+50h+var_30], eax
0x18006a746  call    WPP_SF_DD
0x18006a74b  mov     rdx, [rbx+14h]
0x18006a74f  mov     rcx, rdi
0x18006a752  call    ?ReadVds@VDS@@AEAAEUEXTENTAD@@@Z; VDS::ReadVds(EXTENTAD)
0x18006a757  test    al, al
0x18006a759  jnz     short loc_18006A7C0
0x18006a75b  lea     rcx, [rbp+var_20]; this
0x18006a75f  call    ??1DESCRIPTOR@@UEAA@XZ; DESCRIPTOR::~DESCRIPTOR(void)
0x18006a764  xor     al, al
0x18006a766  lea     r11, [rsp+50h+var_s0]
0x18006a76b  mov     rbx, [r11+38h]
0x18006a76f  mov     rsi, [r11+40h]
0x18006a773  mov     rsp, r11
0x18006a776  pop     r15
0x18006a778  pop     r14
0x18006a77a  pop     r12
0x18006a77c  pop     rdi
0x18006a77d  pop     rbp
0x18006a77e  retn
0x18006a77f  mov     r8, [rdi+28h]; P
0x18006a783  test    r8, r8
0x18006a786  jnz     short loc_18006A78E
0x18006a788  mov     [rdi+28h], rbx
0x18006a78c  jmp     short loc_18006A7BC
0x18006a78e  cmp     [rbp+var_6], r12b
0x18006a792  setnz   [rbp+var_6]
0x18006a796  mov     eax, [rbx+10h]
0x18006a799  cmp     [r8+10h], eax
0x18006a79d  jnb     short loc_18006A7C0
0x18006a79f  mov     rcx, gs:60h
0x18006a7a8  xor     edx, edx; Flags
0x18006a7aa  mov     rcx, [rcx+30h]; HeapHandle
0x18006a7ae  call    cs:__imp_RtlFreeHeap
0x18006a7b4  mov     rax, [rbp+var_10]
0x18006a7b8  mov     [rdi+28h], rax
0x18006a7bc  mov     [rbp+var_6], r12b
0x18006a7c0  add     esi, [rbp+arg_0]
0x18006a7c3  jmp     loc_18006A4C5
0x18006a7c8  mov     [rdi+40h], r12
0x18006a7cc  jmp     short loc_18006A75B
```
