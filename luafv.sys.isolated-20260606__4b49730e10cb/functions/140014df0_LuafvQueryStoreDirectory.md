# LuafvQueryStoreDirectory

- ea: `0x140014df0`
- end: `0x140015072`
- name: `LuafvQueryStoreDirectory`
- size: `642`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140017cc0`

## callees

- `0x140001b34`
- `0x140006380`
- `0x140014df0`
- `0x14001b6a0`
- `0x140021cd0`
- `0x1400220ac`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140014e4b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014e96`
- `ntoskrnl!ExReleaseFastMutex` at `0x140015044`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014e4b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014e96`
- `ntoskrnl!ExReleaseFastMutex` at `0x140015044`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014e24`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014e6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140015003`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014e24`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014e6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140015003`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014f6f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014f6f`
- `FLTMGR!FltReleasePushLockEx` at `0x140015031`
- `FLTMGR!FltReleasePushLockEx` at `0x140015031`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140014e5c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140014e5c`

## pseudocode

```c
__int64 __fastcall LuafvQueryStoreDirectory(PFLT_INSTANCE Instance, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  __int64 v5; // rbx
  unsigned int v8; // r15d
  char *Pool; // rax
  int v10; // ebx
  int v11; // r9d
  __int64 v12; // rcx
  char v13; // r12
  PVOID v14; // r14
  int v15; // ecx
  __int64 v16; // rdi
  int v19; // [rsp+98h] [rbp+10h]
  struct _UNICODE_STRING *v20; // [rsp+A8h] [rbp+20h]

  v3 = *(_QWORD *)(a2 + 16);
  v5 = *(_QWORD *)(a3 + 32);
  v8 = *(_DWORD *)(v3 + 24);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(v5 + 8) == KeGetCurrentThread() )
  {
    ++*(_DWORD *)(v5 + 16);
  }
  else
  {
    ExReleaseFastMutex(&FastMutex);
    FltAcquirePushLockExclusiveEx(v5, 0);
    ExAcquireFastMutex(&FastMutex);
    *(_QWORD *)(v5 + 8) = KeGetCurrentThread();
    *(_DWORD *)(v5 + 16) = 1;
  }
  ExReleaseFastMutex(&FastMutex);
  if ( !*(_QWORD *)(a3 + 96) )
  {
    Pool = LuafvAllocatePool(1, 0x40u, 22);
    *(_QWORD *)(a3 + 96) = Pool;
    if ( !Pool )
    {
      v10 = -1073741670;
      goto LABEL_23;
    }
    memset(Pool, 0, 0x40u);
  }
  v10 = LuafvOpenDirectory(Instance, (struct _UNICODE_STRING *)a3, *(_QWORD *)(a3 + 96), v8);
  if ( v10 >= 0 )
  {
    v10 = LuafvOpenDirectory(Instance, (struct _UNICODE_STRING *)(a3 + 48), *(_QWORD *)(a3 + 96) + 32LL, v8);
    if ( v10 >= 0 )
    {
      v12 = *(_QWORD *)(v3 + 64);
      v19 = *(_DWORD *)(v3 + 40);
      v13 = *(_BYTE *)(*(_QWORD *)(a2 + 16) + 6LL);
      v20 = *(struct _UNICODE_STRING **)(v3 + 32);
      if ( !v12 )
      {
        v14 = *(PVOID *)(v3 + 56);
        if ( (unsigned int)Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline() && (*(_DWORD *)a2 & 8) == 0 )
        {
          LOBYTE(v11) = *(_BYTE *)(a2 + 80);
          goto LABEL_22;
        }
LABEL_20:
        LOBYTE(v11) = 0;
LABEL_22:
        v10 = LuafvMergeStoreDirectory(
                (int)Instance,
                a3,
                v8,
                v11,
                v19,
                (v13 & 2) != 0,
                v20,
                v13 & 1,
                a2 + 24,
                (__int64)v14);
        goto LABEL_23;
      }
      if ( (*(_BYTE *)(v12 + 10) & 5) != 0 )
        v14 = *(PVOID *)(v12 + 24);
      else
        v14 = MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000010u);
      v15 = v10;
      if ( !v14 )
        v15 = -1073741670;
      v10 = v15;
      if ( v15 >= 0 )
        goto LABEL_20;
    }
  }
