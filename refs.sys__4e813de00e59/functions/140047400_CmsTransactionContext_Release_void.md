# CmsTransactionContext::Release(void)

- ea: `0x140047400`
- end: `0x140047574`
- name: `?Release@CmsTransactionContext@@QEAAXXZ`
- size: `372`
- prototype: `void __fastcall(CmsTransactionContext *__hidden this)`
- caller_count: `41`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008ed4`
- `0x1400206c0`
- `0x14002ff00`
- `0x140031904`
- `0x140046200`
- `0x1400462e0`
- `0x140046508`
- `0x1400465e0`
- `0x1400568e0`
- `0x14005af00`
- `0x140077610`
- `0x1400a8560`
- `0x1400a8c00`
- `0x1400aa230`
- `0x1400b48d4`
- `0x1400b4a7c`
- `0x1400b5154`
- `0x1400c01c0`
- `0x1400d5ae0`
- `0x1400d8664`
- `0x14011dae0`
- `0x14011db30`
- `0x14011dd40`
- `0x140126a70`
- `0x14012b35c`
- `0x14012ced4`
- `0x14012ec7c`
- `0x14012f080`
- `0x1401411f4`
- `0x1401414f4`
- `0x140144320`
- `0x140146bcc`
- `0x140154378`
- `0x140154420`
- `0x140154eec`
- `0x14015cf70`
- `0x140167e40`
- `0x1401738fc`
- `0x140175290`
- `0x140175840`
- `0x140177bd0`

## callees

- `0x140047400`
- `0x140047730`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140047505`
- `ntoskrnl!KeSetEvent` at `0x140047505`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047451`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047451`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004746e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004746e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fcedd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fcedd`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004751a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004751a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047563`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047563`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140047534`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140047534`

## pseudocode

```c
void __fastcall CmsTransactionContext::Release(CmsTransactionContext *this)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rbx
  struct _SLIST_ENTRY *v5; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  unsigned int i; // ecx
  __int64 v8; // rbx
  __int64 v9; // rcx
  signed __int32 v10; // ett
  __int64 v11; // rcx

  v2 = *((_QWORD *)this + 1);
  v3 = *(_QWORD *)this & 0x10000000LL;
  CmsTransactionContext::~CmsTransactionContext(this);
  if ( !v3 )
  {
    v4 = *((_QWORD *)this - 2);
    v5 = (struct _SLIST_ENTRY *)((char *)this - 16);
    if ( v4 )
    {
      if ( *(_BYTE *)(v4 + 8) )
      {
        v6 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 + 64);
        if ( *(_BYTE *)(v4 + 9) )
          ExFreeToNPagedLookasideList(v6, v5);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v6, v5);
        return;
      }
      v11 = *(_QWORD *)(v4 + 88);
      if ( (int)v11 < *(_DWORD *)(v4 + 80) || SHIDWORD(v11) >= (int)v11 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v4 + 64), v5);
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 88));
        return;
      }
    }
    ExFreePoolWithTag(v5, 0);
    return;
  }
  if ( *(_DWORD *)(v2 + 172) )
  {
    for ( i = 0; i < *(_DWORD *)(v2 + 168); ++i )
    {
      v8 = 16LL * i;
      if ( *(CmsTransactionContext **)(v8 + *(_QWORD *)(v2 + 160)) == this )
      {
        if ( *(_BYTE *)(v2 + 216) )
          ExAcquirePushLockExclusiveEx(v2 + 208, 0);
        v9 = *(_QWORD *)(v2 + 160);
        _m_prefetchw((const void *)(v8 + v9 + 8));
        do
          v10 = *(_DWORD *)(v8 + v9 + 8);
        while ( v10 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + v9 + 8), v10 & 0xFFFFFFFE, v10) );
        _InterlockedDecrement((volatile signed __int32 *)(v2 + 172));
        if ( *(_BYTE *)(v2 + 216) )
        {
          KeSetEvent((PRKEVENT)(v2 + 184), 0, 0);
          ExReleasePushLockEx(v2 + 208, 0);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x140047400  mov     [rsp+arg_8], rbx
0x140047405  mov     [rsp+arg_10], rsi
0x14004740a  push    rdi
0x14004740b  sub     rsp, 20h
0x14004740f  mov     rbx, [rcx]
0x140047412  mov     rdi, rcx
0x140047415  mov     rsi, [rcx+8]
0x140047419  and     ebx, 10000000h
0x14004741f  call    ??1CmsTransactionContext@@AEAA@XZ; CmsTransactionContext::~CmsTransactionContext(void)
0x140047424  test    rbx, rbx
0x140047427  jnz     short loc_14004748B
0x140047429  mov     rbx, [rdi-10h]
0x14004742d  add     rdi, 0FFFFFFFFFFFFFFF0h
0x140047431  test    rbx, rbx
0x140047434  jz      loc_14004755E
0x14004743a  cmp     byte ptr [rbx+8], 0
0x14004743e  jz      loc_140047542
0x140047444  cmp     byte ptr [rbx+9], 0
0x140047448  lea     rcx, [rbx+40h]; Lookaside
0x14004744c  mov     rdx, rdi; Entry
0x14004744f  jz      short loc_14004746E
0x140047451  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047458  nop     dword ptr [rax+rax+00h]
0x14004745d  mov     rbx, [rsp+28h+arg_8]
0x140047462  mov     rsi, [rsp+28h+arg_10]
0x140047467  add     rsp, 20h
0x14004746b  pop     rdi
0x14004746c  retn
0x14004746e  call    cs:__imp_ExFreeToPagedLookasideList
0x140047475  nop     dword ptr [rax+rax+00h]
0x14004747a  mov     rbx, [rsp+28h+arg_8]
0x14004747f  mov     rsi, [rsp+28h+arg_10]
0x140047484  add     rsp, 20h
0x140047488  pop     rdi
0x140047489  retn
0x14004748b  mov     eax, [rsi+0ACh]
0x140047491  test    eax, eax
0x140047493  jz      short loc_14004745D
0x140047495  mov     edx, [rsi+0A8h]
0x14004749b  xor     ecx, ecx
0x14004749d  nop     dword ptr [rax]
0x1400474a0  cmp     ecx, edx
0x1400474a2  jnb     short loc_14004745D
0x1400474a4  mov     rax, [rsi+0A0h]
0x1400474ab  mov     ebx, ecx
0x1400474ad  shl     rbx, 4
0x1400474b1  cmp     [rbx+rax], rdi
0x1400474b5  jz      short loc_1400474BB
0x1400474b7  inc     ecx
0x1400474b9  jmp     short loc_1400474A0
0x1400474bb  cmp     byte ptr [rsi+0D8h], 0
0x1400474c2  jnz     short loc_14004752B
0x1400474c4  mov     rcx, [rsi+0A0h]
0x1400474cb  prefetchw byte ptr [rbx+rcx+8]
0x1400474d0  mov     eax, [rbx+rcx+8]
0x1400474d4  mov     edx, eax
0x1400474d6  and     edx, 0FFFFFFFEh
0x1400474d9  nop
0x1400474da  lock cmpxchg [rbx+rcx+8], edx
0x1400474e0  nop
0x1400474e1  jnz     short loc_1400474D0
0x1400474e3  nop
0x1400474e4  lock dec dword ptr [rsi+0ACh]
0x1400474eb  nop
0x1400474ec  cmp     byte ptr [rsi+0D8h], 0
0x1400474f3  jz      loc_14004745D
0x1400474f9  lea     rcx, [rsi+0B8h]; Event
0x140047500  xor     r8d, r8d; Wait
0x140047503  xor     edx, edx; Increment
0x140047505  call    cs:__imp_KeSetEvent
0x14004750c  nop     dword ptr [rax+rax+00h]
0x140047511  lea     rcx, [rsi+0D0h]
0x140047518  xor     edx, edx
0x14004751a  call    cs:__imp_ExReleasePushLockEx
0x140047521  nop     dword ptr [rax+rax+00h]
0x140047526  jmp     loc_14004745D
0x14004752b  lea     rcx, [rsi+0D0h]
0x140047532  xor     edx, edx
0x140047534  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004753b  nop     dword ptr [rax+rax+00h]
0x140047540  jmp     short loc_1400474C4
0x140047542  mov     rcx, [rbx+58h]
0x140047546  cmp     ecx, [rbx+50h]
0x140047549  jl      loc_1401FCED6
0x14004754f  mov     rax, rcx
0x140047552  shr     rax, 20h
0x140047556  cmp     eax, ecx
0x140047558  jge     loc_1401FCED6
0x14004755e  xor     edx, edx; Tag
0x140047560  mov     rcx, rdi; P
0x140047563  call    cs:__imp_ExFreePoolWithTag
0x14004756a  nop     dword ptr [rax+rax+00h]
0x14004756f  jmp     loc_14004745D
0x1401fced6  lea     rcx, [rbx+40h]; ListHead
0x1401fceda  mov     rdx, rdi; ListEntry
0x1401fcedd  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fcee4  nop     dword ptr [rax+rax+00h]
0x1401fcee9  nop
0x1401fceea  lock inc dword ptr [rbx+58h]
0x1401fceee  nop
0x1401fceef  jmp     loc_14004745D
```
