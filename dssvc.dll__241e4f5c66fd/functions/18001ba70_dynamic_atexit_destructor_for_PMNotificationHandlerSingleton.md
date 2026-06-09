# _dynamic_atexit_destructor_for__PMNotificationHandlerSingleton__

- ea: `0x18001ba70`
- end: `0x18001bac8`
- name: `_dynamic_atexit_destructor_for__PMNotificationHandlerSingleton__`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013394`
- `0x18001ba70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ba97`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001ba97`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bab7`

## pseudocode

```c
void dynamic_atexit_destructor_for__PMNotificationHandlerSingleton__()
{
  WINBOOL v0; // [rsp+30h] [rbp+8h] BYREF
  PMNotificationHandler *v1; // [rsp+38h] [rbp+10h] BYREF

  v0 = 0;
  v1 = 0;
  InitOnceBeginInitialize(&PMNotificationHandlerSingleton, 0, &v0, (LPVOID *)&v1);
  if ( v1 )
    PMNotificationHandler::~PMNotificationHandler(v1);
  else
    InitOnceComplete(&PMNotificationHandlerSingleton, 0, 0);
}

```

## disassembly

```asm
0x18001ba70  mov     rax, rsp
0x18001ba73  sub     rsp, 28h
0x18001ba77  lea     r9, [rax+10h]; lpContext
0x18001ba7b  mov     dword ptr [rax+8], 0
0x18001ba82  lea     r8, [rax+8]; fPending
0x18001ba86  mov     qword ptr [rax+10h], 0
0x18001ba8e  xor     edx, edx; dwFlags
0x18001ba90  lea     rcx, ?PMNotificationHandlerSingleton@@3V?$static_lazy@VPMNotificationHandler@@$0A@V?$lazy_construct@VPMNotificationHandler@@@tlx@@@tlx@@A; lpInitOnce
0x18001ba97  call    cs:__imp_InitOnceBeginInitialize
0x18001ba9d  mov     rcx, [rsp+28h+arg_8]; this
0x18001baa2  test    rcx, rcx
0x18001baa5  jnz     short loc_18001BABE
0x18001baa7  xor     r8d, r8d
0x18001baaa  lea     rcx, ?PMNotificationHandlerSingleton@@3V?$static_lazy@VPMNotificationHandler@@$0A@V?$lazy_construct@VPMNotificationHandler@@@tlx@@@tlx@@A; tlx::static_lazy<PMNotificationHandler,0,tlx::lazy_construct<PMNotificationHandler>> PMNotificationHandlerSingleton
0x18001bab1  xor     edx, edx
0x18001bab3  add     rsp, 28h
0x18001bab7  jmp     cs:__imp_InitOnceComplete
0x18001babe  call    ??1PMNotificationHandler@@QEAA@XZ; PMNotificationHandler::~PMNotificationHandler(void)
0x18001bac3  add     rsp, 28h
0x18001bac7  retn
```
