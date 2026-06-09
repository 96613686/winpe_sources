# SQLRemoveDriverManager

- ea: `0x180009b80`
- end: `0x180009bbe`
- name: `SQLRemoveDriverManager`
- size: `62`
- prototype: `BOOL __stdcall(LPDWORD lpdwUsageCount)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180001740`
- `0x180009b80`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009bad`
- `KERNEL32!LeaveCriticalSection` at `0x180009bad`
- `KERNEL32!EnterCriticalSection` at `0x180009b90`
- `KERNEL32!EnterCriticalSection` at `0x180009b90`

## pseudocode

```c
BOOL __stdcall SQLRemoveDriverManager(LPDWORD lpdwUsageCount)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  if ( lpdwUsageCount )
    *lpdwUsageCount = 1;
  LeaveCriticalSection(&g_csInstaller);
  return 1;
}

```

## disassembly

```asm
0x180009b80  push    rbx
0x180009b82  sub     rsp, 20h
0x180009b86  mov     rbx, rcx
0x180009b89  lea     rcx, g_csInstaller; lpCriticalSection
0x180009b90  call    cs:__imp_EnterCriticalSection
0x180009b96  call    FreeErrorQueue
0x180009b9b  test    rbx, rbx
0x180009b9e  jz      short loc_180009BA6
0x180009ba0  mov     dword ptr [rbx], 1
0x180009ba6  lea     rcx, g_csInstaller; lpCriticalSection
0x180009bad  call    cs:__imp_LeaveCriticalSection
0x180009bb3  mov     eax, 1
0x180009bb8  add     rsp, 20h
0x180009bbc  pop     rbx
0x180009bbd  retn
```
