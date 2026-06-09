# QuicBindingCreateStatelessOperation

- ea: `0x14003ff2c`
- end: `0x1400401ac`
- name: `QuicBindingCreateStatelessOperation`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002697c`

## callees

- `0x140004840`
- `0x140010820`
- `0x140026a88`
- `0x1400290b4`
- `0x140029104`
- `0x1400291a4`
- `0x140038a6c`
- `0x140038b04`
- `0x140038b78`
- `0x140038bc8`
- `0x14003ff2c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ffe5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ffe5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004017e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004017e`
- `HAL!KeQueryPerformanceCounter` at `0x14003ff54`
- `HAL!KeQueryPerformanceCounter` at `0x14003ff54`

## string_xrefs

- `0x140040103`: `Already in stateless oper table`

## pseudocode

```c
PSLIST_ENTRY __fastcall QuicBindingCreateStatelessOperation(__int64 a1, __int64 a2, __int64 a3)
{
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned __int64 v6; // rax
  __int64 v7; // r14
  unsigned __int64 v8; // r12
  __int64 v9; // rbx
  unsigned __int8 *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  unsigned __int8 *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  PSLIST_ENTRY v16; // rsi
  _DWORD *v17; // r15
  __int64 v18; // rax
  __int64 v19; // r10
  __int64 *v20; // r10
  _QWORD *v21; // rax
  __int64 v22; // rdx
  const char *v23; // r8
  __int64 i; // rax
  PSLIST_ENTRY v25; // rax
  _QWORD *v26; // rax
  __int128 v28; // [rsp+20h] [rbp-48h] BYREF
  __int64 v29; // [rsp+30h] [rbp-38h]

  PerformanceCounter = KeQueryPerformanceCounter(0);
  v6 = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
  v7 = *(_QWORD *)(a3 + 8);
  v8 = v6 / 0x3E8;
  LODWORD(v9) = HIBYTE(*(unsigned __int16 *)(v7 + 10)) + 31 * ((unsigned __int8)*(_WORD *)(v7 + 10) + 166997);
  if ( *(_WORD *)(v7 + 8) == 2 )
  {
    v10 = (unsigned __int8 *)(v7 + 12);
    v11 = 4;
    do
    {
      v12 = *v10++;
      v9 = (unsigned int)(v12 + 31 * v9);
      --v11;
    }
    while ( v11 );
  }
  else
  {
    v13 = (unsigned __int8 *)(v7 + 16);
    v14 = 16;
    do
    {
      v15 = *v13++;
      v9 = (unsigned int)(v15 + 31 * v9);
      --v14;
    }
    while ( v14 );
  }
  v16 = 0;
  *(_BYTE *)(a1 + 136) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 128));
  if ( *(_DWORD *)(a1 + 20) )
  {
    v17 = (_DWORD *)(a1 + 304);
LABEL_9:
    v18 = a1 + 184;
    while ( *(_QWORD *)v18 != v18
         && (unsigned int)CxPlatTimeDiff32(*(unsigned int *)(*(_QWORD *)v18 + 48LL), (unsigned int)v8) >= (unsigned __int16)word_14005C536 )
    {
      *(_BYTE *)(v19 + 52) |= 4u;
      CxPlatHashtableRemove(a1 + 144, v19 + 16);
      v21 = (_QWORD *)v20[1];
      v22 = *v20;
      *v21 = *v20;
      *(_QWORD *)(v22 + 8) = v21;
      v18 = a1 + 184;
      --*(_DWORD *)(a1 + 304);
      if ( (*((_BYTE *)v20 + 52) & 2) != 0 )
      {
        CxPlatPoolFree(v20 - 6);
        goto LABEL_9;
      }
    }
    if ( *v17 < (unsigned int)(unsigned __int16)word_14005C534 )
    {
      v29 = 0;
      v28 = 0;
      for ( i = CxPlatHashtableLookup(a1 + 144, v9, &v28); i; i = CxPlatHashtableLookupNext(a1 + 144, &v28) )
      {
        if ( (unsigned __int8)QuicAddrCompare(i - 48, v7 + 8) )
        {
          v23 = "Already in stateless oper table";
          goto LABEL_16;
        }
      }
      v25 = CxPlatPoolAlloc(*(_QWORD *)(a2 + 48) + 1920LL);
      v16 = v25;
      if ( !v25 )
      {
        v23 = "Alloc failure for stateless oper ctx";
        goto LABEL_16;
      }
      BYTE4(v25[6].Next) &= 0xF8u;
      v25->Next = (struct _SLIST_ENTRY *)a1;
      *((_QWORD *)&v25->Next + 1) = a2;
      *((_QWORD *)&v25[5].Next + 1) = a3;
      LODWORD(v25[6].Next) = v8;
      v25[1] = *(PSLIST_ENTRY)(v7 + 8);
      v25[2].Next = *(struct _SLIST_ENTRY **)(v7 + 24);
      *((_DWORD *)&v25[2].Next + 2) = *(_DWORD *)(v7 + 32);
      CxPlatHashtableInsert(a1 + 144, &v25[4], v9);
      v26 = *(_QWORD **)(a1 + 192);
      v16[3].Next = (struct _SLIST_ENTRY *)(a1 + 184);
      *((_QWORD *)&v16[3].Next + 1) = v26;
      *v26 = v16 + 3;
      ++*v17;
      *(_QWORD *)(a1 + 192) = v16 + 3;
    }
    else
    {
      v23 = "Max binding operations reached";
LABEL_16:
      QuicPacketLogDrop(a1, a3, v23);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 128), *(_BYTE *)(a1 + 136));
  return v16;
}

