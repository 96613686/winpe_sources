# DbTableAccess<SharingTargetTableAdapter>::Delete(SharingTargetTableAdapter *)

- ea: `0x1800165c0`
- end: `0x180016695`
- name: `?Delete@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJPEAVSharingTargetTableAdapter@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001669c`
- `0x180017c90`

## callees

- `0x180003478`
- `0x18000be3c`
- `0x180014770`
- `0x1800165c0`

## pseudocode

```c
__int64 __fastcall DbTableAccess<SharingTargetTableAdapter>::Delete(__int64 a1, _OWORD *a2)
{
  unsigned int v4; // edi
  _OWORD *v5; // rax
  void *v6; // rdi
  PVOID *v7; // rax
  unsigned int v8; // r9d
  PVOID *v9; // rbx
  int i; // esi

  if ( !a2 )
    return (unsigned int)-2147024809;
  v5 = operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  *v5 = *a2;
  v7 = (PVOID *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v7;
  if ( !v7 )
  {
    Common::GlobalHeap::Free(v6);
    return (unsigned int)-2147024882;
  }
  *v7 = v6;
  *((_DWORD *)v7 + 2) = 16;
  *((_DWORD *)v7 + 3) = 1;
  v4 = DbTable::Delete(*(DbTable **)(a1 + 8), (struct _jetSeekCriteria *)v7, 1u, v8);
  for ( i = 0; i < 1; ++i )
    Common::GlobalHeap::Free(v9[2 * (unsigned int)i]);
  Common::GlobalHeap::Free(v9);
  return v4;
}

```

## disassembly

```asm
0x1800165c0  push    rbx
0x1800165c2  push    rbp
0x1800165c3  push    rsi
0x1800165c4  push    rdi
0x1800165c5  push    r14
0x1800165c7  sub     rsp, 20h
0x1800165cb  xor     ebx, ebx
0x1800165cd  xor     r14d, r14d
0x1800165d0  mov     rsi, rdx
0x1800165d3  mov     rbp, rcx
0x1800165d6  test    rdx, rdx
0x1800165d9  jnz     short loc_1800165E2
0x1800165db  mov     edi, 80070057h
0x1800165e0  jmp     short loc_18001665C
0x1800165e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800165e9  mov     ecx, 10h; unsigned __int64
0x1800165ee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800165f3  mov     rdi, rax
0x1800165f6  test    rax, rax
0x1800165f9  jz      short loc_180016657
0x1800165fb  movups  xmm0, xmmword ptr [rsi]
0x1800165fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016605  mov     ecx, 10h; unsigned __int64
0x18001660a  movdqu  xmmword ptr [rax], xmm0
0x18001660e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016613  mov     rbx, rax
0x180016616  test    rax, rax
0x180016619  jz      short loc_18001664D
0x18001661b  mov     [rax], rdi
0x18001661e  mov     r8d, 1; unsigned int
0x180016624  mov     dword ptr [rax+8], 10h
0x18001662b  mov     rdx, rax; struct _jetSeekCriteria *
0x18001662e  mov     dword ptr [rax+0Ch], 1
0x180016635  mov     rcx, [rbp+8]; this
0x180016639  call    ?Delete@DbTable@@QEAAJPEAU_jetSeekCriteria@@KK@Z; DbTable::Delete(_jetSeekCriteria *,ulong,ulong)
0x18001663e  mov     edi, eax
0x180016640  xor     esi, esi
0x180016642  mov     r14d, 1
0x180016648  mov     rbp, rbx
0x18001664b  jmp     short loc_18001666A
0x18001664d  mov     rcx, rdi; P
0x180016650  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180016655  xor     ebx, ebx
0x180016657  mov     edi, 8007000Eh
0x18001665c  xor     ebp, ebp
0x18001665e  test    rbx, rbx
0x180016661  jz      short loc_180016688
0x180016663  xor     esi, esi
0x180016665  test    r14d, r14d
0x180016668  jz      short loc_180016680
0x18001666a  mov     ecx, esi
0x18001666c  add     rcx, rcx
0x18001666f  mov     rcx, [rbp+rcx*8+0]; P
0x180016674  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180016679  inc     esi
0x18001667b  cmp     esi, r14d
0x18001667e  jl      short loc_18001666A
0x180016680  mov     rcx, rbx; P
0x180016683  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180016688  mov     eax, edi
0x18001668a  add     rsp, 20h
0x18001668e  pop     r14
0x180016690  pop     rdi
0x180016691  pop     rsi
0x180016692  pop     rbp
0x180016693  pop     rbx
0x180016694  retn
```
