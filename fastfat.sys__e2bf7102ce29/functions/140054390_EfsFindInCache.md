# EfsFindInCache

- ea: `0x140054390`
- end: `0x14005447a`
- name: `EfsFindInCache`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14005202c`

## callees

- `0x14000a360`
- `0x140054390`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14005445a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005445a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400543c0`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400543c0`
- `ntoskrnl!RtlEqualSid` at `0x140054418`
- `ntoskrnl!RtlEqualSid` at `0x140054418`

## pseudocode

```c
char __fastcall EfsFindInCache(_QWORD *a1, void **a2, __int64 a3, __int64 a4)
{
  void *v4; // r15
  __int64 v8; // rbx
  __int64 *v9; // rsi
  char v10; // di
  __int64 v11; // rcx
  __int64 v12; // r8

  v4 = *a2;
  v8 = MEMORY[0xFFFFF78000000014];
  ExAcquireFastMutex(&stru_140017710);
  v9 = (__int64 *)qword_140017700;
  v10 = 0;
  if ( (__int64 *)qword_140017700 != &qword_140017700 )
  {
    while ( v9 != &qword_140017700 )
    {
      v11 = *(v9 - 6) - *a1;
      if ( !v11 )
        v11 = *(v9 - 5) - a1[1];
      if ( !v11 && v8 - *(v9 - 1) <= (unsigned int)dword_1400175C4 )
      {
        if ( RtlEqualSid(v4, *(PSID *)*(v9 - 4)) )
        {
          v12 = *(v9 - 3);
          if ( !v12 || (unsigned __int8)CanCallerAccessCacheEntry(a3, a4, v12, *(v9 - 2)) )
          {
            v10 = 1;
            break;
          }
        }
      }
      v9 = (__int64 *)*v9;
    }
  }
  ExReleaseFastMutex(&stru_140017710);
  return v10;
}

```

## disassembly

```asm
0x140054390  push    rbx
0x140054392  push    rsi
0x140054393  push    rdi
0x140054394  push    r12
0x140054396  push    r13
0x140054398  push    r14
0x14005439a  push    r15
0x14005439c  sub     rsp, 20h
0x1400543a0  mov     r15, [rdx]
0x1400543a3  mov     r14, rcx
0x1400543a6  mov     rbx, 0FFFFF78000000014h
0x1400543b0  lea     rcx, stru_140017710; FastMutex
0x1400543b7  mov     r12, r9
0x1400543ba  mov     r13, r8
0x1400543bd  mov     rbx, [rbx]
0x1400543c0  call    cs:__imp_ExAcquireFastMutex
0x1400543c7  nop     dword ptr [rax+rax+00h]
0x1400543cc  mov     rsi, cs:qword_140017700
0x1400543d3  lea     rax, qword_140017700
0x1400543da  xor     edi, edi
0x1400543dc  cmp     rsi, rax
0x1400543df  jz      short loc_140054453
0x1400543e1  cmp     rsi, rax
0x1400543e4  jz      short loc_140054453
0x1400543e6  mov     rcx, [rsi-30h]
0x1400543ea  sub     rcx, [r14]
0x1400543ed  jnz     short loc_1400543F7
0x1400543ef  mov     rcx, [rsi-28h]
0x1400543f3  sub     rcx, [r14+8]
0x1400543f7  test    rcx, rcx
0x1400543fa  jnz     short loc_140054444
0x1400543fc  mov     eax, cs:dword_1400175C4
0x140054402  mov     rcx, rbx
0x140054405  sub     rcx, [rsi-8]
0x140054409  cmp     rcx, rax
0x14005440c  jg      short loc_140054444
0x14005440e  mov     rdx, [rsi-20h]
0x140054412  mov     rcx, r15; Sid1
0x140054415  mov     rdx, [rdx]; Sid2
0x140054418  call    cs:__imp_RtlEqualSid
0x14005441f  nop     dword ptr [rax+rax+00h]
0x140054424  test    al, al
0x140054426  jz      short loc_140054444
0x140054428  mov     r8, [rsi-18h]
0x14005442c  test    r8, r8
0x14005442f  jz      short loc_140054450
0x140054431  mov     r9, [rsi-10h]
0x140054435  mov     rdx, r12
0x140054438  mov     rcx, r13
0x14005443b  call    CanCallerAccessCacheEntry
0x140054440  test    al, al
0x140054442  jnz     short loc_140054450
0x140054444  mov     rsi, [rsi]
0x140054447  lea     rax, qword_140017700
0x14005444e  jmp     short loc_1400543E1
0x140054450  mov     dil, 1
0x140054453  lea     rcx, stru_140017710; FastMutex
0x14005445a  call    cs:__imp_ExReleaseFastMutex
0x140054461  nop     dword ptr [rax+rax+00h]
0x140054466  mov     al, dil
0x140054469  add     rsp, 20h
0x14005446d  pop     r15
0x14005446f  pop     r14
0x140054471  pop     r13
0x140054473  pop     r12
0x140054475  pop     rdi
0x140054476  pop     rsi
0x140054477  pop     rbx
0x140054478  retn
```
