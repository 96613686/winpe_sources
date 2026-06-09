# PrjfCreateUnionContext

- ea: `0x140002288`
- end: `0x1400025eb`
- name: `PrjfCreateUnionContext`
- size: `867`
- prototype: `__int64 __fastcall(__int64, _OWORD *, const UNICODE_STRING *, int, char, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003e0d8`

## callees

- `0x140002288`
- `0x140003e6c`
- `0x14000d008`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1400025c7`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400025c7`
- `ntoskrnl!RtlCreateHashTableEx` at `0x1400024f3`
- `ntoskrnl!RtlCreateHashTableEx` at `0x1400024f3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002493`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002493`
- `ntoskrnl!RtlRandomEx` at `0x14000245e`
- `ntoskrnl!RtlRandomEx` at `0x14000245e`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400023b0`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400023f1`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400023b0`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400023f1`
- `ntoskrnl!ExAllocatePool2` at `0x1400022cc`
- `ntoskrnl!ExAllocatePool2` at `0x1400022cc`
- `ntoskrnl!KeInitializeEvent` at `0x14000241c`
- `ntoskrnl!KeInitializeEvent` at `0x14000241c`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000237f`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400023c0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140002404`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400024ca`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000237f`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400023c0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140002404`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400024ca`
- `ntoskrnl!ExDeleteResourceLite` at `0x140002517`
- `ntoskrnl!ExDeleteResourceLite` at `0x140002517`

## pseudocode

```c
__int64 __fastcall PrjfCreateUnionContext(
        __int64 a1,
        _OWORD *a2,
        const UNICODE_STRING *a3,
        int a4,
        char a5,
        __int64 *a6)
{
  __int64 Length; // rdx
  __int64 Pool2; // rax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rbx
  unsigned int v15; // edi
  int v16; // edx
  int v17; // r8d
  __int64 *v18; // rax
  PRTL_DYNAMIC_HASH_TABLE HashTable[2]; // [rsp+50h] [rbp-28h] BYREF
  ULONG Seed; // [rsp+90h] [rbp+18h] BYREF

  Seed = 0;
  Length = a3->Length;
  HashTable[0] = 0;
  Pool2 = ExAllocatePool2(64, Length + 810, 1668631120);
  v14 = Pool2;
  if ( Pool2 )
  {
    *(_OWORD *)Pool2 = *a2;
    *(_DWORD *)(Pool2 + 60) = _InterlockedIncrement((volatile signed __int32 *)(a1 + 168));
    ExInitializeResourceLite((PERESOURCE)(Pool2 + 696));
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(v14 + 200),
      PrjfCompareHandleTableEntry,
      PrjfAllocateHandleTableEntry,
      PrjfFreeHandleTableEntry,
      0);
    ExInitializeResourceLite((PERESOURCE)(v14 + 96));
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(v14 + 416),
      PrjfCompareCommandTableEntry,
      PrjfAllocateCommandTableEntry,
      PrjfFreeCommandTableEntry,
      0);
    ExInitializeResourceLite((PERESOURCE)(v14 + 312));
    KeInitializeEvent((PRKEVENT)(v14 + 520), NotificationEvent, 0);
    *(_DWORD *)(v14 + 88) = 1;
    Seed = MEMORY[0xFFFFF78000000320] ^ v14 ^ MEMORY[0xFFFFF78000000324] ^ (unsigned int)KeGetCurrentThread();
    *(_DWORD *)(v14 + 72) = RtlRandomEx(&Seed);
    *(_QWORD *)(v14 + 64) = 0;
    *(_WORD *)(v14 + 40) = 0;
    *(_WORD *)(v14 + 42) = a3->Length;
    *(_QWORD *)(v14 + 48) = v14 + 810;
    RtlCopyUnicodeString((PUNICODE_STRING)(v14 + 40), a3);
    *(_BYTE *)(v14 + 808) = a5;
    *(_QWORD *)(v14 + 80) = 0;
    *(_DWORD *)(v14 + 56) = a4;
    if ( (a4 & 1) == 0
      || (ExInitializeResourceLite((PERESOURCE)(v14 + 544)),
          HashTable[0] = (PRTL_DYNAMIC_HASH_TABLE)(v14 + 648),
          (unsigned __int8)RtlCreateHashTableEx(HashTable, (unsigned int)dword_14001ABC8, 0, 0)) )
    {
      v18 = a6;
      v15 = 0;
      *(_QWORD *)(v14 + 688) = 0;
      *v18 = v14;
      v14 = 0;
      HashTable[0] = 0;
    }
    else
    {
      HashTable[0] = 0;
      *(_DWORD *)(v14 + 56) &= ~1u;
      ExDeleteResourceLite((PERESOURCE)(v14 + 544));
      v15 = -1073741670;
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          521,
          v16,
          v17,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          34,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          252);
      }
    }
    if ( v14 )
      PrjfReleaseUnionContext((PVOID)v14);
  }
  else
  {
    v15 = -1073741670;
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        521,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        33,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        179);
    }
  }
  if ( HashTable[0] )
    RtlDeleteHashTable(HashTable[0]);
  return v15;
}

