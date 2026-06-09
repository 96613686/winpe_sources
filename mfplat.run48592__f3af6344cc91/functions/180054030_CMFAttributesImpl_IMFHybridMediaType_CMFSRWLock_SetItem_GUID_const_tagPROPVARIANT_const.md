# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x180054030`
- end: `0x180054103`
- name: `?SetItem@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180149aa0`

## callees

- `0x18002f160`
- `0x180054030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054062`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054062`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800540f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800540f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054044`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054044`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800540bf`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800540bf`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::SetItem(
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
  if ( *(_DWORD *)(a1 + 24) == CurrentThreadId )
  {
    ++*(_DWORD *)(a1 + 28);
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    *(_DWORD *)(a1 + 24) = CurrentThreadId;
  }
  v7 = (_DWORD *)(a1 + 28);
  Item = CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CreateItem(a1, a2);
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
        *(_DWORD *)(a1 + 48) = 1;
      }
      else
      {
        v12 = -2147024882;
        v7 = (_DWORD *)(a1 + 28);
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
    *(_DWORD *)(a1 + 24) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180054030  push    rbx
0x180054032  push    rbp
0x180054033  push    rsi
0x180054034  push    rdi
0x180054035  push    r14
0x180054037  sub     rsp, 20h
0x18005403b  mov     r14, r8
0x18005403e  mov     rsi, rdx
0x180054041  mov     rbp, rcx
0x180054044  call    cs:__imp_GetCurrentThreadId
0x18005404a  mov     r9d, [rbp+18h]
0x18005404e  mov     ebx, eax
0x180054050  cmp     r9d, eax
0x180054053  jnz     short loc_18005405E
0x180054055  inc     dword ptr [rbp+1Ch]
0x180054058  lea     rbx, [rbp+1Ch]
0x18005405c  jmp     short loc_18005406F
0x18005405e  lea     rcx, [rbp+10h]; SRWLock
0x180054062  call    cs:__imp_AcquireSRWLockExclusive
0x180054068  mov     [rbp+18h], ebx
0x18005406b  lea     rbx, [rbp+1Ch]
0x18005406f  mov     rdx, rsi
0x180054072  mov     rcx, rbp
0x180054075  call    ?CreateItem@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CreateItem(_GUID const &)
0x18005407a  movzx   ecx, word ptr [r14]
0x18005407e  mov     r8, rax
0x180054081  cmp     ecx, 1Fh
0x180054084  ja      short loc_1800540A0
0x180054086  mov     eax, 80282020h
0x18005408b  bt      eax, ecx
0x18005408e  jnb     short loc_1800540B2
0x180054090  test    r8, r8
0x180054093  jnz     short loc_1800540B9
0x180054095  mov     esi, 8007000Eh
0x18005409a  lea     rbx, [rbp+1Ch]
0x18005409e  jmp     short loc_1800540CE
0x1800540a0  sub     ecx, 48h ; 'H'
0x1800540a3  jz      short loc_180054090
0x1800540a5  sub     ecx, 0FC9h
0x1800540ab  jz      short loc_180054090
0x1800540ad  cmp     ecx, 0Eh
0x1800540b0  jz      short loc_180054090
0x1800540b2  mov     esi, 0C00D36BDh
0x1800540b7  jmp     short loc_1800540CE
0x1800540b9  mov     rdx, r14; pvarSrc
0x1800540bc  mov     rcx, r8; pvarDest
0x1800540bf  call    cs:__imp_PropVariantCopy
0x1800540c5  mov     esi, eax
0x1800540c7  mov     dword ptr [rbp+30h], 1
0x1800540ce  mov     ecx, [rbx]
0x1800540d0  test    ecx, ecx
0x1800540d2  jz      short loc_1800540E5
0x1800540d4  dec     ecx
0x1800540d6  mov     eax, esi
0x1800540d8  mov     [rbx], ecx
0x1800540da  add     rsp, 20h
0x1800540de  pop     r14
0x1800540e0  pop     rdi
0x1800540e1  pop     rsi
0x1800540e2  pop     rbp
0x1800540e3  pop     rbx
0x1800540e4  retn
0x1800540e5  lea     rcx, [rbp+10h]; SRWLock
0x1800540e9  mov     dword ptr [rbp+18h], 0
0x1800540f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800540f6  mov     eax, esi
0x1800540f8  add     rsp, 20h
0x1800540fc  pop     r14
0x1800540fe  pop     rdi
0x1800540ff  pop     rsi
0x180054100  pop     rbp
0x180054101  pop     rbx
0x180054102  retn
```
