# DiscpGetTargetList

- ea: `0x180007320`
- end: `0x1800074e2`
- name: `DiscpGetTargetList`
- size: `450`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, __int64 *, volatile signed __int32 **)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007c44`
- `0x180009898`
- `0x180011df0`
- `0x180011fb8`

## callees

- `0x180006404`
- `0x180006598`
- `0x180007320`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800073de`
- `ISCSIUM!DiscpAllocMemory` at `0x18000747e`
- `ISCSIUM!DiscpAllocMemory` at `0x1800073de`
- `ISCSIUM!DiscpAllocMemory` at `0x18000747e`
- `ISCSIUM!DiscpFreeMemory` at `0x180007446`
- `ISCSIUM!DiscpFreeMemory` at `0x1800074c9`
- `ISCSIUM!DiscpFreeMemory` at `0x180007446`
- `ISCSIUM!DiscpFreeMemory` at `0x1800074c9`
- `ntdll!RtlLeaveCriticalSection` at `0x18000745f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000745f`
- `ntdll!RtlEnterCriticalSection` at `0x1800073a4`
- `ntdll!RtlEnterCriticalSection` at `0x1800073a4`

## pseudocode

```c
__int64 __fastcall DiscpGetTargetList(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 *a4,
        volatile signed __int32 **a5)
{
  volatile signed __int32 **v5; // rdi
  unsigned int v10; // r14d
  unsigned int Target; // ebp
  __int64 v12; // rsi
  volatile signed __int32 **v13; // r12
  _QWORD *v14; // rax
  _QWORD *v15; // rdx
  volatile signed __int32 *v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // r8d
  volatile signed __int32 *i; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v24; // [rsp+78h] [rbp+10h] BYREF

  v5 = a5;
  v24 = 0;
  v10 = 1;
  *a5 = 0;
  if ( a2 )
  {
    Target = DiscpFindTarget(a1, a2, 1, &v24);
    if ( !Target )
      goto LABEL_22;
  }
  Target = DiscpFindTarget(a1, a2, 0, &v24);
  if ( Target )
    return Target;
  if ( a2 )
  {
LABEL_22:
    *a3 = 1;
    v22 = (_QWORD *)DiscpAllocMemory(8);
    v21 = v24;
    *a4 = (__int64)v22;
    if ( v22 )
    {
      *v22 = v21;
      if ( *(_DWORD *)(v21 + 44) == 2 )
      {
        *v5 = (volatile signed __int32 *)v21;
        _InterlockedAdd((volatile signed __int32 *)(v21 + 32), 1u);
      }
      else
      {
        DiscpFindTargetByTag(a1, 2, v5);
      }
    }
    else
    {
      Target = 8;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 + 32), 0xFFFFFFFF) == 1 )
        goto LABEL_27;
    }
  }
  else
  {
    RtlEnterCriticalSection(&DiscpCritSection);
    v12 = v24;
    v13 = (volatile signed __int32 **)(v24 + 16);
    v14 = *(_QWORD **)(v24 + 16);
    v15 = v14;
    do
    {
      v16 = (volatile signed __int32 *)(v14 - 2);
      if ( *((_DWORD *)v14 + 7) == 2 )
      {
        _InterlockedIncrement(v16 + 8);
        *v5 = v16;
      }
      v14 = (_QWORD *)*v14;
      ++v10;
    }
    while ( v14 != v15 );
    v17 = DiscpAllocMemory(8 * v10);
    *a4 = v17;
    if ( v17 )
    {
      v18 = 1;
      _InterlockedAdd((volatile signed __int32 *)(v12 + 32), 1u);
      *(_QWORD *)*a4 = v12;
      for ( i = *v13; i != (volatile signed __int32 *)v13 && v18 < v10; i = *(volatile signed __int32 **)i )
      {
        _InterlockedAdd(i + 4, 1u);
        v20 = v18++;
        *(_QWORD *)(*a4 + 8 * v20) = i - 4;
      }
      *a3 = v18;
    }
    else
    {
      if ( *v5 )
      {
        if ( _InterlockedExchangeAdd(*v5 + 8, 0xFFFFFFFF) == 1 )
          DiscpFreeMemory(*v5);
        *v5 = 0;
      }
      Target = 8;
    }
    RtlLeaveCriticalSection(&DiscpCritSection);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 32), 0xFFFFFFFF) == 1 )
    {
      v21 = v12;
LABEL_27:
      DiscpFreeMemory(v21);
    }
  }
  return Target;
}

```

## disassembly

