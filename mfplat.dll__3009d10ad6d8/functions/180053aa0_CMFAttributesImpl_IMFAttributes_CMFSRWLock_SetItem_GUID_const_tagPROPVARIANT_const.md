# CMFAttributesImpl<IMFAttributes,CMFSRWLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x180053aa0`
- end: `0x180053b73`
- name: `?SetItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002fb40`
- `0x180053aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053ad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053b60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053ab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053ab4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053b2f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053b2f`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFSRWLock>::SetItem(__int64 a1, __int64 a2, const PROPVARIANT *a3)
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
  Item = CMFAttributesImpl<IMFAttributes,CMFSRWLock>::CreateItem(a1, a2);
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
0x180053aa0  push    rbx
0x180053aa2  push    rbp
0x180053aa3  push    rsi
0x180053aa4  push    rdi
0x180053aa5  push    r14
0x180053aa7  sub     rsp, 20h
0x180053aab  mov     r14, r8
0x180053aae  mov     rsi, rdx
0x180053ab1  mov     rbp, rcx
0x180053ab4  call    cs:__imp_GetCurrentThreadId
0x180053aba  mov     r9d, [rbp+10h]
0x180053abe  mov     ebx, eax
0x180053ac0  cmp     r9d, eax
0x180053ac3  jnz     short loc_180053ACE
0x180053ac5  inc     dword ptr [rbp+14h]
0x180053ac8  lea     rbx, [rbp+14h]
0x180053acc  jmp     short loc_180053ADF
0x180053ace  lea     rcx, [rbp+8]; SRWLock
0x180053ad2  call    cs:__imp_AcquireSRWLockExclusive
0x180053ad8  mov     [rbp+10h], ebx
0x180053adb  lea     rbx, [rbp+14h]
0x180053adf  mov     rdx, rsi
0x180053ae2  mov     rcx, rbp
0x180053ae5  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFSRWLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFSRWLock>::CreateItem(_GUID const &)
0x180053aea  movzx   ecx, word ptr [r14]
0x180053aee  mov     r8, rax
0x180053af1  cmp     ecx, 1Fh
0x180053af4  ja      short loc_180053B10
0x180053af6  mov     eax, 80282020h
0x180053afb  bt      eax, ecx
0x180053afe  jnb     short loc_180053B22
0x180053b00  test    r8, r8
0x180053b03  jnz     short loc_180053B29
0x180053b05  mov     esi, 8007000Eh
0x180053b0a  lea     rbx, [rbp+14h]
0x180053b0e  jmp     short loc_180053B3E
0x180053b10  sub     ecx, 48h ; 'H'
0x180053b13  jz      short loc_180053B00
0x180053b15  sub     ecx, 0FC9h
0x180053b1b  jz      short loc_180053B00
0x180053b1d  cmp     ecx, 0Eh
0x180053b20  jz      short loc_180053B00
0x180053b22  mov     esi, 0C00D36BDh
0x180053b27  jmp     short loc_180053B3E
0x180053b29  mov     rdx, r14; pvarSrc
0x180053b2c  mov     rcx, r8; pvarDest
0x180053b2f  call    cs:__imp_PropVariantCopy
0x180053b35  mov     esi, eax
0x180053b37  mov     dword ptr [rbp+28h], 1
0x180053b3e  mov     ecx, [rbx]
0x180053b40  test    ecx, ecx
0x180053b42  jz      short loc_180053B55
0x180053b44  dec     ecx
0x180053b46  mov     eax, esi
0x180053b48  mov     [rbx], ecx
0x180053b4a  add     rsp, 20h
0x180053b4e  pop     r14
0x180053b50  pop     rdi
0x180053b51  pop     rsi
0x180053b52  pop     rbp
0x180053b53  pop     rbx
0x180053b54  retn
0x180053b55  lea     rcx, [rbp+8]; SRWLock
0x180053b59  mov     dword ptr [rbp+10h], 0
0x180053b60  call    cs:__imp_ReleaseSRWLockExclusive
0x180053b66  mov     eax, esi
0x180053b68  add     rsp, 20h
0x180053b6c  pop     r14
0x180053b6e  pop     rdi
0x180053b6f  pop     rsi
0x180053b70  pop     rbp
0x180053b71  pop     rbx
0x180053b72  retn
```
