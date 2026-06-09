# NdisMWriteLogData

- ea: `0x14009e060`
- end: `0x14009e269`
- name: `NdisMWriteLogData`
- size: `521`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE LogHandle, PVOID LogBuffer, UINT LogBufferSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14009e060`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009e15d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009e1a1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009e15d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009e1a1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14009e249`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14009e249`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14009e087`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14009e087`
- `ntoskrnl!IofCompleteRequest` at `0x14009e21f`
- `ntoskrnl!IofCompleteRequest` at `0x14009e21f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14009e236`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14009e236`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14009e097`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14009e097`

## pseudocode

```c
NDIS_STATUS __stdcall NdisMWriteLogData(NDIS_HANDLE LogHandle, PVOID LogBuffer, UINT LogBufferSize)
{
  UINT v6; // r14d
  __int64 v7; // rax
  __int64 v8; // r14
  char *v9; // rcx
  NDIS_STATUS v10; // ebp
  char *v11; // rdx
  size_t v12; // r8
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  __int64 v16; // rbx
  struct _MDL *v17; // rcx
  unsigned int ByteCount; // esi
  __int16 v19; // dx
  char *v20; // rcx
  size_t v21; // r8
  char *v22; // rdx
  char *MappedSystemVa; // r14
  __int64 v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  KIRQL Irql; // [rsp+90h] [rbp+18h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)LogHandle + 1);
  v6 = *((_DWORD *)LogHandle + 6);
  if ( LogBufferSize > v6 )
  {
    v10 = -2147483643;
    goto LABEL_31;
  }
  v7 = *((unsigned int *)LogHandle + 8);
  v8 = v6 - (unsigned int)v7;
  v9 = (char *)LogHandle + v7 + 40;
  v10 = 0;
  v11 = (char *)LogBuffer;
  if ( LogBufferSize > (unsigned int)v8 )
  {
    memmove(v9, LogBuffer, (unsigned int)v8);
    v11 = (char *)LogBuffer + v8;
    v12 = LogBufferSize - (unsigned int)v8;
    v9 = (char *)LogHandle + 40;
  }
  else
  {
    v12 = LogBufferSize;
  }
  memmove(v9, v11, v12);
  *((_DWORD *)LogHandle + 7) += LogBufferSize;
  v13 = *((_DWORD *)LogHandle + 7);
  v14 = *((_DWORD *)LogHandle + 6);
  if ( v13 > v14 )
  {
    *((_DWORD *)LogHandle + 7) = v14;
    v13 = v14;
  }
  *((_DWORD *)LogHandle + 8) += LogBufferSize;
  v15 = *((_DWORD *)LogHandle + 8);
  if ( v15 >= v14 )
  {
    v15 -= v14;
    *((_DWORD *)LogHandle + 8) = v15;
  }
  if ( v13 == v14 )
    *((_DWORD *)LogHandle + 9) = v15;
  v16 = *((_QWORD *)LogHandle + 2);
  if ( v16 )
  {
    *((_QWORD *)LogHandle + 2) = 0;
    v17 = *(struct _MDL **)(v16 + 8);
    ByteCount = v17->ByteCount;
    if ( ByteCount > v13 )
      ByteCount = v13;
    v19 = v17->MdlFlags & 5;
    if ( v14 - *((_DWORD *)LogHandle + 9) < ByteCount )
    {
      if ( v19 )
        MappedSystemVa = (char *)v17->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000000u);
      if ( MappedSystemVa )
      {
        memmove(
          MappedSystemVa,
          (char *)LogHandle + *((unsigned int *)LogHandle + 9) + 40,
          (unsigned int)(*((_DWORD *)LogHandle + 6) - *((_DWORD *)LogHandle + 9)));
        v22 = (char *)LogHandle + 40;
        v24 = *((unsigned int *)LogHandle + 6);
        v21 = ByteCount + *((_DWORD *)LogHandle + 9) - (_DWORD)v24;
        v20 = &MappedSystemVa[v24 - *((unsigned int *)LogHandle + 9)];
        goto LABEL_25;
      }
    }
    else
    {
      if ( v19 )
        v20 = (char *)v17->MappedSystemVa;
      else
        v20 = (char *)MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000000u);
      if ( v20 )
      {
        v21 = ByteCount;
        v22 = (char *)LogHandle + *((unsigned int *)LogHandle + 9) + 40;
LABEL_25:
        memmove(v20, v22, v21);
LABEL_27:
        *((_DWORD *)LogHandle + 9) += ByteCount;
        *((_DWORD *)LogHandle + 7) -= ByteCount;
        v25 = *((_DWORD *)LogHandle + 9);
        v26 = *((_DWORD *)LogHandle + 6);
        if ( v25 >= v26 )
          *((_DWORD *)LogHandle + 9) = v25 - v26;
        *(_QWORD *)(v16 + 56) = ByteCount;
        _InterlockedExchange64((volatile __int64 *)(v16 + 104), 0);
        *(_DWORD *)(v16 + 48) = 0;
        IofCompleteRequest((PIRP)v16, 2);
        goto LABEL_31;
      }
    }
    v10 = -1073741670;
    goto LABEL_27;
  }
LABEL_31:
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)LogHandle + 1);
  IoReleaseCancelSpinLock(Irql);
  return v10;
}

```

