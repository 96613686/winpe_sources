# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18007a440`
- end: `0x18007a4e3`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800781c8`
- `0x18007a440`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a458`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a483`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetGUID(__int64 a1, _DWORD *a2, _OWORD *a3)
{
  PROPVARIANT *Item; // rsi
  unsigned int v7; // ebx
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v8 = CoTaskMemAlloc(0x10u);
    Item->hVal.QuadPart = (LONGLONG)v8;
    if ( v8 )
    {
      Item->vt = 72;
      v7 = 0;
      *v8 = *a3;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v7 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x18007a440  push    rbx
0x18007a442  push    rbp
0x18007a443  push    rsi
0x18007a444  push    rdi
0x18007a445  push    r14
0x18007a447  sub     rsp, 20h
0x18007a44b  mov     rdi, rcx
0x18007a44e  mov     r14, r8
0x18007a451  add     rcx, 8; lpCriticalSection
0x18007a455  mov     rbx, rdx
0x18007a458  call    cs:__imp_EnterCriticalSection
0x18007a45f  nop     dword ptr [rax+rax+00h]
0x18007a464  mov     rdx, rbx
0x18007a467  mov     rcx, rdi
0x18007a46a  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18007a46f  mov     rsi, rax
0x18007a472  test    rax, rax
0x18007a475  jnz     short loc_18007A47E
0x18007a477  mov     ebx, 8007000Eh
0x18007a47c  jmp     short loc_18007A4C5
0x18007a47e  mov     ecx, 10h; cb
0x18007a483  call    cs:__imp_CoTaskMemAlloc
0x18007a48a  nop     dword ptr [rax+rax+00h]
0x18007a48f  mov     [rsi+8], rax
0x18007a493  test    rax, rax
0x18007a496  jnz     short loc_18007A4AF
0x18007a498  mov     rax, [rdi]
0x18007a49b  mov     rdx, rbx
0x18007a49e  mov     rcx, rdi
0x18007a4a1  mov     rax, [rax+98h]
0x18007a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4ad  jmp     short loc_18007A477
0x18007a4af  mov     word ptr [rsi], 48h ; 'H'
0x18007a4b4  xor     ebx, ebx
0x18007a4b6  movups  xmm0, xmmword ptr [r14]
0x18007a4ba  movdqu  xmmword ptr [rax], xmm0
0x18007a4be  mov     dword ptr [rdi+40h], 1
0x18007a4c5  lea     rcx, [rdi+8]; lpCriticalSection
0x18007a4c9  call    cs:__imp_LeaveCriticalSection
0x18007a4d0  nop     dword ptr [rax+rax+00h]
0x18007a4d5  mov     eax, ebx
0x18007a4d7  add     rsp, 20h
0x18007a4db  pop     r14
0x18007a4dd  pop     rdi
0x18007a4de  pop     rsi
0x18007a4df  pop     rbp
0x18007a4e0  pop     rbx
0x18007a4e1  retn
```
