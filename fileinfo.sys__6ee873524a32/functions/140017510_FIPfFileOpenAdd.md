# FIPfFileOpenAdd

- ea: `0x140017510`
- end: `0x1400176f8`
- name: `FIPfFileOpenAdd`
- size: `488`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140017700`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140002538`
- `0x140002d64`
- `0x1400033f0`
- `0x140017510`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400176ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400176ca`
- `ntoskrnl!ExAllocatePool2` at `0x140017537`
- `ntoskrnl!ExAllocatePool2` at `0x140017537`
- `FLTMGR!FltReferenceContext` at `0x1400175f3`
- `FLTMGR!FltReferenceContext` at `0x14001764e`
- `FLTMGR!FltReferenceContext` at `0x1400175f3`
- `FLTMGR!FltReferenceContext` at `0x14001764e`

## pseudocode

```c
__int64 __fastcall FIPfFileOpenAdd(_QWORD *Context, __int64 *a2)
{
  _QWORD *Pool2; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 v9; // r15
  unsigned int v10; // ebp
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbp
  _QWORD *v14; // rdx

  Pool2 = (_QWORD *)ExAllocatePool2(256, 64, 1666206022);
  v5 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 0;
  Pool2[3] = 0;
  Pool2[6] = 0;
  Pool2[7] = 0;
  v6 = (_QWORD *)FILockInitialize(Pool2 + 3);
  v6[1] = v6;
  *v6 = v6;
  v6 += 4;
  v6[1] = v6;
  *v6 = v6;
  FILockExclusiveAcquire(Context + 5);
  if ( (*((_DWORD *)Context + 14) & 0x80u) == 0 )
  {
    Context[9] = v5;
    *((_DWORD *)v5 + 5) = 1;
    FIStreamVolatileBitFieldBitSet(Context, 7, 1);
    v5[7] = Context;
    v5 = 0;
  }
  if ( Context == (_QWORD *)-40LL )
  {
    FILockSharedAcquire(0);
    v7 = MEMORY[0x20];
    _InterlockedIncrement((volatile signed __int32 *)(MEMORY[0x20] + 20LL));
    FILockExclusiveRelease(0);
  }
  else
  {
    v7 = Context[9];
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 20));
  }
  FILockExclusiveRelease(Context + 5);
  v8 = *a2;
  v9 = v7 + 24;
  FILockExclusiveAcquire(v7 + 24);
  FltReferenceContext(Context);
  *(_QWORD *)(v8 + 56) = Context;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v8 + 64), 1, 0) )
  {
    v11 = *(_QWORD **)(v7 + 40);
    *a2 = 0;
    if ( *v11 == v7 + 32 )
    {
      *(_QWORD *)(v8 + 8) = v11;
      *(_QWORD *)v8 = v7 + 32;
      *v11 = v8;
      *(_QWORD *)(v7 + 40) = v8;
      ++*(_DWORD *)(v7 + 48);
      FILockExclusiveRelease(v7 + 24);
      FltReferenceContext(*(PFLT_CONTEXT *)(v7 + 56));
      v12 = *(_QWORD *)(v7 + 56);
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 20));
      v13 = *(_QWORD *)(v12 + 24);
      v9 = v13 + 136;
      FILockExclusiveAcquire(v13 + 136);
      if ( *(_DWORD *)(v7 + 16) )
      {
LABEL_13:
        ++*(_DWORD *)(v7 + 16);
        v10 = 0;
        goto LABEL_14;
      }
      v14 = *(_QWORD **)(v13 + 152);
      if ( *v14 == v13 + 144 )
      {
        *(_QWORD *)v7 = v13 + 144;
        *(_QWORD *)(v7 + 8) = v14;
        *v14 = v7;
        *(_QWORD *)(v13 + 152) = v7;
        ++*(_DWORD *)(v13 + 208);
        goto LABEL_13;
      }
    }
    __fastfail(3u);
  }
  v10 = -1073741598;
LABEL_14:
  FILockExclusiveRelease(v9);
  if ( v7 )
    FIPfFilePfContextDereference(v7, Context);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return v10;
}

