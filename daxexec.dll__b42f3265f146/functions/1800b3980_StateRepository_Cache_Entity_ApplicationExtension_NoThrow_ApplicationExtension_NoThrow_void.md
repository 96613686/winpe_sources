# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x1800b3980`
- end: `0x1800b3a21`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b4e50`
- `0x1800b7104`
- `0x1800b738c`
- `0x1800b868c`
- `0x1800b8910`
- `0x1800b9520`
- `0x1800ba360`
- `0x1800bac84`
- `0x1800c839f`
- `0x1800c83d5`
- `0x1800c8477`
- `0x1800c84f5`
- `0x1800c85a9`

## callees

- `0x1800b3980`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b399a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b39b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b39d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b39f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3a0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b399a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b39b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b39d4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b39f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3a0e`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1800b3980  push    rbx
0x1800b3982  sub     rsp, 20h
0x1800b3986  mov     rbx, rcx
0x1800b3989  mov     rcx, [rcx+40h]
0x1800b398d  mov     qword ptr [rbx+40h], 0
0x1800b3995  test    rcx, rcx
0x1800b3998  jz      short loc_1800B39A6
0x1800b399a  call    cs:__imp_SRCache_Free
0x1800b39a1  nop     dword ptr [rax+rax+00h]
0x1800b39a6  mov     rcx, [rbx+38h]
0x1800b39aa  mov     qword ptr [rbx+38h], 0
0x1800b39b2  test    rcx, rcx
0x1800b39b5  jz      short loc_1800B39C3
0x1800b39b7  call    cs:__imp_SRCache_Free
0x1800b39be  nop     dword ptr [rax+rax+00h]
0x1800b39c3  mov     rcx, [rbx+30h]
0x1800b39c7  mov     qword ptr [rbx+30h], 0
0x1800b39cf  test    rcx, rcx
0x1800b39d2  jz      short loc_1800B39E0
0x1800b39d4  call    cs:__imp_SRCache_Free
0x1800b39db  nop     dword ptr [rax+rax+00h]
0x1800b39e0  mov     rcx, [rbx+28h]
0x1800b39e4  mov     qword ptr [rbx+28h], 0
0x1800b39ec  test    rcx, rcx
0x1800b39ef  jz      short loc_1800B39FD
0x1800b39f1  call    cs:__imp_SRCache_Free
0x1800b39f8  nop     dword ptr [rax+rax+00h]
0x1800b39fd  mov     rcx, [rbx+18h]
0x1800b3a01  mov     qword ptr [rbx+18h], 0
0x1800b3a09  test    rcx, rcx
0x1800b3a0c  jz      short loc_1800B3A1A
0x1800b3a0e  call    cs:__imp_SRCache_Free
0x1800b3a15  nop     dword ptr [rax+rax+00h]
0x1800b3a1a  add     rsp, 20h
0x1800b3a1e  pop     rbx
0x1800b3a1f  retn
```
