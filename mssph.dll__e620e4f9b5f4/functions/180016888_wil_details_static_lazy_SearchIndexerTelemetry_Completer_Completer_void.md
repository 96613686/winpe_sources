# wil::details::static_lazy<SearchIndexerTelemetry>::Completer::~Completer(void)

- ea: `0x180016888`
- end: `0x1800168de`
- name: `??1Completer@?$static_lazy@VSearchIndexerTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c458`

## callees

- `0x180016888`
- `0x18001a0f4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800168d7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SearchIndexerTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = SearchIndexerLogging::Provider();
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
0x180016888  mov     [rsp+arg_0], rbx
0x18001688d  push    rdi
0x18001688e  sub     rsp, 20h
0x180016892  cmp     dword ptr [rcx+8], 0
0x180016896  mov     rdi, rcx
0x180016899  jnz     short loc_1800168C3
0x18001689b  mov     rbx, [rcx]
0x18001689e  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x1800168a3  mov     [rbx+10h], rax
0x1800168a7  lea     rcx, [rbx+8]
0x1800168ab  mov     rax, [rbx+8]
0x1800168af  mov     byte ptr [rbx+18h], 0
0x1800168b3  mov     dword ptr [rbx+1Ch], 1
0x1800168ba  mov     rax, [rax+8]
0x1800168be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c3  mov     rcx, [rdi]
0x1800168c6  mov     edx, [rdi+8]
0x1800168c9  lea     r8, [rcx+8]
0x1800168cd  mov     rbx, [rsp+28h+arg_0]
0x1800168d2  add     rsp, 20h
0x1800168d6  pop     rdi
0x1800168d7  jmp     cs:__imp_InitOnceComplete
```
