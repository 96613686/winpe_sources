# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x1800b1600`
- end: `0x1800b16c6`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `198`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b5f44`
- `0x1800b9c4c`
- `0x1800c701e`
- `0x1800c73bd`

## callees

- `0x1800b1600`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1617`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b164b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b167f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1699`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b16b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1617`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b164b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b167f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b1699`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b16b3`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

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
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1800b1600  push    rbx
0x1800b1602  sub     rsp, 20h
0x1800b1606  mov     rbx, rcx
0x1800b1609  mov     rcx, [rcx+40h]
0x1800b160d  and     qword ptr [rbx+40h], 0
0x1800b1612  test    rcx, rcx
0x1800b1615  jz      short loc_1800B1623
0x1800b1617  call    cs:__imp_SRCache_Free
0x1800b161e  nop     dword ptr [rax+rax+00h]
0x1800b1623  mov     rcx, [rbx+38h]
0x1800b1627  and     qword ptr [rbx+38h], 0
0x1800b162c  test    rcx, rcx
0x1800b162f  jz      short loc_1800B163D
0x1800b1631  call    cs:__imp_SRCache_Free
0x1800b1638  nop     dword ptr [rax+rax+00h]
0x1800b163d  mov     rcx, [rbx+30h]
0x1800b1641  and     qword ptr [rbx+30h], 0
0x1800b1646  test    rcx, rcx
0x1800b1649  jz      short loc_1800B1657
0x1800b164b  call    cs:__imp_SRCache_Free
0x1800b1652  nop     dword ptr [rax+rax+00h]
0x1800b1657  mov     rcx, [rbx+28h]
0x1800b165b  and     qword ptr [rbx+28h], 0
0x1800b1660  test    rcx, rcx
0x1800b1663  jz      short loc_1800B1671
0x1800b1665  call    cs:__imp_SRCache_Free
0x1800b166c  nop     dword ptr [rax+rax+00h]
0x1800b1671  mov     rcx, [rbx+20h]
0x1800b1675  and     qword ptr [rbx+20h], 0
0x1800b167a  test    rcx, rcx
0x1800b167d  jz      short loc_1800B168B
0x1800b167f  call    cs:__imp_SRCache_Free
0x1800b1686  nop     dword ptr [rax+rax+00h]
0x1800b168b  mov     rcx, [rbx+18h]
0x1800b168f  and     qword ptr [rbx+18h], 0
0x1800b1694  test    rcx, rcx
0x1800b1697  jz      short loc_1800B16A5
0x1800b1699  call    cs:__imp_SRCache_Free
0x1800b16a0  nop     dword ptr [rax+rax+00h]
0x1800b16a5  mov     rcx, [rbx+8]
0x1800b16a9  and     qword ptr [rbx+8], 0
0x1800b16ae  test    rcx, rcx
0x1800b16b1  jz      short loc_1800B16BF
0x1800b16b3  call    cs:__imp_SRCache_Free
0x1800b16ba  nop     dword ptr [rax+rax+00h]
0x1800b16bf  add     rsp, 20h
0x1800b16c3  pop     rbx
0x1800b16c4  retn
```
