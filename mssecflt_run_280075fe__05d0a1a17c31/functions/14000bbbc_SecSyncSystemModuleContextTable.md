# SecSyncSystemModuleContextTable

- ea: `0x14000bbbc`
- end: `0x14000c1ef`
- name: `SecSyncSystemModuleContextTable`
- size: `1587`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x14000b824`
- `0x140043ff0`

## callees

- `0x140006684`
- `0x1400088b0`
- `0x140009b80`
- `0x14000b7f0`
- `0x14000b940`
- `0x14000ba24`
- `0x14000bb5c`
- `0x14000bbbc`
- `0x14000f094`
- `0x140010188`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x14000be24`
- `ntoskrnl!RtlInitAnsiString` at `0x14000be24`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14000be3b`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14000be3b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000c053`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000c053`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14000bc7b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14000bc7b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000bd24`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000be75`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000bf67`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000bd24`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000be75`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14000bf67`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000bcab`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000beb3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000c036`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000c0d3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000bcab`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000beb3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000c036`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000c0d3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000bed0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000bed0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bce0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bce0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000be52`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bf45`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000be52`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000bf45`

## pseudocode

```c
__int64 SecSyncSystemModuleContextTable()
{
  _DWORD *v0; // r14
  PSLIST_ENTRY v1; // r15
  char v2; // bl
  NTSTATUS v4; // edi
  _DWORD *PoolWithTag; // rax
  unsigned int v6; // r13d
  __int64 v7; // r11
  ERESOURCE_THREAD OwnerThread; // rdx
  struct _SLIST_ENTRY *v9; // r10
  unsigned __int64 v10; // r8
  ERESOURCE_THREAD v11; // rax
  struct _SLIST_ENTRY *v12; // r12
  __int64 v13; // rsi
  SHORT *p_ActiveCount; // rdi
  union _SLIST_HEADER *v15; // rcx
  PSLIST_ENTRY v16; // rbx
  struct _SLIST_ENTRY *Next; // r8
  OWNER_ENTRY *p_OwnerEntry; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rax
  PERESOURCE v21; // rsi
  ERESOURCE_THREAD v22; // rbx
  ERESOURCE_THREAD v23; // rcx
  __int64 v24; // rax
  char v25; // dl
  unsigned __int64 i; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  _QWORD v29[12]; // [rsp+58h] [rbp-B0h] BYREF
  ULONG ReturnLength; // [rsp+B8h] [rbp-50h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v32; // [rsp+D0h] [rbp-38h] BYREF
  _STRING DestinationString; // [rsp+E0h] [rbp-28h] BYREF
  _DWORD SystemInformation[76]; // [rsp+F8h] [rbp-10h] BYREF

  memset(SystemInformation, 0, 0x12Cu);
  ReturnLength = 0;
  v0 = 0;
  v1 = 0;
  v2 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  v32 = 0;
  if ( !*((_BYTE *)SecData + 1268) )
    return 3221225473LL;
  v4 = ZwQuerySystemInformation_0(SystemModuleInformation, SystemInformation, 0x130u, &ReturnLength);
  if ( v4 == -1073741820 && ReturnLength )
  {
    ExEnterCriticalRegionAndAcquireResourceShared(SecSystemModuleTable);
    v2 = 1;
    if ( LOBYTE(SecSystemModuleTable[2].ActiveEntries)
      && LODWORD(SecSystemModuleTable[2].Reserved2) == SystemInformation[0] )
    {
      v4 = 0;
      goto LABEL_78;
    }
    ExReleaseResourceAndLeaveCriticalRegion(SecSystemModuleTable);
    v2 = 0;
    if ( qword_140020008 )
      PoolWithTag = (_DWORD *)qword_140020008(256, ReturnLength, 2020434771);
    else
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, ReturnLength, 0x786D6353u);
    v0 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v4 = -1073741670;
      goto LABEL_78;
    }
    v4 = ZwQuerySystemInformation_0(SystemModuleInformation, PoolWithTag, ReturnLength, &ReturnLength);
    if ( v4 < 0 )
      goto LABEL_78;
    _mm_lfence();
    ExEnterCriticalRegionAndAcquireResourceExclusive(SecSystemModuleTable);
    SecIncrementSystemModuleTableRepopulateCount();
    v6 = 0;
    LOBYTE(SecSystemModuleTable[2].ActiveEntries) = 1;
    if ( *v0 )
    {
      while ( 1 )
      {
        v7 = 74LL * v6;
        OwnerThread = SecSystemModuleTable[2].OwnerEntry.OwnerThread;
        if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 && OwnerThread )
          OwnerThread ^= (unsigned __int64)&SecSystemModuleTable[2].OwnerEntry;
        if ( !OwnerThread )
          break;
        v9 = *(struct _SLIST_ENTRY **)&v0[v7 + 6];
        do
        {
          v10 = *(_QWORD *)(OwnerThread - 40);
          if ( (unsigned __int64)v9 < v10 )
            goto LABEL_23;
          if ( (unsigned __int64)v9 < v10 + *(_QWORD *)(OwnerThread - 32) )
            break;
          if ( (unsigned __int64)v9 >= v10 )
            v11 = *(_QWORD *)(OwnerThread + 8);
          else
LABEL_23:
            v11 = *(_QWORD *)OwnerThread;
          if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 && v11 )
            OwnerThread ^= v11;
          else
            OwnerThread = v11;
        }
        while ( OwnerThread );
        if ( !OwnerThread )
          break;
        v1 = (PSLIST_ENTRY)(OwnerThread - 56);
        if ( !_bittest64((const signed __int64 *)&xmmword_14001B740, 0x34u)
          || v1[1].Next == v9 && *((_QWORD *)&v1[1].Next + 1) == v0[v7 + 8] )
        {
          goto LABEL_74;
        }
        v1 = 0;
