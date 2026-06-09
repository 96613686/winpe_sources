# CONFIG_CHANGE_NOTIFIER::~CONFIG_CHANGE_NOTIFIER(void)

- ea: `0x18001a5c4`
- end: `0x18001a642`
- name: `??1CONFIG_CHANGE_NOTIFIER@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CONFIG_CHANGE_NOTIFIER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a450`

## callees

- `0x18001a314`
- `0x18001a5c4`
- `0x180051c64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a61c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a61c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a629`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a629`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001a63b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a5db`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a5db`

## pseudocode

```c
void __fastcall CONFIG_CHANGE_NOTIFIER::~CONFIG_CHANGE_NOTIFIER(PTP_CLEANUP_GROUP *this)
{
  unsigned __int16 v2; // si
  _QWORD *i; // r14
  __int64 v4; // rbx
  struct _TP_CLEANUP_GROUP *v5; // rcx

  CONFIG_CHANGE_NOTIFIER::SetChangeHandler((CONFIG_CHANGE_NOTIFIER *)this, 0);
  v2 = 0;
  for ( i = BUFFER::QueryPtr((BUFFER *)this); v2 < *((_WORD *)this + 24); i[v4] = 0 )
  {
    v4 = v2;
    CHANGE_LISTENER::DereferenceChangeListener((CHANGE_LISTENER *)i[v2++]);
  }
  v5 = this[18];
  if ( v5 )
  {
    CloseThreadpoolCleanupGroupMembers(v5, 0, 0);
    CloseThreadpoolCleanupGroup(this[18]);
  }
  BUFFER::~BUFFER((BUFFER *)this);
}

```

## disassembly

```asm
0x18001a5c4  push    rbx
0x18001a5c6  push    rsi
0x18001a5c7  push    rdi
0x18001a5c8  push    r14
0x18001a5ca  sub     rsp, 28h
0x18001a5ce  xor     edx, edx; struct IAppHostChangeHandler *
0x18001a5d0  mov     rdi, rcx
0x18001a5d3  call    ?SetChangeHandler@CONFIG_CHANGE_NOTIFIER@@QEAAJPEAUIAppHostChangeHandler@@@Z; CONFIG_CHANGE_NOTIFIER::SetChangeHandler(IAppHostChangeHandler *)
0x18001a5d8  mov     rcx, rdi
0x18001a5db  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001a5e1  xor     edx, edx
0x18001a5e3  xor     esi, esi
0x18001a5e5  mov     r14, rax
0x18001a5e8  cmp     dx, [rdi+30h]
0x18001a5ec  jnb     short loc_18001A60B
0x18001a5ee  movzx   ebx, si
0x18001a5f1  mov     rcx, [r14+rbx*8]; this
0x18001a5f5  call    ?DereferenceChangeListener@CHANGE_LISTENER@@QEAAXXZ; CHANGE_LISTENER::DereferenceChangeListener(void)
0x18001a5fa  inc     si
0x18001a5fd  mov     qword ptr [r14+rbx*8], 0
0x18001a605  cmp     si, [rdi+30h]
0x18001a609  jb      short loc_18001A5EE
0x18001a60b  mov     rcx, [rdi+90h]; ptpcg
0x18001a612  test    rcx, rcx
0x18001a615  jz      short loc_18001A62F
0x18001a617  xor     r8d, r8d; pvCleanupContext
0x18001a61a  xor     edx, edx; fCancelPendingCallbacks
0x18001a61c  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001a622  mov     rcx, [rdi+90h]; ptpcg
0x18001a629  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001a62f  mov     rcx, rdi
0x18001a632  add     rsp, 28h
0x18001a636  pop     r14
0x18001a638  pop     rdi
0x18001a639  pop     rsi
0x18001a63a  pop     rbx
0x18001a63b  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
