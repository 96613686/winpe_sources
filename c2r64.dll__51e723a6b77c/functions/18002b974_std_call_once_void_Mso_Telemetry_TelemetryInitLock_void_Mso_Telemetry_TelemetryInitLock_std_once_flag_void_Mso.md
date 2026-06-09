# std::call_once<void (Mso::Telemetry::TelemetryInitLock::*)(void),Mso::Telemetry::TelemetryInitLock *>(std::once_flag &,void (Mso::Telemetry::TelemetryInitLock::*&&)(void),Mso::Telemetry::TelemetryInitLock * &&)

- ea: `0x18002b974`
- end: `0x18002b9f7`
- name: `??$call_once@P8TelemetryInitLock@Telemetry@Mso@@EAAXXZPEAV123@@std@@YAXAEAUonce_flag@0@$$QEAP8TelemetryInitLock@Telemetry@Mso@@EAAXXZ$$QEAPEAV234@@Z`
- size: `131`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005c0e0`
- `0x180063f10`

## callees

- `0x18002b974`
- `0x18003d560`
- `0x180146090`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18002b9d0`
- `KERNEL32!InitOnceComplete` at `0x18002b9d0`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002b99d`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002b99d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002b9ea`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002b9ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall std::call_once<void (Mso::Telemetry::TelemetryInitLock::*)(void),Mso::Telemetry::TelemetryInitLock *>(
        LPINIT_ONCE lpInitOnce,
        void (__fastcall **a2)(_QWORD),
        _QWORD *a3)
{
  BOOL result; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  BOOL v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  result = __std_init_once_begin_initialize(lpInitOnce, 0, &v9, 0);
  if ( !result )
    abort();
  if ( v9 )
  {
    (*a2)(*a3);
    result = InitOnceComplete(lpInitOnce, 0, 0);
    if ( !result )
      _std_init_once_link_alternate_names_and_abort(v8, v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002b974  mov     rax, rsp
0x18002b977  mov     [rax+10h], rbx
0x18002b97b  mov     [rax+18h], rsi
0x18002b97f  push    rdi
0x18002b980  sub     rsp, 30h
0x18002b984  mov     rdi, r8
0x18002b987  mov     rsi, rdx
0x18002b98a  mov     rbx, rcx
0x18002b98d  mov     dword ptr [rax+8], 0
0x18002b994  xor     r9d, r9d; lpContext
0x18002b997  lea     r8, [rax+8]; fPending
0x18002b99b  xor     edx, edx; dwFlags
0x18002b99d  call    cs:__imp___std_init_once_begin_initialize
0x18002b9a3  test    eax, eax
0x18002b9a5  jz      short loc_18002B9EA
0x18002b9a7  cmp     [rsp+38h+arg_0], 0
0x18002b9ac  jz      short loc_18002B9DA
0x18002b9ae  mov     [rsp+38h+var_18], rbx
0x18002b9b3  mov     [rsp+38h+var_10], 4
0x18002b9bc  mov     rcx, [rdi]
0x18002b9bf  mov     rax, [rsi]
0x18002b9c2  call    cs:__guard_dispatch_icall_fptr
0x18002b9c8  xor     r8d, r8d; lpContext
0x18002b9cb  xor     edx, edx; dwFlags
0x18002b9cd  mov     rcx, rbx; lpInitOnce
0x18002b9d0  call    cs:__imp_InitOnceComplete
0x18002b9d6  test    eax, eax
0x18002b9d8  jz      short loc_18002B9F1
0x18002b9da  mov     rbx, [rsp+38h+arg_8]
0x18002b9df  mov     rsi, [rsp+38h+arg_10]
0x18002b9e4  add     rsp, 30h
0x18002b9e8  pop     rdi
0x18002b9e9  retn
0x18002b9ea  call    cs:__imp_abort
0x18002b9f1  call    __std_init_once_link_alternate_names_and_abort
```
