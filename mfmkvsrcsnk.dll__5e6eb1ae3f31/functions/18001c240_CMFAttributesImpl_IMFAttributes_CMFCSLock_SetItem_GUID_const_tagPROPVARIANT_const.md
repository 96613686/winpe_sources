# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x18001c240`
- end: `0x18001c2dc`
- name: `?SetItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e798`
- `0x18001c240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c256`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c256`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c2cb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001c2b8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001c2b8`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetItem(__int64 a1, __int64 a2, const PROPVARIANT *a3)
{
  PROPVARIANT *Item; // rax
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = (PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
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
0x18001c240  push    rbx
0x18001c242  push    rbp
0x18001c243  push    rsi
0x18001c244  push    rdi
0x18001c245  sub     rsp, 28h
0x18001c249  mov     rdi, rcx
0x18001c24c  mov     rbp, r8
0x18001c24f  add     rcx, 8; lpCriticalSection
0x18001c253  mov     rbx, rdx
0x18001c256  call    cs:__imp_EnterCriticalSection
0x18001c25c  mov     rdx, rbx
0x18001c25f  mov     rcx, rdi
0x18001c262  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001c267  movzx   r9d, word ptr [rbp+0]
0x18001c26c  sub     r9d, 5
0x18001c270  jz      short loc_18001C2A6
0x18001c272  sub     r9d, 8
0x18001c276  jz      short loc_18001C2A6
0x18001c278  sub     r9d, 6
0x18001c27c  jz      short loc_18001C2A6
0x18001c27e  sub     r9d, 2
0x18001c282  jz      short loc_18001C2A6
0x18001c284  sub     r9d, 0Ah
0x18001c288  jz      short loc_18001C2A6
0x18001c28a  sub     r9d, 29h ; ')'
0x18001c28e  jz      short loc_18001C2A6
0x18001c290  sub     r9d, 0FC9h
0x18001c297  jz      short loc_18001C2A6
0x18001c299  cmp     r9d, 0Eh
0x18001c29d  jz      short loc_18001C2A6
0x18001c29f  mov     ebx, 0C00D36BDh
0x18001c2a4  jmp     short loc_18001C2C7
0x18001c2a6  test    rax, rax
0x18001c2a9  jnz     short loc_18001C2B2
0x18001c2ab  mov     ebx, 8007000Eh
0x18001c2b0  jmp     short loc_18001C2C7
0x18001c2b2  mov     rdx, rbp; pvarSrc
0x18001c2b5  mov     rcx, rax; pvarDest
0x18001c2b8  call    cs:__imp_PropVariantCopy
0x18001c2be  mov     ebx, eax
0x18001c2c0  mov     dword ptr [rdi+40h], 1
0x18001c2c7  lea     rcx, [rdi+8]; lpCriticalSection
0x18001c2cb  call    cs:__imp_LeaveCriticalSection
0x18001c2d1  mov     eax, ebx
0x18001c2d3  add     rsp, 28h
0x18001c2d7  pop     rdi
0x18001c2d8  pop     rsi
0x18001c2d9  pop     rbp
0x18001c2da  pop     rbx
0x18001c2db  retn
```
