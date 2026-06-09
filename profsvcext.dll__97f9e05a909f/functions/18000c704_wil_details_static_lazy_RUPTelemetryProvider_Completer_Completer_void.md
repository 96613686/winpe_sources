# wil::details::static_lazy<RUPTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18000c704`
- end: `0x18000c75e`
- name: `??1Completer@?$static_lazy@VRUPTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800046d0`
- `0x180004780`

## callees

- `0x180004a50`
- `0x18000c704`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c757`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<RUPTelemetryProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    *(_QWORD *)(v2 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    v3 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v3 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18000c704  mov     [rsp+arg_0], rbx
0x18000c709  push    rdi
0x18000c70a  sub     rsp, 20h
0x18000c70e  cmp     dword ptr [rcx+8], 0
0x18000c712  mov     rdi, rcx
0x18000c715  jnz     short loc_18000C743
0x18000c717  mov     rbx, [rcx]
0x18000c71a  mov     rcx, [rbx+20h]
0x18000c71e  mov     [rbx+10h], rcx
0x18000c722  mov     byte ptr [rbx+18h], 1
0x18000c726  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x18000c72b  mov     rax, [rbx+8]
0x18000c72f  lea     rcx, [rbx+8]
0x18000c733  mov     dword ptr [rbx+1Ch], 1
0x18000c73a  mov     rax, [rax+8]
0x18000c73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c743  mov     rcx, [rdi]
0x18000c746  mov     edx, [rdi+8]
0x18000c749  lea     r8, [rcx+8]
0x18000c74d  mov     rbx, [rsp+28h+arg_0]
0x18000c752  add     rsp, 20h
0x18000c756  pop     rdi
0x18000c757  jmp     cs:__imp_InitOnceComplete
```
