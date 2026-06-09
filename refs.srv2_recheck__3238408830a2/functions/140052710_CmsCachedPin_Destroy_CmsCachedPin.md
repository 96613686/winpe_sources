# CmsCachedPin::Destroy(CmsCachedPin *)

- ea: `0x140052710`
- end: `0x140052894`
- name: `?Destroy@CmsCachedPin@@SAXPEAV1@@Z`
- size: `388`
- prototype: `void __fastcall(struct CmsCachedPin *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140051580`
- `0x140051e70`
- `0x140052030`

## callees

- `0x140052710`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400527bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005281d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400527bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005281d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400527d0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140052807`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400527d0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140052807`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd629`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd647`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd629`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd647`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052854`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052883`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052854`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052883`

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
0x140052710  test    rcx, rcx
0x140052713  jz      locret_1400527CE
0x140052719  push    rbx
0x14005271a  sub     rsp, 20h
0x14005271e  mov     eax, [rcx+68h]
0x140052721  mov     rbx, rcx
0x140052724  mov     [rsp+28h+arg_8], rdi
0x140052729  test    al, 8
0x14005272b  jz      short loc_14005273B
0x14005272d  mov     rax, [rcx+88h]
0x140052734  mov     byte ptr [rax+87h], 0
0x14005273b  mov     eax, [rcx+68h]
0x14005273e  mov     edi, eax
0x140052740  and     edi, 8
0x140052743  test    al, 10h
0x140052745  jz      short loc_14005275C
0x140052747  mov     eax, [rcx+98h]
0x14005274d  nop
0x14005274e  neg     eax
0x140052750  movsxd  rcx, eax
0x140052753  lock add cs:?GlobalCachedPinPageCount@CmsCachedPin@@2_JA, rcx; __int64 CmsCachedPin::GlobalCachedPinPageCount
0x14005275b  nop
0x14005275c  mov     rcx, [rbx+30h]
0x140052760  test    rcx, rcx
0x140052763  jz      short loc_140052780
0x140052765  mov     eax, [rbx+48h]
0x140052768  test    al, 8
0x14005276a  jz      short loc_1400527E3
0x14005276c  mov     byte ptr [rcx-97Fh], 0
0x140052773  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x140052777  xor     eax, eax
0x140052779  mov     [rbx+30h], rax
0x14005277d  mov     [rbx+38h], eax
0x140052780  test    edi, edi
0x140052782  mov     rdi, [rsp+28h+arg_8]
0x140052787  jnz     short loc_1400527C9
0x140052789  mov     rax, [rbx+80h]
0x140052790  test    rax, rax
0x140052793  jz      short loc_1400527C9
0x140052795  mov     rbx, [rax-10h]
0x140052799  lea     r8, [rax-10h]
0x14005279d  test    rbx, rbx
0x1400527a0  jz      loc_14005287E
0x1400527a6  cmp     byte ptr [rbx+8], 0
0x1400527aa  jz      loc_140052862
0x1400527b0  cmp     byte ptr [rbx+9], 0
0x1400527b4  lea     rcx, [rbx+40h]; Lookaside
0x1400527b8  mov     rdx, r8; Entry
0x1400527bb  jz      short loc_1400527D0
0x1400527bd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400527c4  nop     dword ptr [rax+rax+00h]
0x1400527c9  add     rsp, 20h
0x1400527cd  pop     rbx
0x1400527ce  retn
0x1400527d0  call    cs:__imp_ExFreeToPagedLookasideList
0x1400527d7  nop     dword ptr [rax+rax+00h]
0x1400527dc  add     rsp, 20h
0x1400527e0  pop     rbx
0x1400527e1  retn
0x1400527e3  lea     r8, [rcx-10h]
0x1400527e7  mov     [rsp+28h+arg_0], rsi
0x1400527ec  mov     rsi, [r8]
0x1400527ef  test    rsi, rsi
0x1400527f2  jz      short loc_14005284F
0x1400527f4  cmp     byte ptr [rsi+8], 0
0x1400527f8  jz      short loc_140052833
0x1400527fa  cmp     byte ptr [rsi+9], 0
0x1400527fe  lea     rcx, [rsi+40h]; Lookaside
0x140052802  mov     rdx, r8; Entry
0x140052805  jnz     short loc_14005281D
0x140052807  call    cs:__imp_ExFreeToPagedLookasideList
0x14005280e  nop     dword ptr [rax+rax+00h]
0x140052813  mov     rsi, [rsp+28h+arg_0]
0x140052818  jmp     loc_140052777
0x14005281d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140052824  nop     dword ptr [rax+rax+00h]
0x140052829  mov     rsi, [rsp+28h+arg_0]
0x14005282e  jmp     loc_140052777
0x140052833  mov     rcx, [rsi+58h]
0x140052837  cmp     ecx, [rsi+50h]
0x14005283a  jl      loc_1401FD622
0x140052840  mov     rax, rcx
0x140052843  shr     rax, 20h
0x140052847  cmp     eax, ecx
0x140052849  jge     loc_1401FD622
0x14005284f  xor     edx, edx; Tag
0x140052851  mov     rcx, r8; P
0x140052854  call    cs:__imp_ExFreePoolWithTag
0x14005285b  nop     dword ptr [rax+rax+00h]
0x140052860  jmp     short loc_140052813
0x140052862  mov     rcx, [rbx+58h]
0x140052866  cmp     ecx, [rbx+50h]
0x140052869  jl      loc_1401FD640
0x14005286f  mov     rax, rcx
0x140052872  shr     rax, 20h
0x140052876  cmp     eax, ecx
0x140052878  jge     loc_1401FD640
0x14005287e  xor     edx, edx; Tag
0x140052880  mov     rcx, r8; P
0x140052883  call    cs:__imp_ExFreePoolWithTag
0x14005288a  nop     dword ptr [rax+rax+00h]
0x14005288f  jmp     loc_1400527C9
0x1401fd622  lea     rcx, [rsi+40h]; ListHead
0x1401fd626  mov     rdx, r8; ListEntry
0x1401fd629  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fd630  nop     dword ptr [rax+rax+00h]
0x1401fd635  nop
0x1401fd636  lock inc dword ptr [rsi+58h]
0x1401fd63a  nop
0x1401fd63b  jmp     loc_140052813
0x1401fd640  lea     rcx, [rbx+40h]; ListHead
0x1401fd644  mov     rdx, r8; ListEntry
0x1401fd647  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401fd64e  nop     dword ptr [rax+rax+00h]
0x1401fd653  nop
0x1401fd654  lock inc dword ptr [rbx+58h]
0x1401fd658  nop
0x1401fd659  jmp     loc_1400527C9
```
