# RxFinalizeFcbTable

- ea: `0x140076860`
- end: `0x14007699c`
- name: `RxFinalizeFcbTable`
- size: `316`
- prototype: `void __stdcall(PRX_FCB_TABLE FcbTable)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140076760`

## callees

- `0x140076860`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400768be`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400768be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007690b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007698b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007690b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007698b`

## pseudocode

```c
void __stdcall RxFinalizeFcbTable(PRX_FCB_TABLE FcbTable)
{
  unsigned __int64 v1; // rdx
  struct _LIST_ENTRY *Blink; // rax
  unsigned __int64 Flink; // r9
  int v5; // r8d
  char v6; // al
  __int64 i; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax

  v1 = (unsigned __int64)&FcbTable->HashBuckets[1];
  Blink = FcbTable->HashBuckets[1].Blink;
  Flink = (unsigned __int64)FcbTable->HashBuckets[1].Flink;
  if ( ((unsigned __int8)Blink & 1) != 0 )
  {
    if ( !Flink )
      goto LABEL_3;
    Flink ^= v1;
  }
  v5 = (unsigned __int8)Blink & 1;
  while ( Flink )
  {
    while ( 1 )
    {
      while ( *(_QWORD *)Flink )
      {
        v10 = (_QWORD *)Flink;
        v11 = Flink ^ *(_QWORD *)Flink;
        Flink = *(_QWORD *)Flink;
        if ( v5 )
          Flink = v11;
        *v10 = 0;
      }
      v12 = *(_QWORD *)(Flink + 8);
      if ( !v12 )
        break;
      *(_QWORD *)(Flink + 8) = 0;
      v13 = Flink ^ v12;
      Flink = v12;
      if ( v5 )
        Flink = v13;
    }
    v9 = *(_QWORD *)(Flink + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v5 && v9 )
      Flink ^= v9;
    else
      Flink = *(_QWORD *)(Flink + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  }
LABEL_3:
  v6 = (char)FcbTable->HashBuckets[1].Blink;
  *(_QWORD *)v1 = 0;
  FcbTable->HashBuckets[1].Blink = 0;
  if ( (v6 & 1) != 0 )
    LOBYTE(FcbTable->HashBuckets[1].Blink) = 1;
  if ( FcbTable->HashBuckets[2].Flink )
  {
    for ( i = 0; i != 64; ++i )
    {
      v8 = *((_QWORD *)&FcbTable->HashBuckets[2].Flink->Flink + i);
      if ( (v8 & 1) != 0 )
        ExFreePoolWithTag((PVOID)(v8 & 0xFFFFFFFFFFFFFFFEuLL), 0);
    }
    ExFreePoolWithTag(FcbTable->HashBuckets[2].Flink, 0);
    FcbTable->HashBuckets[2].Flink = 0;
  }
  ExDeleteResourceLite((PERESOURCE)&FcbTable->TableLock.ActiveCount);
}

```

## disassembly

```asm
0x140076860  mov     [rsp+arg_10], rsi
0x140076865  push    rdi
0x140076866  sub     rsp, 20h
0x14007686a  lea     rdx, [rcx+98h]
0x140076871  xor     esi, esi
0x140076873  mov     rax, [rdx+8]
0x140076877  mov     rdi, rcx
0x14007687a  mov     r9, [rdx]
0x14007687d  test    al, 1
0x14007687f  jnz     loc_140076920
0x140076885  movzx   r8d, al
0x140076889  and     r8d, 1
0x14007688d  test    r9, r9
0x140076890  jnz     loc_140076948
0x140076896  movzx   eax, byte ptr [rdi+0A0h]
0x14007689d  mov     [rdx], rsi
0x1400768a0  mov     [rdi+0A0h], rsi
0x1400768a7  bt      eax, 0
0x1400768ab  jb      loc_140076979
0x1400768b1  cmp     [rdi+0A8h], rsi
0x1400768b8  jnz     short loc_1400768D6
0x1400768ba  lea     rcx, [rdi+30h]; Resource
0x1400768be  call    cs:__imp_ExDeleteResourceLite
0x1400768c5  nop     dword ptr [rax+rax+00h]
0x1400768ca  mov     rsi, [rsp+28h+arg_10]
0x1400768cf  add     rsp, 20h
0x1400768d3  pop     rdi
0x1400768d4  retn
0x1400768d6  mov     [rsp+28h+arg_8], rbx
0x1400768db  mov     rbx, rsi
0x1400768de  xchg    ax, ax
0x1400768e0  mov     rax, [rdi+0A8h]
0x1400768e7  mov     rcx, [rax+rbx*8]
0x1400768eb  test    cl, 1
0x1400768ee  jnz     loc_140076985
0x1400768f4  inc     rbx
0x1400768f7  cmp     rbx, 40h ; '@'
0x1400768fb  jnz     short loc_1400768E0
0x1400768fd  mov     rcx, [rdi+0A8h]; P
0x140076904  xor     edx, edx; Tag
0x140076906  mov     rbx, [rsp+28h+arg_8]
0x14007690b  call    cs:__imp_ExFreePoolWithTag
0x140076912  nop     dword ptr [rax+rax+00h]
0x140076917  mov     [rdi+0A8h], rsi
0x14007691e  jmp     short loc_1400768BA
0x140076920  test    r9, r9
0x140076923  jz      loc_140076896
0x140076929  xor     r9, rdx
0x14007692c  jmp     loc_140076885
0x140076931  mov     rax, [r9+10h]
0x140076935  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076939  test    r8d, r8d
0x14007693c  jz      short loc_140076943
0x14007693e  test    rax, rax
0x140076941  jnz     short loc_14007696C
0x140076943  mov     r9, rax
0x140076946  jmp     short loc_14007696F
0x140076948  mov     r10, [r9]
0x14007694b  test    r10, r10
0x14007694e  jz      loc_14007FA34
0x140076954  mov     rcx, r9
0x140076957  mov     rax, r10
0x14007695a  xor     rax, r9
0x14007695d  mov     r9, r10
0x140076960  test    r8d, r8d
0x140076963  cmovnz  r9, rax
0x140076967  mov     [rcx], rsi
0x14007696a  jmp     short loc_140076948
0x14007696c  xor     r9, rax
0x14007696f  test    r9, r9
0x140076972  jnz     short loc_140076948
0x140076974  jmp     loc_140076896
0x140076979  mov     byte ptr [rdi+0A0h], 1
0x140076980  jmp     loc_1400768B1
0x140076985  and     rcx, 0FFFFFFFFFFFFFFFEh; P
0x140076989  xor     edx, edx; Tag
0x14007698b  call    cs:__imp_ExFreePoolWithTag
0x140076992  nop     dword ptr [rax+rax+00h]
0x140076997  jmp     loc_1400768F4
0x14007fa34  mov     rcx, [r9+8]
0x14007fa38  lea     r10, [r9+8]
0x14007fa3c  test    rcx, rcx
0x14007fa3f  jz      loc_140076931
0x14007fa45  mov     rax, rcx
0x14007fa48  mov     [r10], rsi
0x14007fa4b  xor     rax, r9
0x14007fa4e  mov     r9, rcx
0x14007fa51  test    r8d, r8d
0x14007fa54  cmovnz  r9, rax
0x14007fa58  jmp     loc_140076948
```