```

## disassembly

```asm
0x140002288  mov     rax, rsp
0x14000228b  mov     [rax+8], rbx
0x14000228f  mov     [rax+10h], rbp
0x140002293  push    rsi
0x140002294  push    rdi
0x140002295  push    r14
0x140002297  sub     rsp, 60h
0x14000229b  mov     r14, rdx
0x14000229e  mov     dword ptr [rax+18h], 0
0x1400022a5  movzx   edx, word ptr [r8]
0x1400022a9  mov     rdi, r8
0x1400022ac  mov     rbp, rcx
0x1400022af  mov     qword ptr [rax-28h], 0
0x1400022b7  add     rdx, 32Ah
0x1400022be  mov     ecx, 40h ; '@'
0x1400022c3  mov     r8d, 63754A50h
0x1400022c9  mov     esi, r9d
0x1400022cc  call    cs:__imp_ExAllocatePool2
0x1400022d3  nop     dword ptr [rax+rax+00h]
0x1400022d8  mov     rbx, rax
0x1400022db  test    rax, rax
0x1400022de  jnz     short loc_140002359
0x1400022e0  mov     edi, 0C000009Ah
0x1400022e5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400022eb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400022f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400022f9  setnz   r8b
0x1400022fd  and     dl, 2
0x140002300  jnz     short loc_14000230B
0x140002302  test    r8b, r8b
0x140002305  jz      loc_1400025BD
0x14000230b  mov     r9, cs:WPP_GLOBAL_Control
0x140002312  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002319  mov     [rsp+78h+var_30], 6B3h
0x140002321  mov     ecx, 209h
0x140002326  mov     [rsp+78h+var_38], rax
0x14000232b  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002332  mov     [rsp+78h+var_40], rax
0x140002337  mov     r9, [r9+40h]
0x14000233b  mov     [rsp+78h+var_48], 21h ; '!'
0x140002342  mov     [rsp+78h+var_50], 9
0x14000234a  mov     byte ptr [rsp+78h+TableContext], 2
0x14000234f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140002354  jmp     loc_1400025BD
0x140002359  movaps  xmm0, xmmword ptr [r14]
0x14000235d  mov     r14d, 1
0x140002363  movdqu  xmmword ptr [rax], xmm0
0x140002367  mov     eax, r14d
0x14000236a  lock xadd [rbp+0A8h], eax
0x140002372  add     eax, r14d
0x140002375  lea     rcx, [rbx+2B8h]; Resource
0x14000237c  mov     [rbx+3Ch], eax
0x14000237f  call    cs:__imp_ExInitializeResourceLite
0x140002386  nop     dword ptr [rax+rax+00h]
0x14000238b  lea     rcx, [rbx+0C8h]; Table
0x140002392  mov     [rsp+78h+TableContext], 0; TableContext
0x14000239b  lea     r9, PrjfFreeHandleTableEntry; FreeRoutine
0x1400023a2  lea     r8, PrjfAllocateHandleTableEntry; AllocateRoutine
0x1400023a9  lea     rdx, PrjfCompareHandleTableEntry; CompareRoutine
0x1400023b0  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400023b7  nop     dword ptr [rax+rax+00h]
0x1400023bc  lea     rcx, [rbx+60h]; Resource
0x1400023c0  call    cs:__imp_ExInitializeResourceLite
0x1400023c7  nop     dword ptr [rax+rax+00h]
0x1400023cc  lea     rcx, [rbx+1A0h]; Table
0x1400023d3  mov     [rsp+78h+TableContext], 0; TableContext
0x1400023dc  lea     r9, PrjfFreeCommandTableEntry; FreeRoutine
0x1400023e3  lea     r8, PrjfAllocateCommandTableEntry; AllocateRoutine
0x1400023ea  lea     rdx, PrjfCompareCommandTableEntry; CompareRoutine
0x1400023f1  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400023f8  nop     dword ptr [rax+rax+00h]
0x1400023fd  lea     rcx, [rbx+138h]; Resource
0x140002404  call    cs:__imp_ExInitializeResourceLite
0x14000240b  nop     dword ptr [rax+rax+00h]
0x140002410  lea     rcx, [rbx+208h]; Event
0x140002417  xor     r8d, r8d; State
0x14000241a  xor     edx, edx; Type
0x14000241c  call    cs:__imp_KeInitializeEvent
0x140002423  nop     dword ptr [rax+rax+00h]
0x140002428  mov     [rbx+58h], r14d
0x14000242c  mov     rax, 0FFFFF78000000320h
0x140002436  mov     rax, [rax]
0x140002439  mov     rdx, gs:188h
0x140002442  mov     rcx, rax
0x140002445  shr     rcx, 20h
0x140002449  xor     edx, ecx
0x14000244b  lea     rcx, [rsp+78h+Seed]; Seed
0x140002453  xor     edx, ebx
0x140002455  xor     edx, eax
0x140002457  mov     [rsp+78h+Seed], edx
0x14000245e  call    cs:__imp_RtlRandomEx
0x140002465  nop     dword ptr [rax+rax+00h]
0x14000246a  mov     [rbx+48h], eax
0x14000246d  lea     rcx, [rbx+28h]; DestinationString
0x140002471  mov     qword ptr [rbx+40h], 0
0x140002479  mov     rdx, rdi; SourceString
0x14000247c  xor     eax, eax
0x14000247e  mov     [rcx], ax
0x140002481  movzx   eax, word ptr [rdi]
0x140002484  mov     [rbx+2Ah], ax
0x140002488  lea     rax, [rbx+32Ah]
0x14000248f  mov     [rbx+30h], rax
0x140002493  call    cs:__imp_RtlCopyUnicodeString
0x14000249a  nop     dword ptr [rax+rax+00h]
0x14000249f  mov     al, [rsp+78h+arg_20]
0x1400024a6  mov     [rbx+328h], al
0x1400024ac  mov     qword ptr [rbx+50h], 0
0x1400024b4  mov     [rbx+38h], esi
0x1400024b7  test    r14b, sil
0x1400024ba  jz      loc_140002595
0x1400024c0  lea     rdi, [rbx+220h]
0x1400024c7  mov     rcx, rdi; Resource
0x1400024ca  call    cs:__imp_ExInitializeResourceLite
0x1400024d1  nop     dword ptr [rax+rax+00h]
0x1400024d6  mov     edx, cs:dword_14001ABC8
0x1400024dc  lea     rax, [rbx+288h]
0x1400024e3  xor     r9d, r9d
0x1400024e6  mov     [rsp+78h+HashTable], rax
0x1400024eb  xor     r8d, r8d
0x1400024ee  lea     rcx, [rsp+78h+HashTable]
0x1400024f3  call    cs:__imp_RtlCreateHashTableEx
0x1400024fa  nop     dword ptr [rax+rax+00h]
0x1400024ff  test    al, al
0x140002501  jnz     loc_140002595
0x140002507  mov     [rsp+78h+HashTable], 0
0x140002510  mov     rcx, rdi; Resource
0x140002513  and     dword ptr [rbx+38h], 0FFFFFFFEh
0x140002517  call    cs:__imp_ExDeleteResourceLite
0x14000251e  nop     dword ptr [rax+rax+00h]
0x140002523  mov     edi, 0C000009Ah
0x140002528  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000252e  lea     rax, WPP_RECORDER_INITIALIZED
0x140002535  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000253c  setnz   r8b
0x140002540  and     dl, 2
0x140002543  jnz     short loc_14000254A
0x140002545  test    r8b, r8b
0x140002548  jz      short loc_1400025B0
0x14000254a  mov     r9, cs:WPP_GLOBAL_Control
0x140002551  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002558  mov     [rsp+78h+var_30], 6FCh
0x140002560  mov     ecx, 209h
0x140002565  mov     [rsp+78h+var_38], rax
0x14000256a  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140002571  mov     [rsp+78h+var_40], rax
0x140002576  mov     r9, [r9+40h]
0x14000257a  mov     [rsp+78h+var_48], 22h ; '"'
0x140002581  mov     [rsp+78h+var_50], 9
0x140002589  mov     byte ptr [rsp+78h+TableContext], 2
0x14000258e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140002593  jmp     short loc_1400025B0
0x140002595  mov     rax, [rsp+78h+arg_28]
0x14000259d  xor     edi, edi
0x14000259f  mov     [rbx+2B0h], rdi
0x1400025a6  mov     [rax], rbx
0x1400025a9  xor     ebx, ebx
0x1400025ab  mov     [rsp+78h+HashTable], rbx
0x1400025b0  test    rbx, rbx
0x1400025b3  jz      short loc_1400025BD
0x1400025b5  mov     rcx, rbx; P
0x1400025b8  call    PrjfReleaseUnionContext
0x1400025bd  mov     rcx, [rsp+78h+HashTable]; HashTable
0x1400025c2  test    rcx, rcx
0x1400025c5  jz      short loc_1400025D3
0x1400025c7  call    cs:__imp_RtlDeleteHashTable
0x1400025ce  nop     dword ptr [rax+rax+00h]
0x1400025d3  lea     r11, [rsp+78h+var_18]
0x1400025d8  mov     eax, edi
0x1400025da  mov     rbx, [r11+20h]
0x1400025de  mov     rbp, [r11+28h]
0x1400025e2  mov     rsp, r11
0x1400025e5  pop     r14
0x1400025e7  pop     rdi
0x1400025e8  pop     rsi
0x1400025e9  retn
```
