# NpRemoveDataQueueEntry

- ea: `0x140010310`
- end: `0x1400104b1`
- name: `NpRemoveDataQueueEntry`
- size: `417`
- prototype: `__int64 __fastcall(__int64 *, char, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d314`
- `0x14000e1b0`
- `0x14000f8c0`
- `0x14000fdc4`
- `0x140010290`
- `0x140010310`

## callees

- `0x140010310`
- `0x1400113b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001045b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010471`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001045b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010471`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001044a`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14001044a`

## pseudocode

```c
__int64 __fastcall NpRemoveDataQueueEntry(__int64 *a1, char a2, __int64 a3)
{
  _DWORD *v6; // rdi
  __int64 v7; // rax
  bool v8; // r15
  char *v9; // rbp
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rax

  if ( *((_DWORD *)a1 + 4) == 2 )
  {
    v10 = 0;
  }
  else
  {
    v6 = (_DWORD *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v7 = *(_QWORD *)v6, *(_DWORD **)(*(_QWORD *)v6 + 8LL) != v6) )
LABEL_30:
      __fastfail(3u);
    *a1 = v7;
    *(_QWORD *)(v7 + 8) = a1;
    *((_DWORD *)a1 + 5) -= v6[10];
    --*((_DWORD *)a1 + 6);
    v8 = *((_DWORD *)a1 + 4) == 1 && *((_DWORD *)a1 + 8) >= *((_DWORD *)a1 + 7) && v6[9];
    *((_DWORD *)a1 + 8) -= v6[9];
    if ( (__int64 *)*a1 == a1 )
    {
      *((_DWORD *)a1 + 4) = 2;
      v8 = 0;
    }
    v9 = (char *)*((_QWORD *)v6 + 3);
    v10 = *((_QWORD *)v6 + 2);
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SeDeleteClientSecurity(*((_QWORD *)v6 + 3));
      ExFreePoolWithTag(v9, 0);
    }
    if ( v10 && !_InterlockedExchange64((volatile __int64 *)(v10 + 104), 0) )
    {
      *(_QWORD *)(v10 + 144) = 0;
      v10 = 0;
    }
    if ( (_DWORD *)a1[5] == v6 )
      _interlockedbittestandset((volatile signed __int32 *)a1 + 10, 0);
    else
      ExFreePoolWithTag(v6, 0);
    if ( a2 )
    {
      v11 = *a1;
      if ( (__int64 *)*a1 != a1 )
      {
        while ( *(_DWORD *)(v11 + 32) >= 2u )
        {
          v12 = NpRemoveDataQueueEntry(a1, 0, a3);
          if ( v12 )
          {
            *(_DWORD *)(v12 + 48) = 0;
            v14 = *(_QWORD **)(a3 + 8);
            if ( *v14 != a3 )
              goto LABEL_30;
            v15 = (_QWORD *)(v12 + 168);
            *v15 = a3;
            v15[1] = v14;
            *v14 = v15;
            *(_QWORD *)(a3 + 8) = v15;
          }
          v11 = *a1;
          if ( (__int64 *)*a1 == a1 )
            break;
        }
      }
    }
    if ( v8 )
      NpCompleteStalledWrites(a1, a3);
  }
  *((_DWORD *)a1 + 9) = 0;
  return v10;
}

