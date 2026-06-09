# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18003917c`
- end: `0x18003920e`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bf38`
- `0x18003d844`
- `0x18003db28`
- `0x180097390`
- `0x180097600`
- `0x180097b00`
- `0x18009d790`
- `0x18009f318`
- `0x1800b5cac`
- `0x1800b83a4`
- `0x1800b9910`
- `0x1800b9f80`
- `0x1800c0222`
- `0x1800c030c`
- `0x1800c6643`

## callees

- `0x18003917c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039193`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039193`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800391fb`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(
        StateRepository::Cache::Entity::Package_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18003917c  push    rbx
0x18003917e  sub     rsp, 20h
0x180039182  mov     rbx, rcx
0x180039185  mov     rcx, [rcx+58h]
0x180039189  and     qword ptr [rbx+58h], 0
0x18003918e  test    rcx, rcx
0x180039191  jz      short loc_18003919F
0x180039193  call    cs:__imp_SRCache_Free
0x18003919a  nop     dword ptr [rax+rax+00h]
0x18003919f  mov     rcx, [rbx+48h]
0x1800391a3  and     qword ptr [rbx+48h], 0
0x1800391a8  test    rcx, rcx
0x1800391ab  jz      short loc_1800391B9
0x1800391ad  call    cs:__imp_SRCache_Free
0x1800391b4  nop     dword ptr [rax+rax+00h]
0x1800391b9  mov     rcx, [rbx+40h]
0x1800391bd  and     qword ptr [rbx+40h], 0
0x1800391c2  test    rcx, rcx
0x1800391c5  jz      short loc_1800391D3
0x1800391c7  call    cs:__imp_SRCache_Free
0x1800391ce  nop     dword ptr [rax+rax+00h]
0x1800391d3  mov     rcx, [rbx+38h]
0x1800391d7  and     qword ptr [rbx+38h], 0
0x1800391dc  test    rcx, rcx
0x1800391df  jz      short loc_1800391ED
0x1800391e1  call    cs:__imp_SRCache_Free
0x1800391e8  nop     dword ptr [rax+rax+00h]
0x1800391ed  mov     rcx, [rbx+8]
0x1800391f1  and     qword ptr [rbx+8], 0
0x1800391f6  test    rcx, rcx
0x1800391f9  jz      short loc_180039207
0x1800391fb  call    cs:__imp_SRCache_Free
0x180039202  nop     dword ptr [rax+rax+00h]
0x180039207  add     rsp, 20h
0x18003920b  pop     rbx
0x18003920c  retn
```
