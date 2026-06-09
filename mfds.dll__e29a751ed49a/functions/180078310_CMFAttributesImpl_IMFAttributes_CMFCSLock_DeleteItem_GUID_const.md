# CMFAttributesImpl<IMFAttributes,CMFCSLock>::DeleteItem(_GUID const &)

- ea: `0x180078310`
- end: `0x1800783b9`
- name: `?DeleteItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@@Z`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010350`
- `0x180078310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180078385`
- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180078385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007839f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007839f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078325`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078325`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180078360`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180078360`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::DeleteItem(__int64 a1, __int64 a2)
{
  __int64 i; // rbx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 60); i = (unsigned int)(i + 1) )
  {
    if ( (unsigned __int8)_(a2, *(_QWORD *)(a1 + 48) + 40 * i) )
    {
      PropVariantClear((PROPVARIANT *)(*(_QWORD *)(a1 + 48) + 16LL + 40 * i));
      memmove(
        (void *)(*(_QWORD *)(a1 + 48) + 40 * i),
        (const void *)(*(_QWORD *)(a1 + 48) + 40 * i + 40),
        40LL * (unsigned int)(*(_DWORD *)(a1 + 60) + ~(_DWORD)i));
      --*(_DWORD *)(a1 + 60);
      *(_DWORD *)(a1 + 64) = 1;
      break;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return 0;
}

```

## disassembly

```asm
0x180078310  push    rbx
0x180078312  push    rbp
0x180078313  push    rsi
0x180078314  push    rdi
0x180078315  push    r14
0x180078317  sub     rsp, 20h
0x18007831b  mov     rdi, rcx
0x18007831e  mov     r14, rdx
0x180078321  add     rcx, 8; lpCriticalSection
0x180078325  call    cs:__imp_EnterCriticalSection
0x18007832c  nop     dword ptr [rax+rax+00h]
0x180078331  xor     ebx, ebx
0x180078333  cmp     ebx, [rdi+3Ch]
0x180078336  jnb     short loc_18007839B
0x180078338  mov     rax, [rdi+30h]
0x18007833c  lea     rbp, [rbx+rbx*4]
0x180078340  mov     rcx, r14
0x180078343  lea     rdx, [rax+rbp*8]
0x180078347  call    __
0x18007834c  test    al, al
0x18007834e  jnz     short loc_180078354
0x180078350  inc     ebx
0x180078352  jmp     short loc_180078333
0x180078354  mov     rcx, [rdi+30h]
0x180078358  add     rcx, 10h
0x18007835c  lea     rcx, [rcx+rbp*8]; pvar
0x180078360  call    cs:__imp_PropVariantClear
0x180078367  nop     dword ptr [rax+rax+00h]
0x18007836c  mov     rax, [rdi+30h]
0x180078370  not     ebx
0x180078372  add     ebx, [rdi+3Ch]
0x180078375  lea     rcx, [rax+rbp*8]; void *
0x180078379  lea     r8, [rbx+rbx*4]
0x18007837d  shl     r8, 3; Size
0x180078381  lea     rdx, [rcx+28h]; Src
0x180078385  call    cs:__imp_memmove
0x18007838c  nop     dword ptr [rax+rax+00h]
0x180078391  dec     dword ptr [rdi+3Ch]
0x180078394  mov     dword ptr [rdi+40h], 1
0x18007839b  lea     rcx, [rdi+8]; lpCriticalSection
0x18007839f  call    cs:__imp_LeaveCriticalSection
0x1800783a6  nop     dword ptr [rax+rax+00h]
0x1800783ab  xor     eax, eax
0x1800783ad  add     rsp, 20h
0x1800783b1  pop     r14
0x1800783b3  pop     rdi
0x1800783b4  pop     rsi
0x1800783b5  pop     rbp
0x1800783b6  pop     rbx
0x1800783b7  retn
```
