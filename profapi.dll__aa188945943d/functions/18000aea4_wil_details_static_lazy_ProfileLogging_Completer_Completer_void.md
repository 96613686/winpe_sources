# wil::details::static_lazy<ProfileLogging>::Completer::~Completer(void)

- ea: `0x18000aea4`
- end: `0x18000aefe`
- name: `??1Completer@?$static_lazy@VProfileLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ade4`

## callees

- `0x18000aea4`
- `0x18000af04`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000aef7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ProfileLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18000aea4  mov     [rsp+arg_0], rbx
0x18000aea9  push    rdi
0x18000aeaa  sub     rsp, 20h
0x18000aeae  cmp     dword ptr [rcx+8], 0
0x18000aeb2  mov     rdi, rcx
0x18000aeb5  jnz     short loc_18000AEE3
0x18000aeb7  mov     rbx, [rcx]
0x18000aeba  mov     rcx, [rbx+20h]; CallbackContext
0x18000aebe  mov     [rbx+10h], rcx
0x18000aec2  mov     byte ptr [rbx+18h], 1
0x18000aec6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000aecb  mov     rax, [rbx+8]
0x18000aecf  lea     rcx, [rbx+8]
0x18000aed3  mov     dword ptr [rbx+1Ch], 1
0x18000aeda  mov     rax, [rax+8]
0x18000aede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee3  mov     rcx, [rdi]
0x18000aee6  mov     edx, [rdi+8]
0x18000aee9  lea     r8, [rcx+8]
0x18000aeed  mov     rbx, [rsp+28h+arg_0]
0x18000aef2  add     rsp, 20h
0x18000aef6  pop     rdi
0x18000aef7  jmp     cs:__imp_InitOnceComplete
```
