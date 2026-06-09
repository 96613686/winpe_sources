# wil::details::static_lazy<CleanupMgrTelemetry>::Completer::~Completer(void)

- ea: `0x14000f8a8`
- end: `0x14000f8fe`
- name: `??1Completer@?$static_lazy@VCleanupMgrTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400128bc`

## callees

- `0x14000e15c`
- `0x14000f8a8`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000f8f7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CleanupMgrTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = g_hProvider::Provider();
    v3.Ptr = v2[1].Ptr;
    LOBYTE(v2[3].Ptr) = 0;
    HIDWORD(v2[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v3.Ptr + 1))(v2 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x14000f8a8  mov     [rsp+arg_0], rbx
0x14000f8ad  push    rdi
0x14000f8ae  sub     rsp, 20h
0x14000f8b2  cmp     dword ptr [rcx+8], 0
0x14000f8b6  mov     rdi, rcx
0x14000f8b9  jnz     short loc_14000F8E3
0x14000f8bb  mov     rbx, [rcx]
0x14000f8be  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x14000f8c3  mov     [rbx+10h], rax
0x14000f8c7  lea     rcx, [rbx+8]
0x14000f8cb  mov     rax, [rbx+8]
0x14000f8cf  mov     byte ptr [rbx+18h], 0
0x14000f8d3  mov     dword ptr [rbx+1Ch], 1
0x14000f8da  mov     rax, [rax+8]
0x14000f8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8e3  mov     rcx, [rdi]
0x14000f8e6  mov     edx, [rdi+8]
0x14000f8e9  lea     r8, [rcx+8]
0x14000f8ed  mov     rbx, [rsp+28h+arg_0]
0x14000f8f2  add     rsp, 20h
0x14000f8f6  pop     rdi
0x14000f8f7  jmp     cs:__imp_InitOnceComplete
```
