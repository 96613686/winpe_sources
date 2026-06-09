# std::unique_ptr<ListenerRegistration,std::default_delete<ListenerRegistration>>::~unique_ptr<ListenerRegistration,std::default_delete<ListenerRegistration>>(void)

- ea: `0x180013ce4`
- end: `0x180013d12`
- name: `??1?$unique_ptr@VListenerRegistration@@U?$default_delete@VListenerRegistration@@@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001dc14`

## callees

- `0x1800014d0`
- `0x180013ce4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013cfe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013cfe`

## pseudocode

```c
void __fastcall std::unique_ptr<ListenerRegistration>::~unique_ptr<ListenerRegistration>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    operator delete(v1[1].LockSemaphore);
    DeleteCriticalSection(v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180013ce4  push    rbx
0x180013ce6  sub     rsp, 20h
0x180013cea  mov     rbx, [rcx]
0x180013ced  test    rbx, rbx
0x180013cf0  jz      short loc_180013D0C
0x180013cf2  mov     rcx, [rbx+40h]; Block
0x180013cf6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013cfb  mov     rcx, rbx; lpCriticalSection
0x180013cfe  call    cs:__imp_DeleteCriticalSection
0x180013d04  mov     rcx, rbx; Block
0x180013d07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013d0c  add     rsp, 20h
0x180013d10  pop     rbx
0x180013d11  retn
```
