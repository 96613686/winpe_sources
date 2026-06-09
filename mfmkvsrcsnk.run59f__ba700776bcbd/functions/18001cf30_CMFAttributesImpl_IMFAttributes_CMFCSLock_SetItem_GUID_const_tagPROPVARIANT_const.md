# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetItem(_GUID const &,tagPROPVARIANT const &)

- ea: `0x18001cf30`
- end: `0x18001cfdf`
- name: `?SetItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@@Z`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ede4`
- `0x18001cf30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cfc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cfc7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001cfae`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001cfae`

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
0x18001cf30  push    rbx
0x18001cf32  push    rbp
0x18001cf33  push    rsi
0x18001cf34  push    rdi
0x18001cf35  sub     rsp, 28h
0x18001cf39  mov     rdi, rcx
0x18001cf3c  mov     rbp, r8
0x18001cf3f  add     rcx, 8; lpCriticalSection
0x18001cf43  mov     rbx, rdx
0x18001cf46  call    cs:__imp_EnterCriticalSection
0x18001cf4d  nop     dword ptr [rax+rax+00h]
0x18001cf52  mov     rdx, rbx
0x18001cf55  mov     rcx, rdi
0x18001cf58  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001cf5d  movzx   r9d, word ptr [rbp+0]
0x18001cf62  sub     r9d, 5
0x18001cf66  jz      short loc_18001CF9C
0x18001cf68  sub     r9d, 8
0x18001cf6c  jz      short loc_18001CF9C
0x18001cf6e  sub     r9d, 6
0x18001cf72  jz      short loc_18001CF9C
0x18001cf74  sub     r9d, 2
0x18001cf78  jz      short loc_18001CF9C
0x18001cf7a  sub     r9d, 0Ah
0x18001cf7e  jz      short loc_18001CF9C
0x18001cf80  sub     r9d, 29h ; ')'
0x18001cf84  jz      short loc_18001CF9C
0x18001cf86  sub     r9d, 0FC9h
0x18001cf8d  jz      short loc_18001CF9C
0x18001cf8f  cmp     r9d, 0Eh
0x18001cf93  jz      short loc_18001CF9C
0x18001cf95  mov     ebx, 0C00D36BDh
0x18001cf9a  jmp     short loc_18001CFC3
0x18001cf9c  test    rax, rax
0x18001cf9f  jnz     short loc_18001CFA8
0x18001cfa1  mov     ebx, 8007000Eh
0x18001cfa6  jmp     short loc_18001CFC3
0x18001cfa8  mov     rdx, rbp; pvarSrc
0x18001cfab  mov     rcx, rax; pvarDest
0x18001cfae  call    cs:__imp_PropVariantCopy
0x18001cfb5  nop     dword ptr [rax+rax+00h]
0x18001cfba  mov     ebx, eax
0x18001cfbc  mov     dword ptr [rdi+40h], 1
0x18001cfc3  lea     rcx, [rdi+8]; lpCriticalSection
0x18001cfc7  call    cs:__imp_LeaveCriticalSection
0x18001cfce  nop     dword ptr [rax+rax+00h]
0x18001cfd3  mov     eax, ebx
0x18001cfd5  add     rsp, 28h
0x18001cfd9  pop     rdi
0x18001cfda  pop     rsi
0x18001cfdb  pop     rbp
0x18001cfdc  pop     rbx
0x18001cfdd  retn
```