```asm
0x180007320  push    rbx
0x180007322  push    rbp
0x180007323  push    rsi
0x180007324  push    rdi
0x180007325  push    r12
0x180007327  push    r13
0x180007329  push    r14
0x18000732b  push    r15
0x18000732d  sub     rsp, 28h
0x180007331  mov     rdi, [rsp+68h+arg_20]
0x180007339  mov     r15, r9
0x18000733c  mov     [rsp+68h+arg_8], 0
0x180007345  mov     r13, r8
0x180007348  mov     rbx, rdx
0x18000734b  mov     rsi, rcx
0x18000734e  mov     r14d, 1
0x180007354  mov     qword ptr [rdi], 0
0x18000735b  test    rdx, rdx
0x18000735e  jz      short loc_180007377
0x180007360  lea     r9, [rsp+68h+arg_8]
0x180007365  mov     r8b, r14b
0x180007368  call    DiscpFindTarget
0x18000736d  mov     ebp, eax
0x18000736f  test    eax, eax
0x180007371  jz      loc_180007475
0x180007377  lea     r9, [rsp+68h+arg_8]
0x18000737c  xor     r8d, r8d
0x18000737f  mov     rdx, rbx
0x180007382  mov     rcx, rsi
0x180007385  call    DiscpFindTarget
0x18000738a  mov     ebp, eax
0x18000738c  test    eax, eax
0x18000738e  jnz     loc_1800074CF
0x180007394  test    rbx, rbx
0x180007397  jnz     loc_180007475
0x18000739d  lea     rcx, DiscpCritSection; CriticalSection
0x1800073a4  call    cs:__imp_RtlEnterCriticalSection
0x1800073aa  mov     rsi, [rsp+68h+arg_8]
0x1800073af  lea     r12, [rsi+10h]
0x1800073b3  mov     rax, [r12]
0x1800073b7  mov     rdx, rax
0x1800073ba  lea     rcx, [rax-10h]
0x1800073be  cmp     dword ptr [rcx+2Ch], 2
0x1800073c2  jnz     short loc_1800073CB
0x1800073c4  lock inc dword ptr [rcx+20h]
0x1800073c8  mov     [rdi], rcx
0x1800073cb  mov     rax, [rax]
0x1800073ce  inc     r14d
0x1800073d1  cmp     rax, rdx
0x1800073d4  jnz     short loc_1800073BA
0x1800073d6  lea     ecx, ds:0[r14*8]
0x1800073de  call    cs:__imp_DiscpAllocMemory
0x1800073e4  or      ebx, 0FFFFFFFFh
0x1800073e7  mov     [r15], rax
0x1800073ea  test    rax, rax
0x1800073ed  jz      short loc_180007430
0x1800073ef  lea     r10d, [rbx+2]
0x1800073f3  mov     r8d, r10d
0x1800073f6  lock add [rsi+20h], r10d
0x1800073fb  mov     rax, [r15]
0x1800073fe  mov     [rax], rsi
0x180007401  mov     r9, [r12]
0x180007405  jmp     short loc_180007425
0x180007407  cmp     r8d, r14d
0x18000740a  jnb     short loc_18000742A
0x18000740c  lea     rdx, [r9-10h]
0x180007410  lock add [rdx+20h], r10d
0x180007415  mov     rax, [r15]
0x180007418  mov     ecx, r8d
0x18000741b  add     r8d, r10d
0x18000741e  mov     [rax+rcx*8], rdx
0x180007422  mov     r9, [r9]
0x180007425  cmp     r9, r12
0x180007428  jnz     short loc_180007407
0x18000742a  mov     [r13+0], r8d
0x18000742e  jmp     short loc_180007458
0x180007430  mov     rcx, [rdi]
0x180007433  test    rcx, rcx
0x180007436  jz      short loc_180007453
0x180007438  mov     eax, ebx
0x18000743a  lock xadd [rcx+20h], eax
0x18000743f  add     eax, ebx
0x180007441  jnz     short loc_18000744C
0x180007443  mov     rcx, [rdi]
0x180007446  call    cs:__imp_DiscpFreeMemory
0x18000744c  mov     qword ptr [rdi], 0
0x180007453  mov     ebp, 8
0x180007458  lea     rcx, DiscpCritSection; CriticalSection
0x18000745f  call    cs:__imp_RtlLeaveCriticalSection
0x180007465  mov     eax, ebx
0x180007467  lock xadd [rsi+20h], eax
0x18000746c  add     eax, ebx
0x18000746e  jnz     short loc_1800074CF
0x180007470  mov     rcx, rsi
0x180007473  jmp     short loc_1800074C9
0x180007475  mov     ecx, 8
0x18000747a  mov     [r13+0], r14d
0x18000747e  call    cs:__imp_DiscpAllocMemory
0x180007484  mov     rcx, [rsp+68h+arg_8]
0x180007489  mov     [r15], rax
0x18000748c  test    rax, rax
0x18000748f  jz      short loc_1800074B6
0x180007491  mov     [rax], rcx
0x180007494  cmp     dword ptr [rcx+2Ch], 2
0x180007498  jnz     short loc_1800074A4
0x18000749a  mov     [rdi], rcx
0x18000749d  lock add [rcx+20h], r14d
0x1800074a2  jmp     short loc_1800074CF
0x1800074a4  mov     r8, rdi
0x1800074a7  mov     edx, 2
0x1800074ac  mov     rcx, rsi
0x1800074af  call    DiscpFindTargetByTag
0x1800074b4  jmp     short loc_1800074CF
0x1800074b6  or      ebx, 0FFFFFFFFh
0x1800074b9  mov     ebp, 8
0x1800074be  mov     eax, ebx
0x1800074c0  lock xadd [rcx+20h], eax
0x1800074c5  add     eax, ebx
0x1800074c7  jnz     short loc_1800074CF
0x1800074c9  call    cs:__imp_DiscpFreeMemory
0x1800074cf  mov     eax, ebp
0x1800074d1  add     rsp, 28h
0x1800074d5  pop     r15
0x1800074d7  pop     r14
0x1800074d9  pop     r13
0x1800074db  pop     r12
0x1800074dd  pop     rdi
0x1800074de  pop     rsi
0x1800074df  pop     rbp
0x1800074e0  pop     rbx
0x1800074e1  retn
```
