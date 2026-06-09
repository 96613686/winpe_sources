# RtlpValidateHeapSegment

- ea: `0x1800aba3c`
- end: `0x1800ac27d`
- name: `RtlpValidateHeapSegment`
- size: `2113`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800aa2cc`

## callees

- `0x180004350`
- `0x180004460`
- `0x180007060`
- `0x1800070f0`
- `0x180007450`
- `0x180008124`
- `0x180008488`
- `0x1800a9b38`
- `0x1800ab150`
- `0x1800aba3c`
- `0x18011c718`
- `0x1801625d0`

## string_xrefs

- `0x1800ac0d5`: `Heap Segment at %p contains invalid NumberOfUnCommittedRanges (%x != %x)\n`
- `0x1800ac0a4`: `Heap Segment at %p contains invalid NumberOfUnCommittedPages (%x != %x)\n`

## pseudocode

```c
char __fastcall RtlpValidateHeapSegment(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        _QWORD *a5,
        unsigned __int64 *a6,
        __int64 a7,
        __int64 a8)
{
  _PEB_LDR_DATA *v8; // r10
  __int64 v9; // rbp
  unsigned int v10; // r14d
  unsigned int v11; // r13d
  unsigned __int16 v12; // r12
  unsigned __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // r15
  __int64 v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // rax
  bool v20; // zf
  __int64 v22; // rax
  unsigned __int64 v23; // rsi
  unsigned __int64 v24; // rsi
  __int64 *v25; // r14
  _QWORD *v26; // r15
  __int64 v27; // rsi
  __int64 v28; // rax
  __int64 v29; // r9
  __int64 **v30; // rdx
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // rcx
  int v33; // r8d
  int v34; // ecx
  unsigned __int64 v35; // r14
  _QWORD *v36; // rsi
  _QWORD *Entry; // r8
  int v38; // eax
  __int64 *v39; // rax
  unsigned __int64 v40; // r8
  unsigned __int16 v41; // cx
  __int64 v42; // r14
  unsigned __int16 v43; // cx
  char v44; // al
  char v45; // al
  __int64 v46; // r9
  int v47; // [rsp+20h] [rbp-48h]
  unsigned int v48; // [rsp+80h] [rbp+18h]
  _DWORD *v49; // [rsp+88h] [rbp+20h]

  v49 = a4;
  v8 = 0;
  v9 = a2;
  v10 = 0;
  v48 = 0;
  v11 = 0;
  v12 = 0;
  v14 = a2;
  while ( v14 < *(_QWORD *)(v9 + 72) )
  {
    *a6 = v14;
    if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
    {
      *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
      if ( *(_BYTE *)(v14 + 11) != (*(_BYTE *)(v14 + 8) ^ (unsigned __int8)(*(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10))) )
      {
        RtlpAnalyzeHeapFailure(a1, v14);
        a4 = v49;
        v8 = 0;
      }
    }
    if ( v12 != (*(_WORD *)(a1 + 140) ^ *(_WORD *)(v14 + 12)) )
    {
      if ( NtCurrentPeb()->Ldr == v8 )
        DbgPrint("HEAP: ");
      else
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
      DbgPrint(
        "Heap entry %p has incorrect PreviousSize field (%04x instead of %04x)\n",
        (const void *)v14,
        *(unsigned __int16 *)(a1 + 140) ^ *(unsigned __int16 *)(v14 + 12),
        v12);
LABEL_22:
      v20 = *(_DWORD *)(a1 + 124) == 0;
LABEL_23:
      if ( !v20 )
      {
        *(_BYTE *)(v14 + 11) = *(_BYTE *)(v14 + 8) ^ *(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10);
        *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
      }
      return 0;
    }
    v15 = *(unsigned __int16 *)(v14 + 8);
    LOBYTE(a2) = *(_BYTE *)(v14 + 10);
    v16 = 16 * v15;
    v12 = *(_WORD *)(v14 + 8);
    if ( (a2 & 1) != 0 )
    {
      v17 = a7;
      if ( a7 )
      {
        v41 = (a2 & 2) != 0 ? *(_WORD *)(RtlpGetExtraStuffPointer(v14) + 2) : *(unsigned __int8 *)(v14 + 11);
        if ( v41 )
        {
          if ( (v41 & 0x8000u) != 0 )
          {
            v43 = v41 & 0x7FFF;
            if ( v43 < 0x81u )
              *(_QWORD *)(a8 + 8LL * v43) += v15;
          }
          else if ( (v41 & 0x800) == 0 && v41 < *(_WORD *)(a1 + 224) )
          {
            *(_QWORD *)(v17 + 8LL * v41) += v15;
          }
        }
      }
      if ( (*(_BYTE *)(v14 + 10) & 4) != 0 )
      {
        v44 = RtlpCheckBusyBlockTail(a1, v14);
        v8 = 0;
        if ( !v44 )
        {
          v20 = *(_DWORD *)(a1 + 124) == 0;
          goto LABEL_23;
        }
      }
      a4 = v49;
      goto LABEL_11;
    }
    if ( (((unsigned __int8)a2 >> 2) & ((*(_BYTE *)(a1 + 112) & 0x40) != 0)) != 0 )
    {
      v24 = v16 - 32;
      if ( (a2 & 2) != 0 && v24 > 4 )
        v24 = v16 - 36;
      if ( (a2 & 8) == 0 )
      {
        v42 = RtlCompareMemoryUlong(v14 + 32, v24, 4277075694LL);
        if ( v42 != v24 )
        {
          if ( NtCurrentPeb()->Ldr )
            DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
          else
            DbgPrint("HEAP: ");
          DbgPrint("Free Heap block %p modified at %p after it was freed\n", v14, v42 + v14 + 16);
          goto LABEL_22;
        }
        v10 = v48;
        a4 = v49;
        goto LABEL_27;
      }
      v25 = *(__int64 **)(v14 + 24);
      v26 = (_QWORD *)(v14 + 16);
      v27 = *(_QWORD *)(v14 + 16);
      v28 = *v25;
      v29 = *(_QWORD *)(v27 + 8);
      if ( *v25 != v14 + 16 || v28 != v29 )
      {
        RtlpLogHeapFailure(13, a1, v14 + 16, v29, v28, (__int64)v8);
        goto LABEL_105;
      }
      *(_QWORD *)(a1 + 192) -= v15;
      v30 = *(__int64 ***)(a1 + 312);
      if ( v30 )
      {
        v31 = *(unsigned __int16 *)(v14 + 8);
        while ( 1 )
        {
          v32 = *((unsigned int *)v30 + 2);
          if ( v31 < v32 )
          {
            v34 = *(unsigned __int16 *)(v14 + 8);
            goto LABEL_65;
          }
          if ( !*v30 )
            break;
          v30 = (__int64 **)*v30;
        }
        v34 = v32 - 1;
LABEL_65:
        LOBYTE(v31) = 1;
        RtlpHeapRemoveListEntry(a1, (_DWORD)v30, v31, v14 + 16, v34, *(unsigned __int16 *)(v14 + 8));
        v8 = 0;
      }
      *v25 = v27;
      *(_QWORD *)(v27 + 8) = v25;
      if ( (*(_BYTE *)(v14 + 10) & 8) == 0 || (v45 = RtlpCommitBlock(a1, v14), v8 = 0, v45) )
      {
        v35 = *(unsigned __int16 *)(v14 + 8);
        v36 = (_QWORD *)(a1 + 336);
        *(_BYTE *)(v14 + 10) = (_BYTE)v8;
        *(_BYTE *)(v14 + 15) = (_BYTE)v8;
        if ( *(_PEB_LDR_DATA **)(a1 + 312) == v8 )
        {
          Entry = (_QWORD *)*v36;
        }
        else
        {
          Entry = (_QWORD *)RtlpFindEntry(a1, (unsigned int)v35);
          v8 = 0;
        }
        while ( v36 != Entry )
        {
          if ( *(_DWORD *)(a1 + 124) == (_DWORD)v8 )
          {
            LOWORD(v38) = *((_WORD *)Entry - 4);
          }
          else
          {
            v38 = *((_DWORD *)Entry - 2);
            if ( (v38 & *(_DWORD *)(a1 + 124)) != 0 )
              v38 ^= *(_DWORD *)(a1 + 136);
          }
          if ( v35 <= (unsigned __int16)v38 )
            break;
          Entry = (_QWORD *)*Entry;
        }
        v39 = (__int64 *)Entry[1];
        if ( (_QWORD *)*v39 == Entry )
        {
          *v26 = Entry;
          *(_QWORD *)(v14 + 24) = v39;
          *v39 = (__int64)v26;
          Entry[1] = v26;
        }
        else
        {
          RtlpLogHeapFailure(13, 0, (_DWORD)Entry, 0, *v39, (__int64)v8);
          v8 = 0;
        }
        *(_QWORD *)(a1 + 192) += *(unsigned __int16 *)(v14 + 8);
        a2 = *(_QWORD *)(a1 + 312);
        if ( a2 )
        {
          while ( 1 )
          {
            v40 = *(unsigned int *)(a2 + 8);
            if ( *(unsigned __int16 *)(v14 + 8) < v40 )
            {
              v33 = *(unsigned __int16 *)(v14 + 8);
              goto LABEL_60;
            }
            if ( !*(_QWORD *)a2 )
              break;
            a2 = *(_QWORD *)a2;
          }
          v33 = v40 - 1;
LABEL_60:
          v47 = v33;
          LOBYTE(v33) = 1;
          RtlpHeapAddListEntry(a1, a2, v33, v14 + 16, v47, *(unsigned __int16 *)(v14 + 8));
          v8 = 0;
        }
        v10 = v48;
        a4 = v49;
        if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
        {
          *(_BYTE *)(v14 + 11) = *(_BYTE *)(v14 + 8) ^ *(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10);
          *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
          goto LABEL_63;
        }
      }
      else
      {
        LOBYTE(v46) = 1;
        RtlpDeCommitFreeBlock(a1, v14, *(unsigned __int16 *)(v14 + 8), v46);
LABEL_105:
        v10 = v48;
        v8 = 0;
        a4 = v49;
      }
    }
    else
    {
LABEL_27:
      v22 = *(unsigned __int16 *)(v14 + 8);
      ++*a4;
      *a5 += v22;
      v8 = 0;
LABEL_11:
      v18 = *(unsigned __int8 *)(v14 + 14);
      if ( (_BYTE)v18 )
        v19 = (v14 & 0xFFFFFFFFFFFF0000uLL) - (v18 << 16) + 0x10000;
      else
        v19 = a1;
      if ( v19 != v9 )
      {
        if ( NtCurrentPeb()->Ldr == v8 )
          DbgPrint("HEAP: ", a2, v15, a4);
        else
          DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink, v15, a4);
        DbgPrint("Heap block at %p has incorrect segment offset (%x)\n", v14, *(unsigned __int8 *)(v14 + 14));
        goto LABEL_22;
      }
      if ( *(_BYTE *)(v14 + 15) == 3 )
      {
        v23 = *(_QWORD *)(v14 + 56);
        if ( !v23 )
        {
          if ( v14 + 16LL * *(unsigned __int16 *)(v14 + 8) != *(_QWORD *)(v9 + 72) )
          {
            if ( NtCurrentPeb()->Ldr == v8 )
              DbgPrint("HEAP: ", a2, v15, a4);
            else
              DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
            DbgPrint("Heap block at %p is not last block in segment (%p)\n", v14, *(_QWORD *)(v9 + 72));
            goto LABEL_22;
          }
          if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
          {
            *(_BYTE *)(v14 + 11) = *(_BYTE *)(v14 + 8) ^ *(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10);
            *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
          }
          return 1;
        }
        if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
        {
          *(_BYTE *)(v14 + 11) = *(_BYTE *)(v14 + 8) ^ *(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10);
          *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
        }
        v14 += v23 + 64;
        if ( v14 != *(_QWORD *)(v9 + 72) )
        {
          if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
          {
            *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
            if ( *(_BYTE *)(v14 + 11) != (*(_BYTE *)(v14 + 8)
                                        ^ (unsigned __int8)(*(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10))) )
            {
              RtlpAnalyzeHeapFailure(a1, v14);
              v8 = 0;
            }
          }
          if ( *(_WORD *)(a1 + 140) != *(_WORD *)(v14 + 12) )
          {
            if ( NtCurrentPeb()->Ldr == v8 )
              DbgPrint("HEAP: ", a2, v15, a4);
            else
              DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink, v15, a4);
            DbgPrint(
              "Heap block at %p has corrupted PreviousSize (%lx)\n",
              v14,
              *(unsigned __int16 *)(a1 + 140) ^ (unsigned int)*(unsigned __int16 *)(v14 + 12));
            goto LABEL_22;
          }
          if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
          {
            *(_BYTE *)(v14 + 11) = *(_BYTE *)(v14 + 8) ^ *(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10);
            *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
          }
        }
        ++v11;
        v10 += v23 >> 12;
        v12 = (unsigned __int16)v8;
        v48 = v10;
LABEL_63:
        a4 = v49;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 124) != (_DWORD)v8 )
        {
          *(_BYTE *)(v14 + 11) = *(_BYTE *)(v14 + 8) ^ *(_BYTE *)(v14 + 9) ^ *(_BYTE *)(v14 + 10);
          *(_DWORD *)(v14 + 8) ^= *(_DWORD *)(a1 + 136);
        }
        v14 += v16;
      }
    }
  }
  if ( *(_DWORD *)(v9 + 80) != v10 )
  {
    if ( NtCurrentPeb()->Ldr == v8 )
      DbgPrint("HEAP: ");
    else
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    DbgPrint(
      "Heap Segment at %p contains invalid NumberOfUnCommittedPages (%x != %x)\n",
      v9,
      *(unsigned int *)(v9 + 80),
      v10);
    return 0;
  }
  if ( *(_DWORD *)(v9 + 84) != v11 )
  {
    if ( NtCurrentPeb()->Ldr == v8 )
      DbgPrint("HEAP: ");
    else
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    DbgPrint(
      "Heap Segment at %p contains invalid NumberOfUnCommittedRanges (%x != %x)\n",
      v9,
      *(unsigned int *)(v9 + 84),
      v11);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800aba3c  mov     [rsp+arg_0], rbx
0x1800aba41  mov     [rsp+arg_18], r9
0x1800aba46  mov     byte ptr [rsp+arg_10], r8b
0x1800aba4b  push    rbp
0x1800aba4c  push    rsi
0x1800aba4d  push    rdi
0x1800aba4e  push    r12
0x1800aba50  push    r13
0x1800aba52  push    r14
0x1800aba54  push    r15
0x1800aba56  sub     rsp, 30h
0x1800aba5a  xor     r10d, r10d
0x1800aba5d  mov     rbp, rdx
0x1800aba60  mov     r14d, r10d
0x1800aba63  mov     [rsp+68h+arg_10], r10d
0x1800aba6b  mov     r13d, r10d
0x1800aba6e  mov     r12d, r10d
0x1800aba71  mov     rdi, rcx
0x1800aba74  mov     rbx, rdx
0x1800aba77  cmp     rbx, [rbp+48h]
0x1800aba7b  jnb     loc_1800ABCF1
0x1800aba81  mov     rax, [rsp+68h+arg_28]
0x1800aba89  mov     [rax], rbx
0x1800aba8c  cmp     [rdi+7Ch], r10d
0x1800aba90  jz      short loc_1800ABABF
0x1800aba92  mov     eax, [rdi+88h]
0x1800aba98  xor     [rbx+8], eax
0x1800aba9b  mov     al, [rbx+0Ah]
0x1800aba9e  xor     al, [rbx+9]
0x1800abaa1  xor     al, [rbx+8]
0x1800abaa4  cmp     [rbx+0Bh], al
0x1800abaa7  jz      short loc_1800ABABF
0x1800abaa9  mov     rdx, rbx
0x1800abaac  mov     rcx, rdi
0x1800abaaf  call    RtlpAnalyzeHeapFailure
0x1800abab4  mov     r9, [rsp+68h+arg_18]
0x1800ababc  xor     r10d, r10d
0x1800ababf  movzx   eax, word ptr [rbx+0Ch]
0x1800abac3  xor     ax, [rdi+8Ch]
0x1800abaca  cmp     r12w, ax
0x1800abace  jnz     loc_1800ABB6F
0x1800abad4  movzx   r8d, word ptr [rbx+8]
0x1800abad9  mov     dl, [rbx+0Ah]
0x1800abadc  mov     r15d, r8d
0x1800abadf  shl     r15, 4
0x1800abae3  movzx   r12d, r8w
0x1800abae7  test    dl, 1
0x1800abaea  jz      loc_1800ABBE3
0x1800abaf0  mov     r9, [rsp+68h+arg_30]
0x1800abaf8  test    r9, r9
0x1800abafb  jnz     loc_1800ABF1E
0x1800abb01  test    byte ptr [rbx+0Ah], 4
0x1800abb05  jnz     loc_1800AC1A6
0x1800abb0b  mov     r9, [rsp+68h+arg_18]
0x1800abb13  movzx   eax, byte ptr [rbx+0Eh]
0x1800abb17  test    al, al
0x1800abb19  jnz     short loc_1800ABB54
0x1800abb1b  mov     rax, rdi
0x1800abb1e  cmp     rax, rbp
0x1800abb21  jnz     loc_1800AC01F
0x1800abb27  cmp     byte ptr [rbx+0Fh], 3
0x1800abb2b  jz      loc_1800ABC3A
0x1800abb31  cmp     [rdi+7Ch], r10d
0x1800abb35  jz      short loc_1800ABB4C
0x1800abb37  mov     al, [rbx+0Ah]
0x1800abb3a  xor     al, [rbx+9]
0x1800abb3d  xor     al, [rbx+8]
0x1800abb40  mov     [rbx+0Bh], al
0x1800abb43  mov     eax, [rdi+88h]
0x1800abb49  xor     [rbx+8], eax
0x1800abb4c  add     rbx, r15
0x1800abb4f  jmp     loc_1800ABA77
0x1800abb54  mov     rcx, rax
0x1800abb57  mov     rax, rbx
0x1800abb5a  and     rax, 0FFFFFFFFFFFF0000h
0x1800abb60  shl     rcx, 10h
0x1800abb64  sub     rax, rcx
0x1800abb67  add     rax, 10000h
0x1800abb6d  jmp     short loc_1800ABB1E
0x1800abb6f  mov     rax, gs:60h
0x1800abb78  cmp     [rax+18h], r10
0x1800abb7c  jnz     loc_1800ABC14
0x1800abb82  lea     rcx, aHeap; "HEAP: "
0x1800abb89  call    DbgPrint
0x1800abb8e  movzx   r8d, word ptr [rbx+0Ch]
0x1800abb93  lea     rcx, aHeapEntryPHasI; "Heap entry %p has incorrect PreviousSiz"...
0x1800abb9a  movzx   eax, word ptr [rdi+8Ch]
0x1800abba1  mov     rdx, rbx
0x1800abba4  xor     r8d, eax
0x1800abba7  movzx   r9d, r12w
0x1800abbab  call    DbgPrint
0x1800abbb0  cmp     dword ptr [rdi+7Ch], 0
0x1800abbb4  jz      short loc_1800ABBCB
0x1800abbb6  mov     al, [rbx+0Ah]
0x1800abbb9  xor     al, [rbx+9]
0x1800abbbc  xor     al, [rbx+8]
0x1800abbbf  mov     [rbx+0Bh], al
0x1800abbc2  mov     eax, [rdi+88h]
0x1800abbc8  xor     [rbx+8], eax
0x1800abbcb  xor     al, al
0x1800abbcd  mov     rbx, [rsp+68h+arg_0]
0x1800abbd2  add     rsp, 30h
0x1800abbd6  pop     r15
0x1800abbd8  pop     r14
0x1800abbda  pop     r13
0x1800abbdc  pop     r12
0x1800abbde  pop     rdi
0x1800abbdf  pop     rsi
0x1800abbe0  pop     rbp
0x1800abbe1  retn
0x1800abbe3  test    byte ptr [rdi+70h], 40h
0x1800abbe7  mov     al, dl
0x1800abbe9  setnz   cl
0x1800abbec  shr     al, 2
0x1800abbef  and     cl, al
0x1800abbf1  test    cl, 1
0x1800abbf4  jnz     loc_1800ABC7E
0x1800abbfa  mov     rcx, [rsp+68h+arg_20]
0x1800abc02  movzx   eax, word ptr [rbx+8]
0x1800abc06  inc     dword ptr [r9]
0x1800abc09  add     [rcx], rax
0x1800abc0c  xor     r10d, r10d
0x1800abc0f  jmp     loc_1800ABB13
0x1800abc14  mov     rax, gs:60h
0x1800abc1d  mov     rcx, [rax+18h]
0x1800abc21  mov     rdx, [rcx+10h]
0x1800abc25  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x1800abc2c  add     rdx, 58h ; 'X'
0x1800abc30  call    DbgPrint
0x1800abc35  jmp     loc_1800ABB8E
0x1800abc3a  mov     rsi, [rbx+38h]
0x1800abc3e  test    rsi, rsi
0x1800abc41  jnz     loc_1800ABD29
0x1800abc47  movzx   eax, word ptr [rbx+8]
0x1800abc4b  shl     rax, 4
0x1800abc4f  add     rax, rbx
0x1800abc52  cmp     rax, [rbp+48h]
0x1800abc56  jnz     loc_1800AC002
0x1800abc5c  cmp     [rdi+7Ch], r10d
0x1800abc60  jz      short loc_1800ABC77
0x1800abc62  mov     al, [rbx+0Ah]
0x1800abc65  xor     al, [rbx+9]
0x1800abc68  xor     al, [rbx+8]
0x1800abc6b  mov     [rbx+0Bh], al
0x1800abc6e  mov     eax, [rdi+88h]
0x1800abc74  xor     [rbx+8], eax
0x1800abc77  mov     al, 1
0x1800abc79  jmp     loc_1800ABBCD
0x1800abc7e  lea     rsi, [r15-20h]
0x1800abc82  test    dl, 2
0x1800abc85  jnz     loc_1800AC1C5
0x1800abc8b  test    dl, 8
0x1800abc8e  jz      loc_1800ABF66
0x1800abc94  mov     r14, [rbx+18h]
0x1800abc98  lea     r15, [rbx+10h]
0x1800abc9c  mov     rsi, [r15]
0x1800abc9f  mov     rax, [r14]
0x1800abca2  mov     r9, [rsi+8]
0x1800abca6  cmp     rax, r15
0x1800abca9  jnz     loc_1800AC0F4
0x1800abcaf  cmp     rax, r9
0x1800abcb2  jnz     loc_1800AC0F4
0x1800abcb8  sub     [rdi+0C0h], r8
0x1800abcbf  mov     rdx, [rdi+138h]
0x1800abcc6  test    rdx, rdx
0x1800abcc9  jz      loc_1800ABE56
0x1800abccf  movzx   r8d, word ptr [rbx+8]
0x1800abcd4  mov     ecx, [rdx+8]
0x1800abcd7  cmp     r8, rcx
0x1800abcda  jb      loc_1800ABE39
0x1800abce0  mov     rax, [rdx]
0x1800abce3  test    rax, rax
0x1800abce6  jz      loc_1800AC130
0x1800abcec  mov     rdx, rax
0x1800abcef  jmp     short loc_1800ABCD4
0x1800abcf1  cmp     [rbp+50h], r14d
0x1800abcf5  jnz     loc_1800AC06C
0x1800abcfb  cmp     [rbp+54h], r13d
0x1800abcff  jz      loc_1800ABC77
0x1800abd05  mov     rax, gs:60h
0x1800abd0e  cmp     [rax+18h], r10
0x1800abd12  jnz     loc_1800AC0B0
0x1800abd18  lea     rcx, aHeap; "HEAP: "
0x1800abd1f  call    DbgPrint
0x1800abd24  jmp     loc_1800AC0D1
0x1800abd29  cmp     [rdi+7Ch], r10d
0x1800abd2d  jz      short loc_1800ABD44
0x1800abd2f  mov     al, [rbx+0Ah]
0x1800abd32  xor     al, [rbx+9]
0x1800abd35  xor     al, [rbx+8]
0x1800abd38  mov     [rbx+0Bh], al
0x1800abd3b  mov     eax, [rdi+88h]
0x1800abd41  xor     [rbx+8], eax
0x1800abd44  add     rbx, 40h ; '@'
0x1800abd48  add     rbx, rsi
0x1800abd4b  cmp     rbx, [rbp+48h]
0x1800abd4f  jz      short loc_1800ABDC8
0x1800abd51  cmp     [rdi+7Ch], r10d
0x1800abd55  jz      short loc_1800ABD7C
0x1800abd57  mov     eax, [rdi+88h]
0x1800abd5d  xor     [rbx+8], eax
0x1800abd60  mov     al, [rbx+0Ah]
0x1800abd63  xor     al, [rbx+9]
0x1800abd66  xor     al, [rbx+8]
0x1800abd69  cmp     [rbx+0Bh], al
0x1800abd6c  jz      short loc_1800ABD7C
0x1800abd6e  mov     rdx, rbx
0x1800abd71  mov     rcx, rdi
0x1800abd74  call    RtlpAnalyzeHeapFailure
0x1800abd79  xor     r10d, r10d
0x1800abd7c  movzx   eax, word ptr [rbx+0Ch]
0x1800abd80  cmp     [rdi+8Ch], ax
0x1800abd87  jz      short loc_1800ABDAD
0x1800abd89  mov     rax, gs:60h
0x1800abd92  cmp     [rax+18h], r10
0x1800abd96  jnz     loc_1800AC137
0x1800abd9c  lea     rcx, aHeap; "HEAP: "
0x1800abda3  call    DbgPrint
0x1800abda8  jmp     loc_1800AC158
0x1800abdad  cmp     [rdi+7Ch], r10d
0x1800abdb1  jz      short loc_1800ABDC8
0x1800abdb3  mov     al, [rbx+0Ah]
0x1800abdb6  xor     al, [rbx+9]
0x1800abdb9  xor     al, [rbx+8]
0x1800abdbc  mov     [rbx+0Bh], al
0x1800abdbf  mov     eax, [rdi+88h]
0x1800abdc5  xor     [rbx+8], eax
0x1800abdc8  inc     r13d
0x1800abdcb  shr     rsi, 0Ch
0x1800abdcf  add     r14d, esi
0x1800abdd2  mov     r12d, r10d
0x1800abdd5  mov     [rsp+68h+arg_10], r14d
0x1800abddd  jmp     short loc_1800ABE2C
0x1800abddf  mov     r8, rcx
0x1800abde2  mov     [rsp+68h+var_40], rcx
0x1800abde7  mov     r9, r15
0x1800abdea  mov     dword ptr [rsp+68h+var_48], r8d
0x1800abdef  mov     rcx, rdi
0x1800abdf2  mov     r8b, 1
0x1800abdf5  call    RtlpHeapAddListEntry
0x1800abdfa  xor     r10d, r10d
0x1800abdfd  mov     r14d, [rsp+68h+arg_10]
0x1800abe05  mov     r9, [rsp+68h+arg_18]
0x1800abe0d  cmp     [rdi+7Ch], r10d
0x1800abe11  jz      loc_1800ABA77
0x1800abe17  mov     al, [rbx+0Ah]
0x1800abe1a  xor     al, [rbx+9]
0x1800abe1d  xor     al, [rbx+8]
0x1800abe20  mov     [rbx+0Bh], al
0x1800abe23  mov     eax, [rdi+88h]
0x1800abe29  xor     [rbx+8], eax
0x1800abe2c  mov     r9, [rsp+68h+arg_18]
0x1800abe34  jmp     loc_1800ABA77
0x1800abe39  mov     rcx, r8
0x1800abe3c  mov     [rsp+68h+var_40], r8
0x1800abe41  mov     r9, r15
0x1800abe44  mov     dword ptr [rsp+68h+var_48], ecx
0x1800abe48  mov     r8b, 1
0x1800abe4b  mov     rcx, rdi
0x1800abe4e  call    RtlpHeapRemoveListEntry
0x1800abe53  xor     r10d, r10d
0x1800abe56  mov     [r14], rsi
0x1800abe59  mov     [rsi+8], r14
0x1800abe5d  test    byte ptr [rbx+0Ah], 8
0x1800abe61  jnz     loc_1800AC232
0x1800abe67  movzx   r14d, word ptr [rbx+8]
0x1800abe6c  lea     rsi, [rdi+150h]
0x1800abe73  mov     [rbx+0Ah], r10b
0x1800abe77  mov     [rbx+0Fh], r10b
0x1800abe7b  cmp     [rdi+138h], r10
0x1800abe82  jz      loc_1800AC260
0x1800abe88  mov     edx, r14d
0x1800abe8b  mov     rcx, rdi
0x1800abe8e  call    RtlpFindEntry
0x1800abe93  mov     r8, rax
0x1800abe96  xor     r10d, r10d
0x1800abe99  cmp     rsi, r8
0x1800abe9c  jz      short loc_1800ABEC3
0x1800abe9e  cmp     [rdi+7Ch], r10d
0x1800abea2  jz      loc_1800AC126
0x1800abea8  mov     eax, [r8-8]
0x1800abeac  test    [rdi+7Ch], eax
0x1800abeaf  jz      short loc_1800ABEB7
0x1800abeb1  xor     eax, [rdi+88h]
0x1800abeb7  movzx   eax, ax
0x1800abeba  cmp     r14, rax
0x1800abebd  ja      loc_1800AC20B
0x1800abec3  mov     rax, [r8+8]
0x1800abec7  mov     rcx, [rax]
0x1800abeca  cmp     rcx, r8
0x1800abecd  jnz     loc_1800AC213
0x1800abed3  mov     [r15], r8
0x1800abed6  mov     [r15+8], rax
0x1800abeda  mov     [rax], r15
0x1800abedd  mov     [r8+8], r15
0x1800abee1  movzx   eax, word ptr [rbx+8]
0x1800abee5  add     [rdi+0C0h], rax
0x1800abeec  mov     rdx, [rdi+138h]
0x1800abef3  test    rdx, rdx
0x1800abef6  jz      loc_1800ABDFD
  ... truncated ...
```