## disassembly

```asm
0x14009e060  mov     rax, rsp
0x14009e063  push    rbx
0x14009e064  push    rbp
0x14009e065  push    rsi
0x14009e066  push    rdi
0x14009e067  push    r12
0x14009e069  push    r13
0x14009e06b  push    r14
0x14009e06d  push    r15
0x14009e06f  sub     rsp, 38h
0x14009e073  mov     rdi, rcx
0x14009e076  mov     esi, r8d
0x14009e079  xor     r13d, r13d
0x14009e07c  lea     rcx, [rax+18h]; Irql
0x14009e080  mov     [rax+18h], r13b
0x14009e084  mov     r15, rdx
0x14009e087  call    cs:__imp_IoAcquireCancelSpinLock
0x14009e08e  nop     dword ptr [rax+rax+00h]
0x14009e093  lea     rcx, [rdi+8]; SpinLock
0x14009e097  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14009e09e  nop     dword ptr [rax+rax+00h]
0x14009e0a3  mov     r14d, [rdi+18h]
0x14009e0a7  cmp     esi, r14d
0x14009e0aa  ja      loc_14009E22D
0x14009e0b0  mov     eax, [rdi+20h]
0x14009e0b3  lea     rcx, [rdi+28h]
0x14009e0b7  sub     r14d, eax
0x14009e0ba  add     rcx, rax; void *
0x14009e0bd  mov     ebp, r13d
0x14009e0c0  mov     rdx, r15; Src
0x14009e0c3  cmp     esi, r14d
0x14009e0c6  ja      short loc_14009E0CD
0x14009e0c8  mov     r8d, esi
0x14009e0cb  jmp     short loc_14009E0E3
0x14009e0cd  mov     r8d, r14d; Size
0x14009e0d0  call    memmove
0x14009e0d5  mov     r8d, esi
0x14009e0d8  lea     rdx, [r14+r15]; Src
0x14009e0dc  sub     r8d, r14d; Size
0x14009e0df  lea     rcx, [rdi+28h]; void *
0x14009e0e3  call    memmove
0x14009e0e8  add     [rdi+1Ch], esi
0x14009e0eb  mov     edx, [rdi+1Ch]
0x14009e0ee  mov     eax, [rdi+18h]
0x14009e0f1  cmp     edx, eax
0x14009e0f3  jbe     short loc_14009E0FA
0x14009e0f5  mov     [rdi+1Ch], eax
0x14009e0f8  mov     edx, eax
0x14009e0fa  add     [rdi+20h], esi
0x14009e0fd  mov     ecx, [rdi+20h]
0x14009e100  cmp     ecx, eax
0x14009e102  jb      short loc_14009E109
0x14009e104  sub     ecx, eax
0x14009e106  mov     [rdi+20h], ecx
0x14009e109  cmp     edx, eax
0x14009e10b  jnz     short loc_14009E110
0x14009e10d  mov     [rdi+24h], ecx
0x14009e110  mov     rbx, [rdi+10h]
0x14009e114  test    rbx, rbx
0x14009e117  jz      loc_14009E232
0x14009e11d  mov     [rdi+10h], r13
0x14009e121  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14009e125  mov     esi, [rcx+28h]
0x14009e128  cmp     esi, edx
0x14009e12a  cmova   esi, edx
0x14009e12d  movzx   edx, word ptr [rcx+0Ah]
0x14009e131  sub     eax, [rdi+24h]
0x14009e134  and     dx, 5
0x14009e138  cmp     eax, esi
0x14009e13a  jb      short loc_14009E180
0x14009e13c  test    dx, dx
0x14009e13f  jz      short loc_14009E147
0x14009e141  mov     rcx, [rcx+18h]
0x14009e145  jmp     short loc_14009E16C
0x14009e147  xor     r9d, r9d; RequestedAddress
0x14009e14a  mov     [rsp+78h+Priority], 40000000h; Priority
0x14009e152  xor     edx, edx; AccessMode
0x14009e154  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14009e159  lea     r8d, [r9+1]; CacheType
0x14009e15d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14009e164  nop     dword ptr [rax+rax+00h]
0x14009e169  mov     rcx, rax
0x14009e16c  test    rcx, rcx
0x14009e16f  jz      short loc_14009E1EF
0x14009e171  mov     edx, [rdi+24h]
0x14009e174  add     rdx, 28h ; '('
0x14009e178  mov     r8d, esi
0x14009e17b  add     rdx, rdi
0x14009e17e  jmp     short loc_14009E1E8
0x14009e180  test    dx, dx
0x14009e183  jz      short loc_14009E18B
0x14009e185  mov     r14, [rcx+18h]
0x14009e189  jmp     short loc_14009E1B0
0x14009e18b  xor     r9d, r9d; RequestedAddress
0x14009e18e  mov     [rsp+78h+Priority], 40000000h; Priority
0x14009e196  xor     edx, edx; AccessMode
0x14009e198  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14009e19d  lea     r8d, [r9+1]; CacheType
0x14009e1a1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14009e1a8  nop     dword ptr [rax+rax+00h]
0x14009e1ad  mov     r14, rax
0x14009e1b0  test    r14, r14
0x14009e1b3  jz      short loc_14009E1EF
0x14009e1b5  mov     ecx, [rdi+24h]
0x14009e1b8  mov     r8d, [rdi+18h]
0x14009e1bc  sub     r8d, ecx; Size
0x14009e1bf  lea     rdx, [rcx+28h]
0x14009e1c3  mov     rcx, r14; void *
0x14009e1c6  add     rdx, rdi; Src
0x14009e1c9  call    memmove
0x14009e1ce  mov     r9d, [rdi+24h]
0x14009e1d2  lea     rdx, [rdi+28h]; Src
0x14009e1d6  mov     ecx, [rdi+18h]
0x14009e1d9  mov     r8d, r9d
0x14009e1dc  sub     r8d, ecx
0x14009e1df  sub     rcx, r9
0x14009e1e2  add     r8d, esi; Size
0x14009e1e5  add     rcx, r14; void *
0x14009e1e8  call    memmove
0x14009e1ed  jmp     short loc_14009E1F4
0x14009e1ef  mov     ebp, 0C000009Ah
0x14009e1f4  add     [rdi+24h], esi
0x14009e1f7  sub     [rdi+1Ch], esi
0x14009e1fa  mov     eax, [rdi+24h]
0x14009e1fd  mov     ecx, [rdi+18h]
0x14009e200  cmp     eax, ecx
0x14009e202  jb      short loc_14009E209
0x14009e204  sub     eax, ecx
0x14009e206  mov     [rdi+24h], eax
0x14009e209  mov     eax, esi
0x14009e20b  mov     dl, 2; PriorityBoost
0x14009e20d  mov     [rbx+38h], rax
0x14009e211  mov     rcx, rbx; Irp
0x14009e214  mov     rax, r13
0x14009e217  xchg    rax, [rbx+68h]
0x14009e21b  mov     [rbx+30h], r13d
0x14009e21f  call    cs:__imp_IofCompleteRequest
0x14009e226  nop     dword ptr [rax+rax+00h]
0x14009e22b  jmp     short loc_14009E232
0x14009e22d  mov     ebp, 80000005h
0x14009e232  lea     rcx, [rdi+8]; SpinLock
0x14009e236  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14009e23d  nop     dword ptr [rax+rax+00h]
0x14009e242  mov     cl, [rsp+78h+Irql]; Irql
0x14009e249  call    cs:__imp_IoReleaseCancelSpinLock
0x14009e250  nop     dword ptr [rax+rax+00h]
0x14009e255  mov     eax, ebp
0x14009e257  add     rsp, 38h
0x14009e25b  pop     r15
0x14009e25d  pop     r14
0x14009e25f  pop     r13
0x14009e261  pop     r12
0x14009e263  pop     rdi
0x14009e264  pop     rsi
0x14009e265  pop     rbp
0x14009e266  pop     rbx
0x14009e267  retn
```
