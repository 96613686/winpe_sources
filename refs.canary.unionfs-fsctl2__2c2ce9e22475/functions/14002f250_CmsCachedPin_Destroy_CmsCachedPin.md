# CmsCachedPin::Destroy(CmsCachedPin *)

- ea: `0x14002f250`
- end: `0x14002f3d4`
- name: `?Destroy@CmsCachedPin@@SAXPEAV1@@Z`
- size: `388`
- prototype: `void __fastcall(struct CmsCachedPin *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14002f4b0`
- `0x14002fce0`

## callees

- `0x14002f250`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f2fd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f35d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f2fd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f35d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002f310`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002f347`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002f310`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002f347`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f170b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1729`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f170b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1729`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f394`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f394`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3c3`

## pseudocode

```c
void __fastcall CmsCachedPin::Destroy(struct CmsCachedPin *a1)
{
  int v2; // edi
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rbx
  struct _SLIST_ENTRY *v6; // r8
  struct _NPAGED_LOOKASIDE_LIST *v7; // rcx
  void *v8; // rdx
  struct _SLIST_ENTRY *v9; // r8
  __int64 v10; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx

  if ( !a1 )
    return;
  if ( (*((_DWORD *)a1 + 26) & 8) != 0 )
    *(_BYTE *)(*((_QWORD *)a1 + 17) + 135LL) = 0;
  v2 = *((_DWORD *)a1 + 26) & 8;
  if ( (*((_DWORD *)a1 + 26) & 0x10) != 0 )
    _InterlockedAdd64(&CmsCachedPin::GlobalCachedPinPageCount, -*((_DWORD *)a1 + 38));
  v3 = *((_QWORD *)a1 + 6);
  if ( v3 )
  {
    if ( (*((_DWORD *)a1 + 18) & 8) != 0 )
    {
      *(_BYTE *)(v3 - 2431) = 0;
      *((_DWORD *)a1 + 18) &= ~8u;
    }
    else
    {
      v9 = (struct _SLIST_ENTRY *)(v3 - 16);
      v10 = *(_QWORD *)(v3 - 16);
      if ( !v10 )
        goto LABEL_26;
      if ( *(_BYTE *)(v10 + 8) )
      {
        v11 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
        if ( *(_BYTE *)(v10 + 9) )
          ExFreeToNPagedLookasideList(v11, v9);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v11, v9);
        goto LABEL_9;
      }
      v12 = *(_QWORD *)(v10 + 88);
      if ( (int)v12 < *(_DWORD *)(v10 + 80) || SHIDWORD(v12) >= (int)v12 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), v9);
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
      }
      else
      {
LABEL_26:
        ExFreePoolWithTag(v9, 0);
      }
    }
LABEL_9:
    *((_QWORD *)a1 + 6) = 0;
    *((_DWORD *)a1 + 14) = 0;
  }
  if ( !v2 )
  {
    v4 = *((_QWORD *)a1 + 16);
    if ( v4 )
    {
      v5 = *(_QWORD *)(v4 - 16);
      v6 = (struct _SLIST_ENTRY *)(v4 - 16);
      if ( v5 )
      {
        if ( *(_BYTE *)(v5 + 8) )
        {
          v7 = (struct _NPAGED_LOOKASIDE_LIST *)(v5 + 64);
          v8 = (void *)(v4 - 16);
          if ( *(_BYTE *)(v5 + 9) )
            ExFreeToNPagedLookasideList(v7, v8);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v7, v8);
          return;
        }
        v13 = *(_QWORD *)(v5 + 88);
        if ( (int)v13 < *(_DWORD *)(v5 + 80) || SHIDWORD(v13) >= (int)v13 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v5 + 64), v6);
          _InterlockedIncrement((volatile signed __int32 *)(v5 + 88));
          return;
        }
      }
      ExFreePoolWithTag(v6, 0);
    }
  }
}

