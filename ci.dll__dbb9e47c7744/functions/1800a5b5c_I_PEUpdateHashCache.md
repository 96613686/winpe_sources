# I_PEUpdateHashCache

- ea: `0x1800a5b5c`
- end: `0x1800a5da8`
- name: `I_PEUpdateHashCache`
- size: `588`
- prototype: `__int64 __usercall@<rax>(void *Source2@<rcx>, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007f664`
- `0x18009a1d0`
- `0x1800a5320`

## callees

- `0x1800a5b5c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5b84`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a5b84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a5d08`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a5d08`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800a5bcd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800a5bcd`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5c09`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5cb1`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5c09`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5cb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5d3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5d3d`
- `ntoskrnl!RtlCompareMemory` at `0x1800a5c6f`
- `ntoskrnl!RtlCompareMemory` at `0x1800a5c6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800a5b99`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800a5b99`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5d31`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5d31`

## pseudocode

```c
void __fastcall I_PEUpdateHashCache(_DWORD *Source2, __int64 a2, const UNICODE_STRING *a3, int a4, int a5, int a6)
{
  __int64 Pool2; // rsi
  int *v7; // rbp
  __int64 *v12; // r14
  HANDLE CurrentProcessId; // rax
  char *v14; // rcx
  HANDLE v15; // rbx
  char *v16; // rax
  __int64 i; // rbx
  int v18; // [rsp+20h] [rbp-58h] BYREF

  Pool2 = 0;
  v7 = &v18;
  v18 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&g_HashCacheLock, 1u);
  if ( a5 )
  {
    v12 = &g_KernelHashBucketList;
LABEL_17:
    if ( a4 )
      ++g_ulPEFailedComponentsCount;
    if ( Pool2 || (Pool2 = ExAllocatePool2(258, a3->Length + 82LL, 1430340944)) != 0 )
    {
      *(_OWORD *)(Pool2 + 24) = *(_OWORD *)Source2;
      *(_DWORD *)(Pool2 + 40) = Source2[4];
      *(_OWORD *)(Pool2 + 44) = *(_OWORD *)a2;
      *(_DWORD *)(Pool2 + 60) = *(_DWORD *)(a2 + 16);
      *(_WORD *)(Pool2 + 10) = a3->Length + 2;
      *(_WORD *)(Pool2 + 8) = a3->Length;
      *(_QWORD *)(Pool2 + 16) = Pool2 + 72;
      RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 8), a3);
      *(_DWORD *)(Pool2 + 64) = a4;
      *(_DWORD *)(Pool2 + 68) = 0;
      *(_QWORD *)Pool2 = *v12;
      *v12 = Pool2;
      ++*v7;
    }
    goto LABEL_22;
  }
  if ( a6 == 1 )
  {
    v12 = &g_PEProcessList;
LABEL_12:
    for ( i = *v12; i; i = *(_QWORD *)i )
    {
      if ( RtlCompareMemory((const void *)(i + 24), Source2, 0x14u) == 20 )
      {
        if ( a4 && !*(_DWORD *)(i + 64) )
          ++g_ulPEFailedComponentsCount;
        *(_DWORD *)(i + 64) = a4;
        *(_DWORD *)(i + 68) = 0;
        goto LABEL_22;
      }
    }
    goto LABEL_17;
  }
  v12 = 0;
  if ( a6 )
    goto LABEL_12;
  CurrentProcessId = PsGetCurrentProcessId();
  v14 = (char *)g_PEProcessHashBucketList;
  v15 = CurrentProcessId;
  while ( v14 )
  {
    if ( CurrentProcessId == *((HANDLE *)v14 + 1) )
      goto LABEL_10;
    v14 = *(char **)v14;
  }
  v16 = (char *)ExAllocatePool2(256, a3->Length + 138LL, 1430340944);
  v14 = v16;
  if ( v16 )
  {
    *((_QWORD *)v16 + 1) = v15;
    Pool2 = (__int64)(v16 + 56);
    *((_DWORD *)v16 + 10) = 1;
    *((_DWORD *)v16 + 11) = dword_180049408;
    *(_QWORD *)v16 = g_PEProcessHashBucketList;
    g_PEProcessHashBucketList = v16;
LABEL_10:
    v12 = (__int64 *)(v14 + 24);
    v7 = (int *)(v14 + 32);
    if ( a4 )
      *((_DWORD *)v14 + 4) = 1;
    goto LABEL_12;
  }
  if ( a4 )
    ++g_ulPEFailedComponentsCount;
LABEL_22:
  ExReleaseResourceLite(&g_HashCacheLock);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1800a5b5c  push    rbx
0x1800a5b5e  push    rbp
0x1800a5b5f  push    rsi
0x1800a5b60  push    rdi
0x1800a5b61  push    r12
0x1800a5b63  push    r13
0x1800a5b65  push    r14
0x1800a5b67  push    r15
0x1800a5b69  sub     rsp, 38h
0x1800a5b6d  xor     esi, esi
0x1800a5b6f  lea     rbp, [rsp+78h+var_58]
0x1800a5b74  mov     [rsp+78h+var_58], esi
0x1800a5b78  mov     edi, r9d
0x1800a5b7b  mov     r15, r8
0x1800a5b7e  mov     r12, rdx
0x1800a5b81  mov     r13, rcx
0x1800a5b84  call    cs:__imp_KeEnterCriticalRegion
0x1800a5b8b  nop     dword ptr [rax+rax+00h]
0x1800a5b90  mov     dl, 1; Wait
0x1800a5b92  lea     rcx, g_HashCacheLock; Resource
0x1800a5b99  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800a5ba0  nop     dword ptr [rax+rax+00h]
0x1800a5ba5  cmp     [rsp+78h+arg_20], esi
0x1800a5bac  jnz     loc_1800A5C8A
0x1800a5bb2  mov     eax, [rsp+78h+arg_28]
0x1800a5bb9  cmp     eax, 1
0x1800a5bbc  jz      loc_1800A5D6B
0x1800a5bc2  xor     r14d, r14d
0x1800a5bc5  test    eax, eax
0x1800a5bc7  jnz     loc_1800A5C5A
0x1800a5bcd  call    cs:__imp_PsGetCurrentProcessId
0x1800a5bd4  nop     dword ptr [rax+rax+00h]
0x1800a5bd9  mov     rcx, cs:g_PEProcessHashBucketList
0x1800a5be0  mov     rbx, rax
0x1800a5be3  jmp     short loc_1800A5BEE
0x1800a5be5  cmp     rbx, [rcx+8]
0x1800a5be9  jz      short loc_1800A5C4A
0x1800a5beb  mov     rcx, [rcx]
0x1800a5bee  test    rcx, rcx
0x1800a5bf1  jnz     short loc_1800A5BE5
0x1800a5bf3  movzx   edx, word ptr [r15]
0x1800a5bf7  mov     ecx, 100h
0x1800a5bfc  add     rdx, 8Ah
0x1800a5c03  mov     r8d, 55414550h
0x1800a5c09  call    cs:__imp_ExAllocatePool2
0x1800a5c10  nop     dword ptr [rax+rax+00h]
0x1800a5c15  mov     rcx, rax
0x1800a5c18  test    rax, rax
0x1800a5c1b  jz      loc_1800A5D77
0x1800a5c21  mov     [rax+8], rbx
0x1800a5c25  lea     rsi, [rcx+38h]
0x1800a5c29  mov     dword ptr [rax+28h], 1
0x1800a5c30  mov     eax, cs:dword_180049408
0x1800a5c36  mov     [rcx+2Ch], eax
0x1800a5c39  mov     rax, cs:g_PEProcessHashBucketList
0x1800a5c40  mov     [rcx], rax
0x1800a5c43  mov     cs:g_PEProcessHashBucketList, rcx
0x1800a5c4a  lea     r14, [rcx+18h]
0x1800a5c4e  lea     rbp, [rcx+20h]
0x1800a5c52  test    edi, edi
0x1800a5c54  jnz     loc_1800A5D83
0x1800a5c5a  mov     rbx, [r14]
0x1800a5c5d  test    rbx, rbx
0x1800a5c60  jz      short loc_1800A5C91
0x1800a5c62  lea     rcx, [rbx+18h]; Source1
0x1800a5c66  mov     r8d, 14h; Length
0x1800a5c6c  mov     rdx, r13; Source2
0x1800a5c6f  call    cs:__imp_RtlCompareMemory
0x1800a5c76  nop     dword ptr [rax+rax+00h]
0x1800a5c7b  cmp     rax, 14h
0x1800a5c7f  jz      loc_1800A5D5B
0x1800a5c85  mov     rbx, [rbx]
0x1800a5c88  jmp     short loc_1800A5C5D
0x1800a5c8a  lea     r14, g_KernelHashBucketList
0x1800a5c91  test    edi, edi
0x1800a5c93  jnz     loc_1800A5D9D
0x1800a5c99  test    rsi, rsi
0x1800a5c9c  jnz     short loc_1800A5CC5
0x1800a5c9e  movzx   edx, word ptr [r15]
0x1800a5ca2  mov     ecx, 102h
0x1800a5ca7  add     rdx, 52h ; 'R'
0x1800a5cab  mov     r8d, 55414550h
0x1800a5cb1  call    cs:__imp_ExAllocatePool2
0x1800a5cb8  nop     dword ptr [rax+rax+00h]
0x1800a5cbd  mov     rsi, rax
0x1800a5cc0  test    rax, rax
0x1800a5cc3  jz      short loc_1800A5D2A
0x1800a5cc5  movups  xmm0, xmmword ptr [r13+0]
0x1800a5cca  mov     rdx, r15; SourceString
0x1800a5ccd  movups  xmmword ptr [rsi+18h], xmm0
0x1800a5cd1  mov     ecx, [r13+10h]
0x1800a5cd5  mov     [rsi+28h], ecx
0x1800a5cd8  lea     rcx, [rsi+8]; DestinationString
0x1800a5cdc  movups  xmm0, xmmword ptr [r12]
0x1800a5ce1  movups  xmmword ptr [rsi+2Ch], xmm0
0x1800a5ce5  mov     eax, [r12+10h]
0x1800a5cea  mov     [rsi+3Ch], eax
0x1800a5ced  movzx   eax, word ptr [r15]
0x1800a5cf1  add     ax, 2
0x1800a5cf5  mov     [rsi+0Ah], ax
0x1800a5cf9  movzx   eax, word ptr [r15]
0x1800a5cfd  mov     [rcx], ax
0x1800a5d00  lea     rax, [rsi+48h]
0x1800a5d04  mov     [rsi+10h], rax
0x1800a5d08  call    cs:__imp_RtlCopyUnicodeString
0x1800a5d0f  nop     dword ptr [rax+rax+00h]
0x1800a5d14  mov     [rsi+40h], edi
0x1800a5d17  mov     dword ptr [rsi+44h], 0
0x1800a5d1e  mov     rax, [r14]
0x1800a5d21  mov     [rsi], rax
0x1800a5d24  mov     [r14], rsi
0x1800a5d27  inc     dword ptr [rbp+0]
0x1800a5d2a  lea     rcx, g_HashCacheLock; Resource
0x1800a5d31  call    cs:__imp_ExReleaseResourceLite
0x1800a5d38  nop     dword ptr [rax+rax+00h]
0x1800a5d3d  call    cs:__imp_KeLeaveCriticalRegion
0x1800a5d44  nop     dword ptr [rax+rax+00h]
0x1800a5d49  add     rsp, 38h
0x1800a5d4d  pop     r15
0x1800a5d4f  pop     r14
0x1800a5d51  pop     r13
0x1800a5d53  pop     r12
0x1800a5d55  pop     rdi
0x1800a5d56  pop     rsi
0x1800a5d57  pop     rbp
0x1800a5d58  pop     rbx
0x1800a5d59  retn
0x1800a5d5b  test    edi, edi
0x1800a5d5d  jnz     short loc_1800A5D8F
0x1800a5d5f  mov     [rbx+40h], edi
0x1800a5d62  mov     dword ptr [rbx+44h], 0
0x1800a5d69  jmp     short loc_1800A5D2A
0x1800a5d6b  lea     r14, g_PEProcessList
0x1800a5d72  jmp     loc_1800A5C5A
0x1800a5d77  test    edi, edi
0x1800a5d79  jz      short loc_1800A5D2A
0x1800a5d7b  inc     cs:g_ulPEFailedComponentsCount
0x1800a5d81  jmp     short loc_1800A5D2A
0x1800a5d83  mov     dword ptr [rcx+10h], 1
0x1800a5d8a  jmp     loc_1800A5C5A
0x1800a5d8f  cmp     dword ptr [rbx+40h], 0
0x1800a5d93  jnz     short loc_1800A5D5F
0x1800a5d95  inc     cs:g_ulPEFailedComponentsCount
0x1800a5d9b  jmp     short loc_1800A5D5F
0x1800a5d9d  inc     cs:g_ulPEFailedComponentsCount
0x1800a5da3  jmp     loc_1800A5C99
```
