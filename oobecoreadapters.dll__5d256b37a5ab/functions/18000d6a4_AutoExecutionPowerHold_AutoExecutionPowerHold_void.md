# AutoExecutionPowerHold::~AutoExecutionPowerHold(void)

- ea: `0x18000d6a4`
- end: `0x18000d6f0`
- name: `??1AutoExecutionPowerHold@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(AutoExecutionPowerHold *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010160`
- `0x18006b568`

## callees

- `0x18000d6a4`
- `0x18000e3d0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18000d6c4`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18000d6d3`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18000d6c4`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18000d6d3`
- `api-ms-win-core-kernel32-legacy-l1-1-5!SetThreadExecutionState` at `0x18000d6b2`
- `api-ms-win-core-kernel32-legacy-l1-1-5!SetThreadExecutionState` at `0x18000d6b2`

## pseudocode

```c
void __fastcall AutoExecutionPowerHold::~AutoExecutionPowerHold(AutoExecutionPowerHold *this)
{
  void *v2; // rcx

  SetThreadExecutionState(3u);
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 != (void *)-1LL )
  {
    PowerClearRequest(v2, PowerRequestDisplayRequired);
    PowerClearRequest(*((HANDLE *)this + 1), PowerRequestExecutionRequired);
  }
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::Close(this);
}

```

## disassembly

```asm
0x18000d6a4  push    rbx
0x18000d6a6  sub     rsp, 20h
0x18000d6aa  mov     rbx, rcx
0x18000d6ad  mov     ecx, 3; esFlags
0x18000d6b2  call    cs:__imp_SetThreadExecutionState
0x18000d6b8  mov     rcx, [rbx+8]; PowerRequest
0x18000d6bc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d6c0  jz      short loc_18000D6D9
0x18000d6c2  xor     edx, edx; RequestType
0x18000d6c4  call    cs:__imp_PowerClearRequest
0x18000d6ca  mov     rcx, [rbx+8]; PowerRequest
0x18000d6ce  mov     edx, 3; RequestType
0x18000d6d3  call    cs:__imp_PowerClearRequest
0x18000d6d9  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000d6e0  mov     rcx, rbx
0x18000d6e3  mov     [rbx], rax
0x18000d6e6  add     rsp, 20h
0x18000d6ea  pop     rbx
0x18000d6eb  jmp     ?Close@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::Close(void)
```
