# MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)

- ea: `0x180003fb0`
- end: `0x180003ff2`
- name: `?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z`
- size: `66`
- prototype: `void __fastcall(struct MIME_MAP_TABLE **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019a0`

## callees

- `0x180003fb0`
- `0x1800066b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003fc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003fc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003feb`

## pseudocode

```c
void __fastcall MIME_MAP_TABLE::SetGlobalTable(struct MIME_MAP_TABLE **a1)
{
  AcquireSRWLockExclusive(&MIME_MAP_TABLE::sm_GlobalLock);
  if ( a1 )
  {
    if ( MIME_MAP_TABLE::sm_pGlobalTable )
    {
      MIME_MAP_TABLE::Dereference(*a1);
      _InterlockedIncrement((volatile signed __int32 *)MIME_MAP_TABLE::sm_pGlobalTable + 266);
      *a1 = MIME_MAP_TABLE::sm_pGlobalTable;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)*a1 + 266);
      MIME_MAP_TABLE::sm_pGlobalTable = *a1;
    }
  }
  else if ( MIME_MAP_TABLE::sm_pGlobalTable )
  {
    MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE::sm_pGlobalTable);
    MIME_MAP_TABLE::sm_pGlobalTable = 0;
  }
  ReleaseSRWLockExclusive(&MIME_MAP_TABLE::sm_GlobalLock);
}

```

## disassembly

```asm
0x180003fb0  push    rbx
0x180003fb2  sub     rsp, 20h
0x180003fb6  mov     rbx, rcx
0x180003fb9  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180003fc0  call    cs:__imp_AcquireSRWLockExclusive
0x180003fc6  test    rbx, rbx
0x180003fc9  jnz     loc_180005995
0x180003fcf  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180003fd6  test    rcx, rcx
0x180003fd9  jnz     loc_180005980
0x180003fdf  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK MIME_MAP_TABLE::sm_GlobalLock
0x180003fe6  add     rsp, 20h
0x180003fea  pop     rbx
0x180003feb  jmp     cs:__imp_ReleaseSRWLockExclusive
0x180005980  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180005985  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005990  jmp     loc_180003FDF
0x180005995  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18000599d  mov     rax, [rbx]
0x1800059a0  jz      short loc_1800059C7
0x1800059a2  mov     rcx, rax; this
0x1800059a5  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x1800059aa  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x1800059b1  lock inc dword ptr [rax+428h]
0x1800059b8  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x1800059bf  mov     [rbx], rax
0x1800059c2  jmp     loc_180003FDF
0x1800059c7  lock inc dword ptr [rax+428h]
0x1800059ce  mov     rax, [rbx]
0x1800059d1  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rax; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x1800059d8  jmp     loc_180003FDF
```
