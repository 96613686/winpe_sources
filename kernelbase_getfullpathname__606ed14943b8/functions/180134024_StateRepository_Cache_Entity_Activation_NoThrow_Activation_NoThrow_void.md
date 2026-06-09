# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x180134024`
- end: `0x1801340ff`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180133c10`

## callees

- `0x180134024`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013403e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013405b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180134078`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180134095`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801340b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801340cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801340ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013403e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013405b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180134078`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180134095`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801340b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801340cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801340ec`

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
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free(v8);
}

```

## disassembly

```asm
0x180134024  push    rbx
0x180134026  sub     rsp, 20h
0x18013402a  mov     rbx, rcx
0x18013402d  mov     rcx, [rcx+40h]
0x180134031  mov     qword ptr [rbx+40h], 0
0x180134039  test    rcx, rcx
0x18013403c  jz      short loc_18013404A
0x18013403e  call    cs:__imp_SRCache_Free
0x180134045  nop     dword ptr [rax+rax+00h]
0x18013404a  mov     rcx, [rbx+38h]
0x18013404e  mov     qword ptr [rbx+38h], 0
0x180134056  test    rcx, rcx
0x180134059  jz      short loc_180134067
0x18013405b  call    cs:__imp_SRCache_Free
0x180134062  nop     dword ptr [rax+rax+00h]
0x180134067  mov     rcx, [rbx+30h]
0x18013406b  mov     qword ptr [rbx+30h], 0
0x180134073  test    rcx, rcx
0x180134076  jz      short loc_180134084
0x180134078  call    cs:__imp_SRCache_Free
0x18013407f  nop     dword ptr [rax+rax+00h]
0x180134084  mov     rcx, [rbx+28h]
0x180134088  mov     qword ptr [rbx+28h], 0
0x180134090  test    rcx, rcx
0x180134093  jz      short loc_1801340A1
0x180134095  call    cs:__imp_SRCache_Free
0x18013409c  nop     dword ptr [rax+rax+00h]
0x1801340a1  mov     rcx, [rbx+20h]
0x1801340a5  mov     qword ptr [rbx+20h], 0
0x1801340ad  test    rcx, rcx
0x1801340b0  jz      short loc_1801340BE
0x1801340b2  call    cs:__imp_SRCache_Free
0x1801340b9  nop     dword ptr [rax+rax+00h]
0x1801340be  mov     rcx, [rbx+18h]
0x1801340c2  mov     qword ptr [rbx+18h], 0
0x1801340ca  test    rcx, rcx
0x1801340cd  jz      short loc_1801340DB
0x1801340cf  call    cs:__imp_SRCache_Free
0x1801340d6  nop     dword ptr [rax+rax+00h]
0x1801340db  mov     rcx, [rbx+8]
0x1801340df  mov     qword ptr [rbx+8], 0
0x1801340e7  test    rcx, rcx
0x1801340ea  jz      short loc_1801340F8
0x1801340ec  call    cs:__imp_SRCache_Free
0x1801340f3  nop     dword ptr [rax+rax+00h]
0x1801340f8  add     rsp, 20h
0x1801340fc  pop     rbx
0x1801340fd  retn
```
