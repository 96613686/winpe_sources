# RtlpValidateHeapSegment

- ea: `0x1800b440c`
- end: `0x1800b4c4d`
- name: `RtlpValidateHeapSegment`
- size: `2113`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800b2c9c`

## callees

- `0x180004350`
- `0x180004460`
- `0x180007060`
- `0x1800070f0`
- `0x180007450`
- `0x180008124`
- `0x180008488`
- `0x1800b2508`
- `0x1800b3b20`
- `0x1800b440c`
- `0x18011d208`
- `0x180162de0`

## string_xrefs

- `0x1800b4aa5`: `Heap Segment at %p contains invalid NumberOfUnCommittedRanges (%x != %x)\n`
- `0x1800b4a74`: `Heap Segment at %p contains invalid NumberOfUnCommittedPages (%x != %x)\n`

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
0x1800b440c  mov     [rsp+arg_0], rbx
0x1800b4411  mov     [rsp+arg_18], r9
0x1800b4416  mov     byte ptr [rsp+arg_10], r8b
0x1800b441b  push    rbp
0x1800b441c  push    rsi
0x1800b441d  push    rdi
0x1800b441e  push    r12
0x1800b4420  push    r13
0x1800b4422  push    r14
0x1800b4424  push    r15
0x1800b4426  sub     rsp, 30h
0x1800b442a  xor     r10d, r10d
0x1800b442d  mov     rbp, rdx
0x1800b4430  mov     r14d, r10d
0x1800b4433  mov     [rsp+68h+arg_10], r10d
0x1800b443b  mov     r13d, r10d
0x1800b443e  mov     r12d, r10d
0x1800b4441  mov     rdi, rcx
0x1800b4444  mov     rbx, rdx
0x1800b4447  cmp     rbx, [rbp+48h]
0x1800b444b  jnb     loc_1800B46C1
0x1800b4451  mov     rax, [rsp+68h+arg_28]
0x1800b4459  mov     [rax], rbx
0x1800b445c  cmp     [rdi+7Ch], r10d
0x1800b4460  jz      short loc_1800B448F
0x1800b4462  mov     eax, [rdi+88h]
0x1800b4468  xor     [rbx+8], eax
0x1800b446b  mov     al, [rbx+0Ah]
0x1800b446e  xor     al, [rbx+9]
0x1800b4471  xor     al, [rbx+8]
0x1800b4474  cmp     [rbx+0Bh], al
0x1800b4477  jz      short loc_1800B448F
0x1800b4479  mov     rdx, rbx
0x1800b447c  mov     rcx, rdi
0x1800b447f  call    RtlpAnalyzeHeapFailure
0x1800b4484  mov     r9, [rsp+68h+arg_18]
0x1800b448c  xor     r10d, r10d
0x1800b448f  movzx   eax, word ptr [rbx+0Ch]
0x1800b4493  xor     ax, [rdi+8Ch]
0x1800b449a  cmp     r12w, ax
0x1800b449e  jnz     loc_1800B453F
0x1800b44a4  movzx   r8d, word ptr [rbx+8]
0x1800b44a9  mov     dl, [rbx+0Ah]
0x1800b44ac  mov     r15d, r8d
0x1800b44af  shl     r15, 4
0x1800b44b3  movzx   r12d, r8w
0x1800b44b7  test    dl, 1
0x1800b44ba  jz      loc_1800B45B3
0x1800b44c0  mov     r9, [rsp+68h+arg_30]
0x1800b44c8  test    r9, r9
0x1800b44cb  jnz     loc_1800B48EE
0x1800b44d1  test    byte ptr [rbx+0Ah], 4
0x1800b44d5  jnz     loc_1800B4B76
0x1800b44db  mov     r9, [rsp+68h+arg_18]
0x1800b44e3  movzx   eax, byte ptr [rbx+0Eh]
0x1800b44e7  test    al, al
0x1800b44e9  jnz     short loc_1800B4524
0x1800b44eb  mov     rax, rdi
0x1800b44ee  cmp     rax, rbp
0x1800b44f1  jnz     loc_1800B49EF
0x1800b44f7  cmp     byte ptr [rbx+0Fh], 3
0x1800b44fb  jz      loc_1800B460A
0x1800b4501  cmp     [rdi+7Ch], r10d
0x1800b4505  jz      short loc_1800B451C
0x1800b4507  mov     al, [rbx+0Ah]
0x1800b450a  xor     al, [rbx+9]
0x1800b450d  xor     al, [rbx+8]
0x1800b4510  mov     [rbx+0Bh], al
0x1800b4513  mov     eax, [rdi+88h]
0x1800b4519  xor     [rbx+8], eax
0x1800b451c  add     rbx, r15
0x1800b451f  jmp     loc_1800B4447
0x1800b4524  mov     rcx, rax
0x1800b4527  mov     rax, rbx
0x1800b452a  and     rax, 0FFFFFFFFFFFF0000h
0x1800b4530  shl     rcx, 10h
0x1800b4534  sub     rax, rcx
0x1800b4537  add     rax, 10000h
0x1800b453d  jmp     short loc_1800B44EE
0x1800b453f  mov     rax, gs:60h
0x1800b4548  cmp     [rax+18h], r10
0x1800b454c  jnz     loc_1800B45E4
0x1800b4552  lea     rcx, aHeap; "HEAP: "
0x1800b4559  call    DbgPrint
0x1800b455e  movzx   r8d, word ptr [rbx+0Ch]
0x1800b4563  lea     rcx, aHeapEntryPHasI; "Heap entry %p has incorrect PreviousSiz"...
0x1800b456a  movzx   eax, word ptr [rdi+8Ch]
0x1800b4571  mov     rdx, rbx
0x1800b4574  xor     r8d, eax
0x1800b4577  movzx   r9d, r12w
0x1800b457b  call    DbgPrint
0x1800b4580  cmp     dword ptr [rdi+7Ch], 0
0x1800b4584  jz      short loc_1800B459B
0x1800b4586  mov     al, [rbx+0Ah]
0x1800b4589  xor     al, [rbx+9]
0x1800b458c  xor     al, [rbx+8]
0x1800b458f  mov     [rbx+0Bh], al
0x1800b4592  mov     eax, [rdi+88h]
0x1800b4598  xor     [rbx+8], eax
0x1800b459b  xor     al, al
0x1800b459d  mov     rbx, [rsp+68h+arg_0]
0x1800b45a2  add     rsp, 30h
0x1800b45a6  pop     r15
0x1800b45a8  pop     r14
0x1800b45aa  pop     r13
0x1800b45ac  pop     r12
0x1800b45ae  pop     rdi
0x1800b45af  pop     rsi
0x1800b45b0  pop     rbp
0x1800b45b1  retn
0x1800b45b3  test    byte ptr [rdi+70h], 40h
0x1800b45b7  mov     al, dl
0x1800b45b9  setnz   cl
0x1800b45bc  shr     al, 2
0x1800b45bf  and     cl, al
0x1800b45c1  test    cl, 1
0x1800b45c4  jnz     loc_1800B464E
0x1800b45ca  mov     rcx, [rsp+68h+arg_20]
0x1800b45d2  movzx   eax, word ptr [rbx+8]
0x1800b45d6  inc     dword ptr [r9]
0x1800b45d9  add     [rcx], rax
0x1800b45dc  xor     r10d, r10d
0x1800b45df  jmp     loc_1800B44E3
0x1800b45e4  mov     rax, gs:60h
0x1800b45ed  mov     rcx, [rax+18h]
0x1800b45f1  mov     rdx, [rcx+10h]
0x1800b45f5  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x1800b45fc  add     rdx, 58h ; 'X'
0x1800b4600  call    DbgPrint
0x1800b4605  jmp     loc_1800B455E
0x1800b460a  mov     rsi, [rbx+38h]
0x1800b460e  test    rsi, rsi
0x1800b4611  jnz     loc_1800B46F9
0x1800b4617  movzx   eax, word ptr [rbx+8]
0x1800b461b  shl     rax, 4
0x1800b461f  add     rax, rbx
0x1800b4622  cmp     rax, [rbp+48h]
0x1800b4626  jnz     loc_1800B49D2
0x1800b462c  cmp     [rdi+7Ch], r10d
0x1800b4630  jz      short loc_1800B4647
0x1800b4632  mov     al, [rbx+0Ah]
0x1800b4635  xor     al, [rbx+9]
0x1800b4638  xor     al, [rbx+8]
0x1800b463b  mov     [rbx+0Bh], al
0x1800b463e  mov     eax, [rdi+88h]
0x1800b4644  xor     [rbx+8], eax
0x1800b4647  mov     al, 1
0x1800b4649  jmp     loc_1800B459D
0x1800b464e  lea     rsi, [r15-20h]
0x1800b4652  test    dl, 2
0x1800b4655  jnz     loc_1800B4B95
0x1800b465b  test    dl, 8
0x1800b465e  jz      loc_1800B4936
0x1800b4664  mov     r14, [rbx+18h]
0x1800b4668  lea     r15, [rbx+10h]
0x1800b466c  mov     rsi, [r15]
0x1800b466f  mov     rax, [r14]
0x1800b4672  mov     r9, [rsi+8]
0x1800b4676  cmp     rax, r15
0x1800b4679  jnz     loc_1800B4AC4
0x1800b467f  cmp     rax, r9
0x1800b4682  jnz     loc_1800B4AC4
0x1800b4688  sub     [rdi+0C0h], r8
0x1800b468f  mov     rdx, [rdi+138h]
0x1800b4696  test    rdx, rdx
0x1800b4699  jz      loc_1800B4826
0x1800b469f  movzx   r8d, word ptr [rbx+8]
0x1800b46a4  mov     ecx, [rdx+8]
0x1800b46a7  cmp     r8, rcx
0x1800b46aa  jb      loc_1800B4809
0x1800b46b0  mov     rax, [rdx]
0x1800b46b3  test    rax, rax
0x1800b46b6  jz      loc_1800B4B00
0x1800b46bc  mov     rdx, rax
0x1800b46bf  jmp     short loc_1800B46A4
0x1800b46c1  cmp     [rbp+50h], r14d
0x1800b46c5  jnz     loc_1800B4A3C
0x1800b46cb  cmp     [rbp+54h], r13d
0x1800b46cf  jz      loc_1800B4647
0x1800b46d5  mov     rax, gs:60h
0x1800b46de  cmp     [rax+18h], r10
0x1800b46e2  jnz     loc_1800B4A80
0x1800b46e8  lea     rcx, aHeap; "HEAP: "
0x1800b46ef  call    DbgPrint
0x1800b46f4  jmp     loc_1800B4AA1
0x1800b46f9  cmp     [rdi+7Ch], r10d
0x1800b46fd  jz      short loc_1800B4714
0x1800b46ff  mov     al, [rbx+0Ah]
0x1800b4702  xor     al, [rbx+9]
0x1800b4705  xor     al, [rbx+8]
0x1800b4708  mov     [rbx+0Bh], al
0x1800b470b  mov     eax, [rdi+88h]
0x1800b4711  xor     [rbx+8], eax
0x1800b4714  add     rbx, 40h ; '@'
0x1800b4718  add     rbx, rsi
0x1800b471b  cmp     rbx, [rbp+48h]
0x1800b471f  jz      short loc_1800B4798
0x1800b4721  cmp     [rdi+7Ch], r10d
0x1800b4725  jz      short loc_1800B474C
0x1800b4727  mov     eax, [rdi+88h]
0x1800b472d  xor     [rbx+8], eax
0x1800b4730  mov     al, [rbx+0Ah]
0x1800b4733  xor     al, [rbx+9]
0x1800b4736  xor     al, [rbx+8]
0x1800b4739  cmp     [rbx+0Bh], al
0x1800b473c  jz      short loc_1800B474C
0x1800b473e  mov     rdx, rbx
0x1800b4741  mov     rcx, rdi
0x1800b4744  call    RtlpAnalyzeHeapFailure
0x1800b4749  xor     r10d, r10d
0x1800b474c  movzx   eax, word ptr [rbx+0Ch]
0x1800b4750  cmp     [rdi+8Ch], ax
0x1800b4757  jz      short loc_1800B477D
0x1800b4759  mov     rax, gs:60h
0x1800b4762  cmp     [rax+18h], r10
0x1800b4766  jnz     loc_1800B4B07
0x1800b476c  lea     rcx, aHeap; "HEAP: "
0x1800b4773  call    DbgPrint
0x1800b4778  jmp     loc_1800B4B28
0x1800b477d  cmp     [rdi+7Ch], r10d
0x1800b4781  jz      short loc_1800B4798
0x1800b4783  mov     al, [rbx+0Ah]
0x1800b4786  xor     al, [rbx+9]
0x1800b4789  xor     al, [rbx+8]
0x1800b478c  mov     [rbx+0Bh], al
0x1800b478f  mov     eax, [rdi+88h]
0x1800b4795  xor     [rbx+8], eax
0x1800b4798  inc     r13d
0x1800b479b  shr     rsi, 0Ch
0x1800b479f  add     r14d, esi
0x1800b47a2  mov     r12d, r10d
0x1800b47a5  mov     [rsp+68h+arg_10], r14d
0x1800b47ad  jmp     short loc_1800B47FC
0x1800b47af  mov     r8, rcx
0x1800b47b2  mov     [rsp+68h+var_40], rcx
0x1800b47b7  mov     r9, r15
0x1800b47ba  mov     dword ptr [rsp+68h+var_48], r8d
0x1800b47bf  mov     rcx, rdi
0x1800b47c2  mov     r8b, 1
0x1800b47c5  call    RtlpHeapAddListEntry
0x1800b47ca  xor     r10d, r10d
0x1800b47cd  mov     r14d, [rsp+68h+arg_10]
0x1800b47d5  mov     r9, [rsp+68h+arg_18]
0x1800b47dd  cmp     [rdi+7Ch], r10d
0x1800b47e1  jz      loc_1800B4447
0x1800b47e7  mov     al, [rbx+0Ah]
0x1800b47ea  xor     al, [rbx+9]
0x1800b47ed  xor     al, [rbx+8]
0x1800b47f0  mov     [rbx+0Bh], al
0x1800b47f3  mov     eax, [rdi+88h]
0x1800b47f9  xor     [rbx+8], eax
0x1800b47fc  mov     r9, [rsp+68h+arg_18]
0x1800b4804  jmp     loc_1800B4447
0x1800b4809  mov     rcx, r8
0x1800b480c  mov     [rsp+68h+var_40], r8
0x1800b4811  mov     r9, r15
0x1800b4814  mov     dword ptr [rsp+68h+var_48], ecx
0x1800b4818  mov     r8b, 1
0x1800b481b  mov     rcx, rdi
0x1800b481e  call    RtlpHeapRemoveListEntry
0x1800b4823  xor     r10d, r10d
0x1800b4826  mov     [r14], rsi
0x1800b4829  mov     [rsi+8], r14
0x1800b482d  test    byte ptr [rbx+0Ah], 8
0x1800b4831  jnz     loc_1800B4C02
0x1800b4837  movzx   r14d, word ptr [rbx+8]
0x1800b483c  lea     rsi, [rdi+150h]
0x1800b4843  mov     [rbx+0Ah], r10b
0x1800b4847  mov     [rbx+0Fh], r10b
0x1800b484b  cmp     [rdi+138h], r10
0x1800b4852  jz      loc_1800B4C30
0x1800b4858  mov     edx, r14d
0x1800b485b  mov     rcx, rdi
0x1800b485e  call    RtlpFindEntry
0x1800b4863  mov     r8, rax
0x1800b4866  xor     r10d, r10d
0x1800b4869  cmp     rsi, r8
0x1800b486c  jz      short loc_1800B4893
0x1800b486e  cmp     [rdi+7Ch], r10d
0x1800b4872  jz      loc_1800B4AF6
0x1800b4878  mov     eax, [r8-8]
0x1800b487c  test    [rdi+7Ch], eax
0x1800b487f  jz      short loc_1800B4887
0x1800b4881  xor     eax, [rdi+88h]
0x1800b4887  movzx   eax, ax
0x1800b488a  cmp     r14, rax
0x1800b488d  ja      loc_1800B4BDB
0x1800b4893  mov     rax, [r8+8]
0x1800b4897  mov     rcx, [rax]
0x1800b489a  cmp     rcx, r8
0x1800b489d  jnz     loc_1800B4BE3
0x1800b48a3  mov     [r15], r8
0x1800b48a6  mov     [r15+8], rax
0x1800b48aa  mov     [rax], r15
0x1800b48ad  mov     [r8+8], r15
0x1800b48b1  movzx   eax, word ptr [rbx+8]
0x1800b48b5  add     [rdi+0C0h], rax
0x1800b48bc  mov     rdx, [rdi+138h]
0x1800b48c3  test    rdx, rdx
0x1800b48c6  jz      loc_1800B47CD
  ... truncated ...
```
