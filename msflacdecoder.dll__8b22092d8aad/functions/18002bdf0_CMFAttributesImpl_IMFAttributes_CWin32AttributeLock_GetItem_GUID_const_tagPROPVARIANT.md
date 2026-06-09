# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x18002bdf0`
- end: `0x18002be4d`
- name: `?GetItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002bdf0`
- `0x18002f58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be06`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002be29`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002be29`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItem(
        __int64 a1,
        __int64 a2,
        PROPVARIANT *a3)
{
  const PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (const PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
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
0x18002bdf0  push    rbx
0x18002bdf2  push    rbp
0x18002bdf3  push    rsi
0x18002bdf4  push    rdi
0x18002bdf5  sub     rsp, 28h
0x18002bdf9  mov     rdi, rcx
0x18002bdfc  mov     rsi, r8
0x18002bdff  add     rcx, 8; lpCriticalSection
0x18002be03  mov     rbx, rdx
0x18002be06  call    cs:__imp_EnterCriticalSection
0x18002be0c  mov     rdx, rbx
0x18002be0f  mov     rcx, rdi
0x18002be12  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18002be17  test    rax, rax
0x18002be1a  jz      short loc_18002BE33
0x18002be1c  xor     ebx, ebx
0x18002be1e  test    rsi, rsi
0x18002be21  jz      short loc_18002BE38
0x18002be23  mov     rdx, rax; pvarSrc
0x18002be26  mov     rcx, rsi; pvarDest
0x18002be29  call    cs:__imp_PropVariantCopy
0x18002be2f  mov     ebx, eax
0x18002be31  jmp     short loc_18002BE38
0x18002be33  mov     ebx, 0C00D36E6h
0x18002be38  lea     rcx, [rdi+8]; lpCriticalSection
0x18002be3c  call    cs:__imp_LeaveCriticalSection
0x18002be42  mov     eax, ebx
0x18002be44  add     rsp, 28h
0x18002be48  pop     rdi
0x18002be49  pop     rsi
0x18002be4a  pop     rbp
0x18002be4b  pop     rbx
0x18002be4c  retn
```
