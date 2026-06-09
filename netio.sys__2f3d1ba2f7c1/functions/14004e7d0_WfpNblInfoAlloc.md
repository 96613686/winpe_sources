# WfpNblInfoAlloc

- ea: `0x14004e7d0`
- end: `0x14004e930`
- name: `WfpNblInfoAlloc`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140066568`

## callees

- `0x140017580`
- `0x14001771c`
- `0x14004e7d0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x14004e828`
- `ntoskrnl!MmBadPointer` at `0x14004e8bc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004e902`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004e902`

## pseudocode

```c
__int64 __fastcall WfpNblInfoAlloc(__int64 a1)
{
  signed __int64 v1; // rbp
  int v4; // ecx
  unsigned __int64 v5; // rbx
  char *v6; // rdi
  _QWORD *v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 224);
  v7 = 0;
  if ( (v1 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    return 0;
  v4 = WfpAllocateFromPerProcessorLookasideList((__int64)gWfpNblInfoPool, &v7);
  if ( v4 >= 0 )
  {
    v5 = (unsigned __int64)v7;
    *v7 = 1852859991;
    *(_QWORD *)(v5 + 8) = 0;
    *(_QWORD *)(v5 + 16) = 0;
    *(_QWORD *)(v5 + 24) = 0;
    *(_QWORD *)(v5 + 32) = a1;
    *(_DWORD *)(v5 + 40) = 0;
    *(_DWORD *)(v5 + 632) = 0;
    *(_QWORD *)(v5 + 624) = 0;
    *(_BYTE *)(v5 + 676) = 0;
    *(_WORD *)(v5 + 48) = 1;
    *(_WORD *)(v5 + 120) = 1;
    *(_WORD *)(v5 + 192) = 1;
    *(_WORD *)(v5 + 264) = 1;
    *(_WORD *)(v5 + 336) = 1;
    *(_WORD *)(v5 + 408) = 1;
    *(_WORD *)(v5 + 480) = 1;
    *(_WORD *)(v5 + 552) = 1;
  }
  else
  {
    v5 = (unsigned __int64)MmBadPointer;
  }
  if ( v1 != _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 224), v5 | v1 & 3, v1) )
  {
    if ( (PVOID)v5 != MmBadPointer )
    {
      *(_DWORD *)v5 = -1;
      v6 = (char *)gWfpNblInfoPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v6[176] )
        PplpLazyInitializeLookasideList((__int64)gWfpNblInfoPool, (__int64)(v6 + 64));
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v6 + 64), (PVOID)v5);
    }
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14004e7d0  push    rbp
0x14004e7d2  push    rsi
0x14004e7d3  push    r14
0x14004e7d5  sub     rsp, 20h
0x14004e7d9  mov     rbp, [rcx+0E0h]
0x14004e7e0  xor     r14d, r14d
0x14004e7e3  mov     [rsp+38h+arg_0], r14
0x14004e7e8  mov     rsi, rcx
0x14004e7eb  test    rbp, 0FFFFFFFFFFFFFFFCh
0x14004e7f2  jz      short loc_14004E800
0x14004e7f4  xor     eax, eax
0x14004e7f6  add     rsp, 20h
0x14004e7fa  pop     r14
0x14004e7fc  pop     rsi
0x14004e7fd  pop     rbp
0x14004e7fe  retn
0x14004e800  mov     rcx, cs:gWfpNblInfoPool
0x14004e807  lea     rdx, [rsp+38h+arg_0]
0x14004e80c  mov     [rsp+38h+arg_8], rbx
0x14004e811  mov     [rsp+38h+arg_10], rdi
0x14004e816  mov     rdi, rbp
0x14004e819  and     edi, 3
0x14004e81c  call    WfpAllocateFromPerProcessorLookasideList
0x14004e821  mov     rcx, rax
0x14004e824  test    eax, eax
0x14004e826  jns     short loc_14004E834
0x14004e828  mov     rax, cs:MmBadPointer
0x14004e82f  mov     rbx, [rax]
0x14004e832  jmp     short loc_14004E8AB
0x14004e834  mov     rbx, [rsp+38h+arg_0]
0x14004e839  mov     qword ptr [rbx], 6E706657h
0x14004e840  mov     [rbx+8], r14
0x14004e844  mov     [rbx+10h], r14
0x14004e848  mov     [rbx+18h], r14
0x14004e84c  mov     [rbx+20h], rsi
0x14004e850  mov     [rbx+28h], r14d
0x14004e854  mov     [rbx+278h], r14d
0x14004e85b  mov     [rbx+270h], r14
0x14004e862  mov     [rbx+2A4h], r14b
0x14004e869  mov     word ptr [rbx+30h], 1
0x14004e86f  mov     word ptr [rbx+78h], 1
0x14004e875  mov     word ptr [rbx+0C0h], 1
0x14004e87e  mov     word ptr [rbx+108h], 1
0x14004e887  mov     word ptr [rbx+150h], 1
0x14004e890  mov     word ptr [rbx+198h], 1
0x14004e899  mov     word ptr [rbx+1E0h], 1
0x14004e8a2  mov     word ptr [rbx+228h], 1
0x14004e8ab  or      rdi, rbx
0x14004e8ae  mov     rax, rbp
0x14004e8b1  lock cmpxchg [rsi+0E0h], rdi
0x14004e8ba  jz      short loc_14004E911
0x14004e8bc  mov     rax, cs:MmBadPointer
0x14004e8c3  cmp     rbx, [rax]
0x14004e8c6  jz      short loc_14004E90E
0x14004e8c8  mov     dword ptr [rbx], 0FFFFFFFFh
0x14004e8ce  mov     eax, gs:1A4h
0x14004e8d6  mov     rcx, cs:gWfpNblInfoPool
0x14004e8dd  lea     edi, [rax+1]
0x14004e8e0  shl     rdi, 7
0x14004e8e4  add     rdi, rcx
0x14004e8e7  movzx   eax, byte ptr [rdi+0B0h]
0x14004e8ee  test    al, al
0x14004e8f0  jnz     short loc_14004E8FB
0x14004e8f2  lea     rdx, [rdi+40h]
0x14004e8f6  call    PplpLazyInitializeLookasideList
0x14004e8fb  mov     rdx, rbx; Entry
0x14004e8fe  lea     rcx, [rdi+40h]; Lookaside
0x14004e902  call    cs:__imp_ExFreeToLookasideListEx
0x14004e909  nop     dword ptr [rax+rax+00h]
0x14004e90e  mov     ecx, r14d
0x14004e911  mov     rdi, [rsp+38h+arg_10]
0x14004e916  mov     eax, ecx
0x14004e918  mov     rbx, [rsp+38h+arg_8]
0x14004e91d  add     rsp, 20h
0x14004e921  pop     r14
0x14004e923  pop     rsi
0x14004e924  pop     rbp
0x14004e925  retn
```
