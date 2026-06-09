# wil::details::static_lazy<ProfAPITelemetry>::Completer::~Completer(void)

- ea: `0x18000ad68`
- end: `0x18000adbe`
- name: `??1Completer@?$static_lazy@VProfAPITelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000acb4`

## callees

- `0x18000ad68`
- `0x18000adc4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000adb7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ProfAPITelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = ProfileLogging::Provider();
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
0x18000ad68  mov     [rsp+arg_0], rbx
0x18000ad6d  push    rdi
0x18000ad6e  sub     rsp, 20h
0x18000ad72  cmp     dword ptr [rcx+8], 0
0x18000ad76  mov     rdi, rcx
0x18000ad79  jnz     short loc_18000ADA3
0x18000ad7b  mov     rbx, [rcx]
0x18000ad7e  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x18000ad83  mov     [rbx+10h], rax
0x18000ad87  lea     rcx, [rbx+8]
0x18000ad8b  mov     rax, [rbx+8]
0x18000ad8f  mov     byte ptr [rbx+18h], 0
0x18000ad93  mov     dword ptr [rbx+1Ch], 1
0x18000ad9a  mov     rax, [rax+8]
0x18000ad9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada3  mov     rcx, [rdi]
0x18000ada6  mov     edx, [rdi+8]
0x18000ada9  lea     r8, [rcx+8]
0x18000adad  mov     rbx, [rsp+28h+arg_0]
0x18000adb2  add     rsp, 20h
0x18000adb6  pop     rdi
0x18000adb7  jmp     cs:__imp_InitOnceComplete
```
