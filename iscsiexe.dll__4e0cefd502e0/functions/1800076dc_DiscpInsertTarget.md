# DiscpInsertTarget

- ea: `0x1800076dc`
- end: `0x1800078a5`
- name: `DiscpInsertTarget`
- size: `457`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001fb8`
- `0x1800027cc`
- `0x1800076dc`
- `0x1800078ac`
- `0x18000e040`

## callees

- `0x180006404`
- `0x1800076dc`
- `0x1800079ac`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180007851`
- `ISCSIUM!DiscpFreeMemory` at `0x180007851`
- `ntdll!RtlLeaveCriticalSection` at `0x18000788d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000788d`
- `ntdll!RtlEnterCriticalSection` at `0x180007701`
- `ntdll!RtlEnterCriticalSection` at `0x180007701`

## pseudocode

```c
__int64 __fastcall DiscpInsertTarget(__int64 a1, char a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // r8
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  __int64 v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  unsigned int inserted; // ebx
  _QWORD *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp+8h] BYREF

  v17 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( (unsigned int)DiscpFindTarget(*(_QWORD *)(a1 + 48), 0, 0, &v17) )
  {
    v15 = off_180027018[0];
    if ( *(_UNKNOWN ***)off_180027018[0] != &DiscpTargetsList )
      goto LABEL_21;
    *(_QWORD *)a1 = &DiscpTargetsList;
    *(_QWORD *)(a1 + 8) = v15;
    *v15 = a1;
    off_180027018[0] = (_UNKNOWN **)a1;
    inserted = 0;
  }
  else
  {
    v4 = v17;
    v5 = (_QWORD *)(v17 + 16);
    v6 = (_QWORD *)(v17 + 16);
    while ( 1 )
    {
      v7 = v6 - 2;
      if ( *((_DWORD *)v6 + 7) == *(_DWORD *)(a1 + 44) )
      {
        if ( a2 )
        {
          DiscpRemoveTarget(v6 - 2);
          inserted = DiscpInsertTarget(a1, 0);
        }
        else
        {
          inserted = -268500968;
        }
        goto LABEL_18;
      }
      if ( *(_DWORD *)(a1 + 40) > *((_DWORD *)v7 + 10) )
        break;
      v6 = (_QWORD *)*v6;
      if ( v6 == v5 )
      {
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        v8 = (_QWORD *)v5[1];
        if ( (_QWORD *)*v8 == v5 )
        {
          *(_QWORD *)(a1 + 16) = v5;
          *(_QWORD *)(a1 + 24) = v8;
          *v8 = a1 + 16;
          v5[1] = a1 + 16;
          goto LABEL_14;
        }
LABEL_21:
        __fastfail(3u);
      }
    }
    v9 = *v7;
    if ( *v7 )
    {
      if ( *(_QWORD **)(v9 + 8) != v7 )
        goto LABEL_21;
      v10 = (_QWORD *)v7[1];
      if ( (_QWORD *)*v10 != v7 )
        goto LABEL_21;
      *v10 = v9;
      *(_QWORD *)(v9 + 8) = v10;
      v11 = (_QWORD *)v7[3];
      *v7 = 0;
      v7[1] = 0;
      *(_QWORD *)(a1 + 16) = v6;
      *(_QWORD *)(a1 + 24) = v11;
      v7[3] = a1 + 16;
      *v11 = a1 + 16;
      v12 = off_180027018[0];
      if ( *(_UNKNOWN ***)off_180027018[0] != &DiscpTargetsList )
        goto LABEL_21;
      *(_QWORD *)a1 = &DiscpTargetsList;
      *(_QWORD *)(a1 + 8) = v12;
      *v12 = a1;
      off_180027018[0] = (_UNKNOWN **)a1;
    }
    else
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      v13 = (_QWORD *)v7[3];
      *(_QWORD *)(a1 + 16) = v6;
      *(_QWORD *)(a1 + 24) = v13;
      v7[3] = a1 + 16;
      *v13 = a1 + 16;
    }
LABEL_14:
    inserted = 0;
LABEL_18:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 32), 0xFFFFFFFF) == 1 )
      DiscpFreeMemory(v4);
  }
  RtlLeaveCriticalSection(&DiscpCritSection);
  return inserted;
}

```

## disassembly

