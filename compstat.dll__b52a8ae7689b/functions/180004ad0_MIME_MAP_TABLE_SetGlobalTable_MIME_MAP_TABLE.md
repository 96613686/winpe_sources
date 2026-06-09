# MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)

- ea: `0x180004ad0`
- end: `0x180004b24`
- name: `?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z`
- size: `84`
- prototype: `void __fastcall(struct MIME_MAP_TABLE **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003de0`
- `0x180008004`

## callees

- `0x180004ad0`
- `0x180008480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004b1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ae0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ae0`

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
0x180004ad0  push    rbx
0x180004ad2  sub     rsp, 20h
0x180004ad6  mov     rbx, rcx
0x180004ad9  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180004ae0  call    cs:__imp_AcquireSRWLockExclusive
0x180004ae6  test    rbx, rbx
0x180004ae9  jz      loc_1800072E4
0x180004aef  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180004af7  mov     rax, [rbx]
0x180004afa  jnz     loc_180007309
0x180004b00  lock inc dword ptr [rax+428h]
0x180004b07  mov     rax, [rbx]
0x180004b0a  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rax; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180004b11  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK MIME_MAP_TABLE::sm_GlobalLock
0x180004b18  add     rsp, 20h
0x180004b1c  pop     rbx
0x180004b1d  jmp     cs:__imp_ReleaseSRWLockExclusive
0x1800072e4  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x1800072eb  test    rcx, rcx
0x1800072ee  jz      loc_180004B11
0x1800072f4  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x1800072f9  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007304  jmp     loc_180004B11
0x180007309  mov     rcx, rax; this
0x18000730c  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x180007311  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007318  lock inc dword ptr [rax+428h]
0x18000731f  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007326  mov     [rbx], rax
0x180007329  jmp     loc_180004B11
```