```

## disassembly

```asm
0x140017510  push    rbx
0x140017512  push    rbp
0x140017513  push    rsi
0x140017514  push    rdi
0x140017515  push    r12
0x140017517  push    r13
0x140017519  push    r14
0x14001751b  push    r15
0x14001751d  sub     rsp, 28h
0x140017521  mov     r12, rdx
0x140017524  mov     rsi, rcx
0x140017527  mov     edx, 40h ; '@'
0x14001752c  mov     ecx, 100h
0x140017531  mov     r8d, 63504946h
0x140017537  call    cs:__imp_ExAllocatePool2
0x14001753e  nop     dword ptr [rax+rax+00h]
0x140017543  mov     rdi, rax
0x140017546  test    rax, rax
0x140017549  jz      loc_1400176DF
0x14001754f  xor     r13d, r13d
0x140017552  lea     rcx, [rax+18h]
0x140017556  mov     [rax+10h], r13
0x14001755a  mov     [rax+18h], r13
0x14001755e  mov     [rax+30h], r13
0x140017562  mov     [rax+38h], r13
0x140017566  call    FILockInitialize
0x14001756b  mov     [rax+8], rax
0x14001756f  lea     rbp, [rsi+28h]
0x140017573  mov     [rax], rax
0x140017576  mov     rcx, rbp
0x140017579  add     rax, 20h ; ' '
0x14001757d  mov     [rax+8], rax
0x140017581  mov     [rax], rax
0x140017584  call    FILockExclusiveAcquire
0x140017589  mov     eax, [rsi+38h]
0x14001758c  mov     ecx, 1
0x140017591  test    al, al
0x140017593  js      short loc_1400175B3
0x140017595  mov     [rsi+48h], rdi
0x140017599  mov     r8d, ecx
0x14001759c  mov     [rdi+14h], ecx
0x14001759f  mov     edx, 7
0x1400175a4  mov     rcx, rsi
0x1400175a7  call    FIStreamVolatileBitFieldBitSet
0x1400175ac  mov     [rdi+38h], rsi
0x1400175b0  mov     edi, r13d
0x1400175b3  test    rbp, rbp
0x1400175b6  jnz     short loc_1400175D0
0x1400175b8  xor     ecx, ecx
0x1400175ba  call    FILockSharedAcquire
0x1400175bf  mov     rbx, [rsi+48h]
0x1400175c3  lock inc dword ptr [rbx+14h]
0x1400175c7  xor     ecx, ecx
0x1400175c9  call    FILockExclusiveRelease
0x1400175ce  jmp     short loc_1400175D8
0x1400175d0  mov     rbx, [rsi+48h]
0x1400175d4  lock inc dword ptr [rbx+14h]
0x1400175d8  mov     rcx, rbp
0x1400175db  call    FILockExclusiveRelease
0x1400175e0  mov     r14, [r12]
0x1400175e4  lea     r15, [rbx+18h]
0x1400175e8  mov     rcx, r15
0x1400175eb  call    FILockExclusiveAcquire
0x1400175f0  mov     rcx, rsi; Context
0x1400175f3  call    cs:__imp_FltReferenceContext
0x1400175fa  nop     dword ptr [rax+rax+00h]
0x1400175ff  xor     eax, eax
0x140017601  mov     [r14+38h], rsi
0x140017605  mov     ecx, 1
0x14001760a  lock cmpxchg [r14+40h], ecx
0x140017610  jz      short loc_14001761C
0x140017612  mov     ebp, 0C00000E2h
0x140017617  jmp     loc_1400176A8
0x14001761c  mov     rcx, [rbx+28h]
0x140017620  lea     rax, [rbx+20h]
0x140017624  mov     [r12], r13
0x140017628  cmp     [rcx], rax
0x14001762b  jnz     loc_1400176D8
0x140017631  mov     [r14+8], rcx
0x140017635  mov     [r14], rax
0x140017638  mov     [rcx], r14
0x14001763b  mov     rcx, r15
0x14001763e  mov     [rax+8], r14
0x140017642  inc     dword ptr [rbx+30h]
0x140017645  call    FILockExclusiveRelease
0x14001764a  mov     rcx, [rbx+38h]; Context
0x14001764e  call    cs:__imp_FltReferenceContext
0x140017655  nop     dword ptr [rax+rax+00h]
0x14001765a  mov     rcx, [rbx+38h]
0x14001765e  mov     eax, [rcx+38h]
0x140017661  lock inc dword ptr [rbx+14h]
0x140017665  mov     rbp, [rcx+18h]
0x140017669  lea     r15, [rbp+88h]
0x140017670  mov     rcx, r15
0x140017673  call    FILockExclusiveAcquire
0x140017678  cmp     [rbx+10h], r13d
0x14001767c  jnz     short loc_1400176A2
0x14001767e  lea     rax, [rbp+90h]
0x140017685  mov     rdx, [rax+8]
0x140017689  cmp     [rdx], rax
0x14001768c  jnz     short loc_1400176D8
0x14001768e  mov     [rbx], rax
0x140017691  mov     [rbx+8], rdx
0x140017695  mov     [rdx], rbx
0x140017698  mov     [rax+8], rbx
0x14001769c  inc     dword ptr [rbp+0D0h]
0x1400176a2  inc     dword ptr [rbx+10h]
0x1400176a5  mov     ebp, r13d
0x1400176a8  mov     rcx, r15
0x1400176ab  call    FILockExclusiveRelease
0x1400176b0  test    rbx, rbx
0x1400176b3  jz      short loc_1400176C0
0x1400176b5  mov     rdx, rsi
0x1400176b8  mov     rcx, rbx
0x1400176bb  call    FIPfFilePfContextDereference
0x1400176c0  test    rdi, rdi
0x1400176c3  jz      short loc_1400176E4
0x1400176c5  xor     edx, edx; Tag
0x1400176c7  mov     rcx, rdi; P
0x1400176ca  call    cs:__imp_ExFreePoolWithTag
0x1400176d1  nop     dword ptr [rax+rax+00h]
0x1400176d6  jmp     short loc_1400176E4
0x1400176d8  mov     ecx, 3
0x1400176dd  int     29h; Win8: RtlFailFast(ecx)
0x1400176df  mov     ebp, 0C000009Ah
0x1400176e4  mov     eax, ebp
0x1400176e6  add     rsp, 28h
0x1400176ea  pop     r15
0x1400176ec  pop     r14
0x1400176ee  pop     r13
0x1400176f0  pop     r12
0x1400176f2  pop     rdi
0x1400176f3  pop     rsi
0x1400176f4  pop     rbp
0x1400176f5  pop     rbx
0x1400176f6  retn
```
