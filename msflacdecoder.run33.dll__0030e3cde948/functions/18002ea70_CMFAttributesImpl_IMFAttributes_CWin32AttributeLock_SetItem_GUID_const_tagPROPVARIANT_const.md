# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x18002ea70`
- end: `0x18002eb0c`
- name: `?SetItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002b05c`
- `0x18002ea70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eafb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eafb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ea86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ea86`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002eae8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002eae8`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetItem(
        __int64 a1,
        __int64 a2,
        const PROPVARIANT *a3)
{
  PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( a3->vt == 5
    || a3->vt == 13
    || a3->vt == 19
    || a3->vt == 21
    || a3->vt == 31
    || a3->vt == 72
    || a3->vt == 4113
    || a3->vt == 4127 )
  {
    if ( Item )
    {
      v7 = PropVariantCopy(Item, a3);
      *(_DWORD *)(a1 + 64) = 1;
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -1072875843;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x18002ea70  push    rbx
0x18002ea72  push    rbp
0x18002ea73  push    rsi
0x18002ea74  push    rdi
0x18002ea75  sub     rsp, 28h
0x18002ea79  mov     rdi, rcx
0x18002ea7c  mov     rbp, r8
0x18002ea7f  add     rcx, 8; lpCriticalSection
0x18002ea83  mov     rbx, rdx
0x18002ea86  call    cs:__imp_EnterCriticalSection
0x18002ea8c  mov     rdx, rbx
0x18002ea8f  mov     rcx, rdi
0x18002ea92  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18002ea97  movzx   r9d, word ptr [rbp+0]
0x18002ea9c  sub     r9d, 5
0x18002eaa0  jz      short loc_18002EAD6
0x18002eaa2  sub     r9d, 8
0x18002eaa6  jz      short loc_18002EAD6
0x18002eaa8  sub     r9d, 6
0x18002eaac  jz      short loc_18002EAD6
0x18002eaae  sub     r9d, 2
0x18002eab2  jz      short loc_18002EAD6
0x18002eab4  sub     r9d, 0Ah
0x18002eab8  jz      short loc_18002EAD6
0x18002eaba  sub     r9d, 29h ; ')'
0x18002eabe  jz      short loc_18002EAD6
0x18002eac0  sub     r9d, 0FC9h
0x18002eac7  jz      short loc_18002EAD6
0x18002eac9  cmp     r9d, 0Eh
0x18002eacd  jz      short loc_18002EAD6
0x18002eacf  mov     ebx, 0C00D36BDh
0x18002ead4  jmp     short loc_18002EAF7
0x18002ead6  test    rax, rax
0x18002ead9  jnz     short loc_18002EAE2
0x18002eadb  mov     ebx, 8007000Eh
0x18002eae0  jmp     short loc_18002EAF7
0x18002eae2  mov     rdx, rbp; pvarSrc
0x18002eae5  mov     rcx, rax; pvarDest
0x18002eae8  call    cs:__imp_PropVariantCopy
0x18002eaee  mov     ebx, eax
0x18002eaf0  mov     dword ptr [rdi+40h], 1
0x18002eaf7  lea     rcx, [rdi+8]; lpCriticalSection
0x18002eafb  call    cs:__imp_LeaveCriticalSection
0x18002eb01  mov     eax, ebx
0x18002eb03  add     rsp, 28h
0x18002eb07  pop     rdi
0x18002eb08  pop     rsi
0x18002eb09  pop     rbp
0x18002eb0a  pop     rbx
0x18002eb0b  retn
```
