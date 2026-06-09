# MSCryptUninitializeMemoryLists

- ea: `0x1800129f4`
- end: `0x180012a1e`
- name: `MSCryptUninitializeMemoryLists`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012220`

## callees

- `0x1800129f4`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180012a09`
- `ntdll!RtlDeleteCriticalSection` at `0x180012a09`

## pseudocode

```c
NTSTATUS MSCryptUninitializeMemoryLists()
{
  NTSTATUS result; // eax

  result = dword_18003F1C0;
  if ( dword_18003F1C0 )
  {
    result = RtlDeleteCriticalSection(&CriticalSection);
    dword_18003F1C0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800129f4  sub     rsp, 28h
0x1800129f8  mov     eax, cs:dword_18003F1C0
0x1800129fe  test    eax, eax
0x180012a00  jz      short loc_180012A19
0x180012a02  lea     rcx, CriticalSection; CriticalSection
0x180012a09  call    cs:__imp_RtlDeleteCriticalSection
0x180012a0f  mov     cs:dword_18003F1C0, 0
0x180012a19  add     rsp, 28h
0x180012a1d  retn
```
