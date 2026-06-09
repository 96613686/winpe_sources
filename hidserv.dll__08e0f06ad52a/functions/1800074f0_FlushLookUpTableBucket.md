# FlushLookUpTableBucket

- ea: `0x1800074f0`
- end: `0x18000760c`
- name: `FlushLookUpTableBucket`
- size: `284`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007988`
- `0x180007d6c`

## callees

- `0x1800074f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007516`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007516`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000757e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000757e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075f6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800075db`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800075db`

## pseudocode

```c
__int64 __fastcall FlushLookUpTableBucket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  RTL_SRWLOCK *v5; // rbp
  __int64 v6; // rdi
  unsigned int v7; // esi
  __int64 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 *v12; // rdx
  REGHANDLE v13; // rbp
  PEVENT_DATA_DESCRIPTOR *v14; // rbx
  int v15; // edx
  __int64 v16; // rcx
  PEVENT_DATA_DESCRIPTOR v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8LL * a2) )
    return 0;
  v5 = (RTL_SRWLOCK *)(a1 + 264);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
  v6 = *(_QWORD *)(a1 + 8 * v2);
  *(_QWORD *)(a1 + 8 * v2) = 0;
  v7 = 0;
  v19 = v6;
  if ( v6 )
  {
    v8 = &v19;
    v9 = v6;
    do
    {
      v10 = *(_QWORD *)(v9 + 32);
      *(_QWORD *)(v9 + 32) = 0;
      v8 = (__int64 *)(*v8 + 24);
      v11 = *v8;
      if ( *v8 )
      {
        do
        {
          v12 = (__int64 *)(v11 + 32);
          v11 = *(_QWORD *)(v11 + 32);
        }
        while ( v11 );
      }
      else
      {
        v12 = v8;
      }
      *v12 = v10;
      ++v7;
      v9 = *v8;
    }
    while ( *v8 );
  }
  *(_DWORD *)(a1 + 256) -= v7;
  ReleaseSRWLockExclusive(v5);
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 328) + 32LL);
  while ( v6 )
  {
    v14 = (PEVENT_DATA_DESCRIPTOR *)(v6 + 16);
    v15 = 2;
    if ( (unsigned int)*(unsigned __int8 *)(v6 + 45) + 2 > 2 )
    {
      do
      {
        v16 = v15++;
        (*v14)[v16].Reserved1 = 0;
      }
      while ( v15 < *(unsigned __int8 *)(v6 + 45) + 2 );
    }
    EventWriteTransfer(v13, (PCEVENT_DESCRIPTOR)v6, 0, 0, *(unsigned __int8 *)(v6 + 44), *v14);
    v6 = *(_QWORD *)(v6 + 24);
    v17 = *v14;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
  return v7;
}

```

## disassembly

```asm
0x1800074f0  push    rbx
0x1800074f2  push    rbp
0x1800074f3  push    rsi
0x1800074f4  push    rdi
0x1800074f5  sub     rsp, 38h
0x1800074f9  mov     esi, edx
0x1800074fb  mov     rbx, rcx
0x1800074fe  cmp     qword ptr [rcx+rsi*8], 0
0x180007503  jnz     short loc_18000750C
0x180007505  xor     eax, eax
0x180007507  jmp     loc_180007603
0x18000750c  lea     rbp, [rcx+108h]
0x180007513  mov     rcx, rbp; SRWLock
0x180007516  call    cs:__imp_AcquireSRWLockExclusive
0x18000751c  mov     rdi, [rbx+rsi*8]
0x180007520  mov     qword ptr [rbx+rsi*8], 0
0x180007528  xor     esi, esi
0x18000752a  mov     [rsp+58h+arg_0], rdi
0x18000752f  test    rdi, rdi
0x180007532  jz      short loc_180007575
0x180007534  lea     rax, [rsp+58h+arg_0]
0x180007539  mov     rcx, rdi
0x18000753c  mov     r8, [rcx+20h]
0x180007540  mov     qword ptr [rcx+20h], 0
0x180007548  mov     rax, [rax]
0x18000754b  add     rax, 18h
0x18000754f  mov     rcx, [rax]
0x180007552  test    rcx, rcx
0x180007555  jz      short loc_180007565
0x180007557  lea     rdx, [rcx+20h]
0x18000755b  mov     rcx, [rdx]
0x18000755e  test    rcx, rcx
0x180007561  jnz     short loc_180007557
0x180007563  jmp     short loc_180007568
0x180007565  mov     rdx, rax
0x180007568  mov     [rdx], r8
0x18000756b  inc     esi
0x18000756d  mov     rcx, [rax]
0x180007570  test    rcx, rcx
0x180007573  jnz     short loc_18000753C
0x180007575  sub     [rbx+100h], esi
0x18000757b  mov     rcx, rbp; SRWLock
0x18000757e  call    cs:__imp_ReleaseSRWLockExclusive
0x180007584  mov     rax, [rbx+148h]
0x18000758b  mov     rbp, [rax+20h]
0x18000758f  jmp     short loc_1800075FC
0x180007591  movzx   eax, byte ptr [rdi+2Dh]
0x180007595  lea     rbx, [rdi+10h]
0x180007599  mov     edx, 2
0x18000759e  add     eax, edx
0x1800075a0  cmp     eax, edx
0x1800075a2  jbe     short loc_1800075BF
0x1800075a4  mov     rax, [rbx]
0x1800075a7  movsxd  rcx, edx
0x1800075aa  inc     edx
0x1800075ac  add     rcx, rcx
0x1800075af  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1800075b4  movzx   eax, byte ptr [rdi+2Dh]
0x1800075b8  add     eax, 2
0x1800075bb  cmp     edx, eax
0x1800075bd  jl      short loc_1800075A4
0x1800075bf  movzx   ecx, byte ptr [rdi+2Ch]
0x1800075c3  xor     r9d, r9d; RelatedActivityId
0x1800075c6  mov     rax, [rbx]
0x1800075c9  xor     r8d, r8d; ActivityId
0x1800075cc  mov     [rsp+58h+UserData], rax; UserData
0x1800075d1  mov     rdx, rdi; EventDescriptor
0x1800075d4  mov     [rsp+58h+UserDataCount], ecx; UserDataCount
0x1800075d8  mov     rcx, rbp; RegHandle
0x1800075db  call    cs:__imp_EventWriteTransfer
0x1800075e1  mov     rdi, [rdi+18h]
0x1800075e5  mov     rbx, [rbx]
0x1800075e8  call    cs:__imp_GetProcessHeap
0x1800075ee  mov     r8, rbx; lpMem
0x1800075f1  xor     edx, edx; dwFlags
0x1800075f3  mov     rcx, rax; hHeap
0x1800075f6  call    cs:__imp_HeapFree
0x1800075fc  test    rdi, rdi
0x1800075ff  jnz     short loc_180007591
0x180007601  mov     eax, esi
0x180007603  add     rsp, 38h
0x180007607  pop     rdi
0x180007608  pop     rsi
0x180007609  pop     rbp
0x18000760a  pop     rbx
0x18000760b  retn
```