LABEL_75:
        if ( ++v6 >= *v0 )
          goto LABEL_76;
      }
      v12 = *(struct _SLIST_ENTRY **)&v0[v7 + 6];
      v13 = (unsigned int)v0[v7 + 8];
      HIBYTE(v0[v7 + 75]) = 0;
      RtlInitAnsiString(&DestinationString, (PCSZ)&v0[v7 + 12]);
      if ( RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u) < 0 )
        RtlInitUnicodeString(&UnicodeString, &word_140016A48);
      memset(v29, 0, sizeof(v29));
      ExEnterCriticalRegionAndAcquireResourceExclusive(SecSystemModuleTable);
      if ( BYTE1(SecSystemModuleTable[2].ActiveEntries) )
      {
        v29[2] = v12;
        v29[3] = v13;
        LODWORD(v29[6]) = 1;
        SecRemoveAndReleaseCollidingSystemModuleContexts(v29);
      }
      ExReleaseResourceAndLeaveCriticalRegion(SecSystemModuleTable);
      p_ActiveCount = &SecSystemModuleTable[1].ActiveCount;
      v15 = (union _SLIST_HEADER *)&SecSystemModuleTable[1].ActiveCount;
      ++HIDWORD(SecSystemModuleTable[1].ExclusiveWaiters);
      v16 = ExpInterlockedPopEntrySList(v15);
      if ( !v16 )
      {
        ++*((_DWORD *)p_ActiveCount + 6);
        v16 = (PSLIST_ENTRY)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))p_ActiveCount + 6))(
                              *((unsigned int *)p_ActiveCount + 9),
                              *((unsigned int *)p_ActiveCount + 11),
                              *((unsigned int *)p_ActiveCount + 10));
      }
      if ( v16 )
      {
        memset(v16, 0, 0x60u);
        if ( (int)SecUnicodeToNullTerminatedUnicode(&UnicodeString, v16) < 0 )
        {
          _mm_lfence();
          RtlInitUnicodeString((PUNICODE_STRING)v16, &word_140016A48);
        }
        v16[1].Next = v12;
        *((_QWORD *)&v16[1].Next + 1) = v13;
        LODWORD(v16[3].Next) = 1;
        ExEnterCriticalRegionAndAcquireResourceExclusive(SecSystemModuleTable);
        if ( LOBYTE(SecSystemModuleTable[2].ActiveEntries) )
        {
          p_OwnerEntry = &SecSystemModuleTable[2].OwnerEntry;
          if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 )
          {
            if ( p_OwnerEntry->OwnerThread )
              v19 = p_OwnerEntry->OwnerThread ^ (unsigned __int64)p_OwnerEntry;
            else
              v19 = 0;
          }
          else
          {
            v19 = p_OwnerEntry->OwnerThread;
          }
          LOBYTE(Next) = 0;
          if ( v19 )
          {
            Next = v16[1].Next;
            while ( 1 )
            {
              if ( (unsigned __int64)Next < *(_QWORD *)(v19 - 40) )
              {
                v20 = *(_QWORD *)v19;
                if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 )
                {
                  if ( !v20 )
                    goto LABEL_65;
                  v20 ^= v19;
                }
                if ( !v20 )
                {
LABEL_65:
                  LOBYTE(Next) = 0;
                  break;
                }
              }
              else
              {
                v20 = *(_QWORD *)(v19 + 8);
                if ( (*(_BYTE *)&SecSystemModuleTable[2].OwnerEntry.0 & 1) != 0 )
                {
                  if ( !v20 )
                    goto LABEL_59;
                  v20 ^= v19;
                }
                if ( !v20 )
                {
LABEL_59:
                  LOBYTE(Next) = 1;
                  break;
                }
              }
              v19 = v20;
            }
          }
          TreeRbInsertNodeEx(p_OwnerEntry, v19, Next, &v16[3].Next + 1);
          v1 = v16;
          ++LODWORD(SecSystemModuleTable[2].Reserved2);
          ++LODWORD(v16[3].Next);
          v4 = 0;
        }
        else
        {
          SecReleaseSystemModuleContext(v16);
          v4 = -1073741823;
        }
        ExReleaseResourceAndLeaveCriticalRegion(SecSystemModuleTable);
      }
      else
      {
        v4 = -1073741670;
        LOBYTE(SecSystemModuleTable[2].ActiveEntries) = 0;
      }
      if ( UnicodeString.Buffer != &word_140016A48 )
        RtlFreeUnicodeString(&UnicodeString);
      if ( v4 < 0 )
        goto LABEL_77;
      if ( !v6 )
        *(_QWORD *)&SecSystemModuleTable[2].NumberOfSharedWaiters = v12;
      SecReleaseSystemModuleContext(v1);
