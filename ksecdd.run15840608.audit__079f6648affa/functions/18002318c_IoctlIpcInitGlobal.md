# IoctlIpcInitGlobal

- ea: `0x18002318c`
- end: `0x18002323e`
- name: `IoctlIpcInitGlobal`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002b078`

## callees

- `0x18002318c`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x1800231d2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x18002320c`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1800231d2`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x18002320c`
- `ntoskrnl!KeInitializeSpinLock` at `0x180023199`
- `ntoskrnl!KeInitializeSpinLock` at `0x180023199`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x180023225`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x180023225`

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
0x18002318c  push    rbx
0x18002318e  sub     rsp, 40h
0x180023192  lea     rcx, SpinLock; SpinLock
0x180023199  call    cs:__imp_KeInitializeSpinLock
0x1800231a0  nop     dword ptr [rax+rax+00h]
0x1800231a5  xor     eax, eax
0x1800231a7  lea     rcx, Lookaside; Lookaside
0x1800231ae  mov     [rsp+48h+Depth], ax; Depth
0x1800231b3  mov     ebx, 6365734Bh
0x1800231b8  mov     [rsp+48h+Tag], ebx; Tag
0x1800231bc  xor     r8d, r8d; Free
0x1800231bf  mov     [rsp+48h+Size], 18h; Size
0x1800231c8  xor     edx, edx; Allocate
0x1800231ca  lea     r9d, [rax+1]; PoolType
0x1800231ce  mov     [rsp+48h+Flags], eax; Flags
0x1800231d2  call    cs:__imp_ExInitializeLookasideListEx
0x1800231d9  nop     dword ptr [rax+rax+00h]
0x1800231de  test    eax, eax
0x1800231e0  js      short loc_180023237
0x1800231e2  xor     eax, eax
0x1800231e4  lea     rcx, stru_180019720; Lookaside
0x1800231eb  mov     [rsp+48h+Depth], ax; Depth
0x1800231f0  mov     r9d, 200h; PoolType
0x1800231f6  mov     [rsp+48h+Tag], ebx; Tag
0x1800231fa  xor     r8d, r8d; Free
0x1800231fd  mov     [rsp+48h+Size], 28h ; '('; Size
0x180023206  xor     edx, edx; Allocate
0x180023208  mov     [rsp+48h+Flags], eax; Flags
0x18002320c  call    cs:__imp_ExInitializeLookasideListEx
0x180023213  nop     dword ptr [rax+rax+00h]
0x180023218  mov     ebx, eax
0x18002321a  test    eax, eax
0x18002321c  jns     short loc_180023235
0x18002321e  lea     rcx, Lookaside; Lookaside
0x180023225  call    cs:__imp_ExDeleteLookasideListEx
0x18002322c  nop     dword ptr [rax+rax+00h]
0x180023231  mov     eax, ebx
0x180023233  jmp     short loc_180023237
0x180023235  xor     eax, eax
0x180023237  add     rsp, 40h
0x18002323b  pop     rbx
0x18002323c  retn
```