```asm
0x1800076dc  mov     [rsp+arg_8], rbx
0x1800076e1  mov     [rsp+arg_10], rsi
0x1800076e6  push    rdi
0x1800076e7  sub     rsp, 20h
0x1800076eb  mov     rbx, rcx
0x1800076ee  mov     [rsp+28h+arg_0], 0
0x1800076f7  lea     rcx, DiscpCritSection; CriticalSection
0x1800076fe  mov     sil, dl
0x180007701  call    cs:__imp_RtlEnterCriticalSection
0x180007707  mov     rcx, [rbx+30h]
0x18000770b  lea     r9, [rsp+28h+arg_0]
0x180007710  xor     r8d, r8d
0x180007713  xor     edx, edx
0x180007715  call    DiscpFindTarget
0x18000771a  test    eax, eax
0x18000771c  jnz     loc_180007859
0x180007722  mov     rdi, [rsp+28h+arg_0]
0x180007727  mov     r9d, [rbx+2Ch]
0x18000772b  lea     rcx, [rdi+10h]
0x18000772f  mov     r8, rcx
0x180007732  lea     rdx, [r8-10h]
0x180007736  cmp     [rdx+2Ch], r9d
0x18000773a  jz      loc_180007821
0x180007740  mov     eax, [rdx+28h]
0x180007743  cmp     [rbx+28h], eax
0x180007746  jg      short loc_180007783
0x180007748  mov     r8, [r8]
0x18000774b  cmp     r8, rcx
0x18000774e  jnz     short loc_180007732
0x180007750  mov     qword ptr [rbx], 0
0x180007757  mov     qword ptr [rbx+8], 0
0x18000775f  mov     rdx, [rcx+8]
0x180007763  cmp     [rdx], rcx
0x180007766  jnz     loc_18000786C
0x18000776c  lea     rax, [rbx+10h]
0x180007770  mov     [rax], rcx
0x180007773  mov     [rax+8], rdx
0x180007777  mov     [rdx], rax
0x18000777a  mov     [rcx+8], rax
0x18000777e  jmp     loc_18000781D
0x180007783  mov     rax, [rdx]
0x180007786  test    rax, rax
0x180007789  jz      short loc_1800077F8
0x18000778b  cmp     [rax+8], rdx
0x18000778f  jnz     loc_18000786C
0x180007795  mov     rcx, [rdx+8]
0x180007799  cmp     [rcx], rdx
0x18000779c  jnz     loc_18000786C
0x1800077a2  mov     [rcx], rax
0x1800077a5  mov     [rax+8], rcx
0x1800077a9  lea     rax, [rbx+10h]
0x1800077ad  mov     rcx, [rdx+18h]
0x1800077b1  mov     qword ptr [rdx], 0
0x1800077b8  mov     qword ptr [rdx+8], 0
0x1800077c0  mov     [rax], r8
0x1800077c3  mov     [rbx+18h], rcx
0x1800077c7  mov     [rdx+18h], rax
0x1800077cb  mov     [rcx], rax
0x1800077ce  lea     rax, DiscpTargetsList
0x1800077d5  mov     rcx, cs:off_180027018
0x1800077dc  cmp     [rcx], rax
0x1800077df  jnz     loc_18000786C
0x1800077e5  mov     [rbx], rax
0x1800077e8  mov     [rbx+8], rcx
0x1800077ec  mov     [rcx], rbx
0x1800077ef  mov     cs:off_180027018, rbx
0x1800077f6  jmp     short loc_18000781D
0x1800077f8  mov     qword ptr [rbx], 0
0x1800077ff  lea     rax, [rbx+10h]
0x180007803  mov     qword ptr [rbx+8], 0
0x18000780b  mov     rcx, [rdx+18h]
0x18000780f  mov     [rax], r8
0x180007812  mov     [rbx+18h], rcx
0x180007816  mov     [rdx+18h], rax
0x18000781a  mov     [rcx], rax
0x18000781d  xor     ebx, ebx
0x18000781f  jmp     short loc_180007841
0x180007821  test    sil, sil
0x180007824  jz      short loc_18000783C
0x180007826  mov     rcx, rdx
0x180007829  call    DiscpRemoveTarget
0x18000782e  xor     edx, edx
0x180007830  mov     rcx, rbx
0x180007833  call    DiscpInsertTarget
0x180007838  mov     ebx, eax
0x18000783a  jmp     short loc_180007841
0x18000783c  mov     ebx, 0EFFF0018h
0x180007841  or      eax, 0FFFFFFFFh
0x180007844  lock xadd [rdi+20h], eax
0x180007849  cmp     eax, 1
0x18000784c  jnz     short loc_180007886
0x18000784e  mov     rcx, rdi
0x180007851  call    cs:__imp_DiscpFreeMemory
0x180007857  jmp     short loc_180007886
0x180007859  mov     rcx, cs:off_180027018
0x180007860  lea     rax, DiscpTargetsList
0x180007867  cmp     [rcx], rax
0x18000786a  jz      short loc_180007873
0x18000786c  mov     ecx, 3
0x180007871  int     29h; Win8: RtlFailFast(ecx)
0x180007873  mov     [rbx], rax
0x180007876  mov     [rbx+8], rcx
0x18000787a  mov     [rcx], rbx
0x18000787d  mov     cs:off_180027018, rbx
0x180007884  xor     ebx, ebx
0x180007886  lea     rcx, DiscpCritSection; CriticalSection
0x18000788d  call    cs:__imp_RtlLeaveCriticalSection
0x180007893  mov     rsi, [rsp+28h+arg_10]
0x180007898  mov     eax, ebx
0x18000789a  mov     rbx, [rsp+28h+arg_8]
0x18000789f  add     rsp, 20h
0x1800078a3  pop     rdi
0x1800078a4  retn
```
