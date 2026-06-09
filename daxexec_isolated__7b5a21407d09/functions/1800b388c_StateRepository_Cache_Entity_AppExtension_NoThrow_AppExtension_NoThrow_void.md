# StateRepository::Cache::Entity::AppExtension_NoThrow::~AppExtension_NoThrow(void)

- ea: `0x1800b388c`
- end: `0x1800b394a`
- name: `??1AppExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `190`
- prototype: `void __fastcall(StateRepository::Cache::Entity::AppExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b9520`
- `0x1800c8489`

## callees

- `0x1800b388c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b391a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3937`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b38fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b391a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3937`

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
0x1800b388c  push    rbx
0x1800b388e  sub     rsp, 20h
0x1800b3892  mov     rbx, rcx
0x1800b3895  mov     rcx, [rcx+38h]
0x1800b3899  mov     qword ptr [rbx+38h], 0
0x1800b38a1  test    rcx, rcx
0x1800b38a4  jz      short loc_1800B38B2
0x1800b38a6  call    cs:__imp_SRCache_Free
0x1800b38ad  nop     dword ptr [rax+rax+00h]
0x1800b38b2  mov     rcx, [rbx+28h]
0x1800b38b6  mov     qword ptr [rbx+28h], 0
0x1800b38be  test    rcx, rcx
0x1800b38c1  jz      short loc_1800B38CF
0x1800b38c3  call    cs:__imp_SRCache_Free
0x1800b38ca  nop     dword ptr [rax+rax+00h]
0x1800b38cf  mov     rcx, [rbx+20h]
0x1800b38d3  mov     qword ptr [rbx+20h], 0
0x1800b38db  test    rcx, rcx
0x1800b38de  jz      short loc_1800B38EC
0x1800b38e0  call    cs:__imp_SRCache_Free
0x1800b38e7  nop     dword ptr [rax+rax+00h]
0x1800b38ec  mov     rcx, [rbx+18h]
0x1800b38f0  mov     qword ptr [rbx+18h], 0
0x1800b38f8  test    rcx, rcx
0x1800b38fb  jz      short loc_1800B3909
0x1800b38fd  call    cs:__imp_SRCache_Free
0x1800b3904  nop     dword ptr [rax+rax+00h]
0x1800b3909  mov     rcx, [rbx+10h]
0x1800b390d  mov     qword ptr [rbx+10h], 0
0x1800b3915  test    rcx, rcx
0x1800b3918  jz      short loc_1800B3926
0x1800b391a  call    cs:__imp_SRCache_Free
0x1800b3921  nop     dword ptr [rax+rax+00h]
0x1800b3926  mov     rcx, [rbx+8]
0x1800b392a  mov     qword ptr [rbx+8], 0
0x1800b3932  test    rcx, rcx
0x1800b3935  jz      short loc_1800B3943
0x1800b3937  call    cs:__imp_SRCache_Free
0x1800b393e  nop     dword ptr [rax+rax+00h]
0x1800b3943  add     rsp, 20h
0x1800b3947  pop     rbx
0x1800b3948  retn
```