LABEL_23:
  v16 = *(_QWORD *)(a3 + 32);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(v16 + 8) == KeGetCurrentThread() )
  {
    if ( (*(_DWORD *)(v16 + 16))-- != 1 )
      goto LABEL_27;
    *(_QWORD *)(v16 + 8) = 0;
  }
  FltReleasePushLockEx(v16, 0);
LABEL_27:
  ExReleaseFastMutex(&FastMutex);
  if ( v10 < 0 )
  {
    *(_DWORD *)(a2 + 24) = v10;
    *(_QWORD *)(a2 + 32) = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140014df0  push    rbx
0x140014df2  push    rsi
0x140014df3  push    rdi
0x140014df4  push    r12
0x140014df6  push    r13
0x140014df8  push    r14
0x140014dfa  push    r15
0x140014dfc  sub     rsp, 50h
0x140014e00  mov     r14, [rdx+10h]
0x140014e04  mov     r13, rcx
0x140014e07  mov     rbx, [r8+20h]
0x140014e0b  lea     rcx, FastMutex; FastMutex
0x140014e12  mov     rdi, r8
0x140014e15  mov     rsi, rdx
0x140014e18  mov     r15d, [r14+18h]
0x140014e1c  mov     [rsp+88h+arg_10], r15d
0x140014e24  call    cs:__imp_ExAcquireFastMutex
0x140014e2b  nop     dword ptr [rax+rax+00h]
0x140014e30  mov     rax, gs:188h
0x140014e39  cmp     [rbx+8], rax
0x140014e3d  jnz     short loc_140014E44
0x140014e3f  inc     dword ptr [rbx+10h]
0x140014e42  jmp     short loc_140014E8F
0x140014e44  lea     rcx, FastMutex; FastMutex
0x140014e4b  call    cs:__imp_ExReleaseFastMutex
0x140014e52  nop     dword ptr [rax+rax+00h]
0x140014e57  xor     edx, edx
0x140014e59  mov     rcx, rbx
0x140014e5c  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140014e63  nop     dword ptr [rax+rax+00h]
0x140014e68  lea     rcx, FastMutex; FastMutex
0x140014e6f  call    cs:__imp_ExAcquireFastMutex
0x140014e76  nop     dword ptr [rax+rax+00h]
0x140014e7b  mov     rax, gs:188h
0x140014e84  mov     [rbx+8], rax
0x140014e88  mov     dword ptr [rbx+10h], 1
0x140014e8f  lea     rcx, FastMutex; FastMutex
0x140014e96  call    cs:__imp_ExReleaseFastMutex
0x140014e9d  nop     dword ptr [rax+rax+00h]
0x140014ea2  cmp     qword ptr [rdi+60h], 0
0x140014ea7  jnz     short loc_140014EDB
0x140014ea9  mov     ebx, 40h ; '@'
0x140014eae  mov     r8b, 16h
0x140014eb1  mov     edx, ebx
0x140014eb3  lea     ecx, [rbx-3Fh]
0x140014eb6  call    LuafvAllocatePool
0x140014ebb  mov     [rdi+60h], rax
0x140014ebf  test    rax, rax
0x140014ec2  jnz     short loc_140014ECE
0x140014ec4  mov     ebx, 0C000009Ah
0x140014ec9  jmp     loc_140014FF8
0x140014ece  mov     r8, rbx; Size
0x140014ed1  xor     edx, edx; Val
0x140014ed3  mov     rcx, rax; void *
0x140014ed6  call    memset
0x140014edb  mov     r8, [rdi+60h]
0x140014edf  mov     r9d, r15d
0x140014ee2  mov     rdx, rdi
0x140014ee5  mov     rcx, r13; Instance
0x140014ee8  call    LuafvOpenDirectory
0x140014eed  mov     ebx, eax
0x140014eef  test    eax, eax
0x140014ef1  js      loc_140014FF8
0x140014ef7  mov     r8, [rdi+60h]
0x140014efb  lea     rdx, [rdi+30h]
0x140014eff  add     r8, 20h ; ' '
0x140014f03  mov     r9d, r15d
0x140014f06  mov     rcx, r13; Instance
0x140014f09  call    LuafvOpenDirectory
0x140014f0e  mov     ebx, eax
0x140014f10  test    eax, eax
0x140014f12  js      loc_140014FF8
0x140014f18  mov     eax, [r14+28h]
0x140014f1c  mov     rcx, [r14+40h]; MemoryDescriptorList
0x140014f20  mov     [rsp+88h+arg_8], eax
0x140014f27  mov     rax, [rsi+10h]
0x140014f2b  mov     r12b, [rax+6]
0x140014f2f  mov     rax, [r14+20h]
0x140014f33  mov     r15b, r12b
0x140014f36  shr     r15b, 1
0x140014f39  and     r15b, 1
0x140014f3d  mov     [rsp+88h+arg_18], rax
0x140014f45  test    rcx, rcx
0x140014f48  jz      short loc_140014F93
0x140014f4a  test    byte ptr [rcx+0Ah], 5
0x140014f4e  jz      short loc_140014F56
0x140014f50  mov     r14, [rcx+18h]
0x140014f54  jmp     short loc_140014F7E
0x140014f56  xor     r9d, r9d; RequestedAddress
0x140014f59  mov     [rsp+88h+Priority], 40000010h; Priority
0x140014f61  xor     edx, edx; AccessMode
0x140014f63  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140014f6b  lea     r8d, [r9+1]; CacheType
0x140014f6f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014f76  nop     dword ptr [rax+rax+00h]
0x140014f7b  mov     r14, rax
0x140014f7e  mov     ecx, ebx
0x140014f80  test    r14, r14
0x140014f83  mov     ebx, 0C000009Ah
0x140014f88  cmovz   ecx, ebx
0x140014f8b  mov     ebx, ecx
0x140014f8d  test    ecx, ecx
0x140014f8f  js      short loc_140014FF8
0x140014f91  jmp     short loc_140014FA6
0x140014f93  mov     r14, [r14+38h]
0x140014f97  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x140014f9c  test    eax, eax
0x140014f9e  jz      short loc_140014FA6
0x140014fa0  mov     eax, [rsi]
0x140014fa2  test    al, 8
0x140014fa4  jz      short loc_140014FAB
0x140014fa6  xor     r9b, r9b
0x140014fa9  jmp     short loc_140014FAF
0x140014fab  mov     r9b, [rsi+50h]; int
0x140014faf  mov     r8d, [rsp+88h+arg_10]; int
0x140014fb7  lea     rax, [rsi+18h]
0x140014fbb  mov     [rsp+88h+var_40], r14; __int64
0x140014fc0  and     r12b, 1
0x140014fc4  mov     [rsp+88h+var_48], rax; __int64
0x140014fc9  mov     rdx, rdi; int
0x140014fcc  mov     rax, [rsp+88h+arg_18]
0x140014fd4  mov     rcx, r13; int
0x140014fd7  mov     [rsp+88h+var_50], r12b; BOOLEAN
0x140014fdc  mov     [rsp+88h+var_58], rax; PUNICODE_STRING
0x140014fe1  mov     eax, [rsp+88h+arg_8]
0x140014fe8  mov     byte ptr [rsp+88h+Priority], r15b; char
0x140014fed  mov     [rsp+88h+BugCheckOnFailure], eax; int
0x140014ff1  call    LuafvMergeStoreDirectory
0x140014ff6  mov     ebx, eax
0x140014ff8  mov     rdi, [rdi+20h]
0x140014ffc  lea     rcx, FastMutex; FastMutex
0x140015003  call    cs:__imp_ExAcquireFastMutex
0x14001500a  nop     dword ptr [rax+rax+00h]
0x14001500f  mov     rax, gs:188h
0x140015018  cmp     [rdi+8], rax
0x14001501c  jnz     short loc_14001502C
0x14001501e  sub     dword ptr [rdi+10h], 1
0x140015022  jnz     short loc_14001503D
0x140015024  mov     qword ptr [rdi+8], 0
0x14001502c  xor     edx, edx
0x14001502e  mov     rcx, rdi
0x140015031  call    cs:__imp_FltReleasePushLockEx
0x140015038  nop     dword ptr [rax+rax+00h]
0x14001503d  lea     rcx, FastMutex; FastMutex
0x140015044  call    cs:__imp_ExReleaseFastMutex
0x14001504b  nop     dword ptr [rax+rax+00h]
0x140015050  test    ebx, ebx
0x140015052  jns     short loc_14001505F
0x140015054  mov     [rsi+18h], ebx
0x140015057  mov     qword ptr [rsi+20h], 0
0x14001505f  mov     eax, ebx
0x140015061  add     rsp, 50h
0x140015065  pop     r15
0x140015067  pop     r14
0x140015069  pop     r13
0x14001506b  pop     r12
0x14001506d  pop     rdi
0x14001506e  pop     rsi
0x14001506f  pop     rbx
0x140015070  retn
```
