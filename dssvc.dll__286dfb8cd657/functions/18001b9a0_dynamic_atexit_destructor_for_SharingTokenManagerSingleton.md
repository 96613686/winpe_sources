# _dynamic_atexit_destructor_for__SharingTokenManagerSingleton__

- ea: `0x18001b9a0`
- end: `0x18001b9fc`
- name: `_dynamic_atexit_destructor_for__SharingTokenManagerSingleton__`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180016318`
- `0x18001b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b9c7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b9c7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b9e7`

## pseudocode

```c
void dynamic_atexit_destructor_for__SharingTokenManagerSingleton__()
{
  WINBOOL v0; // [rsp+30h] [rbp+8h] BYREF
  char *v1; // [rsp+38h] [rbp+10h] BYREF

  v0 = 0;
  v1 = 0;
  InitOnceBeginInitialize(&SharingTokenManagerSingleton, 0, &v0, (LPVOID *)&v1);
  if ( v1 )
    SharingTokenDatabase::~SharingTokenDatabase((SharingTokenDatabase *)(v1 + 8));
  else
    InitOnceComplete(&SharingTokenManagerSingleton, 0, 0);
}

```

## disassembly

```asm
0x18001b9a0  mov     rax, rsp
0x18001b9a3  sub     rsp, 28h
0x18001b9a7  lea     r9, [rax+10h]; lpContext
0x18001b9ab  mov     dword ptr [rax+8], 0
0x18001b9b2  lea     r8, [rax+8]; fPending
0x18001b9b6  mov     qword ptr [rax+10h], 0
0x18001b9be  xor     edx, edx; dwFlags
0x18001b9c0  lea     rcx, ?SharingTokenManagerSingleton@@3V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@tlx@@A; lpInitOnce
0x18001b9c7  call    cs:__imp_InitOnceBeginInitialize
0x18001b9cd  mov     rcx, [rsp+28h+arg_8]
0x18001b9d2  test    rcx, rcx
0x18001b9d5  jnz     short loc_18001B9EE
0x18001b9d7  xor     r8d, r8d
0x18001b9da  lea     rcx, ?SharingTokenManagerSingleton@@3V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@tlx@@A; tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>> SharingTokenManagerSingleton
0x18001b9e1  xor     edx, edx
0x18001b9e3  add     rsp, 28h
0x18001b9e7  jmp     cs:__imp_InitOnceComplete
0x18001b9ee  add     rcx, 8; this
0x18001b9f2  call    ??1SharingTokenDatabase@@QEAA@XZ; SharingTokenDatabase::~SharingTokenDatabase(void)
0x18001b9f7  add     rsp, 28h
0x18001b9fb  retn
```
