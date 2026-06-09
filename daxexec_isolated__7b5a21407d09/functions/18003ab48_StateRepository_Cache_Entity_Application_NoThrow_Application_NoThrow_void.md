# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x18003ab48`
- end: `0x18003ac40`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `248`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x18003db44`
- `0x180098f10`
- `0x1800991e0`
- `0x18009c488`
- `0x1800b4e50`
- `0x1800b671c`
- `0x1800b868c`
- `0x1800b9520`
- `0x1800bac84`
- `0x1800bba18`
- `0x1800bd198`
- `0x1800c1e59`
- `0x1800c7a33`
- `0x1800c830f`
- `0x1800c837b`
- `0x1800c8453`
- `0x1800c8585`
- `0x1800c8669`

## callees

- `0x18003ab48`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ab62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ab7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ab9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ac10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ac2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ab62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ab7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ab9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003abf3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ac10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ac2d`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free();
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18003ab48  push    rbx
0x18003ab4a  sub     rsp, 20h
0x18003ab4e  mov     rbx, rcx
0x18003ab51  mov     rcx, [rcx+58h]
0x18003ab55  mov     qword ptr [rbx+58h], 0
0x18003ab5d  test    rcx, rcx
0x18003ab60  jz      short loc_18003AB6E
0x18003ab62  call    cs:__imp_SRCache_Free
0x18003ab69  nop     dword ptr [rax+rax+00h]
0x18003ab6e  mov     rcx, [rbx+50h]
0x18003ab72  mov     qword ptr [rbx+50h], 0
0x18003ab7a  test    rcx, rcx
0x18003ab7d  jz      short loc_18003AB8B
0x18003ab7f  call    cs:__imp_SRCache_Free
0x18003ab86  nop     dword ptr [rax+rax+00h]
0x18003ab8b  mov     rcx, [rbx+48h]
0x18003ab8f  mov     qword ptr [rbx+48h], 0
0x18003ab97  test    rcx, rcx
0x18003ab9a  jz      short loc_18003ABA8
0x18003ab9c  call    cs:__imp_SRCache_Free
0x18003aba3  nop     dword ptr [rax+rax+00h]
0x18003aba8  mov     rcx, [rbx+40h]
0x18003abac  mov     qword ptr [rbx+40h], 0
0x18003abb4  test    rcx, rcx
0x18003abb7  jz      short loc_18003ABC5
0x18003abb9  call    cs:__imp_SRCache_Free
0x18003abc0  nop     dword ptr [rax+rax+00h]
0x18003abc5  mov     rcx, [rbx+38h]
0x18003abc9  mov     qword ptr [rbx+38h], 0
0x18003abd1  test    rcx, rcx
0x18003abd4  jz      short loc_18003ABE2
0x18003abd6  call    cs:__imp_SRCache_Free
0x18003abdd  nop     dword ptr [rax+rax+00h]
0x18003abe2  mov     rcx, [rbx+30h]
0x18003abe6  mov     qword ptr [rbx+30h], 0
0x18003abee  test    rcx, rcx
0x18003abf1  jz      short loc_18003ABFF
0x18003abf3  call    cs:__imp_SRCache_Free
0x18003abfa  nop     dword ptr [rax+rax+00h]
0x18003abff  mov     rcx, [rbx+20h]
0x18003ac03  mov     qword ptr [rbx+20h], 0
0x18003ac0b  test    rcx, rcx
0x18003ac0e  jz      short loc_18003AC1C
0x18003ac10  call    cs:__imp_SRCache_Free
0x18003ac17  nop     dword ptr [rax+rax+00h]
0x18003ac1c  mov     rcx, [rbx+18h]
0x18003ac20  mov     qword ptr [rbx+18h], 0
0x18003ac28  test    rcx, rcx
0x18003ac2b  jz      short loc_18003AC39
0x18003ac2d  call    cs:__imp_SRCache_Free
0x18003ac34  nop     dword ptr [rax+rax+00h]
0x18003ac39  add     rsp, 20h
0x18003ac3d  pop     rbx
0x18003ac3e  retn
```
