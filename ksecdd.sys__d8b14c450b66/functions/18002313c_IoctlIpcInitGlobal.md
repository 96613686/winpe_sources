# IoctlIpcInitGlobal

- ea: `0x18002313c`
- end: `0x1800231ee`
- name: `IoctlIpcInitGlobal`
- size: `178`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002b078`

## callees

- `0x18002313c`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x180023182`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1800231bc`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x180023182`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1800231bc`
- `ntoskrnl!KeInitializeSpinLock` at `0x180023149`
- `ntoskrnl!KeInitializeSpinLock` at `0x180023149`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1800231d5`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1800231d5`

## pseudocode

```c
NTSTATUS IoctlIpcInitGlobal()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx

  KeInitializeSpinLock(&SpinLock);
  result = ExInitializeLookasideListEx(&Lookaside, 0, 0, PagedPool, 0, 0x18u, 0x6365734Bu, 0);
  if ( result >= 0 )
  {
    v1 = ExInitializeLookasideListEx(&stru_180019720, 0, 0, (POOL_TYPE)512, 0, 0x28u, 0x6365734Bu, 0);
    if ( v1 >= 0 )
    {
      return 0;
    }
    else
    {
      ExDeleteLookasideListEx(&Lookaside);
      return v1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002313c  push    rbx
0x18002313e  sub     rsp, 40h
0x180023142  lea     rcx, SpinLock; SpinLock
0x180023149  call    cs:__imp_KeInitializeSpinLock
0x180023150  nop     dword ptr [rax+rax+00h]
0x180023155  xor     eax, eax
0x180023157  lea     rcx, Lookaside; Lookaside
0x18002315e  mov     [rsp+48h+Depth], ax; Depth
0x180023163  mov     ebx, 6365734Bh
0x180023168  mov     [rsp+48h+Tag], ebx; Tag
0x18002316c  xor     r8d, r8d; Free
0x18002316f  mov     [rsp+48h+Size], 18h; Size
0x180023178  xor     edx, edx; Allocate
0x18002317a  lea     r9d, [rax+1]; PoolType
0x18002317e  mov     [rsp+48h+Flags], eax; Flags
0x180023182  call    cs:__imp_ExInitializeLookasideListEx
0x180023189  nop     dword ptr [rax+rax+00h]
0x18002318e  test    eax, eax
0x180023190  js      short loc_1800231E7
0x180023192  xor     eax, eax
0x180023194  lea     rcx, stru_180019720; Lookaside
0x18002319b  mov     [rsp+48h+Depth], ax; Depth
0x1800231a0  mov     r9d, 200h; PoolType
0x1800231a6  mov     [rsp+48h+Tag], ebx; Tag
0x1800231aa  xor     r8d, r8d; Free
0x1800231ad  mov     [rsp+48h+Size], 28h ; '('; Size
0x1800231b6  xor     edx, edx; Allocate
0x1800231b8  mov     [rsp+48h+Flags], eax; Flags
0x1800231bc  call    cs:__imp_ExInitializeLookasideListEx
0x1800231c3  nop     dword ptr [rax+rax+00h]
0x1800231c8  mov     ebx, eax
0x1800231ca  test    eax, eax
0x1800231cc  jns     short loc_1800231E5
0x1800231ce  lea     rcx, Lookaside; Lookaside
0x1800231d5  call    cs:__imp_ExDeleteLookasideListEx
0x1800231dc  nop     dword ptr [rax+rax+00h]
0x1800231e1  mov     eax, ebx
0x1800231e3  jmp     short loc_1800231E7
0x1800231e5  xor     eax, eax
0x1800231e7  add     rsp, 40h
0x1800231eb  pop     rbx
0x1800231ec  retn
```
