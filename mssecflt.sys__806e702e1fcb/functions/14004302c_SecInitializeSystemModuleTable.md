# SecInitializeSystemModuleTable

- ea: `0x14004302c`
- end: `0x1400430f0`
- name: `SecInitializeSystemModuleTable`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14004266c`

## callees

- `0x140011610`
- `0x1400119c0`
- `0x14004302c`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140043091`
- `ntoskrnl!ExInitializeResourceLite` at `0x140043091`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400430c6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400430c6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004305b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004305b`

## pseudocode

```c
__int64 SecInitializeSystemModuleTable()
{
  unsigned int v0; // ebx
  struct _ERESOURCE *PoolWithTag; // rax
  PERESOURCE v2; // rcx

  v0 = 0;
  if ( qword_140020008 )
    PoolWithTag = (struct _ERESOURCE *)qword_140020008(64, 320, 1416454995);
  else
    PoolWithTag = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x140u, 0x546D6353u);
  SecSystemModuleTable = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x140u);
    ExInitializeResourceLite(SecSystemModuleTable);
    ExInitializePagedLookasideList(
      (PPAGED_LOOKASIDE_LIST)&SecSystemModuleTable[1].ActiveCount,
      0,
      0,
      0,
      0x60u,
      0x786D6353u,
      0);
    v2 = SecSystemModuleTable;
    SecSystemModuleTable[2].OwnerEntry.OwnerThread = 0;
    *(_QWORD *)&v2[2].OwnerEntry.0 = 0;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v0;
}

```

## disassembly

```asm
0x14004302c  push    rbx
0x14004302e  sub     rsp, 40h
0x140043032  mov     rax, cs:qword_140020008
0x140043039  xor     ebx, ebx
0x14004303b  mov     edx, 140h; NumberOfBytes
0x140043040  mov     r8d, 546D6353h; Tag
0x140043046  test    rax, rax
0x140043049  jz      short loc_140043056
0x14004304b  lea     ecx, [rbx+40h]
0x14004304e  call    cs:__guard_dispatch_icall_fptr
0x140043054  jmp     short loc_140043067
0x140043056  mov     ecx, 200h; PoolType
0x14004305b  call    cs:__imp_ExAllocatePoolWithTag
0x140043062  nop     dword ptr [rax+rax+00h]
0x140043067  mov     cs:SecSystemModuleTable, rax
0x14004306e  test    rax, rax
0x140043071  jnz     short loc_14004307A
0x140043073  mov     ebx, 0C000009Ah
0x140043078  jmp     short loc_1400430E7
0x14004307a  xor     edx, edx; Val
0x14004307c  mov     r8d, 140h; Size
0x140043082  mov     rcx, rax; void *
0x140043085  call    memset
0x14004308a  mov     rcx, cs:SecSystemModuleTable; Resource
0x140043091  call    cs:__imp_ExInitializeResourceLite
0x140043098  nop     dword ptr [rax+rax+00h]
0x14004309d  mov     rcx, cs:SecSystemModuleTable
0x1400430a4  xor     r9d, r9d; Flags
0x1400430a7  mov     [rsp+48h+Depth], bx; Depth
0x1400430ac  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400430b0  mov     [rsp+48h+Tag], 786D6353h; Tag
0x1400430b8  xor     r8d, r8d; Free
0x1400430bb  xor     edx, edx; Allocate
0x1400430bd  mov     [rsp+48h+Size], 60h ; '`'; Size
0x1400430c6  call    cs:__imp_ExInitializePagedLookasideList
0x1400430cd  nop     dword ptr [rax+rax+00h]
0x1400430d2  mov     rcx, cs:SecSystemModuleTable
0x1400430d9  mov     [rcx+100h], rbx
0x1400430e0  mov     [rcx+108h], rbx
0x1400430e7  mov     eax, ebx
0x1400430e9  add     rsp, 40h
0x1400430ed  pop     rbx
0x1400430ee  retn
```
