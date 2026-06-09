# wil::details::static_lazy<FontSubsettingTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180003abc`
- end: `0x180003b16`
- name: `??1Completer@?$static_lazy@VFontSubsettingTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000714c`

## callees

- `0x180001d90`
- `0x180003abc`
- `0x18001c010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180003b0f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<FontSubsettingTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180003abc  mov     [rsp+arg_0], rbx
0x180003ac1  push    rdi
0x180003ac2  sub     rsp, 20h
0x180003ac6  cmp     dword ptr [rcx+8], 0
0x180003aca  mov     rdi, rcx
0x180003acd  jnz     short loc_180003AFB
0x180003acf  mov     rbx, [rcx]
0x180003ad2  mov     rcx, [rbx+20h]; CallbackContext
0x180003ad6  mov     [rbx+10h], rcx
0x180003ada  mov     byte ptr [rbx+18h], 1
0x180003ade  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180003ae3  mov     rax, [rbx+8]
0x180003ae7  lea     rcx, [rbx+8]
0x180003aeb  mov     dword ptr [rbx+1Ch], 1
0x180003af2  mov     rax, [rax+8]
0x180003af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afb  mov     rcx, [rdi]
0x180003afe  mov     edx, [rdi+8]
0x180003b01  lea     r8, [rcx+8]
0x180003b05  mov     rbx, [rsp+28h+arg_0]
0x180003b0a  add     rsp, 20h
0x180003b0e  pop     rdi
0x180003b0f  jmp     cs:__imp_InitOnceComplete
```
