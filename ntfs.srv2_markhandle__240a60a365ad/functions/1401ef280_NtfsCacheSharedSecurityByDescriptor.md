# NtfsCacheSharedSecurityByDescriptor

- ea: `0x1401ef280`
- end: `0x1401ef7d5`
- name: `NtfsCacheSharedSecurityByDescriptor`
- size: `1365`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PSECURITY_DESCRIPTOR SecurityDescriptor@<rdx>, ULONG Length@<r8d>, char)`
- caller_count: `6`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003a498`
- `0x1401edd00`
- `0x1401ee360`
- `0x1401f0e08`
- `0x140264c54`
- `0x140286b3c`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140012e70`
- `0x140025a40`
- `0x140028590`
- `0x1400593c0`
- `0x140059be0`
- `0x140140380`
- `0x140189300`
- `0x1401ef280`
- `0x1401efab0`
- `0x1401f0d10`

## import_xrefs

- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef327`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef705`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef327`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ef705`
- `ntoskrnl!RtlNormalizeSecurityDescriptor` at `0x1401ef64d`
- `ntoskrnl!RtlNormalizeSecurityDescriptor` at `0x1401ef64d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef2f7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef467`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef2f7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401ef467`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef40c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef7a7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b19b4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef40c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ef7a7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b19b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef519`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef697`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef519`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ef697`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ef597`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ef597`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef2c6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef49e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef2c6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ef49e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401ef605`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401ef605`
- `ntoskrnl!ExRaiseStatus` at `0x1401ef552`
- `ntoskrnl!ExRaiseStatus` at `0x1401ef552`

## pseudocode

