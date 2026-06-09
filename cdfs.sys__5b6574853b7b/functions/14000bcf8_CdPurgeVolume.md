# CdPurgeVolume

- ea: `0x14000bcf8`
- end: `0x14000bf65`
- name: `CdPurgeVolume`
- size: `621`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400016b0`
- `0x140001d0c`
- `0x140001fd0`
- `0x140002630`
- `0x14000d400`
- `0x140015090`
- `0x14001af0c`

## callees

- `0x14000bc18`
- `0x14000bcf8`
- `0x14000c374`
- `0x1400181a4`
- `0x14001943c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000bd45`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000bd45`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bdac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bdd5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bdac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bdd5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000bf41`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000bf41`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000be29`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000bea7`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000bf09`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000be29`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000bea7`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000bf09`
- `ntoskrnl!MmFlushImageSection` at `0x14000be04`
- `ntoskrnl!MmFlushImageSection` at `0x14000be04`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x14000bd6d`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x14000bd6d`

## pseudocode

```c
__int64 __fastcall CdPurgeVolume(__int64 a1, __int64 a2, char a3)
{
  unsigned int v4; // ebx
  _QWORD *v7; // rbp
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rax
  struct _FAST_MUTEX *v11; // rcx
  __int64 v12; // rcx
  SECTION_OBJECT_POINTERS *v13; // rcx
  __int64 v14; // rdi
  SECTION_OBJECT_POINTERS *v15; // rcx
  __int64 v16; // rdi
  SECTION_OBJECT_POINTERS *v17; // rcx
  PVOID RestartKey; // [rsp+68h] [rbp+10h] BYREF
  bool v20; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  RestartKey = 0;
  v7 = 0;
  CdFspClose(a2);
  CdAcquireResource(a1, a2 + 232, 0, 0);
  while ( 1 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
    v8 = RtlEnumerateGenericTableWithoutSplaying((PRTL_GENERIC_TABLE)(a2 + 448), &RestartKey);
    v9 = v8;
    if ( v8 )
    {
      v10 = v8[1];
      v9 = (_QWORD *)v10;
      if ( v10 )
        ++*(_DWORD *)(v10 + 164);
    }
    v11 = (struct _FAST_MUTEX *)(a2 + 336);
    if ( v7 )
    {
      --*((_DWORD *)v7 + 41);
      *(_QWORD *)(a2 + 392) = 0;
      ExReleaseFastMutex(v11);
      CdTeardownStructures(a1, (__int16 *)v7, &v20);
    }
    else
    {
      *(_QWORD *)(a2 + 392) = 0;
      ExReleaseFastMutex(v11);
    }
    if ( !v9 )
      break;
    v12 = v9[25];
    v7 = v9;
    if ( *(_QWORD *)(v12 + 24) )
      MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v12 + 8), MmFlushForWrite);
    v13 = (SECTION_OBJECT_POINTERS *)(v9[25] + 8LL);
    if ( v13->DataSectionObject && !CcPurgeCacheSection(v13, 0, 0, 0) && !v4 )
      v4 = -1073741797;
    if ( a3 && *(_WORD *)v9 != 773 )
    {
      if ( v9[59] )
        CdDeleteInternalStream(v13, v9);
    }
  }
  if ( a3 )
  {
    v14 = *(_QWORD *)(a2 + 88);
    if ( v14 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 164));
      v15 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v14 + 200) + 8LL);
      if ( v15->DataSectionObject && !CcPurgeCacheSection(v15, 0, 0, 0) && !v4 )
        v4 = -1073741797;
      CdDeleteInternalStream(v15, v14);
      _InterlockedDecrement((volatile signed __int32 *)(v14 + 164));
      CdTeardownStructures(a1, (__int16 *)v14, &v20);
    }
    v16 = *(_QWORD *)(a2 + 72);
    if ( v16 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 164));
      v17 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v16 + 200) + 8LL);
      if ( v17->DataSectionObject && !CcPurgeCacheSection(v17, 0, 0, 0) && !v4 )
        v4 = -1073741797;
      _InterlockedDecrement((volatile signed __int32 *)(v16 + 164));
      CdTeardownStructures(a1, (__int16 *)v16, &v20);
    }
  }
  ExReleaseResourceLite((PERESOURCE)(a2 + 232));
  return v4;
}

```

