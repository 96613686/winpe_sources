# CEnergyTaskHandler::Stop(long *)

- ea: `0x180002b30`
- end: `0x180002b89`
- name: `?Stop@CEnergyTaskHandler@@MEAAJPEAJ@Z`
- size: `89`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002b30`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b62`
- `ENERGY!EnergyWizard_CancelTrace` at `0x180002b58`
- `ENERGY!EnergyWizard_CancelTrace` at `0x180002b58`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::Stop(CEnergyTaskHandler *this, int *a2)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *((_QWORD *)this + 12) )
    EnergyWizard_CancelTrace();
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  return (*(__int64 (__fastcall **)(CEnergyTaskHandler *, int *))(*(_QWORD *)this + 80LL))(this, a2);
}

```

## disassembly

```asm
0x180002b30  mov     [rsp+arg_0], rbx
0x180002b35  mov     [rsp+arg_8], rsi
0x180002b3a  push    rdi
0x180002b3b  sub     rsp, 20h
0x180002b3f  mov     rbx, rcx
0x180002b42  mov     rsi, rdx
0x180002b45  add     rcx, 38h ; '8'; lpCriticalSection
0x180002b49  call    cs:__imp_EnterCriticalSection
0x180002b4f  mov     rcx, [rbx+60h]
0x180002b53  test    rcx, rcx
0x180002b56  jz      short loc_180002B5E
0x180002b58  call    cs:__imp_EnergyWizard_CancelTrace
0x180002b5e  lea     rcx, [rbx+38h]; lpCriticalSection
0x180002b62  call    cs:__imp_LeaveCriticalSection
0x180002b68  mov     rax, [rbx]
0x180002b6b  mov     rdx, rsi
0x180002b6e  mov     rcx, rbx
0x180002b71  mov     rax, [rax+50h]
0x180002b75  mov     rbx, [rsp+28h+arg_0]
0x180002b7a  mov     rsi, [rsp+28h+arg_8]
0x180002b7f  add     rsp, 20h
0x180002b83  pop     rdi
0x180002b84  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
