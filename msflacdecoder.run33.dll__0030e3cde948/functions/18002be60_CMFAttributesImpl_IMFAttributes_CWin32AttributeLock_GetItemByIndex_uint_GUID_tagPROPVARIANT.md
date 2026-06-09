# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItemByIndex(uint,_GUID *,tagPROPVARIANT *)

- ea: `0x18002be60`
- end: `0x18002bed8`
- name: `?GetItemByIndex@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJIPEAU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002be60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bec3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be7d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002beb7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002beb7`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetItemByIndex(
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
0x18002be60  push    rbx
0x18002be62  push    rbp
0x18002be63  push    rsi
0x18002be64  push    rdi
0x18002be65  push    r14
0x18002be67  push    r15
0x18002be69  sub     rsp, 28h
0x18002be6d  mov     rdi, rcx
0x18002be70  mov     r14d, edx
0x18002be73  add     rcx, 8; lpCriticalSection
0x18002be77  mov     rbp, r9
0x18002be7a  mov     r15, r8
0x18002be7d  call    cs:__imp_EnterCriticalSection
0x18002be83  cmp     r14d, [rdi+3Ch]
0x18002be87  jb      short loc_18002BE90
0x18002be89  mov     ebx, 80070057h
0x18002be8e  jmp     short loc_18002BEBF
0x18002be90  mov     rax, [rdi+30h]
0x18002be94  lea     rcx, [r14+r14*4]
0x18002be98  xor     ebx, ebx
0x18002be9a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18002be9e  movdqu  xmmword ptr [r15], xmm0
0x18002bea3  test    rbp, rbp
0x18002bea6  jz      short loc_18002BEBF
0x18002bea8  mov     rax, [rdi+30h]
0x18002beac  add     rax, 10h
0x18002beb0  lea     rdx, [rax+rcx*8]; pvarSrc
0x18002beb4  mov     rcx, rbp; pvarDest
0x18002beb7  call    cs:__imp_PropVariantCopy
0x18002bebd  mov     ebx, eax
0x18002bebf  lea     rcx, [rdi+8]; lpCriticalSection
0x18002bec3  call    cs:__imp_LeaveCriticalSection
0x18002bec9  mov     eax, ebx
0x18002becb  add     rsp, 28h
0x18002becf  pop     r15
0x18002bed1  pop     r14
0x18002bed3  pop     rdi
0x18002bed4  pop     rsi
0x18002bed5  pop     rbp
0x18002bed6  pop     rbx
0x18002bed7  retn
```
