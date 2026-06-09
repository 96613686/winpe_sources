# PsmpSubscriptionCreate

- ea: `0x1800244e8`
- end: `0x1800245d6`
- name: `PsmpSubscriptionCreate`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002c5d0`

## callees

- `0x18000436c`
- `0x180012c70`
- `0x18001c10c`
- `0x1800244e8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024591`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024591`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800245c0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800245c0`

## pseudocode

```c
__int64 __fastcall PsmpSubscriptionCreate(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *Heap; // rax
  _QWORD *v10; // rdi
  unsigned __int64 v11; // r10
  signed __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rsi
  _QWORD *v15; // rcx
  __int64 v16; // rbx

  if ( (unsigned __int64)PsmpNotificationSubscriptionIdCounter > 0x8000000000000000uLL )
    return 3221225621LL;
  Heap = PsmpAllocateHeap(0x130u);
  v10 = Heap;
  if ( !Heap )
    return 3221225495LL;
  memset_0(Heap, 0, 0x130u);
  v10[4] = a1;
  v11 = 1;
  *((_DWORD *)v10 + 10) = a2;
  if ( a3 )
  {
    *((_DWORD *)v10 + 11) = 1;
    RtlStringCchCopyW(v10 + 6, 128, a3);
  }
  *((_DWORD *)v10 + 3) = v11;
  v12 = _InterlockedExchangeAdd64(&PsmpNotificationSubscriptionIdCounter, v11);
  v13 = v10[4];
  *v10 = v11 + v12;
  v14 = v13 + 40;
  RtlAcquireSRWLockExclusive(v13 + 40);
  v15 = *(_QWORD **)(v13 + 24);
  v16 = v13 + 16;
  if ( *v15 != v16 )
    __fastfail(3u);
  v10[3] = v15;
  v10[2] = v16;
  *v15 = v10 + 2;
  *(_QWORD *)(v16 + 8) = v10 + 2;
  RtlReleaseSRWLockExclusive(v14);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x1800244e8  push    rbx
0x1800244ea  push    rbp
0x1800244eb  push    rsi
0x1800244ec  push    rdi
0x1800244ed  push    r14
0x1800244ef  sub     rsp, 20h
0x1800244f3  mov     rax, cs:PsmpNotificationSubscriptionIdCounter
0x1800244fa  mov     rbp, rcx
0x1800244fd  mov     rcx, 8000000000000000h
0x180024507  mov     r14, r9
0x18002450a  mov     rbx, r8
0x18002450d  mov     esi, edx
0x18002450f  cmp     rax, rcx
0x180024512  jbe     short loc_18002451E
0x180024514  mov     eax, 0C0000095h
0x180024519  jmp     loc_1800245CB
0x18002451e  mov     ecx, 130h
0x180024523  call    PsmpAllocateHeap
0x180024528  mov     rdi, rax
0x18002452b  test    rax, rax
0x18002452e  jnz     short loc_18002453A
0x180024530  mov     eax, 0C0000017h
0x180024535  jmp     loc_1800245CB
0x18002453a  xor     edx, edx; Val
0x18002453c  mov     r8d, 130h; Size
0x180024542  mov     rcx, rdi; void *
0x180024545  call    memset_0
0x18002454a  mov     [rdi+20h], rbp
0x18002454e  mov     r10d, 1
0x180024554  mov     [rdi+28h], esi
0x180024557  test    rbx, rbx
0x18002455a  jz      short loc_180024570
0x18002455c  lea     rcx, [rdi+30h]
0x180024560  mov     [rdi+2Ch], r10d
0x180024564  mov     r8, rbx
0x180024567  lea     edx, [r10+7Fh]
0x18002456b  call    RtlStringCchCopyW
0x180024570  mov     [rdi+0Ch], r10d
0x180024574  mov     rax, r10
0x180024577  lock xadd cs:PsmpNotificationSubscriptionIdCounter, rax
0x180024580  mov     rbx, [rdi+20h]
0x180024584  add     rax, r10
0x180024587  mov     [rdi], rax
0x18002458a  lea     rsi, [rbx+28h]
0x18002458e  mov     rcx, rsi
0x180024591  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024597  mov     rcx, [rbx+18h]
0x18002459b  add     rbx, 10h
0x18002459f  cmp     [rcx], rbx
0x1800245a2  jz      short loc_1800245AB
0x1800245a4  mov     ecx, 3
0x1800245a9  int     29h; Win8: RtlFailFast(ecx)
0x1800245ab  lea     rax, [rdi+10h]
0x1800245af  mov     [rax+8], rcx
0x1800245b3  mov     [rax], rbx
0x1800245b6  mov     [rcx], rax
0x1800245b9  mov     rcx, rsi
0x1800245bc  mov     [rbx+8], rax
0x1800245c0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800245c6  xor     eax, eax
0x1800245c8  mov     [r14], rdi
0x1800245cb  add     rsp, 20h
0x1800245cf  pop     r14
0x1800245d1  pop     rdi
0x1800245d2  pop     rsi
0x1800245d3  pop     rbp
0x1800245d4  pop     rbx
0x1800245d5  retn
```
