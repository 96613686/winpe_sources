# PROXYPORT::Close(void)

- ea: `0x180095498`
- end: `0x180095503`
- name: `?Close@PROXYPORT@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(PROXYPORT *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180041b00`
- `0x180045d0c`

## callees

- `0x180095498`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800954ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800954be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800954ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800954be`
- `ntdll!RtlFreeHeap` at `0x1800954f0`
- `ntdll!RtlFreeHeap` at `0x1800954f0`
- `ntdll!RtlDeleteCriticalSection` at `0x1800954d8`
- `ntdll!RtlDeleteCriticalSection` at `0x1800954d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800954cb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800954cb`

## pseudocode

```c
void __fastcall PROXYPORT::Close(PVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)*this + 1);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)*this;
  if ( v3 )
    CloseHandle(v3);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)*this + 16));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)*this + 16));
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *this);
  *this = 0;
}

```

## disassembly

```asm
0x180095498  push    rbx
0x18009549a  sub     rsp, 20h
0x18009549e  mov     rax, [rcx]
0x1800954a1  mov     rbx, rcx
0x1800954a4  mov     rcx, [rax+8]; hObject
0x1800954a8  test    rcx, rcx
0x1800954ab  jz      short loc_1800954B3
0x1800954ad  call    cs:__imp_CloseHandle
0x1800954b3  mov     rax, [rbx]
0x1800954b6  mov     rcx, [rax]; hObject
0x1800954b9  test    rcx, rcx
0x1800954bc  jz      short loc_1800954C4
0x1800954be  call    cs:__imp_CloseHandle
0x1800954c4  mov     rcx, [rbx]
0x1800954c7  add     rcx, 10h; CriticalSection
0x1800954cb  call    cs:__imp_RtlLeaveCriticalSection
0x1800954d1  mov     rcx, [rbx]
0x1800954d4  add     rcx, 10h; CriticalSection
0x1800954d8  call    cs:__imp_RtlDeleteCriticalSection
0x1800954de  mov     rcx, gs:60h
0x1800954e7  xor     edx, edx; Flags
0x1800954e9  mov     r8, [rbx]; P
0x1800954ec  mov     rcx, [rcx+30h]; HeapHandle
0x1800954f0  call    cs:__imp_RtlFreeHeap
0x1800954f6  mov     qword ptr [rbx], 0
0x1800954fd  add     rsp, 20h
0x180095501  pop     rbx
0x180095502  retn
```