LABEL_74:
      BYTE4(v1[3].Next) = 1;
      goto LABEL_75;
    }
LABEL_76:
    v21 = SecSystemModuleTable;
    *((_QWORD *)&v32 + 1) = &v32;
    *(_QWORD *)&v32 = &v32;
    v22 = SecSystemModuleTable[2].OwnerEntry.OwnerThread;
    if ( !v22 )
    {
LABEL_77:
      v2 = 1;
      goto LABEL_78;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        if ( (int)SecDeferredDeleteSystemModuleContextIfNotSynced(v22, &v32) < 0 )
        {
LABEL_107:
          while ( 1 )
          {
            v28 = v32;
            if ( (__int128 *)v32 == &v32 )
              break;
            if ( *(__int128 **)(v32 + 8) != &v32
              || (v27 = *(_QWORD *)v32, *(_QWORD *)(*(_QWORD *)v32 + 8LL) != (_QWORD)v32) )
            {
              __fastfail(3u);
            }
            *(_QWORD *)&v32 = *(_QWORD *)v32;
            *(_QWORD *)(v27 + 8) = &v32;
            SecRemoveSystemModuleContextFromTreeAndRelease((PSLIST_ENTRY)(v28 - 80));
          }
          goto LABEL_77;
        }
        v23 = *(_QWORD *)v22;
        if ( !*(_QWORD *)v22 )
          break;
        if ( (*(_BYTE *)&v21[2].OwnerEntry.0 & 1) != 0 )
          v22 ^= v23;
        else
LABEL_101:
          v22 = v23;
      }
      v24 = *(_QWORD *)(v22 + 8);
      v25 = *(_BYTE *)&v21[2].OwnerEntry.0 & 1;
      if ( !v24 )
        break;
      if ( v25 )
        v22 ^= v24;
      else
        v22 = *(_QWORD *)(v22 + 8);
    }
    for ( i = v22; ; v22 = i )
    {
      i = *(_QWORD *)(i + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v25 )
      {
        if ( !i )
          goto LABEL_107;
        i ^= v22;
      }
      if ( !i )
        goto LABEL_107;
      v23 = *(_QWORD *)(i + 8);
      if ( v25 )
      {
        if ( !v23 )
          continue;
        v23 ^= i;
      }
      if ( v23 && v23 != v22 )
        goto LABEL_101;
    }
  }
