# SecGetSessionsFilterMasksAndAsimovNamespaces

- ea: `0x14003a5b8`
- end: `0x14003a766`
- name: `SecGetSessionsFilterMasksAndAsimovNamespaces`
- size: `430`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140007db4`
- `0x140036860`
- `0x140036df4`
- `0x14003715c`
- `0x1400373fc`
- `0x1400376ec`
- `0x140037a04`
- `0x140037d30`
- `0x140038164`

## callees

- `0x140009b80`
- `0x14001042b`
- `0x1400104eb`
- `0x140011610`
- `0x14003a5b8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003a643`
- `ntoskrnl!RtlCompareMemory` at `0x14003a643`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a6be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a6be`

## pseudocode

```c
__int64 __fastcall SecGetSessionsFilterMasksAndAsimovNamespaces(unsigned int a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v4; // r15d
  __int64 v7; // rsi
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  _QWORD *PoolWithTag; // rax
  char v11; // cl
  _QWORD *v12; // rbx

  v3 = 0;
  v4 = 0;
  *a3 = 0;
  if ( !a2 || !a1 )
    return 3221225485LL;
  FltAcquirePushLockSharedEx_0((char *)SecData + 1240, 0);
  v7 = 0;
  if ( !a1 )
  {
LABEL_18:
    *a3 = v3;
    v3 = 0;
    goto LABEL_19;
  }
  while ( 1 )
  {
    v8 = (_QWORD *)*((_QWORD *)SecData + 156);
    if ( v8 != (_QWORD *)((char *)SecData + 1248) )
      break;
LABEL_17:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= a1 )
      goto LABEL_18;
  }
  while ( RtlCompareMemory((const void *)(a2 + 20 * v7), v8 + 2, 0x10u) != 16 )
  {
    v8 = (_QWORD *)*v8;
    if ( v8 == (_QWORD *)((char *)SecData + 1248) )
      goto LABEL_17;
  }
  v9 = v3;
  if ( v3 )
  {
    while ( *v9 != ~v8[4] )
    {
      v9 = (_QWORD *)v9[2];
      if ( !v9 )
        goto LABEL_11;
    }
    *((_BYTE *)v9 + 8) |= *(_BYTE *)(a2 + 20 * v7 + 16);
    goto LABEL_17;
  }
LABEL_11:
  if ( qword_140020008 )
    PoolWithTag = (_QWORD *)qword_140020008(256, 24, 1933927251);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x18u, 0x73456353u);
  if ( PoolWithTag )
  {
    *PoolWithTag = ~v8[4];
    v11 = *(_BYTE *)(a2 + 20 * v7 + 16);
    PoolWithTag[2] = v3;
    v3 = PoolWithTag;
    *((_BYTE *)PoolWithTag + 8) = v11;
    goto LABEL_17;
  }
  v4 = -1073741670;
LABEL_19:
  FltReleasePushLockEx_0((char *)SecData + 1240, 0);
  if ( v3 )
  {
    do
    {
      v12 = (_QWORD *)v3[2];
      SecFreePool(v3, 0x73456353u);
      v3 = v12;
    }
    while ( v12 );
  }
  return v4;
}

```

## disassembly

