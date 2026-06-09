# EapLm::Peer::ThirdPartyDispatcherRuntime::GetProcessId(ulong *)

- ea: `0x180007da0`
- end: `0x180007dce`
- name: `?GetProcessId@ThirdPartyDispatcherRuntime@Peer@EapLm@@UEAAJPEAK@Z`
- size: `46`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherRuntime *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180007da0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180007dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180007dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007db5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007db5`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherRuntime::GetProcessId(
        EapLm::Peer::ThirdPartyDispatcherRuntime *this,
        unsigned int *a2)
{
  HANDLE CurrentProcess; // rax

  if ( !a2 )
    return 2147500035LL;
  CurrentProcess = GetCurrentProcess();
  *a2 = GetProcessId(CurrentProcess);
  return 0;
}

```

## disassembly

```asm
0x180007da0  push    rbx
0x180007da2  sub     rsp, 20h
0x180007da6  mov     rbx, rdx
0x180007da9  test    rdx, rdx
0x180007dac  jnz     short loc_180007DB5
0x180007dae  mov     eax, 80004003h
0x180007db3  jmp     short loc_180007DC8
0x180007db5  call    cs:__imp_GetCurrentProcess
0x180007dbb  mov     rcx, rax; Process
0x180007dbe  call    cs:__imp_GetProcessId
0x180007dc4  mov     [rbx], eax
0x180007dc6  xor     eax, eax
0x180007dc8  add     rsp, 20h
0x180007dcc  pop     rbx
0x180007dcd  retn
```