LABEL_78:
  BYTE1(SecSystemModuleTable[2].ActiveEntries) = 1;
  if ( v2 )
    ExReleaseResourceAndLeaveCriticalRegion(SecSystemModuleTable);
  if ( v0 )
    SecFreePool(v0, 0x786D6353u);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000bbbc  mov     rax, rsp
0x14000bbbf  mov     [rax+8], rbx
0x14000bbc3  mov     [rax+10h], rsi
0x14000bbc7  mov     [rax+18h], rdi
0x14000bbcb  push    rbp
0x14000bbcc  push    r12
0x14000bbce  push    r13
0x14000bbd0  push    r14
0x14000bbd2  push    r15
0x14000bbd4  lea     rbp, [rax-158h]
0x14000bbdb  sub     rsp, 230h
0x14000bbe2  mov     rax, cs:__security_cookie
0x14000bbe9  xor     rax, rsp
0x14000bbec  mov     [rbp+150h+var_30], rax
0x14000bbf3  xor     eax, eax
0x14000bbf5  lea     rcx, [rbp+150h+SystemInformation]; void *
0x14000bbf9  xor     edx, edx; Val
0x14000bbfb  mov     [rbp+150h+var_15C], eax
0x14000bbfe  mov     r8d, 12Ch; Size
0x14000bc04  call    memset
0x14000bc09  mov     rax, cs:SecData
0x14000bc10  xorps   xmm0, xmm0
0x14000bc13  xorps   xmm1, xmm1
0x14000bc16  mov     [rbp+150h+ReturnLength], 0
0x14000bc1d  xor     r14d, r14d
0x14000bc20  xor     r15d, r15d
0x14000bc23  xor     bl, bl
0x14000bc25  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x14000bc29  movups  xmmword ptr [rbp+150h+UnicodeString.Length], xmm1
0x14000bc2d  movups  [rbp+150h+var_188], xmm0
0x14000bc31  cmp     [rax+4F4h], bl
0x14000bc37  jnz     short loc_14000BC43
0x14000bc39  mov     eax, 0C0000001h
0x14000bc3e  jmp     loc_14000C0F3
0x14000bc43  mov     esi, 0Bh
0x14000bc48  lea     r9, [rbp+150h+ReturnLength]; ReturnLength
0x14000bc4c  mov     ecx, esi; SystemInformationClass
0x14000bc4e  lea     rdx, [rbp+150h+SystemInformation]; SystemInformation
0x14000bc52  mov     r8d, 130h; SystemInformationLength
0x14000bc58  call    ZwQuerySystemInformation_0
0x14000bc5d  mov     edi, eax
0x14000bc5f  cmp     eax, 0C0000004h
0x14000bc64  jnz     loc_14000C0BA
0x14000bc6a  cmp     [rbp+150h+ReturnLength], r14d
0x14000bc6e  jz      loc_14000C0BA
0x14000bc74  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000bc7b  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x14000bc82  nop     dword ptr [rax+rax+00h]
0x14000bc87  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000bc8e  mov     bl, 1
0x14000bc90  cmp     [rcx+110h], r14b
0x14000bc97  jz      short loc_14000BCAB
0x14000bc99  mov     eax, [rbp+150h+SystemInformation]
0x14000bc9c  cmp     [rcx+120h], eax
0x14000bca2  jnz     short loc_14000BCAB
0x14000bca4  xor     edi, edi
0x14000bca6  jmp     loc_14000C0BA
0x14000bcab  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000bcb2  nop     dword ptr [rax+rax+00h]
0x14000bcb7  mov     rax, cs:qword_140020008
0x14000bcbe  xor     bl, bl
0x14000bcc0  mov     edx, [rbp+150h+ReturnLength]; NumberOfBytes
0x14000bcc3  mov     r8d, 786D6353h; Tag
0x14000bcc9  test    rax, rax
0x14000bccc  jz      short loc_14000BCDB
0x14000bcce  mov     ecx, 100h
0x14000bcd3  call    cs:__guard_dispatch_icall_fptr
0x14000bcd9  jmp     short loc_14000BCEC
0x14000bcdb  mov     ecx, 1; PoolType
0x14000bce0  call    cs:__imp_ExAllocatePoolWithTag
0x14000bce7  nop     dword ptr [rax+rax+00h]
0x14000bcec  mov     r14, rax
0x14000bcef  test    rax, rax
0x14000bcf2  jnz     short loc_14000BCFE
0x14000bcf4  mov     edi, 0C000009Ah
0x14000bcf9  jmp     loc_14000C0BA
0x14000bcfe  mov     r8d, [rbp+150h+ReturnLength]; SystemInformationLength
0x14000bd02  lea     r9, [rbp+150h+ReturnLength]; ReturnLength
0x14000bd06  mov     rdx, r14; SystemInformation
0x14000bd09  mov     ecx, esi; SystemInformationClass
0x14000bd0b  call    ZwQuerySystemInformation_0
0x14000bd10  mov     edi, eax
0x14000bd12  test    eax, eax
0x14000bd14  js      loc_14000C0BA
0x14000bd1a  lfence
0x14000bd1d  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000bd24  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14000bd2b  nop     dword ptr [rax+rax+00h]
0x14000bd30  mov     [rsp+250h+var_230], 1
0x14000bd35  call    SecIncrementSystemModuleTableRepopulateCount
0x14000bd3a  mov     rax, cs:SecSystemModuleTable
0x14000bd41  xor     r13d, r13d
0x14000bd44  mov     byte ptr [rax+110h], 1
0x14000bd4b  cmp     [r14], r13d
0x14000bd4e  jbe     loc_14000C08F
0x14000bd54  lea     rbx, word_140016A48
0x14000bd5b  mov     rcx, cs:SecSystemModuleTable
0x14000bd62  add     rcx, 100h
0x14000bd69  mov     eax, r13d
0x14000bd6c  imul    r11, rax, 128h
0x14000bd73  test    byte ptr [rcx+8], 1
0x14000bd77  mov     rdx, [rcx]
0x14000bd7a  jz      short loc_14000BD84
0x14000bd7c  test    rdx, rdx
0x14000bd7f  jz      short loc_14000BD84
0x14000bd81  xor     rdx, rcx
0x14000bd84  movzx   r9d, byte ptr [rcx+8]
0x14000bd89  and     r9d, 1
0x14000bd8d  test    rdx, rdx
0x14000bd90  jz      short loc_14000BE06
0x14000bd92  mov     r10, [r11+r14+18h]
0x14000bd97  mov     r8, [rdx-28h]
0x14000bd9b  cmp     r10, r8
0x14000bd9e  jb      short loc_14000BDB1
0x14000bda0  mov     rcx, [rdx-20h]
0x14000bda4  add     rcx, r8
0x14000bda7  cmp     r10, rcx
0x14000bdaa  jb      short loc_14000BDD1
0x14000bdac  cmp     r10, r8
0x14000bdaf  jnb     short loc_14000BDB6
0x14000bdb1  mov     rax, [rdx]
0x14000bdb4  jmp     short loc_14000BDBA
0x14000bdb6  mov     rax, [rdx+8]
0x14000bdba  test    r9d, r9d
0x14000bdbd  jz      short loc_14000BDC9
0x14000bdbf  test    rax, rax
0x14000bdc2  jz      short loc_14000BDC9
0x14000bdc4  xor     rdx, rax
0x14000bdc7  jmp     short loc_14000BDCC
0x14000bdc9  mov     rdx, rax
0x14000bdcc  test    rdx, rdx
0x14000bdcf  jnz     short loc_14000BD97
0x14000bdd1  test    rdx, rdx
0x14000bdd4  jz      short loc_14000BE06
0x14000bdd6  bt      qword ptr cs:xmmword_14001B740, 34h ; '4'
0x14000bddf  lea     r15, [rdx-38h]
0x14000bde3  jnb     loc_14000C07E
0x14000bde9  cmp     [r15+10h], r10
0x14000bded  jnz     short loc_14000BDFE
0x14000bdef  mov     eax, [r11+r14+20h]
0x14000bdf4  cmp     [r15+18h], rax
0x14000bdf8  jz      loc_14000C07E
0x14000bdfe  xor     r15d, r15d
0x14000be01  jmp     loc_14000C083
0x14000be06  mov     r12, [r11+r14+18h]
0x14000be0b  lea     rdx, [r11+30h]
0x14000be0f  mov     esi, [r11+r14+20h]
0x14000be14  lea     rcx, [rbp+150h+DestinationString]; DestinationString
0x14000be18  add     rdx, r14; SourceString
0x14000be1b  mov     byte ptr [r11+r14+12Fh], 0
0x14000be24  call    cs:__imp_RtlInitAnsiString
0x14000be2b  nop     dword ptr [rax+rax+00h]
0x14000be30  mov     r8b, 1; AllocateDestinationString
0x14000be33  lea     rdx, [rbp+150h+DestinationString]; SourceString
0x14000be37  lea     rcx, [rbp+150h+UnicodeString]; DestinationString
0x14000be3b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14000be42  nop     dword ptr [rax+rax+00h]
0x14000be47  test    eax, eax
0x14000be49  jns     short loc_14000BE5E
0x14000be4b  mov     rdx, rbx; SourceString
0x14000be4e  lea     rcx, [rbp+150h+UnicodeString]; DestinationString
0x14000be52  call    cs:__imp_RtlInitUnicodeString
0x14000be59  nop     dword ptr [rax+rax+00h]
0x14000be5e  xor     edx, edx; Val
0x14000be60  lea     rcx, [rsp+250h+var_200]; void *
0x14000be65  lea     r8d, [rdx+60h]; Size
0x14000be69  call    memset
0x14000be6e  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000be75  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14000be7c  nop     dword ptr [rax+rax+00h]
0x14000be81  mov     rax, cs:SecSystemModuleTable
0x14000be88  cmp     byte ptr [rax+111h], 0
0x14000be8f  jz      short loc_14000BEAC
0x14000be91  lea     rcx, [rsp+250h+var_200]
0x14000be96  mov     [rsp+250h+var_1F0], r12
0x14000be9b  mov     [rsp+250h+var_1E8], rsi
0x14000bea0  mov     [rbp+150h+var_1D0], 1
0x14000bea7  call    SecRemoveAndReleaseCollidingSystemModuleContexts
0x14000beac  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000beb3  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000beba  nop     dword ptr [rax+rax+00h]
0x14000bebf  mov     rdi, cs:SecSystemModuleTable
0x14000bec6  sub     rdi, 0FFFFFFFFFFFFFF80h
0x14000beca  mov     rcx, rdi; ListHead
0x14000becd  inc     dword ptr [rdi+14h]
0x14000bed0  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000bed7  nop     dword ptr [rax+rax+00h]
0x14000bedc  mov     rbx, rax
0x14000bedf  test    rax, rax
0x14000bee2  jnz     short loc_14000BEFE
0x14000bee4  inc     dword ptr [rdi+18h]
0x14000bee7  mov     edx, [rdi+2Ch]
0x14000beea  mov     rax, [rdi+30h]
0x14000beee  mov     r8d, [rdi+28h]
0x14000bef2  mov     ecx, [rdi+24h]
0x14000bef5  call    cs:__guard_dispatch_icall_fptr
0x14000befb  mov     rbx, rax
0x14000befe  test    rbx, rbx
0x14000bf01  jnz     short loc_14000BF1A
0x14000bf03  mov     rax, cs:SecSystemModuleTable
0x14000bf0a  mov     edi, 0C000009Ah
0x14000bf0f  mov     [rax+110h], bl
0x14000bf15  jmp     loc_14000C042
0x14000bf1a  xor     edx, edx; Val
0x14000bf1c  mov     rcx, rbx; void *
0x14000bf1f  lea     r8d, [rdx+60h]; Size
0x14000bf23  call    memset
0x14000bf28  mov     rdx, rbx
0x14000bf2b  lea     rcx, [rbp+150h+UnicodeString]
0x14000bf2f  call    SecUnicodeToNullTerminatedUnicode
0x14000bf34  test    eax, eax
0x14000bf36  jns     short loc_14000BF51
0x14000bf38  lfence
0x14000bf3b  lea     rdx, word_140016A48; SourceString
0x14000bf42  mov     rcx, rbx; DestinationString
0x14000bf45  call    cs:__imp_RtlInitUnicodeString
0x14000bf4c  nop     dword ptr [rax+rax+00h]
0x14000bf51  mov     [rbx+10h], r12
0x14000bf55  mov     [rbx+18h], rsi
0x14000bf59  mov     dword ptr [rbx+30h], 1
0x14000bf60  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000bf67  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14000bf6e  nop     dword ptr [rax+rax+00h]
0x14000bf73  mov     rax, cs:SecSystemModuleTable
0x14000bf7a  cmp     byte ptr [rax+110h], 0
0x14000bf81  jnz     short loc_14000BF95
0x14000bf83  mov     rcx, rbx; ListEntry
0x14000bf86  call    SecReleaseSystemModuleContext
0x14000bf8b  mov     edi, 0C0000001h
0x14000bf90  jmp     loc_14000C02F
0x14000bf95  lea     rcx, [rax+100h]
0x14000bf9c  test    byte ptr [rcx+8], 1
0x14000bfa0  jz      short loc_14000BFB6
0x14000bfa2  mov     rax, [rcx]
0x14000bfa5  test    rax, rax
0x14000bfa8  jz      short loc_14000BFB2
0x14000bfaa  mov     rdx, rcx
0x14000bfad  xor     rdx, rax
0x14000bfb0  jmp     short loc_14000BFB9
0x14000bfb2  xor     edx, edx
0x14000bfb4  jmp     short loc_14000BFB9
0x14000bfb6  mov     rdx, [rcx]
0x14000bfb9  movzx   r9d, byte ptr [rcx+8]
0x14000bfbe  xor     r8b, r8b
0x14000bfc1  and     r9d, 1
0x14000bfc5  test    rdx, rdx
0x14000bfc8  jz      short loc_14000C00C
0x14000bfca  mov     r8, [rbx+10h]
0x14000bfce  cmp     r8, [rdx-28h]
0x14000bfd2  jb      short loc_14000BFEF
0x14000bfd4  mov     rax, [rdx+8]
0x14000bfd8  test    r9d, r9d
0x14000bfdb  jz      short loc_14000BFE5
0x14000bfdd  test    rax, rax
0x14000bfe0  jz      short loc_14000BFEA
0x14000bfe2  xor     rax, rdx
0x14000bfe5  test    rax, rax
0x14000bfe8  jnz     short loc_14000C004
0x14000bfea  mov     r8b, 1
0x14000bfed  jmp     short loc_14000C00C
0x14000bfef  mov     rax, [rdx]
0x14000bff2  test    r9d, r9d
0x14000bff5  jz      short loc_14000BFFF
0x14000bff7  test    rax, rax
0x14000bffa  jz      short loc_14000C009
0x14000bffc  xor     rax, rdx
0x14000bfff  test    rax, rax
0x14000c002  jz      short loc_14000C009
0x14000c004  mov     rdx, rax
0x14000c007  jmp     short loc_14000BFCE
0x14000c009  xor     r8b, r8b
0x14000c00c  lea     r9, [rbx+38h]
0x14000c010  call    TreeRbInsertNodeEx
0x14000c015  mov     rax, cs:SecSystemModuleTable
0x14000c01c  mov     r15, rbx
0x14000c01f  inc     dword ptr [rax+120h]
0x14000c025  mov     eax, [rbx+30h]
0x14000c028  inc     eax
0x14000c02a  mov     [rbx+30h], eax
0x14000c02d  xor     edi, edi
0x14000c02f  mov     rcx, cs:SecSystemModuleTable; Resource
0x14000c036  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14000c03d  nop     dword ptr [rax+rax+00h]
0x14000c042  lea     rbx, word_140016A48
0x14000c049  cmp     [rbp+150h+UnicodeString.Buffer], rbx
0x14000c04d  jz      short loc_14000C05F
0x14000c04f  lea     rcx, [rbp+150h+UnicodeString]; UnicodeString
0x14000c053  call    cs:__imp_RtlFreeUnicodeString
0x14000c05a  nop     dword ptr [rax+rax+00h]
0x14000c05f  test    edi, edi
0x14000c061  js      short loc_14000C0B6
0x14000c063  test    r13d, r13d
0x14000c066  jnz     short loc_14000C076
0x14000c068  mov     rax, cs:SecSystemModuleTable
0x14000c06f  mov     [rax+118h], r12
0x14000c076  mov     rcx, r15; ListEntry
0x14000c079  call    SecReleaseSystemModuleContext
0x14000c07e  mov     byte ptr [r15+34h], 1
0x14000c083  inc     r13d
0x14000c086  cmp     r13d, [r14]
  ... truncated ...
```
