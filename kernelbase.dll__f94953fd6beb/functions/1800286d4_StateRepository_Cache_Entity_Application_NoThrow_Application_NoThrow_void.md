# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x1800286d4`
- end: `0x18002879b`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800287a4`
- `0x18015626c`
- `0x180156620`

## callees

- `0x1800286d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800286ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028705`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002871c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028733`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002874a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028778`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002878f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800286ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028705`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002871c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028733`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002874a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028761`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180028778`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002878f`

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
0x1800286d4  push    rbx
0x1800286d6  sub     rsp, 20h
0x1800286da  mov     rbx, rcx
0x1800286dd  mov     rcx, [rcx+58h]
0x1800286e1  mov     qword ptr [rbx+58h], 0
0x1800286e9  test    rcx, rcx
0x1800286ec  jz      short loc_1800286F4
0x1800286ee  call    cs:__imp_SRCache_Free
0x1800286f4  mov     rcx, [rbx+50h]
0x1800286f8  mov     qword ptr [rbx+50h], 0
0x180028700  test    rcx, rcx
0x180028703  jz      short loc_18002870B
0x180028705  call    cs:__imp_SRCache_Free
0x18002870b  mov     rcx, [rbx+48h]
0x18002870f  mov     qword ptr [rbx+48h], 0
0x180028717  test    rcx, rcx
0x18002871a  jz      short loc_180028722
0x18002871c  call    cs:__imp_SRCache_Free
0x180028722  mov     rcx, [rbx+40h]
0x180028726  mov     qword ptr [rbx+40h], 0
0x18002872e  test    rcx, rcx
0x180028731  jz      short loc_180028739
0x180028733  call    cs:__imp_SRCache_Free
0x180028739  mov     rcx, [rbx+38h]
0x18002873d  mov     qword ptr [rbx+38h], 0
0x180028745  test    rcx, rcx
0x180028748  jz      short loc_180028750
0x18002874a  call    cs:__imp_SRCache_Free
0x180028750  mov     rcx, [rbx+30h]
0x180028754  mov     qword ptr [rbx+30h], 0
0x18002875c  test    rcx, rcx
0x18002875f  jz      short loc_180028767
0x180028761  call    cs:__imp_SRCache_Free
0x180028767  mov     rcx, [rbx+20h]
0x18002876b  mov     qword ptr [rbx+20h], 0
0x180028773  test    rcx, rcx
0x180028776  jz      short loc_18002877E
0x180028778  call    cs:__imp_SRCache_Free
0x18002877e  mov     rcx, [rbx+18h]
0x180028782  mov     qword ptr [rbx+18h], 0
0x18002878a  test    rcx, rcx
0x18002878d  jz      short loc_180028795
0x18002878f  call    cs:__imp_SRCache_Free
0x180028795  add     rsp, 20h
0x180028799  pop     rbx
0x18002879a  retn
```
