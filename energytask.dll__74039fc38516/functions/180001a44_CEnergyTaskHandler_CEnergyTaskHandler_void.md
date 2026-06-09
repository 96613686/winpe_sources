# CEnergyTaskHandler::~CEnergyTaskHandler(void)

- ea: `0x180001a44`
- end: `0x180001a6e`
- name: `??1CEnergyTaskHandler@@UEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CEnergyTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180001b20`

## callees

- `0x180001a74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001a5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001a5b`

## pseudocode

```c
void __fastcall CEnergyTaskHandler::~CEnergyTaskHandler(CEnergyTaskHandler *this)
{
  *(_QWORD *)this = &CEnergyTaskHandler::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  CWinTaskHandler::~CWinTaskHandler(this);
}

```

## disassembly

```asm
0x180001a44  push    rbx
0x180001a46  sub     rsp, 20h
0x180001a4a  lea     rax, ??_7CEnergyTaskHandler@@6B@; const CEnergyTaskHandler::`vftable'
0x180001a51  mov     rbx, rcx
0x180001a54  mov     [rcx], rax
0x180001a57  add     rcx, 38h ; '8'; lpCriticalSection
0x180001a5b  call    cs:__imp_DeleteCriticalSection
0x180001a61  mov     rcx, rbx; this
0x180001a64  add     rsp, 20h
0x180001a68  pop     rbx
0x180001a69  jmp     ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
```
