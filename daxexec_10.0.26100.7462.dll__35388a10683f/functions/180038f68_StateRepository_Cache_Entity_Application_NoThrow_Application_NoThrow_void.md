# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180038f68`
- end: `0x180039048`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `224`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bf38`
- `0x180097590`
- `0x1800978b0`
- `0x18009aa1c`
- `0x1800b2d30`
- `0x1800b49e8`
- `0x1800b67e4`
- `0x1800b76c0`
- `0x1800b8e2c`
- `0x1800b9c4c`
- `0x1800bb394`
- `0x1800c0210`
- `0x1800c6631`
- `0x1800c6f94`
- `0x1800c7072`
- `0x1800c72c4`
- `0x1800c73ab`

## callees

- `0x180038f68`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038f7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038f99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038fb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038fcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038fe7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039001`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003901b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039035`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038f7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038f99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038fb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038fcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180038fe7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039001`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003901b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180039035`

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
0x180038f68  push    rbx
0x180038f6a  sub     rsp, 20h
0x180038f6e  mov     rbx, rcx
0x180038f71  mov     rcx, [rcx+58h]
0x180038f75  and     qword ptr [rbx+58h], 0
0x180038f7a  test    rcx, rcx
0x180038f7d  jz      short loc_180038F8B
0x180038f7f  call    cs:__imp_SRCache_Free
0x180038f86  nop     dword ptr [rax+rax+00h]
0x180038f8b  mov     rcx, [rbx+50h]
0x180038f8f  and     qword ptr [rbx+50h], 0
0x180038f94  test    rcx, rcx
0x180038f97  jz      short loc_180038FA5
0x180038f99  call    cs:__imp_SRCache_Free
0x180038fa0  nop     dword ptr [rax+rax+00h]
0x180038fa5  mov     rcx, [rbx+48h]
0x180038fa9  and     qword ptr [rbx+48h], 0
0x180038fae  test    rcx, rcx
0x180038fb1  jz      short loc_180038FBF
0x180038fb3  call    cs:__imp_SRCache_Free
0x180038fba  nop     dword ptr [rax+rax+00h]
0x180038fbf  mov     rcx, [rbx+40h]
0x180038fc3  and     qword ptr [rbx+40h], 0
0x180038fc8  test    rcx, rcx
0x180038fcb  jz      short loc_180038FD9
0x180038fcd  call    cs:__imp_SRCache_Free
0x180038fd4  nop     dword ptr [rax+rax+00h]
0x180038fd9  mov     rcx, [rbx+38h]
0x180038fdd  and     qword ptr [rbx+38h], 0
0x180038fe2  test    rcx, rcx
0x180038fe5  jz      short loc_180038FF3
0x180038fe7  call    cs:__imp_SRCache_Free
0x180038fee  nop     dword ptr [rax+rax+00h]
0x180038ff3  mov     rcx, [rbx+30h]
0x180038ff7  and     qword ptr [rbx+30h], 0
0x180038ffc  test    rcx, rcx
0x180038fff  jz      short loc_18003900D
0x180039001  call    cs:__imp_SRCache_Free
0x180039008  nop     dword ptr [rax+rax+00h]
0x18003900d  mov     rcx, [rbx+20h]
0x180039011  and     qword ptr [rbx+20h], 0
0x180039016  test    rcx, rcx
0x180039019  jz      short loc_180039027
0x18003901b  call    cs:__imp_SRCache_Free
0x180039022  nop     dword ptr [rax+rax+00h]
0x180039027  mov     rcx, [rbx+18h]
0x18003902b  and     qword ptr [rbx+18h], 0
0x180039030  test    rcx, rcx
0x180039033  jz      short loc_180039041
0x180039035  call    cs:__imp_SRCache_Free
0x18003903c  nop     dword ptr [rax+rax+00h]
0x180039041  add     rsp, 20h
0x180039045  pop     rbx
0x180039046  retn
```
