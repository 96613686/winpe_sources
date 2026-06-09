# SystemError::Throw<long>(wchar_t const *,long)

- ea: `0x18000a5ac`
- end: `0x18000a5c5`
- name: `??$Throw@J@SystemError@@SAXPEB_WJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(__int64, int)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a5cc`
- `0x18000cd98`
- `0x18000ce54`
- `0x18000cf50`
- `0x18000d0f8`
- `0x18000d5cc`
- `0x18000f77c`
- `0x18001064c`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180013578`
- `0x1800142dc`
- `0x1800148c4`
- `0x180015569`

## callees

- `0x18000a4d0`
- `0x18000dc54`

## pseudocode

```c
void __fastcall __noreturn SystemError::Throw<long>(__int64 a1, int a2)
{
  int v2; // eax
  const wchar_t *v3; // r8

  v2 = Exception::ComErrorFromWin32<unsigned long>(a2);
  SystemError::ThrowHelper(v3, v2);
}

```

## disassembly

```asm
0x18000a5ac  sub     rsp, 28h
0x18000a5b0  mov     r8, rcx
0x18000a5b3  mov     ecx, edx
0x18000a5b5  call    ??$ComErrorFromWin32@K@Exception@@SAJK@Z; Exception::ComErrorFromWin32<ulong>(ulong)
0x18000a5ba  mov     edx, eax; int
0x18000a5bc  mov     rcx, r8; wchar_t *
0x18000a5bf  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
```
