# CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x180012870`
- end: `0x1800128cd`
- name: `?GetItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012870`
- `0x180020800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128bc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800128a9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800128a9`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetItem(__int64 a1, __int64 a2, PROPVARIANT *a3)
{
  const PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (const PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(a1, a2);
  if ( Item )
  {
    v7 = 0;
    if ( a3 )
      v7 = PropVariantCopy(a3, Item);
  }
  else
  {
    v7 = -1072875802;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x180012870  push    rbx
0x180012872  push    rbp
0x180012873  push    rsi
0x180012874  push    rdi
0x180012875  sub     rsp, 28h
0x180012879  mov     rdi, rcx
0x18001287c  mov     rsi, r8
0x18001287f  add     rcx, 8; lpCriticalSection
0x180012883  mov     rbx, rdx
0x180012886  call    cs:__imp_EnterCriticalSection
0x18001288c  mov     rdx, rbx
0x18001288f  mov     rcx, rdi
0x180012892  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x180012897  test    rax, rax
0x18001289a  jz      short loc_1800128B3
0x18001289c  xor     ebx, ebx
0x18001289e  test    rsi, rsi
0x1800128a1  jz      short loc_1800128B8
0x1800128a3  mov     rdx, rax; pvarSrc
0x1800128a6  mov     rcx, rsi; pvarDest
0x1800128a9  call    cs:__imp_PropVariantCopy
0x1800128af  mov     ebx, eax
0x1800128b1  jmp     short loc_1800128B8
0x1800128b3  mov     ebx, 0C00D36E6h
0x1800128b8  lea     rcx, [rdi+8]; lpCriticalSection
0x1800128bc  call    cs:__imp_LeaveCriticalSection
0x1800128c2  mov     eax, ebx
0x1800128c4  add     rsp, 28h
0x1800128c8  pop     rdi
0x1800128c9  pop     rsi
0x1800128ca  pop     rbp
0x1800128cb  pop     rbx
0x1800128cc  retn
```
