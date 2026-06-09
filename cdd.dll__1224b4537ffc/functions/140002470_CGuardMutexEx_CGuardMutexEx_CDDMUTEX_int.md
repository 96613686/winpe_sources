# CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)

- ea: `0x140002470`
- end: `0x1400024a3`
- name: `??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z`
- size: `51`
- prototype: `CGuardMutexEx *__fastcall(CGuardMutexEx *__hidden this, struct CDDMUTEX *, int)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001230`
- `0x140002504`
- `0x140003840`
- `0x140004904`
- `0x140005cc0`
- `0x140007b00`
- `0x14000919c`
- `0x14000a254`
- `0x14001f270`
- `0x1400200e8`
- `0x1400226b0`
- `0x140027c80`
- `0x140028a40`
- `0x140029254`
- `0x14002b5f0`
- `0x14002e61c`
- `0x14002fbd4`
- `0x140030070`
- `0x14003128c`
- `0x140032000`
- `0x140033134`
- `0x1400332b0`
- `0x14003461c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140002486`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140002486`

## pseudocode

```c
CGuardMutexEx *__fastcall CGuardMutexEx::CGuardMutexEx(CGuardMutexEx *this, struct CDDMUTEX *a2)
{
  CGuardMutexEx *result; // rax

  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = 0;
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(a2);
  result = this;
  *((_DWORD *)this + 2) = 1;
  return result;
}

```

## disassembly

```asm
0x140002470  push    rbx
0x140002472  sub     rsp, 20h
0x140002476  mov     rbx, rcx
0x140002479  mov     [rcx], rdx
0x14000247c  mov     dword ptr [rcx+8], 0
0x140002483  mov     rcx, rdx
0x140002486  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000248d  nop     dword ptr [rax+rax+00h]
0x140002492  mov     rax, rbx
0x140002495  mov     dword ptr [rbx+8], 1
0x14000249c  add     rsp, 20h
0x1400024a0  pop     rbx
0x1400024a1  retn
```