```

## disassembly

```asm
0x14003ff2c  mov     rax, rsp
0x14003ff2f  mov     [rax+8], rbx
0x14003ff33  mov     [rax+18h], rbp
0x14003ff37  mov     [rax+20h], rsi
0x14003ff3b  mov     [rax+10h], rdx
0x14003ff3f  push    rdi
0x14003ff40  push    r12
0x14003ff42  push    r13
0x14003ff44  push    r14
0x14003ff46  push    r15
0x14003ff48  sub     rsp, 40h
0x14003ff4c  mov     rdi, rcx
0x14003ff4f  mov     r13, r8
0x14003ff52  xor     ecx, ecx; PerformanceFrequency
0x14003ff54  call    cs:__imp_KeQueryPerformanceCounter
0x14003ff5b  nop     dword ptr [rax+rax+00h]
0x14003ff60  mov     rcx, rax
0x14003ff63  call    QuicTimePlatToUs64
0x14003ff68  mov     r14, [r13+8]
0x14003ff6c  mov     r12, rax
0x14003ff6f  mov     rax, 624DD2F1A9FBE77h
0x14003ff79  mul     r12
0x14003ff7c  movzx   ecx, word ptr [r14+0Ah]
0x14003ff81  sub     r12, rdx
0x14003ff84  movzx   eax, cl
0x14003ff87  shr     r12, 1
0x14003ff8a  add     eax, 28C55h
0x14003ff8f  imul    ebx, eax, 1Fh
0x14003ff92  add     r12, rdx
0x14003ff95  shr     ecx, 8
0x14003ff98  shr     r12, 9
0x14003ff9c  add     ebx, ecx
0x14003ff9e  cmp     word ptr [r14+8], 2
0x14003ffa4  jnz     short loc_14003FFC2
0x14003ffa6  lea     rcx, [r14+0Ch]
0x14003ffaa  mov     edx, 4
0x14003ffaf  movzx   eax, byte ptr [rcx]
0x14003ffb2  inc     rcx
0x14003ffb5  imul    ebx, 1Fh
0x14003ffb8  add     ebx, eax
0x14003ffba  sub     rdx, 1
0x14003ffbe  jnz     short loc_14003FFAF
0x14003ffc0  jmp     short loc_14003FFDC
0x14003ffc2  lea     rcx, [r14+10h]
0x14003ffc6  mov     edx, 10h
0x14003ffcb  movzx   eax, byte ptr [rcx]
0x14003ffce  inc     rcx
0x14003ffd1  imul    ebx, 1Fh
0x14003ffd4  add     ebx, eax
0x14003ffd6  sub     rdx, 1
0x14003ffda  jnz     short loc_14003FFCB
0x14003ffdc  lea     rcx, [rdi+80h]; SpinLock
0x14003ffe3  xor     esi, esi
0x14003ffe5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003ffec  nop     dword ptr [rax+rax+00h]
0x14003fff1  mov     [rdi+88h], al
0x14003fff7  cmp     [rdi+14h], esi
0x14003fffa  jz      loc_140040171
0x140040000  lea     r15, [rdi+130h]
0x140040007  lea     rbp, [rdi+90h]
0x14004000e  lea     rax, [rdi+0B8h]
0x140040015  mov     r10, [rax]
0x140040018  cmp     r10, rax
0x14004001b  jz      short loc_140040076
0x14004001d  mov     ecx, [r10+30h]
0x140040021  mov     edx, r12d
0x140040024  call    CxPlatTimeDiff32
0x140040029  movzx   ecx, cs:word_14005C536
0x140040030  cmp     eax, ecx
0x140040032  jb      short loc_140040076
0x140040034  or      byte ptr [r10+34h], 4
0x140040039  lea     rdx, [r10+10h]
0x14004003d  lea     rcx, [rdi+90h]
0x140040044  call    CxPlatHashtableRemove
0x140040049  mov     rax, [r10+8]
0x14004004d  mov     rdx, [r10]
0x140040050  mov     [rax], rdx
0x140040053  mov     [rdx+8], rax
0x140040057  lea     rax, [rdi+0B8h]
0x14004005e  dec     dword ptr [rdi+130h]
0x140040064  test    byte ptr [r10+34h], 2
0x140040069  jz      short loc_140040015
0x14004006b  lea     rcx, [r10-30h]
0x14004006f  call    CxPlatPoolFree
0x140040074  jmp     short loc_14004000E
0x140040076  movzx   eax, cs:word_14005C534
0x14004007d  cmp     [r15], eax
0x140040080  jb      short loc_140040099
0x140040082  lea     r8, aMaxBindingOper; "Max binding operations reached"
0x140040089  mov     rdx, r13
0x14004008c  mov     rcx, rdi
0x14004008f  call    QuicPacketLogDrop
0x140040094  jmp     loc_140040171
0x140040099  xorps   xmm0, xmm0
0x14004009c  lea     r8, [rsp+68h+var_48]
0x1400400a1  xor     eax, eax
0x1400400a3  mov     rdx, rbx
0x1400400a6  mov     rcx, rbp
0x1400400a9  mov     [rsp+68h+var_38], rax
0x1400400ae  movups  [rsp+68h+var_48], xmm0
0x1400400b3  call    CxPlatHashtableLookup
0x1400400b8  jmp     short loc_1400400D8
0x1400400ba  lea     rcx, [rax-30h]
0x1400400be  lea     rdx, [r14+8]
0x1400400c2  call    QuicAddrCompare
0x1400400c7  test    al, al
0x1400400c9  jnz     short loc_140040103
0x1400400cb  lea     rdx, [rsp+68h+var_48]
0x1400400d0  mov     rcx, rbp
0x1400400d3  call    CxPlatHashtableLookupNext
0x1400400d8  test    rax, rax
0x1400400db  jnz     short loc_1400400BA
0x1400400dd  mov     rcx, [rsp+68h+arg_8]
0x1400400e2  mov     rcx, [rcx+30h]
0x1400400e6  add     rcx, 780h
0x1400400ed  call    CxPlatPoolAlloc
0x1400400f2  mov     rsi, rax
0x1400400f5  test    rax, rax
0x1400400f8  jnz     short loc_14004010F
0x1400400fa  lea     r8, aAllocFailureFo_0; "Alloc failure for stateless oper ctx"
0x140040101  jmp     short loc_140040089
0x140040103  lea     r8, aAlreadyInState; "Already in stateless oper table"
0x14004010a  jmp     loc_140040089
0x14004010f  and     byte ptr [rsi+64h], 0F8h
0x140040113  lea     rdx, [rsi+40h]
0x140040117  mov     [rax], rdi
0x14004011a  mov     r8, rbx
0x14004011d  mov     rax, [rsp+68h+arg_8]
0x140040122  mov     rcx, rbp
0x140040125  mov     [rsi+8], rax
0x140040129  mov     [rsi+58h], r13
0x14004012d  mov     [rsi+60h], r12d
0x140040131  movups  xmm0, xmmword ptr [r14+8]
0x140040136  movups  xmmword ptr [rsi+10h], xmm0
0x14004013a  movsd   xmm1, qword ptr [r14+18h]
0x140040140  movsd   qword ptr [rsi+20h], xmm1
0x140040145  mov     eax, [r14+20h]
0x140040149  mov     [rsi+28h], eax
0x14004014c  call    CxPlatHashtableInsert
0x140040151  lea     rdx, [rsi+30h]
0x140040155  lea     r8, [rdi+0B8h]
0x14004015c  mov     rax, [r8+8]
0x140040160  mov     [rdx], r8
0x140040163  mov     [rdx+8], rax
0x140040167  mov     [rax], rdx
0x14004016a  inc     dword ptr [r15]
0x14004016d  mov     [r8+8], rdx
0x140040171  mov     dl, [rdi+88h]; NewIrql
0x140040177  lea     rcx, [rdi+80h]; SpinLock
0x14004017e  call    cs:__imp_KeReleaseSpinLock
0x140040185  nop     dword ptr [rax+rax+00h]
0x14004018a  lea     r11, [rsp+68h+var_28]
0x14004018f  mov     rax, rsi
0x140040192  mov     rbx, [r11+30h]
0x140040196  mov     rbp, [r11+40h]
0x14004019a  mov     rsi, [r11+48h]
0x14004019e  mov     rsp, r11
0x1400401a1  pop     r15
0x1400401a3  pop     r14
0x1400401a5  pop     r13
0x1400401a7  pop     r12
0x1400401a9  pop     rdi
0x1400401aa  retn
```
