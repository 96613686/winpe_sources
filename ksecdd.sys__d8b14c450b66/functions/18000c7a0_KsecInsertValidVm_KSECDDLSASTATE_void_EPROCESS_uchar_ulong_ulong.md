# KsecInsertValidVm(_KSECDDLSASTATE *,void *,_EPROCESS *,uchar *,ulong,ulong)

- ea: `0x18000c7a0`
- end: `0x18000c933`
- name: `?KsecInsertValidVm@@YAJPEAU_KSECDDLSASTATE@@PEAXPEAU_EPROCESS@@PEAEKK@Z`
- size: `403`
- prototype: `__int64 __usercall@<rax>(struct _KSECDDLSASTATE *@<rcx>, void *@<rdx>, struct _EPROCESS *@<r8>, unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021bc`
- `0x18000cbb4`
- `0x18000d86c`

## callees

- `0x18000c648`
- `0x18000c7a0`
- `0x180010980`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000c7d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000c7d8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000c7f0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000c7f0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000c900`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000c900`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c90c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c90c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c8a2`
- `ntoskrnl!ExAllocatePool2` at `0x18000c865`
- `ntoskrnl!ExAllocatePool2` at `0x18000c865`

## pseudocode

```c
__int64 __fastcall KsecInsertValidVm(
        struct _KSECDDLSASTATE *a1,
        void *a2,
        struct _EPROCESS *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned __int8 *v7; // r14
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rbp
  void *Pool2; // rax
  void *v15; // r13
  void *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8

  v7 = &a4[a5];
  if ( v7 < a4 )
    return 3221225485LL;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)a1 + 568, 0);
  if ( KsecFindValidVm(a1, a3, a4, a5, 0xFFFFFFFF) == -1 )
  {
    v12 = *((_DWORD *)a1 + 145);
    if ( *((_DWORD *)a1 + 144) == v12 )
    {
      v13 = (unsigned int)(v12 + 512);
      if ( (unsigned int)v13 >= 0x6666666
        || (Pool2 = (void *)ExAllocatePool2(256, 40 * v13, 1667593035), (v15 = Pool2) == 0) )
      {
        v11 = -1073741670;
        goto LABEL_10;
      }
      v16 = (void *)*((_QWORD *)a1 + 73);
      memmove(Pool2, v16, 40LL * *((unsigned int *)a1 + 144));
      ExFreePoolWithTag(v16, 0);
      *((_QWORD *)a1 + 73) = v15;
      *((_DWORD *)a1 + 145) = v13;
    }
    v17 = *((_QWORD *)a1 + 73);
    v18 = 5LL * *((unsigned int *)a1 + 144);
    *(_QWORD *)(v17 + 8 * v18) = a2;
    *(_DWORD *)(v17 + 8 * v18 + 32) = a6;
    *(_QWORD *)(v17 + 8 * v18 + 8) = a3;
    *(_QWORD *)(v17 + 8 * v18 + 16) = a4;
    *(_QWORD *)(v17 + 8 * v18 + 24) = v7;
    ++*((_DWORD *)a1 + 144);
    v11 = 0;
  }
  else
  {
    v11 = -1073741800;
  }
LABEL_10:
  ExReleasePushLockExclusiveEx((char *)a1 + 568, 0);
  KeLeaveCriticalRegion();
  return v11;
}