```asm
0x14003a5b8  mov     rax, rsp
0x14003a5bb  mov     [rax+8], rbx
0x14003a5bf  mov     [rax+10h], rbp
0x14003a5c3  mov     [rax+20h], rsi
0x14003a5c7  mov     [rax+18h], r8
0x14003a5cb  push    rdi
0x14003a5cc  push    r12
0x14003a5ce  push    r13
0x14003a5d0  push    r14
0x14003a5d2  push    r15
0x14003a5d4  sub     rsp, 20h
0x14003a5d8  xor     edi, edi
0x14003a5da  xor     r15d, r15d
0x14003a5dd  mov     [r8], rdi
0x14003a5e0  mov     r12, rdx
0x14003a5e3  mov     ebp, ecx
0x14003a5e5  test    rdx, rdx
0x14003a5e8  jz      loc_14003A743
0x14003a5ee  test    ecx, ecx
0x14003a5f0  jz      loc_14003A743
0x14003a5f6  mov     rcx, cs:SecData
0x14003a5fd  xor     edx, edx
0x14003a5ff  add     rcx, 4D8h
0x14003a606  call    FltAcquirePushLockSharedEx_0
0x14003a60b  xor     esi, esi
0x14003a60d  test    ebp, ebp
0x14003a60f  jz      loc_14003A6F9
0x14003a615  mov     rax, cs:SecData
0x14003a61c  add     rax, 4E0h
0x14003a622  mov     rbx, [rax]
0x14003a625  cmp     rbx, rax
0x14003a628  jz      loc_14003A6EF
0x14003a62e  lea     rax, [rsi+rsi*4]
0x14003a632  lea     r13, [r12+rax*4]
0x14003a636  lea     rdx, [rbx+10h]; Source2
0x14003a63a  mov     r8d, 10h; Length
0x14003a640  mov     rcx, r13; Source1
0x14003a643  call    cs:__imp_RtlCompareMemory
0x14003a64a  nop     dword ptr [rax+rax+00h]
0x14003a64f  cmp     rax, 10h
0x14003a653  jz      short loc_14003A66F
0x14003a655  mov     rax, cs:SecData
0x14003a65c  mov     rbx, [rbx]
0x14003a65f  add     rax, 4E0h
0x14003a665  cmp     rbx, rax
0x14003a668  jnz     short loc_14003A636
0x14003a66a  jmp     loc_14003A6EF
0x14003a66f  mov     rcx, rdi
0x14003a672  test    rdi, rdi
0x14003a675  jz      short loc_14003A68C
0x14003a677  mov     rax, [rbx+20h]
0x14003a67b  not     rax
0x14003a67e  cmp     [rcx], rax
0x14003a681  jz      short loc_14003A6B0
0x14003a683  mov     rcx, [rcx+10h]
0x14003a687  test    rcx, rcx
0x14003a68a  jnz     short loc_14003A67E
0x14003a68c  mov     rax, cs:qword_140020008
0x14003a693  mov     edx, 18h; NumberOfBytes
0x14003a698  mov     r8d, 73456353h; Tag
0x14003a69e  test    rax, rax
0x14003a6a1  jz      short loc_14003A6B9
0x14003a6a3  mov     ecx, 100h
0x14003a6a8  call    cs:__guard_dispatch_icall_fptr
0x14003a6ae  jmp     short loc_14003A6CA
0x14003a6b0  mov     al, [r13+10h]
0x14003a6b4  or      [rcx+8], al
0x14003a6b7  jmp     short loc_14003A6EF
0x14003a6b9  mov     ecx, 1; PoolType
0x14003a6be  call    cs:__imp_ExAllocatePoolWithTag
0x14003a6c5  nop     dword ptr [rax+rax+00h]
0x14003a6ca  mov     rdx, rax
0x14003a6cd  test    rax, rax
0x14003a6d0  jz      short loc_14003A73B
0x14003a6d2  mov     rax, [rbx+20h]
0x14003a6d6  not     rax
0x14003a6d9  mov     [rdx], rax
0x14003a6dc  lea     rax, [rsi+rsi*4]
0x14003a6e0  mov     cl, [r12+rax*4+10h]
0x14003a6e5  mov     [rdx+10h], rdi
0x14003a6e9  mov     rdi, rdx
0x14003a6ec  mov     [rdx+8], cl
0x14003a6ef  inc     esi
0x14003a6f1  cmp     esi, ebp
0x14003a6f3  jb      loc_14003A615
0x14003a6f9  mov     rax, [rsp+48h+arg_10]
0x14003a6fe  mov     [rax], rdi
0x14003a701  xor     edi, edi
0x14003a703  mov     rcx, cs:SecData
0x14003a70a  xor     edx, edx
0x14003a70c  add     rcx, 4D8h
0x14003a713  call    FltReleasePushLockEx_0
0x14003a718  test    rdi, rdi
0x14003a71b  jz      short loc_14003A736
0x14003a71d  mov     rbx, [rdi+10h]
0x14003a721  mov     edx, 73456353h; Tag
0x14003a726  mov     rcx, rdi; P
0x14003a729  call    SecFreePool
0x14003a72e  mov     rdi, rbx
0x14003a731  test    rbx, rbx
0x14003a734  jnz     short loc_14003A71D
0x14003a736  mov     eax, r15d
0x14003a739  jmp     short loc_14003A748
0x14003a73b  mov     r15d, 0C000009Ah
0x14003a741  jmp     short loc_14003A703
0x14003a743  mov     eax, 0C000000Dh
0x14003a748  mov     rbx, [rsp+48h+arg_0]
0x14003a74d  mov     rbp, [rsp+48h+arg_8]
0x14003a752  mov     rsi, [rsp+48h+arg_18]
0x14003a757  add     rsp, 20h
0x14003a75b  pop     r15
0x14003a75d  pop     r14
0x14003a75f  pop     r13
0x14003a761  pop     r12
0x14003a763  pop     rdi
0x14003a764  retn
```
