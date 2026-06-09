# wil::details::static_lazy<g_hProvider>::Completer::~Completer(void)

- ea: `0x14000b8fc`
- end: `0x14000b956`
- name: `??1Completer@?$static_lazy@Vg_hProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ed4c`

## callees

- `0x140001864`
- `0x14000b8fc`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000b94f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<g_hProvider>::Completer::~Completer(_DWORD *a1)
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
0x14000b8fc  mov     [rsp+arg_0], rbx
0x14000b901  push    rdi
0x14000b902  sub     rsp, 20h
0x14000b906  cmp     dword ptr [rcx+8], 0
0x14000b90a  mov     rdi, rcx
0x14000b90d  jnz     short loc_14000B93B
0x14000b90f  mov     rbx, [rcx]
0x14000b912  mov     rcx, [rbx+20h]; CallbackContext
0x14000b916  mov     [rbx+10h], rcx
0x14000b91a  mov     byte ptr [rbx+18h], 1
0x14000b91e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000b923  mov     rax, [rbx+8]
0x14000b927  lea     rcx, [rbx+8]
0x14000b92b  mov     dword ptr [rbx+1Ch], 1
0x14000b932  mov     rax, [rax+8]
0x14000b936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b93b  mov     rcx, [rdi]
0x14000b93e  mov     edx, [rdi+8]
0x14000b941  lea     r8, [rcx+8]
0x14000b945  mov     rbx, [rsp+28h+arg_0]
0x14000b94a  add     rsp, 20h
0x14000b94e  pop     rdi
0x14000b94f  jmp     cs:__imp_InitOnceComplete
```
