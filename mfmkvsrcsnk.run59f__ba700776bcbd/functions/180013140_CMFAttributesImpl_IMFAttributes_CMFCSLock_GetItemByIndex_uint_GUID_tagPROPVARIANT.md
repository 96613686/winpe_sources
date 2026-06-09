# CMFAttributesImpl<IMFAttributes,CMFCSLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x180013140`
- end: `0x1800131cb`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001315d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001315d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131af`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001319d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001319d`

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
0x180013140  push    rbx
0x180013142  push    rbp
0x180013143  push    rsi
0x180013144  push    rdi
0x180013145  push    r14
0x180013147  push    r15
0x180013149  sub     rsp, 28h
0x18001314d  mov     rdi, rcx
0x180013150  mov     r14d, edx
0x180013153  add     rcx, 8; lpCriticalSection
0x180013157  mov     rbp, r9
0x18001315a  mov     r15, r8
0x18001315d  call    cs:__imp_EnterCriticalSection
0x180013164  nop     dword ptr [rax+rax+00h]
0x180013169  cmp     r14d, [rdi+3Ch]
0x18001316d  jb      short loc_180013176
0x18001316f  mov     ebx, 80070057h
0x180013174  jmp     short loc_1800131AB
0x180013176  mov     rax, [rdi+30h]
0x18001317a  lea     rcx, [r14+r14*4]
0x18001317e  xor     ebx, ebx
0x180013180  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180013184  movdqu  xmmword ptr [r15], xmm0
0x180013189  test    rbp, rbp
0x18001318c  jz      short loc_1800131AB
0x18001318e  mov     rax, [rdi+30h]
0x180013192  add     rax, 10h
0x180013196  lea     rdx, [rax+rcx*8]; pvarSrc
0x18001319a  mov     rcx, rbp; pvarDest
0x18001319d  call    cs:__imp_PropVariantCopy
0x1800131a4  nop     dword ptr [rax+rax+00h]
0x1800131a9  mov     ebx, eax
0x1800131ab  lea     rcx, [rdi+8]; lpCriticalSection
0x1800131af  call    cs:__imp_LeaveCriticalSection
0x1800131b6  nop     dword ptr [rax+rax+00h]
0x1800131bb  mov     eax, ebx
0x1800131bd  add     rsp, 28h
0x1800131c1  pop     r15
0x1800131c3  pop     r14
0x1800131c5  pop     rdi
0x1800131c6  pop     rsi
0x1800131c7  pop     rbp
0x1800131c8  pop     rbx
0x1800131c9  retn
```