```c
__int64 __fastcall NtfsCacheSharedSecurityByDescriptor(
        __int64 a1,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        ULONG Length,
        char a4,
        char a5)
{
  __int64 v9; // rcx
  _DWORD *v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  char *v14; // rdi
  __int64 CachedSharedSecurityByHashUnsafe; // rsi
  __int64 v16; // rdi
  __int64 v17; // rcx
  ULONG v18; // eax
  __int64 v19; // r9
  volatile signed __int32 **v20; // rdx
  volatile signed __int32 *v21; // r8
  signed __int32 v22; // ebx
  bool v23; // cc
  signed __int32 v24; // ebx
  char *PoolWithTag; // rax
  void *v26; // r14
  __int64 v27; // r8
  size_t Size; // [rsp+30h] [rbp-68h] BYREF
  int v30; // [rsp+38h] [rbp-60h]
  unsigned int v31; // [rsp+3Ch] [rbp-5Ch]
  void *Buf2; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-50h]
  ULONG IsResourceAcquiredSharedLite; // [rsp+4Ch] [rbp-4Ch]
  __int64 v35; // [rsp+50h] [rbp-48h]
  char *v36; // [rsp+58h] [rbp-40h]
  void *v37; // [rsp+60h] [rbp-38h]
  char *v38; // [rsp+68h] [rbp-30h] BYREF

  v35 = 0;
  v9 = *(_QWORD *)(a1 + 104);
  if ( !*(_QWORD *)(v9 + 104) )
    return 0;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v9 + 664));
  v30 = 1;
  IsResourceAcquiredSharedLite = ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 48LL) + 184LL)
                                                                                       + 104LL)
                                                                           + 64LL));
  LODWORD(Size) = Length;
  Buf2 = SecurityDescriptor;
  v31 = 0;
  v36 = 0;
  if ( !Length || !SeValidSecurityDescriptor(Length, SecurityDescriptor) )
  {
    if ( a4 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225593LL, 2035551);
      NtfsRaiseStatusInternal(a1, -1073741703, 0, 0, 2035551);
      __debugbreak();
    }
    Buf2 = ::SecurityDescriptor;
    LODWORD(Size) = ::Length;
    if ( !SeValidSecurityDescriptor(::Length, ::SecurityDescriptor) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 2035561);
      NtfsRaiseStatusInternal(a1, -1073741811, 0, 0, 2035561);
      __debugbreak();
    }
  }
  v10 = Buf2;
  v37 = Buf2;
  v11 = (unsigned int)Size >> 2;
  v33 = (unsigned int)Size >> 2;
  v12 = 0;
  while ( 1 )
  {
    v13 = v11--;
    v33 = v11;
    if ( !v13 )
      break;
    v12 = *v10++ + __ROR4__(v12, 29);
    v37 = v10;
  }
  v31 = v12;
  v14 = *(char **)(*(_QWORD *)(a1 + 104) + 8LL * (v12 & 0x7F) + 3472);
  if ( v14 )
  {
    if ( *((_DWORD *)v14 + 2) == v12 )
    {
      if ( *((unsigned int *)v14 + 6) - 20LL == (unsigned int)Size )
      {
        if ( memcmp(v14 + 28, Buf2, (unsigned int)Size) )
          v14 = 0;
      }
      else
      {
        v14 = 0;
      }
    }
    else
    {
      v14 = 0;
    }
  }
  else
  {
    v14 = 0;
  }
  v36 = v14;
  if ( v14 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)v14) <= 1 )
      __fastfail(0xEu);
  }
  else
  {
    if ( (unsigned int)Size >= 0xFFFFFFE4 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 2035588);
      ExRaiseStatus(-1073741437);
    }
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned int)(Size + 28), 0x5346744Eu);
    v14 = PoolWithTag;
    v36 = PoolWithTag;
    v26 = PoolWithTag + 28;
    if ( a5 )
    {
      memmove(PoolWithTag + 28, Buf2, (unsigned int)Size);
    }
    else
    {
      v38 = PoolWithTag + 28;
      if ( (unsigned __int8)RtlNormalizeSecurityDescriptor(&Buf2, (unsigned int)Size, &v38, &Size, 0) )
      {
        v12 = NtfsHashSecurityDescriptor(v26, (unsigned int)Size);
        v31 = v12;
        CachedSharedSecurityByHashUnsafe = FindCachedSharedSecurityByHashUnsafe(*(_QWORD *)(a1 + 104), v26, v27, v12);
        if ( CachedSharedSecurityByHashUnsafe )
        {
          ExFreePoolWithTag(v14, 0);
          if ( _InterlockedIncrement((volatile signed __int32 *)CachedSharedSecurityByHashUnsafe) <= 1 )
            __fastfail(0xEu);
          goto LABEL_15;
        }
      }
    }
    *(_DWORD *)v14 = 1;
    *((_DWORD *)v14 + 1) = NtfsSecurityDescriptorFlags(v26);
    *((_DWORD *)v14 + 3) = 0;
    *((_DWORD *)v14 + 2) = v12;
    *((_QWORD *)v14 + 2) = -1;
    *((_DWORD *)v14 + 6) = Size + 20;
  }
  CachedSharedSecurityByHashUnsafe = (__int64)v14;
LABEL_15:
  v35 = CachedSharedSecurityByHashUnsafe;
  if ( !*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) )
  {
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
    v30 = 0;
    *(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) = GetSecurityIdFromSecurityDescriptorUnsafe(a1);
    NtfsCheckpointCurrentTransaction(a1);
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 104LL);
    v17 = *(_QWORD *)(v16 + 184);
    if ( *(_QWORD *)(v17 + 80) && ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v17 + 104) + 64LL)) )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v16 + 184), 0);
    v18 = ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 48LL)
                                                                            + 184LL)
                                                                + 104LL)
                                                    + 64LL));
    if ( v18 != IsResourceAcquiredSharedLite )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 48LL) + 184LL), 0);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
    v30 = 1;
    v19 = *(_QWORD *)(a1 + 104);
    v20 = (volatile signed __int32 **)(v19 + 8 * ((*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 8) & 0x7F) + 434LL));
    v21 = *v20;
    if ( (volatile signed __int32 *)CachedSharedSecurityByHashUnsafe == *v20 )
    {
      *(_QWORD *)(v19 + 8LL * (*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) & 0x7F) + 2448) = v20;
    }
    else
    {
      *v20 = (volatile signed __int32 *)CachedSharedSecurityByHashUnsafe;
      if ( _InterlockedIncrement((volatile signed __int32 *)CachedSharedSecurityByHashUnsafe) <= 1 )
        __fastfail(0xEu);
      *(_QWORD *)(v19 + 8LL * (*(_DWORD *)(CachedSharedSecurityByHashUnsafe + 12) & 0x7F) + 2448) = v20;
      if ( v21 )
      {
        v22 = _InterlockedExchangeAdd(v21, 0xFFFFFFFF);
        v23 = v22 <= 1;
        v24 = v22 - 1;
        if ( v23 )
        {
          if ( v24 )
            __fastfail(0xEu);
          ExFreePoolWithTag((PVOID)v21, 0);
        }
      }
    }
  }
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 104) + 664LL));
  return CachedSharedSecurityByHashUnsafe;
}

```

