# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x18005a650`
- end: `0x18005a723`
- name: `?SetItem@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180047a10`
- `0x18005a650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a682`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a682`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a664`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a664`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005a6df`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005a6df`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::SetItem(
        __int64 a1,
        __int64 a2,
        const PROPVARIANT *a3)
{
  DWORD CurrentThreadId; // ebx
  _DWORD *v7; // rbx
  __int64 Item; // rax
  unsigned int v9; // ecx
  PROPVARIANT *v10; // r8
  int v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( *(_DWORD *)(a1 + 16) == CurrentThreadId )
  {
    ++*(_DWORD *)(a1 + 20);
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    *(_DWORD *)(a1 + 16) = CurrentThreadId;
  }
  v7 = (_DWORD *)(a1 + 20);
  Item = CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::CreateItem(a1, a2);
  v9 = *(unsigned __int16 *)a3;
  v10 = (PROPVARIANT *)Item;
  if ( v9 > 0x1F )
  {
    v13 = v9 - 72;
    if ( !v13 )
      goto LABEL_6;
    v14 = v13 - 4041;
    if ( !v14 || v14 == 14 )
      goto LABEL_6;
  }
  else
  {
    v11 = -2144853984;
    if ( _bittest(&v11, v9) )
    {
LABEL_6:
      if ( v10 )
      {
        v12 = PropVariantCopy(v10, a3);
        *(_DWORD *)(a1 + 40) = 1;
      }
      else
      {
        v12 = -2147024882;
        v7 = (_DWORD *)(a1 + 20);
      }
      goto LABEL_13;
    }
  }
  v12 = -1072875843;
LABEL_13:
  if ( *v7 )
  {
    result = v12;
    --*v7;
  }
  else
  {
    *(_DWORD *)(a1 + 16) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18005a650  push    rbx
0x18005a652  push    rbp
0x18005a653  push    rsi
0x18005a654  push    rdi
0x18005a655  push    r14
0x18005a657  sub     rsp, 20h
0x18005a65b  mov     r14, r8
0x18005a65e  mov     rsi, rdx
0x18005a661  mov     rbp, rcx
0x18005a664  call    cs:__imp_GetCurrentThreadId
0x18005a66a  mov     r9d, [rbp+10h]
0x18005a66e  mov     ebx, eax
0x18005a670  cmp     r9d, eax
0x18005a673  jnz     short loc_18005A67E
0x18005a675  inc     dword ptr [rbp+14h]
0x18005a678  lea     rbx, [rbp+14h]
0x18005a67c  jmp     short loc_18005A68F
0x18005a67e  lea     rcx, [rbp+8]; SRWLock
0x18005a682  call    cs:__imp_AcquireSRWLockExclusive
0x18005a688  mov     [rbp+10h], ebx
0x18005a68b  lea     rbx, [rbp+14h]
0x18005a68f  mov     rdx, rsi
0x18005a692  mov     rcx, rbp
0x18005a695  call    ?CreateItem@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::CreateItem(_GUID const &)
0x18005a69a  movzx   ecx, word ptr [r14]
0x18005a69e  mov     r8, rax
0x18005a6a1  cmp     ecx, 1Fh
0x18005a6a4  ja      short loc_18005A6C0
0x18005a6a6  mov     eax, 80282020h
0x18005a6ab  bt      eax, ecx
0x18005a6ae  jnb     short loc_18005A6D2
0x18005a6b0  test    r8, r8
0x18005a6b3  jnz     short loc_18005A6D9
0x18005a6b5  mov     esi, 8007000Eh
0x18005a6ba  lea     rbx, [rbp+14h]
0x18005a6be  jmp     short loc_18005A6EE
0x18005a6c0  sub     ecx, 48h ; 'H'
0x18005a6c3  jz      short loc_18005A6B0
0x18005a6c5  sub     ecx, 0FC9h
0x18005a6cb  jz      short loc_18005A6B0
0x18005a6cd  cmp     ecx, 0Eh
0x18005a6d0  jz      short loc_18005A6B0
0x18005a6d2  mov     esi, 0C00D36BDh
0x18005a6d7  jmp     short loc_18005A6EE
0x18005a6d9  mov     rdx, r14; pvarSrc
0x18005a6dc  mov     rcx, r8; pvarDest
0x18005a6df  call    cs:__imp_PropVariantCopy
0x18005a6e5  mov     esi, eax
0x18005a6e7  mov     dword ptr [rbp+28h], 1
0x18005a6ee  mov     ecx, [rbx]
0x18005a6f0  test    ecx, ecx
0x18005a6f2  jz      short loc_18005A705
0x18005a6f4  dec     ecx
0x18005a6f6  mov     eax, esi
0x18005a6f8  mov     [rbx], ecx
0x18005a6fa  add     rsp, 20h
0x18005a6fe  pop     r14
0x18005a700  pop     rdi
0x18005a701  pop     rsi
0x18005a702  pop     rbp
0x18005a703  pop     rbx
0x18005a704  retn
0x18005a705  lea     rcx, [rbp+8]; SRWLock
0x18005a709  mov     dword ptr [rbp+10h], 0
0x18005a710  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a716  mov     eax, esi
0x18005a718  add     rsp, 20h
0x18005a71c  pop     r14
0x18005a71e  pop     rdi
0x18005a71f  pop     rsi
0x18005a720  pop     rbp
0x18005a721  pop     rbx
0x18005a722  retn
```
