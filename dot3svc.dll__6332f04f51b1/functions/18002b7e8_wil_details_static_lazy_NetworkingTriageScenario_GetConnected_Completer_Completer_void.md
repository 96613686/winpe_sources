# wil::details::static_lazy<NetworkingTriageScenario::GetConnected>::Completer::~Completer(void)

- ea: `0x18002b7e8`
- end: `0x18002b842`
- name: `??1Completer@?$static_lazy@VGetConnected@NetworkingTriageScenario@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002fd10`

## callees

- `0x180001978`
- `0x18002b7e8`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b83b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NetworkingTriageScenario::GetConnected>::Completer::~Completer(_DWORD *a1)
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
0x18002b7e8  mov     [rsp+arg_0], rbx
0x18002b7ed  push    rdi
0x18002b7ee  sub     rsp, 20h
0x18002b7f2  cmp     dword ptr [rcx+8], 0
0x18002b7f6  mov     rdi, rcx
0x18002b7f9  jnz     short loc_18002B827
0x18002b7fb  mov     rbx, [rcx]
0x18002b7fe  mov     rcx, [rbx+20h]
0x18002b802  mov     [rbx+10h], rcx
0x18002b806  mov     byte ptr [rbx+18h], 1
0x18002b80a  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x18002b80f  mov     rax, [rbx+8]
0x18002b813  lea     rcx, [rbx+8]
0x18002b817  mov     dword ptr [rbx+1Ch], 1
0x18002b81e  mov     rax, [rax+8]
0x18002b822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b827  mov     rcx, [rdi]
0x18002b82a  mov     edx, [rdi+8]
0x18002b82d  lea     r8, [rcx+8]
0x18002b831  mov     rbx, [rsp+28h+arg_0]
0x18002b836  add     rsp, 20h
0x18002b83a  pop     rdi
0x18002b83b  jmp     cs:__imp_InitOnceComplete
```
