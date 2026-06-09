# CVolumeTrackingDescriptor::`scalar deleting destructor'(uint)

- ea: `0x180008680`
- end: `0x1800086d7`
- name: `??_GCVolumeTrackingDescriptor@@QEAAPEAXI@Z`
- size: `87`
- prototype: `CVolumeTrackingDescriptor *__fastcall(CVolumeTrackingDescriptor *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008640`
- `0x180011f2c`

## callees

- `0x180008680`
- `0x180013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800086c8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800086c8`
- `USER32!UnregisterDeviceNotification` at `0x180008692`
- `USER32!UnregisterDeviceNotification` at `0x180008692`

## pseudocode

```c
CVolumeTrackingDescriptor *__fastcall CVolumeTrackingDescriptor::`scalar deleting destructor'(
        CVolumeTrackingDescriptor *this)
{
  void *v2; // rcx
  volatile signed __int32 *v3; // rdx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    UnregisterDeviceNotification(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (volatile signed __int32 *)(*(_QWORD *)this - 24LL);
  if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008680  push    rbx
0x180008682  sub     rsp, 20h
0x180008686  mov     rbx, rcx
0x180008689  mov     rcx, [rcx+8]; Handle
0x18000868d  test    rcx, rcx
0x180008690  jz      short loc_1800086A0
0x180008692  call    cs:__imp_UnregisterDeviceNotification
0x180008698  mov     qword ptr [rbx+8], 0
0x1800086a0  mov     rdx, [rbx]
0x1800086a3  mov     eax, 0FFFFFFFFh
0x1800086a8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800086ac  lock xadd [rdx+10h], eax
0x1800086b1  sub     eax, 1
0x1800086b4  jg      short loc_1800086C5
0x1800086b6  mov     rcx, [rdx]
0x1800086b9  mov     rax, [rcx]
0x1800086bc  mov     rax, [rax+8]
0x1800086c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086c5  mov     rcx, rbx
0x1800086c8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800086ce  mov     rax, rbx
0x1800086d1  add     rsp, 20h
0x1800086d5  pop     rbx
0x1800086d6  retn
```