```

## disassembly

```asm
0x14002f250  test    rcx, rcx
0x14002f253  jz      locret_14002F30E
0x14002f259  push    rbx
0x14002f25a  sub     rsp, 20h
0x14002f25e  mov     eax, [rcx+68h]
0x14002f261  mov     rbx, rcx
0x14002f264  mov     [rsp+28h+arg_8], rdi
0x14002f269  test    al, 8
0x14002f26b  jz      short loc_14002F27B
0x14002f26d  mov     rax, [rcx+88h]
0x14002f274  mov     byte ptr [rax+87h], 0
0x14002f27b  mov     eax, [rcx+68h]
0x14002f27e  mov     edi, eax
0x14002f280  and     edi, 8
0x14002f283  test    al, 10h
0x14002f285  jz      short loc_14002F29C
0x14002f287  mov     eax, [rcx+98h]
0x14002f28d  nop
0x14002f28e  neg     eax
0x14002f290  movsxd  rcx, eax
0x14002f293  lock add cs:?GlobalCachedPinPageCount@CmsCachedPin@@2_JA, rcx; __int64 CmsCachedPin::GlobalCachedPinPageCount
0x14002f29b  nop
0x14002f29c  mov     rcx, [rbx+30h]
0x14002f2a0  test    rcx, rcx
0x14002f2a3  jz      short loc_14002F2C0
0x14002f2a5  mov     eax, [rbx+48h]
0x14002f2a8  test    al, 8
0x14002f2aa  jz      short loc_14002F323
0x14002f2ac  mov     byte ptr [rcx-97Fh], 0
0x14002f2b3  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x14002f2b7  xor     eax, eax
0x14002f2b9  mov     [rbx+30h], rax
0x14002f2bd  mov     [rbx+38h], eax
0x14002f2c0  test    edi, edi
0x14002f2c2  mov     rdi, [rsp+28h+arg_8]
0x14002f2c7  jnz     short loc_14002F309
0x14002f2c9  mov     rax, [rbx+80h]
0x14002f2d0  test    rax, rax
0x14002f2d3  jz      short loc_14002F309
0x14002f2d5  mov     rbx, [rax-10h]
0x14002f2d9  lea     r8, [rax-10h]
0x14002f2dd  test    rbx, rbx
0x14002f2e0  jz      loc_14002F3BE
0x14002f2e6  cmp     byte ptr [rbx+8], 0
0x14002f2ea  jz      loc_14002F3A2
0x14002f2f0  cmp     byte ptr [rbx+9], 0
0x14002f2f4  lea     rcx, [rbx+40h]; Lookaside
0x14002f2f8  mov     rdx, r8; Entry
0x14002f2fb  jz      short loc_14002F310
0x14002f2fd  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002f304  nop     dword ptr [rax+rax+00h]
0x14002f309  add     rsp, 20h
0x14002f30d  pop     rbx
0x14002f30e  retn
0x14002f310  call    cs:__imp_ExFreeToPagedLookasideList
0x14002f317  nop     dword ptr [rax+rax+00h]
0x14002f31c  add     rsp, 20h
0x14002f320  pop     rbx
0x14002f321  retn
0x14002f323  lea     r8, [rcx-10h]
0x14002f327  mov     [rsp+28h+arg_0], rsi
0x14002f32c  mov     rsi, [r8]
0x14002f32f  test    rsi, rsi
0x14002f332  jz      short loc_14002F38F
0x14002f334  cmp     byte ptr [rsi+8], 0
0x14002f338  jz      short loc_14002F373
0x14002f33a  cmp     byte ptr [rsi+9], 0
0x14002f33e  lea     rcx, [rsi+40h]; Lookaside
0x14002f342  mov     rdx, r8; Entry
0x14002f345  jnz     short loc_14002F35D
0x14002f347  call    cs:__imp_ExFreeToPagedLookasideList
0x14002f34e  nop     dword ptr [rax+rax+00h]
0x14002f353  mov     rsi, [rsp+28h+arg_0]
0x14002f358  jmp     loc_14002F2B7
0x14002f35d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002f364  nop     dword ptr [rax+rax+00h]
0x14002f369  mov     rsi, [rsp+28h+arg_0]
0x14002f36e  jmp     loc_14002F2B7
0x14002f373  mov     rcx, [rsi+58h]
0x14002f377  cmp     ecx, [rsi+50h]
0x14002f37a  jl      loc_1401F1704
0x14002f380  mov     rax, rcx
0x14002f383  shr     rax, 20h
0x14002f387  cmp     eax, ecx
0x14002f389  jge     loc_1401F1704
0x14002f38f  xor     edx, edx; Tag
0x14002f391  mov     rcx, r8; P
0x14002f394  call    cs:__imp_ExFreePoolWithTag
0x14002f39b  nop     dword ptr [rax+rax+00h]
0x14002f3a0  jmp     short loc_14002F353
0x14002f3a2  mov     rcx, [rbx+58h]
0x14002f3a6  cmp     ecx, [rbx+50h]
0x14002f3a9  jl      loc_1401F1722
0x14002f3af  mov     rax, rcx
0x14002f3b2  shr     rax, 20h
0x14002f3b6  cmp     eax, ecx
0x14002f3b8  jge     loc_1401F1722
0x14002f3be  xor     edx, edx; Tag
0x14002f3c0  mov     rcx, r8; P
0x14002f3c3  call    cs:__imp_ExFreePoolWithTag
0x14002f3ca  nop     dword ptr [rax+rax+00h]
0x14002f3cf  jmp     loc_14002F309
0x1401f1704  lea     rcx, [rsi+40h]; ListHead
0x1401f1708  mov     rdx, r8; ListEntry
0x1401f170b  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f1712  nop     dword ptr [rax+rax+00h]
0x1401f1717  nop
0x1401f1718  lock inc dword ptr [rsi+58h]
0x1401f171c  nop
0x1401f171d  jmp     loc_14002F353
0x1401f1722  lea     rcx, [rbx+40h]; ListHead
0x1401f1726  mov     rdx, r8; ListEntry
0x1401f1729  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f1730  nop     dword ptr [rax+rax+00h]
0x1401f1735  nop
0x1401f1736  lock inc dword ptr [rbx+58h]
0x1401f173a  nop
0x1401f173b  jmp     loc_14002F309
```
