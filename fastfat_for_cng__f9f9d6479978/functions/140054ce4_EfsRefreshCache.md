# EfsRefreshCache

- ea: `0x140054ce4`
- end: `0x140054e55`
- name: `EfsRefreshCache`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14005202c`

## callees

- `0x14000b5d0`
- `0x14000c680`
- `0x140054ce4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140054dda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054dda`
- `ntoskrnl!ExReleaseFastMutex` at `0x140054e3b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140054e3b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140054d11`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140054d11`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140054df9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140054df9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140054d65`
- `ntoskrnl!ExAcquireFastMutex` at `0x140054d65`

## pseudocode

```c
__int64 __fastcall EfsRefreshCache(__int128 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  __int128 v12; // xmm0
  __int64 v13; // rdx
  __int64 v14; // rsi
  __int64 *v15; // rbp
  __int64 v16; // rcx
  __int64 **v17; // rax

  v8 = MEMORY[0xFFFFF78000000014];
  v9 = ExAllocateFromPagedLookasideList(&stru_140017680);
  v10 = v9;
  if ( !v9 )
    return 3221225626LL;
  memset(v9, 0, 0x40u);
  v12 = *a1;
  v10[2] = a2;
  v10[3] = a3;
  *(_OWORD *)v10 = v12;
  v10[4] = a4;
  v10[5] = v8;
  ExAcquireFastMutex(&stru_140017710);
  v13 = qword_140017700;
  if ( (__int64 *)qword_140017700 != &qword_140017700 )
  {
    do
    {
      v14 = v13 - 48;
      v15 = *(__int64 **)v13;
      if ( v8 - *(_QWORD *)(v13 - 48 + 40) > (unsigned int)dword_1400175C4 )
        goto LABEL_18;
      v16 = *(_QWORD *)v14 - *(_QWORD *)a1;
      if ( *(_QWORD *)v14 == *(_QWORD *)a1 )
        v16 = *(_QWORD *)(v14 + 8) - *((_QWORD *)a1 + 1);
      if ( !v16 )
      {
LABEL_18:
        if ( v15[1] != v13 )
          goto LABEL_15;
        v17 = *(__int64 ***)(v13 + 8);
        if ( *v17 != (__int64 *)v13 )
          goto LABEL_15;
        *v17 = v15;
        v15[1] = (__int64)v17;
        ExFreePoolWithTag(*(PVOID *)(v14 + 16), 0);
        SrpDeleteEnterpriseId(*(_QWORD *)(v14 + 24));
        ExFreeToPagedLookasideList(&stru_140017680, (PVOID)v14);
      }
      v13 = (__int64)v15;
    }
    while ( v15 != &qword_140017700 );
    v13 = qword_140017700;
  }
  if ( *(__int64 **)(v13 + 8) != &qword_140017700 )
LABEL_15:
    __fastfail(3u);
  v10[6] = v13;
  v10[7] = &qword_140017700;
  *(_QWORD *)(v13 + 8) = v10 + 6;
  qword_140017700 = (__int64)(v10 + 6);
  ExReleaseFastMutex(&stru_140017710);
  return 0;
}

