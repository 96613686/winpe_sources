# LuafvAllocatePool

- ea: `0x14001b6a0`
- end: `0x14001b7dc`
- name: `LuafvAllocatePool`
- size: `316`
- prototype: `char *__fastcall(int, unsigned int, char)`
- caller_count: `33`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140002408`
- `0x1400033c0`
- `0x140003788`
- `0x14000393c`
- `0x140003d30`
- `0x1400043c4`
- `0x14000459c`
- `0x1400046c4`
- `0x140004e6c`
- `0x1400051a8`
- `0x1400054e8`
- `0x140005b84`
- `0x140014df0`
- `0x14001513c`
- `0x1400157d4`
- `0x140016d94`
- `0x140017190`
- `0x140018ce8`
- `0x140019780`
- `0x140019f90`
- `0x14001a3c8`
- `0x14001b7e4`
- `0x14001d060`
- `0x1400218d8`
- `0x140022784`
- `0x1400230a8`
- `0x140024fd0`
- `0x1400280d4`
- `0x14002814c`
- `0x140028364`
- `0x140028be8`
- `0x14002965c`
- `0x140029b30`

## callees

- `0x14001b6a0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b6e1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b701`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b7c9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b6e1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b701`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b7c9`
- `ntoskrnl!ExAllocatePool2` at `0x14001b731`
- `ntoskrnl!ExAllocatePool2` at `0x14001b731`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b76e`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b76e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b753`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b753`

## pseudocode

```c
char *__fastcall LuafvAllocatePool(int a1, unsigned int a2, char a3)
{
  unsigned int v3; // ebp
  char v6; // bl
  char *Pool2; // rax
  char *v8; // rax
  char *v9; // rdi
  __int64 v10; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // eax

  v3 = a2 + 8;
  if ( a2 >= 0xFFFFFFF8 )
    return 0;
  if ( a3 != 2 )
  {
    if ( a3 == 10 && a2 <= 0x120 )
    {
      Pool2 = (char *)ExAllocateFromPagedLookasideList(&TableNodeLookaside);
      v6 = 1;
      goto LABEL_10;
    }
    goto LABEL_4;
  }
  if ( a2 > 0xB8 )
  {
LABEL_4:
    v6 = -1;
    if ( a3 == 3 )
    {
      Pool2 = (char *)ExAllocateFromPagedLookasideList(&StoreFileLookaside);
      v6 = 0;
LABEL_10:
      v9 = Pool2;
      goto LABEL_11;
    }
LABEL_7:
    v10 = 256;
    if ( a1 != 1 )
      v10 = 64;
    Pool2 = (char *)ExAllocatePool2(v10, v3, 1717663052);
    goto LABEL_10;
  }
  v12 = 0;
  v13 = 56;
  do
  {
    if ( a2 <= v13 )
      break;
    ++v12;
    v13 += 32;
  }
  while ( v12 < 5 );
  v8 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&StringLookaside[16 * (unsigned __int64)v12]);
  v6 = v12 + 2;
  v9 = v8;
  if ( v6 == -1 )
    goto LABEL_7;
LABEL_11:
  if ( v9 )
  {
    *(_DWORD *)v9 = a2;
    v9[4] = v6;
    FltAcquirePushLockExclusiveEx(&PoolLock, 0);
    dword_14000F2FC += a2;
    FltReleasePushLockEx(&PoolLock, 0);
    return v9 + 8;
  }
  return 0;
}

```

## disassembly

```asm
0x14001b6a0  push    rbx
0x14001b6a2  push    rbp
0x14001b6a3  push    rsi
0x14001b6a4  push    rdi
0x14001b6a5  push    r14
0x14001b6a7  sub     rsp, 20h
0x14001b6ab  lea     ebp, [rdx+8]
0x14001b6ae  mov     esi, edx
0x14001b6b0  mov     r14d, ecx
0x14001b6b3  cmp     ebp, 8
0x14001b6b6  jb      loc_14001B78A
0x14001b6bc  cmp     r8b, 2
0x14001b6c0  jnz     loc_14001B7AC
0x14001b6c6  cmp     edx, 0B8h
0x14001b6cc  jbe     loc_14001B78E
0x14001b6d2  mov     bl, 0FFh
0x14001b6d4  cmp     r8b, 3
0x14001b6d8  jnz     short loc_14001B718
0x14001b6da  lea     rcx, StoreFileLookaside; Lookaside
0x14001b6e1  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001b6e8  nop     dword ptr [rax+rax+00h]
0x14001b6ed  xor     bl, bl
0x14001b6ef  jmp     short loc_14001B73D
0x14001b6f1  lea     rax, StringLookaside
0x14001b6f8  mov     ecx, ebx
0x14001b6fa  shl     rcx, 7
0x14001b6fe  add     rcx, rax; Lookaside
0x14001b701  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001b708  nop     dword ptr [rax+rax+00h]
0x14001b70d  add     bl, 2
0x14001b710  mov     rdi, rax
0x14001b713  cmp     bl, 0FFh
0x14001b716  jnz     short loc_14001B740
0x14001b718  cmp     r14d, 1
0x14001b71c  mov     edx, ebp
0x14001b71e  mov     eax, 40h ; '@'
0x14001b723  mov     ecx, 100h
0x14001b728  cmovnz  ecx, eax
0x14001b72b  mov     r8d, 6661754Ch
0x14001b731  call    cs:__imp_ExAllocatePool2
0x14001b738  nop     dword ptr [rax+rax+00h]
0x14001b73d  mov     rdi, rax
0x14001b740  test    rdi, rdi
0x14001b743  jz      short loc_14001B78A
0x14001b745  xor     edx, edx
0x14001b747  mov     [rdi], esi
0x14001b749  lea     rcx, PoolLock
0x14001b750  mov     [rdi+4], bl
0x14001b753  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b75a  nop     dword ptr [rax+rax+00h]
0x14001b75f  add     cs:dword_14000F2FC, esi
0x14001b765  lea     rcx, PoolLock
0x14001b76c  xor     edx, edx
0x14001b76e  call    cs:__imp_FltReleasePushLockEx
0x14001b775  nop     dword ptr [rax+rax+00h]
0x14001b77a  lea     rax, [rdi+8]
0x14001b77e  add     rsp, 20h
0x14001b782  pop     r14
0x14001b784  pop     rdi
0x14001b785  pop     rsi
0x14001b786  pop     rbp
0x14001b787  pop     rbx
0x14001b788  retn
0x14001b78a  xor     eax, eax
0x14001b78c  jmp     short loc_14001B77E
0x14001b78e  xor     ebx, ebx
0x14001b790  mov     eax, 38h ; '8'
0x14001b795  cmp     esi, eax
0x14001b797  jbe     loc_14001B6F1
0x14001b79d  inc     ebx
0x14001b79f  add     eax, 20h ; ' '
0x14001b7a2  cmp     ebx, 5
0x14001b7a5  jb      short loc_14001B795
0x14001b7a7  jmp     loc_14001B6F1
0x14001b7ac  cmp     r8b, 0Ah
0x14001b7b0  jnz     loc_14001B6D2
0x14001b7b6  cmp     esi, 120h
0x14001b7bc  ja      loc_14001B6D2
0x14001b7c2  lea     rcx, TableNodeLookaside; Lookaside
0x14001b7c9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001b7d0  nop     dword ptr [rax+rax+00h]
0x14001b7d5  mov     bl, 1
0x14001b7d7  jmp     loc_14001B73D
```
