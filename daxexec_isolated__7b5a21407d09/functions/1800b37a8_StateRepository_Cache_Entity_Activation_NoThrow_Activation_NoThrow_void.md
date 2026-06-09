# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x1800b37a8`
- end: `0x1800b3883`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b7d2c`
- `0x1800bba18`
- `0x1800c8357`
- `0x1800c867b`

## callees

- `0x1800b37a8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b37c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b37df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b37fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3819`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3836`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3853`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3870`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b37c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b37df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b37fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3819`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3836`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3853`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3870`

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
0x1800b37a8  push    rbx
0x1800b37aa  sub     rsp, 20h
0x1800b37ae  mov     rbx, rcx
0x1800b37b1  mov     rcx, [rcx+40h]
0x1800b37b5  mov     qword ptr [rbx+40h], 0
0x1800b37bd  test    rcx, rcx
0x1800b37c0  jz      short loc_1800B37CE
0x1800b37c2  call    cs:__imp_SRCache_Free
0x1800b37c9  nop     dword ptr [rax+rax+00h]
0x1800b37ce  mov     rcx, [rbx+38h]
0x1800b37d2  mov     qword ptr [rbx+38h], 0
0x1800b37da  test    rcx, rcx
0x1800b37dd  jz      short loc_1800B37EB
0x1800b37df  call    cs:__imp_SRCache_Free
0x1800b37e6  nop     dword ptr [rax+rax+00h]
0x1800b37eb  mov     rcx, [rbx+30h]
0x1800b37ef  mov     qword ptr [rbx+30h], 0
0x1800b37f7  test    rcx, rcx
0x1800b37fa  jz      short loc_1800B3808
0x1800b37fc  call    cs:__imp_SRCache_Free
0x1800b3803  nop     dword ptr [rax+rax+00h]
0x1800b3808  mov     rcx, [rbx+28h]
0x1800b380c  mov     qword ptr [rbx+28h], 0
0x1800b3814  test    rcx, rcx
0x1800b3817  jz      short loc_1800B3825
0x1800b3819  call    cs:__imp_SRCache_Free
0x1800b3820  nop     dword ptr [rax+rax+00h]
0x1800b3825  mov     rcx, [rbx+20h]
0x1800b3829  mov     qword ptr [rbx+20h], 0
0x1800b3831  test    rcx, rcx
0x1800b3834  jz      short loc_1800B3842
0x1800b3836  call    cs:__imp_SRCache_Free
0x1800b383d  nop     dword ptr [rax+rax+00h]
0x1800b3842  mov     rcx, [rbx+18h]
0x1800b3846  mov     qword ptr [rbx+18h], 0
0x1800b384e  test    rcx, rcx
0x1800b3851  jz      short loc_1800B385F
0x1800b3853  call    cs:__imp_SRCache_Free
0x1800b385a  nop     dword ptr [rax+rax+00h]
0x1800b385f  mov     rcx, [rbx+8]
0x1800b3863  mov     qword ptr [rbx+8], 0
0x1800b386b  test    rcx, rcx
0x1800b386e  jz      short loc_1800B387C
0x1800b3870  call    cs:__imp_SRCache_Free
0x1800b3877  nop     dword ptr [rax+rax+00h]
0x1800b387c  add     rsp, 20h
0x1800b3880  pop     rbx
0x1800b3881  retn
```
