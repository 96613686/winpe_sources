# CmsLookasides::InitializeLibrary(void)

- ea: `0x1c0055bec`
- end: `0x1c0055dc1`
- name: `?InitializeLibrary@CmsLookasides@@SAJXZ`
- size: `469`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1c0054b90`

## callees

- `0x1c0055bec`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0055c74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0055c74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0055d0d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0055d78`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00899e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0089a1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00899e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0089a1b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00899f7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00899f7`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c0055c0d`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c0055c0d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1c0055d14`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1c0055d14`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1c0055d8c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1c0055d8c`
- `ntoskrnl!ExFreePool` at `0x1c0055ccc`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1c00899bb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1c00899bb`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1c00899c9`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1c00899c9`

## pseudocode

```c
__int64 CmsLookasides::InitializeLibrary(void)
{
  int *v0; // rsi
  unsigned int v1; // ebx
  struct _SmsLookaside * near **i; // r14
  unsigned int v3; // r15d
  struct _SmsLookaside **PoolWithTag; // rax
  unsigned int v5; // ebp
  __int64 v6; // rdi
  struct _SmsLookaside * near *v7; // rdx
  _BYTE *v8; // rcx
  struct _SmsLookaside **v9; // r10
  int j; // eax
  PVOID *v12; // r14
  unsigned int v13; // ebp
  __int64 v14; // rdi
  _BYTE *v15; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  PSLIST_ENTRY v17; // rax

  NumProcessors = KeQueryActiveProcessorCountEx(0xFFFFu);
  dword_1C012D4E4 = CmsAvlTableLite::SizeOfAllocationsOnLookaside2;
  v0 = &dword_1C012D464;
  v1 = 0;
  for ( i = &LookasideLists; ; ++i )
  {
    if ( v1 - 17 <= 1 || (v3 = NumProcessors, v1 == 11) )
      v3 = 1;
    PoolWithTag = (struct _SmsLookaside **)ExAllocatePoolWithTag((POOL_TYPE)512, 192LL * v3, *v0);
    *i = PoolWithTag;
    if ( !PoolWithTag )
      break;
    memset(PoolWithTag, 0, 192LL * v3);
    v5 = 0;
    if ( v3 )
    {
      v6 = 0;
      do
      {
        v7 = *i;
        HIDWORD(v7[v6]) = *(v0 - 1) + 8;
        v8 = &v7[v6 + 1];
        LODWORD(v7[v6]) = *(v0 - 1);
        if ( *((_BYTE *)v0 + 4) )
        {
          *v8 = 1;
          v9 = &v7[24 * v5];
          if ( *((_BYTE *)v0 + 5) )
          {
            BYTE1(v7[v6 + 1]) = 1;
            ExInitializeNPagedLookasideList(
              (PNPAGED_LOOKASIDE_LIST)(v9 + 8),
              ExAllocatePoolWithTag,
              ExFreePool,
              0x200u,
              HIDWORD(v7[v6]),
              *v0,
              0);
          }
          else
          {
            BYTE1(v7[v6 + 1]) = 0;
            ExInitializePagedLookasideList(
              (PPAGED_LOOKASIDE_LIST)(v9 + 8),
              ExAllocatePoolWithTag,
              ExFreePool,
              0x200u,
              HIDWORD(v7[v6]),
              *v0,
              0);
          }
        }
        else
        {
          for ( j = 0; j < 2; ++j )
            *v8++ = j;
          HIDWORD(v7[v6 + 10]) = 100;
        }
        ++v5;
        v6 += 24;
      }
      while ( v5 < v3 );
    }
    ++v1;
    v0 += 3;
    if ( v1 >= 0x19 )
    {
      LookasideListsInitialized = 1;
      return 0;
    }
  }
  if ( v1 )
  {
    v12 = (PVOID *)&(&LookasideLists)[v1];
    do
    {
      --v1;
      --v12;
      v13 = 0;
      if ( v3 )
      {
        v14 = 0;
        do
        {
          v15 = *v12;
          if ( *((_BYTE *)*v12 + v14 + 8) )
          {
            v16 = (struct _NPAGED_LOOKASIDE_LIST *)&v15[192 * v13 + 64];
            if ( v15[v14 + 9] )
              ExDeleteNPagedLookasideList(v16);
            else
              ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)v16);
          }
          else
          {
            while ( 1 )
            {
              v17 = ExpInterlockedPopEntrySList((PSLIST_HEADER)&v15[v14 + 64]);
              if ( !v17 )
                break;
              ExFreePoolWithTag(v17, 0);
              --*(_DWORD *)&v15[v14 + 80];
            }
          }
          ++v13;
          v14 += 192;
        }
        while ( v13 < v3 );
      }
      ExFreePoolWithTag(*v12, 0);
      *v12 = 0;
    }
    while ( v1 );
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1c0055bec  mov     [rsp+arg_0], rbx
0x1c0055bf1  mov     [rsp+arg_8], rbp
0x1c0055bf6  mov     [rsp+arg_10], rsi
0x1c0055bfb  push    rdi
0x1c0055bfc  push    r12
0x1c0055bfe  push    r13
0x1c0055c00  push    r14
0x1c0055c02  push    r15
0x1c0055c04  sub     rsp, 40h
0x1c0055c08  mov     ecx, 0FFFFh; GroupNumber
0x1c0055c0d  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1c0055c14  nop     dword ptr [rax+rax+00h]
0x1c0055c19  mov     cs:?NumProcessors@@3KA, eax; ulong NumProcessors
0x1c0055c1f  xor     r13d, r13d
0x1c0055c22  mov     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x1c0055c28  lea     r12, ?LookasideLists@@3PAPEAU_SmsLookaside@@A; _SmsLookaside * near * LookasideLists
0x1c0055c2f  mov     cs:dword_1C012D4E4, eax
0x1c0055c35  lea     rsi, dword_1C012D464
0x1c0055c3c  mov     ebx, r13d
0x1c0055c3f  mov     r14, r12
0x1c0055c42  lea     eax, [rbx-11h]
0x1c0055c45  cmp     eax, 1
0x1c0055c48  jbe     loc_1C0055DB6
0x1c0055c4e  mov     r15d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c0055c55  cmp     ebx, 0Bh
0x1c0055c58  jz      loc_1C0055DB6
0x1c0055c5e  mov     r8d, [rsi]; Tag
0x1c0055c61  mov     ecx, 200h; PoolType
0x1c0055c66  mov     eax, r15d
0x1c0055c69  lea     rdi, [rax+rax*2]
0x1c0055c6d  shl     rdi, 6
0x1c0055c71  mov     rdx, rdi; NumberOfBytes
0x1c0055c74  call    cs:__imp_ExAllocatePoolWithTag
0x1c0055c7b  nop     dword ptr [rax+rax+00h]
0x1c0055c80  mov     [r14], rax
0x1c0055c83  test    rax, rax
0x1c0055c86  jz      loc_1C0089976
0x1c0055c8c  mov     r8, rdi; Size
0x1c0055c8f  xor     edx, edx; Val
0x1c0055c91  mov     rcx, rax; void *
0x1c0055c94  call    memset
0x1c0055c99  mov     ebp, r13d
0x1c0055c9c  test    r15d, r15d
0x1c0055c9f  jz      loc_1C0055D32
0x1c0055ca5  mov     rdi, r13
0x1c0055ca8  mov     rdx, [r14]
0x1c0055cab  mov     eax, [rsi-4]
0x1c0055cae  add     eax, 8
0x1c0055cb1  mov     [rdi+rdx+4], eax
0x1c0055cb5  lea     rcx, [rdx+8]
0x1c0055cb9  mov     eax, [rsi-4]
0x1c0055cbc  add     rcx, rdi
0x1c0055cbf  mov     [rdi+rdx], eax
0x1c0055cc2  cmp     [rsi+4], r13b
0x1c0055cc6  jz      loc_1C0055D9A
0x1c0055ccc  mov     r8, cs:__imp_ExFreePool; Free
0x1c0055cd3  mov     r9d, 200h; Flags
0x1c0055cd9  mov     eax, ebp
0x1c0055cdb  mov     byte ptr [rcx], 1
0x1c0055cde  mov     [rsp+68h+Depth], r13w; Depth
0x1c0055ce4  lea     r10, [rax+rax*2]
0x1c0055ce8  shl     r10, 6
0x1c0055cec  add     r10, rdx
0x1c0055cef  cmp     [rsi+5], r13b
0x1c0055cf3  jz      short loc_1C0055D6D
0x1c0055cf5  mov     byte ptr [rdi+rdx+9], 1
0x1c0055cfa  lea     rcx, [r10+40h]; Lookaside
0x1c0055cfe  mov     edx, [rdi+rdx+4]
0x1c0055d02  mov     eax, [rsi]
0x1c0055d04  mov     [rsp+68h+Tag], eax; Tag
0x1c0055d08  mov     [rsp+68h+Size], rdx; Size
0x1c0055d0d  mov     rdx, cs:__imp_ExAllocatePoolWithTag; Allocate
0x1c0055d14  call    cs:__imp_ExInitializeNPagedLookasideList
0x1c0055d1b  nop     dword ptr [rax+rax+00h]
0x1c0055d20  inc     ebp
0x1c0055d22  add     rdi, 0C0h
0x1c0055d29  cmp     ebp, r15d
0x1c0055d2c  jb      loc_1C0055CA8
0x1c0055d32  inc     ebx
0x1c0055d34  add     r14, 8
0x1c0055d38  add     rsi, 0Ch
0x1c0055d3c  cmp     ebx, 19h
0x1c0055d3f  jb      loc_1C0055C42
0x1c0055d45  mov     cs:?LookasideListsInitialized@@3EA, 1; uchar LookasideListsInitialized
0x1c0055d4c  xor     eax, eax
0x1c0055d4e  lea     r11, [rsp+68h+var_28]
0x1c0055d53  mov     rbx, [r11+30h]
0x1c0055d57  mov     rbp, [r11+38h]
0x1c0055d5b  mov     rsi, [r11+40h]
0x1c0055d5f  mov     rsp, r11
0x1c0055d62  pop     r15
0x1c0055d64  pop     r14
0x1c0055d66  pop     r13
0x1c0055d68  pop     r12
0x1c0055d6a  pop     rdi
0x1c0055d6b  retn
0x1c0055d6d  mov     [rdi+rdx+9], r13b
0x1c0055d72  mov     ecx, [rdi+rdx+4]
0x1c0055d76  mov     eax, [rsi]
0x1c0055d78  mov     rdx, cs:__imp_ExAllocatePoolWithTag; Allocate
0x1c0055d7f  mov     [rsp+68h+Tag], eax; Tag
0x1c0055d83  mov     [rsp+68h+Size], rcx; Size
0x1c0055d88  lea     rcx, [r10+40h]; Lookaside
0x1c0055d8c  call    cs:__imp_ExInitializePagedLookasideList
0x1c0055d93  nop     dword ptr [rax+rax+00h]
0x1c0055d98  jmp     short loc_1C0055D20
0x1c0055d9a  mov     eax, r13d
0x1c0055d9d  mov     [rcx], al
0x1c0055d9f  inc     eax
0x1c0055da1  inc     rcx
0x1c0055da4  cmp     eax, 2
0x1c0055da7  jl      short loc_1C0055D9D
0x1c0055da9  mov     dword ptr [rdi+rdx+54h], 64h ; 'd'
0x1c0055db1  jmp     loc_1C0055D20
0x1c0055db6  mov     r15d, 1
0x1c0055dbc  jmp     loc_1C0055C5E
0x1c0089976  test    ebx, ebx
0x1c0089978  jz      loc_1C0089A32
0x1c008997e  mov     eax, ebx
0x1c0089980  lea     r14, [r12+rax*8]
0x1c0089984  dec     ebx
0x1c0089986  lea     r14, [r14-8]
0x1c008998a  mov     ebp, r13d
0x1c008998d  test    r15d, r15d
0x1c0089990  jz      loc_1C0089A16
0x1c0089996  mov     rdi, r13
0x1c0089999  mov     rsi, [r14]
0x1c008999c  cmp     [rdi+rsi+8], r13b
0x1c00899a1  jz      short loc_1C00899D7
0x1c00899a3  mov     eax, ebp
0x1c00899a5  lea     rcx, [rax+rax*2]
0x1c00899a9  shl     rcx, 6
0x1c00899ad  add     rcx, 40h ; '@'
0x1c00899b1  add     rcx, rsi; Lookaside
0x1c00899b4  cmp     [rdi+rsi+9], r13b
0x1c00899b9  jz      short loc_1C00899C9
0x1c00899bb  call    cs:__imp_ExDeleteNPagedLookasideList
0x1c00899c2  nop     dword ptr [rax+rax+00h]
0x1c00899c7  jmp     short loc_1C0089A08
0x1c00899c9  call    cs:__imp_ExDeletePagedLookasideList
0x1c00899d0  nop     dword ptr [rax+rax+00h]
0x1c00899d5  jmp     short loc_1C0089A08
0x1c00899d7  lea     r12, [rdi+rsi]
0x1c00899db  jmp     short loc_1C00899F2
0x1c00899dd  xor     edx, edx; Tag
0x1c00899df  mov     rcx, rax; P
0x1c00899e2  call    cs:__imp_ExFreePoolWithTag
0x1c00899e9  nop     dword ptr [rax+rax+00h]
0x1c00899ee  dec     dword ptr [rdi+rsi+50h]
0x1c00899f2  lea     rcx, [r12+40h]; ListHead
0x1c00899f7  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00899fe  nop     dword ptr [rax+rax+00h]
0x1c0089a03  test    rax, rax
0x1c0089a06  jnz     short loc_1C00899DD
0x1c0089a08  inc     ebp
0x1c0089a0a  add     rdi, 0C0h
0x1c0089a11  cmp     ebp, r15d
0x1c0089a14  jb      short loc_1C0089999
0x1c0089a16  mov     rcx, [r14]; P
0x1c0089a19  xor     edx, edx; Tag
0x1c0089a1b  call    cs:__imp_ExFreePoolWithTag
0x1c0089a22  nop     dword ptr [rax+rax+00h]
0x1c0089a27  mov     [r14], r13
0x1c0089a2a  test    ebx, ebx
0x1c0089a2c  jnz     loc_1C0089984
0x1c0089a32  mov     eax, 0C000009Ah
0x1c0089a37  jmp     loc_1C0055D4E
```
