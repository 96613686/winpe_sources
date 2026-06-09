# CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x180049350`
- end: `0x180049449`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180049350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180049392`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180049392`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004941e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004941e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049435`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004937b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800493d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004937b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800493d9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800493d1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800493d1`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetItemByIndex(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        PROPVARIANT *a4)
{
  __int64 v4; // rbx
  __int64 v8; // r14
  unsigned int v9; // esi
  int v10; // ecx
  __int64 result; // rax

  v4 = a1 + 8;
  v8 = a2;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v4 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v4);
  if ( (unsigned int)v8 < *(_DWORD *)(a1 + 36) )
  {
    v9 = 0;
    *a3 = *(_OWORD *)(*(_QWORD *)(a1 + 24) + 40 * v8);
    if ( a4 )
      v9 = PropVariantCopy(a4, (const PROPVARIANT *)(*(_QWORD *)(a1 + 24) + 16LL + 40 * v8));
  }
  else
  {
    v9 = -2147024809;
  }
  if ( *(_DWORD *)(v4 + 8) == GetCurrentThreadId() )
  {
    v10 = *(_DWORD *)(v4 + 12);
    if ( v10 )
    {
      result = v9;
      *(_DWORD *)(v4 + 12) = v10 - 1;
    }
    else
    {
      *(_DWORD *)(v4 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v4);
      return v9;
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v4);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180049350  push    rbx
0x180049352  push    rdi
0x180049353  sub     rsp, 28h
0x180049357  mov     [rsp+38h+arg_0], rbp
0x18004935c  lea     rbx, [rcx+8]
0x180049360  mov     [rsp+38h+arg_10], r12
0x180049365  mov     rbp, rcx
0x180049368  mov     [rsp+38h+arg_18], r14
0x18004936d  mov     r12, r8
0x180049370  mov     [rsp+38h+var_18], r15
0x180049375  mov     r15, r9
0x180049378  mov     r14d, edx
0x18004937b  call    cs:__imp_GetCurrentThreadId
0x180049381  mov     r10d, [rbx+8]
0x180049385  cmp     r10d, eax
0x180049388  jnz     short loc_18004938F
0x18004938a  inc     dword ptr [rbx+0Ch]
0x18004938d  jmp     short loc_180049398
0x18004938f  mov     rcx, rbx; SRWLock
0x180049392  call    cs:__imp_AcquireSRWLockShared
0x180049398  mov     [rsp+38h+arg_8], rsi
0x18004939d  cmp     r14d, [rbp+24h]
0x1800493a1  jb      short loc_1800493AA
0x1800493a3  mov     esi, 80070057h
0x1800493a8  jmp     short loc_1800493D9
0x1800493aa  mov     rax, [rbp+18h]
0x1800493ae  lea     rcx, [r14+r14*4]
0x1800493b2  xor     esi, esi
0x1800493b4  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800493b8  movups  xmmword ptr [r12], xmm0
0x1800493bd  test    r15, r15
0x1800493c0  jz      short loc_1800493D9
0x1800493c2  mov     rax, [rbp+18h]
0x1800493c6  add     rax, 10h
0x1800493ca  lea     rdx, [rax+rcx*8]; pvarSrc
0x1800493ce  mov     rcx, r15; pvarDest
0x1800493d1  call    cs:__imp_PropVariantCopy
0x1800493d7  mov     esi, eax
0x1800493d9  call    cs:__imp_GetCurrentThreadId
0x1800493df  mov     ecx, [rbx+8]
0x1800493e2  mov     r15, [rsp+38h+var_18]
0x1800493e7  mov     r14, [rsp+38h+arg_18]
0x1800493ec  mov     r12, [rsp+38h+arg_10]
0x1800493f1  mov     rbp, [rsp+38h+arg_0]
0x1800493f6  cmp     ecx, eax
0x1800493f8  jnz     short loc_180049432
0x1800493fa  mov     ecx, [rbx+0Ch]
0x1800493fd  test    ecx, ecx
0x1800493ff  jz      short loc_180049414
0x180049401  dec     ecx
0x180049403  mov     eax, esi
0x180049405  mov     [rbx+0Ch], ecx
0x180049408  mov     rsi, [rsp+38h+arg_8]
0x18004940d  add     rsp, 28h
0x180049411  pop     rdi
0x180049412  pop     rbx
0x180049413  retn
0x180049414  mov     rcx, rbx; SRWLock
0x180049417  mov     dword ptr [rbx+8], 0
0x18004941e  call    cs:__imp_ReleaseSRWLockExclusive
0x180049424  mov     eax, esi
0x180049426  mov     rsi, [rsp+38h+arg_8]
0x18004942b  add     rsp, 28h
0x18004942f  pop     rdi
0x180049430  pop     rbx
0x180049431  retn
0x180049432  mov     rcx, rbx; SRWLock
0x180049435  call    cs:__imp_ReleaseSRWLockShared
0x18004943b  mov     eax, esi
0x18004943d  mov     rsi, [rsp+38h+arg_8]
0x180049442  add     rsp, 28h
0x180049446  pop     rdi
0x180049447  pop     rbx
0x180049448  retn
```
