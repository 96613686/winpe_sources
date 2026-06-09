# CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x1800130c0`
- end: `0x180013130`
- name: `?GetItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800130c0`
- `0x180021678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013118`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013118`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800130ff`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800130ff`

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
0x1800130c0  push    rbx
0x1800130c2  push    rbp
0x1800130c3  push    rsi
0x1800130c4  push    rdi
0x1800130c5  sub     rsp, 28h
0x1800130c9  mov     rdi, rcx
0x1800130cc  mov     rsi, r8
0x1800130cf  add     rcx, 8; lpCriticalSection
0x1800130d3  mov     rbx, rdx
0x1800130d6  call    cs:__imp_EnterCriticalSection
0x1800130dd  nop     dword ptr [rax+rax+00h]
0x1800130e2  mov     rdx, rbx
0x1800130e5  mov     rcx, rdi
0x1800130e8  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x1800130ed  test    rax, rax
0x1800130f0  jz      short loc_18001310F
0x1800130f2  xor     ebx, ebx
0x1800130f4  test    rsi, rsi
0x1800130f7  jz      short loc_180013114
0x1800130f9  mov     rdx, rax; pvarSrc
0x1800130fc  mov     rcx, rsi; pvarDest
0x1800130ff  call    cs:__imp_PropVariantCopy
0x180013106  nop     dword ptr [rax+rax+00h]
0x18001310b  mov     ebx, eax
0x18001310d  jmp     short loc_180013114
0x18001310f  mov     ebx, 0C00D36E6h
0x180013114  lea     rcx, [rdi+8]; lpCriticalSection
0x180013118  call    cs:__imp_LeaveCriticalSection
0x18001311f  nop     dword ptr [rax+rax+00h]
0x180013124  mov     eax, ebx
0x180013126  add     rsp, 28h
0x18001312a  pop     rdi
0x18001312b  pop     rsi
0x18001312c  pop     rbp
0x18001312d  pop     rbx
0x18001312e  retn
```
