# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x1800b17ac`
- end: `0x1800b183e`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b2d30`
- `0x1800b52fc`
- `0x1800b5598`
- `0x1800b67e4`
- `0x1800b6a64`
- `0x1800b76c0`
- `0x1800b84ec`
- `0x1800b8e2c`
- `0x1800c7096`
- `0x1800c70cc`
- `0x1800c716e`
- `0x1800c7222`
- `0x1800c72e8`

## callees

- `0x1800b17ac`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b17c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b17dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b17f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1811`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b182b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b17c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b17dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b17f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1811`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b182b`

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
0x1800b17ac  push    rbx
0x1800b17ae  sub     rsp, 20h
0x1800b17b2  mov     rbx, rcx
0x1800b17b5  mov     rcx, [rcx+40h]
0x1800b17b9  and     qword ptr [rbx+40h], 0
0x1800b17be  test    rcx, rcx
0x1800b17c1  jz      short loc_1800B17CF
0x1800b17c3  call    cs:__imp_SRCache_Free
0x1800b17ca  nop     dword ptr [rax+rax+00h]
0x1800b17cf  mov     rcx, [rbx+38h]
0x1800b17d3  and     qword ptr [rbx+38h], 0
0x1800b17d8  test    rcx, rcx
0x1800b17db  jz      short loc_1800B17E9
0x1800b17dd  call    cs:__imp_SRCache_Free
0x1800b17e4  nop     dword ptr [rax+rax+00h]
0x1800b17e9  mov     rcx, [rbx+30h]
0x1800b17ed  and     qword ptr [rbx+30h], 0
0x1800b17f2  test    rcx, rcx
0x1800b17f5  jz      short loc_1800B1803
0x1800b17f7  call    cs:__imp_SRCache_Free
0x1800b17fe  nop     dword ptr [rax+rax+00h]
0x1800b1803  mov     rcx, [rbx+28h]
0x1800b1807  and     qword ptr [rbx+28h], 0
0x1800b180c  test    rcx, rcx
0x1800b180f  jz      short loc_1800B181D
0x1800b1811  call    cs:__imp_SRCache_Free
0x1800b1818  nop     dword ptr [rax+rax+00h]
0x1800b181d  mov     rcx, [rbx+18h]
0x1800b1821  and     qword ptr [rbx+18h], 0
0x1800b1826  test    rcx, rcx
0x1800b1829  jz      short loc_1800B1837
0x1800b182b  call    cs:__imp_SRCache_Free
0x1800b1832  nop     dword ptr [rax+rax+00h]
0x1800b1837  add     rsp, 20h
0x1800b183b  pop     rbx
0x1800b183c  retn
```
