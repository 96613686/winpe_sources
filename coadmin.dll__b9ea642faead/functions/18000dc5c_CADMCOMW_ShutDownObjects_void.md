# CADMCOMW::ShutDownObjects(void)

- ea: `0x18000dc5c`
- end: `0x18000dd43`
- name: `?ShutDownObjects@CADMCOMW@@SAXXZ`
- size: `231`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a0b0`
- `0x18000a6c0`

## callees

- `0x18000455c`
- `0x180008614`
- `0x180009920`
- `0x18000dba8`
- `0x18000dc5c`
- `0x180010010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000dc8a`
- `KERNEL32!LeaveCriticalSection` at `0x18000dce0`
- `KERNEL32!LeaveCriticalSection` at `0x18000dc8a`
- `KERNEL32!LeaveCriticalSection` at `0x18000dce0`
- `KERNEL32!EnterCriticalSection` at `0x18000dc72`
- `KERNEL32!EnterCriticalSection` at `0x18000dc9c`
- `KERNEL32!EnterCriticalSection` at `0x18000dc72`
- `KERNEL32!EnterCriticalSection` at `0x18000dc9c`
- `KERNEL32!SleepEx` at `0x18000dd06`
- `KERNEL32!SleepEx` at `0x18000dd06`

## pseudocode

```c
void CADMCOMW::ShutDownObjects(void)
{
  struct _LIST_ENTRY *v0; // rbx
  int i; // edi

  EnterCriticalSection(&CADMCOMW::sm_csObjectListLock);
  CADMCOMW::sm_fShutdownInProgress = 1;
  LeaveCriticalSection(&CADMCOMW::sm_csObjectListLock);
  NOTIFY_CONTEXT::RemoveAllWork();
  while ( 1 )
  {
    EnterCriticalSection(&CADMCOMW::sm_csObjectListLock);
    if ( CADMCOMW::sm_ObjectList.Flink == &CADMCOMW::sm_ObjectList )
    {
      v0 = 0;
    }
    else
    {
      v0 = CADMCOMW::sm_ObjectList.Flink - 9;
      ((void (__fastcall *)(struct _LIST_ENTRY *))CADMCOMW::sm_ObjectList.Flink[-9].Flink->Blink)(&CADMCOMW::sm_ObjectList.Flink[-9]);
      CADMCOMW::RemoveObjectFromList((CADMCOMW *)v0, 1);
    }
    LeaveCriticalSection(&CADMCOMW::sm_csObjectListLock);
    if ( !v0 )
      break;
    CADMCOMW::DisconnectOrphaned((CADMCOMW *)v0, 1);
    for ( i = 0; LODWORD(v0->Blink) > 1 && i < 5; ++i )
      SleepEx(200 * i, 1);
    CADMCOMW::Terminate((CADMCOMW *)v0, 1);
    ((void (__fastcall *)(struct _LIST_ENTRY *))v0->Flink[1].Flink)(v0);
  }
}

```

## disassembly

```asm
0x18000dc5c  mov     [rsp+arg_0], rbx
0x18000dc61  mov     [rsp+arg_8], rsi
0x18000dc66  push    rdi
0x18000dc67  sub     rsp, 20h
0x18000dc6b  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dc72  call    cs:__imp_EnterCriticalSection
0x18000dc78  mov     esi, 1
0x18000dc7d  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dc84  mov     cs:?sm_fShutdownInProgress@CADMCOMW@@2HA, esi; int CADMCOMW::sm_fShutdownInProgress
0x18000dc8a  call    cs:__imp_LeaveCriticalSection
0x18000dc90  call    ?RemoveAllWork@NOTIFY_CONTEXT@@SAXXZ; NOTIFY_CONTEXT::RemoveAllWork(void)
0x18000dc95  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dc9c  call    cs:__imp_EnterCriticalSection
0x18000dca2  mov     rbx, qword ptr cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000dca9  lea     rax, ?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000dcb0  cmp     rbx, rax
0x18000dcb3  jnz     short loc_18000DCB9
0x18000dcb5  xor     ebx, ebx
0x18000dcb7  jmp     short loc_18000DCD9
0x18000dcb9  add     rbx, 0FFFFFFFFFFFFFF70h
0x18000dcc0  mov     rcx, rbx
0x18000dcc3  mov     rax, [rbx]
0x18000dcc6  mov     rax, [rax+8]
0x18000dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dccf  mov     edx, esi; int
0x18000dcd1  mov     rcx, rbx; this
0x18000dcd4  call    ?RemoveObjectFromList@CADMCOMW@@AEAAHH@Z; CADMCOMW::RemoveObjectFromList(int)
0x18000dcd9  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dce0  call    cs:__imp_LeaveCriticalSection
0x18000dce6  test    rbx, rbx
0x18000dce9  jz      short loc_18000DD33
0x18000dceb  mov     edx, esi; int
0x18000dced  mov     rcx, rbx; this
0x18000dcf0  call    ?DisconnectOrphaned@CADMCOMW@@AEAAJH@Z; CADMCOMW::DisconnectOrphaned(int)
0x18000dcf5  xor     edi, edi
0x18000dcf7  jmp     short loc_18000DD0E
0x18000dcf9  cmp     edi, 5
0x18000dcfc  jge     short loc_18000DD15
0x18000dcfe  imul    ecx, edi, 0C8h; dwMilliseconds
0x18000dd04  mov     edx, esi; bAlertable
0x18000dd06  call    cs:__imp_SleepEx
0x18000dd0c  add     edi, esi
0x18000dd0e  mov     eax, [rbx+8]
0x18000dd11  cmp     eax, esi
0x18000dd13  ja      short loc_18000DCF9
0x18000dd15  mov     edx, esi; int
0x18000dd17  mov     rcx, rbx; this
0x18000dd1a  call    ?Terminate@CADMCOMW@@AEAAXH@Z; CADMCOMW::Terminate(int)
0x18000dd1f  mov     rax, [rbx]
0x18000dd22  mov     rcx, rbx
0x18000dd25  mov     rax, [rax+10h]
0x18000dd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd2e  jmp     loc_18000DC95
0x18000dd33  mov     rbx, [rsp+28h+arg_0]
0x18000dd38  mov     rsi, [rsp+28h+arg_8]
0x18000dd3d  add     rsp, 20h
0x18000dd41  pop     rdi
0x18000dd42  retn
```
