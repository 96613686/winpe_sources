# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x18005acc0`
- end: `0x18005adb9`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180149600`

## callees

- `0x18005acc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ad02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ad02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ad8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ad8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ada5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ada5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005aceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ad49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005aceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ad49`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005ad41`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005ad41`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetItemByIndex(
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

  v4 = a1 + 16;
  v8 = a2;
  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
    ++*(_DWORD *)(v4 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v4);
  if ( (unsigned int)v8 < *(_DWORD *)(a1 + 44) )
  {
    v9 = 0;
    *a3 = *(_OWORD *)(*(_QWORD *)(a1 + 32) + 40 * v8);
    if ( a4 )
      v9 = PropVariantCopy(a4, (const PROPVARIANT *)(*(_QWORD *)(a1 + 32) + 16LL + 40 * v8));
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
0x18005acc0  push    rbx
0x18005acc2  push    rdi
0x18005acc3  sub     rsp, 28h
0x18005acc7  mov     [rsp+38h+arg_0], rbp
0x18005accc  lea     rbx, [rcx+10h]
0x18005acd0  mov     [rsp+38h+arg_10], r12
0x18005acd5  mov     rbp, rcx
0x18005acd8  mov     [rsp+38h+arg_18], r14
0x18005acdd  mov     r12, r8
0x18005ace0  mov     [rsp+38h+var_18], r15
0x18005ace5  mov     r15, r9
0x18005ace8  mov     r14d, edx
0x18005aceb  call    cs:__imp_GetCurrentThreadId
0x18005acf1  mov     r10d, [rbx+8]
0x18005acf5  cmp     r10d, eax
0x18005acf8  jnz     short loc_18005ACFF
0x18005acfa  inc     dword ptr [rbx+0Ch]
0x18005acfd  jmp     short loc_18005AD08
0x18005acff  mov     rcx, rbx; SRWLock
0x18005ad02  call    cs:__imp_AcquireSRWLockShared
0x18005ad08  mov     [rsp+38h+arg_8], rsi
0x18005ad0d  cmp     r14d, [rbp+2Ch]
0x18005ad11  jb      short loc_18005AD1A
0x18005ad13  mov     esi, 80070057h
0x18005ad18  jmp     short loc_18005AD49
0x18005ad1a  mov     rax, [rbp+20h]
0x18005ad1e  lea     rcx, [r14+r14*4]
0x18005ad22  xor     esi, esi
0x18005ad24  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18005ad28  movups  xmmword ptr [r12], xmm0
0x18005ad2d  test    r15, r15
0x18005ad30  jz      short loc_18005AD49
0x18005ad32  mov     rax, [rbp+20h]
0x18005ad36  add     rax, 10h
0x18005ad3a  lea     rdx, [rax+rcx*8]; pvarSrc
0x18005ad3e  mov     rcx, r15; pvarDest
0x18005ad41  call    cs:__imp_PropVariantCopy
0x18005ad47  mov     esi, eax
0x18005ad49  call    cs:__imp_GetCurrentThreadId
0x18005ad4f  mov     ecx, [rbx+8]
0x18005ad52  mov     r15, [rsp+38h+var_18]
0x18005ad57  mov     r14, [rsp+38h+arg_18]
0x18005ad5c  mov     r12, [rsp+38h+arg_10]
0x18005ad61  mov     rbp, [rsp+38h+arg_0]
0x18005ad66  cmp     ecx, eax
0x18005ad68  jnz     short loc_18005ADA2
0x18005ad6a  mov     ecx, [rbx+0Ch]
0x18005ad6d  test    ecx, ecx
0x18005ad6f  jz      short loc_18005AD84
0x18005ad71  dec     ecx
0x18005ad73  mov     eax, esi
0x18005ad75  mov     [rbx+0Ch], ecx
0x18005ad78  mov     rsi, [rsp+38h+arg_8]
0x18005ad7d  add     rsp, 28h
0x18005ad81  pop     rdi
0x18005ad82  pop     rbx
0x18005ad83  retn
0x18005ad84  mov     rcx, rbx; SRWLock
0x18005ad87  mov     dword ptr [rbx+8], 0
0x18005ad8e  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ad94  mov     eax, esi
0x18005ad96  mov     rsi, [rsp+38h+arg_8]
0x18005ad9b  add     rsp, 28h
0x18005ad9f  pop     rdi
0x18005ada0  pop     rbx
0x18005ada1  retn
0x18005ada2  mov     rcx, rbx; SRWLock
0x18005ada5  call    cs:__imp_ReleaseSRWLockShared
0x18005adab  mov     eax, esi
0x18005adad  mov     rsi, [rsp+38h+arg_8]
0x18005adb2  add     rsp, 28h
0x18005adb6  pop     rdi
0x18005adb7  pop     rbx
0x18005adb8  retn
```