## disassembly

```asm
0x14000bcf8  mov     [rsp+arg_0], rbx
0x14000bcfd  push    rbp
0x14000bcfe  push    rsi
0x14000bcff  push    rdi
0x14000bd00  push    r12
0x14000bd02  push    r13
0x14000bd04  push    r14
0x14000bd06  push    r15
0x14000bd08  sub     rsp, 20h
0x14000bd0c  mov     r12, rcx
0x14000bd0f  xor     ebx, ebx
0x14000bd11  mov     rcx, rdx
0x14000bd14  mov     [rsp+58h+RestartKey], rbx
0x14000bd19  mov     r15b, r8b
0x14000bd1c  mov     rsi, rdx
0x14000bd1f  xor     ebp, ebp
0x14000bd21  call    CdFspClose
0x14000bd26  lea     rdx, [rsi+0E8h]
0x14000bd2d  xor     r9d, r9d
0x14000bd30  xor     r8d, r8d
0x14000bd33  mov     rcx, r12
0x14000bd36  call    CdAcquireResource
0x14000bd3b  lea     r14, [rsi+150h]
0x14000bd42  mov     rcx, r14; FastMutex
0x14000bd45  call    cs:__imp_ExAcquireFastMutex
0x14000bd4c  nop     dword ptr [rax+rax+00h]
0x14000bd51  mov     rax, gs:188h
0x14000bd5a  lea     rdx, [rsp+58h+RestartKey]; RestartKey
0x14000bd5f  lea     rcx, [rsi+1C0h]; Table
0x14000bd66  mov     [rsi+188h], rax
0x14000bd6d  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x14000bd74  nop     dword ptr [rax+rax+00h]
0x14000bd79  mov     rdi, rax
0x14000bd7c  test    rax, rax
0x14000bd7f  jz      short loc_14000BD93
0x14000bd81  mov     rax, [rax+8]
0x14000bd85  mov     rdi, rax
0x14000bd88  test    rax, rax
0x14000bd8b  jz      short loc_14000BD93
0x14000bd8d  inc     dword ptr [rax+0A4h]
0x14000bd93  mov     rcx, r14; FastMutex
0x14000bd96  test    rbp, rbp
0x14000bd99  jz      short loc_14000BDCA
0x14000bd9b  dec     dword ptr [rbp+0A4h]
0x14000bda1  mov     qword ptr [rsi+188h], 0
0x14000bdac  call    cs:__imp_ExReleaseFastMutex
0x14000bdb3  nop     dword ptr [rax+rax+00h]
0x14000bdb8  lea     r8, [rsp+58h+arg_10]
0x14000bdbd  mov     rdx, rbp
0x14000bdc0  mov     rcx, r12
0x14000bdc3  call    CdTeardownStructures
0x14000bdc8  jmp     short loc_14000BDE1
0x14000bdca  mov     qword ptr [rsi+188h], 0
0x14000bdd5  call    cs:__imp_ExReleaseFastMutex
0x14000bddc  nop     dword ptr [rax+rax+00h]
0x14000bde1  test    rdi, rdi
0x14000bde4  jz      loc_14000BE75
0x14000bdea  mov     rcx, [rdi+0C8h]
0x14000bdf1  mov     rbp, rdi
0x14000bdf4  cmp     qword ptr [rcx+18h], 0
0x14000bdf9  jz      short loc_14000BE10
0x14000bdfb  add     rcx, 8; SectionObjectPointer
0x14000bdff  mov     edx, 1; FlushType
0x14000be04  call    cs:__imp_MmFlushImageSection
0x14000be0b  nop     dword ptr [rax+rax+00h]
0x14000be10  mov     rcx, [rdi+0C8h]
0x14000be17  add     rcx, 8; SectionObjectPointer
0x14000be1b  cmp     qword ptr [rcx], 0
0x14000be1f  jz      short loc_14000BE43
0x14000be21  xor     r9d, r9d; Flags
0x14000be24  xor     r8d, r8d; Length
0x14000be27  xor     edx, edx; FileOffset
0x14000be29  call    cs:__imp_CcPurgeCacheSection
0x14000be30  nop     dword ptr [rax+rax+00h]
0x14000be35  test    al, al
0x14000be37  jnz     short loc_14000BE43
0x14000be39  test    ebx, ebx
0x14000be3b  mov     eax, 0C000001Bh
0x14000be40  cmovz   ebx, eax
0x14000be43  test    r15b, r15b
0x14000be46  jz      loc_14000BD42
0x14000be4c  mov     eax, 305h
0x14000be51  cmp     [rdi], ax
0x14000be54  jz      loc_14000BD42
0x14000be5a  cmp     qword ptr [rdi+1D8h], 0
0x14000be62  jz      loc_14000BD42
0x14000be68  mov     rdx, rdi
0x14000be6b  call    CdDeleteInternalStream
0x14000be70  jmp     loc_14000BD42
0x14000be75  test    r15b, r15b
0x14000be78  jz      loc_14000BF3A
0x14000be7e  mov     rdi, [rsi+58h]
0x14000be82  test    rdi, rdi
0x14000be85  jz      short loc_14000BEE0
0x14000be87  lock inc dword ptr [rdi+0A4h]
0x14000be8e  mov     rcx, [rdi+0C8h]
0x14000be95  add     rcx, 8; SectionObjectPointer
0x14000be99  cmp     qword ptr [rcx], 0
0x14000be9d  jz      short loc_14000BEC1
0x14000be9f  xor     r9d, r9d; Flags
0x14000bea2  xor     r8d, r8d; Length
0x14000bea5  xor     edx, edx; FileOffset
0x14000bea7  call    cs:__imp_CcPurgeCacheSection
0x14000beae  nop     dword ptr [rax+rax+00h]
0x14000beb3  test    al, al
0x14000beb5  jnz     short loc_14000BEC1
0x14000beb7  test    ebx, ebx
0x14000beb9  mov     eax, 0C000001Bh
0x14000bebe  cmovz   ebx, eax
0x14000bec1  mov     rdx, rdi
0x14000bec4  call    CdDeleteInternalStream
0x14000bec9  lock dec dword ptr [rdi+0A4h]
0x14000bed0  lea     r8, [rsp+58h+arg_10]
0x14000bed5  mov     rdx, rdi
0x14000bed8  mov     rcx, r12
0x14000bedb  call    CdTeardownStructures
0x14000bee0  mov     rdi, [rsi+48h]
0x14000bee4  test    rdi, rdi
0x14000bee7  jz      short loc_14000BF3A
0x14000bee9  lock inc dword ptr [rdi+0A4h]
0x14000bef0  mov     rcx, [rdi+0C8h]
0x14000bef7  add     rcx, 8; SectionObjectPointer
0x14000befb  cmp     qword ptr [rcx], 0
0x14000beff  jz      short loc_14000BF23
0x14000bf01  xor     r9d, r9d; Flags
0x14000bf04  xor     r8d, r8d; Length
0x14000bf07  xor     edx, edx; FileOffset
0x14000bf09  call    cs:__imp_CcPurgeCacheSection
0x14000bf10  nop     dword ptr [rax+rax+00h]
0x14000bf15  test    al, al
0x14000bf17  jnz     short loc_14000BF23
0x14000bf19  test    ebx, ebx
0x14000bf1b  mov     eax, 0C000001Bh
0x14000bf20  cmovz   ebx, eax
0x14000bf23  lock dec dword ptr [rdi+0A4h]
0x14000bf2a  lea     r8, [rsp+58h+arg_10]
0x14000bf2f  mov     rdx, rdi
0x14000bf32  mov     rcx, r12
0x14000bf35  call    CdTeardownStructures
0x14000bf3a  lea     rcx, [rsi+0E8h]; Resource
0x14000bf41  call    cs:__imp_ExReleaseResourceLite
0x14000bf48  nop     dword ptr [rax+rax+00h]
0x14000bf4d  mov     eax, ebx
0x14000bf4f  mov     rbx, [rsp+58h+arg_0]
0x14000bf54  add     rsp, 20h
0x14000bf58  pop     r15
0x14000bf5a  pop     r14
0x14000bf5c  pop     r13
0x14000bf5e  pop     r12
0x14000bf60  pop     rdi
0x14000bf61  pop     rsi
0x14000bf62  pop     rbp
0x14000bf63  retn
```
