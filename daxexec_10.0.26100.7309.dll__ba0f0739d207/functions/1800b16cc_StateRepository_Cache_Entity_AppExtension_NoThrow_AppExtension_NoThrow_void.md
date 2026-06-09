# StateRepository::Cache::Entity::AppExtension_NoThrow::~AppExtension_NoThrow(void)

- ea: `0x1800b16cc`
- end: `0x1800b1778`
- name: `??1AppExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `172`
- prototype: `void __fastcall(StateRepository::Cache::Entity::AppExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b76c0`
- `0x1800c7180`

## callees

- `0x1800b16cc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b16e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b16fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1717`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1731`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b174b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1765`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b16e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b16fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1717`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1731`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b174b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1765`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::~AppExtension_NoThrow(
        StateRepository::Cache::Entity::AppExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v7 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1800b16cc  push    rbx
0x1800b16ce  sub     rsp, 20h
0x1800b16d2  mov     rbx, rcx
0x1800b16d5  mov     rcx, [rcx+38h]
0x1800b16d9  and     qword ptr [rbx+38h], 0
0x1800b16de  test    rcx, rcx
0x1800b16e1  jz      short loc_1800B16EF
0x1800b16e3  call    cs:__imp_SRCache_Free
0x1800b16ea  nop     dword ptr [rax+rax+00h]
0x1800b16ef  mov     rcx, [rbx+28h]
0x1800b16f3  and     qword ptr [rbx+28h], 0
0x1800b16f8  test    rcx, rcx
0x1800b16fb  jz      short loc_1800B1709
0x1800b16fd  call    cs:__imp_SRCache_Free
0x1800b1704  nop     dword ptr [rax+rax+00h]
0x1800b1709  mov     rcx, [rbx+20h]
0x1800b170d  and     qword ptr [rbx+20h], 0
0x1800b1712  test    rcx, rcx
0x1800b1715  jz      short loc_1800B1723
0x1800b1717  call    cs:__imp_SRCache_Free
0x1800b171e  nop     dword ptr [rax+rax+00h]
0x1800b1723  mov     rcx, [rbx+18h]
0x1800b1727  and     qword ptr [rbx+18h], 0
0x1800b172c  test    rcx, rcx
0x1800b172f  jz      short loc_1800B173D
0x1800b1731  call    cs:__imp_SRCache_Free
0x1800b1738  nop     dword ptr [rax+rax+00h]
0x1800b173d  mov     rcx, [rbx+10h]
0x1800b1741  and     qword ptr [rbx+10h], 0
0x1800b1746  test    rcx, rcx
0x1800b1749  jz      short loc_1800B1757
0x1800b174b  call    cs:__imp_SRCache_Free
0x1800b1752  nop     dword ptr [rax+rax+00h]
0x1800b1757  mov     rcx, [rbx+8]
0x1800b175b  and     qword ptr [rbx+8], 0
0x1800b1760  test    rcx, rcx
0x1800b1763  jz      short loc_1800B1771
0x1800b1765  call    cs:__imp_SRCache_Free
0x1800b176c  nop     dword ptr [rax+rax+00h]
0x1800b1771  add     rsp, 20h
0x1800b1775  pop     rbx
0x1800b1776  retn
```