```

## disassembly

```asm
0x18000c7a0  mov     [rsp+arg_8], rdx
0x18000c7a5  push    rbx
0x18000c7a6  push    rbp
0x18000c7a7  push    rsi
0x18000c7a8  push    rdi
0x18000c7a9  push    r12
0x18000c7ab  push    r13
0x18000c7ad  push    r14
0x18000c7af  push    r15
0x18000c7b1  sub     rsp, 38h
0x18000c7b5  mov     r14d, [rsp+78h+arg_20]
0x18000c7bd  mov     rsi, r9
0x18000c7c0  add     r14, r9
0x18000c7c3  mov     r12, r8
0x18000c7c6  mov     rdi, rcx
0x18000c7c9  cmp     r14, r9
0x18000c7cc  jnb     short loc_18000C7D8
0x18000c7ce  mov     eax, 0C000000Dh
0x18000c7d3  jmp     loc_18000C91A
0x18000c7d8  call    cs:__imp_KeEnterCriticalRegion
0x18000c7df  nop     dword ptr [rax+rax+00h]
0x18000c7e4  lea     r15, [rdi+238h]
0x18000c7eb  xor     edx, edx
0x18000c7ed  mov     rcx, r15
0x18000c7f0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18000c7f7  nop     dword ptr [rax+rax+00h]
0x18000c7fc  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x18000c804  or      ebx, 0FFFFFFFFh
0x18000c807  mov     r8, rsi; unsigned __int8 *
0x18000c80a  mov     [rsp+78h+var_58], ebx; unsigned int
0x18000c80e  mov     rdx, r12; struct _EPROCESS *
0x18000c811  mov     rcx, rdi; struct _KSECDDLSASTATE *
0x18000c814  call    ?KsecFindValidVm@@YAKPEAU_KSECDDLSASTATE@@PEAU_EPROCESS@@PEAEKK@Z; KsecFindValidVm(_KSECDDLSASTATE *,_EPROCESS *,uchar *,ulong,ulong)
0x18000c819  cmp     eax, ebx
0x18000c81b  jz      short loc_18000C827
0x18000c81d  mov     ebx, 0C0000018h
0x18000c822  jmp     loc_18000C8FB
0x18000c827  mov     eax, [rdi+244h]
0x18000c82d  cmp     [rdi+240h], eax
0x18000c833  jnz     loc_18000C8BB
0x18000c839  lea     ebp, [rax+200h]
0x18000c83f  cmp     ebp, 6666666h
0x18000c845  jnb     loc_18000C92C
0x18000c84b  lea     rdx, ds:0[rbp*4]
0x18000c853  mov     ecx, 100h
0x18000c858  add     rdx, rbp
0x18000c85b  mov     r8d, 6365734Bh
0x18000c861  shl     rdx, 3
0x18000c865  call    cs:__imp_ExAllocatePool2
0x18000c86c  nop     dword ptr [rax+rax+00h]
0x18000c871  mov     r13, rax
0x18000c874  test    rax, rax
0x18000c877  jz      loc_18000C92C
0x18000c87d  mov     edx, [rdi+240h]
0x18000c883  mov     rcx, rax; void *
0x18000c886  mov     rbx, [rdi+248h]
0x18000c88d  lea     r8, [rdx+rdx*4]
0x18000c891  mov     rdx, rbx; Src
0x18000c894  shl     r8, 3; Size
0x18000c898  call    memmove
0x18000c89d  xor     edx, edx; Tag
0x18000c89f  mov     rcx, rbx; P
0x18000c8a2  call    cs:__imp_ExFreePoolWithTag
0x18000c8a9  nop     dword ptr [rax+rax+00h]
0x18000c8ae  mov     [rdi+248h], r13
0x18000c8b5  mov     [rdi+244h], ebp
0x18000c8bb  mov     eax, [rdi+240h]
0x18000c8c1  mov     rdx, [rdi+248h]
0x18000c8c8  lea     r8, [rax+rax*4]
0x18000c8cc  mov     rax, [rsp+78h+arg_8]
0x18000c8d4  mov     [rdx+r8*8], rax
0x18000c8d8  mov     eax, [rsp+78h+arg_28]
0x18000c8df  mov     [rdx+r8*8+20h], eax
0x18000c8e4  mov     [rdx+r8*8+8], r12
0x18000c8e9  mov     [rdx+r8*8+10h], rsi
0x18000c8ee  mov     [rdx+r8*8+18h], r14
0x18000c8f3  inc     dword ptr [rdi+240h]
0x18000c8f9  xor     ebx, ebx
0x18000c8fb  xor     edx, edx
0x18000c8fd  mov     rcx, r15
0x18000c900  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18000c907  nop     dword ptr [rax+rax+00h]
0x18000c90c  call    cs:__imp_KeLeaveCriticalRegion
0x18000c913  nop     dword ptr [rax+rax+00h]
0x18000c918  mov     eax, ebx
0x18000c91a  add     rsp, 38h
0x18000c91e  pop     r15
0x18000c920  pop     r14
0x18000c922  pop     r13
0x18000c924  pop     r12
0x18000c926  pop     rdi
0x18000c927  pop     rsi
0x18000c928  pop     rbp
0x18000c929  pop     rbx
0x18000c92a  retn
0x18000c92c  mov     ebx, 0C000009Ah
0x18000c931  jmp     short loc_18000C8FB
```
