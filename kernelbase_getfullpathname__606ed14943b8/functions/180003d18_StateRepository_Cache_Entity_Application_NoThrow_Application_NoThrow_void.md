# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180003d18`
- end: `0x180003e10`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `248`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e18`
- `0x180160dfc`
- `0x1801611cc`

## callees

- `0x180003d18`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003da6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003dc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003de0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003dfd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003d89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003da6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003dc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003de0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003dfd`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
        StateRepository::Cache::Entity::Application_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free(v8);
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free(v9);
}

```

## disassembly

```asm
0x180003d18  push    rbx
0x180003d1a  sub     rsp, 20h
0x180003d1e  mov     rbx, rcx
0x180003d21  mov     rcx, [rcx+58h]
0x180003d25  mov     qword ptr [rbx+58h], 0
0x180003d2d  test    rcx, rcx
0x180003d30  jz      short loc_180003D3E
0x180003d32  call    cs:__imp_SRCache_Free
0x180003d39  nop     dword ptr [rax+rax+00h]
0x180003d3e  mov     rcx, [rbx+50h]
0x180003d42  mov     qword ptr [rbx+50h], 0
0x180003d4a  test    rcx, rcx
0x180003d4d  jz      short loc_180003D5B
0x180003d4f  call    cs:__imp_SRCache_Free
0x180003d56  nop     dword ptr [rax+rax+00h]
0x180003d5b  mov     rcx, [rbx+48h]
0x180003d5f  mov     qword ptr [rbx+48h], 0
0x180003d67  test    rcx, rcx
0x180003d6a  jz      short loc_180003D78
0x180003d6c  call    cs:__imp_SRCache_Free
0x180003d73  nop     dword ptr [rax+rax+00h]
0x180003d78  mov     rcx, [rbx+40h]
0x180003d7c  mov     qword ptr [rbx+40h], 0
0x180003d84  test    rcx, rcx
0x180003d87  jz      short loc_180003D95
0x180003d89  call    cs:__imp_SRCache_Free
0x180003d90  nop     dword ptr [rax+rax+00h]
0x180003d95  mov     rcx, [rbx+38h]
0x180003d99  mov     qword ptr [rbx+38h], 0
0x180003da1  test    rcx, rcx
0x180003da4  jz      short loc_180003DB2
0x180003da6  call    cs:__imp_SRCache_Free
0x180003dad  nop     dword ptr [rax+rax+00h]
0x180003db2  mov     rcx, [rbx+30h]
0x180003db6  mov     qword ptr [rbx+30h], 0
0x180003dbe  test    rcx, rcx
0x180003dc1  jz      short loc_180003DCF
0x180003dc3  call    cs:__imp_SRCache_Free
0x180003dca  nop     dword ptr [rax+rax+00h]
0x180003dcf  mov     rcx, [rbx+20h]
0x180003dd3  mov     qword ptr [rbx+20h], 0
0x180003ddb  test    rcx, rcx
0x180003dde  jz      short loc_180003DEC
0x180003de0  call    cs:__imp_SRCache_Free
0x180003de7  nop     dword ptr [rax+rax+00h]
0x180003dec  mov     rcx, [rbx+18h]
0x180003df0  mov     qword ptr [rbx+18h], 0
0x180003df8  test    rcx, rcx
0x180003dfb  jz      short loc_180003E09
0x180003dfd  call    cs:__imp_SRCache_Free
0x180003e04  nop     dword ptr [rax+rax+00h]
0x180003e09  add     rsp, 20h
0x180003e0d  pop     rbx
0x180003e0e  retn
```
