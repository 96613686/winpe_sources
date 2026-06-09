# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180010cc8`
- end: `0x180010cfc`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `52`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000faf8`

## callees

- `0x180001dd8`
- `0x180013010`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  __int64 v4; // rax

  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 16) = 1;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(a2);
  v4 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v4 + 8))(this);
}

```

## disassembly

```asm
0x180010cc8  push    rbx
0x180010cca  sub     rsp, 20h
0x180010cce  mov     rbx, rcx
0x180010cd1  mov     [rcx+8], rdx
0x180010cd5  mov     byte ptr [rcx+10h], 1
0x180010cd9  mov     rcx, rdx; CallbackContext
0x180010cdc  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180010ce1  mov     rax, [rbx]
0x180010ce4  mov     rcx, rbx
0x180010ce7  mov     dword ptr [rbx+14h], 1
0x180010cee  mov     rax, [rax+8]
0x180010cf2  add     rsp, 20h
0x180010cf6  pop     rbx
0x180010cf7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