```

## disassembly

```asm
0x140054ce4  push    rbx
0x140054ce6  push    rbp
0x140054ce7  push    rsi
0x140054ce8  push    rdi
0x140054ce9  push    r14
0x140054ceb  push    r15
0x140054ced  sub     rsp, 28h
0x140054cf1  mov     r14, rcx
0x140054cf4  mov     rbx, 0FFFFF78000000014h
0x140054cfe  lea     rcx, stru_140017680; Lookaside
0x140054d05  mov     rsi, r9
0x140054d08  mov     rbp, r8
0x140054d0b  mov     r15, rdx
0x140054d0e  mov     rbx, [rbx]
0x140054d11  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140054d18  nop     dword ptr [rax+rax+00h]
0x140054d1d  mov     rdi, rax
0x140054d20  test    rax, rax
0x140054d23  jnz     short loc_140054D38
0x140054d25  mov     eax, 0C000009Ah
0x140054d2a  add     rsp, 28h
0x140054d2e  pop     r15
0x140054d30  pop     r14
0x140054d32  pop     rdi
0x140054d33  pop     rsi
0x140054d34  pop     rbp
0x140054d35  pop     rbx
0x140054d36  retn
0x140054d38  xor     edx, edx; Val
0x140054d3a  mov     rcx, rdi; void *
0x140054d3d  lea     r8d, [rdx+40h]; Size
0x140054d41  call    memset
0x140054d46  movups  xmm0, xmmword ptr [r14]
0x140054d4a  lea     rcx, stru_140017710; FastMutex
0x140054d51  mov     [rdi+10h], r15
0x140054d55  mov     [rdi+18h], rbp
0x140054d59  movdqu  xmmword ptr [rdi], xmm0
0x140054d5d  mov     [rdi+20h], rsi
0x140054d61  mov     [rdi+28h], rbx
0x140054d65  call    cs:__imp_ExAcquireFastMutex
0x140054d6c  nop     dword ptr [rax+rax+00h]
0x140054d71  mov     rdx, cs:qword_140017700
0x140054d78  lea     r15, qword_140017700
0x140054d7f  cmp     rdx, r15
0x140054d82  jz      loc_140054E18
0x140054d88  mov     eax, cs:dword_1400175C4
0x140054d8e  lea     rsi, [rdx-30h]
0x140054d92  mov     rbp, [rdx]
0x140054d95  mov     rcx, rbx
0x140054d98  sub     rcx, [rsi+28h]
0x140054d9c  cmp     rcx, rax
0x140054d9f  jg      short loc_140054DB6
0x140054da1  mov     rcx, [rsi]
0x140054da4  sub     rcx, [r14]
0x140054da7  jnz     short loc_140054DB1
0x140054da9  mov     rcx, [rsi+8]
0x140054dad  sub     rcx, [r14+8]
0x140054db1  test    rcx, rcx
0x140054db4  jnz     short loc_140054E05
0x140054db6  cmp     [rbp+8], rdx
0x140054dba  jnz     loc_140054E4E
0x140054dc0  mov     rax, [rdx+8]
0x140054dc4  cmp     [rax], rdx
0x140054dc7  jnz     loc_140054E4E
0x140054dcd  mov     [rax], rbp
0x140054dd0  xor     edx, edx; Tag
0x140054dd2  mov     [rbp+8], rax
0x140054dd6  mov     rcx, [rsi+10h]; P
0x140054dda  call    cs:__imp_ExFreePoolWithTag
0x140054de1  nop     dword ptr [rax+rax+00h]
0x140054de6  mov     rcx, [rsi+18h]
0x140054dea  call    SrpDeleteEnterpriseId
0x140054def  mov     rdx, rsi; Entry
0x140054df2  lea     rcx, stru_140017680; Lookaside
0x140054df9  call    cs:__imp_ExFreeToPagedLookasideList
0x140054e00  nop     dword ptr [rax+rax+00h]
0x140054e05  mov     rdx, rbp
0x140054e08  cmp     rbp, r15
0x140054e0b  jnz     loc_140054D88
0x140054e11  mov     rdx, cs:qword_140017700
0x140054e18  cmp     [rdx+8], r15
0x140054e1c  jnz     short loc_140054E4E
0x140054e1e  lea     rax, [rdi+30h]
0x140054e22  mov     [rax], rdx
0x140054e25  lea     rcx, stru_140017710; FastMutex
0x140054e2c  mov     [rax+8], r15
0x140054e30  mov     [rdx+8], rax
0x140054e34  mov     cs:qword_140017700, rax
0x140054e3b  call    cs:__imp_ExReleaseFastMutex
0x140054e42  nop     dword ptr [rax+rax+00h]
0x140054e47  xor     eax, eax
0x140054e49  jmp     loc_140054D2A
0x140054e4e  mov     ecx, 3
0x140054e53  int     29h; Win8: RtlFailFast(ecx)
```
