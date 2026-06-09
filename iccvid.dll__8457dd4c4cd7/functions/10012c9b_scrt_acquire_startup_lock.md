# ___scrt_acquire_startup_lock

- ea: `0x10012c9b`
- end: `0x10012ccf`
- name: `___scrt_acquire_startup_lock`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1001280b`
- `0x1001291b`

## callees

- `0x10012c9b`
- `0x100133f1`

## pseudocode

```c
char __scrt_acquire_startup_lock()
{
  PVOID StackBase; // edx
  signed __int32 v1; // eax

  if ( __scrt_is_ucrt_dll_in_use() )
  {
    StackBase = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v1 = _InterlockedCompareExchange(&__scrt_native_startup_lock, (signed __int32)StackBase, 0);
      if ( !v1 )
        break;
      if ( StackBase == (PVOID)v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10012c9b  mov     edi, edi
0x10012c9d  push    esi
0x10012c9e  call    ___scrt_is_ucrt_dll_in_use
0x10012ca3  test    eax, eax
0x10012ca5  jz      short loc_10012CC7
0x10012ca7  mov     eax, large fs:18h
0x10012cad  mov     esi, offset ___scrt_native_startup_lock
0x10012cb2  mov     edx, [eax+4]
0x10012cb5  jmp     short loc_10012CBB
0x10012cb7  cmp     edx, eax
0x10012cb9  jz      short loc_10012CCB
0x10012cbb  xor     eax, eax
0x10012cbd  mov     ecx, edx
0x10012cbf  lock cmpxchg [esi], ecx
0x10012cc3  test    eax, eax
0x10012cc5  jnz     short loc_10012CB7
0x10012cc7  xor     al, al
0x10012cc9  pop     esi
0x10012cca  retn
0x10012ccb  mov     al, 1
0x10012ccd  pop     esi
0x10012cce  retn
```
