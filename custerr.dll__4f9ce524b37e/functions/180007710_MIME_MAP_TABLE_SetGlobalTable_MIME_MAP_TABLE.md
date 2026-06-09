# MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)

- ea: `0x180007710`
- end: `0x180007798`
- name: `?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z`
- size: `136`
- prototype: `void __fastcall(struct MIME_MAP_TABLE **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002aac`
- `0x180007524`

## callees

- `0x180002c28`
- `0x180007710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007720`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007720`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007791`

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
0x180007710  push    rbx
0x180007712  sub     rsp, 20h
0x180007716  mov     rbx, rcx
0x180007719  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180007720  call    cs:__imp_AcquireSRWLockExclusive
0x180007726  test    rbx, rbx
0x180007729  jnz     short loc_180007745
0x18000772b  mov     rcx, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; this
0x180007732  test    rcx, rcx
0x180007735  jz      short loc_180007785
0x180007737  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x18000773c  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rbx; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007743  jmp     short loc_180007785
0x180007745  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18000774d  mov     rax, [rbx]
0x180007750  jz      short loc_180007774
0x180007752  mov     rcx, rax; this
0x180007755  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x18000775a  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007761  lock inc dword ptr [rax+428h]
0x180007768  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18000776f  mov     [rbx], rax
0x180007772  jmp     short loc_180007785
0x180007774  lock inc dword ptr [rax+428h]
0x18000777b  mov     rax, [rbx]
0x18000777e  mov     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, rax; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180007785  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK MIME_MAP_TABLE::sm_GlobalLock
0x18000778c  add     rsp, 20h
0x180007790  pop     rbx
0x180007791  jmp     cs:__imp_ReleaseSRWLockExclusive
```
