# FreeTracker

- ea: `0x14000b810`
- end: `0x14000ba37`
- name: `FreeTracker`
- size: `551`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: ``

## callers

- `0x140002cb0`
- `0x14000699c`
- `0x140007a08`
- `0x140009844`
- `0x140009e00`
- `0x140009e1c`
- `0x140009ee0`
- `0x14000a7b0`
- `0x14000ba70`
- `0x14000c570`
- `0x14000cca0`
- `0x14000d310`
- `0x14000d594`
- `0x14000e408`
- `0x14000ebe0`
- `0x14000efd4`
- `0x1400182a0`
- `0x140018ea0`
- `0x140019a10`
- `0x14001b7d0`
- `0x14001d580`
- `0x14001e8f4`
- `0x14001f8d0`
- `0x140020470`
- `0x140020900`
- `0x140021280`
- `0x140022d04`
- `0x140025260`
- `0x1400269a8`
- `0x140029420`
- `0x140029d28`
- `0x14002a8c0`
- `0x14002af10`
- `0x140047f20`
- `0x1400485e8`
- `0x140050860`
- `0x140052100`

## callees

- `0x14000b810`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b82b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b82b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b957`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b957`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b872`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b997`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b9d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b9f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b872`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b997`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b9d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b9f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba26`

## pseudocode

```c
void __fastcall FreeTracker(__int64 a1, char a2)
{
  KIRQL v4; // di
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 *v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  _QWORD *v14; // rax
  PVOID v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rcx

  v4 = KeAcquireSpinLockRaiseToDpc(&Lock);
  if ( a1 && *(_DWORD *)(a1 + 16) == 1801548372 )
  {
    if ( (a2 & 2) != 0 )
    {
      v17 = *(_QWORD *)a1;
      if ( *(_QWORD *)(*(_QWORD *)a1 + 8LL) != a1 )
        goto LABEL_24;
      v18 = *(_QWORD **)(a1 + 8);
      if ( *v18 != a1 )
        goto LABEL_24;
      *v18 = v17;
      *(_QWORD *)(v17 + 8) = v18;
    }
    if ( (a2 & 1) != 0 )
    {
      v5 = *(void **)(a1 + 64);
      if ( v5 )
      {
        ExFreePoolWithTag(v5, 0);
        *(_QWORD *)(a1 + 64) = 0;
      }
      v6 = *(void **)(a1 + 216);
      if ( v6 )
      {
        ExFreePoolWithTag(v6, 0);
        *(_QWORD *)(a1 + 216) = 0;
      }
      v7 = *(void **)(a1 + 272);
      if ( v7 )
      {
        ExFreePoolWithTag(v7, 0);
        *(_QWORD *)(a1 + 272) = 0;
      }
    }
    v8 = *(void **)(a1 + 192);
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      *(_QWORD *)(a1 + 192) = 0;
    }
    v9 = *(void **)(a1 + 232);
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    *(_QWORD *)(a1 + 256) = a1 + 248;
    *(_QWORD *)(a1 + 248) = a1 + 248;
    v10 = (__int64 *)qword_140039478;
    if ( *(PVOID **)qword_140039478 == &qword_140039470 )
    {
      *(_QWORD *)a1 = &qword_140039470;
      *(_QWORD *)(a1 + 8) = v10;
      *v10 = a1;
      qword_140039478 = a1;
      v11 = *(int *)(a1 + 432);
      *(_DWORD *)(a1 + 16) = 845247060;
      v12 = (_QWORD *)(a1 + 416);
      --TrackTrackers[v11];
      v13 = *v12;
      if ( *(_QWORD **)(*v12 + 8LL) == v12 )
      {
        v14 = (_QWORD *)v12[1];
        if ( (_QWORD *)*v14 == v12 )
        {
          *v14 = v13;
          *(_QWORD *)(v13 + 8) = v14;
          if ( (unsigned int)NumFreeTrackers <= 0x32 )
          {
            ++NumFreeTrackers;
            goto LABEL_20;
          }
          v15 = qword_140039470;
          if ( *((PVOID **)qword_140039470 + 1) == &qword_140039470 )
          {
            v16 = *(_QWORD *)qword_140039470;
            if ( *(PVOID *)(*(_QWORD *)qword_140039470 + 8LL) == qword_140039470 )
            {
              qword_140039470 = *(PVOID *)qword_140039470;
              *(_QWORD *)(v16 + 8) = &qword_140039470;
              ExFreePoolWithTag(v15, 0);
              --word_14003950A;
              goto LABEL_20;
            }
          }
        }
      }
    }
LABEL_24:
    __fastfail(3u);
  }
