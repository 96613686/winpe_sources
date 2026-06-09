# I_PEUpdateHashCache

- ea: `0x1800a452c`
- end: `0x1800a4778`
- name: `I_PEUpdateHashCache`
- size: `588`
- prototype: `__int64 __usercall@<rax>(void *Source2@<rcx>, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007e038`
- `0x180098ba0`
- `0x1800a3cf0`

## callees

- `0x1800a452c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a4554`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a4554`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a46d8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a46d8`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800a459d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800a459d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a45d9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a4681`
- `ntoskrnl!ExAllocatePool2` at `0x1800a45d9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a4681`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a470d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a470d`
- `ntoskrnl!RtlCompareMemory` at `0x1800a463f`
- `ntoskrnl!RtlCompareMemory` at `0x1800a463f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800a4569`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800a4569`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a4701`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a4701`

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
    *((_DWORD *)v16 + 11) = dword_180048408;
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
0x1800a452c  push    rbx
0x1800a452e  push    rbp
0x1800a452f  push    rsi
0x1800a4530  push    rdi
0x1800a4531  push    r12
0x1800a4533  push    r13
0x1800a4535  push    r14
0x1800a4537  push    r15
0x1800a4539  sub     rsp, 38h
0x1800a453d  xor     esi, esi
0x1800a453f  lea     rbp, [rsp+78h+var_58]
0x1800a4544  mov     [rsp+78h+var_58], esi
0x1800a4548  mov     edi, r9d
0x1800a454b  mov     r15, r8
0x1800a454e  mov     r12, rdx
0x1800a4551  mov     r13, rcx
0x1800a4554  call    cs:__imp_KeEnterCriticalRegion
0x1800a455b  nop     dword ptr [rax+rax+00h]
0x1800a4560  mov     dl, 1; Wait
0x1800a4562  lea     rcx, g_HashCacheLock; Resource
0x1800a4569  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800a4570  nop     dword ptr [rax+rax+00h]
0x1800a4575  cmp     [rsp+78h+arg_20], esi
0x1800a457c  jnz     loc_1800A465A
0x1800a4582  mov     eax, [rsp+78h+arg_28]
0x1800a4589  cmp     eax, 1
0x1800a458c  jz      loc_1800A473B
0x1800a4592  xor     r14d, r14d
0x1800a4595  test    eax, eax
0x1800a4597  jnz     loc_1800A462A
0x1800a459d  call    cs:__imp_PsGetCurrentProcessId
0x1800a45a4  nop     dword ptr [rax+rax+00h]
0x1800a45a9  mov     rcx, cs:g_PEProcessHashBucketList
0x1800a45b0  mov     rbx, rax
0x1800a45b3  jmp     short loc_1800A45BE
0x1800a45b5  cmp     rbx, [rcx+8]
0x1800a45b9  jz      short loc_1800A461A
0x1800a45bb  mov     rcx, [rcx]
0x1800a45be  test    rcx, rcx
0x1800a45c1  jnz     short loc_1800A45B5
0x1800a45c3  movzx   edx, word ptr [r15]
0x1800a45c7  mov     ecx, 100h
0x1800a45cc  add     rdx, 8Ah
0x1800a45d3  mov     r8d, 55414550h
0x1800a45d9  call    cs:__imp_ExAllocatePool2
0x1800a45e0  nop     dword ptr [rax+rax+00h]
0x1800a45e5  mov     rcx, rax
0x1800a45e8  test    rax, rax
0x1800a45eb  jz      loc_1800A4747
0x1800a45f1  mov     [rax+8], rbx
0x1800a45f5  lea     rsi, [rcx+38h]
0x1800a45f9  mov     dword ptr [rax+28h], 1
0x1800a4600  mov     eax, cs:dword_180048408
0x1800a4606  mov     [rcx+2Ch], eax
0x1800a4609  mov     rax, cs:g_PEProcessHashBucketList
0x1800a4610  mov     [rcx], rax
0x1800a4613  mov     cs:g_PEProcessHashBucketList, rcx
0x1800a461a  lea     r14, [rcx+18h]
0x1800a461e  lea     rbp, [rcx+20h]
0x1800a4622  test    edi, edi
0x1800a4624  jnz     loc_1800A4753
0x1800a462a  mov     rbx, [r14]
0x1800a462d  test    rbx, rbx
0x1800a4630  jz      short loc_1800A4661
0x1800a4632  lea     rcx, [rbx+18h]; Source1
0x1800a4636  mov     r8d, 14h; Length
0x1800a463c  mov     rdx, r13; Source2
0x1800a463f  call    cs:__imp_RtlCompareMemory
0x1800a4646  nop     dword ptr [rax+rax+00h]
0x1800a464b  cmp     rax, 14h
0x1800a464f  jz      loc_1800A472B
0x1800a4655  mov     rbx, [rbx]
0x1800a4658  jmp     short loc_1800A462D
0x1800a465a  lea     r14, g_KernelHashBucketList
0x1800a4661  test    edi, edi
0x1800a4663  jnz     loc_1800A476D
0x1800a4669  test    rsi, rsi
0x1800a466c  jnz     short loc_1800A4695
0x1800a466e  movzx   edx, word ptr [r15]
0x1800a4672  mov     ecx, 102h
0x1800a4677  add     rdx, 52h ; 'R'
0x1800a467b  mov     r8d, 55414550h
0x1800a4681  call    cs:__imp_ExAllocatePool2
0x1800a4688  nop     dword ptr [rax+rax+00h]
0x1800a468d  mov     rsi, rax
0x1800a4690  test    rax, rax
0x1800a4693  jz      short loc_1800A46FA
0x1800a4695  movups  xmm0, xmmword ptr [r13+0]
0x1800a469a  mov     rdx, r15; SourceString
0x1800a469d  movups  xmmword ptr [rsi+18h], xmm0
0x1800a46a1  mov     ecx, [r13+10h]
0x1800a46a5  mov     [rsi+28h], ecx
0x1800a46a8  lea     rcx, [rsi+8]; DestinationString
0x1800a46ac  movups  xmm0, xmmword ptr [r12]
0x1800a46b1  movups  xmmword ptr [rsi+2Ch], xmm0
0x1800a46b5  mov     eax, [r12+10h]
0x1800a46ba  mov     [rsi+3Ch], eax
0x1800a46bd  movzx   eax, word ptr [r15]
0x1800a46c1  add     ax, 2
0x1800a46c5  mov     [rsi+0Ah], ax
0x1800a46c9  movzx   eax, word ptr [r15]
0x1800a46cd  mov     [rcx], ax
0x1800a46d0  lea     rax, [rsi+48h]
0x1800a46d4  mov     [rsi+10h], rax
0x1800a46d8  call    cs:__imp_RtlCopyUnicodeString
0x1800a46df  nop     dword ptr [rax+rax+00h]
0x1800a46e4  mov     [rsi+40h], edi
0x1800a46e7  mov     dword ptr [rsi+44h], 0
0x1800a46ee  mov     rax, [r14]
0x1800a46f1  mov     [rsi], rax
0x1800a46f4  mov     [r14], rsi
0x1800a46f7  inc     dword ptr [rbp+0]
0x1800a46fa  lea     rcx, g_HashCacheLock; Resource
0x1800a4701  call    cs:__imp_ExReleaseResourceLite
0x1800a4708  nop     dword ptr [rax+rax+00h]
0x1800a470d  call    cs:__imp_KeLeaveCriticalRegion
0x1800a4714  nop     dword ptr [rax+rax+00h]
0x1800a4719  add     rsp, 38h
0x1800a471d  pop     r15
0x1800a471f  pop     r14
0x1800a4721  pop     r13
0x1800a4723  pop     r12
0x1800a4725  pop     rdi
0x1800a4726  pop     rsi
0x1800a4727  pop     rbp
0x1800a4728  pop     rbx
0x1800a4729  retn
0x1800a472b  test    edi, edi
0x1800a472d  jnz     short loc_1800A475F
0x1800a472f  mov     [rbx+40h], edi
0x1800a4732  mov     dword ptr [rbx+44h], 0
0x1800a4739  jmp     short loc_1800A46FA
0x1800a473b  lea     r14, g_PEProcessList
0x1800a4742  jmp     loc_1800A462A
0x1800a4747  test    edi, edi
0x1800a4749  jz      short loc_1800A46FA
0x1800a474b  inc     cs:g_ulPEFailedComponentsCount
0x1800a4751  jmp     short loc_1800A46FA
0x1800a4753  mov     dword ptr [rcx+10h], 1
0x1800a475a  jmp     loc_1800A462A
0x1800a475f  cmp     dword ptr [rbx+40h], 0
0x1800a4763  jnz     short loc_1800A472F
0x1800a4765  inc     cs:g_ulPEFailedComponentsCount
0x1800a476b  jmp     short loc_1800A472F
0x1800a476d  inc     cs:g_ulPEFailedComponentsCount
0x1800a4773  jmp     loc_1800A4669
```
