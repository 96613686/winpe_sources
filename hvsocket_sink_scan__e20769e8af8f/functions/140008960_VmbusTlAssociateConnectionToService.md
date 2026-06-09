# VmbusTlAssociateConnectionToService

- ea: `0x140008960`
- end: `0x140008ab1`
- name: `VmbusTlAssociateConnectionToService`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14001e1c0`

## callees

- `0x140008960`
- `0x14000a048`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400089f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008a12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400089f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008a12`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400089ea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008a06`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400089ea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008a06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008971`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000898d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008971`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000898d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008981`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000899d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008981`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000899d`

## string_xrefs

- `0x140008a34`: `VmbusTlAssociateConnectionToService`
- `0x140008a76`: `VmbusTlAssociateConnectionToService`

## pseudocode

```c
__int64 __fastcall VmbusTlAssociateConnectionToService(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdx
  __int64 result; // rax

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  *(_QWORD *)(a2 + 872) = a1;
  v4 = *(_QWORD **)(a1 + 320);
  if ( *v4 != a1 + 312 )
    __fastfail(3u);
  *(_QWORD *)(a2 + 120) = a1 + 312;
  *(_QWORD *)(a2 + 128) = v4;
  *v4 = a2 + 120;
  *(_QWORD *)(a1 + 320) = a2 + 120;
  ++*(_DWORD *)(a1 + 304);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 16));
  KeLeaveCriticalRegion();
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlAssociateConnectionToService",
      236,
      a1,
      *(_QWORD *)(a1 + 8),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
    __fastfail(0xEu);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlAssociateConnectionToService",
      237,
      a2,
      *(_QWORD *)(a2 + 8),
      (__int64)"Reference object");
  result = _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8));
  if ( result <= 1 )
    __fastfail(0xEu);
  return result;
}

```

## disassembly

```asm
0x140008960  push    rbx
0x140008962  push    rbp
0x140008963  push    rsi
0x140008964  push    rdi
0x140008965  push    r14
0x140008967  sub     rsp, 30h
0x14000896b  mov     rdi, rdx
0x14000896e  mov     rbx, rcx
0x140008971  call    cs:__imp_KeEnterCriticalRegion
0x140008978  nop     dword ptr [rax+rax+00h]
0x14000897d  lea     rcx, [rdi+10h]; FastMutex
0x140008981  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008988  nop     dword ptr [rax+rax+00h]
0x14000898d  call    cs:__imp_KeEnterCriticalRegion
0x140008994  nop     dword ptr [rax+rax+00h]
0x140008999  lea     rcx, [rbx+10h]; FastMutex
0x14000899d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400089a4  nop     dword ptr [rax+rax+00h]
0x1400089a9  lea     rcx, [rbx+138h]
0x1400089b0  mov     [rdi+368h], rbx
0x1400089b7  mov     rdx, [rcx+8]
0x1400089bb  cmp     [rdx], rcx
0x1400089be  jz      short loc_1400089C7
0x1400089c0  mov     ecx, 3
0x1400089c5  int     29h; Win8: RtlFailFast(ecx)
0x1400089c7  lea     rax, [rdi+78h]
0x1400089cb  mov     r14d, 1
0x1400089d1  mov     [rax], rcx
0x1400089d4  mov     [rax+8], rdx
0x1400089d8  mov     [rdx], rax
0x1400089db  mov     [rcx+8], rax
0x1400089df  lea     rcx, [rbx+10h]; FastMutex
0x1400089e3  add     [rbx+130h], r14d
0x1400089ea  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400089f1  nop     dword ptr [rax+rax+00h]
0x1400089f6  call    cs:__imp_KeLeaveCriticalRegion
0x1400089fd  nop     dword ptr [rax+rax+00h]
0x140008a02  lea     rcx, [rdi+10h]; FastMutex
0x140008a06  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008a0d  nop     dword ptr [rax+rax+00h]
0x140008a12  call    cs:__imp_KeLeaveCriticalRegion
0x140008a19  nop     dword ptr [rax+rax+00h]
0x140008a1e  mov     eax, cs:dword_140013058
0x140008a24  lea     rsi, aReferenceObjec; "Reference object"
0x140008a2b  cmp     eax, 5
0x140008a2e  jbe     short loc_140008A4D
0x140008a30  mov     r9, [rbx+8]
0x140008a34  lea     rcx, aVmbustlassocia_1; "VmbusTlAssociateConnectionToService"
0x140008a3b  mov     r8, rbx
0x140008a3e  mov     [rsp+58h+var_38], rsi
0x140008a43  mov     edx, 0ECh
0x140008a48  call    HvsocketTraceReferenceCount
0x140008a4d  mov     rax, r14
0x140008a50  lock xadd [rbx+8], rax
0x140008a56  add     rax, r14
0x140008a59  mov     ebx, 0Eh
0x140008a5e  cmp     rax, r14
0x140008a61  jg      short loc_140008A67
0x140008a63  mov     ecx, ebx
0x140008a65  int     29h; Win8: RtlFailFast(ecx)
0x140008a67  mov     eax, cs:dword_140013058
0x140008a6d  cmp     eax, 5
0x140008a70  jbe     short loc_140008A8F
0x140008a72  mov     r9, [rdi+8]
0x140008a76  lea     rcx, aVmbustlassocia_1; "VmbusTlAssociateConnectionToService"
0x140008a7d  mov     r8, rdi
0x140008a80  mov     [rsp+58h+var_38], rsi
0x140008a85  mov     edx, 0EDh
0x140008a8a  call    HvsocketTraceReferenceCount
0x140008a8f  mov     rax, r14
0x140008a92  lock xadd [rdi+8], rax
0x140008a98  add     rax, r14
0x140008a9b  cmp     rax, r14
0x140008a9e  jg      short loc_140008AA5
0x140008aa0  mov     rcx, rbx
0x140008aa3  int     29h; Win8: RtlFailFast(ecx)
0x140008aa5  add     rsp, 30h
0x140008aa9  pop     r14
0x140008aab  pop     rdi
0x140008aac  pop     rsi
0x140008aad  pop     rbp
0x140008aae  pop     rbx
0x140008aaf  retn
```
