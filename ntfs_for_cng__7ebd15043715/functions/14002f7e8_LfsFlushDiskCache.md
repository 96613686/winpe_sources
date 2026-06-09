# LfsFlushDiskCache

- ea: `0x14002f7e8`
- end: `0x14002fb6c`
- name: `LfsFlushDiskCache`
- size: `900`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140209910`

## callees

- `0x14002f7e8`
- `0x140059370`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002faa2`
- `ntoskrnl!KeSetEvent` at `0x14002faf3`
- `ntoskrnl!KeSetEvent` at `0x14002faa2`
- `ntoskrnl!KeSetEvent` at `0x14002faf3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f932`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f932`
- `ntoskrnl!ObfReferenceObject` at `0x14002f8a0`
- `ntoskrnl!ObfReferenceObject` at `0x14002f8a0`
- `ntoskrnl!KeSetPriorityThread` at `0x14002f8ba`
- `ntoskrnl!KeSetPriorityThread` at `0x14002f9d4`
- `ntoskrnl!KeSetPriorityThread` at `0x14002f8ba`
- `ntoskrnl!KeSetPriorityThread` at `0x14002f9d4`
- `ntoskrnl!PsEnterPriorityRegion` at `0x14002f8cd`
- `ntoskrnl!PsEnterPriorityRegion` at `0x14002f8cd`
- `ntoskrnl!PsLeavePriorityRegion` at `0x14002f9b2`
- `ntoskrnl!PsLeavePriorityRegion` at `0x14002f9b2`
- `ntoskrnl!KeResetEvent` at `0x14002fa44`
- `ntoskrnl!KeResetEvent` at `0x14002fa44`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002f8eb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002f8eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002f9fb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002f9fb`
- `ntoskrnl!KeInitializeEvent` at `0x14002f848`
- `ntoskrnl!KeInitializeEvent` at `0x14002f848`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002f944`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002fa0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002fb5e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b57f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002f944`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002fa0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002fb5e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b57f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f8ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f8ff`

## pseudocode

```c
__int64 __fastcall LfsFlushDiskCache(__int64 a1, __int64 a2)
{
  KPRIORITY v4; // r13d
  __int64 v5; // rdi
  void *v6; // r12
  __int64 v7; // rax
  char v8; // r14
  __int64 v9; // r15
  __int64 v10; // rdi
  _QWORD *v11; // rbx
  __int64 *v12; // rdi
  __int64 *j; // rcx
  _QWORD *i; // rax
  _QWORD *v15; // rcx
  __int64 *v16; // rax
  __int64 **v17; // rdx
  __int64 *v18; // rcx
  __int64 *v19; // rax
  __int64 **v20; // rdx
  __int128 v22; // [rsp+48h] [rbp-60h] BYREF
  __int128 Object; // [rsp+58h] [rbp-50h] BYREF
  __int128 v24; // [rsp+68h] [rbp-40h]
  __int64 v25; // [rsp+78h] [rbp-30h]
  unsigned int v26; // [rsp+C0h] [rbp+18h]

  v26 = 0;
  v4 = 0;
  v22 = 0;
  Object = 0;
  v24 = 0;
  v25 = 0;
  v5 = *(_QWORD *)(a1 + 24);
  v6 = 0;
  KeInitializeEvent((PRKEVENT)&Object, SynchronizationEvent, 0);
  *((_QWORD *)&v24 + 1) = a2;
  while ( a2 > *(_QWORD *)(v5 + 296) )
  {
    v7 = *(_QWORD *)(a1 + 56);
    if ( *(_DWORD *)(v7 + 180) )
    {
      KeResetEvent((PRKEVENT)&Object);
      for ( i = *(_QWORD **)(v5 + 328); i != (_QWORD *)(v5 + 328) && i[5] <= a2; i = (_QWORD *)*i )
        ;
      v15 = (_QWORD *)i[1];
      if ( (_QWORD *)*v15 != i )
        goto LABEL_22;
      v8 = 0;
      *(_QWORD *)&v22 = i;
      *((_QWORD *)&v22 + 1) = v15;
      *v15 = &v22;
      i[1] = &v22;
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 320));
    }
    else
    {
      *(_DWORD *)(v7 + 180) = 1;
      *(_QWORD *)(v5 + 312) = KeGetCurrentThread();
      v8 = 1;
      v6 = *(void **)(v5 + 24);
      ObfReferenceObject(v6);
      v4 = KeSetPriorityThread(KeGetCurrentThread(), 16);
      PsEnterPriorityRegion();
    }
    v9 = *(_QWORD *)(v5 + 352);
    v10 = *(_QWORD *)(v5 + 280);
    if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a1 + 56)) )
      ExReleaseResourceLite(*(PERESOURCE *)(a1 + 56));
    if ( v8 )
    {
      v26 = qword_140094AF8(v6);
      ObfDereferenceObject(v6);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 56), 1u);
      v11 = *(_QWORD **)(a1 + 24);
      if ( v11 )
      {
        if ( v11[43] < v9 )
          v11[43] = v9;
        if ( v11[37] < v10 )
          v11[37] = v10;
        *(_DWORD *)(*(_QWORD *)(a1 + 56) + 180LL) = 0;
        v11[39] = 0;
        v12 = v11 + 41;
        for ( j = (__int64 *)v11[41]; ; j = (__int64 *)*v12 )
        {
          if ( j == v12 )
            goto LABEL_15;
          if ( v11[37] < j[5] )
            break;
          v16 = (__int64 *)*j;
          if ( *(__int64 **)(*j + 8) != j )
            goto LABEL_22;
          v17 = (__int64 **)j[1];
          if ( *v17 != j )
            goto LABEL_22;
          *v17 = v16;
          v16[1] = (__int64)v17;
          KeSetEvent((PRKEVENT)(j + 2), 0, 0);
        }
        v18 = (__int64 *)v11[42];
        if ( v18 != v12 )
        {
          v19 = (__int64 *)*v18;
          if ( *(__int64 **)(*v18 + 8) != v18 || (v20 = (__int64 **)v18[1], *v20 != v18) )
LABEL_22:
            __fastfail(3u);
          *v20 = v19;
          v19[1] = (__int64)v20;
          KeSetEvent((PRKEVENT)(v18 + 2), 0, 0);
        }
      }