## disassembly

```asm
0x1401ef280  mov     [rsp+arg_8], rbx
0x1401ef285  mov     [rsp+arg_10], rsi
0x1401ef28a  mov     [rsp+arg_0], rcx
0x1401ef28f  push    rdi
0x1401ef290  push    r12
0x1401ef292  push    r13
0x1401ef294  push    r14
0x1401ef296  push    r15
0x1401ef298  sub     rsp, 70h
0x1401ef29c  movzx   esi, r9b
0x1401ef2a0  mov     ebx, r8d
0x1401ef2a3  mov     rdi, rdx
0x1401ef2a6  mov     r15, rcx
0x1401ef2a9  xor     r14d, r14d
0x1401ef2ac  mov     [rsp+98h+var_48], r14
0x1401ef2b1  mov     rcx, [rcx+68h]
0x1401ef2b5  cmp     [rcx+68h], r14
0x1401ef2b9  jz      loc_1401EF7D1
0x1401ef2bf  add     rcx, 298h; Mutex
0x1401ef2c6  call    cs:__imp_KeAcquireGuardedMutex
0x1401ef2cd  nop     dword ptr [rax+rax+00h]
0x1401ef2d2  mov     r13d, 1
0x1401ef2d8  mov     r12d, r13d
0x1401ef2db  mov     [rsp+98h+var_60], r13d
0x1401ef2e0  mov     rax, [r15+68h]
0x1401ef2e4  mov     rcx, [rax+30h]
0x1401ef2e8  mov     rax, [rcx+0B8h]
0x1401ef2ef  mov     rcx, [rax+68h]
0x1401ef2f3  add     rcx, 40h ; '@'; Resource
0x1401ef2f7  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401ef2fe  nop     dword ptr [rax+rax+00h]
0x1401ef303  mov     [rsp+98h+var_4C], eax
0x1401ef307  mov     dword ptr [rsp+98h+Size], ebx
0x1401ef30b  mov     [rsp+98h+Buf2], rdi
0x1401ef310  mov     [rsp+98h+var_5C], r14d
0x1401ef315  mov     [rsp+98h+var_40], r14
0x1401ef31a  test    ebx, ebx
0x1401ef31c  jz      loc_1401EF6EA
0x1401ef322  mov     rdx, rdi; SecurityDescriptor
0x1401ef325  mov     ecx, ebx; Length
0x1401ef327  call    cs:__imp_SeValidSecurityDescriptor
0x1401ef32e  nop     dword ptr [rax+rax+00h]
0x1401ef333  test    al, al
0x1401ef335  jz      loc_1401EF6EA
0x1401ef33b  mov     r9, [rsp+98h+Buf2]
0x1401ef340  mov     rdx, r9
0x1401ef343  mov     [rsp+98h+var_38], rdx
0x1401ef348  mov     esi, dword ptr [rsp+98h+Size]
0x1401ef34c  mov     ecx, esi
0x1401ef34e  shr     ecx, 2
0x1401ef351  mov     [rsp+98h+var_50], ecx
0x1401ef355  mov     ebx, r14d
0x1401ef358  nop     dword ptr [rax+rax+00000000h]
0x1401ef360  mov     eax, ecx
0x1401ef362  dec     ecx
0x1401ef364  mov     [rsp+98h+var_50], ecx
0x1401ef368  test    eax, eax
0x1401ef36a  jz      short loc_1401EF37C
0x1401ef36c  ror     ebx, 1Dh
0x1401ef36f  add     ebx, [rdx]
0x1401ef371  add     rdx, 4
0x1401ef375  mov     [rsp+98h+var_38], rdx
0x1401ef37a  jmp     short loc_1401EF360
0x1401ef37c  mov     [rsp+98h+var_5C], ebx
0x1401ef380  mov     ecx, ebx
0x1401ef382  and     ecx, 7Fh
0x1401ef385  mov     rax, [r15+68h]
0x1401ef389  mov     rdi, [rax+rcx*8+0D90h]
0x1401ef391  test    rdi, rdi
0x1401ef394  jz      loc_1401EF78F
0x1401ef39a  cmp     [rdi+8], ebx
0x1401ef39d  jnz     loc_1401EF52A
0x1401ef3a3  mov     r8, rsi; Size
0x1401ef3a6  mov     eax, [rdi+18h]
0x1401ef3a9  sub     rax, 14h
0x1401ef3ad  cmp     rax, rsi
0x1401ef3b0  jnz     loc_1401EF532
0x1401ef3b6  lea     rcx, [rdi+1Ch]; Buf1
0x1401ef3ba  mov     rdx, r9; Buf2
0x1401ef3bd  call    memcmp
0x1401ef3c2  test    eax, eax
0x1401ef3c4  cmovnz  rdi, r14
0x1401ef3c8  mov     [rsp+98h+var_40], rdi
0x1401ef3cd  test    rdi, rdi
0x1401ef3d0  jz      loc_1401EF53A
0x1401ef3d6  mov     eax, r13d
0x1401ef3d9  lock xadd [rdi], eax
0x1401ef3dd  inc     eax
0x1401ef3df  cmp     eax, 1
0x1401ef3e2  jle     loc_1401EF6BD
0x1401ef3e8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1401ef3ef  mov     rsi, rdi
0x1401ef3f2  mov     [rsp+98h+var_48], rsi
0x1401ef3f7  cmp     dword ptr [rsi+0Ch], 0
0x1401ef3fb  jnz     loc_1401EF797
0x1401ef401  mov     rcx, [r15+68h]
0x1401ef405  add     rcx, 298h; Mutex
0x1401ef40c  call    cs:__imp_KeReleaseGuardedMutex
0x1401ef413  nop     dword ptr [rax+rax+00h]
0x1401ef418  mov     [rsp+98h+var_60], 0
0x1401ef420  mov     rdx, rsi
0x1401ef423  mov     rcx, r15; int
0x1401ef426  call    GetSecurityIdFromSecurityDescriptorUnsafe
0x1401ef42b  mov     [rsi+0Ch], eax
0x1401ef42e  mov     rcx, r15
0x1401ef431  call    NtfsCheckpointCurrentTransaction
0x1401ef436  mov     rax, [r15+68h]
0x1401ef43a  mov     rdi, [rax+68h]
0x1401ef43e  mov     rcx, [rdi+0B8h]
0x1401ef445  cmp     qword ptr [rcx+50h], 0
0x1401ef44a  jnz     loc_1401EF5FD
0x1401ef450  mov     rax, [r15+68h]
0x1401ef454  mov     rcx, [rax+30h]
0x1401ef458  mov     rax, [rcx+0B8h]
0x1401ef45f  mov     rcx, [rax+68h]
0x1401ef463  add     rcx, 40h ; '@'; Resource
0x1401ef467  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401ef46e  nop     dword ptr [rax+rax+00h]
0x1401ef473  cmp     eax, [rsp+98h+var_4C]
0x1401ef477  jz      short loc_1401EF493
0x1401ef479  mov     rax, [r15+68h]
0x1401ef47d  mov     rdx, [rax+30h]
0x1401ef481  xor     r8d, r8d
0x1401ef484  mov     rdx, [rdx+0B8h]
0x1401ef48b  mov     rcx, r15
0x1401ef48e  call    NtfsReleaseFcbEx
0x1401ef493  mov     rcx, [r15+68h]
0x1401ef497  add     rcx, 298h; Mutex
0x1401ef49e  call    cs:__imp_KeAcquireGuardedMutex
0x1401ef4a5  nop     dword ptr [rax+rax+00h]
0x1401ef4aa  mov     r12d, r13d
0x1401ef4ad  mov     [rsp+98h+var_60], r13d
0x1401ef4b2  mov     r9, [r15+68h]
0x1401ef4b6  mov     edx, [rsi+8]
0x1401ef4b9  and     edx, 7Fh
0x1401ef4bc  add     rdx, 1B2h
0x1401ef4c3  lea     rdx, [r9+rdx*8]
0x1401ef4c7  mov     r8, [rdx]
0x1401ef4ca  cmp     rsi, r8
0x1401ef4cd  jz      loc_1401EF573
0x1401ef4d3  mov     [rdx], rsi
0x1401ef4d6  lock xadd [rsi], r13d
0x1401ef4db  inc     r13d
0x1401ef4de  cmp     r13d, r12d
0x1401ef4e1  jle     loc_1401EF6C9
0x1401ef4e7  mov     eax, [rsi+0Ch]
0x1401ef4ea  and     eax, 7Fh
0x1401ef4ed  mov     [r9+rax*8+990h], rdx
0x1401ef4f5  test    r8, r8
0x1401ef4f8  jz      loc_1401EF797
0x1401ef4fe  lock xadd [r8], ebx
0x1401ef503  sub     ebx, r12d
0x1401ef506  jg      loc_1401EF797
0x1401ef50c  test    ebx, ebx
0x1401ef50e  jnz     loc_1401EF6DE
0x1401ef514  xor     edx, edx; Tag
0x1401ef516  mov     rcx, r8; P
0x1401ef519  call    cs:__imp_ExFreePoolWithTag
0x1401ef520  nop     dword ptr [rax+rax+00h]
0x1401ef525  jmp     loc_1401EF797
0x1401ef52a  mov     rdi, r14
0x1401ef52d  jmp     loc_1401EF3C8
0x1401ef532  mov     rdi, r14
0x1401ef535  jmp     loc_1401EF3C8
0x1401ef53a  lea     eax, [rsi+1Ch]
0x1401ef53d  cmp     eax, 1Ch
0x1401ef540  jnb     short loc_1401EF586
0x1401ef542  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ef549  test    al, al
0x1401ef54b  jnz     short loc_1401EF55F
0x1401ef54d  mov     ecx, 0C0000183h; Status
0x1401ef552  call    cs:__imp_ExRaiseStatus
0x1401ef55f  mov     edx, 0C0000183h
0x1401ef564  xor     ecx, ecx
0x1401ef566  mov     r8d, 1F0F84h
0x1401ef56c  call    NtfsStatusTraceAndDebugInternal
0x1401ef571  jmp     short loc_1401EF54D
0x1401ef573  mov     eax, [rsi+0Ch]
0x1401ef576  and     eax, 7Fh
0x1401ef579  mov     [r9+rax*8+990h], rdx
0x1401ef581  jmp     loc_1401EF797
0x1401ef586  mov     edx, eax; NumberOfBytes
0x1401ef588  mov     ecx, cs:PoolType
0x1401ef58e  or      ecx, 10h; PoolType
0x1401ef591  mov     r8d, 5346744Eh; Tag
0x1401ef597  call    cs:__imp_ExAllocatePoolWithTag
0x1401ef59e  nop     dword ptr [rax+rax+00h]
0x1401ef5a3  mov     rdi, rax
0x1401ef5a6  mov     [rsp+98h+var_40], rax
0x1401ef5ab  lea     r14, [rax+1Ch]
0x1401ef5af  cmp     [rsp+98h+arg_20], 0
0x1401ef5b7  jz      short loc_1401EF630
0x1401ef5b9  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x1401ef5be  mov     rdx, [rsp+98h+Buf2]; Src
0x1401ef5c3  mov     rcx, r14; void *
0x1401ef5c6  call    memmove
0x1401ef5cb  mov     [rdi], r13d
0x1401ef5ce  mov     rcx, r14; SecurityDescriptor
0x1401ef5d1  call    NtfsSecurityDescriptorFlags
0x1401ef5d6  mov     [rdi+4], eax
0x1401ef5d9  mov     dword ptr [rdi+0Ch], 0
0x1401ef5e0  mov     [rdi+8], ebx
0x1401ef5e3  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1401ef5ea  mov     [rdi+10h], rbx
0x1401ef5ee  mov     eax, dword ptr [rsp+98h+Size]
0x1401ef5f2  add     eax, 14h
0x1401ef5f5  mov     [rdi+18h], eax
0x1401ef5f8  jmp     loc_1401EF3EF
0x1401ef5fd  mov     rcx, [rcx+68h]
0x1401ef601  add     rcx, 40h ; '@'; Resource
0x1401ef605  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1401ef60c  nop     dword ptr [rax+rax+00h]
0x1401ef611  test    al, al
0x1401ef613  jz      loc_1401EF450
0x1401ef619  xor     r8d, r8d
0x1401ef61c  mov     rdx, [rdi+0B8h]
0x1401ef623  mov     rcx, r15
0x1401ef626  call    NtfsReleaseFcbEx
0x1401ef62b  jmp     loc_1401EF450
0x1401ef630  mov     [rsp+98h+var_30], r14
0x1401ef635  mov     byte ptr [rsp+98h+var_78], 0
0x1401ef63a  lea     r9, [rsp+98h+Size]
0x1401ef63f  lea     r8, [rsp+98h+var_30]
0x1401ef644  mov     edx, dword ptr [rsp+98h+Size]
0x1401ef648  lea     rcx, [rsp+98h+Buf2]
0x1401ef64d  call    cs:__imp_RtlNormalizeSecurityDescriptor
0x1401ef654  nop     dword ptr [rax+rax+00h]
0x1401ef659  test    al, al
0x1401ef65b  jz      loc_1401EF5CB
0x1401ef661  mov     r8d, dword ptr [rsp+98h+Size]
0x1401ef666  mov     edx, r8d
0x1401ef669  mov     rcx, r14
0x1401ef66c  call    NtfsHashSecurityDescriptor
0x1401ef671  mov     ebx, eax
0x1401ef673  mov     [rsp+98h+var_5C], eax
0x1401ef677  mov     r9d, eax
0x1401ef67a  mov     rdx, r14
0x1401ef67d  mov     rcx, [r15+68h]
0x1401ef681  call    FindCachedSharedSecurityByHashUnsafe
0x1401ef686  mov     rsi, rax
0x1401ef689  test    rax, rax
0x1401ef68c  jz      loc_1401EF5CB
0x1401ef692  xor     edx, edx; Tag
0x1401ef694  mov     rcx, rdi; P
0x1401ef697  call    cs:__imp_ExFreePoolWithTag
0x1401ef69e  nop     dword ptr [rax+rax+00h]
0x1401ef6a3  mov     eax, r13d
0x1401ef6a6  lock xadd [rsi], eax
0x1401ef6aa  inc     eax
0x1401ef6ac  cmp     eax, 1
0x1401ef6af  jle     short loc_1401EF6D5
0x1401ef6b1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1401ef6b8  jmp     loc_1401EF3F2
0x1401ef6bd  mov     ecx, 0Eh
0x1401ef6c2  int     29h; Win8: RtlFailFast(ecx)
0x1401ef6c4  jmp     loc_1401EF3E8
0x1401ef6c9  mov     ecx, 0Eh
0x1401ef6ce  int     29h; Win8: RtlFailFast(ecx)
0x1401ef6d0  jmp     loc_1401EF4E7
0x1401ef6d5  mov     ecx, 0Eh
0x1401ef6da  int     29h; Win8: RtlFailFast(ecx)
0x1401ef6dc  jmp     short loc_1401EF6B1
0x1401ef6de  mov     ecx, 0Eh
0x1401ef6e3  int     29h; Win8: RtlFailFast(ecx)
0x1401ef6e5  jmp     loc_1401EF797
0x1401ef6ea  test    sil, sil
0x1401ef6ed  jnz     short loc_1401EF754
0x1401ef6ef  mov     rdx, cs:SecurityDescriptor; SecurityDescriptor
0x1401ef6f6  mov     [rsp+98h+Buf2], rdx
0x1401ef6fb  mov     ecx, cs:Length; Length
0x1401ef701  mov     dword ptr [rsp+98h+Size], ecx
0x1401ef705  call    cs:__imp_SeValidSecurityDescriptor
0x1401ef70c  nop     dword ptr [rax+rax+00h]
0x1401ef711  test    al, al
0x1401ef713  jnz     loc_1401EF33B
0x1401ef719  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ef720  test    al, al
0x1401ef722  jz      short loc_1401EF737
0x1401ef724  mov     edx, 0C000000Dh
0x1401ef729  mov     r8d, 1F0F69h
0x1401ef72f  mov     rcx, r15
0x1401ef732  call    NtfsStatusTraceAndDebugInternal
0x1401ef737  mov     [rsp+98h+var_78], 1F0F69h
0x1401ef740  xor     r9d, r9d
0x1401ef743  xor     r8d, r8d
0x1401ef746  mov     edx, 0C000000Dh
0x1401ef74b  mov     rcx, r15
0x1401ef74e  call    NtfsRaiseStatusInternal
0x1401ef753  int     3; Trap to Debugger
0x1401ef754  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ef75b  test    al, al
0x1401ef75d  jz      short loc_1401EF772
0x1401ef75f  mov     edx, 0C0000079h
0x1401ef764  mov     r8d, 1F0F5Fh
0x1401ef76a  mov     rcx, r15
0x1401ef76d  call    NtfsStatusTraceAndDebugInternal
0x1401ef772  mov     [rsp+98h+var_78], 1F0F5Fh
0x1401ef77b  xor     r9d, r9d
0x1401ef77e  xor     r8d, r8d
0x1401ef781  mov     edx, 0C0000079h
  ... truncated ...
```
