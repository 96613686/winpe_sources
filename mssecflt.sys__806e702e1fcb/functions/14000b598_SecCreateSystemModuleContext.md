# SecCreateSystemModuleContext

- ea: `0x14000b598`
- end: `0x14000b7f0`
- name: `SecCreateSystemModuleContext`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002fa68`

## callees

- `0x140006684`
- `0x14000b598`
- `0x14000b940`
- `0x14000ba24`
- `0x14000f094`
- `0x140011610`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000b5e5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000b6e8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000b5e5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000b6e8`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000b62c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000b7bc`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000b62c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000b7bc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000b649`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000b649`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b6be`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b6be`

## pseudocode

```c
__int64 __fastcall SecCreateSystemModuleContext(__int64 a1, __int64 a2, PSLIST_ENTRY *a3)
{
  SHORT *p_ActiveCount; // rsi
  union _SLIST_HEADER *v7; // rcx
  PSLIST_ENTRY v8; // rbx
  unsigned int v9; // ebx
  struct _SLIST_ENTRY *Next; // r8
  OWNER_ENTRY *p_OwnerEntry; // rcx
  unsigned __int64 OwnerThread; // rdx
  unsigned __int64 v13; // rax
  _QWORD v15[12]; // [rsp+20h] [rbp-68h] BYREF

  memset(v15, 0, sizeof(v15));
  if ( !a1 || !a2 )
    return 3221225485LL;
  ExEnterCriticalRegionAndAcquireResourceExclusive(SecSystemModuleTable);
  if ( BYTE1(SecSystemModuleTable[2].ActiveEntries) )
  {
    v15[2] = *(_QWORD *)(a2 + 8);
    v15[3] = *(_QWORD *)(a2 + 24);
    LODWORD(v15[6]) = 1;
    SecRemoveAndReleaseCollidingSystemModuleContexts(v15);
  }
  ExReleaseResourceAndLeaveCriticalRegion(SecSystemModuleTable);
  p_ActiveCount = &SecSystemModuleTable[1].ActiveCount;
  v7 = (union _SLIST_HEADER *)&SecSystemModuleTable[1].ActiveCount;
  ++HIDWORD(SecSystemModuleTable[1].ExclusiveWaiters);
  v8 = ExpInterlockedPopEntrySList(v7);
  if ( !v8 )
  {
    ++*((_DWORD *)p_ActiveCount + 6);
    v8 = (PSLIST_ENTRY)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))p_ActiveCount + 6))(
                         *((unsigned int *)p_ActiveCount + 9),
                         *((unsigned int *)p_ActiveCount + 11),
                         *((unsigned int *)p_ActiveCount + 10));
  }
  if ( v8 )
  {
    memset(v8, 0, 0x60u);
    if ( (int)SecUnicodeToNullTerminatedUnicode(a1, v8) < 0 )
    {
      _mm_lfence();
      RtlInitUnicodeString((PUNICODE_STRING)v8, &word_140016A48);
    }
    v8[1].Next = *(struct _SLIST_ENTRY **)(a2 + 8);
    *((_QWORD *)&v8[1].Next + 1) = *(_QWORD *)(a2 + 24);
    LODWORD(v8[3].Next) = 1;
    ExEnterCriticalRegionAndAcquireResourceExclusive(SecSystemModuleTable);
    if ( LOBYTE(SecSystemModuleTable[2].ActiveEntries) )
    {
      p_OwnerEntry = &SecSystemModuleTable[2].OwnerEntry;
      if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 )
      {
        if ( p_OwnerEntry->OwnerThread )
          OwnerThread = p_OwnerEntry->OwnerThread ^ (unsigned __int64)p_OwnerEntry;
        else
          OwnerThread = 0;
      }
      else
      {
        OwnerThread = p_OwnerEntry->OwnerThread;
      }
      LOBYTE(Next) = 0;
      if ( OwnerThread )
      {
        Next = v8[1].Next;
        while ( 1 )
        {
          if ( (unsigned __int64)Next < *(_QWORD *)(OwnerThread - 40) )
          {
            v13 = *(_QWORD *)OwnerThread;
            if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 )
            {
              if ( !v13 )
                goto LABEL_31;
              v13 ^= OwnerThread;
            }
            if ( !v13 )
            {
LABEL_31:
              LOBYTE(Next) = 0;
              break;
            }
          }
          else
          {
            v13 = *(_QWORD *)(OwnerThread + 8);
            if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 )
            {
              if ( !v13 )
                goto LABEL_25;
              v13 ^= OwnerThread;
            }
            if ( !v13 )
            {
LABEL_25:
              LOBYTE(Next) = 1;
              break;
            }
          }
          OwnerThread = v13;
        }
      }
      TreeRbInsertNodeEx(p_OwnerEntry, OwnerThread, Next, &v8[3].Next + 1);
      ++LODWORD(SecSystemModuleTable[2].Reserved2);
      if ( a3 )
      {
        ++LODWORD(v8[3].Next);
        *a3 = v8;
      }
      v9 = 0;
    }
    else
    {
      SecReleaseSystemModuleContext(v8);
      v9 = -1073741823;
    }
    ExReleaseResourceAndLeaveCriticalRegion(SecSystemModuleTable);
  }
  else
  {
    v9 = -1073741670;
    LOBYTE(SecSystemModuleTable[2].ActiveEntries) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x14000b598  mov     rax, rsp
0x14000b59b  mov     [rax+8], rbx
0x14000b59f  mov     [rax+10h], rbp
0x14000b5a3  mov     [rax+18h], rsi
0x14000b5a7  mov     [rax+20h], rdi
0x14000b5ab  push    r14
0x14000b5ad  sub     rsp, 80h
0x14000b5b4  mov     rdi, rdx
0x14000b5b7  mov     r14, r8
0x14000b5ba  xor     edx, edx; Val
0x14000b5bc  mov     rbp, rcx
0x14000b5bf  lea     rcx, [rax-68h]; void *
0x14000b5c3  lea     r8d, [rdx+60h]; Size
0x14000b5c7  call    memset
0x14000b5cc  test    rbp, rbp
0x14000b5cf  jz      loc_14000B7CC
0x14000b5d5  test    rdi, rdi
0x14000b5d8  jz      loc_14000B7CC
0x14000b5de  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000b5e5  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14000b5ec  nop     dword ptr [rax+rax+00h]
0x14000b5f1  mov     rax, cs:SecSystemModuleTable
0x14000b5f8  cmp     byte ptr [rax+111h], 0
0x14000b5ff  jz      short loc_14000B625
0x14000b601  mov     rax, [rdi+8]
0x14000b605  lea     rcx, [rsp+88h+var_68]
0x14000b60a  mov     [rsp+88h+var_58], rax
0x14000b60f  mov     rax, [rdi+18h]
0x14000b613  mov     [rsp+88h+var_50], rax
0x14000b618  mov     [rsp+88h+var_38], 1
0x14000b620  call    SecRemoveAndReleaseCollidingSystemModuleContexts
0x14000b625  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000b62c  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000b633  nop     dword ptr [rax+rax+00h]
0x14000b638  mov     rsi, cs:SecSystemModuleTable
0x14000b63f  sub     rsi, 0FFFFFFFFFFFFFF80h
0x14000b643  mov     rcx, rsi; ListHead
0x14000b646  inc     dword ptr [rsi+14h]
0x14000b649  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000b650  nop     dword ptr [rax+rax+00h]
0x14000b655  mov     rbx, rax
0x14000b658  test    rax, rax
0x14000b65b  jnz     short loc_14000B677
0x14000b65d  inc     dword ptr [rsi+18h]
0x14000b660  mov     edx, [rsi+2Ch]
0x14000b663  mov     rax, [rsi+30h]
0x14000b667  mov     r8d, [rsi+28h]
0x14000b66b  mov     ecx, [rsi+24h]
0x14000b66e  call    cs:__guard_dispatch_icall_fptr
0x14000b674  mov     rbx, rax
0x14000b677  test    rbx, rbx
0x14000b67a  jnz     short loc_14000B694
0x14000b67c  mov     rax, cs:SecSystemModuleTable
0x14000b683  mov     ebx, 0C000009Ah
0x14000b688  mov     byte ptr [rax+110h], 0
0x14000b68f  jmp     loc_14000B7C8
0x14000b694  xor     edx, edx; Val
0x14000b696  mov     rcx, rbx; void *
0x14000b699  lea     r8d, [rdx+60h]; Size
0x14000b69d  call    memset
0x14000b6a2  mov     rdx, rbx
0x14000b6a5  mov     rcx, rbp
0x14000b6a8  call    SecUnicodeToNullTerminatedUnicode
0x14000b6ad  test    eax, eax
0x14000b6af  jns     short loc_14000B6CA
0x14000b6b1  lfence
0x14000b6b4  lea     rdx, word_140016A48; SourceString
0x14000b6bb  mov     rcx, rbx; DestinationString
0x14000b6be  call    cs:__imp_RtlInitUnicodeString
0x14000b6c5  nop     dword ptr [rax+rax+00h]
0x14000b6ca  mov     rax, [rdi+8]
0x14000b6ce  mov     [rbx+10h], rax
0x14000b6d2  mov     rax, [rdi+18h]
0x14000b6d6  mov     [rbx+18h], rax
0x14000b6da  mov     dword ptr [rbx+30h], 1
0x14000b6e1  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000b6e8  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14000b6ef  nop     dword ptr [rax+rax+00h]
0x14000b6f4  mov     rcx, cs:SecSystemModuleTable
0x14000b6fb  cmp     byte ptr [rcx+110h], 0
0x14000b702  jnz     short loc_14000B716
0x14000b704  mov     rcx, rbx; ListEntry
0x14000b707  call    SecReleaseSystemModuleContext
0x14000b70c  mov     ebx, 0C0000001h
0x14000b711  jmp     loc_14000B7B5
0x14000b716  add     rcx, 100h
0x14000b71d  test    byte ptr [rcx+8], 1
0x14000b721  jz      short loc_14000B737
0x14000b723  mov     rax, [rcx]
0x14000b726  test    rax, rax
0x14000b729  jz      short loc_14000B733
0x14000b72b  mov     rdx, rcx
0x14000b72e  xor     rdx, rax
0x14000b731  jmp     short loc_14000B73A
0x14000b733  xor     edx, edx
0x14000b735  jmp     short loc_14000B73A
0x14000b737  mov     rdx, [rcx]
0x14000b73a  movzx   r9d, byte ptr [rcx+8]
0x14000b73f  xor     r8b, r8b
0x14000b742  and     r9d, 1
0x14000b746  test    rdx, rdx
0x14000b749  jz      short loc_14000B78D
0x14000b74b  mov     r8, [rbx+10h]
0x14000b74f  cmp     r8, [rdx-28h]
0x14000b753  jb      short loc_14000B770
0x14000b755  mov     rax, [rdx+8]
0x14000b759  test    r9d, r9d
0x14000b75c  jz      short loc_14000B766
0x14000b75e  test    rax, rax
0x14000b761  jz      short loc_14000B76B
0x14000b763  xor     rax, rdx
0x14000b766  test    rax, rax
0x14000b769  jnz     short loc_14000B785
0x14000b76b  mov     r8b, 1
0x14000b76e  jmp     short loc_14000B78D
0x14000b770  mov     rax, [rdx]
0x14000b773  test    r9d, r9d
0x14000b776  jz      short loc_14000B780
0x14000b778  test    rax, rax
0x14000b77b  jz      short loc_14000B78A
0x14000b77d  xor     rax, rdx
0x14000b780  test    rax, rax
0x14000b783  jz      short loc_14000B78A
0x14000b785  mov     rdx, rax
0x14000b788  jmp     short loc_14000B74F
0x14000b78a  xor     r8b, r8b
0x14000b78d  lea     r9, [rbx+38h]
0x14000b791  call    TreeRbInsertNodeEx
0x14000b796  mov     rax, cs:SecSystemModuleTable
0x14000b79d  inc     dword ptr [rax+120h]
0x14000b7a3  test    r14, r14
0x14000b7a6  jz      short loc_14000B7B3
0x14000b7a8  mov     eax, [rbx+30h]
0x14000b7ab  inc     eax
0x14000b7ad  mov     [rbx+30h], eax
0x14000b7b0  mov     [r14], rbx
0x14000b7b3  xor     ebx, ebx
0x14000b7b5  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000b7bc  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000b7c3  nop     dword ptr [rax+rax+00h]
0x14000b7c8  mov     eax, ebx
0x14000b7ca  jmp     short loc_14000B7D1
0x14000b7cc  mov     eax, 0C000000Dh
0x14000b7d1  lea     r11, [rsp+88h+var_8]
0x14000b7d9  mov     rbx, [r11+10h]
0x14000b7dd  mov     rbp, [r11+18h]
0x14000b7e1  mov     rsi, [r11+20h]
0x14000b7e5  mov     rdi, [r11+28h]
0x14000b7e9  mov     rsp, r11
0x14000b7ec  pop     r14
0x14000b7ee  retn
```
