# MakeCaptureToken(void)

- ea: `0x18000a72c`
- end: `0x18000a757`
- name: `?MakeCaptureToken@@YA?AT_LARGE_INTEGER@@XZ`
- size: `43`
- prototype: `union _LARGE_INTEGER(void)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180012b20`
- `0x180012bd0`
- `0x180012c80`
- `0x180012d30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a730`

## pseudocode

```c
union _LARGE_INTEGER MakeCaptureToken(void)
{
  DWORD CurrentProcessId; // eax

  CurrentProcessId = GetCurrentProcessId();
  return (union _LARGE_INTEGER)__PAIR64__(CurrentProcessId, _InterlockedIncrement(&dword_18001F85C));
}

```

## disassembly

```asm
0x18000a72c  sub     rsp, 28h
0x18000a730  call    cs:__imp_GetCurrentProcessId
0x18000a736  mov     dword ptr [rsp+28h+arg_0+4], eax
0x18000a73a  mov     eax, 1
0x18000a73f  lock xadd cs:dword_18001F85C, eax
0x18000a747  inc     eax
0x18000a749  mov     dword ptr [rsp+28h+arg_0], eax
0x18000a74d  mov     rax, [rsp+28h+arg_0]
0x18000a752  add     rsp, 28h
0x18000a756  retn
```
