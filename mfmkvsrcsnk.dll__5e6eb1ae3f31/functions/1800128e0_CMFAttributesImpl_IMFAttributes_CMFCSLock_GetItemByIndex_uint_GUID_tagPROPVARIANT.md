# CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x1800128e0`
- end: `0x180012958`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800128e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012943`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012943`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012937`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012937`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetItemByIndex(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        PROPVARIANT *a4)
{
  __int64 v5; // r14
  unsigned int v8; // ebx

  v5 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( (unsigned int)v5 < *(_DWORD *)(a1 + 60) )
  {
    v8 = 0;
    *a3 = *(_OWORD *)(*(_QWORD *)(a1 + 48) + 40 * v5);
    if ( a4 )
      v8 = PropVariantCopy(a4, (const PROPVARIANT *)(*(_QWORD *)(a1 + 48) + 16LL + 40 * v5));
  }
  else
  {
    v8 = -2147024809;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x1800128e0  push    rbx
0x1800128e2  push    rbp
0x1800128e3  push    rsi
0x1800128e4  push    rdi
0x1800128e5  push    r14
0x1800128e7  push    r15
0x1800128e9  sub     rsp, 28h
0x1800128ed  mov     rdi, rcx
0x1800128f0  mov     r14d, edx
0x1800128f3  add     rcx, 8; lpCriticalSection
0x1800128f7  mov     rbp, r9
0x1800128fa  mov     r15, r8
0x1800128fd  call    cs:__imp_EnterCriticalSection
0x180012903  cmp     r14d, [rdi+3Ch]
0x180012907  jb      short loc_180012910
0x180012909  mov     ebx, 80070057h
0x18001290e  jmp     short loc_18001293F
0x180012910  mov     rax, [rdi+30h]
0x180012914  lea     rcx, [r14+r14*4]
0x180012918  xor     ebx, ebx
0x18001291a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001291e  movdqu  xmmword ptr [r15], xmm0
0x180012923  test    rbp, rbp
0x180012926  jz      short loc_18001293F
0x180012928  mov     rax, [rdi+30h]
0x18001292c  add     rax, 10h
0x180012930  lea     rdx, [rax+rcx*8]; pvarSrc
0x180012934  mov     rcx, rbp; pvarDest
0x180012937  call    cs:__imp_PropVariantCopy
0x18001293d  mov     ebx, eax
0x18001293f  lea     rcx, [rdi+8]; lpCriticalSection
0x180012943  call    cs:__imp_LeaveCriticalSection
0x180012949  mov     eax, ebx
0x18001294b  add     rsp, 28h
0x18001294f  pop     r15
0x180012951  pop     r14
0x180012953  pop     rdi
0x180012954  pop     rsi
0x180012955  pop     rbp
0x180012956  pop     rbx
0x180012957  retn
```
