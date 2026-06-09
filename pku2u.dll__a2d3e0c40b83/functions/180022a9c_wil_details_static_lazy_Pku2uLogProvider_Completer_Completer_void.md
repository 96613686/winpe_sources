# wil::details::static_lazy<Pku2uLogProvider>::Completer::~Completer(void)

- ea: `0x180022a9c`
- end: `0x180022af6`
- name: `??1Completer@?$static_lazy@VPku2uLogProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014d60`
- `0x180017af0`

## callees

- `0x18001b080`
- `0x180022a9c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022aef`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<Pku2uLogProvider>::Completer::~Completer(_DWORD *a1)
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
0x180022a9c  mov     [rsp+arg_0], rbx
0x180022aa1  push    rdi
0x180022aa2  sub     rsp, 20h
0x180022aa6  cmp     dword ptr [rcx+8], 0
0x180022aaa  mov     rdi, rcx
0x180022aad  jnz     short loc_180022ADB
0x180022aaf  mov     rbx, [rcx]
0x180022ab2  mov     rcx, [rbx+20h]; CallbackContext
0x180022ab6  mov     [rbx+10h], rcx
0x180022aba  mov     byte ptr [rbx+18h], 1
0x180022abe  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180022ac3  mov     rax, [rbx+8]
0x180022ac7  lea     rcx, [rbx+8]
0x180022acb  mov     dword ptr [rbx+1Ch], 1
0x180022ad2  mov     rax, [rax+8]
0x180022ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022adb  mov     rcx, [rdi]
0x180022ade  mov     edx, [rdi+8]
0x180022ae1  lea     r8, [rcx+8]
0x180022ae5  mov     rbx, [rsp+28h+arg_0]
0x180022aea  add     rsp, 20h
0x180022aee  pop     rdi
0x180022aef  jmp     cs:__imp_InitOnceComplete
```