LABEL_15:
      PsLeavePriorityRegion();
      if ( v4 != 16 )
        KeSetPriorityThread(KeGetCurrentThread(), v4);
      return v26;
    }
    KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 56), 1u);
    v5 = *(_QWORD *)(a1 + 24);
    if ( !v5 )
      return v26;
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 320));
  }
  return v26;
}

```

## disassembly

```asm
0x14002f7e8  mov     r11, rsp
0x14002f7eb  mov     [r11+10h], rbx
0x14002f7ef  mov     [r11+20h], rsi
0x14002f7f3  mov     [r11+8], rcx
0x14002f7f7  push    rdi
0x14002f7f8  push    r12
0x14002f7fa  push    r13
0x14002f7fc  push    r14
0x14002f7fe  push    r15
0x14002f800  sub     rsp, 80h
0x14002f807  mov     rbx, rdx
0x14002f80a  mov     rsi, rcx
0x14002f80d  mov     dword ptr [r11+18h], 0
0x14002f815  xor     r13d, r13d
0x14002f818  xorps   xmm0, xmm0
0x14002f81b  xor     eax, eax
0x14002f81d  movups  [rsp+0A8h+var_60], xmm0
0x14002f822  movups  [rsp+0A8h+Object], xmm0
0x14002f827  movups  [rsp+0A8h+var_40], xmm0
0x14002f82c  mov     [r11-30h], rax
0x14002f830  xor     r14b, r14b
0x14002f833  mov     [r11-78h], r14b
0x14002f837  mov     rdi, [rcx+18h]
0x14002f83b  xor     r12d, r12d
0x14002f83e  xor     r8d, r8d; State
0x14002f841  lea     edx, [rax+1]; Type
0x14002f844  lea     rcx, [r11-50h]; Event
0x14002f848  call    cs:__imp_KeInitializeEvent
0x14002f84f  nop     dword ptr [rax+rax+00h]
0x14002f854  mov     qword ptr [rsp+0A8h+var_40+8], rbx
0x14002f859  cmp     rbx, [rdi+128h]
0x14002f860  jle     loc_14002FB2E
0x14002f866  mov     rax, [rsi+38h]
0x14002f86a  cmp     dword ptr [rax+0B4h], 0
0x14002f871  jnz     loc_14002FA3F
0x14002f877  mov     dword ptr [rax+0B4h], 1
0x14002f881  mov     rax, gs:188h
0x14002f88a  mov     [rdi+138h], rax
0x14002f891  mov     r14b, 1
0x14002f894  mov     r12, [rdi+18h]
0x14002f898  mov     [rsp+0A8h+var_68], r12
0x14002f89d  mov     rcx, r12; Object
0x14002f8a0  call    cs:__imp_ObfReferenceObject
0x14002f8a7  nop     dword ptr [rax+rax+00h]
0x14002f8ac  mov     rcx, gs:188h; Thread
0x14002f8b5  mov     edx, 10h; Priority
0x14002f8ba  call    cs:__imp_KeSetPriorityThread
0x14002f8c1  nop     dword ptr [rax+rax+00h]
0x14002f8c6  mov     r13d, eax
0x14002f8c9  mov     [rsp+0A8h+var_74], eax
0x14002f8cd  call    cs:__imp_PsEnterPriorityRegion
0x14002f8d4  nop     dword ptr [rax+rax+00h]
0x14002f8d9  mov     r15, [rdi+160h]
0x14002f8e0  mov     rdi, [rdi+118h]
0x14002f8e7  mov     rcx, [rsi+38h]; Resource
0x14002f8eb  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14002f8f2  nop     dword ptr [rax+rax+00h]
0x14002f8f7  test    eax, eax
0x14002f8f9  jz      short loc_14002F90B
0x14002f8fb  mov     rcx, [rsi+38h]; Resource
0x14002f8ff  call    cs:__imp_ExReleaseResourceLite
0x14002f906  nop     dword ptr [rax+rax+00h]
0x14002f90b  mov     [rsp+0A8h+var_78], 1
0x14002f910  test    r14b, r14b
0x14002f913  jz      loc_14002F9E5
0x14002f919  mov     rax, cs:qword_140094AF8
0x14002f920  mov     rcx, r12
0x14002f923  call    _guard_dispatch_icall
0x14002f928  mov     [rsp+0A8h+arg_10], eax
0x14002f92f  mov     rcx, r12; Object
0x14002f932  call    cs:__imp_ObfDereferenceObject
0x14002f939  nop     dword ptr [rax+rax+00h]
0x14002f93e  mov     dl, 1; Wait
0x14002f940  mov     rcx, [rsi+38h]; Resource
0x14002f944  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002f94b  nop     dword ptr [rax+rax+00h]
0x14002f950  xor     r14b, r14b
0x14002f953  mov     [rsp+0A8h+var_78], r14b
0x14002f958  mov     rbx, [rsi+18h]
0x14002f95c  mov     [rsp+0A8h+var_70], rbx
0x14002f961  test    rbx, rbx
0x14002f964  jz      short loc_14002F9B2
0x14002f966  cmp     [rbx+158h], r15
0x14002f96d  jge     short loc_14002F976
0x14002f96f  mov     [rbx+158h], r15
0x14002f976  cmp     [rbx+128h], rdi
0x14002f97d  jge     short loc_14002F986
0x14002f97f  mov     [rbx+128h], rdi
0x14002f986  mov     rax, [rsi+38h]
0x14002f98a  mov     dword ptr [rax+0B4h], 0
0x14002f994  mov     qword ptr [rbx+138h], 0
0x14002f99f  lea     rdi, [rbx+148h]
0x14002f9a6  mov     rcx, [rdi]
0x14002f9a9  cmp     rcx, rdi
0x14002f9ac  jnz     loc_14002FA73
0x14002f9b2  call    cs:__imp_PsLeavePriorityRegion
0x14002f9b9  nop     dword ptr [rax+rax+00h]
0x14002f9be  cmp     r13d, 10h
0x14002f9c2  jz      loc_14002FB2E
0x14002f9c8  mov     rcx, gs:188h; Thread
0x14002f9d1  mov     edx, r13d; Priority
0x14002f9d4  call    cs:__imp_KeSetPriorityThread
0x14002f9db  nop     dword ptr [rax+rax+00h]
0x14002f9e0  jmp     loc_14002FB2E
0x14002f9e5  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14002f9ee  xor     r9d, r9d; Alertable
0x14002f9f1  xor     r8d, r8d; WaitMode
0x14002f9f4  xor     edx, edx; WaitReason
0x14002f9f6  lea     rcx, [rsp+0A8h+Object]; Object
0x14002f9fb  call    cs:__imp_KeWaitForSingleObject
0x14002fa02  nop     dword ptr [rax+rax+00h]
0x14002fa07  mov     dl, 1; Wait
0x14002fa09  mov     rcx, [rsi+38h]; Resource
0x14002fa0d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002fa14  nop     dword ptr [rax+rax+00h]
0x14002fa19  xor     r14b, r14b
0x14002fa1c  mov     [rsp+0A8h+var_78], r14b
0x14002fa21  mov     rdi, [rsi+18h]
0x14002fa25  mov     [rsp+0A8h+var_70], rdi
0x14002fa2a  test    rdi, rdi
0x14002fa2d  jz      loc_14002FB2E
0x14002fa33  lock dec dword ptr [rdi+140h]
0x14002fa3a  jmp     loc_14002F859
0x14002fa3f  lea     rcx, [rsp+0A8h+Object]; Event
0x14002fa44  call    cs:__imp_KeResetEvent
0x14002fa4b  nop     dword ptr [rax+rax+00h]
0x14002fa50  lea     rcx, [rdi+148h]
0x14002fa57  mov     rax, [rcx]
0x14002fa5a  cmp     rax, rcx
0x14002fa5d  jnz     short loc_14002FAB6
0x14002fa5f  mov     rcx, [rax+8]
0x14002fa63  cmp     [rcx], rax
0x14002fa66  jz      loc_14002FB04
0x14002fa6c  mov     ecx, 3
0x14002fa71  int     29h; Win8: RtlFailFast(ecx)
0x14002fa73  mov     rax, [rcx+28h]
0x14002fa77  cmp     [rbx+128h], rax
0x14002fa7e  jl      short loc_14002FAC1
0x14002fa80  mov     rax, [rcx]
0x14002fa83  cmp     [rax+8], rcx
0x14002fa87  jnz     short loc_14002FA6C
0x14002fa89  mov     rdx, [rcx+8]
0x14002fa8d  cmp     [rdx], rcx
0x14002fa90  jnz     short loc_14002FA6C
0x14002fa92  mov     [rdx], rax
0x14002fa95  mov     [rax+8], rdx
0x14002fa99  add     rcx, 10h; Event
0x14002fa9d  xor     r8d, r8d; Wait
0x14002faa0  xor     edx, edx; Increment
0x14002faa2  call    cs:__imp_KeSetEvent
0x14002faa9  nop     dword ptr [rax+rax+00h]
0x14002faae  mov     rcx, [rdi]
0x14002fab1  jmp     loc_14002F9A9
0x14002fab6  cmp     [rax+28h], rbx
0x14002faba  jg      short loc_14002FA5F
0x14002fabc  mov     rax, [rax]
0x14002fabf  jmp     short loc_14002FA5A
0x14002fac1  mov     rcx, [rbx+150h]
0x14002fac8  cmp     rcx, rdi
0x14002facb  jz      loc_14002F9B2
0x14002fad1  mov     rax, [rcx]
0x14002fad4  cmp     [rax+8], rcx
0x14002fad8  jnz     short loc_14002FA6C
0x14002fada  mov     rdx, [rcx+8]
0x14002fade  cmp     [rdx], rcx
0x14002fae1  jnz     short loc_14002FA6C
0x14002fae3  mov     [rdx], rax
0x14002fae6  mov     [rax+8], rdx
0x14002faea  add     rcx, 10h; Event
0x14002faee  xor     r8d, r8d; Wait
0x14002faf1  xor     edx, edx; Increment
0x14002faf3  call    cs:__imp_KeSetEvent
0x14002fafa  nop     dword ptr [rax+rax+00h]
0x14002faff  jmp     loc_14002F9B2
0x14002fb04  xor     r14b, r14b
0x14002fb07  mov     qword ptr [rsp+0A8h+var_60], rax
0x14002fb0c  mov     qword ptr [rsp+0A8h+var_60+8], rcx
0x14002fb11  lea     rdx, [rsp+0A8h+var_60]
0x14002fb16  mov     [rcx], rdx
0x14002fb19  lea     rcx, [rsp+0A8h+var_60]
0x14002fb1e  mov     [rax+8], rcx
0x14002fb22  lock inc dword ptr [rdi+140h]
0x14002fb29  jmp     loc_14002F8D9
0x14002fb2e  test    r14b, r14b
0x14002fb31  jnz     short loc_14002FB58
0x14002fb33  mov     eax, [rsp+0A8h+arg_10]
0x14002fb3a  lea     r11, [rsp+0A8h+var_28]
0x14002fb42  mov     rbx, [r11+38h]
0x14002fb46  mov     rsi, [r11+48h]
0x14002fb4a  mov     rsp, r11
0x14002fb4d  pop     r15
0x14002fb4f  pop     r14
0x14002fb51  pop     r13
0x14002fb53  pop     r12
0x14002fb55  pop     rdi
0x14002fb56  retn
0x14002fb58  mov     dl, 1; Wait
0x14002fb5a  mov     rcx, [rsi+38h]; Resource
0x14002fb5e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002fb65  nop     dword ptr [rax+rax+00h]
0x14002fb6a  jmp     short loc_14002FB33
0x14005b563  push    rbp
0x14005b565  sub     rsp, 30h
0x14005b569  mov     rbp, rdx
0x14005b56c  cmp     byte ptr [rbp+30h], 0
0x14005b570  jz      short loc_14005B58F
0x14005b572  mov     dl, 1; Wait
0x14005b574  mov     rcx, [rbp+0B0h]
0x14005b57b  mov     rcx, [rcx+38h]; Resource
0x14005b57f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005b586  nop     dword ptr [rax+rax+00h]
0x14005b58b  mov     byte ptr [rbp+30h], 0
0x14005b58f  add     rsp, 30h
0x14005b593  pop     rbp
0x14005b594  retn
```