LABEL_20:
  KeReleaseSpinLock(&Lock, v4);
}

```

## disassembly

```asm
0x14000b810  mov     [rsp+arg_8], rbx
0x14000b815  mov     [rsp+arg_10], rsi
0x14000b81a  push    rdi
0x14000b81b  sub     rsp, 20h
0x14000b81f  mov     rbx, rcx
0x14000b822  mov     esi, edx
0x14000b824  lea     rcx, Lock; SpinLock
0x14000b82b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b832  nop     dword ptr [rax+rax+00h]
0x14000b837  movzx   edi, al
0x14000b83a  test    rbx, rbx
0x14000b83d  jz      loc_14000B94C
0x14000b843  cmp     dword ptr [rbx+10h], 6B617254h
0x14000b84a  jnz     loc_14000B94C
0x14000b850  test    sil, 2
0x14000b854  jnz     loc_14000B9B8
0x14000b85a  mov     [rsp+28h+arg_0], rbp
0x14000b85f  xor     ebp, ebp
0x14000b861  test    sil, 1
0x14000b865  jz      short loc_14000B8A2
0x14000b867  mov     rcx, [rbx+40h]; P
0x14000b86b  test    rcx, rcx
0x14000b86e  jz      short loc_14000B882
0x14000b870  xor     edx, edx; Tag
0x14000b872  call    cs:__imp_ExFreePoolWithTag
0x14000b879  nop     dword ptr [rax+rax+00h]
0x14000b87e  mov     [rbx+40h], rbp
0x14000b882  mov     rcx, [rbx+0D8h]; P
0x14000b889  test    rcx, rcx
0x14000b88c  jnz     loc_14000B9D6
0x14000b892  mov     rcx, [rbx+110h]; P
0x14000b899  test    rcx, rcx
0x14000b89c  jnz     loc_14000B9F0
0x14000b8a2  mov     rcx, [rbx+0C0h]; P
0x14000b8a9  test    rcx, rcx
0x14000b8ac  jnz     loc_14000BA0A
0x14000b8b2  mov     rcx, [rbx+0E8h]; P
0x14000b8b9  mov     rbp, [rsp+28h+arg_0]
0x14000b8be  test    rcx, rcx
0x14000b8c1  jnz     loc_14000BA24
0x14000b8c7  lea     rax, [rbx+0F8h]
0x14000b8ce  mov     [rax+8], rax
0x14000b8d2  lea     rdx, qword_140039470
0x14000b8d9  mov     [rax], rax
0x14000b8dc  mov     rax, cs:qword_140039478
0x14000b8e3  cmp     [rax], rdx
0x14000b8e6  jnz     loc_14000B9B1
0x14000b8ec  mov     [rbx], rdx
0x14000b8ef  lea     rcx, TrackTrackers
0x14000b8f6  mov     [rbx+8], rax
0x14000b8fa  mov     [rax], rbx
0x14000b8fd  mov     cs:qword_140039478, rbx
0x14000b904  movsxd  rax, dword ptr [rbx+1B0h]
0x14000b90b  mov     dword ptr [rbx+10h], 32617254h
0x14000b912  add     rbx, 1A0h
0x14000b919  dec     dword ptr [rcx+rax*4]
0x14000b91c  mov     rcx, [rbx]
0x14000b91f  cmp     [rcx+8], rbx
0x14000b923  jnz     loc_14000B9B1
0x14000b929  mov     rax, [rbx+8]
0x14000b92d  cmp     [rax], rbx
0x14000b930  jnz     short loc_14000B9B1
0x14000b932  mov     [rax], rcx
0x14000b935  mov     [rcx+8], rax
0x14000b939  mov     eax, cs:NumFreeTrackers
0x14000b93f  cmp     eax, 32h ; '2'
0x14000b942  ja      short loc_14000B974
0x14000b944  inc     eax
0x14000b946  mov     cs:NumFreeTrackers, eax
0x14000b94c  movzx   edx, dil; NewIrql
0x14000b950  lea     rcx, Lock; SpinLock
0x14000b957  call    cs:__imp_KeReleaseSpinLock
0x14000b95e  nop     dword ptr [rax+rax+00h]
0x14000b963  mov     rbx, [rsp+28h+arg_8]
0x14000b968  mov     rsi, [rsp+28h+arg_10]
0x14000b96d  add     rsp, 20h
0x14000b971  pop     rdi
0x14000b972  retn
0x14000b974  mov     rcx, cs:qword_140039470; P
0x14000b97b  cmp     [rcx+8], rdx
0x14000b97f  jnz     short loc_14000B9B1
0x14000b981  mov     rax, [rcx]
0x14000b984  cmp     [rax+8], rcx
0x14000b988  jnz     short loc_14000B9B1
0x14000b98a  mov     cs:qword_140039470, rax
0x14000b991  mov     [rax+8], rdx
0x14000b995  xor     edx, edx; Tag
0x14000b997  call    cs:__imp_ExFreePoolWithTag
0x14000b99e  nop     dword ptr [rax+rax+00h]
0x14000b9a3  mov     eax, 0FFFFh
0x14000b9a8  add     cs:word_14003950A, ax
0x14000b9af  jmp     short loc_14000B94C
0x14000b9b1  mov     ecx, 3
0x14000b9b6  int     29h; Win8: RtlFailFast(ecx)
0x14000b9b8  mov     rax, [rbx]
0x14000b9bb  cmp     [rax+8], rbx
0x14000b9bf  jnz     short loc_14000B9B1
0x14000b9c1  mov     rcx, [rbx+8]
0x14000b9c5  cmp     [rcx], rbx
0x14000b9c8  jnz     short loc_14000B9B1
0x14000b9ca  mov     [rcx], rax
0x14000b9cd  mov     [rax+8], rcx
0x14000b9d1  jmp     loc_14000B85A
0x14000b9d6  xor     edx, edx; Tag
0x14000b9d8  call    cs:__imp_ExFreePoolWithTag
0x14000b9df  nop     dword ptr [rax+rax+00h]
0x14000b9e4  mov     [rbx+0D8h], rbp
0x14000b9eb  jmp     loc_14000B892
0x14000b9f0  xor     edx, edx; Tag
0x14000b9f2  call    cs:__imp_ExFreePoolWithTag
0x14000b9f9  nop     dword ptr [rax+rax+00h]
0x14000b9fe  mov     [rbx+110h], rbp
0x14000ba05  jmp     loc_14000B8A2
0x14000ba0a  xor     edx, edx; Tag
0x14000ba0c  call    cs:__imp_ExFreePoolWithTag
0x14000ba13  nop     dword ptr [rax+rax+00h]
0x14000ba18  mov     [rbx+0C0h], rbp
0x14000ba1f  jmp     loc_14000B8B2
0x14000ba24  xor     edx, edx; Tag
0x14000ba26  call    cs:__imp_ExFreePoolWithTag
0x14000ba2d  nop     dword ptr [rax+rax+00h]
0x14000ba32  jmp     loc_14000B8C7
```
