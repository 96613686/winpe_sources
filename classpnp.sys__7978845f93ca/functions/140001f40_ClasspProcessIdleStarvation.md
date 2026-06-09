# ClasspProcessIdleStarvation

- ea: `0x140001f40`
- end: `0x1400020e0`
- name: `ClasspProcessIdleStarvation`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001e70`

## callees

- `0x140001f40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f60`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f60`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140001fa7`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002008`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400020a7`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140001fa7`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002008`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400020a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000204a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000204a`

## pseudocode

```c
__int64 __fastcall ClasspProcessIdleStarvation(__int64 a1)
{
  unsigned int v2; // esi
  KIRQL v3; // bp
  __int64 v4; // r14
  ULONG64 v5; // rcx
  ULONG64 v6; // rax
  unsigned __int8 v7; // si
  ULONG64 v8; // rax
  ULONG64 v9; // rdx
  _QWORD *v11; // r12
  __int64 v12; // rax
  _QWORD *v13; // rcx
  unsigned __int64 QpcTimeStamp; // [rsp+50h] [rbp+8h] BYREF

  v2 = 1;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 3672));
  do
  {
    v4 = a1 + 16 * (v2 + 230LL);
    if ( *(_QWORD *)v4 != v4 )
    {
      QpcTimeStamp = 0;
      v5 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
      v6 = *(_QWORD *)(a1 + 8LL * v2 + 3712);
      if ( v5 < v6 || (v5 - v6) / 0x2710 >= *(unsigned __int16 *)(a1 + 3860) )
      {
        v11 = *(_QWORD **)v4;
        if ( *(_QWORD *)(*(_QWORD *)v4 + 8LL) != v4
          || (v12 = *v11, *(_QWORD **)(*v11 + 8LL) != v11)
          || (*(_QWORD *)v4 = v12,
              *(_QWORD *)(v12 + 8) = v4,
              QpcTimeStamp = 0,
              *(_QWORD *)(a1 + 8LL * v2 + 3712) = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp),
              v13 = *(_QWORD **)(a1 + 3688),
              *v13 != a1 + 3680) )
        {
          __fastfail(3u);
        }
        *v11 = a1 + 3680;
        v11[1] = v13;
        *v13 = v11;
        *(_QWORD *)(a1 + 3688) = v11;
      }
    }
    ++v2;
  }
  while ( v2 < 2 );
  v7 = 0;
  if ( *(_QWORD *)(a1 + 3680) != a1 + 3680 )
  {
    QpcTimeStamp = 0;
    v8 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
    v9 = *(_QWORD *)(a1 + 3712);
    if ( v8 < v9 || (v8 - v9) / 0x2710 >= *(unsigned __int16 *)(a1 + 3860) )
      v7 = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 3672), v3);
  return v7;
}

```

## disassembly