```

## disassembly

```asm
0x140010310  push    rbx
0x140010312  push    rbp
0x140010313  push    rsi
0x140010314  push    rdi
0x140010315  push    r13
0x140010317  push    r14
0x140010319  push    r15
0x14001031b  sub     rsp, 20h
0x14001031f  cmp     dword ptr [rcx+10h], 2
0x140010323  mov     r13, r8
0x140010326  movzx   r14d, dl
0x14001032a  mov     rbx, rcx
0x14001032d  jz      loc_140010482
0x140010333  mov     rdi, [rcx]
0x140010336  cmp     [rdi+8], rcx
0x14001033a  jnz     loc_1400104AA
0x140010340  mov     rax, [rdi]
0x140010343  cmp     [rax+8], rdi
0x140010347  jnz     loc_1400104AA
0x14001034d  mov     [rcx], rax
0x140010350  mov     [rax+8], rcx
0x140010354  mov     eax, [rdi+28h]
0x140010357  sub     [rcx+14h], eax
0x14001035a  dec     dword ptr [rcx+18h]
0x14001035d  cmp     dword ptr [rcx+10h], 1
0x140010361  jz      loc_140010407
0x140010367  xor     r15b, r15b
0x14001036a  mov     eax, [rdi+24h]
0x14001036d  sub     [rcx+20h], eax
0x140010370  cmp     [rcx], rbx
0x140010373  jnz     short loc_14001037F
0x140010375  mov     dword ptr [rcx+10h], 2
0x14001037c  xor     r15b, r15b
0x14001037f  mov     rbp, [rdi+18h]
0x140010383  mov     rsi, [rdi+10h]
0x140010387  lea     rax, [rbp-1]
0x14001038b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001038f  jbe     loc_140010447
0x140010395  xor     ebp, ebp
0x140010397  test    rsi, rsi
0x14001039a  jz      short loc_1400103AB
0x14001039c  mov     eax, ebp
0x14001039e  xchg    rax, [rsi+68h]
0x1400103a2  test    rax, rax
0x1400103a5  jz      loc_14001048B
0x1400103ab  cmp     [rbx+28h], rdi
0x1400103af  jnz     loc_14001046C
0x1400103b5  lock bts dword ptr [rbx+28h], 0
0x1400103bb  test    r14b, r14b
0x1400103be  jz      short loc_1400103E8
0x1400103c0  mov     rax, [rbx]
0x1400103c3  cmp     rax, rbx
0x1400103c6  jz      short loc_1400103E8
0x1400103c8  cmp     dword ptr [rax+20h], 2
0x1400103cc  jb      short loc_1400103E8
0x1400103ce  mov     r8, r13
0x1400103d1  xor     edx, edx
0x1400103d3  mov     rcx, rbx
0x1400103d6  call    NpRemoveDataQueueEntry
0x1400103db  test    rax, rax
0x1400103de  jnz     short loc_140010425
0x1400103e0  mov     rax, [rbx]
0x1400103e3  cmp     rax, rbx
0x1400103e6  jnz     short loc_1400103C8
0x1400103e8  test    r15b, r15b
0x1400103eb  jnz     loc_14001049A
0x1400103f1  mov     [rbx+24h], ebp
0x1400103f4  mov     rax, rsi
0x1400103f7  add     rsp, 20h
0x1400103fb  pop     r15
0x1400103fd  pop     r14
0x1400103ff  pop     r13
0x140010401  pop     rdi
0x140010402  pop     rsi
0x140010403  pop     rbp
0x140010404  pop     rbx
0x140010405  retn
0x140010407  mov     eax, [rcx+1Ch]
0x14001040a  cmp     [rcx+20h], eax
0x14001040d  jb      loc_140010367
0x140010413  cmp     dword ptr [rdi+24h], 0
0x140010417  jz      loc_140010367
0x14001041d  mov     r15b, 1
0x140010420  jmp     loc_14001036A
0x140010425  mov     [rax+30h], ebp
0x140010428  mov     rcx, [r13+8]
0x14001042c  cmp     [rcx], r13
0x14001042f  jnz     short loc_1400104AA
0x140010431  add     rax, 0A8h
0x140010437  mov     [rax], r13
0x14001043a  mov     [rax+8], rcx
0x14001043e  mov     [rcx], rax
0x140010441  mov     [r13+8], rax
0x140010445  jmp     short loc_1400103E0
0x140010447  mov     rcx, rbp
0x14001044a  call    cs:__imp_SeDeleteClientSecurity
0x140010451  nop     dword ptr [rax+rax+00h]
0x140010456  xor     edx, edx; Tag
0x140010458  mov     rcx, rbp; P
0x14001045b  call    cs:__imp_ExFreePoolWithTag
0x140010462  nop     dword ptr [rax+rax+00h]
0x140010467  jmp     loc_140010395
0x14001046c  xor     edx, edx; Tag
0x14001046e  mov     rcx, rdi; P
0x140010471  call    cs:__imp_ExFreePoolWithTag
0x140010478  nop     dword ptr [rax+rax+00h]
0x14001047d  jmp     loc_1400103BB
0x140010482  xor     ebp, ebp
0x140010484  mov     esi, ebp
0x140010486  jmp     loc_1400103F1
0x14001048b  mov     [rsi+90h], rbp
0x140010492  mov     rsi, rbp
0x140010495  jmp     loc_1400103AB
0x14001049a  mov     rdx, r13
0x14001049d  mov     rcx, rbx
0x1400104a0  call    NpCompleteStalledWrites
0x1400104a5  jmp     loc_1400103F1
0x1400104aa  mov     ecx, 3
0x1400104af  int     29h; Win8: RtlFailFast(ecx)
```
