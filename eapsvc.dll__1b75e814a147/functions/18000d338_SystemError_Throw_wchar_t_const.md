# SystemError::Throw(wchar_t const *)

- ea: `0x18000d338`
- end: `0x18000d359`
- name: `?Throw@SystemError@@SAXPEB_W@Z`
- size: `33`
- prototype: `void __fastcall __noreturn(const wchar_t *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a5cc`
- `0x18000b4e0`
- `0x18000c2a0`
- `0x18000d4e8`
- `0x18000dfb0`
- `0x18000e21c`
- `0x18000e2bc`
- `0x18000e588`
- `0x18000f57c`
- `0x18001064c`
- `0x180013ba0`
- `0x1800142dc`

## callees

- `0x18000a4d0`
- `0x18000dc54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d341`

## pseudocode

```c
void __fastcall __noreturn SystemError::Throw(const wchar_t *a1)
{
  DWORD LastError; // eax
  int v3; // eax

  LastError = GetLastError();
  v3 = Exception::ComErrorFromWin32<unsigned long>(LastError);
  SystemError::ThrowHelper(a1, v3);
}

```

## disassembly

```asm
0x18000d338  push    rbx
0x18000d33a  sub     rsp, 20h
0x18000d33e  mov     rbx, rcx
0x18000d341  call    cs:__imp_GetLastError
0x18000d347  mov     ecx, eax
0x18000d349  call    ??$ComErrorFromWin32@K@Exception@@SAJK@Z; Exception::ComErrorFromWin32<ulong>(ulong)
0x18000d34e  mov     edx, eax; int
0x18000d350  mov     rcx, rbx; wchar_t *
0x18000d353  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
```
