# BfsAddOrModifyEntry

- ea: `0x1400104ec`
- end: `0x14001074b`
- name: `BfsAddOrModifyEntry`
- size: `607`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140001ba0`
- `0x140005768`
- `0x140009d2c`
- `0x14000dc70`

## callees

- `0x1400104ec`
- `0x14001093c`
- `0x140011404`
- `0x140011838`
- `0x140011a24`
- `0x140011bc8`
- `0x140011ea8`
- `0x140012c40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010681`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010681`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400106c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010707`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400106c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010707`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400105a2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400105a2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400105c2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400105c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010591`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010670`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010591`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010670`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400105ce`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400106d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010713`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400105ce`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400106d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010713`

## pseudocode

```c
__int64 __fastcall BfsAddOrModifyEntry(
        __int64 a1,
        ULONG a2,
        NTSTATUS a3,
        ULONG a4,
        const UNICODE_STRING *a5,
        PVOID *a6)
{
  PVOID *v6; // rax
  __int64 result; // rax
  NTSTATUS EntryBlock; // edi
  PVOID *v11; // rbx
  char v12; // r13
  __m128i v13; // xmm6
  ULONG *Entry; // rsi
  unsigned __int16 v15; // r14
  NTSTATUS v16; // r8d
  ULONG v17; // r9d
  ULONG v18; // edx
  int v19; // eax
  volatile signed __int32 *v20; // rcx
  PVOID *v21; // [rsp+30h] [rbp-50h] BYREF
  void *v22; // [rsp+38h] [rbp-48h] BYREF
  UNICODE_STRING v23; // [rsp+40h] [rbp-40h] BYREF
  __m128i v24; // [rsp+50h] [rbp-30h] BYREF
  __int16 v25[8]; // [rsp+60h] [rbp-20h] BYREF

  v6 = a6;
  a6 = 0;
  v23 = 0;
  v24 = *(__m128i *)v6;
  if ( !*(_WORD *)v6 && a3 == 1 && a4 == 2 )
    return 3221225485LL;
  result = BfsCreateDirectory(a1 + 48, a5, 3, &a6);
  EntryBlock = result;
  if ( (int)result >= 0 )
  {
    v11 = a6;
    v12 = 1;
    v21 = a6;
    while ( 1 )
    {
      v13 = *(__m128i *)BfsGetPathComponent(v25, &v24, (__int64)&v23);
      v24 = v13;
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(v11, 0);
      Entry = (ULONG *)BfsFindEntry(v11, &v23);
      ExReleasePushLockSharedEx(v11, 0);
      KeLeaveCriticalRegion();
      v15 = _mm_cvtsi128_si32(v13);
      if ( !Entry )
      {
        if ( v15 >= 2u )
        {
          v16 = 0;
          v17 = 0;
        }
        else
        {
          v16 = a3;
          v17 = a4;
          v12 = 0;
        }
        v18 = 2;
        if ( v15 < 2u )
          v18 = a2;
        Entry = BfsInsertDirectoryEntry((__int64)v11, v18, v16, v17, (__int64)&v23);
        if ( !Entry )
          return 3221225495LL;
      }
      if ( v15 < 2u )
      {
        if ( v12 )
        {
          LODWORD(a6) = 0;
          v22 = 0;
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v11, 0);
          Entry[1] = a3;
          Entry[2] = a4;
          EntryBlock = BfsGetEntryBlock(v11, Entry, &v22, &a6);
          if ( EntryBlock < 0 )
          {
            ExReleasePushLockExclusiveEx(v11, 0);
            KeLeaveCriticalRegion();
            v20 = (volatile signed __int32 *)(v11 - 1);
LABEL_24:
            BfsDereferenceTableEntry(v20);
            return (unsigned int)EntryBlock;
          }
          EntryBlock = BfsWriteBlock(a1, (int)a6, v22);
          ExReleasePushLockExclusiveEx(v11, 0);
          KeLeaveCriticalRegion();
          BfsDereferenceTableEntry((volatile signed __int32 *)v11 - 2);
          if ( EntryBlock < 0 )
            return (unsigned int)EntryBlock;
        }
      }
      else
      {
        v19 = BfsCreateDirectory((__int64)v11, &v23, 1, &v21);
        v20 = (volatile signed __int32 *)(v11 - 1);
        EntryBlock = v19;
        if ( v19 < 0 )
          goto LABEL_24;
        BfsDereferenceTableEntry(v20);
        v11 = v21;
      }
      if ( v15 < 2u )
        return (unsigned int)EntryBlock;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400104ec  mov     rax, rsp
0x1400104ef  mov     [rax+18h], rbx
0x1400104f3  mov     [rax+10h], edx
0x1400104f6  mov     [rax+8], rcx
0x1400104fa  push    rbp
0x1400104fb  push    rsi
0x1400104fc  push    rdi
0x1400104fd  push    r12
0x1400104ff  push    r13
0x140010501  push    r14
0x140010503  push    r15
0x140010505  mov     rbp, rsp
0x140010508  sub     rsp, 80h
0x14001050f  xor     esi, esi
0x140010511  movaps  xmmword ptr [rax-48h], xmm6
0x140010515  mov     rax, [rbp+arg_28]
0x140010519  xorps   xmm0, xmm0
0x14001051c  mov     r15d, r9d
0x14001051f  mov     [rbp+arg_28], rsi
0x140010523  mov     r12d, r8d
0x140010526  movups  [rbp+var_40], xmm0
0x14001052a  movups  xmm1, xmmword ptr [rax]
0x14001052d  movdqu  [rbp+var_30], xmm1
0x140010532  cmp     [rax], si
0x140010535  jnz     short loc_14001054D
0x140010537  cmp     r8d, 1
0x14001053b  jnz     short loc_14001054D
0x14001053d  cmp     r9d, 2
0x140010541  jnz     short loc_14001054D
0x140010543  mov     eax, 0C000000Dh
0x140010548  jmp     loc_14001072A
0x14001054d  mov     rdx, [rbp+arg_20]
0x140010551  lea     r9, [rbp+arg_28]
0x140010555  add     rcx, 30h ; '0'
0x140010559  mov     r8d, 3
0x14001055f  call    BfsCreateDirectory
0x140010564  mov     edi, eax
0x140010566  test    eax, eax
0x140010568  js      loc_14001072A
0x14001056e  mov     rbx, [rbp+arg_28]
0x140010572  mov     r13b, 1
0x140010575  mov     [rbp+var_50], rbx
0x140010579  lea     r8, [rbp+var_40]
0x14001057d  lea     rdx, [rbp+var_30]
0x140010581  lea     rcx, [rbp+var_20]
0x140010585  call    BfsGetPathComponent
0x14001058a  movups  xmm6, xmmword ptr [rax]
0x14001058d  movups  [rbp+var_30], xmm6
0x140010591  call    cs:__imp_KeEnterCriticalRegion
0x140010598  nop     dword ptr [rax+rax+00h]
0x14001059d  xor     edx, edx
0x14001059f  mov     rcx, rbx
0x1400105a2  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400105a9  nop     dword ptr [rax+rax+00h]
0x1400105ae  lea     rdx, [rbp+var_40]
0x1400105b2  mov     rcx, rbx
0x1400105b5  call    BfsFindEntry
0x1400105ba  xor     edx, edx
0x1400105bc  mov     rcx, rbx
0x1400105bf  mov     rsi, rax
0x1400105c2  call    cs:__imp_ExReleasePushLockSharedEx
0x1400105c9  nop     dword ptr [rax+rax+00h]
0x1400105ce  call    cs:__imp_KeLeaveCriticalRegion
0x1400105d5  nop     dword ptr [rax+rax+00h]
0x1400105da  xor     eax, eax
0x1400105dc  movd    r14d, xmm6
0x1400105e1  test    rsi, rsi
0x1400105e4  jnz     short loc_140010625
0x1400105e6  lea     ecx, [rax+2]
0x1400105e9  cmp     r14w, cx
0x1400105ed  jnb     short loc_1400105FA
0x1400105ef  mov     r8d, r12d
0x1400105f2  mov     r9d, r15d
0x1400105f5  mov     r13b, al
0x1400105f8  jmp     short loc_140010600
0x1400105fa  mov     r8d, eax
0x1400105fd  mov     r9d, eax
0x140010600  mov     edx, ecx
0x140010602  lea     rax, [rbp+var_40]
0x140010606  cmovb   edx, [rbp+arg_8]
0x14001060a  mov     rcx, rbx
0x14001060d  mov     [rsp+80h+var_60], rax
0x140010612  call    BfsInsertDirectoryEntry
0x140010617  mov     rsi, rax
0x14001061a  xor     eax, eax
0x14001061c  test    rsi, rsi
0x14001061f  jz      loc_1400106FB
0x140010625  mov     ecx, 2
0x14001062a  cmp     r14w, cx
0x14001062e  jb      short loc_140010660
0x140010630  lea     r8d, [rcx-1]
0x140010634  mov     rcx, rbx
0x140010637  lea     r9, [rbp+var_50]
0x14001063b  lea     rdx, [rbp+var_40]
0x14001063f  call    BfsCreateDirectory
0x140010644  lea     rcx, [rbx-8]; Buffer
0x140010648  mov     edi, eax
0x14001064a  test    eax, eax
0x14001064c  js      loc_140010723
0x140010652  call    BfsDereferenceTableEntry
0x140010657  mov     rbx, [rbp+var_50]
0x14001065b  jmp     loc_1400106EA
0x140010660  test    r13b, r13b
0x140010663  jz      loc_1400106EA
0x140010669  mov     dword ptr [rbp+arg_28], eax
0x14001066c  mov     [rbp+var_48], rax
0x140010670  call    cs:__imp_KeEnterCriticalRegion
0x140010677  nop     dword ptr [rax+rax+00h]
0x14001067c  xor     edx, edx
0x14001067e  mov     rcx, rbx
0x140010681  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140010688  nop     dword ptr [rax+rax+00h]
0x14001068d  lea     r9, [rbp+arg_28]
0x140010691  mov     [rsi+4], r12d
0x140010695  lea     r8, [rbp+var_48]
0x140010699  mov     [rsi+8], r15d
0x14001069d  mov     rdx, rsi
0x1400106a0  mov     rcx, rbx
0x1400106a3  call    BfsGetEntryBlock
0x1400106a8  mov     edi, eax
0x1400106aa  test    eax, eax
0x1400106ac  js      short loc_140010702
0x1400106ae  mov     r8, [rbp+var_48]
0x1400106b2  mov     edx, dword ptr [rbp+arg_28]
0x1400106b5  mov     rcx, [rbp+arg_0]
0x1400106b9  call    BfsWriteBlock
0x1400106be  xor     edx, edx
0x1400106c0  mov     rcx, rbx
0x1400106c3  mov     edi, eax
0x1400106c5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400106cc  nop     dword ptr [rax+rax+00h]
0x1400106d1  call    cs:__imp_KeLeaveCriticalRegion
0x1400106d8  nop     dword ptr [rax+rax+00h]
0x1400106dd  lea     rcx, [rbx-8]; Buffer
0x1400106e1  call    BfsDereferenceTableEntry
0x1400106e6  test    edi, edi
0x1400106e8  js      short loc_140010728
0x1400106ea  mov     eax, 2
0x1400106ef  cmp     r14w, ax
0x1400106f3  jnb     loc_140010579
0x1400106f9  jmp     short loc_140010728
0x1400106fb  mov     eax, 0C0000017h
0x140010700  jmp     short loc_14001072A
0x140010702  xor     edx, edx
0x140010704  mov     rcx, rbx
0x140010707  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001070e  nop     dword ptr [rax+rax+00h]
0x140010713  call    cs:__imp_KeLeaveCriticalRegion
0x14001071a  nop     dword ptr [rax+rax+00h]
0x14001071f  lea     rcx, [rbx-8]; Buffer
0x140010723  call    BfsDereferenceTableEntry
0x140010728  mov     eax, edi
0x14001072a  mov     rbx, [rsp+80h+arg_10]
0x140010732  movaps  xmm6, [rsp+80h+var_10]
0x140010737  add     rsp, 80h
0x14001073e  pop     r15
0x140010740  pop     r14
0x140010742  pop     r13
0x140010744  pop     r12
0x140010746  pop     rdi
0x140010747  pop     rsi
0x140010748  pop     rbp
0x140010749  retn
```
