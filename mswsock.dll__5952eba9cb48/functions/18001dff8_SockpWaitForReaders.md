# SockpWaitForReaders

- ea: `0x18001dff8`
- end: `0x18001e0d8`
- name: `SockpWaitForReaders`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000db30`

## callees

- `0x18001dff8`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18001e0bb`
- `ntdll!RtlRaiseStatus` at `0x18001e0bb`
- `ntdll!NtDelayExecution` at `0x18001e011`
- `ntdll!NtDelayExecution` at `0x18001e072`
- `ntdll!NtDelayExecution` at `0x18001e011`
- `ntdll!NtDelayExecution` at `0x18001e072`
- `ntdll!NtWaitForSingleObject` at `0x18001e0a9`
- `ntdll!NtWaitForSingleObject` at `0x18001e0a9`
- `ntdll!NtCreateEvent` at `0x18001e050`
- `ntdll!NtCreateEvent` at `0x18001e050`

## pseudocode

```c
int SockpWaitForReaders()
{
  int result; // eax
  LARGE_INTEGER Interval; // [rsp+40h] [rbp+8h] BYREF
  LARGE_INTEGER v2; // [rsp+48h] [rbp+10h] BYREF

  Interval.QuadPart = 0;
  NtDelayExecution(0, &Interval);
  result = SocketGlobalLock;
  if ( SocketGlobalLock != -2 )
  {
    if ( !Handle && NtCreateEvent(&Handle, 0x1F0003u, 0, SynchronizationEvent, 0) < 0 )
    {
      v2.QuadPart = -100000;
      while ( SocketGlobalLock != -2 )
        NtDelayExecution(0, &v2);
    }
    result = _InterlockedIncrement(&SocketGlobalLock);
    if ( result != -1 )
    {
      result = NtWaitForSingleObject(Handle, 0, 0);
      if ( result < 0 )
        RtlRaiseStatus(result);
    }
    SocketGlobalLock = -2;
  }
  return result;
}

```

## disassembly

```asm
0x18001dff8  mov     qword ptr [rsp+Interval], rcx
0x18001dffd  sub     rsp, 38h
0x18001e001  lea     rdx, [rsp+38h+Interval]; Interval
0x18001e006  mov     qword ptr [rsp+38h+Interval], 0
0x18001e00f  xor     ecx, ecx; Alertable
0x18001e011  call    cs:__imp_NtDelayExecution
0x18001e018  nop     dword ptr [rax+rax+00h]
0x18001e01d  mov     eax, cs:SocketGlobalLock
0x18001e023  cmp     eax, 0FFFFFFFEh
0x18001e026  jz      loc_18001E0D2
0x18001e02c  cmp     cs:Handle, 0
0x18001e034  jnz     short loc_18001E089
0x18001e036  mov     r9d, 1; EventType
0x18001e03c  mov     [rsp+38h+InitialState], 0; InitialState
0x18001e041  xor     r8d, r8d; ObjectAttributes
0x18001e044  lea     rcx, Handle; EventHandle
0x18001e04b  mov     edx, 1F0003h; DesiredAccess
0x18001e050  call    cs:__imp_NtCreateEvent
0x18001e057  nop     dword ptr [rax+rax+00h]
0x18001e05c  test    eax, eax
0x18001e05e  jns     short loc_18001E089
0x18001e060  mov     qword ptr [rsp+38h+arg_8], 0FFFFFFFFFFFE7960h
0x18001e069  jmp     short loc_18001E07E
0x18001e06b  lea     rdx, [rsp+38h+arg_8]; Interval
0x18001e070  xor     ecx, ecx; Alertable
0x18001e072  call    cs:__imp_NtDelayExecution
0x18001e079  nop     dword ptr [rax+rax+00h]
0x18001e07e  mov     eax, cs:SocketGlobalLock
0x18001e084  cmp     eax, 0FFFFFFFEh
0x18001e087  jnz     short loc_18001E06B
0x18001e089  mov     eax, 1
0x18001e08e  lock xadd cs:SocketGlobalLock, eax
0x18001e096  inc     eax
0x18001e098  cmp     eax, 0FFFFFFFFh
0x18001e09b  jz      short loc_18001E0C8
0x18001e09d  mov     rcx, cs:Handle; Handle
0x18001e0a4  xor     r8d, r8d; Timeout
0x18001e0a7  xor     edx, edx; Alertable
0x18001e0a9  call    cs:__imp_NtWaitForSingleObject
0x18001e0b0  nop     dword ptr [rax+rax+00h]
0x18001e0b5  test    eax, eax
0x18001e0b7  jns     short loc_18001E0C8
0x18001e0b9  mov     ecx, eax; Status
0x18001e0bb  call    cs:__imp_RtlRaiseStatus
0x18001e0c2  nop     dword ptr [rax+rax+00h]
0x18001e0c7  int     3; Trap to Debugger
0x18001e0c8  mov     cs:SocketGlobalLock, 0FFFFFFFEh
0x18001e0d2  add     rsp, 38h
0x18001e0d6  retn
```
