# LuafvAllocatePool

- ea: `0x14001b650`
- end: `0x14001b78c`
- name: `LuafvAllocatePool`
- size: `316`
- prototype: `char *__fastcall(int, unsigned int, char)`
- caller_count: `33`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001f7c`
- `0x140002698`
- `0x1400035f0`
- `0x1400039b8`
- `0x140003b6c`
- `0x140003f60`
- `0x1400045f4`
- `0x1400047cc`
- `0x14000488c`
- `0x140005034`
- `0x140005370`
- `0x140005800`
- `0x140014df0`
- `0x14001513c`
- `0x1400157d4`
- `0x140016d44`
- `0x140017140`
- `0x140018c98`
- `0x140019730`
- `0x140019f40`
- `0x14001a378`
- `0x14001b794`
- `0x14001d010`
- `0x140021888`
- `0x140022734`
- `0x140023058`
- `0x140024f80`
- `0x1400280d4`
- `0x14002814c`
- `0x140028364`
- `0x140028be8`
- `0x14002965c`
- `0x140029b30`

## callees

- `0x14001b650`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b691`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b6b1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b779`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b691`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b6b1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001b779`
- `ntoskrnl!ExAllocatePool2` at `0x14001b6e1`
- `ntoskrnl!ExAllocatePool2` at `0x14001b6e1`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b71e`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b71e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b703`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b703`

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
    dword_14000ECBC += a2;
    FltReleasePushLockEx(&PoolLock, 0);
    return v9 + 8;
  }
  return 0;
}

```

## disassembly

```asm
0x14001b650  push    rbx
0x14001b652  push    rbp
0x14001b653  push    rsi
0x14001b654  push    rdi
0x14001b655  push    r14
0x14001b657  sub     rsp, 20h
0x14001b65b  lea     ebp, [rdx+8]
0x14001b65e  mov     esi, edx
0x14001b660  mov     r14d, ecx
0x14001b663  cmp     ebp, 8
0x14001b666  jb      loc_14001B73A
0x14001b66c  cmp     r8b, 2
0x14001b670  jnz     loc_14001B75C
0x14001b676  cmp     edx, 0B8h
0x14001b67c  jbe     loc_14001B73E
0x14001b682  mov     bl, 0FFh
0x14001b684  cmp     r8b, 3
0x14001b688  jnz     short loc_14001B6C8
0x14001b68a  lea     rcx, StoreFileLookaside; Lookaside
0x14001b691  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001b698  nop     dword ptr [rax+rax+00h]
0x14001b69d  xor     bl, bl
0x14001b69f  jmp     short loc_14001B6ED
0x14001b6a1  lea     rax, StringLookaside
0x14001b6a8  mov     ecx, ebx
0x14001b6aa  shl     rcx, 7
0x14001b6ae  add     rcx, rax; Lookaside
0x14001b6b1  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001b6b8  nop     dword ptr [rax+rax+00h]
0x14001b6bd  add     bl, 2
0x14001b6c0  mov     rdi, rax
0x14001b6c3  cmp     bl, 0FFh
0x14001b6c6  jnz     short loc_14001B6F0
0x14001b6c8  cmp     r14d, 1
0x14001b6cc  mov     edx, ebp
0x14001b6ce  mov     eax, 40h ; '@'
0x14001b6d3  mov     ecx, 100h
0x14001b6d8  cmovnz  ecx, eax
0x14001b6db  mov     r8d, 6661754Ch
0x14001b6e1  call    cs:__imp_ExAllocatePool2
0x14001b6e8  nop     dword ptr [rax+rax+00h]
0x14001b6ed  mov     rdi, rax
0x14001b6f0  test    rdi, rdi
0x14001b6f3  jz      short loc_14001B73A
0x14001b6f5  xor     edx, edx
0x14001b6f7  mov     [rdi], esi
0x14001b6f9  lea     rcx, PoolLock
0x14001b700  mov     [rdi+4], bl
0x14001b703  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b70a  nop     dword ptr [rax+rax+00h]
0x14001b70f  add     cs:dword_14000ECBC, esi
0x14001b715  lea     rcx, PoolLock
0x14001b71c  xor     edx, edx
0x14001b71e  call    cs:__imp_FltReleasePushLockEx
0x14001b725  nop     dword ptr [rax+rax+00h]
0x14001b72a  lea     rax, [rdi+8]
0x14001b72e  add     rsp, 20h
0x14001b732  pop     r14
0x14001b734  pop     rdi
0x14001b735  pop     rsi
0x14001b736  pop     rbp
0x14001b737  pop     rbx
0x14001b738  retn
0x14001b73a  xor     eax, eax
0x14001b73c  jmp     short loc_14001B72E
0x14001b73e  xor     ebx, ebx
0x14001b740  mov     eax, 38h ; '8'
0x14001b745  cmp     esi, eax
0x14001b747  jbe     loc_14001B6A1
0x14001b74d  inc     ebx
0x14001b74f  add     eax, 20h ; ' '
0x14001b752  cmp     ebx, 5
0x14001b755  jb      short loc_14001B745
0x14001b757  jmp     loc_14001B6A1
0x14001b75c  cmp     r8b, 0Ah
0x14001b760  jnz     loc_14001B682
0x14001b766  cmp     esi, 120h
0x14001b76c  ja      loc_14001B682
0x14001b772  lea     rcx, TableNodeLookaside; Lookaside
0x14001b779  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001b780  nop     dword ptr [rax+rax+00h]
0x14001b785  mov     bl, 1
0x14001b787  jmp     loc_14001B6ED
```
