# SystemError::Throw<ulong>(wchar_t const *,ulong)

- ea: `0x18000d4c8`
- end: `0x18000d4e2`
- name: `??$Throw@K@SystemError@@SAXPEB_WK@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e2bc`

## callees

- `0x18000a4d0`
- `0x18000dc54`

## string_xrefs

- `0x18000d4d5`: `SetServiceStatus`

## pseudocode

```c
void __fastcall __noreturn SystemError::Throw<unsigned long>(__int64 a1, int a2)
{
  int v2; // eax

  v2 = Exception::ComErrorFromWin32<unsigned long>(a2);
  SystemError::ThrowHelper(L"SetServiceStatus", v2);
}

```

## disassembly

```asm
0x18000d4c8  sub     rsp, 28h
0x18000d4cc  mov     ecx, edx
0x18000d4ce  call    ??$ComErrorFromWin32@K@Exception@@SAJK@Z; Exception::ComErrorFromWin32<ulong>(ulong)
0x18000d4d3  mov     edx, eax; int
0x18000d4d5  lea     rcx, aSetservicestat_0; "SetServiceStatus"
0x18000d4dc  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
```