```asm
0x140001f40  mov     [rsp+arg_10], rbx
0x140001f45  mov     [rsp+arg_18], rbp
0x140001f4a  push    rsi
0x140001f4b  push    rdi
0x140001f4c  push    r13
0x140001f4e  push    r14
0x140001f50  push    r15
0x140001f52  sub     rsp, 20h
0x140001f56  mov     rbx, rcx
0x140001f59  add     rcx, 0E58h; SpinLock
0x140001f60  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001f67  nop     dword ptr [rax+rax+00h]
0x140001f6c  mov     esi, 1
0x140001f71  mov     [rsp+48h+arg_8], r12
0x140001f76  movzx   ebp, al
0x140001f79  mov     r13, 346DC5D63886594Bh
0x140001f83  mov     r15d, esi
0x140001f86  lea     r14, [r15+0E6h]
0x140001f8d  shl     r14, 4
0x140001f91  add     r14, rbx
0x140001f94  cmp     [r14], r14
0x140001f97  jz      short loc_140001FE4
0x140001f99  lea     rcx, [rsp+48h+QpcTimeStamp]; QpcTimeStamp
0x140001f9e  mov     [rsp+48h+QpcTimeStamp], 0
0x140001fa7  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140001fae  nop     dword ptr [rax+rax+00h]
0x140001fb3  mov     rcx, rax
0x140001fb6  mov     rax, [rbx+r15*8+0E80h]
0x140001fbe  cmp     rcx, rax
0x140001fc1  jb      loc_140002077
0x140001fc7  sub     rcx, rax
0x140001fca  mov     rax, r13
0x140001fcd  mul     rcx
0x140001fd0  movzx   eax, word ptr [rbx+0F14h]
0x140001fd7  shr     rdx, 0Bh
0x140001fdb  cmp     rdx, rax
0x140001fde  jnb     loc_140002077
0x140001fe4  inc     esi
0x140001fe6  cmp     esi, 2
0x140001fe9  jb      short loc_140001F83
0x140001feb  xor     sil, sil
0x140001fee  lea     rcx, [rbx+0E60h]
0x140001ff5  cmp     [rcx], rcx
0x140001ff8  jz      short loc_14000203F
0x140001ffa  lea     rcx, [rsp+48h+QpcTimeStamp]; QpcTimeStamp
0x140001fff  mov     [rsp+48h+QpcTimeStamp], 0
0x140002008  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x14000200f  nop     dword ptr [rax+rax+00h]
0x140002014  mov     rdx, [rbx+0E80h]
0x14000201b  mov     rcx, rax
0x14000201e  cmp     rax, rdx
0x140002021  jb      short loc_14000203C
0x140002023  sub     rcx, rdx
0x140002026  mov     rax, r13
0x140002029  mul     rcx
0x14000202c  movzx   eax, word ptr [rbx+0F14h]
0x140002033  shr     rdx, 0Bh
0x140002037  cmp     rdx, rax
0x14000203a  jb      short loc_14000203F
0x14000203c  mov     sil, 1
0x14000203f  movzx   edx, bpl; NewIrql
0x140002043  lea     rcx, [rbx+0E58h]; SpinLock
0x14000204a  call    cs:__imp_KeReleaseSpinLock
0x140002051  nop     dword ptr [rax+rax+00h]
0x140002056  mov     r12, [rsp+48h+arg_8]
0x14000205b  movzx   eax, sil
0x14000205f  mov     rbx, [rsp+48h+arg_10]
0x140002064  mov     rbp, [rsp+48h+arg_18]
0x140002069  add     rsp, 20h
0x14000206d  pop     r15
0x14000206f  pop     r14
0x140002071  pop     r13
0x140002073  pop     rdi
0x140002074  pop     rsi
0x140002075  retn
0x140002077  mov     r12, [r14]
0x14000207a  cmp     [r12+8], r14
0x14000207f  jz      short loc_140002088
0x140002081  mov     ecx, 3
0x140002086  int     29h; Win8: RtlFailFast(ecx)
0x140002088  mov     rax, [r12]
0x14000208c  cmp     [rax+8], r12
0x140002090  jnz     short loc_140002081
0x140002092  mov     [r14], rax
0x140002095  lea     rcx, [rsp+48h+QpcTimeStamp]; QpcTimeStamp
0x14000209a  mov     [rax+8], r14
0x14000209e  mov     [rsp+48h+QpcTimeStamp], 0
0x1400020a7  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1400020ae  nop     dword ptr [rax+rax+00h]
0x1400020b3  mov     [rbx+r15*8+0E80h], rax
0x1400020bb  lea     rax, [rbx+0E60h]
0x1400020c2  mov     rcx, [rax+8]
0x1400020c6  cmp     [rcx], rax
0x1400020c9  jnz     short loc_140002081
0x1400020cb  mov     [r12], rax
0x1400020cf  mov     [r12+8], rcx
0x1400020d4  mov     [rcx], r12
0x1400020d7  mov     [rax+8], r12
0x1400020db  jmp     loc_140001FE4
```
