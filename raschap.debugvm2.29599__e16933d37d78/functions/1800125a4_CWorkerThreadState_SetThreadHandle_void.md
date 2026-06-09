# CWorkerThreadState::SetThreadHandle(void *)

- ea: `0x1800125a4`
- end: `0x1800125e3`
- name: `?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z`
- size: `63`
- prototype: `void __fastcall(CWorkerThreadState *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006c60`

## callees

- `0x18000e020`
- `0x1800125a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125b4`

## pseudocode

```c
void __fastcall CWorkerThreadState::SetThreadHandle(CWorkerThreadState *this, void *a2)
{
  CWorkerThreadState *v3; // rcx

  EnterCriticalSection(&g_EapCredThreadState);
  if ( hObject )
    CWorkerThreadState::WaitForThread(v3);
  hObject = a2;
  LeaveCriticalSection(&g_EapCredThreadState);
}

```

## disassembly

```asm
0x1800125a4  push    rbx
0x1800125a6  sub     rsp, 20h
0x1800125aa  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; lpCriticalSection
0x1800125b1  mov     rbx, rdx
0x1800125b4  call    cs:__imp_EnterCriticalSection
0x1800125ba  cmp     cs:hObject, 0
0x1800125c2  jz      short loc_1800125C9
0x1800125c4  call    ?WaitForThread@CWorkerThreadState@@QEAAKXZ; CWorkerThreadState::WaitForThread(void)
0x1800125c9  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; CWorkerThreadState g_EapCredThreadState
0x1800125d0  mov     cs:hObject, rbx
0x1800125d7  add     rsp, 20h
0x1800125db  pop     rbx
0x1800125dc  jmp     cs:__imp_LeaveCriticalSection
```
