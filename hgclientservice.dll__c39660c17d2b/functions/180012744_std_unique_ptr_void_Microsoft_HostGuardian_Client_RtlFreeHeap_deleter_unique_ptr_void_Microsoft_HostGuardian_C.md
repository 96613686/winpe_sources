# std::unique_ptr<void *,Microsoft::HostGuardian::Client::RtlFreeHeap_deleter>::~unique_ptr<void *,Microsoft::HostGuardian::Client::RtlFreeHeap_deleter>(void)

- ea: `0x180012744`
- end: `0x18001276a`
- name: `??1?$unique_ptr@PEAXURtlFreeHeap_deleter@Client@HostGuardian@Microsoft@@@std@@QEAA@XZ`
- size: `38`
- prototype: `BOOLEAN __fastcall(PVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001666a`

## callees

- `0x180012744`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001275f`
- `ntdll!RtlFreeHeap` at `0x18001275f`

## pseudocode

```c
BOOLEAN __fastcall std::unique_ptr<void *,Microsoft::HostGuardian::Client::RtlFreeHeap_deleter>::~unique_ptr<void *,Microsoft::HostGuardian::Client::RtlFreeHeap_deleter>(
        PVOID *a1)
{
  BOOLEAN result; // al

  if ( *a1 )
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a1);
  return result;
}

```

## disassembly

```asm
0x180012744  sub     rsp, 28h
0x180012748  mov     r8, [rcx]; P
0x18001274b  test    r8, r8
0x18001274e  jz      short loc_180012765
0x180012750  mov     rcx, gs:60h
0x180012759  xor     edx, edx; Flags
0x18001275b  mov     rcx, [rcx+30h]; HeapHandle
0x18001275f  call    cs:__imp_RtlFreeHeap
0x180012765  add     rsp, 28h
0x180012769  retn
```
